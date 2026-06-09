# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1400064f0`
- end: `0x140006557`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `103`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400064f0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006537`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006537`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006520`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006520`

## string_xrefs

- `0x140006519`: `ntdll.dll`

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
0x1400064f0  push    rbx
0x1400064f2  sub     rsp, 30h
0x1400064f6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400064ff  mov     ebx, ecx
0x140006501  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x140006508  test    rax, rax
0x14000650b  jnz     short loc_140006549
0x14000650d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006514  test    rax, rax
0x140006517  jnz     short loc_14000652D
0x140006519  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140006520  call    cs:__imp_GetModuleHandleW
0x140006526  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000652d  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x140006534  mov     rcx, rax; hModule
0x140006537  call    cs:__imp_GetProcAddress
0x14000653d  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x140006544  test    rax, rax
0x140006547  jz      short loc_140006551
0x140006549  mov     ecx, ebx
0x14000654b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006550  nop
0x140006551  add     rsp, 30h
0x140006555  pop     rbx
0x140006556  retn
```
