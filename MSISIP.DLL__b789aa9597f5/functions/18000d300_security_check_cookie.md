# __security_check_cookie

- ea: `0x18000d300`
- end: `0x18000d31e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010a8`
- `0x1800011c0`
- `0x1800022b0`
- `0x180003370`
- `0x180003a70`
- `0x1800051d0`
- `0x180005a30`
- `0x1800064b0`
- `0x1800070cc`
- `0x180007450`
- `0x180007640`
- `0x1800077a8`
- `0x180007910`
- `0x180007b28`
- `0x1800080dc`
- `0x180008fc4`
- `0x180009194`
- `0x18000a780`
- `0x18000aa28`
- `0x18000b0c4`
- `0x18000b3e8`
- `0x18000bff0`
- `0x18000d1dc`

## callees

- `0x18000a3b0`
- `0x18000d300`

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
0x18000d300  cmp     rcx, cs:__security_cookie
0x18000d307  jnz     short ReportFailure
0x18000d309  rol     rcx, 10h
0x18000d30d  test    cx, 0FFFFh
0x18000d312  jnz     short RestoreRcx
0x18000d314  retn
0x18000d315  ror     rcx, 10h
0x18000d319  jmp     __report_gsfailure
```
