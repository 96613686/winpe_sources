# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000ae70`
- end: `0x18000aece`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ae70`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aeae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aeae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae97`

## string_xrefs

- `0x18000ae90`: `ntdll.dll`

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
0x18000ae70  push    rbx
0x18000ae72  sub     rsp, 20h
0x18000ae76  mov     ebx, ecx
0x18000ae78  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000ae7f  test    rax, rax
0x18000ae82  jnz     short loc_18000AEC0
0x18000ae84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ae8b  test    rax, rax
0x18000ae8e  jnz     short loc_18000AEA4
0x18000ae90  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ae97  call    cs:__imp_GetModuleHandleW
0x18000ae9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aea4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000aeab  mov     rcx, rax; hModule
0x18000aeae  call    cs:__imp_GetProcAddress
0x18000aeb4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000aebb  test    rax, rax
0x18000aebe  jz      short loc_18000AEC8
0x18000aec0  mov     ecx, ebx
0x18000aec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec7  nop
0x18000aec8  add     rsp, 20h
0x18000aecc  pop     rbx
0x18000aecd  retn
```
