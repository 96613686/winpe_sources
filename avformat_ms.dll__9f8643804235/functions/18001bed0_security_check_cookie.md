# __security_check_cookie

- ea: `0x18001bed0`
- end: `0x18001beee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003c8c`
- `0x180004870`
- `0x180004e10`
- `0x180006390`
- `0x180008068`
- `0x180008910`
- `0x180009e98`
- `0x18000a920`
- `0x18000b7f8`
- `0x18000b8fc`
- `0x18000d77c`
- `0x18000e06c`
- `0x18000e598`
- `0x18000f4c4`
- `0x180010290`
- `0x180010550`
- `0x180010e4c`
- `0x1800110fc`
- `0x180011814`
- `0x1800119cc`
- `0x18001278c`
- `0x180013214`
- `0x180013478`
- `0x180014004`
- `0x18001436c`
- `0x180015420`
- `0x1800157e8`
- `0x1800168f0`
- `0x18001a314`
- `0x18001aaf0`
- `0x18001b380`
- `0x18001b8e4`
- `0x18001be58`

## callees

- `0x18001bed0`
- `0x18001bf30`

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
0x18001bed0  cmp     rcx, cs:__security_cookie
0x18001bed7  jnz     short ReportFailure
0x18001bed9  rol     rcx, 10h
0x18001bedd  test    cx, 0FFFFh
0x18001bee2  jnz     short RestoreRcx
0x18001bee4  retn
0x18001bee5  ror     rcx, 10h; StackCookie
0x18001bee9  jmp     __report_gsfailure
```
