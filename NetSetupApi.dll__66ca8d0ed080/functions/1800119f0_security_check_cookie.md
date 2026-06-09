# __security_check_cookie

- ea: `0x1800119f0`
- end: `0x180011a0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `73`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001210`
- `0x180001390`
- `0x180001600`
- `0x1800035ac`
- `0x180003970`
- `0x180003b90`
- `0x180004120`
- `0x180004260`
- `0x180004430`
- `0x180004b20`
- `0x180004dbc`
- `0x180005844`
- `0x180005edc`
- `0x180006208`
- `0x180006880`
- `0x180006af8`
- `0x1800079b4`
- `0x180007af4`
- `0x180009028`
- `0x180009118`
- `0x18000966c`
- `0x180009848`
- `0x180009b94`
- `0x180009eb8`
- `0x18000a18c`
- `0x18000a5fc`
- `0x18000a7c0`
- `0x18000ae68`
- `0x18000aff0`
- `0x18000bb10`
- `0x18000bcc4`
- `0x18000bd18`
- `0x18000be20`
- `0x18000c188`
- `0x18000c354`
- `0x18000c4a8`
- `0x18000c660`
- `0x18000c760`
- `0x18000cadc`
- `0x18000d0a0`
- `0x18000d18c`
- `0x18000d800`
- `0x18000dda4`
- `0x18000e0d8`
- `0x18000e70c`
- `0x18000e90c`
- `0x18000ed54`
- `0x18000eec0`
- `0x18000efe8`

## callees

- `0x180008bb0`
- `0x1800119f0`

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
0x1800119f0  cmp     rcx, cs:__security_cookie
0x1800119f7  jnz     short ReportFailure
0x1800119f9  rol     rcx, 10h
0x1800119fd  test    cx, 0FFFFh
0x180011a02  jnz     short RestoreRcx
0x180011a04  retn
0x180011a05  ror     rcx, 10h
0x180011a09  jmp     __report_gsfailure
```
