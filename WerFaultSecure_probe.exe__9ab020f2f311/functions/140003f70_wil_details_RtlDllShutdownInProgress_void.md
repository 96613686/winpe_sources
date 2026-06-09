# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140003f70`
- end: `0x140003fc7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140003f70`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003faa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003faa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003f93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003f93`

## string_xrefs

- `0x140003f8c`: `ntdll.dll`
- `0x140003fa0`: `RtlDllShutdownInProgress`

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
0x140003f70  sub     rsp, 28h
0x140003f74  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140003f7b  test    rax, rax
0x140003f7e  jnz     short loc_140003FBC
0x140003f80  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003f87  test    rax, rax
0x140003f8a  jnz     short loc_140003FA0
0x140003f8c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140003f93  call    cs:__imp_GetModuleHandleW
0x140003f99  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003fa0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140003fa7  mov     rcx, rax; hModule
0x140003faa  call    cs:__imp_GetProcAddress
0x140003fb0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140003fb7  test    rax, rax
0x140003fba  jz      short loc_140003FC2
0x140003fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fc1  nop
0x140003fc2  add     rsp, 28h
0x140003fc6  retn
```
