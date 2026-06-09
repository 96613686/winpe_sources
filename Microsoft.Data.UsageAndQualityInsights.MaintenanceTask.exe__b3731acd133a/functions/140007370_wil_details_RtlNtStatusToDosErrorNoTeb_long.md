# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140007370`
- end: `0x1400073ce`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140007370`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007397`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007397`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400073ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400073ae`

## string_xrefs

- `0x140007390`: `ntdll.dll`

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
0x140007370  push    rbx
0x140007372  sub     rsp, 20h
0x140007376  mov     ebx, ecx
0x140007378  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000737f  test    rax, rax
0x140007382  jnz     short loc_1400073C0
0x140007384  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000738b  test    rax, rax
0x14000738e  jnz     short loc_1400073A4
0x140007390  lea     rcx, ModuleName; "ntdll.dll"
0x140007397  call    cs:__imp_GetModuleHandleW
0x14000739d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400073a4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1400073ab  mov     rcx, rax; hModule
0x1400073ae  call    cs:__imp_GetProcAddress
0x1400073b4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1400073bb  test    rax, rax
0x1400073be  jz      short loc_1400073C8
0x1400073c0  mov     ecx, ebx
0x1400073c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073c7  nop
0x1400073c8  add     rsp, 20h
0x1400073cc  pop     rbx
0x1400073cd  retn
```
