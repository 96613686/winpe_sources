# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180010620`
- end: `0x180010677`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180010620`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010643`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010643`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001065a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001065a`

## string_xrefs

- `0x18001063c`: `ntdll.dll`
- `0x180010650`: `RtlDllShutdownInProgress`

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
0x180010620  sub     rsp, 28h
0x180010624  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001062b  test    rax, rax
0x18001062e  jnz     short loc_18001066C
0x180010630  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010637  test    rax, rax
0x18001063a  jnz     short loc_180010650
0x18001063c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010643  call    cs:__imp_GetModuleHandleW
0x180010649  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010650  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180010657  mov     rcx, rax; hModule
0x18001065a  call    cs:__imp_GetProcAddress
0x180010660  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180010667  test    rax, rax
0x18001066a  jz      short loc_180010672
0x18001066c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010671  nop
0x180010672  add     rsp, 28h
0x180010676  retn
```
