# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800156c0`
- end: `0x180015722`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800156c0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800156e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800156e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800156fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800156fe`

## string_xrefs

- `0x1800156e0`: `ntdll.dll`

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
0x1800156c0  push    rbx
0x1800156c2  sub     rsp, 20h
0x1800156c6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800156cd  mov     ebx, ecx
0x1800156cf  test    rax, rax
0x1800156d2  jnz     short loc_180015716
0x1800156d4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800156db  test    rax, rax
0x1800156de  jnz     short loc_1800156F4
0x1800156e0  lea     rcx, ModuleName; "ntdll.dll"
0x1800156e7  call    cs:__imp_GetModuleHandleW
0x1800156ed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800156f4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800156fb  mov     rcx, rax; hModule
0x1800156fe  call    cs:__imp_GetProcAddress
0x180015704  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18001570b  test    rax, rax
0x18001570e  jnz     short loc_180015716
0x180015710  add     rsp, 20h
0x180015714  pop     rbx
0x180015715  retn
0x180015716  mov     ecx, ebx
0x180015718  add     rsp, 20h
0x18001571c  pop     rbx
0x18001571d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
