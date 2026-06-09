# GetCacheTimeStampsFromHeaders(CHttpHeaderParser *,uchar const *,_FILETIME *,_FILETIME *,int *,int *,int *)

- ea: `0x18006751c`
- end: `0x18006815b`
- name: `?GetCacheTimeStampsFromHeaders@@YAXPEAVCHttpHeaderParser@@PEBEPEAU_FILETIME@@2PEAH33@Z`
- size: `3135`
- prototype: `void __usercall(struct CHttpHeaderParser *this@<rcx>, const unsigned __int8 *@<rdx>, struct _FILETIME *@<r8>, struct _FILETIME *@<r9>, int *, int *, int *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180033a3c`
- `0x1800c9f5c`
- `0x1801942c8`

## callees

- `0x180009cf0`
- `0x18002d9a0`
- `0x18006751c`
- `0x180068170`
- `0x180107c90`
- `0x180114068`
- `0x18014a7a0`
- `0x18014a7e0`
- `0x1801e285c`
- `0x1801e2c8c`
- `0x1801e3c78`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180067ac5`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180067ac5`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180067ad2`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180067ad2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006790a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180067be8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180067c4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180067f0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180067faf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800680f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180068117`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006790a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180067be8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180067c4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180067f0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180067faf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800680f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180068117`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180067bd6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180067ce3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180067bd6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180067ce3`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x18006779f`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x1800677db`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x1800679c7`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x18006779f`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x1800677db`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x1800679c7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180067827`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180067845`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180067863`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180067881`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18006789f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800678bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800678db`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180067827`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180067845`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180067863`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180067881`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18006789f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800678bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800678db`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeA` at `0x180067bc4`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeA` at `0x180067ccd`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeA` at `0x180067bc4`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeA` at `0x180067ccd`

## string_xrefs

- `0x1800678d1`: `no-cache`

## pseudocode

```c

```
