# Binary::Policy::PutBooleanUnit<Binary::Policy::SlowSource,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[8],int)

- ea: `0x1800908b0`
- end: `0x180090e23`
- name: `??$PutBooleanUnit@VSlowSource@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY07$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1395`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008f1e0`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x1800908b0`

## pseudocode

```c
__int64 __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::SlowSource,2>(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5)
{
  signed int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r10
  __int64 v10; // r11
  __int64 v11; // r14
  __int64 v12; // r15
  __int64 v13; // r12
  __int64 v14; // r13
  __int64 v15; // rax
  __int64 v16; // r9
  char *v17; // rbx
  char *v18; // rcx
  __int16 *v19; // rdx
  __int64 v20; // rdi
  char *v21; // rsi
  __int16 v22; // ax
  __int16 v23; // dx
  unsigned __int16 v24; // dx
  int v25; // ebx
  _QWORD *v26; // rdi
  int v27; // esi
  __int64 v28; // rdx
  __int64 v29; // r10
  __int64 v30; // rdx
  __int64 v31; // rax
  int v32; // ecx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r14
  __int64 v36; // r15
  __int64 v37; // r12
  __int64 v38; // r13
  __int64 v39; // rcx
  __int64 v40; // rsi
  __int64 v41; // r8
  __int64 v42; // rdi
  char *v43; // r10
  __int64 v44; // r11
  __int16 v45; // dx
  __int16 v46; // cx
  int v47; // eax
  __int64 v48; // rdx
  int v50; // [rsp+20h] [rbp-91h]
  int v51; // [rsp+24h] [rbp-8Dh]
  __int64 v52; // [rsp+28h] [rbp-89h]
  char *v53; // [rsp+30h] [rbp-81h]
  __int16 *v54; // [rsp+38h] [rbp-79h]
  char *v55; // [rsp+40h] [rbp-71h]
  _WORD *v56; // [rsp+48h] [rbp-69h]
  char *v57; // [rsp+50h] [rbp-61h]
  _WORD *v58; // [rsp+58h] [rbp-59h]
  char *v59; // [rsp+60h] [rbp-51h]
  _WORD *v60; // [rsp+68h] [rbp-49h]
  int v62; // [rsp+78h] [rbp-39h]
  __int64 v64; // [rsp+88h] [rbp-29h]
  __int128 v66; // [rsp+A0h] [rbp-11h] BYREF
  __int16 v67; // [rsp+B0h] [rbp-1h] BYREF
  __int16 v68; // [rsp+B2h] [rbp+1h]
  __int16 v69; // [rsp+B4h] [rbp+3h]
  __int16 v70; // [rsp+B6h] [rbp+5h]
  __int16 v71; // [rsp+B8h] [rbp+7h]
  __int16 v72; // [rsp+BAh] [rbp+9h]
  __int16 v73; // [rsp+BCh] [rbp+Bh]
  __int16 v74; // [rsp+BEh] [rbp+Dh]

  v50 = a1;
  v66 = 0;
  Binary::Policy::CompleteOperation::TargetDigitalRegion(a2, &v66);
  if ( a1 > 3 )
  {
    v7 = a1 & 0x80000003;
    v50 = v7;
    if ( v7 < 0 )
    {
      v7 = (((_BYTE)v7 - 1) | 0xFFFFFFFC) + 1;
      v50 = v7;
    }
    if ( v7 < 0 )
      v50 = v7 + 4;
  }
  v8 = a4[3];
  v9 = a4[2] - v8;
  v10 = a4[4] - v8;
  v11 = a4[5] - v8;
  v12 = a4[6] - v8;
  v13 = a4[7] - v8;
  v14 = *a4 - v8;
  v15 = (__int64)a5 << 6;
  v16 = 8;
  v53 = &byte_1800DE484[v15];
  v17 = &byte_1800DE484[v15];
  v60 = (__int16 *)((char *)&word_1800DE486 + v15);
  v59 = &byte_1800DE488[v15];
  v58 = (__int16 *)((char *)&word_1800DE48A + v15);
  v57 = &byte_1800DE48C[v15];
  v56 = (__int16 *)((char *)&word_1800DE48E + v15);
  v18 = &Binary::Policy::SlowSource::OddOperation[v15];
  v19 = (__int16 *)((char *)&word_1800DE482 + v15);
  v55 = &Binary::Policy::SlowSource::OddOperation[v15];
  v54 = (__int16 *)((char *)&word_1800DE482 + v15);
  v20 = a4[1] - v8;
  v21 = (char *)&v67 - v8;
  do
  {
    v22 = *v19;
    v23 = *(_WORD *)(v20 + v8);
    v8 += 2;
    v24 = *(_WORD *)(v8 - 2) * *v60
        + *(_WORD *)v17 * *(_WORD *)(v9 + v8 - 2)
        + *(_WORD *)v59 * *(_WORD *)(v10 + v8 - 2)
        + *v58 * *(_WORD *)(v11 + v8 - 2)
        + *(_WORD *)v57 * *(_WORD *)(v12 + v8 - 2)
        + *v56 * *(_WORD *)(v13 + v8 - 2)
        + *(_WORD *)v18 * *(_WORD *)(v8 + v14 - 2)
        + v22 * v23;
    v18 = v55;
    *(_WORD *)&v21[v8 - 2] = v24 >> 6;
    v19 = v54;
    --v16;
  }
  while ( v16 );
  v25 = v50;
  v26 = a4;
  v27 = 0;
  v28 = (__int64)v50 << 6;
  **((_BYTE **)&v66 + 1) = (unsigned __int16)(v67 * *(_WORD *)&Binary::Policy::SlowSource::OddOperation[v28]
                                            + v68 * *(__int16 *)((char *)&word_1800DE482 + v28)
                                            + v72 * *(__int16 *)((char *)&word_1800DE48A + v28)
                                            + v73 * *(_WORD *)&byte_1800DE48C[v28]
                                            + v69 * *(_WORD *)&byte_1800DE484[v28]
                                            + v70 * *(__int16 *)((char *)&word_1800DE486 + v28)
                                            + v74 * *(__int16 *)((char *)&word_1800DE48E + v28)
                                            + v71 * *(_WORD *)&byte_1800DE488[v28]) >> 8;
  v62 = 1;
  if ( *(int *)(a3 + 12) > 1 )
  {
    v29 = 1;
    v52 = 1;
    do
    {
      v30 = Binary::Policy::SlowSource::GlobalCase[v25];
      v31 = 0;
      v27 += v30;
      v32 = 8 - v30;
      v51 = v27;
      v33 = 8 - (int)v30;
      if ( 8 - (int)v30 > 0 )
      {
        do
        {
          *(&v67 + v31) = *(&v67 + v30 + v31);
          ++v31;
        }
        while ( v31 < v32 );
      }
      if ( v32 < 8LL )
      {
        v34 = v26[3];
        v35 = v26[4] - v34;
        v36 = v26[5] - v34;
        v37 = v26[6] - v34;
        v38 = v26[7] - v34;
        v39 = v27;
        v40 = v26[2] - v34;
        v41 = v34 + 2 * (v39 + v33);
        v64 = *v26 - v34;
        v42 = v26[1] - v34;
        v43 = (char *)&v67 - v34 + -2 * v39;
        v44 = 8 - v33;
        do
        {
          v45 = *(_WORD *)(v42 + v41);
          v46 = *(_WORD *)(v64 + v41);
          v41 += 2;
          *(_WORD *)&v43[v41 - 2] = (unsigned __int16)(*v60 * *(_WORD *)(v41 - 2)
                                                     + *(_WORD *)v53 * *(_WORD *)(v40 + v41 - 2)
                                                     + *(_WORD *)v59 * *(_WORD *)(v35 + v41 - 2)
                                                     + *v58 * *(_WORD *)(v36 + v41 - 2)
                                                     + *(_WORD *)v57 * *(_WORD *)(v37 + v41 - 2)
                                                     + *v56 * *(_WORD *)(v41 + v38 - 2)
                                                     + *(_WORD *)v55 * v46
                                                     + *v54 * v45) >> 6;
          --v44;
        }
        while ( v44 );
        v25 = v50;
        v26 = a4;
        v27 = v51;
        v29 = v52;
      }
      v47 = v25 + 1;
      v25 = 0;
      if ( v47 < 4 )
        v25 = v47;
      v48 = (__int64)v25 << 6;
      v50 = v25;
      *(_BYTE *)(v29 + *((_QWORD *)&v66 + 1)) = (unsigned __int16)(v67
                                                                 * *(_WORD *)&Binary::Policy::SlowSource::OddOperation[v48]
                                                                 + v68 * *(__int16 *)((char *)&word_1800DE482 + v48)
                                                                 + v72 * *(__int16 *)((char *)&word_1800DE48A + v48)
                                                                 + v73 * *(_WORD *)&byte_1800DE48C[v48]
                                                                 + v69 * *(_WORD *)&byte_1800DE484[v48]
                                                                 + v70 * *(__int16 *)((char *)&word_1800DE486 + v48)
                                                                 + v74 * *(__int16 *)((char *)&word_1800DE48E + v48)
                                                                 + v71 * *(_WORD *)&byte_1800DE488[v48]) >> 8;
      ++v29;
      ++v62;
      v52 = v29;
    }
    while ( v62 < *(_DWORD *)(a3 + 12) );
  }
  return Binary::Policy::CompleteOperation::MoveVirtualAddition(a2, &v66);
}

```

