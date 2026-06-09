# sqlite3ErrStr

- ea: `0x18007ed94`
- end: `0x18007ede8`
- name: `sqlite3ErrStr`
- size: `84`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800124e0`
- `0x180016bf4`
- `0x18001b670`
- `0x180021aa0`
- `0x180028470`
- `0x18003549c`
- `0x1800427d0`
- `0x1800958b0`
- `0x180095950`
- `0x180095a50`

## callees

- `0x18007ed94`

## string_xrefs

- `0x18007edcb`: `abort due to ROLLBACK`

## pseudocode

```c
const char *__fastcall sqlite3ErrStr(int a1)
{
  const char *v1; // rdx

  switch ( a1 )
  {
    case 100:
      return "another row available";
    case 101:
      return "no more rows available";
    case 516:
      return "abort due to ROLLBACK";
  }
  v1 = "unknown error";
  if ( (unsigned __int8)a1 < 0x1Du && off_1800AA280[(unsigned __int8)a1] )
    return off_1800AA280[(unsigned __int8)a1];
  return v1;
}

```

## disassembly

```asm
0x18007ed94  mov     edx, ecx
0x18007ed96  sub     edx, 64h ; 'd'
0x18007ed99  jz      short loc_18007EDDD
0x18007ed9b  sub     edx, 1
0x18007ed9e  jz      short loc_18007EDD4
0x18007eda0  cmp     edx, 19Fh
0x18007eda6  jz      short loc_18007EDCB
0x18007eda8  movzx   eax, cl
0x18007edab  lea     rdx, aUnknownError; "unknown error"
0x18007edb2  cmp     eax, 1Dh
0x18007edb5  jnb     short loc_18007EDE4
0x18007edb7  lea     rcx, off_1800AA280; "not an error"
0x18007edbe  cmp     qword ptr [rcx+rax*8], 0
0x18007edc3  jz      short loc_18007EDE4
0x18007edc5  mov     rdx, [rcx+rax*8]
0x18007edc9  jmp     short loc_18007EDE4
0x18007edcb  lea     rdx, aAbortDueToRoll; "abort due to ROLLBACK"
0x18007edd2  jmp     short loc_18007EDE4
0x18007edd4  lea     rdx, aNoMoreRowsAvai; "no more rows available"
0x18007eddb  jmp     short loc_18007EDE4
0x18007eddd  lea     rdx, aAnotherRowAvai; "another row available"
0x18007ede4  mov     rax, rdx
0x18007ede7  retn
```
