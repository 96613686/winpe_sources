# __security_check_cookie

- ea: `0x1800021d0`
- end: `0x1800021ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `61`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015b4`
- `0x1800017d8`
- `0x180001820`
- `0x1800018cc`
- `0x18000192c`
- `0x1800019a0`
- `0x180001a34`
- `0x1800032f4`
- `0x18000367c`
- `0x180003c08`
- `0x180003d04`
- `0x180004da8`
- `0x180004f14`
- `0x180005150`
- `0x180005628`
- `0x180005814`
- `0x180006674`
- `0x180006ab0`
- `0x1800083b4`
- `0x180008b0c`
- `0x18000a610`
- `0x18000b490`
- `0x18000b698`
- `0x18000ba2c`
- `0x18000c048`
- `0x18000cad0`
- `0x18000cc8c`
- `0x18000d074`
- `0x18000d48c`
- `0x18000d4f4`
- `0x18000d8a8`
- `0x18000d940`
- `0x18000fbc4`
- `0x18000fee0`
- `0x18001317c`
- `0x1800137e4`
- `0x180013a2c`
- `0x180017ec4`
- `0x1800181f0`
- `0x180019550`
- `0x180019898`
- `0x18001bb84`
- `0x18001bfe4`
- `0x18001c150`
- `0x18001c588`
- `0x18001d134`
- `0x18001d5b8`
- `0x18001d670`

## callees

- `0x1800021d0`
- `0x1800027d0`

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
0x1800021d0  cmp     rcx, cs:__security_cookie
0x1800021d7  jnz     short ReportFailure
0x1800021d9  rol     rcx, 10h
0x1800021dd  test    cx, 0FFFFh
0x1800021e2  jnz     short RestoreRcx
0x1800021e4  retn
0x1800021e5  ror     rcx, 10h; StackCookie
0x1800021e9  jmp     __report_gsfailure
```
