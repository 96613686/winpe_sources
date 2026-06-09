# __security_check_cookie

- ea: `0x180078e90`
- end: `0x180078eae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029da0`
- `0x180029f30`
- `0x18002ad1c`
- `0x18002b6a4`
- `0x18002d200`
- `0x18002d610`
- `0x18002e940`
- `0x180030510`
- `0x180031a30`
- `0x180032290`
- `0x180032bc0`
- `0x1800330b0`
- `0x1800332ec`
- `0x180035f40`
- `0x1800364b0`
- `0x18003a0e0`
- `0x18003afe0`
- `0x18003b520`
- `0x18003c57c`
- `0x18003c970`
- `0x18003ca20`
- `0x18003caa0`
- `0x18003ce10`
- `0x18003ed60`
- `0x18003ee90`
- `0x180040350`
- `0x180040800`
- `0x180040b50`
- `0x180040da0`
- `0x180041120`
- `0x1800412a0`
- `0x1800413d0`
- `0x1800414c0`
- `0x1800415d0`
- `0x180041a50`
- `0x180041bb0`
- `0x180041f20`
- `0x1800420a0`
- `0x1800426b0`
- `0x180042b00`
- `0x180042d38`
- `0x180042f08`
- `0x180043384`
- `0x1800443e0`
- `0x180045b60`
- `0x180045cc0`
- `0x180046e40`
- `0x180047be0`
- `0x180048524`
- `0x180048658`

## callees

- `0x180078e90`
- `0x180078f50`

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
0x180078e90  cmp     rcx, cs:__security_cookie
0x180078e97  jnz     short ReportFailure
0x180078e99  rol     rcx, 10h
0x180078e9d  test    cx, 0FFFFh
0x180078ea2  jnz     short RestoreRcx
0x180078ea4  retn
0x180078ea5  ror     rcx, 10h; StackCookie
0x180078ea9  jmp     __report_gsfailure
```
