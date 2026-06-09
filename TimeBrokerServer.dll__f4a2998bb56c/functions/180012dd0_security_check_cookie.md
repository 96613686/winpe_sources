# __security_check_cookie

- ea: `0x180012dd0`
- end: `0x180012dee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000106c`
- `0x1800010e8`
- `0x1800011b0`
- `0x1800012f8`
- `0x180001500`
- `0x180001654`
- `0x180001a78`
- `0x180001c14`
- `0x180002000`
- `0x180002500`
- `0x180003700`
- `0x180003ac0`
- `0x180003cac`
- `0x1800042e8`
- `0x1800044a0`
- `0x180004be0`
- `0x180007c60`
- `0x1800085a0`
- `0x180009200`
- `0x180009750`
- `0x180009cf0`
- `0x18000aa90`
- `0x18000ba98`
- `0x18000bba0`
- `0x18000c038`
- `0x18000ca68`
- `0x18000cf38`
- `0x18000d034`
- `0x18000ef50`
- `0x18000fa10`
- `0x18000fe70`
- `0x180010350`
- `0x1800113dc`
- `0x1800118e0`
- `0x180011c20`
- `0x180013ca0`
- `0x1800140f4`
- `0x180014168`
- `0x1800147b0`
- `0x1800149d0`
- `0x180015178`
- `0x180018c8c`
- `0x180018f9c`
- `0x180019784`
- `0x180019c68`

## callees

- `0x180012dd0`
- `0x180013520`

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
0x180012dd0  cmp     rcx, cs:__security_cookie
0x180012dd7  jnz     short ReportFailure
0x180012dd9  rol     rcx, 10h
0x180012ddd  test    cx, 0FFFFh
0x180012de2  jnz     short RestoreRcx
0x180012de4  retn
0x180012de5  ror     rcx, 10h; StackCookie
0x180012de9  jmp     __report_gsfailure
```
