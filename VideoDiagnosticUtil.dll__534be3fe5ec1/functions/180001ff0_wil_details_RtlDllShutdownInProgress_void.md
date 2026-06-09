# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180001ff0`
- end: `0x180002057`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `103`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001ff0`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180002030`
- `KERNEL32!GetProcAddress` at `0x180002030`
- `KERNEL32!GetModuleHandleW` at `0x180002013`
- `KERNEL32!GetModuleHandleW` at `0x180002013`

## string_xrefs

- `0x18000200c`: `ntdll.dll`
- `0x180002026`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x180001ff0  sub     rsp, 28h
0x180001ff4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180001ffb  test    rax, rax
0x180001ffe  jnz     short loc_18000204E
0x180002000  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002007  test    rax, rax
0x18000200a  jnz     short loc_180002026
0x18000200c  lea     rcx, ModuleName; "ntdll.dll"
0x180002013  call    cs:__imp_GetModuleHandleW
0x18000201a  nop     dword ptr [rax+rax+00h]
0x18000201f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002026  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000202d  mov     rcx, rax; hModule
0x180002030  call    cs:__imp_GetProcAddress
0x180002037  nop     dword ptr [rax+rax+00h]
0x18000203c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180002043  test    rax, rax
0x180002046  jnz     short loc_18000204E
0x180002048  add     rsp, 28h
0x18000204c  retn
0x18000204e  add     rsp, 28h
0x180002052  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
