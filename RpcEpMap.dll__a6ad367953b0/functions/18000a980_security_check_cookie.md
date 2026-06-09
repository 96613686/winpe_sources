# __security_check_cookie

- ea: `0x18000a980`
- end: `0x18000a99e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001220`
- `0x1800012c4`
- `0x1800018a0`
- `0x1800023a8`
- `0x180002bc0`
- `0x1800033f0`
- `0x180003a1c`
- `0x180004f94`
- `0x180005428`
- `0x180005994`
- `0x1800064e8`
- `0x180006758`
- `0x180007094`
- `0x180007fb0`
- `0x18000804c`
- `0x180008570`
- `0x18000888c`
- `0x180008df0`
- `0x180009128`
- `0x1800099b8`
- `0x180009acc`
- `0x18000a8f0`

## callees

- `0x1800060f0`
- `0x18000a980`

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
0x18000a980  cmp     rcx, cs:__security_cookie
0x18000a987  jnz     short ReportFailure
0x18000a989  rol     rcx, 10h
0x18000a98d  test    cx, 0FFFFh
0x18000a992  jnz     short RestoreRcx
0x18000a994  retn
0x18000a995  ror     rcx, 10h
0x18000a999  jmp     __report_gsfailure
```
