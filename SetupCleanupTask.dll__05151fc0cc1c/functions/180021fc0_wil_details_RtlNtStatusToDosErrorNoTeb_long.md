# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180021fc0`
- end: `0x180022022`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180021fc0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021fe7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021fe7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021ffe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021ffe`

## string_xrefs

- `0x180021fe0`: `ntdll.dll`

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
0x180021fc0  push    rbx
0x180021fc2  sub     rsp, 20h
0x180021fc6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180021fcd  mov     ebx, ecx
0x180021fcf  test    rax, rax
0x180021fd2  jnz     short loc_180022016
0x180021fd4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180021fdb  test    rax, rax
0x180021fde  jnz     short loc_180021FF4
0x180021fe0  lea     rcx, LibFileName; "ntdll.dll"
0x180021fe7  call    cs:__imp_GetModuleHandleW
0x180021fed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180021ff4  lea     rdx, aRtlntstatustod_0; "RtlNtStatusToDosErrorNoTeb"
0x180021ffb  mov     rcx, rax; hModule
0x180021ffe  call    cs:__imp_GetProcAddress
0x180022004  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18002200b  test    rax, rax
0x18002200e  jnz     short loc_180022016
0x180022010  add     rsp, 20h
0x180022014  pop     rbx
0x180022015  retn
0x180022016  mov     ecx, ebx
0x180022018  add     rsp, 20h
0x18002201c  pop     rbx
0x18002201d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
