# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140002c30`
- end: `0x140002c8f`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `char __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140002c30`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140002c6e`
- `KERNEL32!GetProcAddress` at `0x140002c6e`
- `KERNEL32!GetModuleHandleW` at `0x140002c57`
- `KERNEL32!GetModuleHandleW` at `0x140002c57`

## string_xrefs

- `0x140002c50`: `ntdll.dll`
- `0x140002c64`: `RtlDllShutdownInProgress`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x140002c30  push    rbx
0x140002c32  sub     rsp, 20h
0x140002c36  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140002c3d  xor     ebx, ebx
0x140002c3f  test    rax, rax
0x140002c42  jnz     short loc_140002C80
0x140002c44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002c4b  test    rax, rax
0x140002c4e  jnz     short loc_140002C64
0x140002c50  lea     rcx, ModuleName; "ntdll.dll"
0x140002c57  call    cs:__imp_GetModuleHandleW
0x140002c5d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002c64  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140002c6b  mov     rcx, rax; hModule
0x140002c6e  call    cs:__imp_GetProcAddress
0x140002c74  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140002c7b  test    rax, rax
0x140002c7e  jz      short loc_140002C87
0x140002c80  call    _guard_dispatch_icall
0x140002c85  mov     bl, al
0x140002c87  mov     al, bl
0x140002c89  add     rsp, 20h
0x140002c8d  pop     rbx
0x140002c8e  retn
```
