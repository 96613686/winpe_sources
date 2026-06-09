# __security_check_cookie

- ea: `0x180015af0`
- end: `0x180015b0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `62`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001208`
- `0x180003db0`
- `0x180004140`
- `0x180004570`
- `0x180006540`
- `0x180006b30`
- `0x180007350`
- `0x1800074d0`
- `0x180007be0`
- `0x180008724`
- `0x1800087e8`
- `0x180009460`
- `0x180009bb0`
- `0x180009ee0`
- `0x18000a970`
- `0x18000ae30`
- `0x18000b190`
- `0x18000b3cc`
- `0x18000bcc0`
- `0x18000c4c0`
- `0x18000ce2c`
- `0x18000ceac`
- `0x18000cf2c`
- `0x18000d610`
- `0x18000db08`
- `0x18000de1c`
- `0x18000e538`
- `0x18000e8a4`
- `0x18000ea30`
- `0x18000ed78`
- `0x18000ee54`
- `0x18000f648`
- `0x18000f888`
- `0x18000f978`
- `0x18000fc28`
- `0x180010080`
- `0x1800110a0`
- `0x180011874`
- `0x1800128fc`
- `0x180012ac0`
- `0x180013bf0`
- `0x180013c70`
- `0x180013cf0`
- `0x180013d70`
- `0x180013df0`
- `0x180013e70`
- `0x180013ef0`
- `0x180014a7c`
- `0x180014f50`

## callees

- `0x180015af0`
- `0x180016430`

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
0x180015af0  cmp     rcx, cs:__security_cookie
0x180015af7  jnz     short ReportFailure
0x180015af9  rol     rcx, 10h
0x180015afd  test    cx, 0FFFFh
0x180015b02  jnz     short RestoreRcx
0x180015b04  retn
0x180015b05  ror     rcx, 10h; StackCookie
0x180015b09  jmp     __report_gsfailure
```
