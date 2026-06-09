# __security_check_cookie

- ea: `0x18017e9e0`
- end: `0x18017e9fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `213`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000113c`
- `0x180001284`
- `0x180001338`
- `0x180124218`
- `0x180124780`
- `0x180125020`
- `0x180125c10`
- `0x180126d54`
- `0x18012705c`
- `0x180128040`
- `0x180128dbc`
- `0x18012c440`
- `0x18012cca0`
- `0x18012d6e0`
- `0x18012f288`
- `0x18012f4f4`
- `0x18012f9b0`
- `0x18013179c`
- `0x18013224c`
- `0x1801329b0`
- `0x180135cb0`
- `0x180135dd8`
- `0x1801362c0`
- `0x1801369b0`
- `0x18013795c`
- `0x180137b20`
- `0x180138aa0`
- `0x180139440`
- `0x18013a4f0`
- `0x18013a860`
- `0x18013aa10`
- `0x18013ab20`
- `0x18013bd70`
- `0x18013c0e0`
- `0x18013d138`
- `0x18013d278`
- `0x18013d3f4`
- `0x18013d594`
- `0x18013d87c`
- `0x18013ddb4`
- `0x18013e8f0`
- `0x18013eebc`
- `0x18013f4b8`
- `0x18013fa80`
- `0x180140ba0`
- `0x1801450c0`
- `0x180145370`
- `0x180145a60`
- `0x180146070`
- `0x1801463a0`

## callees

- `0x18017e9e0`
- `0x18017f210`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    sub_18017F210(StackCookie);
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
0x18017e9e0  cmp     rcx, cs:__security_cookie
0x18017e9e7  jnz     short ReportFailure
0x18017e9e9  rol     rcx, 10h
0x18017e9ed  test    cx, 0FFFFh
0x18017e9f2  jnz     short RestoreRcx
0x18017e9f4  retn
0x18017e9f5  ror     rcx, 10h
0x18017e9f9  jmp     sub_18017F210
```
