# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006100`
- end: `0x18000615e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006100`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000613e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000613e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006127`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006127`

## string_xrefs

- `0x180006120`: `ntdll.dll`

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
0x180006100  push    rbx
0x180006102  sub     rsp, 20h
0x180006106  mov     ebx, ecx
0x180006108  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000610f  test    rax, rax
0x180006112  jnz     short loc_180006150
0x180006114  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000611b  test    rax, rax
0x18000611e  jnz     short loc_180006134
0x180006120  lea     rcx, ModuleName; "ntdll.dll"
0x180006127  call    cs:__imp_GetModuleHandleW
0x18000612d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006134  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000613b  mov     rcx, rax; hModule
0x18000613e  call    cs:__imp_GetProcAddress
0x180006144  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000614b  test    rax, rax
0x18000614e  jz      short loc_180006158
0x180006150  mov     ecx, ebx
0x180006152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006157  nop
0x180006158  add     rsp, 20h
0x18000615c  pop     rbx
0x18000615d  retn
```
