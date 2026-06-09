# g_MotionCompAndAddErrorRndCtrl(uchar *,Buffer const *,uchar const *,long,long,long)

- ea: `0x1800157f0`
- end: `0x180015d14`
- name: `?g_MotionCompAndAddErrorRndCtrl@@YAXPEAEPEBTBuffer@@PEBEJJJ@Z`
- size: `1316`
- prototype: `void __fastcall(unsigned __int8 *, const union Buffer *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800157f0`

## pseudocode

```c
void __fastcall g_MotionCompAndAddErrorRndCtrl(
        unsigned __int8 *a1,
        const union Buffer *a2,
        const unsigned __int8 *a3,
        int a4,
        int a5,
        int a6)
{
  __int64 v6; // r14
  int v10; // r9d
  unsigned __int8 *v11; // r8
  int v12; // edx
  int v13; // r15d
  int v14; // ebp
  int v15; // edi
  int v16; // edx
  int v17; // edx
  int v18; // r15d
  int v19; // ebp
  int v20; // edi
  int v21; // edx
  unsigned __int8 *v22; // rdi
  int v23; // r8d
  int v24; // edx
  signed int v25; // ebp
  unsigned int v26; // r15d
  int v27; // r8d
  int v28; // r15d
  signed int v29; // r12d
  signed int v30; // edx
  int v31; // edx
  int v32; // r8d
  int v33; // edx
  signed int v34; // ebp
  unsigned int v35; // r15d
  int v36; // r8d
  int v37; // r15d
  signed int v38; // r12d
  signed int v39; // edx
  int v40; // edx
  unsigned __int8 *v41; // rdi
  const unsigned __int8 *v42; // r8
  signed int v43; // r12d
  signed int v44; // edx
  signed int v45; // r15d
  signed int v46; // ebp
  int v47; // edx
  signed int v48; // r12d
  signed int v49; // edx
  signed int v50; // r15d
  signed int v51; // ebp
  int v52; // edx
  int v53; // edx
  int v54; // edx
  int v55; // edx
  int v56; // edx
  int v57; // ecx
  int v58; // eax

  v6 = a4;
  v10 = 8;
  if ( a6 )
  {
    if ( a5 )
    {
      v11 = g_rgiClapTabMC;
      do
      {
        v12 = *((_DWORD *)a2 + 3) + a3[3];
        v13 = *((_DWORD *)a2 + 2) + a3[2];
        v14 = *((_DWORD *)a2 + 1) + a3[1];
        v15 = *(_DWORD *)a2 + *a3;
        if ( ((v15 | v14 | v13 | v12) & 0xFFFFFF00) != 0 )
          v16 = v11[v15] | ((v11[v14] | ((v11[v13] | (v11[v12] << 8)) << 8)) << 8);
        else
          v16 = v15 | ((v14 | ((v13 | (v12 << 8)) << 8)) << 8);
        *(_DWORD *)a1 = v16;
        v17 = *((_DWORD *)a2 + 7) + a3[7];
        v18 = *((_DWORD *)a2 + 6) + a3[6];
        v19 = *((_DWORD *)a2 + 5) + a3[5];
        v20 = *((_DWORD *)a2 + 4) + a3[4];
        if ( ((v20 | v19 | v18 | v17) & 0xFFFFFF00) != 0 )
          v21 = v11[v20] | ((v11[v19] | ((v11[v18] | (v11[v17] << 8)) << 8)) << 8);
        else
          v21 = v20 | ((v19 | ((v18 | (v17 << 8)) << 8)) << 8);
        *((_DWORD *)a1 + 1) = v21;
        a3 += v6;
        a1 += v6;
        a2 = (const union Buffer *)((char *)a2 + 32);
        --v10;
      }
      while ( v10 );
    }
    else
    {
      v22 = g_rgiClapTabMC;
      do
      {
        v23 = a3[1];
        v24 = a3[2];
        v25 = *(_DWORD *)a2 + ((v23 + (unsigned int)*a3) >> 1);
        v26 = v24 + v23;
        v27 = a3[3];
        v28 = *((_DWORD *)a2 + 1) + (v26 >> 1);
        v29 = *((_DWORD *)a2 + 2) + ((unsigned int)(v27 + v24) >> 1);
        v30 = *((_DWORD *)a2 + 3) + ((v27 + (unsigned int)a3[4]) >> 1);
        if ( ((v25 | v28 | v29 | v30) & 0xFFFFFF00) != 0 )
          v31 = v22[v25] | ((v22[v28] | ((v22[v29] | (v22[v30] << 8)) << 8)) << 8);
        else
          v31 = v25 | ((v28 | ((v29 | (v30 << 8)) << 8)) << 8);
        *(_DWORD *)a1 = v31;
        v32 = a3[5];
        v33 = a3[6];
        v34 = *((_DWORD *)a2 + 4) + ((v32 + (unsigned int)a3[4]) >> 1);
        v35 = v33 + v32;
        v36 = a3[7];
        v37 = *((_DWORD *)a2 + 5) + (v35 >> 1);
        v38 = *((_DWORD *)a2 + 6) + ((unsigned int)(v36 + v33) >> 1);
        v39 = *((_DWORD *)a2 + 7) + ((v36 + (unsigned int)a3[8]) >> 1);
        if ( ((v34 | v37 | v38 | v39) & 0xFFFFFF00) != 0 )
          v40 = v22[v34] | ((v22[v37] | ((v22[v38] | (v22[v39] << 8)) << 8)) << 8);
        else
          v40 = v34 | ((v37 | ((v38 | (v39 << 8)) << 8)) << 8);
        *((_DWORD *)a1 + 1) = v40;
        a3 += v6;
        a1 += v6;
        a2 = (const union Buffer *)((char *)a2 + 32);
        --v10;
      }
      while ( v10 );
    }
  }
  else
  {
    v41 = g_rgiClapTabMC;
    if ( a5 )
    {
      do
      {
        v42 = &a3[v6];
        v43 = *((_DWORD *)a2 + 2) + ((a3[2] + (unsigned int)a3[v6 + 2]) >> 1);
        v44 = *((_DWORD *)a2 + 3) + ((a3[3] + (unsigned int)a3[v6 + 3]) >> 1);
        v45 = *((_DWORD *)a2 + 1) + ((a3[1] + (unsigned int)a3[v6 + 1]) >> 1);
        v46 = *(_DWORD *)a2 + ((a3[v6] + (unsigned int)*a3) >> 1);
        if ( ((v46 | v45 | v43 | v44) & 0xFFFFFF00) != 0 )
          v47 = v41[v46] | ((v41[v45] | ((v41[v43] | (v41[v44] << 8)) << 8)) << 8);
        else
          v47 = v46 | ((v45 | ((v43 | (v44 << 8)) << 8)) << 8);
        *(_DWORD *)a1 = v47;
        v48 = *((_DWORD *)a2 + 6) + ((a3[6] + (unsigned int)v42[6]) >> 1);
        v49 = *((_DWORD *)a2 + 7) + ((a3[7] + (unsigned int)v42[7]) >> 1);
        v50 = *((_DWORD *)a2 + 5) + ((a3[5] + (unsigned int)v42[5]) >> 1);
        v51 = *((_DWORD *)a2 + 4) + ((a3[4] + (unsigned int)v42[4]) >> 1);
        if ( ((v51 | v50 | v48 | v49) & 0xFFFFFF00) != 0 )
          v52 = v41[v51] | ((v41[v50] | ((v41[v48] | (v41[v49] << 8)) << 8)) << 8);
        else
          v52 = v51 | ((v50 | ((v48 | (v49 << 8)) << 8)) << 8);
        *((_DWORD *)a1 + 1) = v52;
        a2 = (const union Buffer *)((char *)a2 + 32);
        a1 += v6;
        a3 += v6;
        --v10;
      }
      while ( v10 );
    }
    else
    {
      do
      {
        v53 = a3[v6 + 1] + 1 + a3[1];
        *a1 = v41[*(_DWORD *)a2 + ((a3[v6] + v53 + (unsigned int)*a3) >> 2)];
        a1[1] = v41[*((_DWORD *)a2 + 1) + ((a3[v6 + 2] + v53 + (unsigned int)a3[2]) >> 2)];
        v54 = a3[v6 + 3] + 1 + a3[3];
        a1[2] = v41[*((_DWORD *)a2 + 2) + ((a3[v6 + 2] + v54 + (unsigned int)a3[2]) >> 2)];
        a1[3] = v41[*((_DWORD *)a2 + 3) + ((a3[4] + v54 + (unsigned int)a3[v6 + 4]) >> 2)];
        v55 = a3[v6 + 5] + 1 + a3[5];
        a1[4] = v41[*((_DWORD *)a2 + 4) + ((a3[4] + v55 + (unsigned int)a3[v6 + 4]) >> 2)];
        a1[5] = v41[*((_DWORD *)a2 + 5) + ((a3[6] + v55 + (unsigned int)a3[v6 + 6]) >> 2)];
        v56 = a3[v6 + 7] + 1 + a3[7];
        a1[6] = v41[*((_DWORD *)a2 + 6) + ((a3[6] + v56 + (unsigned int)a3[v6 + 6]) >> 2)];
        v57 = a3[8];
        a2 = (const union Buffer *)((char *)a2 + 32);
        v58 = v56 + a3[v6 + 8];
        a3 += v6;
        a1[7] = v41[*((_DWORD *)a2 - 1) + ((unsigned int)(v57 + v58) >> 2)];
        a1 += v6;
        --v10;
      }
      while ( v10 );
    }
  }
}

```

