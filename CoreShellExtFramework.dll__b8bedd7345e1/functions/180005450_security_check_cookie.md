# __security_check_cookie

- ea: `0x180005450`
- end: `0x18000546e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001318`
- `0x1800015f0`
- `0x1800016c4`
- `0x180001788`
- `0x180001a3c`
- `0x180001d34`
- `0x180001df8`
- `0x180001ea4`
- `0x1800021d8`
- `0x180002280`
- `0x180002374`
- `0x180002468`
- `0x18000270c`
- `0x180003150`
- `0x1800038a0`
- `0x18000651c`
- `0x1800067c8`
- `0x180006dc8`
- `0x180006f60`
- `0x180007304`
- `0x180007664`
- `0x180008bdc`
- `0x1800091f0`
- `0x180009488`
- `0x180009db4`
- `0x180009e4c`
- `0x18000ad0c`
- `0x18000c780`
- `0x18000cd98`
- `0x18000d408`
- `0x18000ebd4`
- `0x180010480`
- `0x1800105b8`
- `0x180010de0`
- `0x180011ccc`
- `0x180012630`
- `0x1800137f0`
- `0x1800146c0`

## callees

- `0x180005450`
- `0x180005a10`

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
0x180005450  cmp     rcx, cs:__security_cookie
0x180005457  jnz     short ReportFailure
0x180005459  rol     rcx, 10h
0x18000545d  test    cx, 0FFFFh
0x180005462  jnz     short RestoreRcx
0x180005464  retn
0x180005465  ror     rcx, 10h; StackCookie
0x180005469  jmp     __report_gsfailure
```
