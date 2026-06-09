# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180026f70`
- end: `0x180026fd2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180026f70`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180026f97`
- `KERNEL32!GetModuleHandleW` at `0x180026f97`
- `KERNEL32!GetProcAddress` at `0x180026fae`
- `KERNEL32!GetProcAddress` at `0x180026fae`

## string_xrefs

- `0x180026f90`: `ntdll.dll`

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
0x180026f70  push    rbx
0x180026f72  sub     rsp, 20h
0x180026f76  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180026f7d  mov     ebx, ecx
0x180026f7f  test    rax, rax
0x180026f82  jnz     short loc_180026FC6
0x180026f84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026f8b  test    rax, rax
0x180026f8e  jnz     short loc_180026FA4
0x180026f90  lea     rcx, aNtdllDll; "ntdll.dll"
0x180026f97  call    cs:__imp_GetModuleHandleW
0x180026f9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026fa4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180026fab  mov     rcx, rax; hModule
0x180026fae  call    cs:__imp_GetProcAddress
0x180026fb4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180026fbb  test    rax, rax
0x180026fbe  jnz     short loc_180026FC6
0x180026fc0  add     rsp, 20h
0x180026fc4  pop     rbx
0x180026fc5  retn
0x180026fc6  mov     ecx, ebx
0x180026fc8  add     rsp, 20h
0x180026fcc  pop     rbx
0x180026fcd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
