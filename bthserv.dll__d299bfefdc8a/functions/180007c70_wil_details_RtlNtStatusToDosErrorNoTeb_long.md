# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007c70`
- end: `0x180007cce`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007c70`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cae`

## string_xrefs

- `0x180007c90`: `ntdll.dll`

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
0x180007c70  push    rbx
0x180007c72  sub     rsp, 20h
0x180007c76  mov     ebx, ecx
0x180007c78  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180007c7f  test    rax, rax
0x180007c82  jnz     short loc_180007CC0
0x180007c84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007c8b  test    rax, rax
0x180007c8e  jnz     short loc_180007CA4
0x180007c90  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180007c97  call    cs:__imp_GetModuleHandleW
0x180007c9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007ca4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180007cab  mov     rcx, rax; hModule
0x180007cae  call    cs:__imp_GetProcAddress
0x180007cb4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180007cbb  test    rax, rax
0x180007cbe  jz      short loc_180007CC8
0x180007cc0  mov     ecx, ebx
0x180007cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc7  nop
0x180007cc8  add     rsp, 20h
0x180007ccc  pop     rbx
0x180007ccd  retn
```
