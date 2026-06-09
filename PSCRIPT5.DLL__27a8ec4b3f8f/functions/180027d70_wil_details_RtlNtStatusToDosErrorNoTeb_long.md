# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180027d70`
- end: `0x180027ddf`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `111`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180027d70`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180027d97`
- `KERNEL32!GetModuleHandleW` at `0x180027d97`
- `KERNEL32!GetProcAddress` at `0x180027db4`
- `KERNEL32!GetProcAddress` at `0x180027db4`

## string_xrefs

- `0x180027d90`: `ntdll.dll`

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
0x180027d70  push    rbx
0x180027d72  sub     rsp, 20h
0x180027d76  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180027d7d  mov     ebx, ecx
0x180027d7f  test    rax, rax
0x180027d82  jnz     short loc_180027DD3
0x180027d84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027d8b  test    rax, rax
0x180027d8e  jnz     short loc_180027DAA
0x180027d90  lea     rcx, aNtdllDll; "ntdll.dll"
0x180027d97  call    cs:__imp_GetModuleHandleW
0x180027d9e  nop     dword ptr [rax+rax+00h]
0x180027da3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027daa  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180027db1  mov     rcx, rax; hModule
0x180027db4  call    cs:__imp_GetProcAddress
0x180027dbb  nop     dword ptr [rax+rax+00h]
0x180027dc0  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180027dc7  test    rax, rax
0x180027dca  jnz     short loc_180027DD3
0x180027dcc  add     rsp, 20h
0x180027dd0  pop     rbx
0x180027dd1  retn
0x180027dd3  mov     ecx, ebx
0x180027dd5  add     rsp, 20h
0x180027dd9  pop     rbx
0x180027dda  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
