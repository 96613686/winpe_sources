# __security_check_cookie

- ea: `0x180002a70`
- end: `0x180002a8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010f4`
- `0x180001150`
- `0x180001218`
- `0x180001270`
- `0x18000131c`
- `0x1800013ac`
- `0x180001428`
- `0x18000148c`
- `0x180001524`
- `0x1800015c0`
- `0x180001670`
- `0x1800016f0`
- `0x18000178c`
- `0x180001838`
- `0x1800018b4`
- `0x180001934`
- `0x180001c40`
- `0x180001d9c`
- `0x180001e7c`
- `0x180001f74`
- `0x180002020`
- `0x18000211c`
- `0x1800021e4`
- `0x1800022ac`
- `0x180002370`
- `0x180002440`
- `0x180003cf4`
- `0x180003d8c`
- `0x1800045e0`
- `0x18000488c`
- `0x180005cc8`
- `0x18000603c`
- `0x1800061ac`
- `0x180006350`
- `0x180006598`
- `0x1800069e4`
- `0x180006d98`
- `0x18000743c`
- `0x180007534`
- `0x180008388`
- `0x1800084c4`
- `0x180008798`
- `0x18000891c`
- `0x180009f48`
- `0x18000ab60`
- `0x18000af0c`
- `0x18000b668`
- `0x18000bd34`
- `0x18000c154`

## callees

- `0x180002a70`
- `0x180002fc0`

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
0x180002a70  cmp     rcx, cs:__security_cookie
0x180002a77  jnz     short ReportFailure
0x180002a79  rol     rcx, 10h
0x180002a7d  test    cx, 0FFFFh
0x180002a82  jnz     short RestoreRcx
0x180002a84  retn
0x180002a85  ror     rcx, 10h; StackCookie
0x180002a89  jmp     __report_gsfailure
```
