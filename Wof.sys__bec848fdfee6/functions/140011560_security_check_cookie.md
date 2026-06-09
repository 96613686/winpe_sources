# __security_check_cookie

- ea: `0x140011560`
- end: `0x14001157e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `56`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140002b50`
- `0x140002fcc`
- `0x1400059a4`
- `0x140005e1c`
- `0x140006080`
- `0x1400075c0`
- `0x140008d30`
- `0x140009910`
- `0x14000a35c`
- `0x14000ac54`
- `0x14000ae04`
- `0x14000b1e8`
- `0x14000b4a4`
- `0x14000d470`
- `0x14000f2e4`
- `0x14000f4f8`
- `0x14000f970`
- `0x140010954`
- `0x140010f74`
- `0x14001145c`
- `0x140022048`
- `0x140023ec4`
- `0x140025bf0`
- `0x140026360`
- `0x140026440`
- `0x140027870`
- `0x140027ffc`
- `0x140028924`
- `0x140028f44`
- `0x140029ca0`
- `0x140029db0`
- `0x140029e9c`
- `0x140029f78`
- `0x14002a090`
- `0x14002a750`
- `0x14002aa88`
- `0x14002c58c`
- `0x14002d990`
- `0x14002dd10`
- `0x14002e008`
- `0x14002e244`
- `0x14002e5c8`
- `0x14002eaa0`
- `0x140031380`
- `0x140032ee4`
- `0x1400331d0`
- `0x140035118`
- `0x140036954`
- `0x140039aa0`

## callees

- `0x14000da00`
- `0x140011560`

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
0x140011560  cmp     rcx, cs:__security_cookie
0x140011567  jnz     short ReportFailure
0x140011569  rol     rcx, 10h
0x14001156d  test    cx, 0FFFFh
0x140011572  jnz     short RestoreRcx
0x140011574  retn
0x140011575  ror     rcx, 10h; StackCookie
0x140011579  jmp     __report_gsfailure
```