## disassembly

```asm
0x1800908b0  mov     [rsp-8+arg_0], rbx
0x1800908b5  push    rbp
0x1800908b6  push    rsi
0x1800908b7  push    rdi
0x1800908b8  push    r12
0x1800908ba  push    r13
0x1800908bc  push    r14
0x1800908be  push    r15
0x1800908c0  lea     rbp, [rsp-1Fh]
0x1800908c5  sub     rsp, 0D0h
0x1800908cc  mov     rax, cs:__security_cookie
0x1800908d3  xor     rax, rsp
0x1800908d6  mov     [rbp+4Fh+var_40], rax
0x1800908da  mov     rax, rdx
0x1800908dd  mov     [rbp+4Fh+var_68], rdx
0x1800908e1  mov     ebx, ecx
0x1800908e3  mov     [rsp+100h+var_E0], ecx
0x1800908e7  xorps   xmm0, xmm0
0x1800908ea  mov     [rbp+4Fh+var_90], r9
0x1800908ee  xor     esi, esi
0x1800908f0  mov     [rbp+4Fh+var_80], r8
0x1800908f4  mov     rcx, rax
0x1800908f7  mov     [rsp+100h+var_DC], esi
0x1800908fb  lea     rdx, [rbp+4Fh+var_60]
0x1800908ff  mov     rdi, r9
0x180090902  movups  [rbp+4Fh+var_60], xmm0
0x180090906  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18009090b  cmp     ebx, 3
0x18009090e  jbe     short loc_180090932
0x180090910  and     ebx, 80000003h
0x180090916  mov     [rsp+100h+var_E0], ebx
0x18009091a  jge     short loc_180090927
0x18009091c  dec     ebx
0x18009091e  or      ebx, 0FFFFFFFCh
0x180090921  inc     ebx
0x180090923  mov     [rsp+100h+var_E0], ebx
0x180090927  test    ebx, ebx
0x180090929  jns     short loc_180090932
0x18009092b  add     ebx, 4
0x18009092e  mov     [rsp+100h+var_E0], ebx
0x180090932  mov     r8, [rdi+18h]
0x180090936  lea     rdx, cs:180000000h
0x18009093d  mov     r10, [rdi+10h]
0x180090941  lea     rcx, rva byte_1800DE484[rdx]
0x180090948  mov     r11, [rdi+20h]
0x18009094c  sub     r10, r8
0x18009094f  mov     r14, [rdi+28h]
0x180090953  sub     r11, r8
0x180090956  mov     r15, [rdi+30h]
0x18009095a  sub     r14, r8
0x18009095d  mov     r12, [rdi+38h]
0x180090961  sub     r15, r8
0x180090964  mov     r13, [rdi]
0x180090967  sub     r12, r8
0x18009096a  movsxd  rax, [rbp+4Fh+arg_20]
0x18009096e  sub     r13, r8
0x180090971  shl     rax, 6
0x180090975  mov     r9d, 8
0x18009097b  add     rcx, rax
0x18009097e  mov     [rsp+100h+var_D0], rcx
0x180090983  lea     rcx, rva word_1800DE486[rdx]
0x18009098a  mov     rbx, [rsp+100h+var_D0]
0x18009098f  add     rcx, rax
0x180090992  mov     [rbp+4Fh+var_98], rcx
0x180090996  lea     rcx, rva byte_1800DE488[rdx]
0x18009099d  add     rcx, rax
0x1800909a0  mov     [rbp+4Fh+var_A0], rcx
0x1800909a4  lea     rcx, rva word_1800DE48A[rdx]
0x1800909ab  add     rcx, rax
0x1800909ae  mov     [rbp+4Fh+var_A8], rcx
0x1800909b2  lea     rcx, rva byte_1800DE48C[rdx]
0x1800909b9  add     rcx, rax
0x1800909bc  mov     [rbp+4Fh+var_B0], rcx
0x1800909c0  lea     rcx, rva word_1800DE48E[rdx]
0x1800909c7  add     rcx, rax
0x1800909ca  mov     [rbp+4Fh+var_B8], rcx
0x1800909ce  lea     rcx, rva ?OddOperation@SlowSource@Policy@Binary@@2V?$OneContext@V?$OneContext@G$07$00$0A@$0BA@@Data@@$03$00$0A@$0BAA@@Data@@B[rdx]; Data::OneContext<Data::OneContext<ushort,8,1,0,16>,4,1,0,256> const Binary::Policy::SlowSource::OddOperation ...
0x1800909d5  add     rcx, rax
0x1800909d8  lea     rdx, rva word_1800DE482[rdx]
0x1800909df  add     rdx, rax
0x1800909e2  mov     [rbp+4Fh+var_C0], rcx
0x1800909e6  mov     rax, [rdi+8]
0x1800909ea  mov     rdi, rax
0x1800909ed  mov     [rbp+4Fh+var_C8], rdx
0x1800909f1  sub     rdi, r8
0x1800909f4  lea     rax, [rbp+4Fh+var_50]
0x1800909f8  sub     rax, r8
0x1800909fb  mov     rsi, rax
0x1800909fe  xchg    ax, ax
0x180090a00  movzx   eax, word ptr [rdx]
0x180090a03  movzx   edx, word ptr [rdi+r8]
0x180090a08  lea     r8, [r8+2]
0x180090a0c  imul    edx, eax
0x180090a0f  movzx   eax, word ptr [rcx]
0x180090a12  movzx   ecx, word ptr [r8+r13-2]
0x180090a18  imul    ecx, eax
0x180090a1b  mov     rax, [rbp+4Fh+var_B8]
0x180090a1f  movzx   eax, word ptr [rax]
0x180090a22  add     dx, cx
0x180090a25  movzx   ecx, word ptr [r12+r8-2]
0x180090a2b  imul    ecx, eax
0x180090a2e  mov     rax, [rbp+4Fh+var_B0]
0x180090a32  movzx   eax, word ptr [rax]
0x180090a35  add     dx, cx
0x180090a38  movzx   ecx, word ptr [r15+r8-2]
0x180090a3e  imul    ecx, eax
0x180090a41  mov     rax, [rbp+4Fh+var_A8]
0x180090a45  movzx   eax, word ptr [rax]
0x180090a48  add     dx, cx
0x180090a4b  movzx   ecx, word ptr [r14+r8-2]
0x180090a51  imul    ecx, eax
0x180090a54  mov     rax, [rbp+4Fh+var_A0]
0x180090a58  movzx   eax, word ptr [rax]
0x180090a5b  add     dx, cx
0x180090a5e  movzx   ecx, word ptr [r11+r8-2]
0x180090a64  imul    ecx, eax
0x180090a67  movzx   eax, word ptr [rbx]
0x180090a6a  add     dx, cx
0x180090a6d  movzx   ecx, word ptr [r10+r8-2]
0x180090a73  imul    ecx, eax
0x180090a76  movzx   eax, word ptr [r8-2]
0x180090a7b  add     dx, cx
0x180090a7e  mov     rcx, [rbp+4Fh+var_98]
0x180090a82  movzx   ecx, word ptr [rcx]
0x180090a85  imul    ecx, eax
0x180090a88  add     dx, cx
0x180090a8b  mov     rcx, [rbp+4Fh+var_C0]
0x180090a8f  shr     dx, 6
0x180090a93  mov     [rsi+r8-2], dx
0x180090a99  mov     rdx, [rbp+4Fh+var_C8]
0x180090a9d  sub     r9, 1
0x180090aa1  jnz     loc_180090A00
0x180090aa7  movzx   eax, [rbp+4Fh+var_48]
0x180090aab  lea     r9, cs:180000000h
0x180090ab2  movsxd  rbx, [rsp+100h+var_E0]
0x180090ab7  mov     rdi, [rbp+4Fh+var_90]
0x180090abb  mov     rdx, rbx
0x180090abe  mov     esi, [rsp+100h+var_DC]
0x180090ac2  shl     rdx, 6
0x180090ac6  movzx   r8d, word ptr [rdx+r9+0DE488h]
0x180090acf  movzx   ecx, word ptr [rdx+r9+0DE48Eh]
0x180090ad8  imul    r8d, eax
0x180090adc  movzx   eax, [rbp+4Fh+var_42]
0x180090ae0  imul    ecx, eax
0x180090ae3  movzx   eax, [rbp+4Fh+var_4A]
0x180090ae7  add     r8w, cx
0x180090aeb  movzx   ecx, word ptr [rdx+r9+0DE486h]
0x180090af4  imul    ecx, eax
0x180090af7  movzx   eax, [rbp+4Fh+var_4C]
0x180090afb  add     r8w, cx
0x180090aff  movzx   ecx, word ptr [rdx+r9+0DE484h]
0x180090b08  imul    ecx, eax
0x180090b0b  movzx   eax, [rbp+4Fh+var_44]
0x180090b0f  add     r8w, cx
0x180090b13  movzx   ecx, word ptr [rdx+r9+0DE48Ch]
0x180090b1c  imul    ecx, eax
0x180090b1f  movzx   eax, [rbp+4Fh+var_46]
0x180090b23  add     r8w, cx
0x180090b27  movzx   ecx, word ptr [rdx+r9+0DE48Ah]
0x180090b30  imul    ecx, eax
0x180090b33  movzx   eax, [rbp+4Fh+var_4E]
0x180090b37  add     r8w, cx
0x180090b3b  movzx   ecx, word ptr [rdx+r9+0DE482h]
0x180090b44  imul    ecx, eax
0x180090b47  movzx   eax, [rbp+4Fh+var_50]
0x180090b4b  add     r8w, cx
0x180090b4f  movzx   ecx, word ptr [rdx+r9+0DE480h]
0x180090b58  imul    ecx, eax
0x180090b5b  mov     rax, qword ptr [rbp+4Fh+var_60+8]
0x180090b5f  add     r8w, cx
0x180090b63  shr     r8w, 8
0x180090b68  mov     [rax], r8b
0x180090b6b  mov     r8d, 1
0x180090b71  mov     rax, [rbp+4Fh+var_80]
0x180090b75  mov     [rbp+4Fh+var_88], r8
0x180090b79  cmp     [rax+0Ch], r8d
0x180090b7d  jle     loc_180090DEF
0x180090b83  mov     r10d, r8d
0x180090b86  mov     [rsp+100h+var_D8], r8
0x180090b8b  nop     dword ptr [rax+rax+00h]
0x180090b90  movsxd  rax, ebx
0x180090b93  mov     ecx, 8
0x180090b98  movsxd  rdx, ds:rva ?GlobalCase@SlowSource@Policy@Binary@@2V?$StripedCategory@H$03@Data@@B[r9+rax*4]; Data::StripedCategory<int,4> const Binary::Policy::SlowSource::GlobalCase ...
0x180090ba0  xor     eax, eax
0x180090ba2  add     esi, edx
0x180090ba4  sub     ecx, edx
0x180090ba6  mov     [rsp+100h+var_DC], esi
0x180090baa  movsxd  r9, ecx
0x180090bad  test    ecx, ecx
0x180090baf  jle     short loc_180090BD6
0x180090bb1  lea     r8, [rdx+rdx]
0x180090bb5  nop     word ptr [rax+rax+00000000h]
0x180090bc0  lea     rcx, [r8+rax*2]
0x180090bc4  movzx   edx, [rbp+rcx+4Fh+var_50]
0x180090bc9  mov     [rbp+rax*2+4Fh+var_50], dx
0x180090bce  inc     rax
0x180090bd1  cmp     rax, r9
0x180090bd4  jl      short loc_180090BC0
0x180090bd6  cmp     r9, 8
0x180090bda  jge     loc_180090D07
0x180090be0  mov     rdx, [rdi+18h]
0x180090be4  lea     r10, [rbp+4Fh+var_50]
0x180090be8  mov     r14, [rdi+20h]
0x180090bec  mov     r11d, 8
0x180090bf2  mov     r15, [rdi+28h]
0x180090bf6  sub     r14, rdx
0x180090bf9  mov     r12, [rdi+30h]
0x180090bfd  sub     r15, rdx
0x180090c00  mov     r13, [rdi+38h]
0x180090c04  sub     r12, rdx
0x180090c07  mov     rbx, [rsp+100h+var_D0]
0x180090c0c  sub     r13, rdx
0x180090c0f  movsxd  rcx, esi
0x180090c12  mov     rsi, [rdi+10h]
0x180090c16  sub     rsi, rdx
0x180090c19  lea     rax, [rcx+r9]
0x180090c1d  lea     r8, [rdx+rax*2]
0x180090c21  mov     rax, [rdi]
0x180090c24  sub     rax, rdx
0x180090c27  mov     [rbp+4Fh+var_78], rax
0x180090c2b  mov     rax, [rdi+8]
0x180090c2f  sub     rax, rdx
0x180090c32  mov     [rbp+4Fh+var_70], rax
0x180090c36  lea     rax, [rcx+rcx]
0x180090c3a  mov     rdi, [rbp+4Fh+var_70]
0x180090c3e  sub     r10, rax
0x180090c41  sub     r10, rdx
0x180090c44  sub     r11, r9
0x180090c47  mov     r9, [rbp+4Fh+var_78]
0x180090c4b  nop     dword ptr [rax+rax+00h]
0x180090c50  mov     rax, [rbp+4Fh+var_C8]
0x180090c54  movzx   edx, word ptr [rdi+r8]
0x180090c59  movzx   ecx, word ptr [r9+r8]
0x180090c5e  lea     r8, [r8+2]
0x180090c62  movzx   eax, word ptr [rax]
0x180090c65  imul    edx, eax
0x180090c68  mov     rax, [rbp+4Fh+var_C0]
0x180090c6c  movzx   eax, word ptr [rax]
0x180090c6f  imul    ecx, eax
0x180090c72  mov     rax, [rbp+4Fh+var_B8]
0x180090c76  movzx   eax, word ptr [rax]
0x180090c79  add     dx, cx
0x180090c7c  movzx   ecx, word ptr [r8+r13-2]
0x180090c82  imul    ecx, eax
0x180090c85  mov     rax, [rbp+4Fh+var_B0]
0x180090c89  movzx   eax, word ptr [rax]
0x180090c8c  add     dx, cx
0x180090c8f  movzx   ecx, word ptr [r12+r8-2]
0x180090c95  imul    ecx, eax
0x180090c98  mov     rax, [rbp+4Fh+var_A8]
0x180090c9c  movzx   eax, word ptr [rax]
0x180090c9f  add     dx, cx
0x180090ca2  movzx   ecx, word ptr [r15+r8-2]
0x180090ca8  imul    ecx, eax
0x180090cab  mov     rax, [rbp+4Fh+var_A0]
0x180090caf  movzx   eax, word ptr [rax]
0x180090cb2  add     dx, cx
0x180090cb5  movzx   ecx, word ptr [r14+r8-2]
0x180090cbb  imul    ecx, eax
0x180090cbe  movzx   eax, word ptr [rbx]
0x180090cc1  add     dx, cx
0x180090cc4  movzx   ecx, word ptr [rsi+r8-2]
0x180090cca  imul    ecx, eax
0x180090ccd  mov     rax, [rbp+4Fh+var_98]
0x180090cd1  movzx   eax, word ptr [rax]
0x180090cd4  add     dx, cx
0x180090cd7  movzx   ecx, word ptr [r8-2]
0x180090cdc  imul    ecx, eax
0x180090cdf  add     dx, cx
0x180090ce2  shr     dx, 6
0x180090ce6  mov     [r10+r8-2], dx
0x180090cec  sub     r11, 1
0x180090cf0  jnz     loc_180090C50
0x180090cf6  mov     ebx, [rsp+100h+var_E0]
0x180090cfa  mov     rdi, [rbp+4Fh+var_90]
0x180090cfe  mov     esi, [rsp+100h+var_DC]
0x180090d02  mov     r10, [rsp+100h+var_D8]
0x180090d07  lea     r9, cs:180000000h
0x180090d0e  lea     eax, [rbx+1]
0x180090d11  xor     ebx, ebx
0x180090d13  cmp     eax, 4
0x180090d16  cmovl   ebx, eax
0x180090d19  movzx   eax, [rbp+4Fh+var_48]
0x180090d1d  movsxd  rdx, ebx
0x180090d20  shl     rdx, 6
0x180090d24  mov     [rsp+100h+var_E0], ebx
0x180090d28  movzx   r8d, word ptr [rdx+r9+0DE488h]
0x180090d31  movzx   ecx, word ptr [rdx+r9+0DE48Eh]
0x180090d3a  imul    r8d, eax
0x180090d3e  movzx   eax, [rbp+4Fh+var_42]
0x180090d42  imul    ecx, eax
0x180090d45  movzx   eax, [rbp+4Fh+var_4A]
0x180090d49  add     r8w, cx
0x180090d4d  movzx   ecx, word ptr [rdx+r9+0DE486h]
0x180090d56  imul    ecx, eax
0x180090d59  movzx   eax, [rbp+4Fh+var_4C]
0x180090d5d  add     r8w, cx
0x180090d61  movzx   ecx, word ptr [rdx+r9+0DE484h]
0x180090d6a  imul    ecx, eax
0x180090d6d  movzx   eax, [rbp+4Fh+var_44]
  ... truncated ...
```
