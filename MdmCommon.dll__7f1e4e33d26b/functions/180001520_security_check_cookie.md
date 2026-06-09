# __security_check_cookie

- ea: `0x180001520`
- end: `0x18000153e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `81`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003010`
- `0x1800030c0`
- `0x1800034b0`
- `0x1800035d0`
- `0x1800036c0`
- `0x180003930`
- `0x180003a20`
- `0x180003d40`
- `0x180003f90`
- `0x1800040c0`
- `0x1800043b0`
- `0x180004520`
- `0x1800049e0`
- `0x180004b60`
- `0x180004c70`
- `0x180005070`
- `0x180005360`
- `0x180005450`
- `0x180005550`
- `0x180005670`
- `0x180005860`
- `0x180005a10`
- `0x180005cb0`
- `0x180005e50`
- `0x180006548`
- `0x180006aa0`
- `0x18000745c`
- `0x180008f04`
- `0x18000933c`
- `0x1800095e8`
- `0x180009868`
- `0x180009b24`
- `0x18000a314`
- `0x18000ae24`
- `0x18000b350`
- `0x18000ba7c`
- `0x18000c38c`
- `0x18000e97c`
- `0x18000ef34`
- `0x180010740`
- `0x180010b0c`
- `0x180010f90`
- `0x18001142c`
- `0x180011a78`
- `0x180012038`
- `0x180012578`
- `0x1800126e0`
- `0x180012848`
- `0x180012a24`
- `0x180012b8c`

## callees

- `0x180001520`
- `0x180001b70`

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
0x180001520  cmp     rcx, cs:__security_cookie
0x180001527  jnz     short ReportFailure
0x180001529  rol     rcx, 10h
0x18000152d  test    cx, 0FFFFh
0x180001532  jnz     short RestoreRcx
0x180001534  retn
0x180001535  ror     rcx, 10h; StackCookie
0x180001539  jmp     __report_gsfailure
```
