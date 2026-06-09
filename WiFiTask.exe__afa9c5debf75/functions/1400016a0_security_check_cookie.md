# __security_check_cookie

- ea: `0x1400016a0`
- end: `0x1400016be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400029ac`
- `0x140002c48`
- `0x140003e78`
- `0x14000421c`
- `0x140004600`
- `0x140006064`
- `0x14000623c`
- `0x1400065b8`
- `0x14000728c`
- `0x140008334`
- `0x140008440`
- `0x140008e4c`
- `0x140009994`
- `0x14000a4a0`
- `0x14000ac6c`
- `0x14000ba10`
- `0x14000bb38`
- `0x14000c234`
- `0x14000e1b4`
- `0x14000ee64`
- `0x14000f1c8`
- `0x14000f45c`
- `0x140010684`
- `0x140010ca0`

## callees

- `0x1400016a0`
- `0x140001cb0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x1400016a0  cmp     rcx, cs:__security_cookie
0x1400016a7  jnz     short loc_1400016B9
0x1400016a9  rol     rcx, 10h
0x1400016ad  test    cx, 0FFFFh
0x1400016b2  jnz     short loc_1400016B5
0x1400016b4  retn
0x1400016b5  ror     rcx, 10h; StackCookie
0x1400016b9  jmp     __report_gsfailure
```
