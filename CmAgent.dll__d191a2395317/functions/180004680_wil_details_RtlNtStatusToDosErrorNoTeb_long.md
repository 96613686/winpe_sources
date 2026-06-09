# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180004680`
- end: `0x1800046eb`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004680`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046c4`

## string_xrefs

- `0x1800046a0`: `ntdll.dll`

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
0x180004680  push    rbx
0x180004682  sub     rsp, 20h
0x180004686  mov     ebx, ecx
0x180004688  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000468f  test    rax, rax
0x180004692  jnz     short loc_1800046DC
0x180004694  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000469b  test    rax, rax
0x18000469e  jnz     short loc_1800046BA
0x1800046a0  lea     rcx, ModuleName; "ntdll.dll"
0x1800046a7  call    cs:__imp_GetModuleHandleW
0x1800046ae  nop     dword ptr [rax+rax+00h]
0x1800046b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800046ba  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800046c1  mov     rcx, rax; hModule
0x1800046c4  call    cs:__imp_GetProcAddress
0x1800046cb  nop     dword ptr [rax+rax+00h]
0x1800046d0  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800046d7  test    rax, rax
0x1800046da  jz      short loc_1800046E4
0x1800046dc  mov     ecx, ebx
0x1800046de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046e3  nop
0x1800046e4  add     rsp, 20h
0x1800046e8  pop     rbx
0x1800046e9  retn
```
