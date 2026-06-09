# __security_check_cookie

- ea: `0x1800021c0`
- end: `0x1800021de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015d0`
- `0x180001660`
- `0x180001a7c`
- `0x180002f40`
- `0x180003500`
- `0x180003880`
- `0x180003d34`
- `0x180003fe4`
- `0x180004600`
- `0x1800048ac`
- `0x180004bb4`
- `0x180006128`
- `0x1800065d4`
- `0x180006810`
- `0x1800069e0`
- `0x1800072bc`
- `0x180007814`
- `0x180008bbc`
- `0x18000a44c`
- `0x18000b620`
- `0x18000b860`
- `0x18000bea0`
- `0x18000e324`
- `0x18000e70c`
- `0x18000fa9c`
- `0x18000fdd0`
- `0x1800104e8`
- `0x1800123e0`
- `0x180012eb8`
- `0x180012f34`
- `0x180013344`
- `0x1800139a4`
- `0x180015284`
- `0x180016c60`
- `0x1800176e4`
- `0x180017db0`
- `0x18001815c`
- `0x180018360`
- `0x180018648`
- `0x180018870`
- `0x18001956c`
- `0x180019b9c`
- `0x18001aaf0`
- `0x18001ab70`
- `0x18001abf0`
- `0x18001aca4`
- `0x18001ad24`
- `0x18001ada4`

## callees

- `0x1800021c0`
- `0x1800027f0`

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
0x1800021c0  cmp     rcx, cs:__security_cookie
0x1800021c7  jnz     short ReportFailure
0x1800021c9  rol     rcx, 10h
0x1800021cd  test    cx, 0FFFFh
0x1800021d2  jnz     short RestoreRcx
0x1800021d4  retn
0x1800021d5  ror     rcx, 10h; StackCookie
0x1800021d9  jmp     __report_gsfailure
```
