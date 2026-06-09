# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007650`
- end: `0x1800076b2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007650`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007677`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007677`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000768e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000768e`

## string_xrefs

- `0x180007670`: `ntdll.dll`

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
0x180007650  push    rbx
0x180007652  sub     rsp, 20h
0x180007656  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000765d  mov     ebx, ecx
0x18000765f  test    rax, rax
0x180007662  jnz     short loc_1800076A6
0x180007664  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000766b  test    rax, rax
0x18000766e  jnz     short loc_180007684
0x180007670  lea     rcx, ModuleName; "ntdll.dll"
0x180007677  call    cs:__imp_GetModuleHandleW
0x18000767d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007684  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000768b  mov     rcx, rax; hModule
0x18000768e  call    cs:__imp_GetProcAddress
0x180007694  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000769b  test    rax, rax
0x18000769e  jnz     short loc_1800076A6
0x1800076a0  add     rsp, 20h
0x1800076a4  pop     rbx
0x1800076a5  retn
0x1800076a6  mov     ecx, ebx
0x1800076a8  add     rsp, 20h
0x1800076ac  pop     rbx
0x1800076ad  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
