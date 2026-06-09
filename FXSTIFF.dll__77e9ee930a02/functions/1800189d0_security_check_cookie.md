# __security_check_cookie

- ea: `0x1800189d0`
- end: `0x1800189ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002dac`
- `0x180004cbc`
- `0x1800066d0`
- `0x180006bb0`
- `0x18000a130`
- `0x18000b120`
- `0x18000bb50`
- `0x18000d060`
- `0x18000da70`
- `0x18000e268`
- `0x180010688`
- `0x180010938`
- `0x180011648`
- `0x180011a14`
- `0x180011df8`
- `0x1800127e4`
- `0x180012b80`
- `0x1800139fc`
- `0x180013c64`
- `0x180013ee0`
- `0x180014820`
- `0x180015dcc`
- `0x1800169e0`
- `0x180016afc`
- `0x1800172f4`
- `0x1800174d8`
- `0x180018270`
- `0x180018340`
- `0x1800188a4`

## callees

- `0x180001a20`
- `0x1800189d0`

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
0x1800189d0  cmp     rcx, cs:__security_cookie
0x1800189d7  jnz     short ReportFailure
0x1800189d9  rol     rcx, 10h
0x1800189dd  test    cx, 0FFFFh
0x1800189e2  jnz     short RestoreRcx
0x1800189e4  retn
0x1800189e5  ror     rcx, 10h
0x1800189e9  jmp     __report_gsfailure
```
