# CTSparseBlock<ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::RemoveValue(ulong)

- ea: `0x18002d944`
- end: `0x18002dadc`
- name: `?RemoveValue@?$CTSparseBlock@KUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@$0A@@@QEAAJK@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d6bc`

## callees

- `0x18001a9b0`
- `0x18002d944`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::RemoveValue(
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
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::s_bSingleBitMasks) != 0 )
      {
        v12 = *(_QWORD *)(i + 64);
        v19 = *(_OWORD *)(i + 48);
        v20 = v12;
        v8 = CTSparseBlock<unsigned long,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::SetValue(
               a1,
               v9 - 1,
               &v19);
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
        *(_BYTE *)(v15 + 40) &= *((_BYTE *)&qword_18004A3F0 - v17);
        *(_BYTE *)(v15 + 40) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::s_bLeftBitMasks
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
0x18002d944  push    rbx
0x18002d946  push    rbp
0x18002d947  push    rsi
0x18002d948  push    rdi
0x18002d949  push    r12
0x18002d94b  push    r14
0x18002d94d  push    r15
0x18002d94f  sub     rsp, 40h
0x18002d953  mov     ebp, edx
0x18002d955  mov     rdi, rcx
0x18002d958  mov     rbx, rcx
0x18002d95b  test    rcx, rcx
0x18002d95e  jz      short loc_18002D976
0x18002d960  mov     eax, [rbx+8]
0x18002d963  add     eax, 14h
0x18002d966  cmp     ebp, eax
0x18002d968  jb      short loc_18002D976
0x18002d96a  mov     rbx, [rbx+210h]
0x18002d971  test    rbx, rbx
0x18002d974  jnz     short loc_18002D960
0x18002d976  mov     rax, [rcx+218h]
0x18002d97d  xor     r12d, r12d
0x18002d980  test    rax, rax
0x18002d983  jz      short loc_18002D9A7
0x18002d985  mov     edx, [rcx+220h]
0x18002d98b  mov     ecx, [rax+8]
0x18002d98e  add     ecx, edx
0x18002d990  cmp     ebp, ecx
0x18002d992  jnb     short loc_18002D9A7
0x18002d994  test    edx, edx
0x18002d996  jnz     short loc_18002D99E
0x18002d998  lea     r12d, [rdx+1]
0x18002d99c  jmp     short loc_18002D9A7
0x18002d99e  lea     eax, [rdx-1]
0x18002d9a1  mov     [rdi+220h], eax
0x18002d9a7  xor     r14d, r14d
0x18002d9aa  jmp     loc_18002DAC1
0x18002d9af  mov     edx, [rbx+8]
0x18002d9b2  cmp     ebp, edx
0x18002d9b4  jb      short loc_18002D9C2
0x18002d9b6  mov     esi, ebp
0x18002d9b8  mov     r15d, 1
0x18002d9be  sub     esi, edx
0x18002d9c0  jmp     short loc_18002DA00
0x18002d9c2  mov     al, [rbx+28h]
0x18002d9c5  xor     r15d, r15d
0x18002d9c8  xor     esi, esi
0x18002d9ca  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::s_bSingleBitMasks
0x18002d9d0  jz      short loc_18002DA00
0x18002d9d2  movups  xmm0, xmmword ptr [rbx+30h]
0x18002d9d6  lea     r8, [rsp+78h+var_58]
0x18002d9db  dec     edx
0x18002d9dd  movsd   xmm1, qword ptr [rbx+40h]
0x18002d9e2  mov     rcx, rdi
0x18002d9e5  movaps  [rsp+78h+var_58], xmm0
0x18002d9ea  movsd   [rsp+78h+var_48], xmm1
0x18002d9f0  call    ?SetValue@?$CTSparseBlock@KUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@$0A@@@QEAAJKUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@@Z; CTSparseBlock<ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::SetValue(ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC)
0x18002d9f5  mov     r14d, eax
0x18002d9f8  test    eax, eax
0x18002d9fa  js      loc_18002DACA
0x18002da00  mov     eax, 13h
0x18002da05  lea     ecx, [rsi+1]
0x18002da08  sub     eax, esi
0x18002da0a  lea     rcx, [rcx+2]
0x18002da0e  lea     r8, [rax+rax*2]
0x18002da12  lea     rax, [rcx+rcx*2]
0x18002da16  shl     r8, 3; Size
0x18002da1a  lea     rdx, [rbx+rax*8]; Src
0x18002da1e  mov     eax, esi
0x18002da20  add     rax, 2
0x18002da24  lea     rax, [rax+rax*2]
0x18002da28  lea     rcx, [rbx+rax*8]; void *
0x18002da2c  call    memmove_0
0x18002da31  mov     eax, esi
0x18002da33  shr     eax, 3
0x18002da36  mov     edx, eax
0x18002da38  lea     r10, [rax+rbx]
0x18002da3c  mov     r11b, [r10+28h]
0x18002da40  cmp     eax, 3
0x18002da43  jnb     short loc_18002DA64
0x18002da45  shl     byte ptr [rdx+rbx+28h], 1
0x18002da49  cmp     edx, 2
0x18002da4c  jnb     short loc_18002DA5D
0x18002da4e  lea     eax, [rdx+1]
0x18002da51  cmp     byte ptr [rax+rbx+28h], 0
0x18002da56  jge     short loc_18002DA5D
0x18002da58  or      byte ptr [rdx+rbx+28h], 1
0x18002da5d  inc     edx
0x18002da5f  cmp     edx, 3
0x18002da62  jb      short loc_18002DA45
0x18002da64  test    r15d, r15d
0x18002da67  jz      short loc_18002DA94
0x18002da69  and     sil, 7
0x18002da6d  jbe     short loc_18002DA94
0x18002da6f  movzx   ecx, sil
0x18002da73  lea     rax, qword_18004A3F0
0x18002da7a  sub     rax, rcx
0x18002da7d  mov     al, [rax]
0x18002da7f  and     [r10+28h], al
0x18002da83  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::s_bLeftBitMasks
0x18002da8a  mov     al, [rcx+rax]
0x18002da8d  and     al, r11b
0x18002da90  or      [r10+28h], al
0x18002da94  test    r12d, r12d
0x18002da97  jz      short loc_18002DABA
0x18002da99  mov     rax, [rdi+218h]
0x18002daa0  cmp     [rbx+210h], rax
0x18002daa7  jnz     short loc_18002DABA
0x18002daa9  mov     [rdi+218h], rbx
0x18002dab0  mov     dword ptr [rdi+220h], 13h
0x18002daba  mov     rbx, [rbx+210h]
0x18002dac1  test    rbx, rbx
0x18002dac4  jnz     loc_18002D9AF
0x18002daca  mov     eax, r14d
0x18002dacd  add     rsp, 40h
0x18002dad1  pop     r15
0x18002dad3  pop     r14
0x18002dad5  pop     r12
0x18002dad7  pop     rdi
0x18002dad8  pop     rsi
0x18002dad9  pop     rbp
0x18002dada  pop     rbx
0x18002dadb  retn
```
