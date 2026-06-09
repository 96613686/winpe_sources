# __security_check_cookie

- ea: `0x180001630`
- end: `0x18000164e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002bf0`
- `0x180003160`
- `0x180004624`
- `0x180004a00`
- `0x1800054e0`
- `0x180005a24`
- `0x180006908`
- `0x180006d10`
- `0x18000713c`
- `0x180007a10`
- `0x180007e98`
- `0x1800080e8`
- `0x180008570`
- `0x180008eb4`
- `0x180009ba4`
- `0x180009e04`
- `0x18000a26c`
- `0x18000a9f0`
- `0x18000abbc`
- `0x18000aef0`
- `0x18000b758`
- `0x18000bb30`
- `0x18000bd0c`
- `0x18000be6c`
- `0x18000c8d8`
- `0x18000e644`
- `0x18000e8a0`
- `0x18000f640`
- `0x18000fd6c`
- `0x1800100d0`
- `0x180010304`
- `0x180011768`
- `0x180011a04`
- `0x18001223c`
- `0x1800125e0`
- `0x1800129b0`
- `0x180013414`
- `0x18001378c`
- `0x180014418`
- `0x180014694`
- `0x180014f88`
- `0x180015d78`
- `0x18001664c`
- `0x18001688c`
- `0x180016b30`
- `0x180018c7c`
- `0x18001a5c0`

## callees

- `0x180001630`
- `0x180001bc0`

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
0x180001630  cmp     rcx, cs:__security_cookie
0x180001637  jnz     short ReportFailure
0x180001639  rol     rcx, 10h
0x18000163d  test    cx, 0FFFFh
0x180001642  jnz     short RestoreRcx
0x180001644  retn
0x180001645  ror     rcx, 10h; StackCookie
0x180001649  jmp     __report_gsfailure
```
