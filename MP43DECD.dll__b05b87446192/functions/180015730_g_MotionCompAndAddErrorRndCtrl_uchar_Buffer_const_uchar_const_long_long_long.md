# g_MotionCompAndAddErrorRndCtrl(uchar *,Buffer const *,uchar const *,long,long,long)

- ea: `0x180015730`
- end: `0x180015c54`
- name: `?g_MotionCompAndAddErrorRndCtrl@@YAXPEAEPEBTBuffer@@PEBEJJJ@Z`
- size: `1316`
- prototype: `void __fastcall(unsigned __int8 *, const union Buffer *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015730`

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
0x180015730  push    rbx
0x180015732  push    rbp
0x180015733  push    rdi
0x180015734  push    r12
0x180015736  push    r14
0x180015738  push    r15
0x18001573a  xor     eax, eax
0x18001573c  movsxd  r14, r9d
0x18001573f  mov     r10, r8
0x180015742  mov     r11, rdx
0x180015745  mov     rbx, rcx
0x180015748  lea     r9d, [rax+8]
0x18001574c  cmp     [rsp+30h+arg_28], eax
0x180015750  jz      loc_1800159B0
0x180015756  cmp     [rsp+30h+arg_20], eax
0x18001575a  jz      loc_18001586D
0x180015760  mov     r8, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x180015767  movzx   edx, byte ptr [r10+3]
0x18001576c  add     edx, [r11+0Ch]
0x180015770  movzx   r15d, byte ptr [r10+2]
0x180015775  mov     eax, edx
0x180015777  add     r15d, [r11+8]
0x18001577b  movzx   ebp, byte ptr [r10+1]
0x180015780  or      eax, r15d
0x180015783  add     ebp, [r11+4]
0x180015787  movzx   edi, byte ptr [r10]
0x18001578b  or      eax, ebp
0x18001578d  add     edi, [r11]
0x180015790  or      eax, edi
0x180015792  test    eax, 0FFFFFF00h
0x180015797  jnz     short loc_1800157AB
0x180015799  shl     edx, 8
0x18001579c  or      edx, r15d
0x18001579f  shl     edx, 8
0x1800157a2  or      edx, ebp
0x1800157a4  shl     edx, 8
0x1800157a7  or      edx, edi
0x1800157a9  jmp     short loc_1800157DA
0x1800157ab  movsxd  rax, edx
0x1800157ae  movzx   edx, byte ptr [rax+r8]
0x1800157b3  shl     edx, 8
0x1800157b6  movsxd  rax, r15d
0x1800157b9  movzx   ecx, byte ptr [rax+r8]
0x1800157be  or      edx, ecx
0x1800157c0  movsxd  rax, ebp
0x1800157c3  shl     edx, 8
0x1800157c6  movzx   ecx, byte ptr [rax+r8]
0x1800157cb  or      edx, ecx
0x1800157cd  movsxd  rax, edi
0x1800157d0  shl     edx, 8
0x1800157d3  movzx   ecx, byte ptr [rax+r8]
0x1800157d8  or      edx, ecx
0x1800157da  mov     [rbx], edx
0x1800157dc  movzx   edx, byte ptr [r10+7]
0x1800157e1  add     edx, [r11+1Ch]
0x1800157e5  movzx   r15d, byte ptr [r10+6]
0x1800157ea  mov     eax, edx
0x1800157ec  add     r15d, [r11+18h]
0x1800157f0  movzx   ebp, byte ptr [r10+5]
0x1800157f5  or      eax, r15d
0x1800157f8  add     ebp, [r11+14h]
0x1800157fc  movzx   edi, byte ptr [r10+4]
0x180015801  or      eax, ebp
0x180015803  add     edi, [r11+10h]
0x180015807  or      eax, edi
0x180015809  test    eax, 0FFFFFF00h
0x18001580e  jnz     short loc_180015822
0x180015810  shl     edx, 8
0x180015813  or      edx, r15d
0x180015816  shl     edx, 8
0x180015819  or      edx, ebp
0x18001581b  shl     edx, 8
0x18001581e  or      edx, edi
0x180015820  jmp     short loc_180015851
0x180015822  movsxd  rax, edx
0x180015825  movzx   edx, byte ptr [rax+r8]
0x18001582a  shl     edx, 8
0x18001582d  movsxd  rax, r15d
0x180015830  movzx   ecx, byte ptr [rax+r8]
0x180015835  or      edx, ecx
0x180015837  movsxd  rax, ebp
0x18001583a  shl     edx, 8
0x18001583d  movzx   ecx, byte ptr [rax+r8]
0x180015842  or      edx, ecx
0x180015844  movsxd  rax, edi
0x180015847  shl     edx, 8
0x18001584a  movzx   ecx, byte ptr [rax+r8]
0x18001584f  or      edx, ecx
0x180015851  mov     [rbx+4], edx
0x180015854  add     r10, r14
0x180015857  add     rbx, r14
0x18001585a  add     r11, 20h ; ' '
0x18001585e  sub     r9d, 1
0x180015862  jnz     loc_180015767
0x180015868  jmp     loc_180015C4A
0x18001586d  mov     rdi, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x180015874  movzx   r8d, byte ptr [r10+1]
0x180015879  movzx   edx, byte ptr [r10+2]
0x18001587e  movzx   ebp, byte ptr [r10]
0x180015882  add     ebp, r8d
0x180015885  shr     ebp, 1
0x180015887  add     ebp, [r11]
0x18001588a  lea     r15d, [rdx+r8]
0x18001588e  movzx   r8d, byte ptr [r10+3]
0x180015893  shr     r15d, 1
0x180015896  add     r15d, [r11+4]
0x18001589a  lea     r12d, [r8+rdx]
0x18001589e  movzx   edx, byte ptr [r10+4]
0x1800158a3  add     edx, r8d
0x1800158a6  shr     r12d, 1
0x1800158a9  add     r12d, [r11+8]
0x1800158ad  shr     edx, 1
0x1800158af  add     edx, [r11+0Ch]
0x1800158b3  mov     eax, edx
0x1800158b5  or      eax, r12d
0x1800158b8  or      eax, r15d
0x1800158bb  or      eax, ebp
0x1800158bd  test    eax, 0FFFFFF00h
0x1800158c2  jnz     short loc_1800158D7
0x1800158c4  shl     edx, 8
0x1800158c7  or      edx, r12d
0x1800158ca  shl     edx, 8
0x1800158cd  or      edx, r15d
0x1800158d0  shl     edx, 8
0x1800158d3  or      edx, ebp
0x1800158d5  jmp     short loc_180015902
0x1800158d7  movsxd  rax, edx
0x1800158da  movzx   edx, byte ptr [rax+rdi]
0x1800158de  shl     edx, 8
0x1800158e1  movsxd  rax, r12d
0x1800158e4  movzx   ecx, byte ptr [rax+rdi]
0x1800158e8  or      edx, ecx
0x1800158ea  movsxd  rax, r15d
0x1800158ed  shl     edx, 8
0x1800158f0  movzx   ecx, byte ptr [rax+rdi]
0x1800158f4  or      edx, ecx
0x1800158f6  movsxd  rax, ebp
0x1800158f9  shl     edx, 8
0x1800158fc  movzx   ecx, byte ptr [rax+rdi]
0x180015900  or      edx, ecx
0x180015902  mov     [rbx], edx
0x180015904  movzx   r8d, byte ptr [r10+5]
0x180015909  movzx   edx, byte ptr [r10+6]
0x18001590e  movzx   ebp, byte ptr [r10+4]
0x180015913  add     ebp, r8d
0x180015916  shr     ebp, 1
0x180015918  add     ebp, [r11+10h]
0x18001591c  lea     r15d, [rdx+r8]
0x180015920  movzx   r8d, byte ptr [r10+7]
0x180015925  shr     r15d, 1
0x180015928  add     r15d, [r11+14h]
0x18001592c  lea     r12d, [r8+rdx]
0x180015930  movzx   edx, byte ptr [r10+8]
0x180015935  add     edx, r8d
0x180015938  shr     r12d, 1
0x18001593b  add     r12d, [r11+18h]
0x18001593f  shr     edx, 1
0x180015941  add     edx, [r11+1Ch]
0x180015945  mov     eax, edx
0x180015947  or      eax, r12d
0x18001594a  or      eax, r15d
0x18001594d  or      eax, ebp
0x18001594f  test    eax, 0FFFFFF00h
0x180015954  jnz     short loc_180015969
0x180015956  shl     edx, 8
0x180015959  or      edx, r12d
0x18001595c  shl     edx, 8
0x18001595f  or      edx, r15d
0x180015962  shl     edx, 8
0x180015965  or      edx, ebp
0x180015967  jmp     short loc_180015994
0x180015969  movsxd  rax, edx
0x18001596c  movzx   edx, byte ptr [rax+rdi]
0x180015970  shl     edx, 8
0x180015973  movsxd  rax, r12d
0x180015976  movzx   ecx, byte ptr [rax+rdi]
0x18001597a  or      edx, ecx
0x18001597c  movsxd  rax, r15d
0x18001597f  shl     edx, 8
0x180015982  movzx   ecx, byte ptr [rax+rdi]
0x180015986  or      edx, ecx
0x180015988  movsxd  rax, ebp
0x18001598b  shl     edx, 8
0x18001598e  movzx   ecx, byte ptr [rax+rdi]
0x180015992  or      edx, ecx
0x180015994  mov     [rbx+4], edx
0x180015997  add     r10, r14
0x18001599a  add     rbx, r14
0x18001599d  add     r11, 20h ; ' '
0x1800159a1  sub     r9d, 1
0x1800159a5  jnz     loc_180015874
0x1800159ab  jmp     loc_180015C4A
0x1800159b0  mov     rdi, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x1800159b7  cmp     [rsp+30h+arg_20], eax
0x1800159bb  jz      loc_180015B16
0x1800159c1  movzx   ebp, byte ptr [r10]
0x1800159c5  lea     r8, [r14+r10]
0x1800159c9  movzx   eax, byte ptr [r8]
0x1800159cd  movzx   r15d, byte ptr [r8+1]
0x1800159d2  add     ebp, eax
0x1800159d4  movzx   eax, byte ptr [r10+1]
0x1800159d9  movzx   r12d, byte ptr [r8+2]
0x1800159de  add     r15d, eax
0x1800159e1  movzx   eax, byte ptr [r10+2]
0x1800159e6  movzx   edx, byte ptr [r8+3]
0x1800159eb  add     r12d, eax
0x1800159ee  movzx   eax, byte ptr [r10+3]
0x1800159f3  add     edx, eax
0x1800159f5  shr     r12d, 1
0x1800159f8  add     r12d, [r11+8]
0x1800159fc  shr     edx, 1
0x1800159fe  add     edx, [r11+0Ch]
0x180015a02  shr     r15d, 1
0x180015a05  mov     eax, edx
0x180015a07  add     r15d, [r11+4]
0x180015a0b  or      eax, r12d
0x180015a0e  shr     ebp, 1
0x180015a10  or      eax, r15d
0x180015a13  add     ebp, [r11]
0x180015a16  or      eax, ebp
0x180015a18  test    eax, 0FFFFFF00h
0x180015a1d  jnz     short loc_180015A32
0x180015a1f  shl     edx, 8
0x180015a22  or      edx, r12d
0x180015a25  shl     edx, 8
0x180015a28  or      edx, r15d
0x180015a2b  shl     edx, 8
0x180015a2e  or      edx, ebp
0x180015a30  jmp     short loc_180015A5D
0x180015a32  movsxd  rax, edx
0x180015a35  movzx   edx, byte ptr [rax+rdi]
0x180015a39  shl     edx, 8
0x180015a3c  movsxd  rax, r12d
0x180015a3f  movzx   ecx, byte ptr [rax+rdi]
0x180015a43  or      edx, ecx
0x180015a45  movsxd  rax, r15d
0x180015a48  shl     edx, 8
0x180015a4b  movzx   ecx, byte ptr [rax+rdi]
0x180015a4f  or      edx, ecx
0x180015a51  movsxd  rax, ebp
0x180015a54  shl     edx, 8
0x180015a57  movzx   ecx, byte ptr [rax+rdi]
0x180015a5b  or      edx, ecx
0x180015a5d  mov     [rbx], edx
0x180015a5f  movzx   eax, byte ptr [r10+4]
0x180015a64  movzx   ebp, byte ptr [r8+4]
0x180015a69  movzx   r15d, byte ptr [r8+5]
0x180015a6e  add     ebp, eax
0x180015a70  movzx   eax, byte ptr [r10+5]
0x180015a75  movzx   r12d, byte ptr [r8+6]
0x180015a7a  add     r15d, eax
0x180015a7d  movzx   eax, byte ptr [r10+6]
0x180015a82  movzx   edx, byte ptr [r8+7]
0x180015a87  add     r12d, eax
0x180015a8a  movzx   eax, byte ptr [r10+7]
0x180015a8f  add     edx, eax
0x180015a91  shr     r12d, 1
0x180015a94  add     r12d, [r11+18h]
0x180015a98  shr     edx, 1
0x180015a9a  add     edx, [r11+1Ch]
0x180015a9e  shr     r15d, 1
0x180015aa1  mov     eax, edx
0x180015aa3  add     r15d, [r11+14h]
0x180015aa7  or      eax, r12d
0x180015aaa  shr     ebp, 1
0x180015aac  or      eax, r15d
0x180015aaf  add     ebp, [r11+10h]
0x180015ab3  or      eax, ebp
0x180015ab5  test    eax, 0FFFFFF00h
0x180015aba  jnz     short loc_180015ACF
0x180015abc  shl     edx, 8
0x180015abf  or      edx, r12d
0x180015ac2  shl     edx, 8
0x180015ac5  or      edx, r15d
0x180015ac8  shl     edx, 8
0x180015acb  or      edx, ebp
0x180015acd  jmp     short loc_180015AFA
0x180015acf  movsxd  rax, edx
0x180015ad2  movzx   edx, byte ptr [rax+rdi]
0x180015ad6  shl     edx, 8
0x180015ad9  movsxd  rax, r12d
0x180015adc  movzx   ecx, byte ptr [rax+rdi]
0x180015ae0  or      edx, ecx
0x180015ae2  movsxd  rax, r15d
0x180015ae5  shl     edx, 8
0x180015ae8  movzx   ecx, byte ptr [rax+rdi]
0x180015aec  or      edx, ecx
0x180015aee  movsxd  rax, ebp
0x180015af1  shl     edx, 8
0x180015af4  movzx   ecx, byte ptr [rax+rdi]
0x180015af8  or      edx, ecx
0x180015afa  mov     [rbx+4], edx
0x180015afd  add     r11, 20h ; ' '
0x180015b01  add     rbx, r14
0x180015b04  mov     r10, r8
0x180015b07  sub     r9d, 1
0x180015b0b  jnz     loc_1800159C1
0x180015b11  jmp     loc_180015C4A
0x180015b16  movzx   eax, byte ptr [r10]
0x180015b1a  lea     r8, [r14+r10]
  ... truncated ...
```
