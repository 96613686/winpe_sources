# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180010c10`
- end: `0x180010c6e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180010c10`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010c37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010c37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010c4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010c4e`

## string_xrefs

- `0x180010c30`: `ntdll.dll`

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
0x180010c10  push    rbx
0x180010c12  sub     rsp, 20h
0x180010c16  mov     ebx, ecx
0x180010c18  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180010c1f  test    rax, rax
0x180010c22  jnz     short loc_180010C60
0x180010c24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010c2b  test    rax, rax
0x180010c2e  jnz     short loc_180010C44
0x180010c30  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010c37  call    cs:__imp_GetModuleHandleW
0x180010c3d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010c44  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180010c4b  mov     rcx, rax; hModule
0x180010c4e  call    cs:__imp_GetProcAddress
0x180010c54  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180010c5b  test    rax, rax
0x180010c5e  jz      short loc_180010C68
0x180010c60  mov     ecx, ebx
0x180010c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c67  nop
0x180010c68  add     rsp, 20h
0x180010c6c  pop     rbx
0x180010c6d  retn
```
