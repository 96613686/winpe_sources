# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000c040`
- end: `0x18000c09e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000c040`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c07e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c07e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c067`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c067`

## string_xrefs

- `0x18000c060`: `ntdll.dll`

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
0x18000c040  push    rbx
0x18000c042  sub     rsp, 20h
0x18000c046  mov     ebx, ecx
0x18000c048  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000c04f  test    rax, rax
0x18000c052  jnz     short loc_18000C090
0x18000c054  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c05b  test    rax, rax
0x18000c05e  jnz     short loc_18000C074
0x18000c060  lea     rcx, ModuleName; "ntdll.dll"
0x18000c067  call    cs:__imp_GetModuleHandleW
0x18000c06d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c074  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000c07b  mov     rcx, rax; hModule
0x18000c07e  call    cs:__imp_GetProcAddress
0x18000c084  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000c08b  test    rax, rax
0x18000c08e  jz      short loc_18000C098
0x18000c090  mov     ecx, ebx
0x18000c092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c097  nop
0x18000c098  add     rsp, 20h
0x18000c09c  pop     rbx
0x18000c09d  retn
```
