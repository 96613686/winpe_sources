# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800055b0`
- end: `0x18000560e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800055b0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055ee`

## string_xrefs

- `0x1800055d0`: `ntdll.dll`

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
0x1800055b0  push    rbx
0x1800055b2  sub     rsp, 20h
0x1800055b6  mov     ebx, ecx
0x1800055b8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800055bf  test    rax, rax
0x1800055c2  jnz     short loc_180005600
0x1800055c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800055cb  test    rax, rax
0x1800055ce  jnz     short loc_1800055E4
0x1800055d0  lea     rcx, ModuleName; "ntdll.dll"
0x1800055d7  call    cs:__imp_GetModuleHandleW
0x1800055dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800055e4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800055eb  mov     rcx, rax; hModule
0x1800055ee  call    cs:__imp_GetProcAddress
0x1800055f4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800055fb  test    rax, rax
0x1800055fe  jz      short loc_180005608
0x180005600  mov     ecx, ebx
0x180005602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005607  nop
0x180005608  add     rsp, 20h
0x18000560c  pop     rbx
0x18000560d  retn
```
