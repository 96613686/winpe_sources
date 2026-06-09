# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140009410`
- end: `0x140009472`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140009410`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000944e`
- `KERNEL32!GetProcAddress` at `0x14000944e`
- `KERNEL32!GetModuleHandleW` at `0x140009437`
- `KERNEL32!GetModuleHandleW` at `0x140009437`

## string_xrefs

- `0x140009430`: `ntdll.dll`

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
0x140009410  push    rbx
0x140009412  sub     rsp, 20h
0x140009416  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000941d  mov     ebx, ecx
0x14000941f  test    rax, rax
0x140009422  jnz     short loc_140009466
0x140009424  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000942b  test    rax, rax
0x14000942e  jnz     short loc_140009444
0x140009430  lea     rcx, ModuleName; "ntdll.dll"
0x140009437  call    cs:__imp_GetModuleHandleW
0x14000943d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009444  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000944b  mov     rcx, rax; hModule
0x14000944e  call    cs:__imp_GetProcAddress
0x140009454  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000945b  test    rax, rax
0x14000945e  jnz     short loc_140009466
0x140009460  add     rsp, 20h
0x140009464  pop     rbx
0x140009465  retn
0x140009466  mov     ecx, ebx
0x140009468  add     rsp, 20h
0x14000946c  pop     rbx
0x14000946d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
