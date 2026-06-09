# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1400064b0`
- end: `0x14000650e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400064b0`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400064d7`
- `KERNEL32!GetModuleHandleW` at `0x1400064d7`
- `KERNEL32!GetProcAddress` at `0x1400064ee`
- `KERNEL32!GetProcAddress` at `0x1400064ee`

## string_xrefs

- `0x1400064d0`: `ntdll.dll`

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
0x1400064b0  push    rbx
0x1400064b2  sub     rsp, 20h
0x1400064b6  mov     ebx, ecx
0x1400064b8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1400064bf  test    rax, rax
0x1400064c2  jnz     short loc_140006500
0x1400064c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400064cb  test    rax, rax
0x1400064ce  jnz     short loc_1400064E4
0x1400064d0  lea     rcx, ModuleName; "ntdll.dll"
0x1400064d7  call    cs:__imp_GetModuleHandleW
0x1400064dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400064e4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1400064eb  mov     rcx, rax; hModule
0x1400064ee  call    cs:__imp_GetProcAddress
0x1400064f4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1400064fb  test    rax, rax
0x1400064fe  jz      short loc_140006508
0x140006500  mov     ecx, ebx
0x140006502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006507  nop
0x140006508  add     rsp, 20h
0x14000650c  pop     rbx
0x14000650d  retn
```
