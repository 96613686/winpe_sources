# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000e3e0`
- end: `0x18000e43e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000e3e0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e407`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e407`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e41e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e41e`

## string_xrefs

- `0x18000e400`: `ntdll.dll`

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
0x18000e3e0  push    rbx
0x18000e3e2  sub     rsp, 20h
0x18000e3e6  mov     ebx, ecx
0x18000e3e8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000e3ef  test    rax, rax
0x18000e3f2  jnz     short loc_18000E430
0x18000e3f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e3fb  test    rax, rax
0x18000e3fe  jnz     short loc_18000E414
0x18000e400  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000e407  call    cs:__imp_GetModuleHandleW
0x18000e40d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e414  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000e41b  mov     rcx, rax; hModule
0x18000e41e  call    cs:__imp_GetProcAddress
0x18000e424  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000e42b  test    rax, rax
0x18000e42e  jz      short loc_18000E438
0x18000e430  mov     ecx, ebx
0x18000e432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e437  nop
0x18000e438  add     rsp, 20h
0x18000e43c  pop     rbx
0x18000e43d  retn
```
