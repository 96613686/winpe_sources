# Binary::Policy::PutBooleanUnit<Binary::Policy::StripedXPS,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[5],int)

- ea: `0x18008a670`
- end: `0x18008aad6`
- name: `??$PutBooleanUnit@VStripedXPS@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY04$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1126`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180088ce0`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x18008a670`

## pseudocode

```c
void __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::StripedXPS,3>(
        int a1,
        _DWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        int a5)
{
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // r10
  __int64 v15; // r11
  __int16 v16; // r12
  __int64 v17; // rsi
  __int64 v18; // r14
  __int16 v19; // r13
  char *v20; // r15
  __int16 v21; // dx
  __int16 v22; // cx
  _QWORD *v23; // rbp
  int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // r10
  __int64 v27; // rdx
  __int64 v28; // rax
  int v29; // ecx
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // rdi
  __int64 v33; // rcx
  __int64 v34; // rsi
  __int16 v35; // r14
  __int64 v36; // rbx
  __int64 v37; // rbp
  __int16 v38; // r15
  __int16 v39; // r12
  __int16 v40; // r13
  __int16 *v41; // r8
  char *v42; // r11
  __int64 v43; // r10
  __int16 v44; // r9
  __int16 v45; // dx
  __int16 v46; // cx
  __int16 v47; // ax
  int v48; // eax
  __int64 v49; // rdx
  int v50; // [rsp+24h] [rbp-C4h]
  int v51; // [rsp+28h] [rbp-C0h]
  __int16 *v52; // [rsp+30h] [rbp-B8h]
  int v54; // [rsp+40h] [rbp-A8h]
  __int64 v55; // [rsp+48h] [rbp-A0h]
  char *v57; // [rsp+58h] [rbp-90h]
  __int16 *v58; // [rsp+60h] [rbp-88h]
  __int16 *v59; // [rsp+68h] [rbp-80h]
  char *v60; // [rsp+70h] [rbp-78h]
  __int64 v62; // [rsp+80h] [rbp-68h] BYREF
  _BYTE *v63; // [rsp+88h] [rbp-60h]
  __int16 v64; // [rsp+90h] [rbp-58h] BYREF
  __int16 v65; // [rsp+92h] [rbp-56h]
  __int16 v66; // [rsp+94h] [rbp-54h]
  __int16 v67; // [rsp+96h] [rbp-52h]
  __int16 v68; // [rsp+98h] [rbp-50h]

  __asm { vpxor   xmm0, xmm0, xmm0 }
  _RDX = &v62;
  __asm { vmovups xmmword ptr [r11-68h], xmm0 }
  Binary::Policy::CompleteOperation::TargetDigitalRegion((__int64)a2, &v62, a3);
  v11 = a4[3];
  v12 = 5;
  if ( a1 )
    a1 = 0;
  v13 = (__int64)a5 << 6;
  v14 = a4[2] - v11;
  v51 = a1;
  v57 = &byte_1800DE684[v13];
  v15 = a4[4] - v11;
  v60 = &Binary::Policy::StripedXPS::OddOperation[v13];
  v16 = *(_WORD *)&byte_1800DE684[v13];
  v17 = *a4 - v11;
  v59 = (__int16 *)((char *)&word_1800DE682 + v13);
  v18 = a4[1] - v11;
  v58 = (__int16 *)((char *)&word_1800DE686 + v13);
  v19 = *(__int16 *)((char *)&word_1800DE686 + v13);
  v52 = (__int16 *)((char *)qword_1800DE688 + v13);
  v20 = (char *)&v64 - v11;
  do
  {
    v21 = *(_WORD *)(v11 + v18);
    v22 = *(_WORD *)(v11 + v17);
    v11 += 2;
    *(_WORD *)&v20[v11 - 2] = (unsigned __int16)(*(_WORD *)(v11 - 2) * v19
                                               + v16 * *(_WORD *)(v11 + v14 - 2)
                                               + *(_WORD *)((char *)qword_1800DE688 + v13) * *(_WORD *)(v11 + v15 - 2)
                                               + *(_WORD *)&Binary::Policy::StripedXPS::OddOperation[v13] * v22
                                               + *(__int16 *)((char *)&word_1800DE682 + v13) * v21) >> 6;
    --v12;
  }
  while ( v12 );
  v23 = a4;
  v24 = 0;
  v25 = (__int64)a1 << 6;
  *v63 = (unsigned __int16)(v64 * *(_WORD *)&Binary::Policy::StripedXPS::OddOperation[v25]
                          + v66 * *(_WORD *)&byte_1800DE684[v25]
                          + v67 * *(__int16 *)((char *)&word_1800DE686 + v25)
                          + v68 * *(_WORD *)((char *)qword_1800DE688 + v25)
                          + v65 * *(__int16 *)((char *)&word_1800DE682 + v25)) >> 8;
  v54 = 1;
  if ( (int)a3[3] > 1 )
  {
    v26 = 1;
    v55 = 1;
    do
    {
      v27 = Binary::Policy::StripedXPS::GlobalCase[a1];
      v28 = 0;
      v24 += v27;
      v29 = 5 - v27;
      v50 = v24;
      v30 = 5 - (int)v27;
      if ( 5 - (int)v27 > 0 )
      {
        do
        {
          *(&v64 + v28) = *(&v64 + v27 + v28);
          ++v28;
        }
        while ( v28 < v29 );
      }
      if ( v29 < 5LL )
      {
        v31 = v23[3];
        v32 = v23[4] - v31;
        v33 = v24;
        v34 = v23[1] - v31;
        v35 = *(_WORD *)v57;
        v36 = v23[2] - v31;
        v37 = *v23 - v31;
        v38 = *v58;
        v39 = *v52;
        v40 = *v59;
        v41 = (__int16 *)(v31 + 2 * (v30 + v33));
        v42 = (char *)&v64 - v31 + -2 * v33;
        v43 = 5 - v30;
        v44 = *(_WORD *)v60;
        do
        {
          v45 = *(__int16 *)((char *)v41 + v34);
          v46 = *(__int16 *)((char *)v41 + v37);
          v47 = *v41++;
          *(__int16 *)((char *)v41 + (_QWORD)v42 - 2) = (unsigned __int16)(v47 * v38
                                                                         + v35 * *(__int16 *)((char *)v41 + v36 - 2)
                                                                         + v39 * *(__int16 *)((char *)v41 + v32 - 2)
                                                                         + v44 * v46
                                                                         + v40 * v45) >> 6;
          --v43;
        }
        while ( v43 );
        v23 = a4;
        v24 = v50;
        a1 = v51;
        v26 = v55;
      }
      v48 = a1 + 1;
      a1 = 0;
      if ( v48 < 1 )
        a1 = v48;
      v49 = (__int64)a1 << 6;
      v51 = a1;
      v63[v26++] = (unsigned __int16)(v64 * *(_WORD *)&Binary::Policy::StripedXPS::OddOperation[v49]
                                    + v66 * *(_WORD *)&byte_1800DE684[v49]
                                    + v67 * *(__int16 *)((char *)&word_1800DE686 + v49)
                                    + v68 * *(_WORD *)((char *)qword_1800DE688 + v49)
                                    + v65 * *(__int16 *)((char *)&word_1800DE682 + v49)) >> 8;
      ++v54;
      v55 = v26;
    }
    while ( v54 < a3[3] );
  }
  Binary::Policy::CompleteOperation::MoveVirtualAddition(a2);
}

```

