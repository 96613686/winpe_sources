# mp3SideInfoRead(CBitStream &,MP3SI &,MPEG_INFO const &)

- ea: `0x1800056c0`
- end: `0x180005f75`
- name: `?mp3SideInfoRead@@YA_NAEAVCBitStream@@AEAUMP3SI@@AEBUMPEG_INFO@@@Z`
- size: `2229`
- prototype: `char __fastcall(struct CBitStream *this, struct MP3SI *, const struct MPEG_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000625c`

## callees

- `0x1800056c0`
- `0x180005f80`
- `0x180006068`

## pseudocode

```c
char __fastcall mp3SideInfoRead(struct CBitStream *this, struct MP3SI *a2, const struct MPEG_INFO *a3)
{
  int v3; // r13d
  int i; // r8d
  int j; // edx
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // edx
  int k; // r15d
  int v13; // r11d
  unsigned __int16 v14; // r9
  _DWORD *v15; // rbp
  int v16; // r11d
  unsigned __int16 v17; // r9
  int v18; // esi
  unsigned __int16 v19; // r9
  int v20; // r11d
  unsigned __int16 v21; // r9
  int m; // ecx
  __int64 v23; // r14
  __int64 v24; // rbp
  _DWORD *v25; // rsi
  unsigned int v26; // edx
  unsigned int Bits; // eax
  bool v28; // cc
  int v29; // r11d
  __int64 v30; // r15
  unsigned __int16 v31; // r9
  unsigned int v32; // ecx
  int v33; // r11d
  __int64 v34; // rsi
  unsigned __int16 v35; // r9
  unsigned int v36; // ecx
  int v37; // r11d
  __int64 v38; // r10
  unsigned __int16 v39; // r9
  unsigned int v40; // ecx
  unsigned int v41; // eax
  int v43; // eax
  int v44; // edx
  int n; // ecx
  __int64 v46; // rax
  __int64 v47; // rcx
  int ii; // edx
  int v49; // r8d
  __int64 v50; // r9
  __int64 v51; // rax
  char *v52; // rcx
  int v53; // [rsp+60h] [rbp+18h]

  v3 = 0;
  for ( i = 0; i < (*((_BYTE *)a3 + 32) != 0) + 1; ++i )
  {
    for ( j = 0; j < *(_DWORD *)a3; *(_DWORD *)((char *)a2 + v10 + 128) = 0 )
    {
      v9 = j++;
      v10 = 108LL * i + 232 * v9;
      *(_QWORD *)((char *)a2 + v10 + 96) = 0;
      *(_QWORD *)((char *)a2 + v10 + 104) = 0;
      *(_QWORD *)((char *)a2 + v10 + 112) = 0;
      *(_QWORD *)((char *)a2 + v10 + 120) = 0;
    }
  }
  if ( (unsigned __int8)CrcOk(this) )
  {
    if ( *((_BYTE *)a3 + 32) )
    {
      *(_DWORD *)a2 = CBitStream::GetBits(this, 9u);
      v11 = 5;
      if ( *(_DWORD *)a3 != 1 )
        v11 = 3;
      *((_DWORD *)a2 + 1) = CBitStream::GetBits(this, v11);
      for ( k = 0; k < *(_DWORD *)a3; v15[5] = v21 >> 15 )
      {
        v13 = *((_DWORD *)this + 9);
        v14 = (*(unsigned __int8 *)(((v13 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)this + 6))
             | (unsigned __int16)(*(unsigned __int8 *)(((v13 >> 3) & 0xFFFFFFFE) + *((_QWORD *)this + 6)) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        ++*((_DWORD *)this + 8);
        --*((_DWORD *)this + 6);
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v13 + 1);
        v15 = (_DWORD *)((char *)a2 + 232 * k);
        v15[2] = v14 >> 15;
        v16 = *((_DWORD *)this + 9);
        v17 = (*(unsigned __int8 *)(((v16 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)this + 6))
             | (unsigned __int16)(*(unsigned __int8 *)(((v16 >> 3) & 0xFFFFFFFE) + *((_QWORD *)this + 6)) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        *((_DWORD *)this + 9) = (v16 + 1) & (*((_DWORD *)this + 5) - 1);
        ++*((_DWORD *)this + 8);
        --*((_DWORD *)this + 6);
        v15[3] = v17 >> 15;
        v18 = *((_DWORD *)this + 9);
        v19 = (*(unsigned __int8 *)(((v18 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)this + 6))
             | (unsigned __int16)(*(unsigned __int8 *)(((v18 >> 3) & 0xFFFFFFFE) + *((_QWORD *)this + 6)) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        *((_DWORD *)this + 9) = (v18 + 1) & (*((_DWORD *)this + 5) - 1);
        ++*((_DWORD *)this + 8);
        --*((_DWORD *)this + 6);
        v15[4] = v19 >> 15;
        v20 = *((_DWORD *)this + 9);
        v21 = (*(unsigned __int8 *)(((v20 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)this + 6))
             | (unsigned __int16)(*(unsigned __int8 *)(((v20 >> 3) & 0xFFFFFFFE) + *((_QWORD *)this + 6)) << 8)) << (*((_BYTE *)this + 36) & 0xF);
        ++k;
        *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v20 + 1);
        ++*((_DWORD *)this + 8);
        --*((_DWORD *)this + 6);
      }
    }
    else
    {
      *(_DWORD *)a2 = CBitStream::GetBits(this, 8u);
      if ( *(_DWORD *)a3 == 1 )
        *((_DWORD *)a2 + 1) = CBitStream::GetBits(this, 1u);
      else
        *((_DWORD *)a2 + 1) = CBitStream::GetBits(this, 2u);
    }
    for ( m = 0; ; ++m )
    {
      v53 = m;
      if ( m >= (*((_BYTE *)a3 + 32) != 0) + 1 )
        break;
      while ( v3 < *(_DWORD *)a3 )
      {
        v23 = m;
        v24 = v3;
        v25 = (_DWORD *)((char *)a2 + 232 * v3 + 108 * m);
        v25[6] = CBitStream::GetBits(this, 0xCu);
        v25[7] = CBitStream::GetBits(this, 9u);
        v25[8] = CBitStream::GetBits(this, 8u);
        v26 = 4;
        if ( !*((_BYTE *)a3 + 32) )
          v26 = 9;
        v25[9] = CBitStream::GetBits(this, v26);
        Bits = CBitStream::GetBits(this, 1u);
        v28 = v25[7] <= 288;
        v25[10] = Bits;
        if ( !v28 )
        {
          *((_QWORD *)v25 + 3) = 0;
          v25[9] = 0;
        }
        if ( Bits )
        {
          v25[11] = CBitStream::GetBits(this, 2u);
          v25[12] = CBitStream::GetBits(this, 1u);
          v25[13] = CBitStream::GetBits(this, 5u);
          v25[14] = CBitStream::GetBits(this, 5u);
          v25[15] = 0;
          v25[16] = CBitStream::GetBits(this, 3u);
          v25[17] = CBitStream::GetBits(this, 3u);
          v25[18] = CBitStream::GetBits(this, 3u);
          v43 = v25[11];
          if ( !v43 )
            goto LABEL_40;
          if ( v43 != 2 || v25[12] )
          {
            v25[19] = 7;
            v41 = 13;
          }
          else
          {
            v25[19] = 8;
            v41 = 12;
          }
        }
        else
        {
          v29 = *((_DWORD *)this + 9);
          v30 = *((_QWORD *)this + 6);
          v31 = (*(unsigned __int8 *)(((v29 >> 3) & 0xFFFFFFFE) + 1 + v30)
               | (unsigned __int16)(*(unsigned __int8 *)(((v29 >> 3) & 0xFFFFFFFE) + v30) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v32 = 16 - (v29 & 0xF);
          if ( v32 < 5 )
            v31 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)this + 4) - 1) & (((v29 >> 3) & 0xFFFFFFFE) + 2))
                                                         + 1
                                                         + v30)
                                    | (*(unsigned __int8 *)(((*((_DWORD *)this + 4) - 1)
                                                           & (((v29 >> 3) & 0xFFFFFFFE) + 2))
                                                          + v30) << 8)) >> v32;
          *((_DWORD *)this + 8) += 5;
          *((_DWORD *)this + 6) -= 5;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v29 + 5);
          v25[13] = v31 >> 11;
          v33 = *((_DWORD *)this + 9);
          v34 = *((_QWORD *)this + 6);
          v35 = (*(unsigned __int8 *)(((v33 >> 3) & 0xFFFFFFFE) + 1 + v34)
               | (unsigned __int16)(*(unsigned __int8 *)(((v33 >> 3) & 0xFFFFFFFE) + v34) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v36 = 16 - (v33 & 0xF);
          if ( v36 < 5 )
            v35 |= (unsigned __int16)(*(unsigned __int8 *)(((((v33 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1))
                                                         + 1
                                                         + v34)
                                    | (*(unsigned __int8 *)(((((v33 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + v34) << 8)) >> v36;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v33 + 5);
          *((_DWORD *)this + 8) += 5;
          *((_DWORD *)this + 6) -= 5;
          *((_DWORD *)a2 + 58 * v3 + 27 * v23 + 14) = v35 >> 11;
          v37 = *((_DWORD *)this + 9);
          v38 = *((_QWORD *)this + 6);
          v39 = (*(unsigned __int8 *)(((v37 >> 3) & 0xFFFFFFFE) + 1 + v38)
               | (unsigned __int16)(*(unsigned __int8 *)(((v37 >> 3) & 0xFFFFFFFE) + v38) << 8)) << (*((_BYTE *)this + 36) & 0xF);
          v40 = 16 - (v37 & 0xF);
          if ( v40 < 5 )
            v39 |= (unsigned __int16)(*(unsigned __int8 *)(((((v37 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)this + 4) - 1))
                                                         + 1
                                                         + v38)
                                    | (*(unsigned __int8 *)(((((v37 >> 3) & 0xFFFFFFFE) + 2)
                                                           & (*((_DWORD *)this + 4) - 1))
                                                          + v38) << 8)) >> v40;
          *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & (v37 + 5);
          *((_DWORD *)this + 8) += 5;
          *((_DWORD *)this + 6) -= 5;
          *((_DWORD *)a2 + 58 * v3 + 27 * v23 + 15) = v39 >> 11;
          *((_DWORD *)a2 + 58 * v3 + 27 * v23 + 19) = CBitStream::GetBits(this, 4u);
          v41 = CBitStream::GetBits(this, 3u);
          *((_DWORD *)a2 + 58 * v3 + 27 * v23 + 11) = 0;
          v25 = (_DWORD *)((char *)a2 + 232 * v3 + 108 * v23);
        }
        v25[20] = v41;
        if ( *((_BYTE *)a3 + 32) )
          *((_DWORD *)a2 + 58 * v3 + 27 * v23 + 21) = CBitStream::GetBits(this, 1u);
        *((_DWORD *)a2 + 58 * v3++ + 27 * v23 + 22) = CBitStream::GetBits(this, 1u);
        *((_DWORD *)a2 + 58 * v24 + 27 * v23 + 23) = CBitStream::GetBits(this, 1u);
        m = v53;
      }
      v3 = 0;
    }
    return 1;
  }
  else
  {
LABEL_40:
    *(_DWORD *)a2 = 0;
    v44 = 0;
    for ( n = *(_DWORD *)a3; v44 < *(_DWORD *)a3; n = *(_DWORD *)a3 )
    {
      v46 = v44++;
      v47 = 232 * v46;
      *(_QWORD *)((char *)a2 + v47 + 8) = 0;
      *(_QWORD *)((char *)a2 + v47 + 16) = 0;
    }
    for ( ii = 0; ii < (*((_BYTE *)a3 + 32) != 0) + 1; ++ii )
    {
      v49 = 0;
      if ( n > 0 )
      {
        v50 = 108LL * ii;
        do
        {
          v51 = v49++;
          v52 = (char *)a2 + 232 * v51;
          *(_QWORD *)&v52[v50 + 24] = 0;
          *(_QWORD *)&v52[v50 + 36] = 0;
          *(_QWORD *)&v52[v50 + 44] = 0;
          *(_QWORD *)&v52[v50 + 52] = 0;
          *(_QWORD *)&v52[v50 + 60] = 0;
          *(_QWORD *)&v52[v50 + 68] = 0;
          *(_QWORD *)&v52[v50 + 76] = 0;
          *(_QWORD *)&v52[v50 + 84] = 0;
          *(_DWORD *)&v52[v50 + 92] = 0;
          n = *(_DWORD *)a3;
        }
        while ( v49 < *(_DWORD *)a3 );
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800056c0  push    rbx
0x1800056c2  push    rdi
0x1800056c3  push    r12
0x1800056c5  push    r13
0x1800056c7  sub     rsp, 28h
0x1800056cb  xor     r13d, r13d
0x1800056ce  mov     r12, r8
0x1800056d1  mov     r8d, r13d
0x1800056d4  mov     rdi, rdx
0x1800056d7  mov     rbx, rcx
0x1800056da  cmp     [r12+20h], r13b
0x1800056df  mov     eax, r13d
0x1800056e2  setnz   al
0x1800056e5  inc     eax
0x1800056e7  cmp     r8d, eax
0x1800056ea  jge     short loc_180005732
0x1800056ec  mov     edx, r13d
0x1800056ef  cmp     [r12], r13d
0x1800056f3  jle     short loc_18000572D
0x1800056f5  movsxd  rax, r8d
0x1800056f8  imul    r9, rax, 6Ch ; 'l'
0x1800056fc  movsxd  rax, edx
0x1800056ff  inc     edx
0x180005701  imul    rcx, rax, 0E8h
0x180005708  add     rcx, r9
0x18000570b  mov     [rcx+rdi+60h], r13
0x180005710  mov     [rcx+rdi+68h], r13
0x180005715  mov     [rcx+rdi+70h], r13
0x18000571a  mov     [rcx+rdi+78h], r13
0x18000571f  mov     [rcx+rdi+80h], r13d
0x180005727  cmp     edx, [r12]
0x18000572b  jl      short loc_1800056FC
0x18000572d  inc     r8d
0x180005730  jmp     short loc_1800056DA
0x180005732  mov     [rsp+48h+arg_0], rbp
0x180005737  mov     rdx, r12
0x18000573a  mov     [rsp+48h+arg_8], rsi
0x18000573f  mov     rcx, rbx; this
0x180005742  mov     [rsp+48h+arg_18], r14
0x180005747  mov     [rsp+48h+var_28], r15
0x18000574c  call    CrcOk
0x180005751  test    al, al
0x180005753  jz      loc_180005EAA
0x180005759  mov     r15d, 3
0x18000575f  mov     rcx, rbx; this
0x180005762  cmp     [r12+20h], r13b
0x180005767  jz      loc_180005DAA
0x18000576d  mov     edx, 9; unsigned int
0x180005772  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180005777  mov     [rdi], eax
0x180005779  mov     edx, 5
0x18000577e  cmp     dword ptr [r12], 1
0x180005783  mov     rcx, rbx; this
0x180005786  cmovnz  edx, r15d; unsigned int
0x18000578a  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000578f  mov     [rdi+4], eax
0x180005792  mov     r15d, r13d
0x180005795  cmp     [r12], r13d
0x180005799  jle     loc_180005958
0x18000579f  lea     r14, [rbx+10h]
0x1800057a3  nop     dword ptr [rax+00h]
0x1800057a7  nop     word ptr [rax+rax+00000000h]
0x1800057b0  mov     r11d, [rbx+24h]
0x1800057b4  mov     eax, r11d
0x1800057b7  mov     r10, [rbx+30h]
0x1800057bb  mov     edx, r11d
0x1800057be  sar     eax, 3
0x1800057c1  and     edx, 0Fh
0x1800057c4  and     eax, 0FFFFFFFEh
0x1800057c7  mov     ecx, edx
0x1800057c9  mov     r8d, eax
0x1800057cc  movzx   r9d, byte ptr [rax+r10]
0x1800057d1  inc     eax
0x1800057d3  shl     r9w, 8
0x1800057d8  movzx   eax, byte ptr [rax+r10]
0x1800057dd  or      r9w, ax
0x1800057e1  shl     r9w, cl
0x1800057e5  mov     ecx, 10h
0x1800057ea  sub     ecx, edx
0x1800057ec  cmp     ecx, 1
0x1800057ef  jb      loc_180005CE6
0x1800057f5  inc     dword ptr [rbx+20h]
0x1800057f8  lea     ecx, [r11+1]
0x1800057fc  dec     dword ptr [rbx+18h]
0x1800057ff  mov     eax, [rbx+14h]
0x180005802  dec     eax
0x180005804  and     ecx, eax
0x180005806  movsxd  rax, r15d
0x180005809  imul    rbp, rax, 0E8h
0x180005810  mov     [rbx+24h], ecx
0x180005813  movzx   eax, r9w
0x180005817  add     rbp, rdi
0x18000581a  shr     eax, 0Fh
0x18000581d  mov     [rbp+8], eax
0x180005820  mov     r11d, [rbx+24h]
0x180005824  mov     eax, r11d
0x180005827  mov     r10, [rbx+30h]
0x18000582b  mov     edx, r11d
0x18000582e  sar     eax, 3
0x180005831  and     edx, 0Fh
0x180005834  and     eax, 0FFFFFFFEh
0x180005837  mov     ecx, edx
0x180005839  mov     r8d, eax
0x18000583c  movzx   r9d, byte ptr [rax+r10]
0x180005841  inc     eax
0x180005843  shl     r9w, 8
0x180005848  movzx   eax, byte ptr [rax+r10]
0x18000584d  or      r9w, ax
0x180005851  shl     r9w, cl
0x180005855  mov     ecx, 10h
0x18000585a  sub     ecx, edx
0x18000585c  cmp     ecx, 1
0x18000585f  jb      loc_180005D15
0x180005865  lea     r8, [rbx+10h]
0x180005869  mov     ecx, [rbx+14h]
0x18000586c  lea     eax, [r11+1]
0x180005870  dec     ecx
0x180005872  and     ecx, eax
0x180005874  movzx   eax, r9w
0x180005878  mov     [rbx+24h], ecx
0x18000587b  inc     dword ptr [rbx+20h]
0x18000587e  dec     dword ptr [rbx+18h]
0x180005881  shr     eax, 0Fh
0x180005884  mov     [rbp+0Ch], eax
0x180005887  mov     esi, [rbx+24h]
0x18000588a  mov     eax, esi
0x18000588c  mov     r10, [rbx+30h]
0x180005890  mov     edx, esi
0x180005892  sar     eax, 3
0x180005895  and     edx, 0Fh
0x180005898  and     eax, 0FFFFFFFEh
0x18000589b  mov     ecx, edx
0x18000589d  mov     r11d, eax
0x1800058a0  movzx   r9d, byte ptr [rax+r10]
0x1800058a5  inc     eax
0x1800058a7  shl     r9w, 8
0x1800058ac  movzx   eax, byte ptr [rax+r10]
0x1800058b1  or      r9w, ax
0x1800058b5  shl     r9w, cl
0x1800058b9  mov     ecx, 10h
0x1800058be  sub     ecx, edx
0x1800058c0  cmp     ecx, 1
0x1800058c3  jb      loc_180005D47
0x1800058c9  mov     ecx, [rbx+14h]
0x1800058cc  lea     eax, [rsi+1]
0x1800058cf  dec     ecx
0x1800058d1  and     ecx, eax
0x1800058d3  movzx   eax, r9w
0x1800058d7  mov     [rbx+24h], ecx
0x1800058da  inc     dword ptr [rbx+20h]
0x1800058dd  dec     dword ptr [rbx+18h]
0x1800058e0  shr     eax, 0Fh
0x1800058e3  mov     [rbp+10h], eax
0x1800058e6  mov     r11d, [rbx+24h]
0x1800058ea  mov     eax, r11d
0x1800058ed  mov     r10, [rbx+30h]
0x1800058f1  mov     edx, r11d
0x1800058f4  sar     eax, 3
0x1800058f7  and     edx, 0Fh
0x1800058fa  and     eax, 0FFFFFFFEh
0x1800058fd  mov     ecx, edx
0x1800058ff  mov     esi, eax
0x180005901  movzx   r9d, byte ptr [rax+r10]
0x180005906  inc     eax
0x180005908  shl     r9w, 8
0x18000590d  movzx   eax, byte ptr [rax+r10]
0x180005912  or      r9w, ax
0x180005916  shl     r9w, cl
0x18000591a  mov     ecx, 10h
0x18000591f  sub     ecx, edx
0x180005921  cmp     ecx, 1
0x180005924  jb      loc_180005D79
0x18000592a  mov     eax, [rbx+14h]
0x18000592d  lea     ecx, [r11+1]
0x180005931  dec     eax
0x180005933  inc     r15d
0x180005936  and     ecx, eax
0x180005938  mov     r14, r8
0x18000593b  mov     [rbx+24h], ecx
0x18000593e  inc     dword ptr [rbx+20h]
0x180005941  dec     dword ptr [rbx+18h]
0x180005944  movzx   eax, r9w
0x180005948  shr     eax, 0Fh
0x18000594b  mov     [rbp+14h], eax
0x18000594e  cmp     r15d, [r12]
0x180005952  jl      loc_1800057B0
0x180005958  mov     r15d, 3
0x18000595e  mov     ecx, r13d
0x180005961  cmp     byte ptr [r12+20h], 0
0x180005967  mov     eax, r13d
0x18000596a  mov     [rsp+48h+arg_10], ecx
0x18000596e  setnz   al
0x180005971  inc     eax
0x180005973  cmp     ecx, eax
0x180005975  jge     loc_180005CC5
0x18000597b  cmp     r13d, [r12]
0x18000597f  jge     loc_180005C2F
0x180005985  movsxd  r14, ecx
0x180005988  mov     edx, 0Ch; unsigned int
0x18000598d  movsxd  rbp, r13d
0x180005990  mov     rcx, rbx; this
0x180005993  imul    rax, rbp, 0E8h
0x18000599a  imul    rsi, r14, 6Ch ; 'l'
0x18000599e  add     rax, rdi
0x1800059a1  add     rsi, rax
0x1800059a4  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x1800059a9  mov     edx, 9; unsigned int
0x1800059ae  mov     [rsi+18h], eax
0x1800059b1  mov     rcx, rbx; this
0x1800059b4  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x1800059b9  mov     edx, 8; unsigned int
0x1800059be  mov     [rsi+1Ch], eax
0x1800059c1  mov     rcx, rbx; this
0x1800059c4  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x1800059c9  mov     [rsi+20h], eax
0x1800059cc  mov     edx, 4
0x1800059d1  cmp     byte ptr [r12+20h], 0
0x1800059d7  mov     eax, 9
0x1800059dc  mov     rcx, rbx; this
0x1800059df  cmovz   edx, eax; unsigned int
0x1800059e2  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x1800059e7  mov     edx, 1; unsigned int
0x1800059ec  mov     [rsi+24h], eax
0x1800059ef  mov     rcx, rbx; this
0x1800059f2  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x1800059f7  cmp     dword ptr [rsi+1Ch], 120h
0x1800059fe  mov     [rsi+28h], eax
0x180005a01  jg      loc_180005E93
0x180005a07  test    eax, eax
0x180005a09  jnz     loc_180005DD6
0x180005a0f  mov     r11d, [rbx+24h]
0x180005a13  mov     eax, r11d
0x180005a16  mov     r15, [rbx+30h]
0x180005a1a  mov     edx, r11d
0x180005a1d  sar     eax, 3
0x180005a20  and     edx, 0Fh
0x180005a23  and     eax, 0FFFFFFFEh
0x180005a26  mov     ecx, edx
0x180005a28  mov     r8d, eax
0x180005a2b  movzx   r9d, byte ptr [rax+r15]
0x180005a30  inc     eax
0x180005a32  shl     r9w, 8
0x180005a37  movzx   eax, byte ptr [rax+r15]
0x180005a3c  or      r9w, ax
0x180005a40  shl     r9w, cl
0x180005a44  mov     ecx, 10h
0x180005a49  sub     ecx, edx
0x180005a4b  cmp     ecx, 5
0x180005a4e  jb      loc_180005C39
0x180005a54  add     dword ptr [rbx+20h], 5
0x180005a58  lea     ecx, [r11+5]
0x180005a5c  add     dword ptr [rbx+18h], 0FFFFFFFBh
0x180005a60  lea     r15, [rbx+24h]
0x180005a64  mov     eax, [rbx+14h]
0x180005a67  dec     eax
0x180005a69  and     ecx, eax
0x180005a6b  movzx   eax, r9w
0x180005a6f  shr     eax, 0Bh
0x180005a72  mov     [rbx+24h], ecx
0x180005a75  mov     [rsi+34h], eax
0x180005a78  mov     r11d, [rbx+24h]
0x180005a7c  mov     eax, r11d
0x180005a7f  mov     rsi, [rbx+30h]
0x180005a83  mov     edx, r11d
0x180005a86  sar     eax, 3
0x180005a89  and     edx, 0Fh
0x180005a8c  and     eax, 0FFFFFFFEh
0x180005a8f  mov     ecx, edx
0x180005a91  mov     r8d, eax
0x180005a94  movzx   r9d, byte ptr [rax+rsi]
0x180005a99  inc     eax
0x180005a9b  shl     r9w, 8
0x180005aa0  movzx   eax, byte ptr [rax+rsi]
0x180005aa4  or      r9w, ax
0x180005aa8  shl     r9w, cl
0x180005aac  mov     ecx, 10h
0x180005ab1  sub     ecx, edx
0x180005ab3  cmp     ecx, 5
0x180005ab6  jb      loc_180005C68
0x180005abc  mov     eax, [rbx+14h]
0x180005abf  lea     ecx, [r11+5]
0x180005ac3  dec     eax
0x180005ac5  movzx   edx, r9w
0x180005ac9  and     ecx, eax
0x180005acb  shr     edx, 0Bh
0x180005ace  mov     [rbx+24h], ecx
0x180005ad1  add     dword ptr [rbx+20h], 5
0x180005ad5  add     dword ptr [rbx+18h], 0FFFFFFFBh
0x180005ad9  imul    rcx, r14, 6Ch ; 'l'
0x180005add  imul    rax, rbp, 0E8h
0x180005ae4  add     rax, rdi
0x180005ae7  mov     [rcx+rax+38h], edx
0x180005aeb  mov     r11d, [rbx+24h]
0x180005aef  mov     eax, r11d
0x180005af2  mov     r10, [rbx+30h]
0x180005af6  mov     edx, r11d
0x180005af9  sar     eax, 3
0x180005afc  and     edx, 0Fh
0x180005aff  and     eax, 0FFFFFFFEh
0x180005b02  mov     ecx, edx
  ... truncated ...
```
