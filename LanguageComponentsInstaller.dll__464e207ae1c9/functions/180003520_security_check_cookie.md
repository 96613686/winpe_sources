# __security_check_cookie

- ea: `0x180003520`
- end: `0x18000353e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `139`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x18000196c`
- `0x1800019fc`
- `0x180001ca0`
- `0x180001f98`
- `0x1800020dc`
- `0x180002860`
- `0x180002b50`
- `0x180002ed0`
- `0x180003a9c`
- `0x1800046e8`
- `0x1800049f8`
- `0x180004b3c`
- `0x180005508`
- `0x1800057b4`
- `0x180005c60`
- `0x180006a78`
- `0x180006e80`
- `0x18000708c`
- `0x180007454`
- `0x180007594`
- `0x180007d64`
- `0x180008184`
- `0x180008458`
- `0x180008790`
- `0x180008b80`
- `0x180008c40`
- `0x180009d88`
- `0x18000a160`
- `0x18000a3cc`
- `0x18000aa40`
- `0x18000ac60`
- `0x18000ad40`
- `0x18000afac`
- `0x18000b560`
- `0x18000b6b4`
- `0x18000b908`
- `0x18000ba74`
- `0x18000bc70`
- `0x18000d7e4`
- `0x18000d970`
- `0x18000daa0`
- `0x18000f0a8`
- `0x18000f3f8`
- `0x18000fac8`
- `0x18000fb40`
- `0x18000ff28`

## callees

- `0x180003520`
- `0x180003f40`

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
0x180003520  cmp     rcx, cs:__security_cookie
0x180003527  jnz     short ReportFailure
0x180003529  rol     rcx, 10h
0x18000352d  test    cx, 0FFFFh
0x180003532  jnz     short RestoreRcx
0x180003534  retn
0x180003535  ror     rcx, 10h; StackCookie
0x180003539  jmp     __report_gsfailure
```
