# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800075f0`
- end: `0x18000764a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800075f0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007613`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007613`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000762a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000762a`

## string_xrefs

- `0x18000760c`: `ntdll.dll`
- `0x180007620`: `RtlDllShutdownInProgress`

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
0x1800075f0  sub     rsp, 28h
0x1800075f4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800075fb  test    rax, rax
0x1800075fe  jnz     short loc_180007641
0x180007600  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007607  test    rax, rax
0x18000760a  jnz     short loc_180007620
0x18000760c  lea     rcx, ModuleName; "ntdll.dll"
0x180007613  call    cs:__imp_GetModuleHandleW
0x180007619  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007620  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007627  mov     rcx, rax; hModule
0x18000762a  call    cs:__imp_GetProcAddress
0x180007630  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007637  test    rax, rax
0x18000763a  jnz     short loc_180007641
0x18000763c  add     rsp, 28h
0x180007640  retn
0x180007641  add     rsp, 28h
0x180007645  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
