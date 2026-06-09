# CERT_MAP_RULE_ELEMENT::InitializeInstance(CERT_FIELD_ID,ushort const *,ushort const *,int)

- ea: `0x1800036b0`
- end: `0x18000381c`
- name: `?InitializeInstance@CERT_MAP_RULE_ELEMENT@@QEAAJW4CERT_FIELD_ID@@PEBG1H@Z`
- size: `364`
- prototype: `int __fastcall(__int64, int, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800041f0`

## callees

- `0x1800036b0`

## import_xrefs

- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800036e4`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800036e4`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003739`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003739`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800037dd`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800037dd`

## pseudocode

```c
int __fastcall CERT_MAP_RULE_ELEMENT::InitializeInstance(
        __int64 a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  int result; // eax
  unsigned int v9; // eax
  const unsigned __int16 *v10; // rcx
  int v11; // r8d
  int v12; // edx
  const char *v13; // rdx
  __int64 v14; // r8
  BOOL v15; // edx
  BOOL v16; // eax
  bool v17; // zf
  const unsigned __int16 *v18; // rdx
  _WORD *v19; // rcx

  *(_DWORD *)(a1 + 16) = a2;
  if ( (unsigned __int16)(*a3 - 48) > 9u )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = a3;
      do
      {
        v11 = *(const unsigned __int16 *)((char *)v10 + *(&aMapOID + 2 * v9 + 1) - (struct _MAP_ASN near *)a3);
        v12 = *v10 - v11;
        if ( v12 )
          break;
        ++v10;
      }
      while ( v11 );
      if ( !v12 )
        break;
      if ( ++v9 >= 0xB )
      {
        v13 = (const char *)word_18000A1C2;
        goto LABEL_11;
      }
    }
    v13 = (const char *)*(&aMapOID + 2 * v9);
LABEL_11:
    result = STRA::Copy((STRA *)(a1 + 24), v13);
  }
  else
  {
    result = STRA::CopyW((STRA *)(a1 + 24), a3);
  }
  if ( result < 0 )
    return result;
  v14 = -1;
  do
    ++v14;
  while ( a4[v14] );
  if ( !(_DWORD)v14 )
  {
    v19 = *(_WORD **)(a1 + 128);
    *(_DWORD *)(a1 + 216) = 1;
    *v19 = 0;
    *(_DWORD *)(a1 + 144) = 0;
    goto LABEL_35;
  }
  v15 = 0;
  if ( (_DWORD)v14 != 1 )
    v15 = a4[(unsigned int)(v14 - 1)] == 42;
  v16 = 0;
  if ( *a4 == 42 )
    v16 = v15;
  if ( v16 )
  {
    *(_DWORD *)(a1 + 216) = 4;
    v17 = (_DWORD)v14 == 2;
    LODWORD(v14) = v14 - 2;
LABEL_22:
    if ( v17 )
    {
LABEL_23:
      **(_WORD **)(a1 + 128) = 0;
      *(_DWORD *)(a1 + 144) = 0;
LABEL_35:
      *(_DWORD *)(a1 + 220) = a5;
      return 0;
    }
    v18 = a4 + 1;
    goto LABEL_32;
  }
  if ( v15 )
  {
    *(_DWORD *)(a1 + 216) = 2;
    LODWORD(v14) = v14 - 1;
    if ( !(_DWORD)v14 )
      goto LABEL_23;
  }
  else
  {
    if ( *a4 == 42 )
    {
      *(_DWORD *)(a1 + 216) = 3;
      LODWORD(v14) = v14 - 1;
      v17 = (_DWORD)v14 == 0;
      goto LABEL_22;
    }
    *(_DWORD *)(a1 + 216) = 1;
  }
  v18 = a4;
LABEL_32:
  result = STRU::Copy((STRU *)(a1 + 96), v18, v14);
  if ( result >= 0 )
    goto LABEL_35;
  return result;
}

```

## disassembly

