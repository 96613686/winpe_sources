# __security_check_cookie

- ea: `0x180016280`
- end: `0x18001629e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800021ec`
- `0x180002b5c`
- `0x180002df8`
- `0x1800038a8`
- `0x180003c4c`
- `0x180004044`
- `0x180004c84`
- `0x18000508c`
- `0x180005e98`
- `0x180006118`
- `0x180006224`
- `0x180006bcc`
- `0x1800079e0`
- `0x180008438`
- `0x180008738`
- `0x1800089c8`
- `0x180009710`
- `0x18000a0e4`
- `0x18000a830`
- `0x18000aa90`
- `0x18000b2e0`
- `0x18000b4d0`
- `0x18000b6a8`
- `0x18000b7c8`
- `0x18000c0d0`
- `0x18000c508`
- `0x18000c630`
- `0x18000c8e4`
- `0x18000ca04`
- `0x18000cb60`
- `0x18000dfe0`
- `0x18000e440`
- `0x18000fb14`
- `0x18000fc80`
- `0x18001010c`
- `0x1800102a8`
- `0x1800106f8`
- `0x18001123c`
- `0x180011b28`
- `0x180011e94`
- `0x180014f6c`

## callees

- `0x180001dc0`
- `0x180016280`

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
0x180016280  cmp     rcx, cs:__security_cookie
0x180016287  jnz     short ReportFailure
0x180016289  rol     rcx, 10h
0x18001628d  test    cx, 0FFFFh
0x180016292  jnz     short RestoreRcx
0x180016294  retn
0x180016295  ror     rcx, 10h
0x180016299  jmp     __report_gsfailure
```
