# __security_check_cookie

- ea: `0x18001a380`
- end: `0x18001a39e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `66`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001068`
- `0x1800011b4`
- `0x180001468`
- `0x180001760`
- `0x180002560`
- `0x1800030f0`
- `0x180003e60`
- `0x180003fb0`
- `0x1800043d0`
- `0x1800066f0`
- `0x180006fa0`
- `0x180007230`
- `0x180007980`
- `0x180007bc0`
- `0x180007c90`
- `0x180007d20`
- `0x180007ef0`
- `0x180008360`
- `0x180008950`
- `0x1800097cc`
- `0x180009960`
- `0x180009ce8`
- `0x180009e54`
- `0x180009fc0`
- `0x18000a530`
- `0x18000aebc`
- `0x18000b08c`
- `0x18000b8bc`
- `0x18000c344`
- `0x18000c494`
- `0x18000caa0`
- `0x18000d51c`
- `0x18000f0dc`
- `0x18000f7d0`
- `0x18000fdf4`
- `0x18001010c`
- `0x1800110fc`
- `0x180012b50`
- `0x180012d10`
- `0x180012ee0`
- `0x1800131d0`
- `0x180013404`
- `0x18001374c`
- `0x180013ec8`
- `0x180014c2c`
- `0x180015518`
- `0x1800157d4`
- `0x180015c94`
- `0x18001640c`

## callees

- `0x18000e6e0`
- `0x18001a380`

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
0x18001a380  cmp     rcx, cs:__security_cookie
0x18001a387  jnz     short ReportFailure
0x18001a389  rol     rcx, 10h
0x18001a38d  test    cx, 0FFFFh
0x18001a392  jnz     short RestoreRcx
0x18001a394  retn
0x18001a395  ror     rcx, 10h
0x18001a399  jmp     __report_gsfailure
```
