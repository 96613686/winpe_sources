# GameInputModule::GetModulePath(HINSTANCE__ *,unsigned __int64,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)

- ea: `0x18002c3b4`
- end: `0x18002c4d1`
- name: `?GetModulePath@GameInputModule@@CAJPEAUHINSTANCE__@@_KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z`
- size: `285`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002ca98`

## callees

- `0x18000c11c`
- `0x18002c3b4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002c414`
- `ntdll!RtlAllocateHeap` at `0x18002c414`
- `ntdll!towlower` at `0x18002c493`
- `ntdll!towlower` at `0x18002c493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c44d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c44d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002c43b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002c43b`

## pseudocode

```c

```
