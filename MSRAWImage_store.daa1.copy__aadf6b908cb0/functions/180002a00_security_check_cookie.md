# __security_check_cookie

- ea: `0x180002a00`
- end: `0x180002a1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `168`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001220`
- `0x180001288`
- `0x180001710`
- `0x180001a40`
- `0x1800020f0`
- `0x180003a0c`
- `0x180004800`
- `0x180005e68`
- `0x1800078d0`
- `0x18000adf0`
- `0x18000d370`
- `0x18000e780`
- `0x180010240`
- `0x180010410`
- `0x1800108d0`
- `0x180011720`
- `0x180013010`
- `0x180013a50`
- `0x180014a70`
- `0x180022ba0`
- `0x180024c40`
- `0x180026500`
- `0x1800276f0`
- `0x18002a750`
- `0x18002abf0`
- `0x18002b8e0`
- `0x18002cf40`
- `0x18002dc80`
- `0x18002ea30`
- `0x180032a50`
- `0x180035690`
- `0x180041d80`
- `0x1800420e0`
- `0x1800425d0`
- `0x180043230`
- `0x1800434c0`
- `0x180044eb0`
- `0x1800451f0`
- `0x180045600`
- `0x180046110`
- `0x180046300`
- `0x1800463c0`
- `0x1800467a0`
- `0x1800471e0`
- `0x1800487e0`
- `0x180048c00`
- `0x180048e20`
- `0x1800491d0`
- `0x180049aa0`

## callees

- `0x180002a00`
- `0x180003000`

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
0x180002a00  cmp     rcx, cs:__security_cookie
0x180002a07  jnz     short ReportFailure
0x180002a09  rol     rcx, 10h
0x180002a0d  test    cx, 0FFFFh
0x180002a12  jnz     short RestoreRcx
0x180002a14  retn
0x180002a15  ror     rcx, 10h; StackCookie
0x180002a19  jmp     __report_gsfailure
```
