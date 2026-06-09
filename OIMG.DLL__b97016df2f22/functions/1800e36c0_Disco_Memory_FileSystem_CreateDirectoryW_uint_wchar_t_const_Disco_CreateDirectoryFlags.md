# Disco::Memory::FileSystem::CreateDirectoryW(uint,wchar_t const *,Disco::CreateDirectoryFlags)

- ea: `0x1800e36c0`
- end: `0x1800e3d70`
- name: `?CreateDirectoryW@FileSystem@Memory@Disco@@UEAAKIPEB_WW4CreateDirectoryFlags@3@@Z`
- size: `1712`
- prototype: `unsigned int __high(unsigned int, const wchar_t *, enum Disco::CreateDirectoryFlags)`
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x1800deb5c`

## callees

- `0x1800124f0`
- `0x180012aa0`
- `0x180012e20`
- `0x180013018`
- `0x1800175c8`
- `0x180018860`
- `0x180018cd4`
- `0x180023670`
- `0x1800236f0`
- `0x180084290`
- `0x1800862d0`
- `0x1800dd9bc`
- `0x1800de4f0`
- `0x1800de750`
- `0x1800e36c0`
- `0x1800e71e0`
- `0x1800ec6f4`
- `0x1800ed0b8`
- `0x1800eff58`
- `0x1800f0020`
- `0x1800f1528`
- `0x1800f1780`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800e370e`
- `KERNEL32!SetLastError` at `0x1800e370e`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1800e3b30`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1800e3b30`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800e3a74`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800e3b22`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800e3a74`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800e3b22`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e3bc6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e3cdd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e3bc6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e3cdd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800e39aa`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800e3a68`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800e3cd6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800e39aa`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800e3a68`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800e3cd6`

## string_xrefs

- `0x1800e37b2`: `Creating directory failed as it already exists`
- `0x1800e396d`: `Subpath`
- `0x1800e3a02`: `Cannot create path as subpath under it does not exist`
- `0x1800e3c60`: `Created directory`

## pseudocode

```c

```
