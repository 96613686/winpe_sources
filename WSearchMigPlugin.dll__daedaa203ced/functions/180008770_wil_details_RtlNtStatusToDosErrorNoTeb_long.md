# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180008770`
- end: `0x1800087d7`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `103`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008770`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800087a0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800087a0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800087b7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800087b7`

## string_xrefs

- `0x180008799`: `ntdll.dll`

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
0x180008770  push    rbx
0x180008772  sub     rsp, 30h
0x180008776  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000877f  mov     ebx, ecx
0x180008781  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180008788  test    rax, rax
0x18000878b  jnz     short loc_1800087C9
0x18000878d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008794  test    rax, rax
0x180008797  jnz     short loc_1800087AD
0x180008799  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800087a0  call    cs:__imp_GetModuleHandleW
0x1800087a6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800087ad  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800087b4  mov     rcx, rax; hModule
0x1800087b7  call    cs:__imp_GetProcAddress
0x1800087bd  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800087c4  test    rax, rax
0x1800087c7  jz      short loc_1800087D1
0x1800087c9  mov     ecx, ebx
0x1800087cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d0  nop
0x1800087d1  add     rsp, 30h
0x1800087d5  pop     rbx
0x1800087d6  retn
```
