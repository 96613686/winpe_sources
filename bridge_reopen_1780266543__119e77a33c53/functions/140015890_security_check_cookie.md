# __security_check_cookie

- ea: `0x140015890`
- end: `0x1400158ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001384`
- `0x140001d88`
- `0x140002570`
- `0x140002ccc`
- `0x1400036cc`
- `0x140003784`
- `0x140003e98`
- `0x14000437c`
- `0x140004498`
- `0x140004668`
- `0x140004a60`
- `0x140004c40`
- `0x140005380`
- `0x140006a20`
- `0x140007084`
- `0x140007480`
- `0x140008720`
- `0x140008be0`
- `0x140008d0c`
- `0x140008e34`
- `0x140009068`
- `0x140009408`
- `0x140009e9c`
- `0x140009f24`
- `0x14000a19c`
- `0x14000a65c`
- `0x14000a85c`
- `0x14000afe8`
- `0x14000b4f4`
- `0x14000b830`
- `0x14000bc98`
- `0x14000bd9c`
- `0x14000c104`
- `0x14000c3fc`
- `0x14000cb90`
- `0x14000d0bc`
- `0x14000d214`
- `0x14000dc24`
- `0x14000dd88`
- `0x14000dedc`
- `0x14000f490`
- `0x140010000`
- `0x140012464`
- `0x140012638`
- `0x140013330`
- `0x14001575c`
- `0x1400223a0`
- `0x140024138`

## callees

- `0x140001120`
- `0x140015890`

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
0x140015890  cmp     rcx, cs:__security_cookie
0x140015897  jnz     short ReportFailure
0x140015899  rol     rcx, 10h
0x14001589d  test    cx, 0FFFFh
0x1400158a2  jnz     short RestoreRcx
0x1400158a4  retn
0x1400158a5  ror     rcx, 10h; StackCookie
0x1400158a9  jmp     __report_gsfailure
```
