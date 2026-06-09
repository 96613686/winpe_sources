# __security_check_cookie

- ea: `0x1800227c0`
- end: `0x1800227de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `92`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ebc`
- `0x180003f90`
- `0x1800040bc`
- `0x18000418c`
- `0x180004534`
- `0x180004bb4`
- `0x1800052a0`
- `0x180005780`
- `0x1800061f0`
- `0x1800064d0`
- `0x180008638`
- `0x180009070`
- `0x180009440`
- `0x1800098c0`
- `0x180009984`
- `0x180009a88`
- `0x180009c84`
- `0x180009da8`
- `0x18000a948`
- `0x18000adb0`
- `0x18000ae80`
- `0x18000b468`
- `0x18000b528`
- `0x18000c738`
- `0x18000cef0`
- `0x18000d510`
- `0x18000d930`
- `0x18000d9c0`
- `0x18000db80`
- `0x18000ddc0`
- `0x18000e060`
- `0x18000e73c`
- `0x18000e840`
- `0x18000eac0`
- `0x18000ef28`
- `0x18000f520`
- `0x18000f7a0`
- `0x18000fa30`
- `0x18000fb54`
- `0x18000ff6c`
- `0x1800101d0`
- `0x180010310`
- `0x180010954`
- `0x180010a78`
- `0x180010c40`
- `0x180013bbc`
- `0x180013e70`
- `0x180014438`
- `0x1800145d0`
- `0x180014984`

## callees

- `0x180013510`
- `0x1800227c0`

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
0x1800227c0  cmp     rcx, cs:__security_cookie
0x1800227c7  jnz     short ReportFailure
0x1800227c9  rol     rcx, 10h
0x1800227cd  test    cx, 0FFFFh
0x1800227d2  jnz     short RestoreRcx
0x1800227d4  retn
0x1800227d5  ror     rcx, 10h
0x1800227d9  jmp     __report_gsfailure
```
