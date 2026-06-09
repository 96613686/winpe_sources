# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140004d70`
- end: `0x140004dd2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004d70`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004dae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004dae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004d97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004d97`

## string_xrefs

- `0x140004d90`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC result; // rax
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  return result;
}

```

## disassembly

```asm
0x140004d70  push    rbx
0x140004d72  sub     rsp, 20h
0x140004d76  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x140004d7d  mov     ebx, ecx
0x140004d7f  test    rax, rax
0x140004d82  jnz     short loc_140004DC6
0x140004d84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004d8b  test    rax, rax
0x140004d8e  jnz     short loc_140004DA4
0x140004d90  lea     rcx, ModuleName; "ntdll.dll"
0x140004d97  call    cs:__imp_GetModuleHandleW
0x140004d9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004da4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x140004dab  mov     rcx, rax; hModule
0x140004dae  call    cs:__imp_GetProcAddress
0x140004db4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x140004dbb  test    rax, rax
0x140004dbe  jnz     short loc_140004DC6
0x140004dc0  add     rsp, 20h
0x140004dc4  pop     rbx
0x140004dc5  retn
0x140004dc6  mov     ecx, ebx
0x140004dc8  add     rsp, 20h
0x140004dcc  pop     rbx
0x140004dcd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
