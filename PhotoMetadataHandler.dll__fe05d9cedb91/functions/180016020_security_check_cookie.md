# __security_check_cookie

- ea: `0x180016020`
- end: `0x18001603e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `61`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b9c`
- `0x1800044f0`
- `0x180005360`
- `0x180005b48`
- `0x1800064f0`
- `0x180006ae8`
- `0x180006da4`
- `0x1800074e0`
- `0x180009870`
- `0x18000c58c`
- `0x18000c7bc`
- `0x18000dda0`
- `0x18000e3d0`
- `0x18000e950`
- `0x18000efb4`
- `0x18000f6b4`
- `0x18000ff94`
- `0x180010390`
- `0x180010830`
- `0x180012afc`
- `0x180012c54`
- `0x1800130bc`
- `0x18001329c`
- `0x180013624`
- `0x1800136c0`
- `0x180013c88`
- `0x180013e70`
- `0x180017adc`
- `0x18001833c`
- `0x180018d5c`
- `0x180019058`
- `0x18001916c`
- `0x1800192e0`
- `0x180019528`
- `0x180019c24`
- `0x180019e1c`
- `0x18001a094`
- `0x18001b5e0`
- `0x18001b95c`
- `0x18001bf8c`
- `0x18001d2f8`
- `0x18001db40`
- `0x18001ec58`
- `0x18001ed94`
- `0x18001f2c0`
- `0x18001f660`
- `0x18001f724`
- `0x18001fb3c`
- `0x18002061c`
- `0x180022224`

## callees

- `0x180016020`
- `0x180016050`

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
0x180016020  cmp     rcx, cs:__security_cookie
0x180016027  jnz     short ReportFailure
0x180016029  rol     rcx, 10h
0x18001602d  test    cx, 0FFFFh
0x180016032  jnz     short RestoreRcx
0x180016034  retn
0x180016035  ror     rcx, 10h; StackCookie
0x180016039  jmp     __report_gsfailure
```
