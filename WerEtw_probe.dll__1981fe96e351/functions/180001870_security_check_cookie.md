# __security_check_cookie

- ea: `0x180001870`
- end: `0x18000188e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180002730`
- `0x1800059a4`
- `0x180006dc0`
- `0x1800075ac`
- `0x180007e84`
- `0x180008290`
- `0x180008a88`
- `0x18000b7b0`
- `0x18000d770`
- `0x18000edc4`
- `0x18000f1d8`
- `0x18000f3cc`
- `0x18000f5dc`
- `0x1800111f8`
- `0x180011394`
- `0x180011820`
- `0x180012308`
- `0x1800127d0`
- `0x180013890`
- `0x180015264`
- `0x1800166b4`
- `0x180016e84`
- `0x180017214`
- `0x18001753c`
- `0x180017bd0`
- `0x180017f3c`
- `0x180018968`
- `0x180018bc4`
- `0x180019558`
- `0x18001a004`
- `0x18001a2a0`
- `0x18001be2c`
- `0x18001c280`
- `0x18001c584`
- `0x18001cc84`
- `0x18001d000`
- `0x18001da60`
- `0x18001f524`
- `0x180020100`
- `0x180020508`
- `0x180020a90`
- `0x180020d24`
- `0x180020fdc`
- `0x180021230`
- `0x1800217d4`
- `0x180021a7c`
- `0x180021f6c`
- `0x180022930`
- `0x180023510`

## callees

- `0x180001870`
- `0x180001f50`

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
0x180001870  cmp     rcx, cs:__security_cookie
0x180001877  jnz     short ReportFailure
0x180001879  rol     rcx, 10h
0x18000187d  test    cx, 0FFFFh
0x180001882  jnz     short RestoreRcx
0x180001884  retn
0x180001885  ror     rcx, 10h; StackCookie
0x180001889  jmp     __report_gsfailure
```
