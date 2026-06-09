# DllMain

- ea: `0x1800aff28`
- end: `0x1800aff51`
- name: `DllMain`
- size: `41`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800aa4c4`

## callees

- `0x180001930`
- `0x1800aff28`
- `0x1800b85a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800aff35`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800aff35`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  DWriteTraceLogging *v3; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      DWriteTraceLogging::RegisterServerSideTraceLogging(v3);
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x1800aff28  sub     rsp, 28h
0x1800aff2c  test    edx, edx
0x1800aff2e  jz      short loc_1800AFF42
0x1800aff30  cmp     edx, 1
0x1800aff33  jnz     short loc_1800AFF47
0x1800aff35  call    cs:__imp_DisableThreadLibraryCalls
0x1800aff3b  call    ?RegisterServerSideTraceLogging@DWriteTraceLogging@@YAXXZ; DWriteTraceLogging::RegisterServerSideTraceLogging(void)
0x1800aff40  jmp     short loc_1800AFF47
0x1800aff42  call    TraceLoggingUnregister_EventUnregister
0x1800aff47  mov     eax, 1
0x1800aff4c  add     rsp, 28h
0x1800aff50  retn
```
