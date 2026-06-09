# __security_check_cookie

- ea: `0x14005a8a0`
- end: `0x14005a8be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `162`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001350`
- `0x140001ae0`
- `0x140002c50`
- `0x140003964`
- `0x140003bf0`
- `0x1400049ac`
- `0x140004de0`
- `0x140009ccc`
- `0x14000c1b0`
- `0x14000c370`
- `0x14000d27c`
- `0x14000ed8c`
- `0x14000efc0`
- `0x14000fcac`
- `0x140010688`
- `0x1400107b0`
- `0x140011370`
- `0x140011cd0`
- `0x140012c40`
- `0x140012eb4`
- `0x140013100`
- `0x140014950`
- `0x140015468`
- `0x140015550`
- `0x1400156a0`
- `0x140015d10`
- `0x140016b18`
- `0x140017390`
- `0x140018b1c`
- `0x140019010`
- `0x140019530`
- `0x1400196c0`
- `0x140019d90`
- `0x14001a350`
- `0x14001af00`
- `0x14001b170`
- `0x14001b2a0`
- `0x14001bc70`
- `0x14001bd18`
- `0x14001bdc8`
- `0x14001bef0`
- `0x14001c0e0`
- `0x14001c580`
- `0x14001cc00`
- `0x14001ea4c`
- `0x14001ef60`
- `0x14001f834`
- `0x140020830`
- `0x140020958`
- `0x140021ed4`

## callees

- `0x14005a8a0`
- `0x14005acf0`

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
0x14005a8a0  cmp     rcx, cs:__security_cookie
0x14005a8a7  jnz     short ReportFailure
0x14005a8a9  rol     rcx, 10h
0x14005a8ad  test    cx, 0FFFFh
0x14005a8b2  jnz     short RestoreRcx
0x14005a8b4  retn
0x14005a8b5  ror     rcx, 10h; StackCookie
0x14005a8b9  jmp     __report_gsfailure
```
