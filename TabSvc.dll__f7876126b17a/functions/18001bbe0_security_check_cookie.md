# __security_check_cookie

- ea: `0x18001bbe0`
- end: `0x18001bbfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `77`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010f8`
- `0x180001148`
- `0x180001420`
- `0x1800016d4`
- `0x180001778`
- `0x180001820`
- `0x180001b18`
- `0x180001c78`
- `0x180001d08`
- `0x180001dcc`
- `0x180001ec0`
- `0x180001f24`
- `0x180001f9c`
- `0x180002070`
- `0x180002134`
- `0x1800021f8`
- `0x1800022d4`
- `0x1800023cc`
- `0x1800024c0`
- `0x18000256c`
- `0x180002af0`
- `0x180002cd0`
- `0x180003170`
- `0x180003860`
- `0x18000dff0`
- `0x18000ed70`
- `0x18000f260`
- `0x18000f5d0`
- `0x18000fa00`
- `0x1800108f0`
- `0x180012060`
- `0x180012700`
- `0x180012df0`
- `0x180013240`
- `0x180013f64`
- `0x180014890`
- `0x18001506c`
- `0x180015660`
- `0x180016620`
- `0x1800169d0`
- `0x180018cd4`
- `0x180019314`
- `0x18001aa64`
- `0x18001af84`
- `0x18001d3c8`
- `0x18001d540`
- `0x18001dba4`
- `0x18001dc94`
- `0x18001decc`

## callees

- `0x18001bbe0`
- `0x18001bc10`

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
0x18001bbe0  cmp     rcx, cs:__security_cookie
0x18001bbe7  jnz     short ReportFailure
0x18001bbe9  rol     rcx, 10h
0x18001bbed  test    cx, 0FFFFh
0x18001bbf2  jnz     short RestoreRcx
0x18001bbf4  retn
0x18001bbf5  ror     rcx, 10h; StackCookie
0x18001bbf9  jmp     __report_gsfailure
```
