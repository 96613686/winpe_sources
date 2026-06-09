# CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::RemoveValue(ulong)

- ea: `0x1800221d0`
- end: `0x180022368`
- name: `?RemoveValue@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@QEAAJK@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022120`

## callees

- `0x18000cb20`
- `0x1800221d0`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::RemoveValue(
        __int64 a1,
        unsigned int a2)
{
  __int64 i; // rbx
  __int64 v5; // rax
  int v6; // r12d
  int v7; // edx
  int v8; // r14d
  unsigned int v9; // edx
  int v10; // r15d
  unsigned int v11; // esi
  __int64 v12; // xmm1_8
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r10
  char j; // r11
  unsigned __int8 v17; // si
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+30h] [rbp-48h]

  for ( i = a1; i; i = *(_QWORD *)(i + 528) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 536);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 544);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 544) = v7 - 1;
      else
        v6 = 1;
    }
  }
  v8 = 0;
  while ( i )
  {
    v9 = *(_DWORD *)(i + 8);
    if ( a2 < v9 )
    {
      v10 = 0;
      v11 = 0;
      if ( (*(_BYTE *)(i + 40)
          & CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::s_bSingleBitMasks[0]) != 0 )
      {
        v12 = *(_QWORD *)(i + 64);
        v19 = *(_OWORD *)(i + 48);
        v20 = v12;
        v8 = CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::SetValue(a1, v9 - 1, &v19);
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 24 * (v11 + 2LL)), (const void *)(i + 24 * (v11 + 1 + 2LL)), 24LL * (19 - v11));
    v13 = v11 >> 3;
    v14 = v13;
    v15 = v13 + i;
    for ( j = *(_BYTE *)(v13 + i + 40); (unsigned int)v14 < 3; v14 = (unsigned int)(v14 + 1) )
    {
      *(_BYTE *)(v14 + i + 40) *= 2;
      if ( (unsigned int)v14 < 2 && *(char *)((unsigned int)(v14 + 1) + i + 40) < 0 )
        *(_BYTE *)(v14 + i + 40) |= 1u;
    }
    if ( v10 )
    {
      v17 = v11 & 7;
      if ( v17 )
      {
        *(_BYTE *)(v15 + 40) &= *((_BYTE *)&qword_18004A270 - v17);
        *(_BYTE *)(v15 + 40) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::s_bLeftBitMasks
                                + v17);
      }
    }
    if ( v6 && *(_QWORD *)(i + 528) == *(_QWORD *)(a1 + 536) )
    {
      *(_QWORD *)(a1 + 536) = i;
      *(_DWORD *)(a1 + 544) = 19;
    }
    i = *(_QWORD *)(i + 528);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800221d0  push    rbx
