# Jot::CSharedMemory::CreateImpl(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,int,ulong,bool *,bool)

- ea: `0x1400427fc`
- end: `0x140042a31`
- name: `?CreateImpl@CSharedMemory@Jot@@IEAA?AW4ErrorType@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0HKPEA_N_N@Z`
- size: `565`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140042dd4`

## callees

- `0x1400427fc`
- `0x140042a40`
- `0x1400478b0`
- `0x1401a9be8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400428c8`
- `KERNEL32!GetLastError` at `0x1400428c8`
- `KERNEL32!CloseHandle` at `0x1400428ef`
- `KERNEL32!CloseHandle` at `0x140042957`
- `KERNEL32!CloseHandle` at `0x14004296f`
- `KERNEL32!CloseHandle` at `0x140042a16`
- `KERNEL32!CloseHandle` at `0x1400428ef`
- `KERNEL32!CloseHandle` at `0x140042957`
- `KERNEL32!CloseHandle` at `0x14004296f`
- `KERNEL32!CloseHandle` at `0x140042a16`
- `KERNEL32!WaitForSingleObjectEx` at `0x14004287e`
- `KERNEL32!WaitForSingleObjectEx` at `0x14004287e`
- `KERNEL32!CreateFileMappingW` at `0x1400428b6`
- `KERNEL32!CreateFileMappingW` at `0x1400428b6`
- `KERNEL32!OutputDebugStringW` at `0x1400429c6`
- `KERNEL32!OutputDebugStringW` at `0x1400429fa`
- `KERNEL32!OutputDebugStringW` at `0x1400429c6`
- `KERNEL32!OutputDebugStringW` at `0x1400429fa`
- `KERNEL32!MapViewOfFile` at `0x14004293b`
- `KERNEL32!MapViewOfFile` at `0x14004293b`
- `KERNEL32!ReleaseMutex` at `0x1400429cf`
- `KERNEL32!ReleaseMutex` at `0x1400429cf`
- `KERNEL32!CreateMutexExW` at `0x140042843`
- `KERNEL32!CreateMutexExW` at `0x140042843`

## pseudocode

```c

```
