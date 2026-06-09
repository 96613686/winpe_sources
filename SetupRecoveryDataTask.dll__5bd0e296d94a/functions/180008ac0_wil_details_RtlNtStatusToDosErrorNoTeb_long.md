# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180008ac0`
- end: `0x180008b1e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008ac0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ae7`

## string_xrefs

- `0x180008ae0`: `ntdll.dll`

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
0x180008ac0  push    rbx
0x180008ac2  sub     rsp, 20h
0x180008ac6  mov     ebx, ecx
0x180008ac8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180008acf  test    rax, rax
0x180008ad2  jnz     short loc_180008B10
0x180008ad4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008adb  test    rax, rax
0x180008ade  jnz     short loc_180008AF4
0x180008ae0  lea     rcx, ModuleName; "ntdll.dll"
0x180008ae7  call    cs:__imp_GetModuleHandleW
0x180008aed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008af4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180008afb  mov     rcx, rax; hModule
0x180008afe  call    cs:__imp_GetProcAddress
0x180008b04  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180008b0b  test    rax, rax
0x180008b0e  jz      short loc_180008B18
0x180008b10  mov     ecx, ebx
0x180008b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b17  nop
0x180008b18  add     rsp, 20h
0x180008b1c  pop     rbx
0x180008b1d  retn
```
