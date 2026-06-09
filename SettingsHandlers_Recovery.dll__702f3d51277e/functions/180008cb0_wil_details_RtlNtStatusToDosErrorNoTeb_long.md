# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180008cb0`
- end: `0x180008d0e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008cb0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008cee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008cee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008cd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008cd7`

## string_xrefs

- `0x180008cd0`: `ntdll.dll`

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
0x180008cb0  push    rbx
0x180008cb2  sub     rsp, 20h
0x180008cb6  mov     ebx, ecx
0x180008cb8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180008cbf  test    rax, rax
0x180008cc2  jnz     short loc_180008D00
0x180008cc4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008ccb  test    rax, rax
0x180008cce  jnz     short loc_180008CE4
0x180008cd0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008cd7  call    cs:__imp_GetModuleHandleW
0x180008cdd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008ce4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180008ceb  mov     rcx, rax; hModule
0x180008cee  call    cs:__imp_GetProcAddress
0x180008cf4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180008cfb  test    rax, rax
0x180008cfe  jz      short loc_180008D08
0x180008d00  mov     ecx, ebx
0x180008d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d07  nop
0x180008d08  add     rsp, 20h
0x180008d0c  pop     rbx
0x180008d0d  retn
```