0x1800221d2  push    rbp
0x1800221d3  push    rsi
0x1800221d4  push    rdi
0x1800221d5  push    r12
0x1800221d7  push    r14
0x1800221d9  push    r15
0x1800221db  sub     rsp, 40h
0x1800221df  mov     ebp, edx
0x1800221e1  mov     rdi, rcx
0x1800221e4  mov     rbx, rcx
0x1800221e7  test    rcx, rcx
0x1800221ea  jz      short loc_180022202
0x1800221ec  mov     eax, [rbx+8]
0x1800221ef  add     eax, 14h
0x1800221f2  cmp     ebp, eax
0x1800221f4  jb      short loc_180022202
0x1800221f6  mov     rbx, [rbx+210h]
0x1800221fd  test    rbx, rbx
0x180022200  jnz     short loc_1800221EC
0x180022202  mov     rax, [rcx+218h]
0x180022209  xor     r12d, r12d
0x18002220c  test    rax, rax
0x18002220f  jz      short loc_180022233
0x180022211  mov     edx, [rcx+220h]
0x180022217  mov     ecx, [rax+8]
0x18002221a  add     ecx, edx
0x18002221c  cmp     ebp, ecx
0x18002221e  jnb     short loc_180022233
0x180022220  test    edx, edx
0x180022222  jnz     short loc_18002222A
0x180022224  lea     r12d, [rdx+1]
0x180022228  jmp     short loc_180022233
0x18002222a  lea     eax, [rdx-1]
0x18002222d  mov     [rdi+220h], eax
0x180022233  xor     r14d, r14d
0x180022236  jmp     loc_18002234D
0x18002223b  mov     edx, [rbx+8]
0x18002223e  cmp     ebp, edx
0x180022240  jb      short loc_18002224E
0x180022242  mov     esi, ebp
0x180022244  mov     r15d, 1
0x18002224a  sub     esi, edx
0x18002224c  jmp     short loc_18002228C
0x18002224e  mov     al, [rbx+28h]
0x180022251  xor     r15d, r15d
0x180022254  xor     esi, esi
0x180022256  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::s_bSingleBitMasks
0x18002225c  jz      short loc_18002228C
0x18002225e  movups  xmm0, xmmword ptr [rbx+30h]
0x180022262  lea     r8, [rsp+78h+var_58]
0x180022267  dec     edx
0x180022269  movsd   xmm1, qword ptr [rbx+40h]
0x18002226e  mov     rcx, rdi
0x180022271  movaps  [rsp+78h+var_58], xmm0
0x180022276  movsd   [rsp+78h+var_48], xmm1
0x18002227c  call    ?SetValue@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@QEAAJKUCOMMAND_RECORD@CASFScriptCommandObjectBase@@@Z; CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::SetValue(ulong,CASFScriptCommandObjectBase::COMMAND_RECORD)
0x180022281  mov     r14d, eax
0x180022284  test    eax, eax
0x180022286  js      loc_180022356
0x18002228c  mov     eax, 13h
0x180022291  lea     ecx, [rsi+1]
0x180022294  sub     eax, esi
0x180022296  lea     rcx, [rcx+2]
0x18002229a  lea     r8, [rax+rax*2]
0x18002229e  lea     rax, [rcx+rcx*2]
0x1800222a2  shl     r8, 3; Size
0x1800222a6  lea     rdx, [rbx+rax*8]; Src
0x1800222aa  mov     eax, esi
0x1800222ac  add     rax, 2
0x1800222b0  lea     rax, [rax+rax*2]
0x1800222b4  lea     rcx, [rbx+rax*8]; void *
0x1800222b8  call    memmove_0
0x1800222bd  mov     eax, esi
0x1800222bf  shr     eax, 3
0x1800222c2  mov     edx, eax
0x1800222c4  lea     r10, [rax+rbx]
0x1800222c8  mov     r11b, [r10+28h]
0x1800222cc  cmp     eax, 3
0x1800222cf  jnb     short loc_1800222F0
0x1800222d1  shl     byte ptr [rdx+rbx+28h], 1
0x1800222d5  cmp     edx, 2
0x1800222d8  jnb     short loc_1800222E9
0x1800222da  lea     eax, [rdx+1]
0x1800222dd  cmp     byte ptr [rax+rbx+28h], 0
0x1800222e2  jge     short loc_1800222E9
0x1800222e4  or      byte ptr [rdx+rbx+28h], 1
0x1800222e9  inc     edx
0x1800222eb  cmp     edx, 3
0x1800222ee  jb      short loc_1800222D1
0x1800222f0  test    r15d, r15d
0x1800222f3  jz      short loc_180022320
0x1800222f5  and     sil, 7
0x1800222f9  jbe     short loc_180022320
0x1800222fb  movzx   ecx, sil
0x1800222ff  lea     rax, qword_18004A270
0x180022306  sub     rax, rcx
0x180022309  mov     al, [rax]
0x18002230b  and     [r10+28h], al
0x18002230f  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::s_bLeftBitMasks
0x180022316  mov     al, [rcx+rax]
0x180022319  and     al, r11b
0x18002231c  or      [r10+28h], al
0x180022320  test    r12d, r12d
0x180022323  jz      short loc_180022346
0x180022325  mov     rax, [rdi+218h]
0x18002232c  cmp     [rbx+210h], rax
0x180022333  jnz     short loc_180022346
0x180022335  mov     [rdi+218h], rbx
0x18002233c  mov     dword ptr [rdi+220h], 13h
0x180022346  mov     rbx, [rbx+210h]
0x18002234d  test    rbx, rbx
0x180022350  jnz     loc_18002223B
0x180022356  mov     eax, r14d
0x180022359  add     rsp, 40h
0x18002235d  pop     r15
0x18002235f  pop     r14
0x180022361  pop     r12
0x180022363  pop     rdi
0x180022364  pop     rsi
0x180022365  pop     rbp
0x180022366  pop     rbx
0x180022367  retn
```
