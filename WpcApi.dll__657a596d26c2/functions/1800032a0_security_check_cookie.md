# __security_check_cookie

- ea: `0x1800032a0`
- end: `0x1800032be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `124`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015d0`
- `0x180001660`
- `0x18000175c`
- `0x180001a00`
- `0x180002340`
- `0x180002a70`
- `0x180002af0`
- `0x180002b70`
- `0x180002bf0`
- `0x180002c70`
- `0x180002cf0`
- `0x180004120`
- `0x1800043a0`
- `0x1800048a4`
- `0x180004940`
- `0x1800049dc`
- `0x180004a78`
- `0x180004b14`
- `0x180005504`
- `0x1800057b0`
- `0x1800064a8`
- `0x180006960`
- `0x180006b30`
- `0x180006e00`
- `0x180006ee0`
- `0x180007000`
- `0x1800076e4`
- `0x180007c20`
- `0x180008440`
- `0x18000a040`
- `0x18000a2c0`
- `0x18000aa90`
- `0x18000abe0`
- `0x18000ad10`
- `0x18000aea0`
- `0x18000b808`
- `0x18000bc98`
- `0x18000bf74`
- `0x18000c164`
- `0x18000c414`
- `0x18000c648`
- `0x18000c9a0`
- `0x18000ca70`
- `0x18000cb40`
- `0x18000ccd0`
- `0x18000d150`
- `0x18000e008`
- `0x18000e0c8`

## callees

- `0x1800032a0`
- `0x1800038d0`

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
0x1800032a0  cmp     rcx, cs:__security_cookie
0x1800032a7  jnz     short ReportFailure
0x1800032a9  rol     rcx, 10h
0x1800032ad  test    cx, 0FFFFh
0x1800032b2  jnz     short RestoreRcx
0x1800032b4  retn
0x1800032b5  ror     rcx, 10h; StackCookie
0x1800032b9  jmp     __report_gsfailure
```
