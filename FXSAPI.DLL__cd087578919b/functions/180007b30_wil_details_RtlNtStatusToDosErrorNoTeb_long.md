# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007b30`
- end: `0x180007b9b`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007b30`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007b74`
- `KERNEL32!GetProcAddress` at `0x180007b74`
- `KERNEL32!GetModuleHandleW` at `0x180007b57`
- `KERNEL32!GetModuleHandleW` at `0x180007b57`

## string_xrefs

- `0x180007b50`: `ntdll.dll`

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
0x180007b30  push    rbx
0x180007b32  sub     rsp, 20h
0x180007b36  mov     ebx, ecx
0x180007b38  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180007b3f  test    rax, rax
0x180007b42  jnz     short loc_180007B8C
0x180007b44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b4b  test    rax, rax
0x180007b4e  jnz     short loc_180007B6A
0x180007b50  lea     rcx, ModuleName; "ntdll.dll"
0x180007b57  call    cs:__imp_GetModuleHandleW
0x180007b5e  nop     dword ptr [rax+rax+00h]
0x180007b63  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b6a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180007b71  mov     rcx, rax; hModule
0x180007b74  call    cs:__imp_GetProcAddress
0x180007b7b  nop     dword ptr [rax+rax+00h]
0x180007b80  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180007b87  test    rax, rax
0x180007b8a  jz      short loc_180007B94
0x180007b8c  mov     ecx, ebx
0x180007b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b93  nop
0x180007b94  add     rsp, 20h
0x180007b98  pop     rbx
0x180007b99  retn
```
