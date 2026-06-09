# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180004ac0`
- end: `0x180004b1e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004ac0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ae7`

## string_xrefs

- `0x180004ae0`: `ntdll.dll`

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
0x180004ac0  push    rbx
0x180004ac2  sub     rsp, 20h
0x180004ac6  mov     ebx, ecx
0x180004ac8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180004acf  test    rax, rax
0x180004ad2  jnz     short loc_180004B10
0x180004ad4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004adb  test    rax, rax
0x180004ade  jnz     short loc_180004AF4
0x180004ae0  lea     rcx, ModuleName; "ntdll.dll"
0x180004ae7  call    cs:__imp_GetModuleHandleW
0x180004aed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004af4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180004afb  mov     rcx, rax; hModule
0x180004afe  call    cs:__imp_GetProcAddress
0x180004b04  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180004b0b  test    rax, rax
0x180004b0e  jz      short loc_180004B18
0x180004b10  mov     ecx, ebx
0x180004b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b17  nop
0x180004b18  add     rsp, 20h
0x180004b1c  pop     rbx
0x180004b1d  retn
```
