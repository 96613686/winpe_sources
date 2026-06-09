# Disco::Durable::FileSystem::EnumerateDirectoryTreeInternalW(uint,wchar_t const *,bool,Mso::Functor<void (wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)> &&)

- ea: `0x1800f341c`
- end: `0x1800f3883`
- name: `?EnumerateDirectoryTreeInternalW@FileSystem@Durable@Disco@@AEAAKIPEB_W_N$$QEAV?$Functor@$$A6AXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z@Mso@@@Z`
- size: `1127`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x1800f33c0`
- `0x1800f4460`

## callees

- `0x180012aa0`
- `0x180013080`
- `0x1800843d8`
- `0x180086814`
- `0x1800dd9bc`
- `0x1800de750`
- `0x1800ee530`
- `0x1800effd8`
- `0x1800f0020`
- `0x1800f1528`
- `0x1800f1780`
- `0x1800f2834`
- `0x1800f341c`
- `0x1800f3890`
- `0x1800f8f84`
- `0x18056bd00`
- `0x18056d14c`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800f3588`
- `KERNEL32!SetLastError` at `0x1800f3588`
- `KERNEL32!GetLastError` at `0x1800f35d5`
- `KERNEL32!GetLastError` at `0x1800f35d5`
- `KERNEL32!FindFirstFileExW` at `0x1800f35c6`
- `KERNEL32!FindFirstFileExW` at `0x1800f35c6`
- `KERNEL32!FindNextFileW` at `0x1800f36ef`
- `KERNEL32!FindNextFileW` at `0x1800f36ef`
- `KERNEL32!FindClose` at `0x1800f3700`
- `KERNEL32!FindClose` at `0x1800f3700`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1800f3483`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1800f3483`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800f3475`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800f3475`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f3854`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f3854`

## string_xrefs

- `0x1800f3772`: `File not found / path not found when enumerating. Continuing`

## pseudocode

```c

```
