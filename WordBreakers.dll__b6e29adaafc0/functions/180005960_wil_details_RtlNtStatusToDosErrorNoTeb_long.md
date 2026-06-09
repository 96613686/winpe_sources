# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180005960`
- end: `0x1800059be`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005960`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000599e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000599e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005987`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005987`

## string_xrefs

- `0x180005980`: `ntdll.dll`

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
0x180005960  push    rbx
0x180005962  sub     rsp, 20h
0x180005966  mov     ebx, ecx
0x180005968  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000596f  test    rax, rax
0x180005972  jnz     short loc_1800059B0
0x180005974  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000597b  test    rax, rax
0x18000597e  jnz     short loc_180005994
0x180005980  lea     rcx, ModuleName; "ntdll.dll"
0x180005987  call    cs:__imp_GetModuleHandleW
0x18000598d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005994  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000599b  mov     rcx, rax; hModule
0x18000599e  call    cs:__imp_GetProcAddress
0x1800059a4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800059ab  test    rax, rax
0x1800059ae  jz      short loc_1800059B8
0x1800059b0  mov     ecx, ebx
0x1800059b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b7  nop
0x1800059b8  add     rsp, 20h
0x1800059bc  pop     rbx
0x1800059bd  retn
```
