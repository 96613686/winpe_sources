# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007460`
- end: `0x1800074ba`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007460`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000749a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000749a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007483`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007483`

## string_xrefs

- `0x18000747c`: `ntdll.dll`
- `0x180007490`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180007460  sub     rsp, 28h
0x180007464  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000746b  test    rax, rax
0x18000746e  jnz     short loc_1800074B1
0x180007470  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007477  test    rax, rax
0x18000747a  jnz     short loc_180007490
0x18000747c  lea     rcx, ModuleName; "ntdll.dll"
0x180007483  call    cs:__imp_GetModuleHandleW
0x180007489  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007490  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007497  mov     rcx, rax; hModule
0x18000749a  call    cs:__imp_GetProcAddress
0x1800074a0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800074a7  test    rax, rax
0x1800074aa  jnz     short loc_1800074B1
0x1800074ac  add     rsp, 28h
0x1800074b0  retn
0x1800074b1  add     rsp, 28h
0x1800074b5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
