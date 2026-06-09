# __security_check_cookie

- ea: `0x180003560`
- end: `0x18000357e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `144`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010b0`
- `0x180001364`
- `0x18000165c`
- `0x180002ba0`
- `0x1800042cc`
- `0x18000478c`
- `0x180004a38`
- `0x180005148`
- `0x1800052e0`
- `0x1800056d4`
- `0x180005b90`
- `0x1800072c0`
- `0x1800078c0`
- `0x180007d08`
- `0x18000bdd8`
- `0x18000bedc`
- `0x18000bfe0`
- `0x18000c0e4`
- `0x18000c1e8`
- `0x18000c2ec`
- `0x18000c3f0`
- `0x18000c4f4`
- `0x18000cac0`
- `0x18000fab0`
- `0x18000fb48`
- `0x180010200`
- `0x18001046c`
- `0x1800105bc`
- `0x1800106d0`
- `0x180010890`
- `0x1800109a0`
- `0x180010cc4`
- `0x180010dc8`
- `0x180012abc`
- `0x180012ca4`
- `0x180012e8c`
- `0x180013074`
- `0x18001325c`
- `0x180013454`
- `0x18001363c`
- `0x180013824`
- `0x180013aa4`
- `0x180013d24`
- `0x180013fa4`
- `0x180014224`
- `0x1800144b8`
- `0x180014738`
- `0x1800149b8`
- `0x180014d2c`

## callees

- `0x180003560`
- `0x180003b50`

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
0x180003560  cmp     rcx, cs:__security_cookie
0x180003567  jnz     short ReportFailure
0x180003569  rol     rcx, 10h
0x18000356d  test    cx, 0FFFFh
0x180003572  jnz     short RestoreRcx
0x180003574  retn
0x180003575  ror     rcx, 10h; StackCookie
0x180003579  jmp     __report_gsfailure
```
