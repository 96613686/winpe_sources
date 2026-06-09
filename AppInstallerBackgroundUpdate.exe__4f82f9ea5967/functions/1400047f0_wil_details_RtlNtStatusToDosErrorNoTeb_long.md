# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1400047f0`
- end: `0x14000484e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400047f0`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004817`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004817`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000482e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000482e`

## string_xrefs

- `0x140004810`: `ntdll.dll`

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
0x1400047f0  push    rbx
0x1400047f2  sub     rsp, 20h
0x1400047f6  mov     ebx, ecx
0x1400047f8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1400047ff  test    rax, rax
0x140004802  jnz     short loc_140004840
0x140004804  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000480b  test    rax, rax
0x14000480e  jnz     short loc_140004824
0x140004810  lea     rcx, ModuleName; "ntdll.dll"
0x140004817  call    cs:__imp_GetModuleHandleW
0x14000481d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004824  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000482b  mov     rcx, rax; hModule
0x14000482e  call    cs:__imp_GetProcAddress
0x140004834  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000483b  test    rax, rax
0x14000483e  jz      short loc_140004848
0x140004840  mov     ecx, ebx
0x140004842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004847  nop
0x140004848  add     rsp, 20h
0x14000484c  pop     rbx
0x14000484d  retn
```