## disassembly

```asm
0x18008a670  mov     r11, rsp
0x18008a673  mov     [r11+8], rbx
0x18008a677  push    rbp
0x18008a678  push    rsi
0x18008a679  push    rdi
0x18008a67a  push    r12
0x18008a67c  push    r13
0x18008a67e  push    r14
0x18008a680  push    r15
0x18008a682  sub     rsp, 0B0h
0x18008a689  mov     rax, cs:__security_cookie
0x18008a690  xor     rax, rsp
0x18008a693  mov     [rsp+0E8h+var_48], rax
0x18008a69b  mov     rbp, r9
0x18008a69e  mov     [rsp+0E8h+var_B0], r9
0x18008a6a3  mov     r9, rdx
0x18008a6a6  mov     [rsp+0E8h+var_70], rdx
0x18008a6ab  mov     edi, ecx
0x18008a6ad  mov     [rsp+0E8h+var_98], r8
0x18008a6b2  vpxor   xmm0, xmm0, xmm0
0x18008a6b6  xor     esi, esi
0x18008a6b8  lea     rdx, [r11-68h]
0x18008a6bc  mov     rcx, r9
0x18008a6bf  mov     [rsp+0E8h+var_C4], esi
0x18008a6c3  vmovups xmmword ptr [r11-68h], xmm0
0x18008a6c9  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18008a6ce  mov     r8, [rbp+18h]
0x18008a6d2  lea     rdx, cs:180000000h
0x18008a6d9  mov     r10, [rbp+10h]
0x18008a6dd  lea     rcx, rva byte_1800DE684[rdx]
0x18008a6e4  mov     r11, [rbp+20h]
0x18008a6e8  lea     rbx, rva word_1800DE682[rdx]
0x18008a6ef  mov     r14, [rbp+8]
0x18008a6f3  lea     r15, [rsp+0E8h+var_58]
0x18008a6fb  movsxd  rax, [rsp+0E8h+arg_20]
0x18008a703  test    edi, edi
0x18008a705  mov     r9d, 5
0x18008a70b  cmovnz  edi, esi
0x18008a70e  mov     rsi, [rbp+0]
0x18008a712  shl     rax, 6
0x18008a716  sub     r10, r8
0x18008a719  add     rcx, rax
0x18008a71c  mov     [rsp+0E8h+var_C0], edi
0x18008a720  mov     [rsp+0E8h+var_90], rcx
0x18008a725  lea     rdi, rva ?OddOperation@StripedXPS@Policy@Binary@@2V?$OneContext@V?$OneContext@G$04$00$0A@$09@Data@@$00$00$0A@$0EA@@Data@@B[rdx]; Data::OneContext<Data::OneContext<ushort,5,1,0,10>,1,1,0,64> const Binary::Policy::StripedXPS::OddOperation ...
0x18008a72c  add     rdi, rax
0x18008a72f  add     rbx, rax
0x18008a732  sub     r11, r8
0x18008a735  mov     [rsp+0E8h+var_78], rdi
0x18008a73a  movzx   r12d, word ptr [rcx]
0x18008a73e  sub     rsi, r8
0x18008a741  lea     rcx, rva word_1800DE686[rdx]
0x18008a748  mov     [rsp+0E8h+var_80], rbx
0x18008a74d  add     rcx, rax
0x18008a750  sub     r14, r8
0x18008a753  mov     [rsp+0E8h+var_88], rcx
0x18008a758  movzx   r13d, word ptr [rcx]
0x18008a75c  lea     rcx, rva qword_1800DE688[rdx]
0x18008a763  add     rcx, rax
0x18008a766  mov     [rsp+0E8h+var_B8], rcx
0x18008a76b  sub     r15, r8
0x18008a76e  mov     rbp, rcx
0x18008a771  movzx   eax, word ptr [rbx]
0x18008a774  movzx   edx, word ptr [r8+r14]
0x18008a779  movzx   ecx, word ptr [r8+rsi]
0x18008a77e  lea     r8, [r8+2]
0x18008a782  imul    edx, eax
0x18008a785  movzx   eax, word ptr [rdi]
0x18008a788  imul    ecx, eax
0x18008a78b  movzx   eax, word ptr [rbp+0]
0x18008a78f  add     dx, cx
0x18008a792  movzx   ecx, word ptr [r8+r11-2]
0x18008a798  imul    ecx, eax
0x18008a79b  movzx   eax, word ptr [r8-2]
0x18008a7a0  add     dx, cx
0x18008a7a3  movzx   ecx, word ptr [r8+r10-2]
0x18008a7a9  imul    ecx, r12d
0x18008a7ad  add     dx, cx
0x18008a7b0  mov     ecx, r13d
0x18008a7b3  imul    ecx, eax
0x18008a7b6  add     dx, cx
0x18008a7b9  shr     dx, 6
0x18008a7bd  mov     [r8+r15-2], dx
0x18008a7c3  sub     r9, 1
0x18008a7c7  jnz     short loc_18008A771
0x18008a7c9  movzx   eax, [rsp+0E8h+var_56]
0x18008a7d1  lea     r9, cs:180000000h
0x18008a7d8  movsxd  rdi, [rsp+0E8h+var_C0]
0x18008a7dd  mov     rbp, [rsp+0E8h+var_B0]
0x18008a7e2  mov     rdx, rdi
0x18008a7e5  mov     ebx, [rsp+0E8h+var_C4]
0x18008a7e9  shl     rdx, 6
0x18008a7ed  movzx   r8d, word ptr [rdx+r9+0DE682h]
0x18008a7f6  movzx   ecx, word ptr [rdx+r9+0DE688h]
0x18008a7ff  imul    r8d, eax
0x18008a803  movzx   eax, [rsp+0E8h+var_50]
0x18008a80b  imul    ecx, eax
0x18008a80e  movzx   eax, [rsp+0E8h+var_52]
0x18008a816  add     r8w, cx
0x18008a81a  movzx   ecx, word ptr [rdx+r9+0DE686h]
0x18008a823  imul    ecx, eax
0x18008a826  movzx   eax, [rsp+0E8h+var_54]
0x18008a82e  add     r8w, cx
0x18008a832  movzx   ecx, word ptr [rdx+r9+0DE684h]
0x18008a83b  imul    ecx, eax
0x18008a83e  movzx   eax, [rsp+0E8h+var_58]
0x18008a846  add     r8w, cx
0x18008a84a  movzx   ecx, word ptr [rdx+r9+0DE680h]
0x18008a853  imul    ecx, eax
0x18008a856  mov     rax, [rsp+0E8h+var_60]
0x18008a85e  add     r8w, cx
0x18008a862  shr     r8w, 8
0x18008a867  mov     [rax], r8b
0x18008a86a  mov     r8d, 1
0x18008a870  mov     rax, [rsp+0E8h+var_98]
0x18008a875  mov     [rsp+0E8h+var_A8], r8
0x18008a87a  cmp     [rax+0Ch], r8d
0x18008a87e  jle     loc_18008AA99
0x18008a884  mov     r10d, r8d
0x18008a887  mov     [rsp+0E8h+var_A0], r8
0x18008a88c  nop     dword ptr [rax+00h]
0x18008a890  movsxd  rax, edi
0x18008a893  mov     ecx, 5
0x18008a898  movsxd  rdx, ds:rva ?GlobalCase@StripedXPS@Policy@Binary@@2V?$StripedCategory@H$00@Data@@B[r9+rax*4]; Data::StripedCategory<int,1> const Binary::Policy::StripedXPS::GlobalCase ...
0x18008a8a0  xor     eax, eax
0x18008a8a2  add     ebx, edx
0x18008a8a4  sub     ecx, edx
0x18008a8a6  mov     [rsp+0E8h+var_C4], ebx
0x18008a8aa  movsxd  r9, ecx
0x18008a8ad  test    ecx, ecx
0x18008a8af  jle     short loc_18008A8DC
0x18008a8b1  lea     r8, [rdx+rdx]
0x18008a8b5  nop     word ptr [rax+rax+00000000h]
0x18008a8c0  lea     rcx, [r8+rax*2]
0x18008a8c4  movzx   edx, [rsp+rcx+0E8h+var_58]
0x18008a8cc  mov     [rsp+rax*2+0E8h+var_58], dx
0x18008a8d4  inc     rax
0x18008a8d7  cmp     rax, r9
0x18008a8da  jl      short loc_18008A8C0
0x18008a8dc  cmp     r9, 5
0x18008a8e0  jge     loc_18008A9D2
0x18008a8e6  mov     rdx, [rbp+18h]
0x18008a8ea  lea     r11, [rsp+0E8h+var_58]
0x18008a8f2  mov     rax, [rsp+0E8h+var_90]
0x18008a8f7  mov     r10d, 5
0x18008a8fd  mov     rdi, [rbp+20h]
0x18008a901  mov     rsi, [rbp+8]
0x18008a905  sub     rdi, rdx
0x18008a908  movsxd  rcx, ebx
0x18008a90b  sub     rsi, rdx
0x18008a90e  movzx   r14d, word ptr [rax]
0x18008a912  mov     rbx, [rbp+10h]
0x18008a916  mov     rax, [rsp+0E8h+var_88]
0x18008a91b  sub     rbx, rdx
0x18008a91e  mov     rbp, [rbp+0]
0x18008a922  sub     rbp, rdx
0x18008a925  movzx   r15d, word ptr [rax]
0x18008a929  mov     rax, [rsp+0E8h+var_B8]
0x18008a92e  movzx   r12d, word ptr [rax]
0x18008a932  mov     rax, [rsp+0E8h+var_80]
0x18008a937  movzx   r13d, word ptr [rax]
0x18008a93b  mov     rax, [rsp+0E8h+var_78]
0x18008a940  movzx   eax, word ptr [rax]
0x18008a943  mov     [rsp+0E8h+var_C8], ax
0x18008a948  lea     rax, [r9+rcx]
0x18008a94c  lea     r8, [rdx+rax*2]
0x18008a950  lea     rax, [rcx+rcx]
0x18008a954  sub     r11, rax
0x18008a957  sub     r11, rdx
0x18008a95a  sub     r10, r9
0x18008a95d  movzx   r9d, [rsp+0E8h+var_C8]
0x18008a963  nop     dword ptr [rax+00h]
0x18008a967  nop     word ptr [rax+rax+00000000h]
0x18008a970  movzx   edx, word ptr [r8+rsi]
0x18008a975  movzx   ecx, word ptr [r8+rbp]
0x18008a97a  movzx   eax, word ptr [r8]
0x18008a97e  lea     r8, [r8+2]
0x18008a982  imul    ecx, r9d
0x18008a986  imul    edx, r13d
0x18008a98a  add     dx, cx
0x18008a98d  movzx   ecx, word ptr [r8+rdi-2]
0x18008a993  imul    ecx, r12d
0x18008a997  add     dx, cx
0x18008a99a  movzx   ecx, word ptr [r8+rbx-2]
0x18008a9a0  imul    ecx, r14d
0x18008a9a4  add     dx, cx
0x18008a9a7  mov     ecx, r15d
0x18008a9aa  imul    ecx, eax
0x18008a9ad  add     dx, cx
0x18008a9b0  shr     dx, 6
0x18008a9b4  mov     [r11+r8-2], dx
0x18008a9ba  sub     r10, 1
0x18008a9be  jnz     short loc_18008A970
0x18008a9c0  mov     rbp, [rsp+0E8h+var_B0]
0x18008a9c5  mov     ebx, [rsp+0E8h+var_C4]
0x18008a9c9  mov     edi, [rsp+0E8h+var_C0]
0x18008a9cd  mov     r10, [rsp+0E8h+var_A0]
0x18008a9d2  lea     eax, [rdi+1]
0x18008a9d5  xor     edi, edi
0x18008a9d7  cmp     eax, 1
0x18008a9da  lea     r9, cs:180000000h
0x18008a9e1  cmovl   edi, eax
0x18008a9e4  movzx   eax, [rsp+0E8h+var_56]
0x18008a9ec  movsxd  rdx, edi
0x18008a9ef  shl     rdx, 6
0x18008a9f3  mov     [rsp+0E8h+var_C0], edi
0x18008a9f7  movzx   r8d, word ptr [rdx+r9+0DE682h]
0x18008aa00  movzx   ecx, word ptr [rdx+r9+0DE688h]
0x18008aa09  imul    r8d, eax
0x18008aa0d  movzx   eax, [rsp+0E8h+var_50]
0x18008aa15  imul    ecx, eax
0x18008aa18  movzx   eax, [rsp+0E8h+var_52]
0x18008aa20  add     r8w, cx
0x18008aa24  movzx   ecx, word ptr [rdx+r9+0DE686h]
0x18008aa2d  imul    ecx, eax
0x18008aa30  movzx   eax, [rsp+0E8h+var_54]
0x18008aa38  add     r8w, cx
0x18008aa3c  movzx   ecx, word ptr [rdx+r9+0DE684h]
0x18008aa45  imul    ecx, eax
0x18008aa48  movzx   eax, [rsp+0E8h+var_58]
0x18008aa50  add     r8w, cx
0x18008aa54  movzx   ecx, word ptr [rdx+r9+0DE680h]
0x18008aa5d  imul    ecx, eax
0x18008aa60  mov     rax, [rsp+0E8h+var_60]
0x18008aa68  add     r8w, cx
0x18008aa6c  shr     r8w, 8
0x18008aa71  mov     [r10+rax], r8b
0x18008aa75  inc     r10
0x18008aa78  mov     r8, [rsp+0E8h+var_A8]
0x18008aa7d  mov     rax, [rsp+0E8h+var_98]
0x18008aa82  inc     r8d
0x18008aa85  mov     [rsp+0E8h+var_A8], r8
0x18008aa8a  mov     [rsp+0E8h+var_A0], r10
0x18008aa8f  cmp     r8d, [rax+0Ch]
0x18008aa93  jl      loc_18008A890
0x18008aa99  mov     rcx, [rsp+0E8h+var_70]
0x18008aa9e  lea     rdx, [rsp+0E8h+var_68]
0x18008aaa6  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x18008aaab  mov     rcx, [rsp+0E8h+var_48]
0x18008aab3  xor     rcx, rsp; StackCookie
0x18008aab6  call    __security_check_cookie
0x18008aabb  mov     rbx, [rsp+0E8h+arg_0]
0x18008aac3  add     rsp, 0B0h
0x18008aaca  pop     r15
0x18008aacc  pop     r14
0x18008aace  pop     r13
0x18008aad0  pop     r12
0x18008aad2  pop     rdi
0x18008aad3  pop     rsi
0x18008aad4  pop     rbp
0x18008aad5  retn
```
