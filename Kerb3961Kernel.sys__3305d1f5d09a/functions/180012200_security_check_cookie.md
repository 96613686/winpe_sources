# __security_check_cookie

- ea: `0x180012200`
- end: `0x18001221e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800028d4`
- `0x180002cc4`
- `0x180003b10`
- `0x180003dc0`
- `0x180004390`
- `0x180004700`
- `0x180004a00`
- `0x180004f80`
- `0x1800060f0`
- `0x180007338`
- `0x180007ad0`
- `0x180008020`
- `0x1800083f0`
- `0x18000d900`
- `0x18000f2c0`
- `0x18000fb70`
- `0x180010460`
- `0x180011760`
- `0x180011814`
- `0x1800118cc`
- `0x1800119a4`
- `0x180011b90`
- `0x180011eb8`
- `0x1800120cc`
- `0x18001d3a0`
- `0x18001f1e0`

## callees

- `0x180001420`
- `0x180012200`

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
0x180012200  cmp     rcx, cs:__security_cookie
0x180012207  jnz     short ReportFailure
0x180012209  rol     rcx, 10h
0x18001220d  test    cx, 0FFFFh
0x180012212  jnz     short RestoreRcx
0x180012214  retn
0x180012215  ror     rcx, 10h; StackCookie
0x180012219  jmp     __report_gsfailure
```
