# sqlite3ErrStr

- ea: `0x180031e2c`
- end: `0x180031e80`
- name: `sqlite3ErrStr`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180021404`
- `0x1800286a4`
- `0x180031d80`
- `0x180032060`
- `0x180061870`
- `0x18006d81c`
- `0x1800777a0`
- `0x180093bb0`
- `0x18009c4c0`
- `0x18009c5c0`

## callees

- `0x180031e2c`

## string_xrefs

- `0x180031e63`: `abort due to ROLLBACK`

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
  if ( (unsigned __int8)a1 < 0x1Du && off_1800B1020[(unsigned __int8)a1] )
    return off_1800B1020[(unsigned __int8)a1];
  return v1;
}

```

## disassembly

```asm
0x180031e2c  mov     edx, ecx
0x180031e2e  sub     edx, 64h ; 'd'
0x180031e31  jz      short loc_180031E75
0x180031e33  sub     edx, 1
0x180031e36  jz      short loc_180031E6C
0x180031e38  cmp     edx, 19Fh
0x180031e3e  jz      short loc_180031E63
0x180031e40  movzx   eax, cl
0x180031e43  lea     rdx, aUnknownError; "unknown error"
0x180031e4a  cmp     eax, 1Dh
0x180031e4d  jnb     short loc_180031E7C
0x180031e4f  lea     rcx, off_1800B1020; "not an error"
0x180031e56  cmp     qword ptr [rcx+rax*8], 0
0x180031e5b  jz      short loc_180031E7C
0x180031e5d  mov     rdx, [rcx+rax*8]
0x180031e61  jmp     short loc_180031E7C
0x180031e63  lea     rdx, aAbortDueToRoll; "abort due to ROLLBACK"
0x180031e6a  jmp     short loc_180031E7C
0x180031e6c  lea     rdx, aNoMoreRowsAvai; "no more rows available"
0x180031e73  jmp     short loc_180031E7C
0x180031e75  lea     rdx, aAnotherRowAvai; "another row available"
0x180031e7c  mov     rax, rdx
0x180031e7f  retn
```
