# __security_check_cookie

- ea: `0x140013b00`
- end: `0x140013b1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001090`
- `0x1400010e0`
- `0x1400011c0`
- `0x140001380`
- `0x140001530`
- `0x140001690`
- `0x1400017e0`
- `0x1400022b4`
- `0x1400074f4`
- `0x140007bac`
- `0x140009784`
- `0x140009b0c`
- `0x140009d44`
- `0x14000c1b4`
- `0x14000c40c`
- `0x14000da2c`
- `0x14000db50`
- `0x14000de04`
- `0x14000f8a4`
- `0x14000f984`
- `0x140011520`
- `0x140012acc`
- `0x140012fa0`
- `0x14001395c`
- `0x1400253a8`
- `0x140025f1c`
- `0x14002709c`

## callees

- `0x140001010`
- `0x140013b00`

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
0x140013b00  cmp     rcx, cs:__security_cookie
0x140013b07  jnz     short ReportFailure
0x140013b09  rol     rcx, 10h
0x140013b0d  test    cx, 0FFFFh
0x140013b12  jnz     short RestoreRcx
0x140013b14  retn
0x140013b15  ror     rcx, 10h; StackCookie
0x140013b19  jmp     __report_gsfailure
```
