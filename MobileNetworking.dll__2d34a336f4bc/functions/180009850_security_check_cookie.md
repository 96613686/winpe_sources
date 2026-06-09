# __security_check_cookie

- ea: `0x180009850`
- end: `0x18000986e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d10`
- `0x180005720`
- `0x180005c20`
- `0x180005e30`
- `0x180006340`
- `0x180006ee0`
- `0x180007170`
- `0x180008250`
- `0x180008ce0`
- `0x18000c8a0`
- `0x18000da00`
- `0x18000dc90`
- `0x18000e014`
- `0x18000e1e8`
- `0x18000e6a0`
- `0x18000e960`
- `0x18000eac4`
- `0x18000eda0`
- `0x18000f160`
- `0x18000f5d0`
- `0x18000f86c`
- `0x18000fc40`
- `0x18000fe38`
- `0x1800100fc`
- `0x180011300`
- `0x1800117c0`

## callees

- `0x180009850`
- `0x180009de0`

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
0x180009850  cmp     rcx, cs:__security_cookie
0x180009857  jnz     short ReportFailure
0x180009859  rol     rcx, 10h
0x18000985d  test    cx, 0FFFFh
0x180009862  jnz     short RestoreRcx
0x180009864  retn
0x180009865  ror     rcx, 10h; StackCookie
0x180009869  jmp     __report_gsfailure
```
