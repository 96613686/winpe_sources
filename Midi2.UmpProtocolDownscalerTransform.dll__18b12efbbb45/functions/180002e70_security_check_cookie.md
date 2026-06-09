# __security_check_cookie

- ea: `0x180002e70`
- end: `0x180002e8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x180001b30`
- `0x180001d20`
- `0x180002040`
- `0x180002550`
- `0x1800027c0`
- `0x180002930`
- `0x180003404`
- `0x1800040d8`
- `0x18000436c`
- `0x180004b58`
- `0x180005290`
- `0x180005ac0`
- `0x180006474`
- `0x1800067f0`
- `0x18000746c`
- `0x18000792c`
- `0x180007a7c`
- `0x180007c0c`
- `0x180007dec`
- `0x180009200`
- `0x18000941c`
- `0x1800096b4`
- `0x180009bc0`
- `0x180009ebc`
- `0x18000a170`
- `0x18000bc5c`
- `0x18000d940`
- `0x18000e640`
- `0x18000e950`

## callees

- `0x180002e70`
- `0x180002ea0`

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
0x180002e70  cmp     rcx, cs:__security_cookie
0x180002e77  jnz     short ReportFailure
0x180002e79  rol     rcx, 10h
0x180002e7d  test    cx, 0FFFFh
0x180002e82  jnz     short RestoreRcx
0x180002e84  retn
0x180002e85  ror     rcx, 10h; StackCookie
0x180002e89  jmp     __report_gsfailure
```
