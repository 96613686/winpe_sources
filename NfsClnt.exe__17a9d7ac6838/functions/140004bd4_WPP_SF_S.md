# WPP_SF_S

- ea: `0x140004bd4`
- end: `0x140004c2e`
- name: `WPP_SF_S`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140004868`
- `0x14000664c`
- `0x140007dd0`
- `0x140008720`
- `0x1400088c0`
- `0x140008b50`
- `0x140009710`

## callees

- `0x140004bd4`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x140004c23`
- `ADVAPI32!TraceMessage` at `0x140004c23`

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
0x140004bd4  sub     rsp, 48h
0x140004bd8  xor     r11d, r11d
0x140004bdb  test    r9, r9
0x140004bde  jz      short loc_140004BF8
0x140004be0  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004be4  inc     rax
0x140004be7  cmp     [r9+rax*2], r11w
0x140004bec  jnz     short loc_140004BE4
0x140004bee  lea     rax, ds:2[rax*2]
0x140004bf6  jmp     short loc_140004BFD
0x140004bf8  mov     eax, 0Ah
0x140004bfd  test    r9, r9
0x140004c00  mov     [rsp+48h+var_18], r11
0x140004c05  lea     r10, aNull_1; "NULL"
0x140004c0c  mov     [rsp+48h+var_20], rax
0x140004c11  cmovz   r9, r10
0x140004c15  mov     [rsp+48h+var_28], r9
0x140004c1a  movzx   r9d, dx; MessageNumber
0x140004c1e  mov     edx, 2Bh ; '+'; MessageFlags
0x140004c23  call    cs:__imp_TraceMessage
0x140004c29  add     rsp, 48h
0x140004c2d  retn
```
