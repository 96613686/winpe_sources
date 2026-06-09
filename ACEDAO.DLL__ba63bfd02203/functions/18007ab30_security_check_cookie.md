# __security_check_cookie

- ea: `0x18007ab30`
- end: `0x18007ab4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `111`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000443c`
- `0x1800084a0`
- `0x180009290`
- `0x18000df24`
- `0x1800100f0`
- `0x1800122bc`
- `0x1800134e0`
- `0x18001448c`
- `0x180014ef0`
- `0x180015210`
- `0x180015c60`
- `0x1800160a0`
- `0x180017210`
- `0x180019f7c`
- `0x18001a2c0`
- `0x18001ad80`
- `0x1800209a4`
- `0x180023860`
- `0x1800259a0`
- `0x1800318b8`
- `0x180033c30`
- `0x18003eec0`
- `0x18003fc90`
- `0x1800406d0`
- `0x180040b80`
- `0x1800413e0`
- `0x180043630`
- `0x1800445c8`
- `0x180044e30`
- `0x1800452c8`
- `0x180045550`
- `0x180045814`
- `0x1800459e0`
- `0x180045f0c`
- `0x180046160`
- `0x180047694`
- `0x180047f1c`
- `0x180048784`
- `0x1800489ac`
- `0x180048d84`
- `0x1800495f0`
- `0x1800498b0`
- `0x180049da0`
- `0x18004ce94`
- `0x18004e258`
- `0x18004e814`
- `0x18004eb54`
- `0x18004eff4`
- `0x18004fbc0`
- `0x1800508c8`

## callees

- `0x18007ab30`
- `0x18007af60`

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
0x18007ab30  cmp     rcx, cs:__security_cookie
0x18007ab37  jnz     short ReportFailure
0x18007ab39  rol     rcx, 10h
0x18007ab3d  test    cx, 0FFFFh
0x18007ab42  jnz     short RestoreRcx
0x18007ab44  retn
0x18007ab45  ror     rcx, 10h; StackCookie
0x18007ab49  jmp     __report_gsfailure
```
