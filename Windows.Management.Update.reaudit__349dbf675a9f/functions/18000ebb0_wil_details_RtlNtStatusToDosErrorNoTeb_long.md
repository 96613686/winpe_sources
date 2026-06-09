# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000ebb0`
- end: `0x18000ec29`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ebb0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ebfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ebfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ebdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ebdd`

## string_xrefs

- `0x18000ebd6`: `ntdll.dll`

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
0x18000ebb0  mov     [rsp+arg_0], rbx
0x18000ebb5  push    rdi
0x18000ebb6  sub     rsp, 20h
0x18000ebba  mov     edi, ecx
0x18000ebbc  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000ebc3  xor     ebx, ebx
0x18000ebc5  test    rax, rax
0x18000ebc8  jnz     short loc_18000EC12
0x18000ebca  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebd1  test    rax, rax
0x18000ebd4  jnz     short loc_18000EBF0
0x18000ebd6  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000ebdd  call    cs:__imp_GetModuleHandleW
0x18000ebe4  nop     dword ptr [rax+rax+00h]
0x18000ebe9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebf0  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000ebf7  mov     rcx, rax; hModule
0x18000ebfa  call    cs:__imp_GetProcAddress
0x18000ec01  nop     dword ptr [rax+rax+00h]
0x18000ec06  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000ec0d  test    rax, rax
0x18000ec10  jz      short loc_18000EC1B
0x18000ec12  mov     ecx, edi
0x18000ec14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec19  mov     ebx, eax
0x18000ec1b  mov     eax, ebx
0x18000ec1d  mov     rbx, [rsp+28h+arg_0]
0x18000ec22  add     rsp, 20h
0x18000ec26  pop     rdi
0x18000ec27  retn
```
