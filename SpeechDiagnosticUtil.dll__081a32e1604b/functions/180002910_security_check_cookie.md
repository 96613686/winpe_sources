# __security_check_cookie

- ea: `0x180002910`
- end: `0x18000292e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016e4`
- `0x1800019f8`
- `0x180001d24`
- `0x180002050`
- `0x1800023a4`
- `0x180003ae0`
- `0x180003da0`
- `0x1800040b4`
- `0x180004624`
- `0x180004a68`
- `0x180005434`
- `0x180005f94`
- `0x180006630`
- `0x18000713c`
- `0x1800071fc`
- `0x1800073f4`
- `0x180007714`
- `0x180007c88`
- `0x180007e38`
- `0x180008040`
- `0x180008190`
- `0x1800082d0`
- `0x1800084a0`
- `0x1800087b0`
- `0x180008d10`
- `0x180008fe0`
- `0x180009330`
- `0x180009df0`
- `0x180009f44`
- `0x18000a098`
- `0x18000a1ec`
- `0x18000a340`
- `0x18000a494`
- `0x18000a5d4`
- `0x18000a714`
- `0x18000a964`
- `0x18000ac60`
- `0x18000af58`
- `0x18000b26c`
- `0x18000b590`
- `0x18000b888`
- `0x18000d2a0`
- `0x18000d8bc`
- `0x18000d93c`
- `0x18000d9f0`
- `0x18000ddf4`
- `0x18000f710`
- `0x18000fa9c`

## callees

- `0x180002910`
- `0x180002ea0`

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
0x180002910  cmp     rcx, cs:__security_cookie
0x180002917  jnz     short ReportFailure
0x180002919  rol     rcx, 10h
0x18000291d  test    cx, 0FFFFh
0x180002922  jnz     short RestoreRcx
0x180002924  retn
0x180002925  ror     rcx, 10h; StackCookie
0x180002929  jmp     __report_gsfailure
```
