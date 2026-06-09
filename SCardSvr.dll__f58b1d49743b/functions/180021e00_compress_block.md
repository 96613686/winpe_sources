# compress_block

- ea: `0x180021e00`
- end: `0x180022228`
- name: `compress_block`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021500`

## callees

- `0x180021e00`

## pseudocode

```c
__int64 __fastcall compress_block(__int64 a1, __int64 a2, __int64 a3)
{
  int *v3; // r11
  __int64 v4; // r10
  _DWORD *v5; // rax
  __int64 v6; // r14
  _QWORD *v7; // rdi
  __int64 v8; // r12
  __int64 v10; // r9
  _QWORD *v11; // r13
  _DWORD *v12; // rsi
  int v13; // r8d
  __int64 v14; // r14
  int v15; // edx
  __int64 v16; // r14
  __int64 v17; // rbp
  int v18; // ecx
  unsigned __int16 v19; // r9
  int v20; // edi
  __int16 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // edx
  __int64 v25; // r13
  __int64 v26; // rcx
  unsigned __int16 v27; // r9
  int v28; // esi
  __int16 v29; // dx
  __int64 v30; // rcx
  char v31; // dl
  int v32; // r8d
  __int16 v33; // r9
  int v34; // r12d
  unsigned __int16 v35; // bp
  __int16 v36; // si
  int v37; // r8d
  char v38; // cl
  __int16 v39; // bp
  __int16 v40; // si
  unsigned int v41; // ecx
  int v42; // r12d
  unsigned __int16 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int16 v46; // r8
  _QWORD *v47; // r13
  int v48; // r12d
  _DWORD *v49; // rdx
  __int16 v50; // r9
  int v51; // ebp
  unsigned __int16 v52; // si
  __int16 v53; // r8
  int v54; // r8d
  unsigned __int16 v55; // r9
  int v56; // ebx
  int v57; // ecx
  __int16 v58; // dx
  __int64 result; // rax
  _QWORD *v60; // [rsp+0h] [rbp-58h]
  int v61; // [rsp+60h] [rbp+8h]
  __int64 v62; // [rsp+60h] [rbp+8h]

  v3 = (int *)(a1 + 5904);
  v4 = a1 + 5900;
  v5 = (_DWORD *)(a1 + 40);
  v6 = 0;
  v7 = (_QWORD *)(a1 + 16);
  v8 = a2;
  if ( *(_DWORD *)(a1 + 5876) )
  {
    while ( 1 )
    {
      v10 = *(_QWORD *)(a1 + 5864);
      v11 = v7;
      v60 = v7;
      v12 = v5;
      v13 = *(unsigned __int8 *)(v6 + v10);
      v14 = (unsigned int)(v6 + 1);
      v15 = *(unsigned __int8 *)(v14 + v10);
      v16 = (unsigned int)(v14 + 1);
      v61 = v13 + (v15 << 8);
      v17 = *(unsigned __int8 *)(v16 + v10);
      v6 = (unsigned int)(v16 + 1);
      if ( !v61 )
      {
        v18 = *v3;
        v19 = *(_WORD *)(v8 + 4 * v17);
        v20 = *(unsigned __int16 *)(v8 + 4 * v17 + 2);
        v21 = *(_WORD *)v4 | (v19 << *v3);
        if ( *v3 <= 16 - v20 )
        {
          *(_WORD *)v4 = v21;
          *v3 = v18 + v20;
          v5 = (_DWORD *)(a1 + 40);
          v7 = (_QWORD *)(a1 + 16);
        }
        else
        {
          v22 = *(unsigned int *)(a1 + 40);
          v23 = *(_QWORD *)(a1 + 16);
          *(_WORD *)v4 = v21;
          *(_BYTE *)(v22 + v23) = v21;
          *(_BYTE *)((unsigned int)++*(_DWORD *)(a1 + 40) + *(_QWORD *)(a1 + 16)) = *(_BYTE *)(v4 + 1);
          LODWORD(v23) = *v3;
          LOBYTE(v22) = 16 - *v3;
          ++*(_DWORD *)(a1 + 40);
          v24 = v20 + v23 - 16;
          v5 = (_DWORD *)(a1 + 40);
          v7 = (_QWORD *)(a1 + 16);
          *(_WORD *)v4 = v19 >> v22;
          *v3 = v24;
        }
        goto LABEL_26;
      }
      v25 = (unsigned __int8)length_code[v17];
      v26 = (unsigned int)(v25 + 257);
      v27 = *(_WORD *)(v8 + 4 * v26);
      v28 = *(unsigned __int16 *)(v8 + 4 * v26 + 2);
      v29 = *(_WORD *)v4 | (v27 << *v3);
      if ( *v3 <= 16 - v28 )
      {
        v32 = v28 + *v3;
        v33 = *(_WORD *)v4 | (v27 << *v3);
      }
      else
      {
        v30 = *v7;
        *(_WORD *)v4 = v29;
        *(_BYTE *)((unsigned int)(*v5)++ + v30) = v29;
        *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
        LODWORD(v30) = *v3;
        v31 = 16 - *v3;
        ++*v5;
        v32 = v28 + v30 - 16;
        v33 = v27 >> v31;
      }
      *(_WORD *)v4 = v33;
      *v3 = v32;
      v34 = dword_180038700[v25];
      if ( v34 )
      {
        v35 = v17 - word_180038D70[2 * v25];
        v36 = v33 | (v35 << v32);
        *(_WORD *)v4 = v36;
        if ( v32 <= 16 - v34 )
        {
          v32 += v34;
          v39 = v36;
        }
        else
        {
          *(_BYTE *)((unsigned int)(*v5)++ + *v7) = v36;
          *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
          v37 = *v3;
          v38 = 16 - *v3;
          ++*v5;
          v39 = v35 >> v38;
          v32 = v34 + v37 - 16;
          *(_WORD *)v4 = v39;
        }
        *v3 = v32;
      }
      else
      {
        v39 = v33;
      }
      v40 = v61 - 1;
      v41 = v61 - 1;
      if ( (unsigned int)(v61 - 1) >= 0x100 )
        v41 = (v41 >> 7) + 256;
      v62 = 4LL * *((unsigned __int8 *)dist_code + v41);
      v42 = *(unsigned __int16 *)(v62 + a3 + 2);
      v43 = *(_WORD *)(v62 + a3);
      if ( v32 <= 16 - v42 )
      {
        v48 = v32 + v42;
        v50 = v39 | (v43 << v32);
        v49 = (_DWORD *)(a1 + 40);
        v47 = (_QWORD *)(a1 + 16);
      }
      else
      {
        v44 = (unsigned int)*v5;
        v45 = *v7;
        v46 = v39 | (v43 << v32);
        *(_WORD *)v4 = v46;
        v47 = v7;
        *(_BYTE *)(v44 + v45) = v46;
        *(_BYTE *)((unsigned int)++*v5 + *v7) = *(_BYTE *)(v4 + 1);
        LODWORD(v45) = *v3;
        v48 = *v3 + v42 - 16;
        ++*v5;
        v49 = v5;
        v50 = v43 >> (16 - v45);
      }
      *(_WORD *)v4 = v50;
      *v3 = v48;
      v51 = *(_DWORD *)((char *)&qword_180038720[12] + v62);
      if ( !v51 )
        goto LABEL_24;
      v52 = v40 - *(_WORD *)((char *)qword_180038DF0 + v62);
      v53 = v50 | (v52 << v48);
      *(_WORD *)v4 = v53;
      if ( v48 <= 16 - v51 )
        break;
      v11 = v7;
      *(_BYTE *)((unsigned int)(*v5)++ + *v7) = v53;
      *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
      v54 = *v3;
      ++*v5;
      *(_WORD *)v4 = v52 >> (16 - v54);
      *v3 = v54 + v51 - 16;
      v12 = v5;
LABEL_25:
      v8 = a2;
LABEL_26:
      if ( (unsigned int)v6 >= *(_DWORD *)(a1 + 5876) )
        goto LABEL_29;
    }
    *v3 = v48 + v51;
LABEL_24:
    v12 = v5;
    v7 = v47;
    v11 = v60;
    v5 = v49;
    goto LABEL_25;
  }
  v12 = (_DWORD *)(a1 + 40);
  v11 = (_QWORD *)(a1 + 16);
LABEL_29:
  v55 = *(_WORD *)(v8 + 1024);
  v56 = *(unsigned __int16 *)(v8 + 1026);
  v57 = *v3;
  v58 = *(_WORD *)v4 | (v55 << *v3);
  *(_WORD *)v4 = v58;
  if ( v57 <= 16 - v56 )
  {
    result = (unsigned int)(v57 + v56);
    *v3 = result;
  }
  else
  {
    *(_BYTE *)((unsigned int)(*v12)++ + *v11) = v58;
    *(_BYTE *)((unsigned int)*v12 + *v11) = *(_BYTE *)(v4 + 1);
    result = (unsigned int)*v3;
    ++*v12;
    *(_WORD *)v4 = v55 >> (16 - result);
    *v3 = v56 + result - 16;
  }
  return result;
}

