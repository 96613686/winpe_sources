# Binary::Policy::PutBooleanUnit<Binary::Policy::UniqueFact,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[7],int)

- ea: `0x180091820`
- end: `0x180091d89`
- name: `??$PutBooleanUnit@VUniqueFact@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY06$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1385`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008fa80`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x180091820`

## pseudocode

```c
void __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::UniqueFact,2>(
        int a1,
        _DWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        int a5)
{
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r10
  __int64 v10; // r11
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rbp
  char *v14; // rdi
  __int64 v15; // r14
  __int64 v16; // r12
  _WORD *v17; // rbx
  char *v18; // r15
  _WORD *v19; // rcx
  _WORD *v20; // rax
  char *v21; // r13
  __int16 v22; // dx
  __int16 v23; // dx
  unsigned __int16 v24; // dx
  int v25; // edi
  int v26; // r9d
  _QWORD *v27; // r15
  int v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // r10
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r11
  __int64 v37; // rdi
  __int16 v38; // r12
  __int64 v39; // rsi
  __int64 v40; // rbp
  __int64 v41; // rcx
  __int64 v42; // r14
  __int16 v43; // r13
  __int64 v44; // rbx
  __int64 v45; // rax
  char *v46; // r10
  __int64 v47; // r9
  __int16 v48; // r8
  __int16 v49; // dx
  int v50; // eax
  __int64 v51; // rdx
  int v52; // [rsp+20h] [rbp-C8h]
  int v53; // [rsp+24h] [rbp-C4h]
  int v54; // [rsp+28h] [rbp-C0h]
  char *v55; // [rsp+30h] [rbp-B8h]
  __int16 *v56; // [rsp+38h] [rbp-B0h]
  char *v57; // [rsp+40h] [rbp-A8h]
  _WORD *v58; // [rsp+48h] [rbp-A0h]
  _WORD *v59; // [rsp+50h] [rbp-98h]
  _WORD *v60; // [rsp+58h] [rbp-90h]
  _WORD *v61; // [rsp+60h] [rbp-88h]
  __int64 v63; // [rsp+70h] [rbp-78h]
  __int128 v66; // [rsp+88h] [rbp-60h] BYREF
  __int16 v67; // [rsp+98h] [rbp-50h] BYREF
  __int16 v68; // [rsp+9Ah] [rbp-4Eh]
  __int16 v69; // [rsp+9Ch] [rbp-4Ch]
  __int16 v70; // [rsp+9Eh] [rbp-4Ah]
  __int16 v71; // [rsp+A0h] [rbp-48h]
  __int16 v72; // [rsp+A2h] [rbp-46h]
  __int16 v73; // [rsp+A4h] [rbp-44h]

  v66 = 0;
  Binary::Policy::CompleteOperation::TargetDigitalRegion((__int64)a2, &v66, a3);
  v7 = a4[3];
  v8 = 7;
  if ( a1 )
    a1 = 0;
  v9 = a4[2] - v7;
  v10 = a4[4] - v7;
  v11 = (__int64)a5 << 6;
  v12 = a4[5] - v7;
  v53 = a1;
  v55 = &byte_1800DE7C4[v11];
  v13 = a4[6] - v7;
  v14 = &byte_1800DE7C4[v11];
  v15 = a4[1] - v7;
  v56 = (__int16 *)((char *)&word_1800DE7C6 + v11);
  v16 = *a4 - v7;
  v17 = (__int16 *)((char *)&word_1800DE7C6 + v11);
  v57 = &byte_1800DE7C8[v11];
  v18 = &byte_1800DE7C8[v11];
  v61 = (__int16 *)((char *)&word_1800DE7CA + v11);
  v60 = (_WORD *)((char *)&dword_1800DE7CC + v11);
  v19 = (__int16 *)((char *)&word_1800DE7C2 + v11);
  v20 = (_WORD *)(0x180000000LL + v11 + 911296);
  v59 = v19;
  v58 = v20;
  v21 = (char *)&v67 - v7;
  do
  {
    v22 = *(_WORD *)(v16 + v7);
    v7 += 2;
    v23 = *v20 * v22;
    v20 = v58;
    v24 = *v17 * *(_WORD *)(v7 - 2)
        + *(_WORD *)v14 * *(_WORD *)(v9 + v7 - 2)
        + *(_WORD *)v18 * *(_WORD *)(v10 + v7 - 2)
        + *v61 * *(_WORD *)(v12 + v7 - 2)
        + *v60 * *(_WORD *)(v7 + v13 - 2)
        + *v19 * *(_WORD *)(v15 + v7 - 2)
        + v23;
    v19 = v59;
    *(_WORD *)&v21[v7 - 2] = v24 >> 6;
    --v8;
  }
  while ( v8 );
  v25 = v53;
  v26 = 1;
  v27 = a4;
  v28 = 0;
  v29 = (__int64)v53 << 6;
  v54 = 1;
  **((_BYTE **)&v66 + 1) = (unsigned __int16)(v71 * *(_WORD *)&byte_1800DE7C8[v29]
                                            + v72 * *(__int16 *)((char *)&word_1800DE7CA + v29)
                                            + v68 * *(__int16 *)((char *)&word_1800DE7C2 + v29)
                                            + v69 * *(_WORD *)&byte_1800DE7C4[v29]
                                            + v73 * *(_WORD *)((char *)&dword_1800DE7CC + v29)
                                            + v70 * *(__int16 *)((char *)&word_1800DE7C6 + v29)
                                            + v67 * *(_WORD *)&Binary::Policy::UniqueFact::OddOperation[v29]) >> 8;
  if ( (int)a3[3] > 1 )
  {
    v30 = 1;
    v63 = 1;
    do
    {
      v31 = 0;
      v32 = Binary::Policy::UniqueFact::GlobalCase[v25];
      v33 = 7 - v32;
      v28 += v32;
      v52 = v28;
      v34 = 7 - (int)v32;
      if ( 7 - (int)v32 > 0 )
      {
        do
        {
          *(&v67 + v31) = *(&v67 + v32 + v31);
          ++v31;
        }
        while ( v31 < v33 );
        v26 = v54;
      }
      if ( v33 < 7LL )
      {
        v35 = v27[3];
        v36 = v27[2] - v35;
        v37 = v27[5] - v35;
        v38 = *(_WORD *)v55;
        v39 = v27[6] - v35;
        v40 = *v27 - v35;
        v41 = v28;
        v42 = v27[1] - v35;
        v43 = *v56;
        v44 = v27[4] - v35;
        v45 = v35 + 2 * (v33 + v41);
        v46 = (char *)&v67 - v35 + -2 * v41;
        v47 = 7 - v34;
        do
        {
          v48 = *(_WORD *)(v45 + v40);
          v49 = *(_WORD *)(v42 + v45);
          v45 += 2;
          *(_WORD *)&v46[v45 - 2] = (unsigned __int16)(v43 * *(_WORD *)(v45 - 2)
                                                     + v38 * *(_WORD *)(v36 + v45 - 2)
                                                     + *(_WORD *)v57 * *(_WORD *)(v44 + v45 - 2)
                                                     + *v61 * *(_WORD *)(v37 + v45 - 2)
                                                     + *v60 * *(_WORD *)(v39 + v45 - 2)
                                                     + *v59 * v49
                                                     + *v58 * v48) >> 6;
          --v47;
        }
        while ( v47 );
        v27 = a4;
        v28 = v52;
        v25 = v53;
        v26 = v54;
        v30 = v63;
      }
      v50 = v25 + 1;
      v25 = 0;
      if ( v50 < 1 )
        v25 = v50;
      ++v26;
      v51 = (__int64)v25 << 6;
      v53 = v25;
      v54 = v26;
      *(_BYTE *)(v30 + *((_QWORD *)&v66 + 1)) = (unsigned __int16)(v71 * *(_WORD *)&byte_1800DE7C8[v51]
                                                                 + v72 * *(__int16 *)((char *)&word_1800DE7CA + v51)
                                                                 + v68 * *(__int16 *)((char *)&word_1800DE7C2 + v51)
                                                                 + v69 * *(_WORD *)&byte_1800DE7C4[v51]
                                                                 + v73 * *(_WORD *)((char *)&dword_1800DE7CC + v51)
                                                                 + v70 * *(__int16 *)((char *)&word_1800DE7C6 + v51)
                                                                 + v67
                                                                 * *(_WORD *)&Binary::Policy::UniqueFact::OddOperation[v51]) >> 8;
      v63 = ++v30;
    }
    while ( v26 < a3[3] );
  }
  Binary::Policy::CompleteOperation::MoveVirtualAddition(a2);
}

```

