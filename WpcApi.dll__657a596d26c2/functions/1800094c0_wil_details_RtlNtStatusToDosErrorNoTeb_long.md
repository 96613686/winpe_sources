# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800094c0`
- end: `0x18000951e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800094c0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800094e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800094e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800094fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800094fe`

## string_xrefs

- `0x1800094e0`: `ntdll.dll`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x1800094c0  push    rbx
0x1800094c2  sub     rsp, 20h
0x1800094c6  mov     ebx, ecx
0x1800094c8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800094cf  test    rax, rax
0x1800094d2  jnz     short loc_180009510
0x1800094d4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800094db  test    rax, rax
0x1800094de  jnz     short loc_1800094F4
0x1800094e0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800094e7  call    cs:__imp_GetModuleHandleW
0x1800094ed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800094f4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800094fb  mov     rcx, rax; hModule
0x1800094fe  call    cs:__imp_GetProcAddress
0x180009504  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000950b  test    rax, rax
0x18000950e  jz      short loc_180009518
0x180009510  mov     ecx, ebx
0x180009512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009517  nop
0x180009518  add     rsp, 20h
0x18000951c  pop     rbx
0x18000951d  retn
```
