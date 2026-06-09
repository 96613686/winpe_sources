# Binary::Policy::PutBooleanUnit<Binary::Policy::SmoothArticle,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[8],int)

- ea: `0x180090e30`
- end: `0x1800913a3`
- name: `??$PutBooleanUnit@VSmoothArticle@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY07$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1395`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008f4f0`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x180090e30`

## pseudocode

```c
__int64 __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::SmoothArticle,2>(
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
  if ( a1 > 1 )
  {
    v7 = a1 & 0x80000001;
    v50 = v7;
    if ( v7 < 0 )
    {
      v7 = (((_BYTE)v7 - 1) | 0xFFFFFFFE) + 1;
      v50 = v7;
    }
    if ( v7 < 0 )
      v50 = v7 + 2;
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
  v53 = &byte_1800DE704[v15];
  v17 = &byte_1800DE704[v15];
  v60 = (__int16 *)((char *)&word_1800DE706 + v15);
  v59 = &byte_1800DE708[v15];
  v58 = (__int16 *)((char *)&word_1800DE70A + v15);
  v57 = &byte_1800DE70C[v15];
  v56 = (__int16 *)((char *)&word_1800DE70E + v15);
  v18 = &Binary::Policy::SmoothArticle::OddOperation[v15];
  v19 = (__int16 *)((char *)&word_1800DE702 + v15);
  v55 = &Binary::Policy::SmoothArticle::OddOperation[v15];
  v54 = (__int16 *)((char *)&word_1800DE702 + v15);
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
  **((_BYTE **)&v66 + 1) = (unsigned __int16)(v67 * *(_WORD *)&Binary::Policy::SmoothArticle::OddOperation[v28]
                                            + v68 * *(__int16 *)((char *)&word_1800DE702 + v28)
                                            + v72 * *(__int16 *)((char *)&word_1800DE70A + v28)
                                            + v73 * *(_WORD *)&byte_1800DE70C[v28]
                                            + v69 * *(_WORD *)&byte_1800DE704[v28]
                                            + v70 * *(__int16 *)((char *)&word_1800DE706 + v28)
                                            + v74 * *(__int16 *)((char *)&word_1800DE70E + v28)
                                            + v71 * *(_WORD *)&byte_1800DE708[v28]) >> 8;
  v62 = 1;
  if ( *(int *)(a3 + 12) > 1 )
  {
    v29 = 1;
    v52 = 1;
    do
    {
      v30 = Binary::Policy::SmoothArticle::GlobalCase[v25];
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
      if ( v47 < 2 )
        v25 = v47;
      v48 = (__int64)v25 << 6;
      v50 = v25;
      *(_BYTE *)(v29 + *((_QWORD *)&v66 + 1)) = (unsigned __int16)(v67
                                                                 * *(_WORD *)&Binary::Policy::SmoothArticle::OddOperation[v48]
                                                                 + v68 * *(__int16 *)((char *)&word_1800DE702 + v48)
                                                                 + v72 * *(__int16 *)((char *)&word_1800DE70A + v48)
                                                                 + v73 * *(_WORD *)&byte_1800DE70C[v48]
                                                                 + v69 * *(_WORD *)&byte_1800DE704[v48]
                                                                 + v70 * *(__int16 *)((char *)&word_1800DE706 + v48)
                                                                 + v74 * *(__int16 *)((char *)&word_1800DE70E + v48)
                                                                 + v71 * *(_WORD *)&byte_1800DE708[v48]) >> 8;
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
0x180090e30  mov     [rsp-8+arg_0], rbx
0x180090e35  push    rbp
0x180090e36  push    rsi
0x180090e37  push    rdi
0x180090e38  push    r12
0x180090e3a  push    r13
0x180090e3c  push    r14
0x180090e3e  push    r15
0x180090e40  lea     rbp, [rsp-1Fh]
0x180090e45  sub     rsp, 0D0h
0x180090e4c  mov     rax, cs:__security_cookie
0x180090e53  xor     rax, rsp
0x180090e56  mov     [rbp+4Fh+var_40], rax
0x180090e5a  mov     rax, rdx
0x180090e5d  mov     [rbp+4Fh+var_68], rdx
0x180090e61  mov     ebx, ecx
0x180090e63  mov     [rsp+100h+var_E0], ecx
0x180090e67  xorps   xmm0, xmm0
0x180090e6a  mov     [rbp+4Fh+var_90], r9
0x180090e6e  xor     esi, esi
0x180090e70  mov     [rbp+4Fh+var_80], r8
0x180090e74  mov     rcx, rax
0x180090e77  mov     [rsp+100h+var_DC], esi
0x180090e7b  lea     rdx, [rbp+4Fh+var_60]
0x180090e7f  mov     rdi, r9
0x180090e82  movups  [rbp+4Fh+var_60], xmm0
0x180090e86  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x180090e8b  cmp     ebx, 1
0x180090e8e  jbe     short loc_180090EB2
0x180090e90  and     ebx, 80000001h
0x180090e96  mov     [rsp+100h+var_E0], ebx
0x180090e9a  jge     short loc_180090EA7
0x180090e9c  dec     ebx
0x180090e9e  or      ebx, 0FFFFFFFEh
0x180090ea1  inc     ebx
0x180090ea3  mov     [rsp+100h+var_E0], ebx
0x180090ea7  test    ebx, ebx
0x180090ea9  jns     short loc_180090EB2
0x180090eab  add     ebx, 2
0x180090eae  mov     [rsp+100h+var_E0], ebx
0x180090eb2  mov     r8, [rdi+18h]
0x180090eb6  lea     rdx, cs:180000000h
0x180090ebd  mov     r10, [rdi+10h]
0x180090ec1  lea     rcx, rva byte_1800DE704[rdx]
0x180090ec8  mov     r11, [rdi+20h]
0x180090ecc  sub     r10, r8
0x180090ecf  mov     r14, [rdi+28h]
0x180090ed3  sub     r11, r8
0x180090ed6  mov     r15, [rdi+30h]
0x180090eda  sub     r14, r8
0x180090edd  mov     r12, [rdi+38h]
0x180090ee1  sub     r15, r8
0x180090ee4  mov     r13, [rdi]
0x180090ee7  sub     r12, r8
0x180090eea  movsxd  rax, [rbp+4Fh+arg_20]
0x180090eee  sub     r13, r8
0x180090ef1  shl     rax, 6
0x180090ef5  mov     r9d, 8
0x180090efb  add     rcx, rax
0x180090efe  mov     [rsp+100h+var_D0], rcx
0x180090f03  lea     rcx, rva word_1800DE706[rdx]
0x180090f0a  mov     rbx, [rsp+100h+var_D0]
0x180090f0f  add     rcx, rax
0x180090f12  mov     [rbp+4Fh+var_98], rcx
0x180090f16  lea     rcx, rva byte_1800DE708[rdx]
0x180090f1d  add     rcx, rax
0x180090f20  mov     [rbp+4Fh+var_A0], rcx
0x180090f24  lea     rcx, rva word_1800DE70A[rdx]
0x180090f2b  add     rcx, rax
0x180090f2e  mov     [rbp+4Fh+var_A8], rcx
0x180090f32  lea     rcx, rva byte_1800DE70C[rdx]
0x180090f39  add     rcx, rax
0x180090f3c  mov     [rbp+4Fh+var_B0], rcx
0x180090f40  lea     rcx, rva word_1800DE70E[rdx]
0x180090f47  add     rcx, rax
0x180090f4a  mov     [rbp+4Fh+var_B8], rcx
0x180090f4e  lea     rcx, rva ?OddOperation@SmoothArticle@Policy@Binary@@2V?$OneContext@V?$OneContext@G$07$00$0A@$0BA@@Data@@$01$00$0A@$0IA@@Data@@B[rdx]; Data::OneContext<Data::OneContext<ushort,8,1,0,16>,2,1,0,128> const Binary::Policy::SmoothArticle::OddOperation ...
0x180090f55  add     rcx, rax
0x180090f58  lea     rdx, rva word_1800DE702[rdx]
0x180090f5f  add     rdx, rax
0x180090f62  mov     [rbp+4Fh+var_C0], rcx
0x180090f66  mov     rax, [rdi+8]
0x180090f6a  mov     rdi, rax
0x180090f6d  mov     [rbp+4Fh+var_C8], rdx
0x180090f71  sub     rdi, r8
0x180090f74  lea     rax, [rbp+4Fh+var_50]
0x180090f78  sub     rax, r8
0x180090f7b  mov     rsi, rax
0x180090f7e  xchg    ax, ax
0x180090f80  movzx   eax, word ptr [rdx]
0x180090f83  movzx   edx, word ptr [rdi+r8]
0x180090f88  lea     r8, [r8+2]
0x180090f8c  imul    edx, eax
0x180090f8f  movzx   eax, word ptr [rcx]
0x180090f92  movzx   ecx, word ptr [r8+r13-2]
0x180090f98  imul    ecx, eax
0x180090f9b  mov     rax, [rbp+4Fh+var_B8]
0x180090f9f  movzx   eax, word ptr [rax]
0x180090fa2  add     dx, cx
0x180090fa5  movzx   ecx, word ptr [r12+r8-2]
0x180090fab  imul    ecx, eax
0x180090fae  mov     rax, [rbp+4Fh+var_B0]
0x180090fb2  movzx   eax, word ptr [rax]
0x180090fb5  add     dx, cx
0x180090fb8  movzx   ecx, word ptr [r15+r8-2]
0x180090fbe  imul    ecx, eax
0x180090fc1  mov     rax, [rbp+4Fh+var_A8]
0x180090fc5  movzx   eax, word ptr [rax]
0x180090fc8  add     dx, cx
0x180090fcb  movzx   ecx, word ptr [r14+r8-2]
0x180090fd1  imul    ecx, eax
0x180090fd4  mov     rax, [rbp+4Fh+var_A0]
0x180090fd8  movzx   eax, word ptr [rax]
0x180090fdb  add     dx, cx
0x180090fde  movzx   ecx, word ptr [r11+r8-2]
0x180090fe4  imul    ecx, eax
0x180090fe7  movzx   eax, word ptr [rbx]
0x180090fea  add     dx, cx
0x180090fed  movzx   ecx, word ptr [r10+r8-2]
0x180090ff3  imul    ecx, eax
0x180090ff6  movzx   eax, word ptr [r8-2]
0x180090ffb  add     dx, cx
0x180090ffe  mov     rcx, [rbp+4Fh+var_98]
0x180091002  movzx   ecx, word ptr [rcx]
0x180091005  imul    ecx, eax
0x180091008  add     dx, cx
0x18009100b  mov     rcx, [rbp+4Fh+var_C0]
0x18009100f  shr     dx, 6
0x180091013  mov     [rsi+r8-2], dx
0x180091019  mov     rdx, [rbp+4Fh+var_C8]
0x18009101d  sub     r9, 1
0x180091021  jnz     loc_180090F80
0x180091027  movzx   eax, [rbp+4Fh+var_48]
0x18009102b  lea     r9, cs:180000000h
0x180091032  movsxd  rbx, [rsp+100h+var_E0]
0x180091037  mov     rdi, [rbp+4Fh+var_90]
0x18009103b  mov     rdx, rbx
0x18009103e  mov     esi, [rsp+100h+var_DC]
0x180091042  shl     rdx, 6
0x180091046  movzx   r8d, word ptr [rdx+r9+0DE708h]
0x18009104f  movzx   ecx, word ptr [rdx+r9+0DE70Eh]
0x180091058  imul    r8d, eax
0x18009105c  movzx   eax, [rbp+4Fh+var_42]
0x180091060  imul    ecx, eax
0x180091063  movzx   eax, [rbp+4Fh+var_4A]
0x180091067  add     r8w, cx
0x18009106b  movzx   ecx, word ptr [rdx+r9+0DE706h]
0x180091074  imul    ecx, eax
0x180091077  movzx   eax, [rbp+4Fh+var_4C]
0x18009107b  add     r8w, cx
0x18009107f  movzx   ecx, word ptr [rdx+r9+0DE704h]
0x180091088  imul    ecx, eax
0x18009108b  movzx   eax, [rbp+4Fh+var_44]
0x18009108f  add     r8w, cx
0x180091093  movzx   ecx, word ptr [rdx+r9+0DE70Ch]
0x18009109c  imul    ecx, eax
0x18009109f  movzx   eax, [rbp+4Fh+var_46]
0x1800910a3  add     r8w, cx
0x1800910a7  movzx   ecx, word ptr [rdx+r9+0DE70Ah]
0x1800910b0  imul    ecx, eax
0x1800910b3  movzx   eax, [rbp+4Fh+var_4E]
0x1800910b7  add     r8w, cx
0x1800910bb  movzx   ecx, word ptr [rdx+r9+0DE702h]
0x1800910c4  imul    ecx, eax
0x1800910c7  movzx   eax, [rbp+4Fh+var_50]
0x1800910cb  add     r8w, cx
0x1800910cf  movzx   ecx, word ptr [rdx+r9+0DE700h]
0x1800910d8  imul    ecx, eax
0x1800910db  mov     rax, qword ptr [rbp+4Fh+var_60+8]
0x1800910df  add     r8w, cx
0x1800910e3  shr     r8w, 8
0x1800910e8  mov     [rax], r8b
0x1800910eb  mov     r8d, 1
0x1800910f1  mov     rax, [rbp+4Fh+var_80]
0x1800910f5  mov     [rbp+4Fh+var_88], r8
0x1800910f9  cmp     [rax+0Ch], r8d
0x1800910fd  jle     loc_18009136F
0x180091103  mov     r10d, r8d
0x180091106  mov     [rsp+100h+var_D8], r8
0x18009110b  nop     dword ptr [rax+rax+00h]
0x180091110  movsxd  rax, ebx
0x180091113  mov     ecx, 8
0x180091118  movsxd  rdx, ds:rva ?GlobalCase@SmoothArticle@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B[r9+rax*4]; Data::StripedCategory<int,2> const Binary::Policy::SmoothArticle::GlobalCase ...
0x180091120  xor     eax, eax
0x180091122  add     esi, edx
0x180091124  sub     ecx, edx
0x180091126  mov     [rsp+100h+var_DC], esi
0x18009112a  movsxd  r9, ecx
0x18009112d  test    ecx, ecx
0x18009112f  jle     short loc_180091156
0x180091131  lea     r8, [rdx+rdx]
0x180091135  nop     word ptr [rax+rax+00000000h]
0x180091140  lea     rcx, [r8+rax*2]
0x180091144  movzx   edx, [rbp+rcx+4Fh+var_50]
0x180091149  mov     [rbp+rax*2+4Fh+var_50], dx
0x18009114e  inc     rax
0x180091151  cmp     rax, r9
0x180091154  jl      short loc_180091140
0x180091156  cmp     r9, 8
0x18009115a  jge     loc_180091287
0x180091160  mov     rdx, [rdi+18h]
0x180091164  lea     r10, [rbp+4Fh+var_50]
0x180091168  mov     r14, [rdi+20h]
0x18009116c  mov     r11d, 8
0x180091172  mov     r15, [rdi+28h]
0x180091176  sub     r14, rdx
0x180091179  mov     r12, [rdi+30h]
0x18009117d  sub     r15, rdx
0x180091180  mov     r13, [rdi+38h]
0x180091184  sub     r12, rdx
0x180091187  mov     rbx, [rsp+100h+var_D0]
0x18009118c  sub     r13, rdx
0x18009118f  movsxd  rcx, esi
0x180091192  mov     rsi, [rdi+10h]
0x180091196  sub     rsi, rdx
0x180091199  lea     rax, [rcx+r9]
0x18009119d  lea     r8, [rdx+rax*2]
0x1800911a1  mov     rax, [rdi]
0x1800911a4  sub     rax, rdx
0x1800911a7  mov     [rbp+4Fh+var_78], rax
0x1800911ab  mov     rax, [rdi+8]
0x1800911af  sub     rax, rdx
0x1800911b2  mov     [rbp+4Fh+var_70], rax
0x1800911b6  lea     rax, [rcx+rcx]
0x1800911ba  mov     rdi, [rbp+4Fh+var_70]
0x1800911be  sub     r10, rax
0x1800911c1  sub     r10, rdx
0x1800911c4  sub     r11, r9
0x1800911c7  mov     r9, [rbp+4Fh+var_78]
0x1800911cb  nop     dword ptr [rax+rax+00h]
0x1800911d0  mov     rax, [rbp+4Fh+var_C8]
0x1800911d4  movzx   edx, word ptr [rdi+r8]
0x1800911d9  movzx   ecx, word ptr [r9+r8]
0x1800911de  lea     r8, [r8+2]
0x1800911e2  movzx   eax, word ptr [rax]
0x1800911e5  imul    edx, eax
0x1800911e8  mov     rax, [rbp+4Fh+var_C0]
0x1800911ec  movzx   eax, word ptr [rax]
0x1800911ef  imul    ecx, eax
0x1800911f2  mov     rax, [rbp+4Fh+var_B8]
0x1800911f6  movzx   eax, word ptr [rax]
0x1800911f9  add     dx, cx
0x1800911fc  movzx   ecx, word ptr [r8+r13-2]
0x180091202  imul    ecx, eax
0x180091205  mov     rax, [rbp+4Fh+var_B0]
0x180091209  movzx   eax, word ptr [rax]
0x18009120c  add     dx, cx
0x18009120f  movzx   ecx, word ptr [r12+r8-2]
0x180091215  imul    ecx, eax
0x180091218  mov     rax, [rbp+4Fh+var_A8]
0x18009121c  movzx   eax, word ptr [rax]
0x18009121f  add     dx, cx
0x180091222  movzx   ecx, word ptr [r15+r8-2]
0x180091228  imul    ecx, eax
0x18009122b  mov     rax, [rbp+4Fh+var_A0]
0x18009122f  movzx   eax, word ptr [rax]
0x180091232  add     dx, cx
0x180091235  movzx   ecx, word ptr [r14+r8-2]
0x18009123b  imul    ecx, eax
0x18009123e  movzx   eax, word ptr [rbx]
0x180091241  add     dx, cx
0x180091244  movzx   ecx, word ptr [rsi+r8-2]
0x18009124a  imul    ecx, eax
0x18009124d  mov     rax, [rbp+4Fh+var_98]
0x180091251  movzx   eax, word ptr [rax]
0x180091254  add     dx, cx
0x180091257  movzx   ecx, word ptr [r8-2]
0x18009125c  imul    ecx, eax
0x18009125f  add     dx, cx
0x180091262  shr     dx, 6
0x180091266  mov     [r10+r8-2], dx
0x18009126c  sub     r11, 1
0x180091270  jnz     loc_1800911D0
0x180091276  mov     ebx, [rsp+100h+var_E0]
0x18009127a  mov     rdi, [rbp+4Fh+var_90]
0x18009127e  mov     esi, [rsp+100h+var_DC]
0x180091282  mov     r10, [rsp+100h+var_D8]
0x180091287  lea     r9, cs:180000000h
0x18009128e  lea     eax, [rbx+1]
0x180091291  xor     ebx, ebx
0x180091293  cmp     eax, 2
0x180091296  cmovl   ebx, eax
0x180091299  movzx   eax, [rbp+4Fh+var_48]
0x18009129d  movsxd  rdx, ebx
0x1800912a0  shl     rdx, 6
0x1800912a4  mov     [rsp+100h+var_E0], ebx
0x1800912a8  movzx   r8d, word ptr [rdx+r9+0DE708h]
0x1800912b1  movzx   ecx, word ptr [rdx+r9+0DE70Eh]
0x1800912ba  imul    r8d, eax
0x1800912be  movzx   eax, [rbp+4Fh+var_42]
0x1800912c2  imul    ecx, eax
0x1800912c5  movzx   eax, [rbp+4Fh+var_4A]
0x1800912c9  add     r8w, cx
0x1800912cd  movzx   ecx, word ptr [rdx+r9+0DE706h]
0x1800912d6  imul    ecx, eax
0x1800912d9  movzx   eax, [rbp+4Fh+var_4C]
0x1800912dd  add     r8w, cx
0x1800912e1  movzx   ecx, word ptr [rdx+r9+0DE704h]
0x1800912ea  imul    ecx, eax
0x1800912ed  movzx   eax, [rbp+4Fh+var_44]
  ... truncated ...
```
