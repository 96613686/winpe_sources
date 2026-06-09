# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180010800`
- end: `0x18001086b`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180010800`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010827`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010827`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010844`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010844`

## string_xrefs

- `0x180010820`: `ntdll.dll`

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
0x180010800  push    rbx
0x180010802  sub     rsp, 20h
0x180010806  mov     ebx, ecx
0x180010808  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18001080f  test    rax, rax
0x180010812  jnz     short loc_18001085C
0x180010814  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001081b  test    rax, rax
0x18001081e  jnz     short loc_18001083A
0x180010820  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010827  call    cs:__imp_GetModuleHandleW
0x18001082e  nop     dword ptr [rax+rax+00h]
0x180010833  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001083a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180010841  mov     rcx, rax; hModule
0x180010844  call    cs:__imp_GetProcAddress
0x18001084b  nop     dword ptr [rax+rax+00h]
0x180010850  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180010857  test    rax, rax
0x18001085a  jz      short loc_180010864
0x18001085c  mov     ecx, ebx
0x18001085e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010863  nop
0x180010864  add     rsp, 20h
0x180010868  pop     rbx
0x180010869  retn
```
