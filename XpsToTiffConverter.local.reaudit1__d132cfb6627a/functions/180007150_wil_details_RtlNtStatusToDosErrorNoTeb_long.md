# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007150`
- end: `0x1800071ae`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007150`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000718e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000718e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007177`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007177`

## string_xrefs

- `0x180007170`: `ntdll.dll`

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
0x180007150  push    rbx
0x180007152  sub     rsp, 20h
0x180007156  mov     ebx, ecx
0x180007158  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000715f  test    rax, rax
0x180007162  jnz     short loc_1800071A0
0x180007164  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000716b  test    rax, rax
0x18000716e  jnz     short loc_180007184
0x180007170  lea     rcx, ModuleName; "ntdll.dll"
0x180007177  call    cs:__imp_GetModuleHandleW
0x18000717d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007184  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000718b  mov     rcx, rax; hModule
0x18000718e  call    cs:__imp_GetProcAddress
0x180007194  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000719b  test    rax, rax
0x18000719e  jz      short loc_1800071A8
0x1800071a0  mov     ecx, ebx
0x1800071a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a7  nop
0x1800071a8  add     rsp, 20h
0x1800071ac  pop     rbx
0x1800071ad  retn
```
