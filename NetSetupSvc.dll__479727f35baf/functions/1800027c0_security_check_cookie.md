# __security_check_cookie

- ea: `0x1800027c0`
- end: `0x1800027de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `239`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x18000116c`
- `0x180001420`
- `0x180001734`
- `0x1800017c4`
- `0x180001abc`
- `0x180001b7c`
- `0x180001c38`
- `0x180001d2c`
- `0x180001dd8`
- `0x180002c34`
- `0x180003990`
- `0x180003c24`
- `0x180004338`
- `0x1800044d0`
- `0x1800048a4`
- `0x180004ca0`
- `0x180004f74`
- `0x1800055a4`
- `0x180005610`
- `0x1800057f0`
- `0x180006214`
- `0x180006450`
- `0x180006760`
- `0x180006a70`
- `0x18000717c`
- `0x180007324`
- `0x180007740`
- `0x1800078f8`
- `0x1800079e8`
- `0x180007bfc`
- `0x180007d80`
- `0x180007f00`
- `0x180008084`
- `0x1800082c0`
- `0x1800096f4`
- `0x1800098d0`
- `0x180009b7c`
- `0x180009cfc`
- `0x18000a1ac`
- `0x18000a2a0`
- `0x18000a4d0`
- `0x18000a570`
- `0x18000a6d4`
- `0x18000a95c`
- `0x18000aa8c`
- `0x18000abfc`
- `0x18000adb0`
- `0x18000affc`
- `0x18000b120`

## callees

- `0x1800027c0`
- `0x1800030e0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x1800027c0  cmp     rcx, cs:__security_cookie
0x1800027c7  jnz     short ReportFailure
0x1800027c9  rol     rcx, 10h
0x1800027cd  test    cx, 0FFFFh
0x1800027d2  jnz     short RestoreRcx
0x1800027d4  retn
0x1800027d5  ror     rcx, 10h; StackCookie
0x1800027d9  jmp     __report_gsfailure
```
