# __security_check_cookie

- ea: `0x1800026f0`
- end: `0x18000270e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015b4`
- `0x1800019ec`
- `0x180001a9c`
- `0x180003e10`
- `0x1800040c4`
- `0x180004df8`
- `0x18000519c`
- `0x18000556c`
- `0x1800060b4`
- `0x180006450`
- `0x18000757c`
- `0x180007688`
- `0x18000806c`
- `0x18000964c`
- `0x18000a140`
- `0x18000a268`
- `0x18000a538`
- `0x18000abac`
- `0x18000ad54`
- `0x18000b224`
- `0x18000b9fc`
- `0x18000c490`
- `0x18000c590`
- `0x18000d498`
- `0x18000dec0`
- `0x18000dfe8`
- `0x18000fa28`
- `0x18000fc68`
- `0x1800105b4`
- `0x180010774`
- `0x180010a58`
- `0x180010c50`
- `0x180011220`
- `0x180011678`
- `0x180011ccc`
- `0x1800124d8`
- `0x180012654`
- `0x1800127e0`
- `0x1800128fc`
- `0x180012b04`
- `0x1800141d0`
- `0x1800144e0`
- `0x1800149a0`
- `0x180015774`
- `0x18001639c`
- `0x180016c90`

## callees

- `0x1800026f0`
- `0x180002be0`

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
0x1800026f0  cmp     rcx, cs:__security_cookie
0x1800026f7  jnz     short ReportFailure
0x1800026f9  rol     rcx, 10h
0x1800026fd  test    cx, 0FFFFh
0x180002702  jnz     short RestoreRcx
0x180002704  retn
0x180002705  ror     rcx, 10h; StackCookie
0x180002709  jmp     __report_gsfailure
```
