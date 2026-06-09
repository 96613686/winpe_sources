# __security_check_cookie

- ea: `0x18001b980`
- end: `0x18001b99e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `119`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e40`
- `0x180002450`
- `0x18000279c`
- `0x180002928`
- `0x180002ad4`
- `0x180002c74`
- `0x180002d50`
- `0x180002eb0`
- `0x180003978`
- `0x180003a5c`
- `0x180003be0`
- `0x1800040e0`
- `0x180004498`
- `0x1800045e8`
- `0x180004880`
- `0x18000521c`
- `0x180005584`
- `0x1800056d0`
- `0x180005a8c`
- `0x180005f80`
- `0x18000616c`
- `0x1800063c4`
- `0x1800067dc`
- `0x180006d24`
- `0x1800071c0`
- `0x1800078d8`
- `0x1800079c0`
- `0x180008138`
- `0x180008524`
- `0x1800088c4`
- `0x180008a6c`
- `0x180008cf0`
- `0x180008f2c`
- `0x180009004`
- `0x18000931c`
- `0x180009580`
- `0x1800096f0`
- `0x180009928`
- `0x180009c14`
- `0x18000a0c0`
- `0x18000a24c`
- `0x18000a428`
- `0x18000a61c`
- `0x18000a918`
- `0x18000ae68`
- `0x18000b240`
- `0x18000b710`
- `0x18000b8f0`
- `0x18000c0c0`
- `0x18000c334`

## callees

- `0x180001600`
- `0x18001b980`

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
0x18001b980  cmp     rcx, cs:__security_cookie
0x18001b987  jnz     short ReportFailure
0x18001b989  rol     rcx, 10h
0x18001b98d  test    cx, 0FFFFh
0x18001b992  jnz     short RestoreRcx
0x18001b994  retn
0x18001b995  ror     rcx, 10h
0x18001b999  jmp     __report_gsfailure
```
