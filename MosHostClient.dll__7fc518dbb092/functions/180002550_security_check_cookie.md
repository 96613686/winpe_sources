# __security_check_cookie

- ea: `0x180002550`
- end: `0x18000256e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x1800019f0`
- `0x18000383c`
- `0x180003ad0`
- `0x180003ea4`
- `0x1800041d4`
- `0x1800045a8`
- `0x180004c44`
- `0x180005064`
- `0x180006cdc`
- `0x180007240`
- `0x18000861c`
- `0x180009f30`
- `0x18000a280`
- `0x18000a3f0`
- `0x18000a810`
- `0x18000ae98`
- `0x18000b1cc`
- `0x18000b28c`
- `0x18000b400`
- `0x18000b5c0`
- `0x18000b8e8`
- `0x18000c41c`
- `0x18000d760`
- `0x18000da30`
- `0x18000dad8`
- `0x18000f0c0`
- `0x18000f1e4`
- `0x18000fdb0`
- `0x180010038`
- `0x180010f60`

## callees

- `0x180002550`
- `0x180002b80`

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
0x180002550  cmp     rcx, cs:__security_cookie
0x180002557  jnz     short ReportFailure
0x180002559  rol     rcx, 10h
0x18000255d  test    cx, 0FFFFh
0x180002562  jnz     short RestoreRcx
0x180002564  retn
0x180002565  ror     rcx, 10h; StackCookie
0x180002569  jmp     __report_gsfailure
```
