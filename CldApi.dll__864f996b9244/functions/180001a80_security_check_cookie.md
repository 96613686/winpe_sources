# __security_check_cookie

- ea: `0x180001a80`
- end: `0x180001a9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001138`
- `0x18000155c`
- `0x180002630`
- `0x180002d20`
- `0x1800031d0`
- `0x180003be0`
- `0x180004ac0`
- `0x180006060`
- `0x1800073b0`
- `0x1800079c0`
- `0x180007cf0`
- `0x180009f88`
- `0x18000a0d0`
- `0x18000a234`
- `0x18000a4c8`
- `0x18000a608`
- `0x18000a794`
- `0x18000a8f4`
- `0x18000aa48`
- `0x18000b080`
- `0x18000b8e0`
- `0x18000d7b0`
- `0x18000f330`
- `0x18000feb8`
- `0x1800118a4`
- `0x1800119c4`
- `0x180011e18`
- `0x180017728`
- `0x180018404`
- `0x180018680`
- `0x1800189d0`
- `0x180018f70`
- `0x180019384`
- `0x1800196e4`
- `0x18001b010`
- `0x18001bd74`

## callees

- `0x180001a80`
- `0x180001fb0`

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
0x180001a80  cmp     rcx, cs:__security_cookie
0x180001a87  jnz     short ReportFailure
0x180001a89  rol     rcx, 10h
0x180001a8d  test    cx, 0FFFFh
0x180001a92  jnz     short RestoreRcx
0x180001a94  retn
0x180001a95  ror     rcx, 10h; StackCookie
0x180001a99  jmp     __report_gsfailure
```
