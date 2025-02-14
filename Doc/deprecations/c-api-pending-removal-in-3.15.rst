Pending removal in Python 3.15
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* The bundled copy of ``libmpdecimal``.
* The :c:func:`PyImport_ImportModuleNoBlock`:
  Use :c:func:`PyImport_ImportModule` instead.
* :c:func:`PyWeakref_GetObject` and :c:func:`PyWeakref_GET_OBJECT`:
  Use :c:func:`PyWeakref_GetRef` instead.
* :c:type:`Py_UNICODE` type and the :c:macro:`!Py_UNICODE_WIDE` macro:
  Use :c:type:`wchar_t` instead.
* Python initialization functions:

  * :c:func:`PySys_ResetWarnOptions`:
    Clear :data:`sys.warnoptions` and :data:`!warnings.filters` instead.
  * :c:func:`Py_GetExecPrefix`:
    Get :data:`sys.base_exec_prefix` and :data:`sys.exec_prefix` instead.
  * :c:func:`Py_GetPath`:
    Get :data:`sys.path` instead.
  * :c:func:`Py_GetPrefix`:
    Get :data:`sys.base_prefix` and :data:`sys.prefix` instead.
  * :c:func:`Py_GetProgramFullPath`:
    Get :data:`sys.executable` instead.
  * :c:func:`Py_GetProgramName`:
    Get :data:`sys.executable` instead.
  * :c:func:`Py_GetPythonHome`:
    Get :c:member:`PyConfig.home`
    or the :envvar:`PYTHONHOME` environment variable instead.

* Functions to configure Python's initialization, deprecated in Python 3.11:

  * :c:func:`!PySys_SetArgvEx()`:
    Set :c:member:`PyConfig.argv` instead.
  * :c:func:`!PySys_SetArgv()`:
    Set :c:member:`PyConfig.argv` instead.
  * :c:func:`!Py_SetProgramName()`:
    Set :c:member:`PyConfig.program_name` instead.
  * :c:func:`!Py_SetPythonHome()`:
    Set :c:member:`PyConfig.home` instead.

  The :c:func:`Py_InitializeFromConfig` API should be used with
  :c:type:`PyConfig` instead.

* Global configuration variables:

  * :c:var:`Py_DebugFlag`:
    Use :c:member:`PyConfig.parser_debug` or
    :c:func:`PyConfig_Get("parser_debug") <PyConfig_Get>` instead.
  * :c:var:`Py_VerboseFlag`:
    Use :c:member:`PyConfig.verbose` or
    :c:func:`PyConfig_Get("verbose") <PyConfig_Get>` instead.
  * :c:var:`Py_QuietFlag`:
    Use :c:member:`PyConfig.quiet` or
    :c:func:`PyConfig_Get("quiet") <PyConfig_Get>` instead.
  * :c:var:`Py_InteractiveFlag`:
    Use :c:member:`PyConfig.interactive` or
    :c:func:`PyConfig_Get("interactive") <PyConfig_Get>` instead.
  * :c:var:`Py_InspectFlag`:
    Use :c:member:`PyConfig.inspect` or
    :c:func:`PyConfig_Get("inspect") <PyConfig_Get>` instead.
  * :c:var:`Py_OptimizeFlag`:
    Use :c:member:`PyConfig.optimization_level` or
    :c:func:`PyConfig_Get("optimization_level") <PyConfig_Get>` instead.
  * :c:var:`Py_NoSiteFlag`:
    Use :c:member:`PyConfig.site_import` or
    :c:func:`PyConfig_Get("site_import") <PyConfig_Get>` instead.
  * :c:var:`Py_BytesWarningFlag`:
    Use :c:member:`PyConfig.bytes_warning` or
    :c:func:`PyConfig_Get("bytes_warning") <PyConfig_Get>` instead.
  * :c:var:`Py_FrozenFlag`:
    Use :c:member:`PyConfig.pathconfig_warnings` or
    :c:func:`PyConfig_Get("pathconfig_warnings") <PyConfig_Get>` instead.
  * :c:var:`Py_IgnoreEnvironmentFlag`:
    Use :c:member:`PyConfig.use_environment` or
    :c:func:`PyConfig_Get("use_environment") <PyConfig_Get>` instead.
  * :c:var:`Py_DontWriteBytecodeFlag`:
    Use :c:member:`PyConfig.write_bytecode` or
    :c:func:`PyConfig_Get("write_bytecode") <PyConfig_Get>` instead.
  * :c:var:`Py_NoUserSiteDirectory`:
    Use :c:member:`PyConfig.user_site_directory` or
    :c:func:`PyConfig_Get("user_site_directory") <PyConfig_Get>` instead.
  * :c:var:`Py_UnbufferedStdioFlag`:
    Use :c:member:`PyConfig.buffered_stdio` or
    :c:func:`PyConfig_Get("buffered_stdio") <PyConfig_Get>` instead.
  * :c:var:`Py_HashRandomizationFlag`:
    Use :c:member:`PyConfig.use_hash_seed`
    and :c:member:`PyConfig.hash_seed` or
    :c:func:`PyConfig_Get("hash_seed") <PyConfig_Get>` instead.
  * :c:var:`Py_IsolatedFlag`:
    Use :c:member:`PyConfig.isolated` or
    :c:func:`PyConfig_Get("isolated") <PyConfig_Get>` instead.
  * :c:var:`Py_LegacyWindowsFSEncodingFlag`:
    Use :c:member:`PyPreConfig.legacy_windows_fs_encoding` or
    :c:func:`PyConfig_Get("legacy_windows_fs_encoding") <PyConfig_Get>` instead.
  * :c:var:`Py_LegacyWindowsStdioFlag`:
    Use :c:member:`PyConfig.legacy_windows_stdio` or
    :c:func:`PyConfig_Get("legacy_windows_stdio") <PyConfig_Get>` instead.
  * :c:var:`!Py_FileSystemDefaultEncoding`, :c:var:`!Py_HasFileSystemDefaultEncoding`:
    Use :c:member:`PyConfig.filesystem_encoding` or
    :c:func:`PyConfig_Get("filesystem_encoding") <PyConfig_Get>` instead.
  * :c:var:`!Py_FileSystemDefaultEncodeErrors`:
    Use :c:member:`PyConfig.filesystem_errors` or
    :c:func:`PyConfig_Get("filesystem_errors") <PyConfig_Get>` instead.
  * :c:var:`!Py_UTF8Mode`:
    Use :c:member:`PyPreConfig.utf8_mode` or
    :c:func:`PyConfig_Get("utf8_mode") <PyConfig_Get>` instead.
    (see :c:func:`Py_PreInitialize`)

  The :c:func:`Py_InitializeFromConfig` API should be used with
  :c:type:`PyConfig` to set these options. Or :c:func:`PyConfig_Get` can be
  used to get these options at runtime.
