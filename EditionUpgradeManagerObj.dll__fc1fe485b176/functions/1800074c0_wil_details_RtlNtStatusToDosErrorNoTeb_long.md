# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800074c0`
- end: `0x180007522`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800074c0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074e7`

## string_xrefs

- `0x1800074e0`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC result; // rax
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  return result;
}

```

## disassembly

```asm
0x1800074c0  push    rbx
0x1800074c2  sub     rsp, 20h
0x1800074c6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800074cd  mov     ebx, ecx
0x1800074cf  test    rax, rax
0x1800074d2  jnz     short loc_180007516
0x1800074d4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800074db  test    rax, rax
0x1800074de  jnz     short loc_1800074F4
0x1800074e0  lea     rcx, ModuleName; "ntdll.dll"
0x1800074e7  call    cs:__imp_GetModuleHandleW
0x1800074ed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800074f4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800074fb  mov     rcx, rax; hModule
0x1800074fe  call    cs:__imp_GetProcAddress
0x180007504  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000750b  test    rax, rax
0x18000750e  jnz     short loc_180007516
0x180007510  add     rsp, 20h
0x180007514  pop     rbx
0x180007515  retn
0x180007516  mov     ecx, ebx
0x180007518  add     rsp, 20h
0x18000751c  pop     rbx
0x18000751d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
