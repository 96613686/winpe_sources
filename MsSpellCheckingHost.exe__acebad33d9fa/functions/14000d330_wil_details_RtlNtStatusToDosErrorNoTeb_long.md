# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x14000d330`
- end: `0x14000d38e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000d330`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d357`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d357`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d36e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d36e`

## string_xrefs

- `0x14000d350`: `ntdll.dll`

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
0x14000d330  push    rbx
0x14000d332  sub     rsp, 20h
0x14000d336  mov     ebx, ecx
0x14000d338  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000d33f  test    rax, rax
0x14000d342  jnz     short loc_14000D380
0x14000d344  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d34b  test    rax, rax
0x14000d34e  jnz     short loc_14000D364
0x14000d350  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000d357  call    cs:__imp_GetModuleHandleW
0x14000d35d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d364  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000d36b  mov     rcx, rax; hModule
0x14000d36e  call    cs:__imp_GetProcAddress
0x14000d374  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000d37b  test    rax, rax
0x14000d37e  jz      short loc_14000D388
0x14000d380  mov     ecx, ebx
0x14000d382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d387  nop
0x14000d388  add     rsp, 20h
0x14000d38c  pop     rbx
0x14000d38d  retn
```
