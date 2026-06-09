# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000a1a0`
- end: `0x18000a207`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `103`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a1a0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a1d0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a1d0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a1e7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a1e7`

## string_xrefs

- `0x18000a1c9`: `ntdll.dll`

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
0x18000a1a0  push    rbx
0x18000a1a2  sub     rsp, 30h
0x18000a1a6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a1af  mov     ebx, ecx
0x18000a1b1  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000a1b8  test    rax, rax
0x18000a1bb  jnz     short loc_18000A1F9
0x18000a1bd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a1c4  test    rax, rax
0x18000a1c7  jnz     short loc_18000A1DD
0x18000a1c9  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a1d0  call    cs:__imp_GetModuleHandleW
0x18000a1d6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a1dd  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000a1e4  mov     rcx, rax; hModule
0x18000a1e7  call    cs:__imp_GetProcAddress
0x18000a1ed  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000a1f4  test    rax, rax
0x18000a1f7  jz      short loc_18000A201
0x18000a1f9  mov     ecx, ebx
0x18000a1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a200  nop
0x18000a201  add     rsp, 30h
0x18000a205  pop     rbx
0x18000a206  retn
```
