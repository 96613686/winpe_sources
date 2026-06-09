# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800079f0`
- end: `0x180007a4e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800079f0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007a2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007a2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007a17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007a17`

## string_xrefs

- `0x180007a10`: `ntdll.dll`

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
0x1800079f0  push    rbx
0x1800079f2  sub     rsp, 20h
0x1800079f6  mov     ebx, ecx
0x1800079f8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800079ff  test    rax, rax
0x180007a02  jnz     short loc_180007A40
0x180007a04  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007a0b  test    rax, rax
0x180007a0e  jnz     short loc_180007A24
0x180007a10  lea     rcx, ModuleName; "ntdll.dll"
0x180007a17  call    cs:__imp_GetModuleHandleW
0x180007a1d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007a24  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180007a2b  mov     rcx, rax; hModule
0x180007a2e  call    cs:__imp_GetProcAddress
0x180007a34  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180007a3b  test    rax, rax
0x180007a3e  jz      short loc_180007A48
0x180007a40  mov     ecx, ebx
0x180007a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a47  nop
0x180007a48  add     rsp, 20h
0x180007a4c  pop     rbx
0x180007a4d  retn
```
