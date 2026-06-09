# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140009930`
- end: `0x14000998e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140009930`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009957`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009957`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000996e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000996e`

## string_xrefs

- `0x140009950`: `ntdll.dll`

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
0x140009930  push    rbx
0x140009932  sub     rsp, 20h
0x140009936  mov     ebx, ecx
0x140009938  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000993f  test    rax, rax
0x140009942  jnz     short loc_140009980
0x140009944  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000994b  test    rax, rax
0x14000994e  jnz     short loc_140009964
0x140009950  lea     rcx, ModuleName; "ntdll.dll"
0x140009957  call    cs:__imp_GetModuleHandleW
0x14000995d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009964  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000996b  mov     rcx, rax; hModule
0x14000996e  call    cs:__imp_GetProcAddress
0x140009974  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000997b  test    rax, rax
0x14000997e  jz      short loc_140009988
0x140009980  mov     ecx, ebx
0x140009982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009987  nop
0x140009988  add     rsp, 20h
0x14000998c  pop     rbx
0x14000998d  retn
```
