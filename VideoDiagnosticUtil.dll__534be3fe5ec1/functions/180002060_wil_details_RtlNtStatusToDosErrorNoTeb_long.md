# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180002060`
- end: `0x1800020cf`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `111`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002060`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800020a4`
- `KERNEL32!GetProcAddress` at `0x1800020a4`
- `KERNEL32!GetModuleHandleW` at `0x180002087`
- `KERNEL32!GetModuleHandleW` at `0x180002087`

## string_xrefs

- `0x180002080`: `ntdll.dll`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180002060  push    rbx
0x180002062  sub     rsp, 20h
0x180002066  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000206d  mov     ebx, ecx
0x18000206f  test    rax, rax
0x180002072  jnz     short loc_1800020C3
0x180002074  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000207b  test    rax, rax
0x18000207e  jnz     short loc_18000209A
0x180002080  lea     rcx, ModuleName; "ntdll.dll"
0x180002087  call    cs:__imp_GetModuleHandleW
0x18000208e  nop     dword ptr [rax+rax+00h]
0x180002093  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000209a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800020a1  mov     rcx, rax; hModule
0x1800020a4  call    cs:__imp_GetProcAddress
0x1800020ab  nop     dword ptr [rax+rax+00h]
0x1800020b0  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800020b7  test    rax, rax
0x1800020ba  jnz     short loc_1800020C3
0x1800020bc  add     rsp, 20h
0x1800020c0  pop     rbx
0x1800020c1  retn
0x1800020c3  mov     ecx, ebx
0x1800020c5  add     rsp, 20h
0x1800020c9  pop     rbx
0x1800020ca  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
