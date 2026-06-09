# __security_check_cookie

- ea: `0x140005c20`
- end: `0x140005c3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `103`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001000`
- `0x1400010ac`
- `0x140001440`
- `0x140001724`
- `0x140001ad4`
- `0x1400029b0`
- `0x140002af0`
- `0x140002f34`
- `0x1400030e4`
- `0x140003254`
- `0x140003380`
- `0x140003414`
- `0x14000355c`
- `0x140003a24`
- `0x140003c50`
- `0x140003de4`
- `0x140003f6c`
- `0x140004440`
- `0x140004740`
- `0x1400047e0`
- `0x140004dc0`
- `0x140004f34`
- `0x140004fac`
- `0x1400050f8`
- `0x14000513c`
- `0x1400051d0`
- `0x14000530c`
- `0x140006048`
- `0x1400070ec`
- `0x1400071f0`
- `0x140008a3c`
- `0x140008f40`
- `0x1400096f0`
- `0x14000ab70`
- `0x14000bc90`
- `0x14000bfd0`
- `0x14000f240`
- `0x14000f6b0`
- `0x140010784`
- `0x1400109d8`
- `0x140011758`
- `0x140011cfc`
- `0x140015480`
- `0x1400158fc`
- `0x140016664`
- `0x140016a94`
- `0x140018b74`
- `0x14001a20c`
- `0x14001a6a0`
- `0x14001a7a8`

## callees

- `0x140005c20`
- `0x140006610`

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
0x140005c20  cmp     rcx, cs:__security_cookie
0x140005c27  jnz     short ReportFailure
0x140005c29  rol     rcx, 10h
0x140005c2d  test    cx, 0FFFFh
0x140005c32  jnz     short RestoreRcx
0x140005c34  retn
0x140005c35  ror     rcx, 10h
0x140005c39  jmp     __report_gsfailure
```
