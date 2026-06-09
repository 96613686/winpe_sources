# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006aa0`
- end: `0x180006afe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006aa0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ade`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ade`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ac7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ac7`

## string_xrefs

- `0x180006ac0`: `ntdll.dll`

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
0x180006aa0  push    rbx
0x180006aa2  sub     rsp, 20h
0x180006aa6  mov     ebx, ecx
0x180006aa8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180006aaf  test    rax, rax
0x180006ab2  jnz     short loc_180006AF0
0x180006ab4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006abb  test    rax, rax
0x180006abe  jnz     short loc_180006AD4
0x180006ac0  lea     rcx, ModuleName; "ntdll.dll"
0x180006ac7  call    cs:__imp_GetModuleHandleW
0x180006acd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006ad4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180006adb  mov     rcx, rax; hModule
0x180006ade  call    cs:__imp_GetProcAddress
0x180006ae4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180006aeb  test    rax, rax
0x180006aee  jz      short loc_180006AF8
0x180006af0  mov     ecx, ebx
0x180006af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006af7  nop
0x180006af8  add     rsp, 20h
0x180006afc  pop     rbx
0x180006afd  retn
```
