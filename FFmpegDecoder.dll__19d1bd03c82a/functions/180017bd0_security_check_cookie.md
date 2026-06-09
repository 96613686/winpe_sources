# __security_check_cookie

- ea: `0x180017bd0`
- end: `0x180017bee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `120`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001084`
- `0x180001138`
- `0x1800013e4`
- `0x180001498`
- `0x180001788`
- `0x180001a94`
- `0x180002460`
- `0x180002740`
- `0x1800027d0`
- `0x180002be8`
- `0x180003154`
- `0x1800031e8`
- `0x1800036b0`
- `0x180003710`
- `0x180003fb8`
- `0x180004260`
- `0x18000513c`
- `0x1800051ec`
- `0x1800052d0`
- `0x180005380`
- `0x180005430`
- `0x180005550`
- `0x1800059b0`
- `0x180005cc0`
- `0x180005f10`
- `0x180005fc0`
- `0x180006110`
- `0x180006828`
- `0x180006b48`
- `0x180006d60`
- `0x180007070`
- `0x180007220`
- `0x1800072d0`
- `0x180007650`
- `0x180007790`
- `0x180007840`
- `0x180007a20`
- `0x180007ad0`
- `0x180007ea0`
- `0x1800080e0`
- `0x180008570`
- `0x1800088fc`
- `0x180008b80`
- `0x180008c30`
- `0x180008fc4`
- `0x180009290`
- `0x1800094c0`
- `0x180009bf8`
- `0x180009c38`
- `0x180009c78`

## callees

- `0x180017bd0`
- `0x180018390`

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
0x180017bd0  cmp     rcx, cs:__security_cookie
0x180017bd7  jnz     short ReportFailure
0x180017bd9  rol     rcx, 10h
0x180017bdd  test    cx, 0FFFFh
0x180017be2  jnz     short RestoreRcx
0x180017be4  retn
0x180017be5  ror     rcx, 10h; StackCookie
0x180017be9  jmp     __report_gsfailure
```
