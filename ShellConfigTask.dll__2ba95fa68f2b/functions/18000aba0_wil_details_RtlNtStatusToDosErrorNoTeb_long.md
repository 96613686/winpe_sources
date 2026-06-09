# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000aba0`
- end: `0x18000abfe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000aba0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000abc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000abc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000abde`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000abde`

## string_xrefs

- `0x18000abc0`: `ntdll.dll`

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
0x18000aba0  push    rbx
0x18000aba2  sub     rsp, 20h
0x18000aba6  mov     ebx, ecx
0x18000aba8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000abaf  test    rax, rax
0x18000abb2  jnz     short loc_18000ABF0
0x18000abb4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000abbb  test    rax, rax
0x18000abbe  jnz     short loc_18000ABD4
0x18000abc0  lea     rcx, ModuleName; "ntdll.dll"
0x18000abc7  call    cs:__imp_GetModuleHandleW
0x18000abcd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000abd4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000abdb  mov     rcx, rax; hModule
0x18000abde  call    cs:__imp_GetProcAddress
0x18000abe4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000abeb  test    rax, rax
0x18000abee  jz      short loc_18000ABF8
0x18000abf0  mov     ecx, ebx
0x18000abf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abf7  nop
0x18000abf8  add     rsp, 20h
0x18000abfc  pop     rbx
0x18000abfd  retn
```
