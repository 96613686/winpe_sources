# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180010b60`
- end: `0x180010b9e`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `62`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180010b60`
- `0x180010ba4`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010b8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010b8a`

## string_xrefs

- `0x180010b83`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE NtDllModuleHandle; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  result = GetProcAddress(NtDllModuleHandle, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x180010b60  sub     rsp, 28h
0x180010b64  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180010b6b  test    rax, rax
0x180010b6e  jz      short loc_180010B7B
0x180010b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b75  nop
0x180010b76  add     rsp, 28h
0x180010b7a  retn
0x180010b7b  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180010b80  mov     rcx, rax; hModule
0x180010b83  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180010b8a  call    cs:__imp_GetProcAddress
0x180010b90  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180010b97  test    rax, rax
0x180010b9a  jnz     short loc_180010B70
0x180010b9c  jmp     short loc_180010B76
```
