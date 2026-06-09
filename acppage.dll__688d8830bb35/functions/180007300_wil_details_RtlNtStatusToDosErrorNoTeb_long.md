# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007300`
- end: `0x180007362`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007300`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180007327`
- `KERNEL32!GetModuleHandleW` at `0x180007327`
- `KERNEL32!GetProcAddress` at `0x18000733e`
- `KERNEL32!GetProcAddress` at `0x18000733e`

## string_xrefs

- `0x180007320`: `ntdll.dll`

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
0x180007300  push    rbx
0x180007302  sub     rsp, 20h
0x180007306  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000730d  mov     ebx, ecx
0x18000730f  test    rax, rax
0x180007312  jnz     short loc_180007356
0x180007314  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000731b  test    rax, rax
0x18000731e  jnz     short loc_180007334
0x180007320  lea     rcx, ModuleName; "ntdll.dll"
0x180007327  call    cs:__imp_GetModuleHandleW
0x18000732d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007334  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000733b  mov     rcx, rax; hModule
0x18000733e  call    cs:__imp_GetProcAddress
0x180007344  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000734b  test    rax, rax
0x18000734e  jnz     short loc_180007356
0x180007350  add     rsp, 20h
0x180007354  pop     rbx
0x180007355  retn
0x180007356  mov     ecx, ebx
0x180007358  add     rsp, 20h
0x18000735c  pop     rbx
0x18000735d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
