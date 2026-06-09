# __security_check_cookie

- ea: `0x180001d40`
- end: `0x180001d5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x18000398c`
- `0x180003c28`
- `0x180004988`
- `0x180004d38`
- `0x180005114`
- `0x180005c34`
- `0x180005fb0`
- `0x180007064`
- `0x180007170`
- `0x180007b7c`
- `0x18000930c`
- `0x180009e00`
- `0x180009f28`
- `0x18000a1f8`
- `0x18000b8c0`
- `0x18000ba4c`
- `0x18000bed4`
- `0x18000c27c`
- `0x18000c450`
- `0x18000c590`
- `0x18000c7d0`
- `0x18000c9dc`
- `0x18000cb48`
- `0x18000ccd0`
- `0x18000ce30`
- `0x18000dcc8`
- `0x18000e2f4`
- `0x18000ea3c`
- `0x18000ed18`
- `0x18000f184`
- `0x18000f668`
- `0x18000fdf0`
- `0x18001088c`
- `0x180010e6c`
- `0x180011134`
- `0x180011400`
- `0x1800122a0`
- `0x180012388`
- `0x180012430`
- `0x18001254c`
- `0x180012620`
- `0x180012728`
- `0x1800127fc`
- `0x1800128d0`
- `0x1800131d0`
- `0x1800133ac`
- `0x180013720`
- `0x180014344`

## callees

- `0x180001d40`
- `0x180002600`

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
0x180001d40  cmp     rcx, cs:__security_cookie
0x180001d47  jnz     short ReportFailure
0x180001d49  rol     rcx, 10h
0x180001d4d  test    cx, 0FFFFh
0x180001d52  jnz     short RestoreRcx
0x180001d54  retn
0x180001d55  ror     rcx, 10h; StackCookie
0x180001d59  jmp     __report_gsfailure
```