```

## disassembly

```asm
0x180021e00  mov     [rsp+arg_10], r8
0x180021e05  mov     [rsp+arg_8], rdx
0x180021e0a  push    rbx
0x180021e0b  push    rsi
0x180021e0c  push    r13
0x180021e0e  push    r15
0x180021e10  sub     rsp, 38h
0x180021e14  mov     [rsp+58h+var_30], rdi
0x180021e19  lea     r11, [rcx+1710h]
0x180021e20  mov     [rsp+58h+var_38], r12
0x180021e25  lea     r10, [rcx+170Ch]
0x180021e2c  mov     [rsp+58h+var_40], r14
0x180021e31  lea     rax, [rcx+28h]
0x180021e35  xor     r14d, r14d
0x180021e38  lea     rdi, [rcx+10h]
0x180021e3c  mov     r12, rdx
0x180021e3f  mov     rbx, rcx
0x180021e42  mov     r15d, 10h
0x180021e48  cmp     [rcx+16F4h], r14d
0x180021e4f  jz      loc_18002218E
0x180021e55  mov     [rsp+58h+var_28], rbp
0x180021e5a  nop     word ptr [rax+rax+00h]
0x180021e60  mov     r9, [rbx+16E8h]
0x180021e67  mov     r13, rdi
0x180021e6a  mov     [rsp+58h+var_58], rdi
0x180021e6e  mov     rsi, rax
0x180021e71  mov     [rsp+58h+arg_18], rax
0x180021e76  movzx   r8d, byte ptr [r14+r9]
0x180021e7b  inc     r14d
0x180021e7e  movzx   edx, byte ptr [r14+r9]
0x180021e83  inc     r14d
0x180021e86  shl     edx, 8
0x180021e89  add     edx, r8d
0x180021e8c  mov     dword ptr [rsp+58h+arg_0], edx
0x180021e90  movzx   ebp, byte ptr [r14+r9]
0x180021e95  inc     r14d
0x180021e98  test    edx, edx
0x180021e9a  jnz     loc_180021F27
0x180021ea0  mov     ecx, [r11]
0x180021ea3  mov     eax, r15d
0x180021ea6  movzx   r9d, word ptr [r12+rbp*4]
0x180021eab  movzx   edi, word ptr [r12+rbp*4+2]
0x180021eb1  movzx   r8d, r9w
0x180021eb5  shl     r8w, cl
0x180021eb9  sub     eax, edi
0x180021ebb  or      r8w, [r10]
0x180021ebf  cmp     ecx, eax
0x180021ec1  jle     short loc_180021F0C
0x180021ec3  mov     ecx, [rbx+28h]
0x180021ec6  mov     rax, [rbx+10h]
0x180021eca  mov     [r10], r8w
0x180021ece  mov     [rcx+rax], r8b
0x180021ed2  inc     dword ptr [rbx+28h]
0x180021ed5  mov     edx, [rbx+28h]
0x180021ed8  movzx   eax, byte ptr [r10+1]
0x180021edd  mov     rcx, [rbx+10h]
0x180021ee1  mov     [rdx+rcx], al
0x180021ee4  mov     ecx, r15d
0x180021ee7  mov     eax, [r11]
0x180021eea  sub     cl, al
0x180021eec  inc     dword ptr [rbx+28h]
0x180021eef  lea     edx, [rax-10h]
0x180021ef2  add     edx, edi
0x180021ef4  lea     rax, [rbx+28h]
0x180021ef8  shr     r9w, cl
0x180021efc  lea     rdi, [rbx+10h]
0x180021f00  mov     [r10], r9w
0x180021f04  mov     [r11], edx
0x180021f07  jmp     loc_18002217A
0x180021f0c  lea     edx, [rcx+rdi]
0x180021f0f  mov     [r10], r8w
0x180021f13  mov     [r11], edx
0x180021f16  lea     rax, [rbx+28h]
0x180021f1a  movzx   r9d, r8w
0x180021f1e  lea     rdi, [rbx+10h]
0x180021f22  jmp     loc_18002217A
0x180021f27  mov     r8d, [r11]
0x180021f2a  lea     rcx, cs:180000000h
0x180021f31  movzx   r13d, ds:rva _length_code[rcx+rbp]
0x180021f3a  lea     ecx, [r13+101h]
0x180021f41  movzx   r9d, word ptr [r12+rcx*4]
0x180021f46  movzx   esi, word ptr [r12+rcx*4+2]
0x180021f4c  movzx   edx, r9w
0x180021f50  mov     ecx, r8d
0x180021f53  shl     dx, cl
0x180021f56  mov     ecx, r15d
0x180021f59  or      dx, [r10]
0x180021f5d  sub     ecx, esi
0x180021f5f  cmp     r8d, ecx
0x180021f62  jle     short loc_180021FA0
0x180021f64  mov     rcx, [rdi]
0x180021f67  movzx   r8d, dx
0x180021f6b  mov     [r10], dx
0x180021f6f  mov     edx, [rax]
0x180021f71  mov     [rdx+rcx], r8b
0x180021f75  inc     dword ptr [rax]
0x180021f77  mov     r8d, [rax]
0x180021f7a  mov     rdx, [rdi]
0x180021f7d  movzx   ecx, byte ptr [r10+1]
0x180021f82  mov     [r8+rdx], cl
0x180021f86  mov     edx, r15d
0x180021f89  mov     ecx, [r11]
0x180021f8c  sub     dl, cl
0x180021f8e  inc     dword ptr [rax]
0x180021f90  lea     r8d, [rcx-10h]
0x180021f94  movzx   ecx, dl
0x180021f97  add     r8d, esi
0x180021f9a  shr     r9w, cl
0x180021f9e  jmp     short loc_180021FA7
0x180021fa0  add     r8d, esi
0x180021fa3  movzx   r9d, dx
0x180021fa7  mov     rcx, r13
0x180021faa  mov     [r10], r9w
0x180021fae  lea     r13, cs:180000000h
0x180021fb5  mov     [r11], r8d
0x180021fb8  mov     r12d, ds:rva dword_180038700[r13+rcx*4]
0x180021fc0  test    r12d, r12d
0x180021fc3  jz      short loc_18002202D
0x180021fc5  sub     bp, ds:rva word_180038D70[r13+rcx*4]
0x180021fce  mov     ecx, r8d
0x180021fd1  movzx   esi, bp
0x180021fd4  shl     si, cl
0x180021fd7  mov     ecx, r15d
0x180021fda  or      si, r9w
0x180021fde  sub     ecx, r12d
0x180021fe1  mov     [r10], si
0x180021fe5  cmp     r8d, ecx
0x180021fe8  jle     short loc_180022022
0x180021fea  mov     edx, [rax]
0x180021fec  mov     rcx, [rdi]
0x180021fef  mov     [rdx+rcx], sil
0x180021ff3  inc     dword ptr [rax]
0x180021ff5  mov     r8d, [rax]
0x180021ff8  movzx   ecx, byte ptr [r10+1]
0x180021ffd  mov     rdx, [rdi]
0x180022000  mov     [r8+rdx], cl
0x180022004  mov     ecx, r15d
0x180022007  mov     r8d, [r11]
0x18002200a  sub     cl, r8b
0x18002200d  inc     dword ptr [rax]
0x18002200f  add     r8d, 0FFFFFFF0h
0x180022013  shr     bp, cl
0x180022016  add     r8d, r12d
0x180022019  mov     [r10], bp
0x18002201d  mov     [r11], r8d
0x180022020  jmp     short loc_180022031
0x180022022  add     r8d, r12d
0x180022025  movzx   ebp, si
0x180022028  mov     [r11], r8d
0x18002202b  jmp     short loc_180022031
0x18002202d  movzx   ebp, r9w
0x180022031  mov     esi, dword ptr [rsp+58h+arg_0]
0x180022035  dec     esi
0x180022037  mov     ecx, esi
0x180022039  cmp     esi, 100h
0x18002203f  jb      short loc_18002204A
0x180022041  shr     ecx, 7
0x180022044  add     ecx, 100h
0x18002204a  mov     edx, ecx
0x18002204c  movzx   edx, byte ptr [rdx+r13+38500h]
0x180022055  lea     rcx, ds:0[rdx*4]
0x18002205d  mov     rdx, [rsp+58h+arg_10]
0x180022062  mov     [rsp+58h+arg_0], rcx
0x180022067  movzx   r12d, word ptr [rcx+rdx+2]
0x18002206d  movzx   r9d, word ptr [rcx+rdx]
0x180022072  mov     edx, r15d
0x180022075  sub     edx, r12d
0x180022078  mov     ecx, r8d
0x18002207b  cmp     r8d, edx
0x18002207e  jle     short loc_1800220CA
0x180022080  mov     edx, [rax]
0x180022082  movzx   r8d, r9w
0x180022086  shl     r8w, cl
0x18002208a  add     r12d, 0FFFFFFF0h
0x18002208e  mov     rcx, [rdi]
0x180022091  or      r8w, bp
0x180022095  mov     [r10], r8w
0x180022099  mov     r13, rdi
0x18002209c  mov     [rdx+rcx], r8b
0x1800220a0  inc     dword ptr [rax]
0x1800220a2  mov     rdx, [rdi]
0x1800220a5  mov     r8d, [rax]
0x1800220a8  movzx   ecx, byte ptr [r10+1]
0x1800220ad  mov     [r8+rdx], cl
0x1800220b1  mov     edx, r15d
0x1800220b4  mov     ecx, [r11]
0x1800220b7  add     r12d, ecx
0x1800220ba  inc     dword ptr [rax]
0x1800220bc  sub     dl, cl
0x1800220be  movzx   ecx, dl
0x1800220c1  mov     rdx, rax
0x1800220c4  shr     r9w, cl
0x1800220c8  jmp     short loc_1800220DD
0x1800220ca  add     r12d, r8d
0x1800220cd  shl     r9w, cl
0x1800220d1  or      r9w, bp
0x1800220d5  lea     rdx, [rbx+28h]
0x1800220d9  lea     r13, [rbx+10h]
0x1800220dd  mov     rcx, [rsp+58h+arg_0]
0x1800220e2  lea     r8, cs:180000000h
0x1800220e9  mov     [r10], r9w
0x1800220ed  mov     [r11], r12d
0x1800220f0  mov     ebp, [rcx+r8+38780h]
0x1800220f8  test    ebp, ebp
0x1800220fa  jz      short loc_180022166
0x1800220fc  sub     si, [rcx+r8+38DF0h]
0x180022105  mov     ecx, r12d
0x180022108  movzx   r8d, si
0x18002210c  shl     r8w, cl
0x180022110  mov     ecx, r15d
0x180022113  or      r8w, r9w
0x180022117  sub     ecx, ebp
0x180022119  mov     [r10], r8w
0x18002211d  cmp     r12d, ecx
0x180022120  jle     short loc_18002215F
0x180022122  mov     edx, [rax]
0x180022124  mov     r13, rdi
0x180022127  mov     rcx, [rdi]
0x18002212a  mov     [rdx+rcx], r8b
0x18002212e  inc     dword ptr [rax]
0x180022130  mov     r8d, [rax]
0x180022133  movzx   ecx, byte ptr [r10+1]
0x180022138  mov     rdx, [rdi]
0x18002213b  mov     [r8+rdx], cl
0x18002213f  mov     ecx, r15d
0x180022142  mov     r8d, [r11]
0x180022145  sub     cl, r8b
0x180022148  inc     dword ptr [rax]
0x18002214a  shr     si, cl
0x18002214d  lea     ecx, [rbp-10h]
0x180022150  add     ecx, r8d
0x180022153  mov     [r10], si
0x180022157  mov     [r11], ecx
0x18002215a  mov     rsi, rax
0x18002215d  jmp     short loc_180022175
0x18002215f  lea     eax, [r12+rbp]
0x180022163  mov     [r11], eax
0x180022166  mov     rsi, [rsp+58h+arg_18]
0x18002216b  mov     rdi, r13
0x18002216e  mov     r13, [rsp+58h+var_58]
0x180022172  mov     rax, rdx
0x180022175  mov     r12, [rsp+58h+arg_8]
0x18002217a  cmp     r14d, [rbx+16F4h]
0x180022181  jb      loc_180021E60
0x180022187  mov     rbp, [rsp+58h+var_28]
0x18002218c  jmp     short loc_180022194
0x18002218e  mov     rsi, rax
0x180022191  mov     r13, rdi
0x180022194  movzx   r9d, word ptr [r12+400h]
0x18002219d  mov     eax, r15d
0x1800221a0  movzx   ebx, word ptr [r12+402h]
0x1800221a9  movzx   edx, r9w
0x1800221ad  mov     ecx, [r11]
0x1800221b0  sub     eax, ebx
0x1800221b2  mov     r14, [rsp+58h+var_40]
0x1800221b7  mov     r12, [rsp+58h+var_38]
0x1800221bc  mov     rdi, [rsp+58h+var_30]
0x1800221c1  shl     dx, cl
0x1800221c4  or      dx, [r10]
0x1800221c8  mov     [r10], dx
0x1800221cc  cmp     ecx, eax
0x1800221ce  jle     short loc_180022217
0x1800221d0  mov     rax, [r13+0]
0x1800221d4  movzx   r8d, dx
0x1800221d8  mov     edx, [rsi]
0x1800221da  mov     [rdx+rax], r8b
0x1800221de  inc     dword ptr [rsi]
0x1800221e0  mov     r8d, [rsi]
0x1800221e3  mov     rdx, [r13+0]
0x1800221e7  movzx   eax, byte ptr [r10+1]
0x1800221ec  mov     [r8+rdx], al
0x1800221f0  mov     eax, [r11]
0x1800221f3  sub     r15b, al
0x1800221f6  inc     dword ptr [rsi]
0x1800221f8  movzx   ecx, r15b
0x1800221fc  lea     edx, [rax-10h]
0x1800221ff  add     edx, ebx
0x180022201  shr     r9w, cl
0x180022205  mov     [r10], r9w
0x180022209  mov     [r11], edx
0x18002220c  add     rsp, 38h
0x180022210  pop     r15
0x180022212  pop     r13
0x180022214  pop     rsi
0x180022215  pop     rbx
0x180022216  retn
0x180022217  lea     eax, [rcx+rbx]
0x18002221a  mov     [r11], eax
0x18002221d  add     rsp, 38h
0x180022221  pop     r15
0x180022223  pop     r13
0x180022225  pop     rsi
0x180022226  pop     rbx
0x180022227  retn
```
