# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800062a0`
- end: `0x1800062fe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800062a0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062c7`

## string_xrefs

- `0x1800062c0`: `ntdll.dll`

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
0x1800062a0  push    rbx
0x1800062a2  sub     rsp, 20h
0x1800062a6  mov     ebx, ecx
0x1800062a8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800062af  test    rax, rax
0x1800062b2  jnz     short loc_1800062F0
0x1800062b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800062bb  test    rax, rax
0x1800062be  jnz     short loc_1800062D4
0x1800062c0  lea     rcx, ModuleName; "ntdll.dll"
0x1800062c7  call    cs:__imp_GetModuleHandleW
0x1800062cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800062d4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800062db  mov     rcx, rax; hModule
0x1800062de  call    cs:__imp_GetProcAddress
0x1800062e4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800062eb  test    rax, rax
0x1800062ee  jz      short loc_1800062F8
0x1800062f0  mov     ecx, ebx
0x1800062f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f7  nop
0x1800062f8  add     rsp, 20h
0x1800062fc  pop     rbx
0x1800062fd  retn
```
