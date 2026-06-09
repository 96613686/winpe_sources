# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180008d10`
- end: `0x180008d6e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008d10`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d37`

## string_xrefs

- `0x180008d30`: `ntdll.dll`

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
0x180008d10  push    rbx
0x180008d12  sub     rsp, 20h
0x180008d16  mov     ebx, ecx
0x180008d18  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180008d1f  test    rax, rax
0x180008d22  jnz     short loc_180008D60
0x180008d24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d2b  test    rax, rax
0x180008d2e  jnz     short loc_180008D44
0x180008d30  lea     rcx, ModuleName; "ntdll.dll"
0x180008d37  call    cs:__imp_GetModuleHandleW
0x180008d3d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d44  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180008d4b  mov     rcx, rax; hModule
0x180008d4e  call    cs:__imp_GetProcAddress
0x180008d54  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180008d5b  test    rax, rax
0x180008d5e  jz      short loc_180008D68
0x180008d60  mov     ecx, ebx
0x180008d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d67  nop
0x180008d68  add     rsp, 20h
0x180008d6c  pop     rbx
0x180008d6d  retn
```
