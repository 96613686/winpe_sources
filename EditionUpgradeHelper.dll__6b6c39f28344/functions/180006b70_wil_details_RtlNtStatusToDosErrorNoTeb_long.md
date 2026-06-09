# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006b70`
- end: `0x180006bd2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006b70`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006b97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006b97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bae`

## string_xrefs

- `0x180006b90`: `ntdll.dll`

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
0x180006b70  push    rbx
0x180006b72  sub     rsp, 20h
0x180006b76  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180006b7d  mov     ebx, ecx
0x180006b7f  test    rax, rax
0x180006b82  jnz     short loc_180006BC6
0x180006b84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006b8b  test    rax, rax
0x180006b8e  jnz     short loc_180006BA4
0x180006b90  lea     rcx, ModuleName; "ntdll.dll"
0x180006b97  call    cs:__imp_GetModuleHandleW
0x180006b9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006ba4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180006bab  mov     rcx, rax; hModule
0x180006bae  call    cs:__imp_GetProcAddress
0x180006bb4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180006bbb  test    rax, rax
0x180006bbe  jnz     short loc_180006BC6
0x180006bc0  add     rsp, 20h
0x180006bc4  pop     rbx
0x180006bc5  retn
0x180006bc6  mov     ecx, ebx
0x180006bc8  add     rsp, 20h
0x180006bcc  pop     rbx
0x180006bcd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
