# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180018240`
- end: `0x18001829e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180018240`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001827e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001827e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018267`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018267`

## string_xrefs

- `0x180018260`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // ebx
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  return result;
}

```

## disassembly

```asm
0x180018240  push    rbx
0x180018242  sub     rsp, 20h
0x180018246  mov     ebx, ecx
0x180018248  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18001824f  test    rax, rax
0x180018252  jnz     short loc_180018290
0x180018254  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001825b  test    rax, rax
0x18001825e  jnz     short loc_180018274
0x180018260  lea     rcx, ModuleName; "ntdll.dll"
0x180018267  call    cs:__imp_GetModuleHandleW
0x18001826d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018274  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18001827b  mov     rcx, rax; hModule
0x18001827e  call    cs:__imp_GetProcAddress
0x180018284  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18001828b  test    rax, rax
0x18001828e  jz      short loc_180018298
0x180018290  mov     ecx, ebx
0x180018292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018297  nop
0x180018298  add     rsp, 20h
0x18001829c  pop     rbx
0x18001829d  retn
```
