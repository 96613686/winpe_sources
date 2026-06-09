# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180002f30`
- end: `0x180002f8e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002f30`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002f6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002f6e`

## string_xrefs

- `0x180002f50`: `ntdll.dll`

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
0x180002f30  push    rbx
0x180002f32  sub     rsp, 20h
0x180002f36  mov     ebx, ecx
0x180002f38  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180002f3f  test    rax, rax
0x180002f42  jnz     short loc_180002F80
0x180002f44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002f4b  test    rax, rax
0x180002f4e  jnz     short loc_180002F64
0x180002f50  lea     rcx, ModuleName; "ntdll.dll"
0x180002f57  call    cs:__imp_GetModuleHandleW
0x180002f5d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002f64  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180002f6b  mov     rcx, rax; hModule
0x180002f6e  call    cs:__imp_GetProcAddress
0x180002f74  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180002f7b  test    rax, rax
0x180002f7e  jz      short loc_180002F88
0x180002f80  mov     ecx, ebx
0x180002f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f87  nop
0x180002f88  add     rsp, 20h
0x180002f8c  pop     rbx
0x180002f8d  retn
```
