# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140005500`
- end: `0x14000555e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140005500`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000553e`
- `KERNEL32!GetProcAddress` at `0x14000553e`
- `KERNEL32!GetModuleHandleW` at `0x140005527`
- `KERNEL32!GetModuleHandleW` at `0x140005527`

## string_xrefs

- `0x140005520`: `ntdll.dll`

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
0x140005500  push    rbx
0x140005502  sub     rsp, 20h
0x140005506  mov     ebx, ecx
0x140005508  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000550f  test    rax, rax
0x140005512  jnz     short loc_140005550
0x140005514  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000551b  test    rax, rax
0x14000551e  jnz     short loc_140005534
0x140005520  lea     rcx, ModuleName; "ntdll.dll"
0x140005527  call    cs:__imp_GetModuleHandleW
0x14000552d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005534  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000553b  mov     rcx, rax; hModule
0x14000553e  call    cs:__imp_GetProcAddress
0x140005544  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000554b  test    rax, rax
0x14000554e  jz      short loc_140005558
0x140005550  mov     ecx, ebx
0x140005552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005557  nop
0x140005558  add     rsp, 20h
0x14000555c  pop     rbx
0x14000555d  retn
```