## disassembly

```asm
0x180091820  mov     r11, rsp
0x180091823  mov     [r11+8], rbx
0x180091827  push    rbp
0x180091828  push    rsi
0x180091829  push    rdi
0x18009182a  push    r12
0x18009182c  push    r13
0x18009182e  push    r14
0x180091830  push    r15
0x180091832  sub     rsp, 0B0h
0x180091839  mov     rax, cs:__security_cookie
0x180091840  xor     rax, rsp
0x180091843  mov     [rsp+0E8h+var_40], rax
0x18009184b  mov     r15, r9
0x18009184e  mov     [rsp+0E8h+var_80], r9
0x180091853  mov     r9, rdx
0x180091856  mov     [rsp+0E8h+var_68], rdx
0x18009185e  mov     edi, ecx
0x180091860  mov     [rsp+0E8h+var_70], r8
0x180091865  xorps   xmm0, xmm0
0x180091868  lea     rdx, [r11-60h]
0x18009186c  xor     esi, esi
0x18009186e  mov     rcx, r9
0x180091871  mov     [rsp+0E8h+var_C8], esi
0x180091875  movups  xmmword ptr [r11-60h], xmm0
0x18009187a  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18009187f  mov     r8, [r15+18h]
0x180091883  lea     rdx, cs:180000000h
0x18009188a  mov     r10, [r15+10h]
0x18009188e  lea     rcx, rva byte_1800DE7C4[rdx]
0x180091895  mov     r11, [r15+20h]
0x180091899  lea     r13, [rsp+0E8h+var_50]
0x1800918a1  mov     rbp, [r15+30h]
0x1800918a5  test    edi, edi
0x1800918a7  mov     r14, [r15+8]
0x1800918ab  mov     r9d, 7
0x1800918b1  mov     r12, [r15]
0x1800918b4  cmovnz  edi, esi
0x1800918b7  mov     rsi, [r15+28h]
0x1800918bb  sub     r10, r8
0x1800918be  movsxd  rax, [rsp+0E8h+arg_20]
0x1800918c6  sub     r11, r8
0x1800918c9  shl     rax, 6
0x1800918cd  sub     rsi, r8
0x1800918d0  add     rcx, rax
0x1800918d3  mov     [rsp+0E8h+var_C4], edi
0x1800918d7  mov     [rsp+0E8h+var_B8], rcx
0x1800918dc  sub     rbp, r8
0x1800918df  mov     rdi, [rsp+0E8h+var_B8]
0x1800918e4  lea     rcx, rva word_1800DE7C6[rdx]
0x1800918eb  add     rcx, rax
0x1800918ee  sub     r14, r8
0x1800918f1  mov     [rsp+0E8h+var_B0], rcx
0x1800918f6  sub     r12, r8
0x1800918f9  mov     rbx, [rsp+0E8h+var_B0]
0x1800918fe  lea     rcx, rva byte_1800DE7C8[rdx]
0x180091905  add     rcx, rax
0x180091908  mov     [rsp+0E8h+var_A8], rcx
0x18009190d  lea     rcx, rva word_1800DE7CA[rdx]
0x180091914  mov     r15, [rsp+0E8h+var_A8]
0x180091919  add     rcx, rax
0x18009191c  mov     [rsp+0E8h+var_88], rcx
0x180091921  lea     rcx, rva dword_1800DE7CC[rdx]
0x180091928  add     rcx, rax
0x18009192b  mov     [rsp+0E8h+var_90], rcx
0x180091930  lea     rcx, rva word_1800DE7C2[rdx]
0x180091937  add     rcx, rax
0x18009193a  lea     rax, [rax+0DE7C0h]
0x180091941  add     rax, rdx
0x180091944  mov     [rsp+0E8h+var_98], rcx
0x180091949  mov     [rsp+0E8h+var_A0], rax
0x18009194e  sub     r13, r8
0x180091951  movzx   eax, word ptr [rax]
0x180091954  movzx   edx, word ptr [r12+r8]
0x180091959  lea     r8, [r8+2]
0x18009195d  imul    edx, eax
0x180091960  movzx   eax, word ptr [rcx]
0x180091963  movzx   ecx, word ptr [r14+r8-2]
0x180091969  imul    ecx, eax
0x18009196c  mov     rax, [rsp+0E8h+var_90]
0x180091971  movzx   eax, word ptr [rax]
0x180091974  add     dx, cx
0x180091977  movzx   ecx, word ptr [r8+rbp-2]
0x18009197d  imul    ecx, eax
0x180091980  mov     rax, [rsp+0E8h+var_88]
0x180091985  movzx   eax, word ptr [rax]
0x180091988  add     dx, cx
0x18009198b  movzx   ecx, word ptr [rsi+r8-2]
0x180091991  imul    ecx, eax
0x180091994  movzx   eax, word ptr [r15]
0x180091998  add     dx, cx
0x18009199b  movzx   ecx, word ptr [r11+r8-2]
0x1800919a1  imul    ecx, eax
0x1800919a4  movzx   eax, word ptr [rdi]
0x1800919a7  add     dx, cx
0x1800919aa  movzx   ecx, word ptr [r10+r8-2]
0x1800919b0  imul    ecx, eax
0x1800919b3  movzx   eax, word ptr [rbx]
0x1800919b6  add     dx, cx
0x1800919b9  movzx   ecx, word ptr [r8-2]
0x1800919be  imul    ecx, eax
0x1800919c1  mov     rax, [rsp+0E8h+var_A0]
0x1800919c6  add     dx, cx
0x1800919c9  mov     rcx, [rsp+0E8h+var_98]
0x1800919ce  shr     dx, 6
0x1800919d2  mov     [r8+r13-2], dx
0x1800919d8  sub     r9, 1
0x1800919dc  jnz     loc_180091951
0x1800919e2  movzx   eax, [rsp+0E8h+var_50]
0x1800919ea  lea     r11, cs:180000000h
0x1800919f1  movsxd  rdi, [rsp+0E8h+var_C4]
0x1800919f6  mov     r9d, 1
0x1800919fc  mov     r15, [rsp+0E8h+var_80]
0x180091a01  mov     rdx, rdi
0x180091a04  mov     ebx, [rsp+0E8h+var_C8]
0x180091a08  shl     rdx, 6
0x180091a0c  mov     [rsp+0E8h+var_C0], r9
0x180091a11  movzx   r8d, word ptr [rdx+r11+0DE7C0h]
0x180091a1a  movzx   ecx, word ptr [rdx+r11+0DE7C6h]
0x180091a23  imul    r8d, eax
0x180091a27  movzx   eax, [rsp+0E8h+var_4A]
0x180091a2f  imul    ecx, eax
0x180091a32  movzx   eax, [rsp+0E8h+var_44]
0x180091a3a  add     r8w, cx
0x180091a3e  movzx   ecx, word ptr [rdx+r11+0DE7CCh]
0x180091a47  imul    ecx, eax
0x180091a4a  movzx   eax, [rsp+0E8h+var_4C]
0x180091a52  add     r8w, cx
0x180091a56  movzx   ecx, word ptr [rdx+r11+0DE7C4h]
0x180091a5f  imul    ecx, eax
0x180091a62  movzx   eax, [rsp+0E8h+var_4E]
0x180091a6a  add     r8w, cx
0x180091a6e  movzx   ecx, word ptr [rdx+r11+0DE7C2h]
0x180091a77  imul    ecx, eax
0x180091a7a  movzx   eax, [rsp+0E8h+var_46]
0x180091a82  add     r8w, cx
0x180091a86  movzx   ecx, word ptr [rdx+r11+0DE7CAh]
0x180091a8f  imul    ecx, eax
0x180091a92  movzx   eax, [rsp+0E8h+var_48]
0x180091a9a  add     r8w, cx
0x180091a9e  movzx   ecx, word ptr [rdx+r11+0DE7C8h]
0x180091aa7  imul    ecx, eax
0x180091aaa  mov     rax, [rsp+0E8h+var_58]
0x180091ab2  add     r8w, cx
0x180091ab6  shr     r8w, 8
0x180091abb  mov     [rax], r8b
0x180091abe  mov     rax, [rsp+0E8h+var_70]
0x180091ac3  cmp     [rax+0Ch], r9d
0x180091ac7  jle     loc_180091D49
0x180091acd  mov     r10d, r9d
0x180091ad0  mov     [rsp+0E8h+var_78], r9
0x180091ad5  nop     word ptr [rax+rax+00000000h]
0x180091ae0  movsxd  rax, edi
0x180091ae3  xor     edx, edx
0x180091ae5  movsxd  rcx, ds:rva ?GlobalCase@UniqueFact@Policy@Binary@@2V?$StripedCategory@H$00@Data@@B[r11+rax*4]; Data::StripedCategory<int,1> const Binary::Policy::UniqueFact::GlobalCase ...
0x180091aed  mov     eax, 7
0x180091af2  sub     eax, ecx
0x180091af4  add     ebx, ecx
0x180091af6  mov     [rsp+0E8h+var_C8], ebx
0x180091afa  movsxd  r8, eax
0x180091afd  test    eax, eax
0x180091aff  jle     short loc_180091B31
0x180091b01  lea     r9, [rcx+rcx]
0x180091b05  nop     word ptr [rax+rax+00000000h]
0x180091b10  lea     rax, [r9+rdx*2]
0x180091b14  movzx   ecx, [rsp+rax+0E8h+var_50]
0x180091b1c  mov     [rsp+rdx*2+0E8h+var_50], cx
0x180091b24  inc     rdx
0x180091b27  cmp     rdx, r8
0x180091b2a  jl      short loc_180091B10
0x180091b2c  mov     r9, [rsp+0E8h+var_C0]
0x180091b31  cmp     r8, 7
0x180091b35  jge     loc_180091C5E
0x180091b3b  mov     rdx, [r15+18h]
0x180091b3f  lea     r10, [rsp+0E8h+var_50]
0x180091b47  mov     rax, [rsp+0E8h+var_B8]
0x180091b4c  mov     r9d, 7
0x180091b52  mov     r11, [r15+10h]
0x180091b56  mov     rdi, [r15+28h]
0x180091b5a  sub     r11, rdx
0x180091b5d  mov     rsi, [r15+30h]
0x180091b61  sub     rdi, rdx
0x180091b64  movzx   r12d, word ptr [rax]
0x180091b68  sub     rsi, rdx
0x180091b6b  mov     rax, [rsp+0E8h+var_B0]
0x180091b70  mov     rbp, [r15]
0x180091b73  mov     r14, [r15+8]
0x180091b77  sub     rbp, rdx
0x180091b7a  movsxd  rcx, ebx
0x180091b7d  sub     r14, rdx
0x180091b80  movzx   r13d, word ptr [rax]
0x180091b84  mov     rbx, [r15+20h]
0x180091b88  mov     r15, [rsp+0E8h+var_A8]
0x180091b8d  sub     rbx, rdx
0x180091b90  lea     rax, [r8+rcx]
0x180091b94  add     rcx, rcx
0x180091b97  sub     r10, rcx
0x180091b9a  lea     rax, [rdx+rax*2]
0x180091b9e  sub     r10, rdx
0x180091ba1  sub     r9, r8
0x180091ba4  nop     dword ptr [rax+00h]
0x180091ba8  nop     dword ptr [rax+rax+00000000h]
0x180091bb0  mov     rcx, [rsp+0E8h+var_A0]
0x180091bb5  movzx   r8d, word ptr [rax+rbp]
0x180091bba  movzx   edx, word ptr [r14+rax]
0x180091bbf  lea     rax, [rax+2]
0x180091bc3  movzx   ecx, word ptr [rcx]
0x180091bc6  imul    r8d, ecx
0x180091bca  mov     rcx, [rsp+0E8h+var_98]
0x180091bcf  movzx   ecx, word ptr [rcx]
0x180091bd2  imul    edx, ecx
0x180091bd5  mov     rcx, [rsp+0E8h+var_90]
0x180091bda  movzx   ecx, word ptr [rcx]
0x180091bdd  add     r8w, dx
0x180091be1  movzx   edx, word ptr [rsi+rax-2]
0x180091be6  imul    edx, ecx
0x180091be9  mov     rcx, [rsp+0E8h+var_88]
0x180091bee  movzx   ecx, word ptr [rcx]
0x180091bf1  add     r8w, dx
0x180091bf5  movzx   edx, word ptr [rdi+rax-2]
0x180091bfa  imul    edx, ecx
0x180091bfd  movzx   ecx, word ptr [r15]
0x180091c01  add     r8w, dx
0x180091c05  movzx   edx, word ptr [rbx+rax-2]
0x180091c0a  imul    edx, ecx
0x180091c0d  add     r8w, dx
0x180091c11  movzx   edx, word ptr [r11+rax-2]
0x180091c17  imul    edx, r12d
0x180091c1b  add     r8w, dx
0x180091c1f  movzx   edx, word ptr [rax-2]
0x180091c23  imul    edx, r13d
0x180091c27  add     r8w, dx
0x180091c2b  shr     r8w, 6
0x180091c30  mov     [r10+rax-2], r8w
0x180091c36  sub     r9, 1
0x180091c3a  jnz     loc_180091BB0
0x180091c40  mov     r15, [rsp+0E8h+var_80]
0x180091c45  lea     r11, cs:180000000h
0x180091c4c  mov     ebx, [rsp+0E8h+var_C8]
0x180091c50  mov     edi, [rsp+0E8h+var_C4]
0x180091c54  mov     r9, [rsp+0E8h+var_C0]
0x180091c59  mov     r10, [rsp+0E8h+var_78]
0x180091c5e  lea     eax, [rdi+1]
0x180091c61  xor     edi, edi
0x180091c63  cmp     eax, 1
0x180091c66  cmovl   edi, eax
0x180091c69  movzx   eax, [rsp+0E8h+var_50]
0x180091c71  movsxd  rdx, edi
0x180091c74  inc     r9d
0x180091c77  shl     rdx, 6
0x180091c7b  mov     [rsp+0E8h+var_C4], edi
0x180091c7f  mov     [rsp+0E8h+var_C0], r9
0x180091c84  movzx   r8d, word ptr [rdx+r11+0DE7C0h]
0x180091c8d  movzx   ecx, word ptr [rdx+r11+0DE7C6h]
0x180091c96  imul    r8d, eax
0x180091c9a  movzx   eax, [rsp+0E8h+var_4A]
0x180091ca2  imul    ecx, eax
0x180091ca5  movzx   eax, [rsp+0E8h+var_44]
0x180091cad  add     r8w, cx
0x180091cb1  movzx   ecx, word ptr [rdx+r11+0DE7CCh]
0x180091cba  imul    ecx, eax
0x180091cbd  movzx   eax, [rsp+0E8h+var_4C]
0x180091cc5  add     r8w, cx
0x180091cc9  movzx   ecx, word ptr [rdx+r11+0DE7C4h]
0x180091cd2  imul    ecx, eax
0x180091cd5  movzx   eax, [rsp+0E8h+var_4E]
0x180091cdd  add     r8w, cx
0x180091ce1  movzx   ecx, word ptr [rdx+r11+0DE7C2h]
0x180091cea  imul    ecx, eax
0x180091ced  movzx   eax, [rsp+0E8h+var_46]
0x180091cf5  add     r8w, cx
0x180091cf9  movzx   ecx, word ptr [rdx+r11+0DE7CAh]
0x180091d02  imul    ecx, eax
0x180091d05  movzx   eax, [rsp+0E8h+var_48]
0x180091d0d  add     r8w, cx
0x180091d11  movzx   ecx, word ptr [rdx+r11+0DE7C8h]
0x180091d1a  imul    ecx, eax
0x180091d1d  mov     rax, [rsp+0E8h+var_58]
0x180091d25  add     r8w, cx
0x180091d29  shr     r8w, 8
0x180091d2e  mov     [r10+rax], r8b
0x180091d32  inc     r10
0x180091d35  mov     rax, [rsp+0E8h+var_70]
0x180091d3a  mov     [rsp+0E8h+var_78], r10
0x180091d3f  cmp     r9d, [rax+0Ch]
0x180091d43  jl      loc_180091AE0
0x180091d49  mov     rcx, [rsp+0E8h+var_68]
0x180091d51  lea     rdx, [rsp+0E8h+var_60]
0x180091d59  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x180091d5e  mov     rcx, [rsp+0E8h+var_40]
0x180091d66  xor     rcx, rsp; StackCookie
0x180091d69  call    __security_check_cookie
0x180091d6e  mov     rbx, [rsp+0E8h+arg_0]
0x180091d76  add     rsp, 0B0h
0x180091d7d  pop     r15
0x180091d7f  pop     r14
0x180091d81  pop     r13
0x180091d83  pop     r12
0x180091d85  pop     rdi
0x180091d86  pop     rsi
  ... truncated ...
```
