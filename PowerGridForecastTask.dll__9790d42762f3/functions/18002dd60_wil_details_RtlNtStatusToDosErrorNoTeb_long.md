# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18002dd60`
- end: `0x18002ddbe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002dd60`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dd9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dd9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dd87`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dd87`

## string_xrefs

- `0x18002dd80`: `ntdll.dll`

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
0x18002dd60  push    rbx
0x18002dd62  sub     rsp, 20h
0x18002dd66  mov     ebx, ecx
0x18002dd68  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18002dd6f  test    rax, rax
0x18002dd72  jnz     short loc_18002DDB0
0x18002dd74  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002dd7b  test    rax, rax
0x18002dd7e  jnz     short loc_18002DD94
0x18002dd80  lea     rcx, ModuleName; "ntdll.dll"
0x18002dd87  call    cs:__imp_GetModuleHandleW
0x18002dd8d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002dd94  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18002dd9b  mov     rcx, rax; hModule
0x18002dd9e  call    cs:__imp_GetProcAddress
0x18002dda4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18002ddab  test    rax, rax
0x18002ddae  jz      short loc_18002DDB8
0x18002ddb0  mov     ecx, ebx
0x18002ddb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddb7  nop
0x18002ddb8  add     rsp, 20h
0x18002ddbc  pop     rbx
0x18002ddbd  retn
```