```asm
0x1800036b0  push    rbx
0x1800036b2  push    rbp
0x1800036b3  push    rsi
0x1800036b4  push    rdi
0x1800036b5  push    r14
0x1800036b7  push    r15
0x1800036b9  sub     rsp, 28h
0x1800036bd  xor     ebp, ebp
0x1800036bf  mov     [rcx+10h], edx
0x1800036c2  movzx   eax, word ptr [r8]
0x1800036c6  mov     rdi, r9
0x1800036c9  sub     ax, 30h ; '0'
0x1800036cd  mov     r10, r8
0x1800036d0  mov     rbx, rcx
0x1800036d3  lea     r14d, [rbp+1]
0x1800036d7  cmp     ax, 9
0x1800036db  ja      short loc_1800036EC
0x1800036dd  mov     rdx, r8
0x1800036e0  add     rcx, 18h
0x1800036e4  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800036ea  jmp     short loc_18000373F
0x1800036ec  mov     eax, ebp
0x1800036ee  lea     r15, ?aMapOID@@3PAU_MAP_ASN@@A; _MAP_ASN near * aMapOID
0x1800036f5  mov     r9d, eax
0x1800036f8  mov     rcx, r10
0x1800036fb  add     r9, r9
0x1800036fe  mov     r11, [r15+r9*8+8]
0x180003703  sub     r11, r10
0x180003706  movzx   edx, word ptr [rcx]
0x180003709  movzx   r8d, word ptr [rcx+r11]
0x18000370e  sub     edx, r8d
0x180003711  jnz     short loc_18000371C
0x180003713  add     rcx, 2
0x180003717  test    r8d, r8d
0x18000371a  jnz     short loc_180003706
0x18000371c  test    edx, edx
0x18000371e  jz      short loc_180003731
0x180003720  add     eax, r14d
0x180003723  cmp     eax, 0Bh
0x180003726  jb      short loc_1800036F5
0x180003728  lea     rdx, word_18000A1C2
0x18000372f  jmp     short loc_180003735
0x180003731  mov     rdx, [r15+r9*8]
0x180003735  lea     rcx, [rbx+18h]
0x180003739  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000373f  test    eax, eax
0x180003741  js      loc_18000380F
0x180003747  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000374b  inc     r8
0x18000374e  cmp     [rdi+r8*2], bp
0x180003753  jnz     short loc_18000374B
0x180003755  test    r8d, r8d
0x180003758  jz      loc_1800037E9
0x18000375e  mov     edx, ebp
0x180003760  cmp     r8d, r14d
0x180003763  jz      short loc_180003772
0x180003765  lea     eax, [r8-1]
0x180003769  cmp     word ptr [rdi+rax*2], 2Ah ; '*'
0x18000376e  cmovz   edx, r14d
0x180003772  cmp     word ptr [rdi], 2Ah ; '*'
0x180003776  lea     r9, [rbx+60h]
0x18000377a  mov     eax, ebp
0x18000377c  cmovz   eax, edx
0x18000377f  test    eax, eax
0x180003781  jz      short loc_1800037A6
0x180003783  mov     dword ptr [rbx+0D8h], 4
0x18000378d  add     r8d, 0FFFFFFFEh
0x180003791  jnz     short loc_1800037A0
0x180003793  mov     rcx, [r9+20h]
0x180003797  mov     [rcx], bp
0x18000379a  mov     [r9+30h], ebp
0x18000379e  jmp     short loc_180003800
0x1800037a0  lea     rdx, [rdi+2]
0x1800037a4  jmp     short loc_1800037DA
0x1800037a6  test    edx, edx
0x1800037a8  jz      short loc_1800037BB
0x1800037aa  mov     dword ptr [rbx+0D8h], 2
0x1800037b4  sub     r8d, r14d
0x1800037b7  jnz     short loc_1800037D7
0x1800037b9  jmp     short loc_180003793
0x1800037bb  cmp     word ptr [rdi], 2Ah ; '*'
0x1800037bf  jnz     short loc_1800037D0
0x1800037c1  mov     dword ptr [rbx+0D8h], 3
0x1800037cb  sub     r8d, r14d
0x1800037ce  jmp     short loc_180003791
0x1800037d0  mov     [rbx+0D8h], r14d
0x1800037d7  mov     rdx, rdi
0x1800037da  mov     rcx, r9
0x1800037dd  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800037e3  test    eax, eax
0x1800037e5  jns     short loc_180003800
0x1800037e7  jmp     short loc_18000380F
0x1800037e9  mov     rcx, [rbx+80h]
0x1800037f0  mov     [rbx+0D8h], r14d
0x1800037f7  mov     [rcx], bp
0x1800037fa  mov     [rbx+90h], ebp
0x180003800  mov     eax, [rsp+58h+arg_20]
0x180003807  mov     [rbx+0DCh], eax
0x18000380d  xor     eax, eax
0x18000380f  add     rsp, 28h
0x180003813  pop     r15
0x180003815  pop     r14
0x180003817  pop     rdi
0x180003818  pop     rsi
0x180003819  pop     rbp
0x18000381a  pop     rbx
0x18000381b  retn
```
