# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800095d0`
- end: `0x18000962e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800095d0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000960e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000960e`

## string_xrefs

- `0x1800095f0`: `ntdll.dll`

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
0x1800095d0  push    rbx
0x1800095d2  sub     rsp, 20h
0x1800095d6  mov     ebx, ecx
0x1800095d8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800095df  test    rax, rax
0x1800095e2  jnz     short loc_180009620
0x1800095e4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800095eb  test    rax, rax
0x1800095ee  jnz     short loc_180009604
0x1800095f0  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800095f7  call    cs:__imp_GetModuleHandleW
0x1800095fd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009604  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000960b  mov     rcx, rax; hModule
0x18000960e  call    cs:__imp_GetProcAddress
0x180009614  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000961b  test    rax, rax
0x18000961e  jz      short loc_180009628
0x180009620  mov     ecx, ebx
0x180009622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009627  nop
0x180009628  add     rsp, 20h
0x18000962c  pop     rbx
0x18000962d  retn
```
