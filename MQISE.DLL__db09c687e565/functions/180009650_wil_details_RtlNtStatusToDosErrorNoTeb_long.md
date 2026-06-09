# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180009650`
- end: `0x1800096af`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `95`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009650`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180009677`
- `KERNEL32!GetModuleHandleW` at `0x180009677`
- `KERNEL32!GetProcAddress` at `0x18000968e`
- `KERNEL32!GetProcAddress` at `0x18000968e`

## string_xrefs

- `0x180009670`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180009650  push    rbx
0x180009652  sub     rsp, 20h
0x180009656  mov     ebx, ecx
0x180009658  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000965f  test    rax, rax
0x180009662  jnz     short loc_1800096A1
0x180009664  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000966b  test    rax, rax
0x18000966e  jnz     short loc_180009684
0x180009670  lea     rcx, ModuleName; "ntdll.dll"
0x180009677  call    cs:__imp_GetModuleHandleW
0x18000967d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009684  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000968b  mov     rcx, rax; hModule
0x18000968e  call    cs:__imp_GetProcAddress
0x180009694  nop
0x180009695  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000969c  test    rax, rax
0x18000969f  jz      short loc_1800096A9
0x1800096a1  mov     ecx, ebx
0x1800096a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a8  nop
0x1800096a9  add     rsp, 20h
0x1800096ad  pop     rbx
0x1800096ae  retn
```
