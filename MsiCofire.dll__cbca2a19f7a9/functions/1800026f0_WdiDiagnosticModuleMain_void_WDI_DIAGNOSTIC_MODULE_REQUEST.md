# WdiDiagnosticModuleMain(void *,WDI_DIAGNOSTIC_MODULE_REQUEST)

- ea: `0x1800026f0`
- end: `0x180002751`
- name: `?WdiDiagnosticModuleMain@@YAJPEAXW4WDI_DIAGNOSTIC_MODULE_REQUEST@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180002590`
- `0x1800026f0`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x180002734`
- `ADVAPI32!EventUnregister` at `0x180002734`

## string_xrefs

- `0x18000270f`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall WdiDiagnosticModuleMain(__int64 a1, int a2)
{
  unsigned int v2; // ebx

  if ( a1 )
  {
    v2 = 0;
    if ( a2 )
    {
      if ( a2 == 1 && HServerEtwProvider )
      {
        EventUnregister(HServerEtwProvider);
        HServerEtwProvider = 0;
      }
    }
    else
    {
      g_bDmCanceled = 0;
    }
  }
  else
  {
    v2 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WdiDiagnosticModuleMain", 118, -2147024809);
  }
  return v2;
}

```

## disassembly

```asm
0x1800026f0  push    rbx
0x1800026f2  sub     rsp, 30h
0x1800026f6  test    rcx, rcx
0x1800026f9  jnz     short loc_18000271D
0x1800026fb  mov     ebx, 80070057h
0x180002700  lea     r9d, [rcx+76h]
0x180002704  lea     r8, aWdidiagnosticm_0; "WdiDiagnosticModuleMain"
0x18000270b  mov     [rsp+38h+var_18], ebx
0x18000270f  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180002716  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x18000271b  jmp     short loc_180002749
0x18000271d  xor     ebx, ebx
0x18000271f  test    edx, edx
0x180002721  jz      short loc_180002743
0x180002723  cmp     edx, 1
0x180002726  jnz     short loc_180002749
0x180002728  mov     rcx, cs:HServerEtwProvider; RegHandle
0x18000272f  test    rcx, rcx
0x180002732  jz      short loc_180002749
0x180002734  call    cs:__imp_EventUnregister
0x18000273a  mov     cs:HServerEtwProvider, rbx
0x180002741  jmp     short loc_180002749
0x180002743  mov     cs:g_bDmCanceled, ebx
0x180002749  mov     eax, ebx
0x18000274b  add     rsp, 30h
0x18000274f  pop     rbx
0x180002750  retn
```
