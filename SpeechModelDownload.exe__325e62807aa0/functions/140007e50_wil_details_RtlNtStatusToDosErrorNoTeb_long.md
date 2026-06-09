# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140007e50`
- end: `0x140007eae`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140007e50`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007e77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007e77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e8e`

## string_xrefs

- `0x140007e70`: `ntdll.dll`

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
0x140007e50  push    rbx
0x140007e52  sub     rsp, 20h
0x140007e56  mov     ebx, ecx
0x140007e58  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x140007e5f  test    rax, rax
0x140007e62  jnz     short loc_140007EA0
0x140007e64  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007e6b  test    rax, rax
0x140007e6e  jnz     short loc_140007E84
0x140007e70  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140007e77  call    cs:__imp_GetModuleHandleW
0x140007e7d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007e84  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x140007e8b  mov     rcx, rax; hModule
0x140007e8e  call    cs:__imp_GetProcAddress
0x140007e94  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x140007e9b  test    rax, rax
0x140007e9e  jz      short loc_140007EA8
0x140007ea0  mov     ecx, ebx
0x140007ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ea7  nop
0x140007ea8  add     rsp, 20h
0x140007eac  pop     rbx
0x140007ead  retn
```
