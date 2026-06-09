# __security_check_cookie

- ea: `0x180004c70`
- end: `0x180004c8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002cd8`
- `0x180003dc0`
- `0x180004388`
- `0x180006894`
- `0x180006b28`
- `0x1800073a8`
- `0x1800075ac`
- `0x180007c24`
- `0x180007fe8`
- `0x1800098bc`
- `0x180009e30`
- `0x18000b978`
- `0x18000c3a8`
- `0x18000c630`
- `0x18000d178`
- `0x18000d3ec`
- `0x18000daac`
- `0x18000eb08`
- `0x18000ed24`
- `0x18000ef98`
- `0x18000f530`
- `0x1800103c0`
- `0x180010a5c`
- `0x1800116c0`
- `0x180011760`
- `0x180011890`
- `0x180011f10`
- `0x18001248c`
- `0x18001260c`
- `0x180012bbc`
- `0x180012e9c`
- `0x180013168`
- `0x180013348`
- `0x180013500`

## callees

- `0x180004c70`
- `0x180005260`

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
0x180004c70  cmp     rcx, cs:__security_cookie
0x180004c77  jnz     short ReportFailure
0x180004c79  rol     rcx, 10h
0x180004c7d  test    cx, 0FFFFh
0x180004c82  jnz     short RestoreRcx
0x180004c84  retn
0x180004c85  ror     rcx, 10h; StackCookie
0x180004c89  jmp     __report_gsfailure
```
