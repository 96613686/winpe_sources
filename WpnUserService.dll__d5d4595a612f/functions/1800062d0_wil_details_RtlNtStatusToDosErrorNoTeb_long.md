# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800062d0`
- end: `0x18000632e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800062d0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000630e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000630e`

## string_xrefs

- `0x1800062f0`: `ntdll.dll`

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
0x1800062d0  push    rbx
0x1800062d2  sub     rsp, 20h
0x1800062d6  mov     ebx, ecx
0x1800062d8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800062df  test    rax, rax
0x1800062e2  jnz     short loc_180006320
0x1800062e4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800062eb  test    rax, rax
0x1800062ee  jnz     short loc_180006304
0x1800062f0  lea     rcx, ModuleName; "ntdll.dll"
0x1800062f7  call    cs:__imp_GetModuleHandleW
0x1800062fd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006304  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000630b  mov     rcx, rax; hModule
0x18000630e  call    cs:__imp_GetProcAddress
0x180006314  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000631b  test    rax, rax
0x18000631e  jz      short loc_180006328
0x180006320  mov     ecx, ebx
0x180006322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006327  nop
0x180006328  add     rsp, 20h
0x18000632c  pop     rbx
0x18000632d  retn
```
