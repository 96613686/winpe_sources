# sqlite3ErrStr

- ea: `0x18004d39c`
- end: `0x18004d3f0`
- name: `sqlite3ErrStr`
- size: `84`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180015248`
- `0x18002a050`
- `0x180030d98`
- `0x18004d2f0`
- `0x180050420`
- `0x180065930`
- `0x180088a34`
- `0x18008e5a0`
- `0x18008e6a0`
- `0x180094cfc`

## callees

- `0x18004d39c`

## string_xrefs

- `0x18004d3d5`: `abort due to ROLLBACK`

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
  if ( (unsigned __int8)a1 < 0x1Du && off_18009B1D0[(unsigned __int8)a1] )
    return off_18009B1D0[(unsigned __int8)a1];
  return v1;
}

```

## disassembly

```asm
0x18004d39c  mov     edx, ecx
0x18004d39e  sub     edx, 64h ; 'd'
0x18004d3a1  jz      short loc_18004D3E7
0x18004d3a3  sub     edx, 1
0x18004d3a6  jz      short loc_18004D3DE
0x18004d3a8  cmp     edx, 19Fh
0x18004d3ae  jz      short loc_18004D3D5
0x18004d3b0  movzx   eax, cl
0x18004d3b3  lea     rdx, aUnknownError; "unknown error"
0x18004d3ba  cmp     eax, 1Dh
0x18004d3bd  jnb     short loc_18004D3D1
0x18004d3bf  lea     rcx, off_18009B1D0; "not an error"
0x18004d3c6  cmp     qword ptr [rcx+rax*8], 0
0x18004d3cb  jz      short loc_18004D3D1
0x18004d3cd  mov     rdx, [rcx+rax*8]
0x18004d3d1  mov     rax, rdx
0x18004d3d4  retn
0x18004d3d5  lea     rdx, aAbortDueToRoll; "abort due to ROLLBACK"
0x18004d3dc  jmp     short loc_18004D3D1
0x18004d3de  lea     rdx, aNoMoreRowsAvai; "no more rows available"
0x18004d3e5  jmp     short loc_18004D3D1
0x18004d3e7  lea     rdx, aAnotherRowAvai; "another row available"
0x18004d3ee  jmp     short loc_18004D3D1
```
