# __security_check_cookie

- ea: `0x18000eb70`
- end: `0x18000eb8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180007760`
- `0x180007860`
- `0x180008d70`
- `0x18000984c`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000a920`
- `0x18000c2d0`
- `0x18000c8c0`
- `0x18000fde8`
- `0x18001007c`
- `0x180010724`
- `0x18001088c`
- `0x180010a54`
- `0x180011174`
- `0x180011528`
- `0x180012970`
- `0x180012cf0`
- `0x180013ae8`
- `0x1800144f4`
- `0x1800148a8`
- `0x180014ba0`
- `0x180016a70`
- `0x1800280c4`
- `0x180028310`

## callees

- `0x18000eb70`
- `0x18000f150`

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
0x18000eb70  cmp     rcx, cs:__security_cookie
0x18000eb77  jnz     short ReportFailure
0x18000eb79  rol     rcx, 10h
0x18000eb7d  test    cx, 0FFFFh
0x18000eb82  jnz     short RestoreRcx
0x18000eb84  retn
0x18000eb85  ror     rcx, 10h; StackCookie
0x18000eb89  jmp     __report_gsfailure
```