## disassembly

```asm
0x1800157f0  push    rbx
0x1800157f2  push    rbp
0x1800157f3  push    rdi
0x1800157f4  push    r12
0x1800157f6  push    r14
0x1800157f8  push    r15
0x1800157fa  xor     eax, eax
0x1800157fc  movsxd  r14, r9d
0x1800157ff  mov     r10, r8
0x180015802  mov     r11, rdx
0x180015805  mov     rbx, rcx
0x180015808  lea     r9d, [rax+8]
0x18001580c  cmp     [rsp+30h+arg_28], eax
0x180015810  jz      loc_180015A70
0x180015816  cmp     [rsp+30h+arg_20], eax
0x18001581a  jz      loc_18001592D
0x180015820  mov     r8, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x180015827  movzx   edx, byte ptr [r10+3]
0x18001582c  add     edx, [r11+0Ch]
0x180015830  movzx   r15d, byte ptr [r10+2]
0x180015835  mov     eax, edx
0x180015837  add     r15d, [r11+8]
0x18001583b  movzx   ebp, byte ptr [r10+1]
0x180015840  or      eax, r15d
0x180015843  add     ebp, [r11+4]
0x180015847  movzx   edi, byte ptr [r10]
0x18001584b  or      eax, ebp
0x18001584d  add     edi, [r11]
0x180015850  or      eax, edi
0x180015852  test    eax, 0FFFFFF00h
0x180015857  jnz     short loc_18001586B
0x180015859  shl     edx, 8
0x18001585c  or      edx, r15d
0x18001585f  shl     edx, 8
0x180015862  or      edx, ebp
0x180015864  shl     edx, 8
0x180015867  or      edx, edi
0x180015869  jmp     short loc_18001589A
0x18001586b  movsxd  rax, edx
0x18001586e  movzx   edx, byte ptr [rax+r8]
0x180015873  shl     edx, 8
0x180015876  movsxd  rax, r15d
0x180015879  movzx   ecx, byte ptr [rax+r8]
0x18001587e  or      edx, ecx
0x180015880  movsxd  rax, ebp
0x180015883  shl     edx, 8
0x180015886  movzx   ecx, byte ptr [rax+r8]
0x18001588b  or      edx, ecx
0x18001588d  movsxd  rax, edi
0x180015890  shl     edx, 8
0x180015893  movzx   ecx, byte ptr [rax+r8]
0x180015898  or      edx, ecx
0x18001589a  mov     [rbx], edx
0x18001589c  movzx   edx, byte ptr [r10+7]
0x1800158a1  add     edx, [r11+1Ch]
0x1800158a5  movzx   r15d, byte ptr [r10+6]
0x1800158aa  mov     eax, edx
0x1800158ac  add     r15d, [r11+18h]
0x1800158b0  movzx   ebp, byte ptr [r10+5]
0x1800158b5  or      eax, r15d
0x1800158b8  add     ebp, [r11+14h]
0x1800158bc  movzx   edi, byte ptr [r10+4]
0x1800158c1  or      eax, ebp
0x1800158c3  add     edi, [r11+10h]
0x1800158c7  or      eax, edi
0x1800158c9  test    eax, 0FFFFFF00h
0x1800158ce  jnz     short loc_1800158E2
0x1800158d0  shl     edx, 8
0x1800158d3  or      edx, r15d
0x1800158d6  shl     edx, 8
0x1800158d9  or      edx, ebp
0x1800158db  shl     edx, 8
0x1800158de  or      edx, edi
0x1800158e0  jmp     short loc_180015911
0x1800158e2  movsxd  rax, edx
0x1800158e5  movzx   edx, byte ptr [rax+r8]
0x1800158ea  shl     edx, 8
0x1800158ed  movsxd  rax, r15d
0x1800158f0  movzx   ecx, byte ptr [rax+r8]
0x1800158f5  or      edx, ecx
0x1800158f7  movsxd  rax, ebp
0x1800158fa  shl     edx, 8
0x1800158fd  movzx   ecx, byte ptr [rax+r8]
0x180015902  or      edx, ecx
0x180015904  movsxd  rax, edi
0x180015907  shl     edx, 8
0x18001590a  movzx   ecx, byte ptr [rax+r8]
0x18001590f  or      edx, ecx
0x180015911  mov     [rbx+4], edx
0x180015914  add     r10, r14
0x180015917  add     rbx, r14
0x18001591a  add     r11, 20h ; ' '
0x18001591e  sub     r9d, 1
0x180015922  jnz     loc_180015827
0x180015928  jmp     loc_180015D0A
0x18001592d  mov     rdi, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x180015934  movzx   r8d, byte ptr [r10+1]
0x180015939  movzx   edx, byte ptr [r10+2]
0x18001593e  movzx   ebp, byte ptr [r10]
0x180015942  add     ebp, r8d
0x180015945  shr     ebp, 1
0x180015947  add     ebp, [r11]
0x18001594a  lea     r15d, [rdx+r8]
0x18001594e  movzx   r8d, byte ptr [r10+3]
0x180015953  shr     r15d, 1
0x180015956  add     r15d, [r11+4]
0x18001595a  lea     r12d, [r8+rdx]
0x18001595e  movzx   edx, byte ptr [r10+4]
0x180015963  add     edx, r8d
0x180015966  shr     r12d, 1
0x180015969  add     r12d, [r11+8]
0x18001596d  shr     edx, 1
0x18001596f  add     edx, [r11+0Ch]
0x180015973  mov     eax, edx
0x180015975  or      eax, r12d
0x180015978  or      eax, r15d
0x18001597b  or      eax, ebp
0x18001597d  test    eax, 0FFFFFF00h
0x180015982  jnz     short loc_180015997
0x180015984  shl     edx, 8
0x180015987  or      edx, r12d
0x18001598a  shl     edx, 8
0x18001598d  or      edx, r15d
0x180015990  shl     edx, 8
0x180015993  or      edx, ebp
0x180015995  jmp     short loc_1800159C2
0x180015997  movsxd  rax, edx
0x18001599a  movzx   edx, byte ptr [rax+rdi]
0x18001599e  shl     edx, 8
0x1800159a1  movsxd  rax, r12d
0x1800159a4  movzx   ecx, byte ptr [rax+rdi]
0x1800159a8  or      edx, ecx
0x1800159aa  movsxd  rax, r15d
0x1800159ad  shl     edx, 8
0x1800159b0  movzx   ecx, byte ptr [rax+rdi]
0x1800159b4  or      edx, ecx
0x1800159b6  movsxd  rax, ebp
0x1800159b9  shl     edx, 8
0x1800159bc  movzx   ecx, byte ptr [rax+rdi]
0x1800159c0  or      edx, ecx
0x1800159c2  mov     [rbx], edx
0x1800159c4  movzx   r8d, byte ptr [r10+5]
0x1800159c9  movzx   edx, byte ptr [r10+6]
0x1800159ce  movzx   ebp, byte ptr [r10+4]
0x1800159d3  add     ebp, r8d
0x1800159d6  shr     ebp, 1
0x1800159d8  add     ebp, [r11+10h]
0x1800159dc  lea     r15d, [rdx+r8]
0x1800159e0  movzx   r8d, byte ptr [r10+7]
0x1800159e5  shr     r15d, 1
0x1800159e8  add     r15d, [r11+14h]
0x1800159ec  lea     r12d, [r8+rdx]
0x1800159f0  movzx   edx, byte ptr [r10+8]
0x1800159f5  add     edx, r8d
0x1800159f8  shr     r12d, 1
0x1800159fb  add     r12d, [r11+18h]
0x1800159ff  shr     edx, 1
0x180015a01  add     edx, [r11+1Ch]
0x180015a05  mov     eax, edx
0x180015a07  or      eax, r12d
0x180015a0a  or      eax, r15d
0x180015a0d  or      eax, ebp
0x180015a0f  test    eax, 0FFFFFF00h
0x180015a14  jnz     short loc_180015A29
0x180015a16  shl     edx, 8
0x180015a19  or      edx, r12d
0x180015a1c  shl     edx, 8
0x180015a1f  or      edx, r15d
0x180015a22  shl     edx, 8
0x180015a25  or      edx, ebp
0x180015a27  jmp     short loc_180015A54
0x180015a29  movsxd  rax, edx
0x180015a2c  movzx   edx, byte ptr [rax+rdi]
0x180015a30  shl     edx, 8
0x180015a33  movsxd  rax, r12d
0x180015a36  movzx   ecx, byte ptr [rax+rdi]
0x180015a3a  or      edx, ecx
0x180015a3c  movsxd  rax, r15d
0x180015a3f  shl     edx, 8
0x180015a42  movzx   ecx, byte ptr [rax+rdi]
0x180015a46  or      edx, ecx
0x180015a48  movsxd  rax, ebp
0x180015a4b  shl     edx, 8
0x180015a4e  movzx   ecx, byte ptr [rax+rdi]
0x180015a52  or      edx, ecx
0x180015a54  mov     [rbx+4], edx
0x180015a57  add     r10, r14
0x180015a5a  add     rbx, r14
0x180015a5d  add     r11, 20h ; ' '
0x180015a61  sub     r9d, 1
0x180015a65  jnz     loc_180015934
0x180015a6b  jmp     loc_180015D0A
0x180015a70  mov     rdi, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x180015a77  cmp     [rsp+30h+arg_20], eax
0x180015a7b  jz      loc_180015BD6
0x180015a81  movzx   ebp, byte ptr [r10]
0x180015a85  lea     r8, [r14+r10]
0x180015a89  movzx   eax, byte ptr [r8]
0x180015a8d  movzx   r15d, byte ptr [r8+1]
0x180015a92  add     ebp, eax
0x180015a94  movzx   eax, byte ptr [r10+1]
0x180015a99  movzx   r12d, byte ptr [r8+2]
0x180015a9e  add     r15d, eax
0x180015aa1  movzx   eax, byte ptr [r10+2]
0x180015aa6  movzx   edx, byte ptr [r8+3]
0x180015aab  add     r12d, eax
0x180015aae  movzx   eax, byte ptr [r10+3]
0x180015ab3  add     edx, eax
0x180015ab5  shr     r12d, 1
0x180015ab8  add     r12d, [r11+8]
0x180015abc  shr     edx, 1
0x180015abe  add     edx, [r11+0Ch]
0x180015ac2  shr     r15d, 1
0x180015ac5  mov     eax, edx
0x180015ac7  add     r15d, [r11+4]
0x180015acb  or      eax, r12d
0x180015ace  shr     ebp, 1
0x180015ad0  or      eax, r15d
0x180015ad3  add     ebp, [r11]
0x180015ad6  or      eax, ebp
0x180015ad8  test    eax, 0FFFFFF00h
0x180015add  jnz     short loc_180015AF2
0x180015adf  shl     edx, 8
0x180015ae2  or      edx, r12d
0x180015ae5  shl     edx, 8
0x180015ae8  or      edx, r15d
0x180015aeb  shl     edx, 8
0x180015aee  or      edx, ebp
0x180015af0  jmp     short loc_180015B1D
0x180015af2  movsxd  rax, edx
0x180015af5  movzx   edx, byte ptr [rax+rdi]
0x180015af9  shl     edx, 8
0x180015afc  movsxd  rax, r12d
0x180015aff  movzx   ecx, byte ptr [rax+rdi]
0x180015b03  or      edx, ecx
0x180015b05  movsxd  rax, r15d
0x180015b08  shl     edx, 8
0x180015b0b  movzx   ecx, byte ptr [rax+rdi]
0x180015b0f  or      edx, ecx
0x180015b11  movsxd  rax, ebp
0x180015b14  shl     edx, 8
0x180015b17  movzx   ecx, byte ptr [rax+rdi]
0x180015b1b  or      edx, ecx
0x180015b1d  mov     [rbx], edx
0x180015b1f  movzx   eax, byte ptr [r10+4]
0x180015b24  movzx   ebp, byte ptr [r8+4]
0x180015b29  movzx   r15d, byte ptr [r8+5]
0x180015b2e  add     ebp, eax
0x180015b30  movzx   eax, byte ptr [r10+5]
0x180015b35  movzx   r12d, byte ptr [r8+6]
0x180015b3a  add     r15d, eax
0x180015b3d  movzx   eax, byte ptr [r10+6]
0x180015b42  movzx   edx, byte ptr [r8+7]
0x180015b47  add     r12d, eax
0x180015b4a  movzx   eax, byte ptr [r10+7]
0x180015b4f  add     edx, eax
0x180015b51  shr     r12d, 1
0x180015b54  add     r12d, [r11+18h]
0x180015b58  shr     edx, 1
0x180015b5a  add     edx, [r11+1Ch]
0x180015b5e  shr     r15d, 1
0x180015b61  mov     eax, edx
0x180015b63  add     r15d, [r11+14h]
0x180015b67  or      eax, r12d
0x180015b6a  shr     ebp, 1
0x180015b6c  or      eax, r15d
0x180015b6f  add     ebp, [r11+10h]
0x180015b73  or      eax, ebp
0x180015b75  test    eax, 0FFFFFF00h
0x180015b7a  jnz     short loc_180015B8F
0x180015b7c  shl     edx, 8
0x180015b7f  or      edx, r12d
0x180015b82  shl     edx, 8
0x180015b85  or      edx, r15d
0x180015b88  shl     edx, 8
0x180015b8b  or      edx, ebp
0x180015b8d  jmp     short loc_180015BBA
0x180015b8f  movsxd  rax, edx
0x180015b92  movzx   edx, byte ptr [rax+rdi]
0x180015b96  shl     edx, 8
0x180015b99  movsxd  rax, r12d
0x180015b9c  movzx   ecx, byte ptr [rax+rdi]
0x180015ba0  or      edx, ecx
0x180015ba2  movsxd  rax, r15d
0x180015ba5  shl     edx, 8
0x180015ba8  movzx   ecx, byte ptr [rax+rdi]
0x180015bac  or      edx, ecx
0x180015bae  movsxd  rax, ebp
0x180015bb1  shl     edx, 8
0x180015bb4  movzx   ecx, byte ptr [rax+rdi]
0x180015bb8  or      edx, ecx
0x180015bba  mov     [rbx+4], edx
0x180015bbd  add     r11, 20h ; ' '
0x180015bc1  add     rbx, r14
0x180015bc4  mov     r10, r8
0x180015bc7  sub     r9d, 1
0x180015bcb  jnz     loc_180015A81
0x180015bd1  jmp     loc_180015D0A
0x180015bd6  movzx   eax, byte ptr [r10]
0x180015bda  lea     r8, [r14+r10]
  ... truncated ...
```
