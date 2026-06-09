# __security_check_cookie

- ea: `0x1800036a0`
- end: `0x1800036be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013b4`
- `0x180001478`
- `0x180001734`
- `0x180001b14`
- `0x180002900`
- `0x18000298c`
- `0x180002a48`
- `0x180002bdc`
- `0x180002c84`
- `0x180002d34`
- `0x180002e00`
- `0x180002fe0`
- `0x1800046fc`
- `0x180004990`
- `0x1800050c8`
- `0x180005260`
- `0x180005630`
- `0x180005a2c`
- `0x180006f30`
- `0x1800074d0`
- `0x18000818c`
- `0x1800094f4`
- `0x180009b68`
- `0x18000ae0c`
- `0x180012960`
- `0x1800148f8`
- `0x180014df0`
- `0x18001984c`
- `0x18001a35c`
- `0x18001a444`
- `0x18001a4c8`
- `0x18001a54c`
- `0x18001a5d0`
- `0x18001b060`
- `0x18001b300`

## callees

- `0x1800036a0`
- `0x180003c60`

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
0x1800036a0  cmp     rcx, cs:__security_cookie
0x1800036a7  jnz     short ReportFailure
0x1800036a9  rol     rcx, 10h
0x1800036ad  test    cx, 0FFFFh
0x1800036b2  jnz     short RestoreRcx
0x1800036b4  retn
0x1800036b5  ror     rcx, 10h; StackCookie
0x1800036b9  jmp     __report_gsfailure
```
