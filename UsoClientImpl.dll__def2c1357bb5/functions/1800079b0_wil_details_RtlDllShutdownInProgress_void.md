# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800079b0`
- end: `0x180007a0f`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800079b0`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079ee`

## string_xrefs

- `0x1800079d0`: `ntdll.dll`
- `0x1800079e4`: `RtlDllShutdownInProgress`

## pseudocode

```c
char __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC ProcAddress; // rax
  char v2; // bl
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  v2 = 0;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  return v2;
}

```

## disassembly

```asm
0x1800079b0  push    rbx
0x1800079b2  sub     rsp, 20h
0x1800079b6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800079bd  xor     ebx, ebx
0x1800079bf  test    rax, rax
0x1800079c2  jnz     short loc_180007A00
0x1800079c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800079cb  test    rax, rax
0x1800079ce  jnz     short loc_1800079E4
0x1800079d0  lea     rcx, ModuleName; "ntdll.dll"
0x1800079d7  call    cs:__imp_GetModuleHandleW
0x1800079dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800079e4  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800079eb  mov     rcx, rax; hModule
0x1800079ee  call    cs:__imp_GetProcAddress
0x1800079f4  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800079fb  test    rax, rax
0x1800079fe  jz      short loc_180007A07
0x180007a00  call    _guard_dispatch_icall
0x180007a05  mov     bl, al
0x180007a07  mov     al, bl
0x180007a09  add     rsp, 20h
0x180007a0d  pop     rbx
0x180007a0e  retn
```
