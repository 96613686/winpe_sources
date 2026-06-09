# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007930`
- end: `0x18000799c`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `108`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007930`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000795d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000795d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007974`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007974`

## string_xrefs

- `0x180007956`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // edi
  FARPROC ProcAddress; // rax
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  ProcAddress = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v3 = 0;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1);
  return v3;
}

```

## disassembly

```asm
0x180007930  mov     [rsp+arg_0], rbx
0x180007935  push    rdi
0x180007936  sub     rsp, 20h
0x18000793a  mov     edi, ecx
0x18000793c  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180007943  xor     ebx, ebx
0x180007945  test    rax, rax
0x180007948  jnz     short loc_180007986
0x18000794a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007951  test    rax, rax
0x180007954  jnz     short loc_18000796A
0x180007956  lea     rcx, ModuleName; "ntdll.dll"
0x18000795d  call    cs:__imp_GetModuleHandleW
0x180007963  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000796a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180007971  mov     rcx, rax; hModule
0x180007974  call    cs:__imp_GetProcAddress
0x18000797a  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180007981  test    rax, rax
0x180007984  jz      short loc_18000798F
0x180007986  mov     ecx, edi
0x180007988  call    _guard_dispatch_icall
0x18000798d  mov     ebx, eax
0x18000798f  mov     eax, ebx
0x180007991  mov     rbx, [rsp+28h+arg_0]
0x180007996  add     rsp, 20h
0x18000799a  pop     rdi
0x18000799b  retn
```
