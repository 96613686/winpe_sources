# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180016670`
- end: `0x1800166d2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180016670`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800166ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800166ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016697`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016697`

## string_xrefs

- `0x180016690`: `ntdll.dll`

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
0x180016670  push    rbx
0x180016672  sub     rsp, 20h
0x180016676  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18001667d  mov     ebx, ecx
0x18001667f  test    rax, rax
0x180016682  jnz     short loc_1800166C6
0x180016684  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001668b  test    rax, rax
0x18001668e  jnz     short loc_1800166A4
0x180016690  lea     rcx, ModuleName; "ntdll.dll"
0x180016697  call    cs:__imp_GetModuleHandleW
0x18001669d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800166a4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800166ab  mov     rcx, rax; hModule
0x1800166ae  call    cs:__imp_GetProcAddress
0x1800166b4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800166bb  test    rax, rax
0x1800166be  jnz     short loc_1800166C6
0x1800166c0  add     rsp, 20h
0x1800166c4  pop     rbx
0x1800166c5  retn
0x1800166c6  mov     ecx, ebx
0x1800166c8  add     rsp, 20h
0x1800166cc  pop     rbx
0x1800166cd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
