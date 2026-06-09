# __security_check_cookie

- ea: `0x180002c00`
- end: `0x180002c1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `43`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010f0`
- `0x1800011b0`
- `0x180001464`
- `0x18000175c`
- `0x180001988`
- `0x180001ac0`
- `0x180001b84`
- `0x180001c78`
- `0x180002240`
- `0x1800024c0`
- `0x1800030a4`
- `0x180003ae0`
- `0x180003f30`
- `0x18000402c`
- `0x180004e58`
- `0x180004fc4`
- `0x180005194`
- `0x180005904`
- `0x180005d00`
- `0x18000730c`
- `0x180007a5c`
- `0x180008bf0`
- `0x180009ca0`
- `0x180009ea8`
- `0x18000a148`
- `0x18000a440`
- `0x18000d0fc`
- `0x18000d5ec`
- `0x18000e47c`
- `0x18000fc74`
- `0x18000fe58`
- `0x1800118d4`
- `0x180011a84`
- `0x180011e50`
- `0x180012ec0`
- `0x180013540`
- `0x1800161f8`
- `0x180016b6c`
- `0x180017834`
- `0x180018a70`
- `0x1800199d0`
- `0x180019e10`

## callees

- `0x180002c00`
- `0x180003560`

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
0x180002c00  cmp     rcx, cs:__security_cookie
0x180002c07  jnz     short ReportFailure
0x180002c09  rol     rcx, 10h
0x180002c0d  test    cx, 0FFFFh
0x180002c12  jnz     short RestoreRcx
0x180002c14  retn
0x180002c15  ror     rcx, 10h; StackCookie
0x180002c19  jmp     __report_gsfailure
```
