# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1400167b0`
- end: `0x140016812`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400167b0`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400167ee`
- `KERNEL32!GetProcAddress` at `0x1400167ee`
- `KERNEL32!GetModuleHandleW` at `0x1400167d7`
- `KERNEL32!GetModuleHandleW` at `0x1400167d7`

## string_xrefs

- `0x1400167d0`: `ntdll.dll`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x1400167b0  push    rbx
0x1400167b2  sub     rsp, 20h
0x1400167b6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1400167bd  mov     ebx, ecx
0x1400167bf  test    rax, rax
0x1400167c2  jnz     short loc_140016806
0x1400167c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400167cb  test    rax, rax
0x1400167ce  jnz     short loc_1400167E4
0x1400167d0  lea     rcx, ModuleName; "ntdll.dll"
0x1400167d7  call    cs:__imp_GetModuleHandleW
0x1400167dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400167e4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1400167eb  mov     rcx, rax; hModule
0x1400167ee  call    cs:__imp_GetProcAddress
0x1400167f4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1400167fb  test    rax, rax
0x1400167fe  jnz     short loc_140016806
0x140016800  add     rsp, 20h
0x140016804  pop     rbx
0x140016805  retn
0x140016806  mov     ecx, ebx
0x140016808  add     rsp, 20h
0x14001680c  pop     rbx
0x14001680d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
