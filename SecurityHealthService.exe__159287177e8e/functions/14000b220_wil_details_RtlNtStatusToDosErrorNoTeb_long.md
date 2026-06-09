# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x14000b220`
- end: `0x14000b27e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000b220`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000b247`
- `KERNEL32!GetModuleHandleW` at `0x14000b247`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b25e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b25e`

## string_xrefs

- `0x14000b240`: `ntdll.dll`

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
0x14000b220  push    rbx
0x14000b222  sub     rsp, 20h
0x14000b226  mov     ebx, ecx
0x14000b228  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000b22f  test    rax, rax
0x14000b232  jnz     short loc_14000B270
0x14000b234  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b23b  test    rax, rax
0x14000b23e  jnz     short loc_14000B254
0x14000b240  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000b247  call    cs:__imp_GetModuleHandleW
0x14000b24d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b254  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000b25b  mov     rcx, rax; hModule
0x14000b25e  call    cs:__imp_GetProcAddress
0x14000b264  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000b26b  test    rax, rax
0x14000b26e  jz      short loc_14000B278
0x14000b270  mov     ecx, ebx
0x14000b272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b277  nop
0x14000b278  add     rsp, 20h
0x14000b27c  pop     rbx
0x14000b27d  retn
```
