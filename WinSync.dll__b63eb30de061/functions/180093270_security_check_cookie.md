# __security_check_cookie

- ea: `0x180093270`
- end: `0x18009328e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `49`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c9f0`
- `0x18000ec2c`
- `0x1800166e0`
- `0x180022490`
- `0x180029810`
- `0x18002a290`
- `0x18002c600`
- `0x180036264`
- `0x180036eb4`
- `0x1800371e0`
- `0x18003734c`
- `0x180037cb0`
- `0x1800383f4`
- `0x18003ea50`
- `0x18003fe48`
- `0x18004008c`
- `0x18004a8fc`
- `0x18004cb40`
- `0x18004dda4`
- `0x18004e2e4`
- `0x180055ed8`
- `0x180059fc0`
- `0x18005adc4`
- `0x18005cd9c`
- `0x180062b80`
- `0x18006685c`
- `0x1800672ec`
- `0x18006c5a4`
- `0x18006d9c8`
- `0x18006e66c`
- `0x1800727f0`
- `0x180073b3c`
- `0x180073dac`
- `0x18007a0c4`
- `0x18007a1b8`
- `0x18007c32c`
- `0x18007c6a8`
- `0x18007cb4c`
- `0x180080af4`
- `0x180080c64`
- `0x180081978`
- `0x180081e7c`
- `0x18008b918`
- `0x180090bbc`
- `0x180092a54`
- `0x180092b20`
- `0x180092bc0`
- `0x180092e04`
- `0x1800931b0`

## callees

- `0x18002ac20`
- `0x180093270`

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
0x180093270  cmp     rcx, cs:__security_cookie
0x180093277  jnz     short ReportFailure
0x180093279  rol     rcx, 10h
0x18009327d  test    cx, 0FFFFh
0x180093282  jnz     short RestoreRcx
0x180093284  retn
0x180093285  ror     rcx, 10h
0x180093289  jmp     __report_gsfailure
```
