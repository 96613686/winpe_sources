# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x14000a560`
- end: `0x14000a5be`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000a560`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000a587`
- `KERNEL32!GetModuleHandleW` at `0x14000a587`
- `KERNEL32!GetProcAddress` at `0x14000a59e`
- `KERNEL32!GetProcAddress` at `0x14000a59e`

## string_xrefs

- `0x14000a580`: `ntdll.dll`

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
0x14000a560  push    rbx
0x14000a562  sub     rsp, 20h
0x14000a566  mov     ebx, ecx
0x14000a568  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000a56f  test    rax, rax
0x14000a572  jnz     short loc_14000A5B0
0x14000a574  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a57b  test    rax, rax
0x14000a57e  jnz     short loc_14000A594
0x14000a580  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000a587  call    cs:__imp_GetModuleHandleW
0x14000a58d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a594  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000a59b  mov     rcx, rax; hModule
0x14000a59e  call    cs:__imp_GetProcAddress
0x14000a5a4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000a5ab  test    rax, rax
0x14000a5ae  jz      short loc_14000A5B8
0x14000a5b0  mov     ecx, ebx
0x14000a5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5b7  nop
0x14000a5b8  add     rsp, 20h
0x14000a5bc  pop     rbx
0x14000a5bd  retn
```
