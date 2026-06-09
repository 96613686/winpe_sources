# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180010680`
- end: `0x1800106de`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180010680`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800106a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800106a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800106be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800106be`

## string_xrefs

- `0x1800106a0`: `ntdll.dll`

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
0x180010680  push    rbx
0x180010682  sub     rsp, 20h
0x180010686  mov     ebx, ecx
0x180010688  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18001068f  test    rax, rax
0x180010692  jnz     short loc_1800106D0
0x180010694  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001069b  test    rax, rax
0x18001069e  jnz     short loc_1800106B4
0x1800106a0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800106a7  call    cs:__imp_GetModuleHandleW
0x1800106ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800106b4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800106bb  mov     rcx, rax; hModule
0x1800106be  call    cs:__imp_GetProcAddress
0x1800106c4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800106cb  test    rax, rax
0x1800106ce  jz      short loc_1800106D8
0x1800106d0  mov     ecx, ebx
0x1800106d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106d7  nop
0x1800106d8  add     rsp, 20h
0x1800106dc  pop     rbx
0x1800106dd  retn
```
