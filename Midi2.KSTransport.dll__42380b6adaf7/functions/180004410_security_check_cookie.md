# __security_check_cookie

- ea: `0x180004410`
- end: `0x18000442e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `102`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x1800017d0`
- `0x180001918`
- `0x1800019c0`
- `0x180001af8`
- `0x180001c20`
- `0x180001d38`
- `0x180001e88`
- `0x180001fac`
- `0x180002098`
- `0x1800021ec`
- `0x180002314`
- `0x180002454`
- `0x180002a10`
- `0x180002c00`
- `0x180003120`
- `0x180003630`
- `0x1800038a0`
- `0x180003a10`
- `0x180003c90`
- `0x180003eb0`
- `0x180004c38`
- `0x180005a7c`
- `0x180005d10`
- `0x1800066b8`
- `0x180006df0`
- `0x180007620`
- `0x180008094`
- `0x180008424`
- `0x1800090a8`
- `0x180009598`
- `0x180009804`
- `0x180009954`
- `0x180009ae4`
- `0x180009cc4`
- `0x18000b0f0`
- `0x18000b3cc`
- `0x18000b684`
- `0x18000bd00`
- `0x18000d4f0`
- `0x18000dc7c`
- `0x18000fb5c`
- `0x1800124c8`
- `0x18001b7a0`
- `0x18001e8a0`
- `0x18001eeb8`
- `0x18001f7e8`
- `0x18001f8e0`

## callees

- `0x180004410`
- `0x180004440`

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
0x180004410  cmp     rcx, cs:__security_cookie
0x180004417  jnz     short ReportFailure
0x180004419  rol     rcx, 10h
0x18000441d  test    cx, 0FFFFh
0x180004422  jnz     short RestoreRcx
0x180004424  retn
0x180004425  ror     rcx, 10h; StackCookie
0x180004429  jmp     __report_gsfailure
```
