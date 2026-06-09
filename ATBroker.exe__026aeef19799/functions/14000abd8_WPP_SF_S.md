# WPP_SF_S

- ea: `0x14000abd8`
- end: `0x14000ac32`
- name: `WPP_SF_S`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b250`
- `0x14000c220`
- `0x14000c2bc`
- `0x14000f9c0`
- `0x140010e44`

## callees

- `0x14000abd8`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x14000ac27`
- `ADVAPI32!TraceMessage` at `0x14000ac27`

## pseudocode

```c
ULONG __fastcall WPP_SF_S(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x14000abd8  sub     rsp, 48h
0x14000abdc  xor     r11d, r11d
0x14000abdf  test    r9, r9
0x14000abe2  jz      short loc_14000ABFC
0x14000abe4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000abe8  inc     rax
0x14000abeb  cmp     [r9+rax*2], r11w
0x14000abf0  jnz     short loc_14000ABE8
0x14000abf2  lea     rax, ds:2[rax*2]
0x14000abfa  jmp     short loc_14000AC01
0x14000abfc  mov     eax, 0Ah
0x14000ac01  test    r9, r9
0x14000ac04  mov     [rsp+48h+var_18], r11
0x14000ac09  lea     r10, aNull_0; "NULL"
0x14000ac10  mov     [rsp+48h+var_20], rax
0x14000ac15  cmovz   r9, r10
0x14000ac19  mov     [rsp+48h+var_28], r9
0x14000ac1e  movzx   r9d, dx; MessageNumber
0x14000ac22  mov     edx, 2Bh ; '+'; MessageFlags
0x14000ac27  call    cs:__imp_TraceMessage
0x14000ac2d  add     rsp, 48h
0x14000ac31  retn
```
