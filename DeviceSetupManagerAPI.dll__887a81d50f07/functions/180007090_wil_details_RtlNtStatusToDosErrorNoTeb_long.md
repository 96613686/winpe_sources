# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007090`
- end: `0x1800070ee`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007090`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800070ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800070ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800070b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800070b7`

## string_xrefs

- `0x1800070b0`: `ntdll.dll`

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
0x180007090  push    rbx
0x180007092  sub     rsp, 20h
0x180007096  mov     ebx, ecx
0x180007098  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000709f  test    rax, rax
0x1800070a2  jnz     short loc_1800070E0
0x1800070a4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800070ab  test    rax, rax
0x1800070ae  jnz     short loc_1800070C4
0x1800070b0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800070b7  call    cs:__imp_GetModuleHandleW
0x1800070bd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800070c4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800070cb  mov     rcx, rax; hModule
0x1800070ce  call    cs:__imp_GetProcAddress
0x1800070d4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800070db  test    rax, rax
0x1800070de  jz      short loc_1800070E8
0x1800070e0  mov     ecx, ebx
0x1800070e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070e7  nop
0x1800070e8  add     rsp, 20h
0x1800070ec  pop     rbx
0x1800070ed  retn
```
