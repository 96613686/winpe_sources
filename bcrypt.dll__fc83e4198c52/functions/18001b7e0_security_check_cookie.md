# __security_check_cookie

- ea: `0x18001b7e0`
- end: `0x18001b7fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `57`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010ac`
- `0x180001168`
- `0x180001590`
- `0x180001dd0`
- `0x180002040`
- `0x1800023f0`
- `0x180002bd0`
- `0x1800030a0`
- `0x1800049a0`
- `0x1800070d0`
- `0x18000997c`
- `0x18000b0c4`
- `0x18000b824`
- `0x18000bba0`
- `0x18000c1e0`
- `0x18000cb10`
- `0x18000d550`
- `0x18000d994`
- `0x18000dca4`
- `0x18000e910`
- `0x18000fb30`
- `0x1800101c0`
- `0x180010680`
- `0x18001181c`
- `0x180011ea8`
- `0x180012780`
- `0x180012f40`
- `0x18001316c`
- `0x180013330`
- `0x180013510`
- `0x180013720`
- `0x1800138c0`
- `0x180014510`
- `0x180014740`
- `0x180014990`
- `0x180015a7c`
- `0x180015db4`
- `0x180017abc`
- `0x180017c5c`
- `0x180017dd0`
- `0x180017f48`
- `0x180018460`
- `0x1800186e0`
- `0x180018860`
- `0x180018a00`
- `0x180018b80`
- `0x180018e90`
- `0x180019070`
- `0x1800192a0`
- `0x180019500`

## callees

- `0x180013b00`
- `0x18001b7e0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x18001b7e0  cmp     rcx, cs:__security_cookie
0x18001b7e7  jnz     short loc_18001B7F9
0x18001b7e9  rol     rcx, 10h
0x18001b7ed  test    cx, 0FFFFh
0x18001b7f2  jnz     short loc_18001B7F5
0x18001b7f4  retn
0x18001b7f5  ror     rcx, 10h
0x18001b7f9  jmp     __report_gsfailure
```
