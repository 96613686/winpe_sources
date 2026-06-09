# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000e010`
- end: `0x18000e06e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000e010`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000e04e`
- `KERNEL32!GetProcAddress` at `0x18000e04e`
- `KERNEL32!GetModuleHandleW` at `0x18000e037`
- `KERNEL32!GetModuleHandleW` at `0x18000e037`

## string_xrefs

- `0x18000e030`: `ntdll.dll`

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
0x18000e010  push    rbx
0x18000e012  sub     rsp, 20h
0x18000e016  mov     ebx, ecx
0x18000e018  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000e01f  test    rax, rax
0x18000e022  jnz     short loc_18000E060
0x18000e024  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e02b  test    rax, rax
0x18000e02e  jnz     short loc_18000E044
0x18000e030  lea     rcx, ModuleName; "ntdll.dll"
0x18000e037  call    cs:__imp_GetModuleHandleW
0x18000e03d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e044  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000e04b  mov     rcx, rax; hModule
0x18000e04e  call    cs:__imp_GetProcAddress
0x18000e054  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000e05b  test    rax, rax
0x18000e05e  jz      short loc_18000E068
0x18000e060  mov     ecx, ebx
0x18000e062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e067  nop
0x18000e068  add     rsp, 20h
0x18000e06c  pop     rbx
0x18000e06d  retn
```
