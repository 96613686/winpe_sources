# __security_check_cookie

- ea: `0x180001720`
- end: `0x18000173e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005328`
- `0x1800053e4`
- `0x1800056e0`
- `0x180005934`
- `0x180005ee0`
- `0x1800063c4`
- `0x18000725c`
- `0x1800072f4`
- `0x18000743c`
- `0x180007a34`
- `0x180007cd0`
- `0x180008efc`
- `0x180009064`
- `0x180009420`
- `0x1800096cc`
- `0x18000a22c`
- `0x18000a3ac`
- `0x18000b174`
- `0x18000b5bc`
- `0x18000bf6c`
- `0x18000c5ec`
- `0x18000d3ac`
- `0x18000da6c`
- `0x18000e148`
- `0x18000e344`
- `0x18000e458`
- `0x18000e660`
- `0x18000e810`
- `0x18000fb80`
- `0x1800102ec`
- `0x1800105bc`
- `0x180010834`
- `0x180011380`
- `0x180011568`
- `0x18001329c`
- `0x180013330`
- `0x180013460`
- `0x1800138f0`
- `0x180013e1c`
- `0x180014160`

## callees

- `0x180001720`
- `0x1800017f0`

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
0x180001720  cmp     rcx, cs:__security_cookie
0x180001727  jnz     short ReportFailure
0x180001729  rol     rcx, 10h
0x18000172d  test    cx, 0FFFFh
0x180001732  jnz     short RestoreRcx
0x180001734  retn
0x180001735  ror     rcx, 10h; StackCookie
0x180001739  jmp     __report_gsfailure
```
