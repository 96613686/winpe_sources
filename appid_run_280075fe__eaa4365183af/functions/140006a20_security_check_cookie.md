# __security_check_cookie

- ea: `0x140006a20`
- end: `0x140006a3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001100`
- `0x14000178c`
- `0x14000212c`
- `0x140002708`
- `0x140002bd0`
- `0x140003598`
- `0x140003878`
- `0x140003a54`
- `0x140004f8c`
- `0x140005b48`
- `0x14000687c`
- `0x14001fe30`
- `0x14001fef0`
- `0x140020a70`
- `0x140021298`
- `0x140021924`
- `0x140021c3c`
- `0x140021d30`
- `0x140022054`
- `0x140022a10`
- `0x140022c20`
- `0x1400240a0`
- `0x140024494`
- `0x140024e30`
- `0x140024fec`
- `0x140025194`
- `0x140025560`
- `0x140025964`
- `0x140026afc`
- `0x140026e44`
- `0x140026fd0`
- `0x1400273e8`
- `0x140027560`
- `0x140028bbc`
- `0x140028c6c`
- `0x140029678`
- `0x140029714`
- `0x1400299cc`
- `0x140029db4`
- `0x14002ab78`
- `0x14002b378`
- `0x14002b5e0`
- `0x14002c450`
- `0x14002cd1c`
- `0x14002d430`
- `0x14002daa0`
- `0x14002dbbc`
- `0x14002f2f0`
- `0x14002f434`
- `0x14002fc50`

## callees

- `0x140001600`
- `0x140006a20`

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
0x140006a20  cmp     rcx, cs:__security_cookie
0x140006a27  jnz     short ReportFailure
0x140006a29  rol     rcx, 10h
0x140006a2d  test    cx, 0FFFFh
0x140006a32  jnz     short RestoreRcx
0x140006a34  retn
0x140006a35  ror     rcx, 10h; StackCookie
0x140006a39  jmp     __report_gsfailure
```
