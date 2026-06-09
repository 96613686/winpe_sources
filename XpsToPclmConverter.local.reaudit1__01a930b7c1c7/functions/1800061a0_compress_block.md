# compress_block

- ea: `0x1800061a0`
- end: `0x1800065c8`
- name: `compress_block`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005830`

## callees

- `0x1800061a0`

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
      v34 = dword_1800204A0[v25];
      if ( v34 )
      {
        v35 = v17 - word_180020B10[2 * v25];
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
      v62 = 4LL * (unsigned __int8)dist_code[v41];
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
      v51 = *(_DWORD *)((char *)&qword_1800204C0[12] + v62);
      if ( !v51 )
        goto LABEL_24;
      v52 = v40 - *(_WORD *)((char *)qword_180020B90 + v62);
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
0x1800061a0  mov     [rsp+arg_10], r8
0x1800061a5  mov     [rsp+arg_8], rdx
0x1800061aa  push    rbx
0x1800061ab  push    rsi
0x1800061ac  push    r13
0x1800061ae  push    r15
0x1800061b0  sub     rsp, 38h
0x1800061b4  mov     [rsp+58h+var_30], rdi
0x1800061b9  lea     r11, [rcx+1710h]
0x1800061c0  mov     [rsp+58h+var_38], r12
0x1800061c5  lea     r10, [rcx+170Ch]
0x1800061cc  mov     [rsp+58h+var_40], r14
0x1800061d1  lea     rax, [rcx+28h]
0x1800061d5  xor     r14d, r14d
0x1800061d8  lea     rdi, [rcx+10h]
0x1800061dc  mov     r12, rdx
0x1800061df  mov     rbx, rcx
0x1800061e2  mov     r15d, 10h
0x1800061e8  cmp     [rcx+16F4h], r14d
0x1800061ef  jz      loc_18000652E
0x1800061f5  mov     [rsp+58h+var_28], rbp
0x1800061fa  nop     word ptr [rax+rax+00h]
0x180006200  mov     r9, [rbx+16E8h]
0x180006207  mov     r13, rdi
0x18000620a  mov     [rsp+58h+var_58], rdi
0x18000620e  mov     rsi, rax
0x180006211  mov     [rsp+58h+arg_18], rax
0x180006216  movzx   r8d, byte ptr [r14+r9]
0x18000621b  inc     r14d
0x18000621e  movzx   edx, byte ptr [r14+r9]
0x180006223  inc     r14d
0x180006226  shl     edx, 8
0x180006229  add     edx, r8d
0x18000622c  mov     dword ptr [rsp+58h+arg_0], edx
0x180006230  movzx   ebp, byte ptr [r14+r9]
0x180006235  inc     r14d
0x180006238  test    edx, edx
0x18000623a  jnz     loc_1800062C7
0x180006240  mov     ecx, [r11]
0x180006243  mov     eax, r15d
0x180006246  movzx   r9d, word ptr [r12+rbp*4]
0x18000624b  movzx   edi, word ptr [r12+rbp*4+2]
0x180006251  movzx   r8d, r9w
0x180006255  shl     r8w, cl
0x180006259  sub     eax, edi
0x18000625b  or      r8w, [r10]
0x18000625f  cmp     ecx, eax
0x180006261  jle     short loc_1800062AC
0x180006263  mov     ecx, [rbx+28h]
0x180006266  mov     rax, [rbx+10h]
0x18000626a  mov     [r10], r8w
0x18000626e  mov     [rcx+rax], r8b
0x180006272  inc     dword ptr [rbx+28h]
0x180006275  mov     edx, [rbx+28h]
0x180006278  movzx   eax, byte ptr [r10+1]
0x18000627d  mov     rcx, [rbx+10h]
0x180006281  mov     [rdx+rcx], al
0x180006284  mov     ecx, r15d
0x180006287  mov     eax, [r11]
0x18000628a  sub     cl, al
0x18000628c  inc     dword ptr [rbx+28h]
0x18000628f  lea     edx, [rax-10h]
0x180006292  add     edx, edi
0x180006294  lea     rax, [rbx+28h]
0x180006298  shr     r9w, cl
0x18000629c  lea     rdi, [rbx+10h]
0x1800062a0  mov     [r10], r9w
0x1800062a4  mov     [r11], edx
0x1800062a7  jmp     loc_18000651A
0x1800062ac  lea     edx, [rcx+rdi]
0x1800062af  mov     [r10], r8w
0x1800062b3  mov     [r11], edx
0x1800062b6  lea     rax, [rbx+28h]
0x1800062ba  movzx   r9d, r8w
0x1800062be  lea     rdi, [rbx+10h]
0x1800062c2  jmp     loc_18000651A
0x1800062c7  mov     r8d, [r11]
0x1800062ca  lea     rcx, cs:180000000h
0x1800062d1  movzx   r13d, ds:rva _length_code[rcx+rbp]
0x1800062da  lea     ecx, [r13+101h]
0x1800062e1  movzx   r9d, word ptr [r12+rcx*4]
0x1800062e6  movzx   esi, word ptr [r12+rcx*4+2]
0x1800062ec  movzx   edx, r9w
0x1800062f0  mov     ecx, r8d
0x1800062f3  shl     dx, cl
0x1800062f6  mov     ecx, r15d
0x1800062f9  or      dx, [r10]
0x1800062fd  sub     ecx, esi
0x1800062ff  cmp     r8d, ecx
0x180006302  jle     short loc_180006340
0x180006304  mov     rcx, [rdi]
0x180006307  movzx   r8d, dx
0x18000630b  mov     [r10], dx
0x18000630f  mov     edx, [rax]
0x180006311  mov     [rdx+rcx], r8b
0x180006315  inc     dword ptr [rax]
0x180006317  mov     r8d, [rax]
0x18000631a  mov     rdx, [rdi]
0x18000631d  movzx   ecx, byte ptr [r10+1]
0x180006322  mov     [r8+rdx], cl
0x180006326  mov     edx, r15d
0x180006329  mov     ecx, [r11]
0x18000632c  sub     dl, cl
0x18000632e  inc     dword ptr [rax]
0x180006330  lea     r8d, [rcx-10h]
0x180006334  movzx   ecx, dl
0x180006337  add     r8d, esi
0x18000633a  shr     r9w, cl
0x18000633e  jmp     short loc_180006347
0x180006340  add     r8d, esi
0x180006343  movzx   r9d, dx
0x180006347  mov     rcx, r13
0x18000634a  mov     [r10], r9w
0x18000634e  lea     r13, cs:180000000h
0x180006355  mov     [r11], r8d
0x180006358  mov     r12d, ds:rva dword_1800204A0[r13+rcx*4]
0x180006360  test    r12d, r12d
0x180006363  jz      short loc_1800063CD
0x180006365  sub     bp, ds:rva word_180020B10[r13+rcx*4]
0x18000636e  mov     ecx, r8d
0x180006371  movzx   esi, bp
0x180006374  shl     si, cl
0x180006377  mov     ecx, r15d
0x18000637a  or      si, r9w
0x18000637e  sub     ecx, r12d
0x180006381  mov     [r10], si
0x180006385  cmp     r8d, ecx
0x180006388  jle     short loc_1800063C2
0x18000638a  mov     edx, [rax]
0x18000638c  mov     rcx, [rdi]
0x18000638f  mov     [rdx+rcx], sil
0x180006393  inc     dword ptr [rax]
0x180006395  mov     r8d, [rax]
0x180006398  movzx   ecx, byte ptr [r10+1]
0x18000639d  mov     rdx, [rdi]
0x1800063a0  mov     [r8+rdx], cl
0x1800063a4  mov     ecx, r15d
0x1800063a7  mov     r8d, [r11]
0x1800063aa  sub     cl, r8b
0x1800063ad  inc     dword ptr [rax]
0x1800063af  add     r8d, 0FFFFFFF0h
0x1800063b3  shr     bp, cl
0x1800063b6  add     r8d, r12d
0x1800063b9  mov     [r10], bp
0x1800063bd  mov     [r11], r8d
0x1800063c0  jmp     short loc_1800063D1
0x1800063c2  add     r8d, r12d
0x1800063c5  movzx   ebp, si
0x1800063c8  mov     [r11], r8d
0x1800063cb  jmp     short loc_1800063D1
0x1800063cd  movzx   ebp, r9w
0x1800063d1  mov     esi, dword ptr [rsp+58h+arg_0]
0x1800063d5  dec     esi
0x1800063d7  mov     ecx, esi
0x1800063d9  cmp     esi, 100h
0x1800063df  jb      short loc_1800063EA
0x1800063e1  shr     ecx, 7
0x1800063e4  add     ecx, 100h
0x1800063ea  mov     edx, ecx
0x1800063ec  movzx   edx, byte ptr [rdx+r13+202A0h]
0x1800063f5  lea     rcx, ds:0[rdx*4]
0x1800063fd  mov     rdx, [rsp+58h+arg_10]
0x180006402  mov     [rsp+58h+arg_0], rcx
0x180006407  movzx   r12d, word ptr [rcx+rdx+2]
0x18000640d  movzx   r9d, word ptr [rcx+rdx]
0x180006412  mov     edx, r15d
0x180006415  sub     edx, r12d
0x180006418  mov     ecx, r8d
0x18000641b  cmp     r8d, edx
0x18000641e  jle     short loc_18000646A
0x180006420  mov     edx, [rax]
0x180006422  movzx   r8d, r9w
0x180006426  shl     r8w, cl
0x18000642a  add     r12d, 0FFFFFFF0h
0x18000642e  mov     rcx, [rdi]
0x180006431  or      r8w, bp
0x180006435  mov     [r10], r8w
0x180006439  mov     r13, rdi
0x18000643c  mov     [rdx+rcx], r8b
0x180006440  inc     dword ptr [rax]
0x180006442  mov     rdx, [rdi]
0x180006445  mov     r8d, [rax]
0x180006448  movzx   ecx, byte ptr [r10+1]
0x18000644d  mov     [r8+rdx], cl
0x180006451  mov     edx, r15d
0x180006454  mov     ecx, [r11]
0x180006457  add     r12d, ecx
0x18000645a  inc     dword ptr [rax]
0x18000645c  sub     dl, cl
0x18000645e  movzx   ecx, dl
0x180006461  mov     rdx, rax
0x180006464  shr     r9w, cl
0x180006468  jmp     short loc_18000647D
0x18000646a  add     r12d, r8d
0x18000646d  shl     r9w, cl
0x180006471  or      r9w, bp
0x180006475  lea     rdx, [rbx+28h]
0x180006479  lea     r13, [rbx+10h]
0x18000647d  mov     rcx, [rsp+58h+arg_0]
0x180006482  lea     r8, cs:180000000h
0x180006489  mov     [r10], r9w
0x18000648d  mov     [r11], r12d
0x180006490  mov     ebp, [rcx+r8+20520h]
0x180006498  test    ebp, ebp
0x18000649a  jz      short loc_180006506
0x18000649c  sub     si, [rcx+r8+20B90h]
0x1800064a5  mov     ecx, r12d
0x1800064a8  movzx   r8d, si
0x1800064ac  shl     r8w, cl
0x1800064b0  mov     ecx, r15d
0x1800064b3  or      r8w, r9w
0x1800064b7  sub     ecx, ebp
0x1800064b9  mov     [r10], r8w
0x1800064bd  cmp     r12d, ecx
0x1800064c0  jle     short loc_1800064FF
0x1800064c2  mov     edx, [rax]
0x1800064c4  mov     r13, rdi
0x1800064c7  mov     rcx, [rdi]
0x1800064ca  mov     [rdx+rcx], r8b
0x1800064ce  inc     dword ptr [rax]
0x1800064d0  mov     r8d, [rax]
0x1800064d3  movzx   ecx, byte ptr [r10+1]
0x1800064d8  mov     rdx, [rdi]
0x1800064db  mov     [r8+rdx], cl
0x1800064df  mov     ecx, r15d
0x1800064e2  mov     r8d, [r11]
0x1800064e5  sub     cl, r8b
0x1800064e8  inc     dword ptr [rax]
0x1800064ea  shr     si, cl
0x1800064ed  lea     ecx, [rbp-10h]
0x1800064f0  add     ecx, r8d
0x1800064f3  mov     [r10], si
0x1800064f7  mov     [r11], ecx
0x1800064fa  mov     rsi, rax
0x1800064fd  jmp     short loc_180006515
0x1800064ff  lea     eax, [r12+rbp]
0x180006503  mov     [r11], eax
0x180006506  mov     rsi, [rsp+58h+arg_18]
0x18000650b  mov     rdi, r13
0x18000650e  mov     r13, [rsp+58h+var_58]
0x180006512  mov     rax, rdx
0x180006515  mov     r12, [rsp+58h+arg_8]
0x18000651a  cmp     r14d, [rbx+16F4h]
0x180006521  jb      loc_180006200
0x180006527  mov     rbp, [rsp+58h+var_28]
0x18000652c  jmp     short loc_180006534
0x18000652e  mov     rsi, rax
0x180006531  mov     r13, rdi
0x180006534  movzx   r9d, word ptr [r12+400h]
0x18000653d  mov     eax, r15d
0x180006540  movzx   ebx, word ptr [r12+402h]
0x180006549  movzx   edx, r9w
0x18000654d  mov     ecx, [r11]
0x180006550  sub     eax, ebx
0x180006552  mov     r14, [rsp+58h+var_40]
0x180006557  mov     r12, [rsp+58h+var_38]
0x18000655c  mov     rdi, [rsp+58h+var_30]
0x180006561  shl     dx, cl
0x180006564  or      dx, [r10]
0x180006568  mov     [r10], dx
0x18000656c  cmp     ecx, eax
0x18000656e  jle     short loc_1800065B7
0x180006570  mov     rax, [r13+0]
0x180006574  movzx   r8d, dx
0x180006578  mov     edx, [rsi]
0x18000657a  mov     [rdx+rax], r8b
0x18000657e  inc     dword ptr [rsi]
0x180006580  mov     r8d, [rsi]
0x180006583  mov     rdx, [r13+0]
0x180006587  movzx   eax, byte ptr [r10+1]
0x18000658c  mov     [r8+rdx], al
0x180006590  mov     eax, [r11]
0x180006593  sub     r15b, al
0x180006596  inc     dword ptr [rsi]
0x180006598  movzx   ecx, r15b
0x18000659c  lea     edx, [rax-10h]
0x18000659f  add     edx, ebx
0x1800065a1  shr     r9w, cl
0x1800065a5  mov     [r10], r9w
0x1800065a9  mov     [r11], edx
0x1800065ac  add     rsp, 38h
0x1800065b0  pop     r15
0x1800065b2  pop     r13
0x1800065b4  pop     rsi
0x1800065b5  pop     rbx
0x1800065b6  retn
0x1800065b7  lea     eax, [rcx+rbx]
0x1800065ba  mov     [r11], eax
0x1800065bd  add     rsp, 38h
0x1800065c1  pop     r15
0x1800065c3  pop     r13
0x1800065c5  pop     rsi
0x1800065c6  pop     rbx
0x1800065c7  retn
```
