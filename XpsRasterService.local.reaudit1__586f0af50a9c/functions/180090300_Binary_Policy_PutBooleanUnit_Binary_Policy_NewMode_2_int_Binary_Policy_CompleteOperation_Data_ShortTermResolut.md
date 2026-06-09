# Binary::Policy::PutBooleanUnit<Binary::Policy::NewMode,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[7],int)

- ea: `0x180090300`
- end: `0x18009089b`
- name: `??$PutBooleanUnit@VNewMode@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY06$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1435`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008eef0`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x180090300`

## pseudocode

```c
void __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::NewMode,2>(
        unsigned int a1,
        _DWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        int a5)
{
  signed int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r10
  __int64 v10; // r11
  __int64 v11; // rsi
  __int64 v12; // rbp
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // r15
  __int64 v16; // r9
  char *v17; // rdi
  _WORD *v18; // r13
  char *v19; // rbx
  _WORD *v20; // rcx
  _WORD *v21; // rax
  char *v22; // r12
  __int16 v23; // dx
  __int16 v24; // dx
  unsigned __int16 v25; // dx
  int v26; // ebx
  _QWORD *v27; // r13
  int v28; // edi
  __int64 v29; // rdx
  __int64 v30; // r10
  __int64 v31; // rdx
  __int64 v32; // rax
  int v33; // ecx
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rsi
  __int64 v37; // rbp
  __int64 v38; // r14
  __int64 v39; // r15
  __int64 v40; // r12
  __int64 v41; // rcx
  __int64 v42; // rdi
  __int64 v43; // r8
  char *v44; // r11
  __int64 v45; // r10
  __int16 v46; // r9
  __int16 v47; // dx
  __int16 v48; // cx
  int v49; // eax
  __int64 v50; // rdx
  int v51; // [rsp+20h] [rbp-D8h]
  int v52; // [rsp+28h] [rbp-D0h]
  char *v53; // [rsp+30h] [rbp-C8h]
  char *v54; // [rsp+38h] [rbp-C0h]
  _WORD *v55; // [rsp+40h] [rbp-B8h]
  _WORD *v56; // [rsp+48h] [rbp-B0h]
  _WORD *v57; // [rsp+50h] [rbp-A8h]
  _WORD *v58; // [rsp+58h] [rbp-A0h]
  _WORD *v59; // [rsp+60h] [rbp-98h]
  int v61; // [rsp+70h] [rbp-88h]
  __int64 v62; // [rsp+78h] [rbp-80h]
  __int128 v65; // [rsp+90h] [rbp-68h] BYREF
  __int16 v66; // [rsp+A0h] [rbp-58h] BYREF
  __int16 v67; // [rsp+A2h] [rbp-56h]
  __int16 v68; // [rsp+A4h] [rbp-54h]
  __int16 v69; // [rsp+A6h] [rbp-52h]
  __int16 v70; // [rsp+A8h] [rbp-50h]
  __int16 v71; // [rsp+AAh] [rbp-4Eh]
  __int16 v72; // [rsp+ACh] [rbp-4Ch]

  v51 = a1;
  v65 = 0;
  Binary::Policy::CompleteOperation::TargetDigitalRegion((__int64)a2, &v65, a3);
  if ( a1 > 1 )
  {
    v7 = a1 & 0x80000001;
    v51 = v7;
    if ( v7 < 0 )
    {
      v7 = (((_BYTE)v7 - 1) | 0xFFFFFFFE) + 1;
      v51 = v7;
    }
    if ( v7 < 0 )
      v51 = v7 + 2;
  }
  v8 = a4[3];
  v9 = a4[2] - v8;
  v10 = a4[4] - v8;
  v11 = a4[5] - v8;
  v12 = a4[6] - v8;
  v13 = a4[1] - v8;
  v14 = (__int64)a5 << 6;
  v15 = *a4 - v8;
  v16 = 7;
  v53 = &byte_1800DE844[v14];
  v17 = &byte_1800DE844[v14];
  v55 = (__int16 *)((char *)&word_1800DE846 + v14);
  v18 = (__int16 *)((char *)&word_1800DE846 + v14);
  v54 = &byte_1800DE848[v14];
  v19 = &byte_1800DE848[v14];
  v59 = (__int16 *)((char *)&word_1800DE84A + v14);
  v58 = (_WORD *)((char *)&dword_1800DE84C + v14);
  v20 = (__int16 *)((char *)&word_1800DE842 + v14);
  v21 = (_WORD *)(0x180000000LL + v14 + 911424);
  v57 = v20;
  v56 = v21;
  v22 = (char *)&v66 - v8;
  do
  {
    v23 = *(_WORD *)(v15 + v8);
    v8 += 2;
    v24 = *v21 * v23;
    v21 = v56;
    v25 = *v18 * *(_WORD *)(v8 - 2)
        + *(_WORD *)v17 * *(_WORD *)(v9 + v8 - 2)
        + *(_WORD *)v19 * *(_WORD *)(v10 + v8 - 2)
        + *v59 * *(_WORD *)(v11 + v8 - 2)
        + *v58 * *(_WORD *)(v8 + v12 - 2)
        + *v20 * *(_WORD *)(v13 + v8 - 2)
        + v24;
    v20 = v57;
    *(_WORD *)&v22[v8 - 2] = v25 >> 6;
    --v16;
  }
  while ( v16 );
  v26 = v51;
  v27 = a4;
  v28 = 0;
  v29 = (__int64)v51 << 6;
  **((_BYTE **)&v65 + 1) = (unsigned __int16)(v70 * *(_WORD *)&byte_1800DE848[v29]
                                            + v71 * *(__int16 *)((char *)&word_1800DE84A + v29)
                                            + v67 * *(__int16 *)((char *)&word_1800DE842 + v29)
                                            + v68 * *(_WORD *)&byte_1800DE844[v29]
                                            + v72 * *(_WORD *)((char *)&dword_1800DE84C + v29)
                                            + v69 * *(__int16 *)((char *)&word_1800DE846 + v29)
                                            + v66 * *(_WORD *)&Binary::Policy::NewMode::OddOperation[v29]) >> 8;
  v61 = 1;
  if ( (int)a3[3] > 1 )
  {
    v30 = 1;
    v62 = 1;
    do
    {
      v31 = Binary::Policy::NewMode::GlobalCase[v26];
      v32 = 0;
      v28 += v31;
      v33 = 7 - v31;
      v52 = v28;
      v34 = 7 - (int)v31;
      if ( 7 - (int)v31 > 0 )
      {
        do
        {
          *(&v66 + v32) = *(&v66 + v31 + v32);
          ++v32;
        }
        while ( v32 < v33 );
      }
      if ( v33 < 7LL )
      {
        v35 = v27[3];
        v36 = v27[4] - v35;
        v37 = v27[5] - v35;
        v38 = v27[6] - v35;
        v39 = *v27 - v35;
        v40 = v27[1] - v35;
        v41 = v28;
        v42 = v27[2] - v35;
        v43 = v35 + 2 * (v41 + v34);
        v44 = (char *)&v66 - v35 + -2 * v41;
        v45 = 7 - v34;
        v46 = *(_WORD *)v53;
        do
        {
          v47 = *(_WORD *)(v39 + v43);
          v48 = *(_WORD *)(v40 + v43);
          v43 += 2;
          *(_WORD *)&v44[v43 - 2] = (unsigned __int16)(*v55 * *(_WORD *)(v43 - 2)
                                                     + v46 * *(_WORD *)(v42 + v43 - 2)
                                                     + *(_WORD *)v54 * *(_WORD *)(v36 + v43 - 2)
                                                     + *v59 * *(_WORD *)(v43 + v37 - 2)
                                                     + *v58 * *(_WORD *)(v38 + v43 - 2)
                                                     + *v57 * v48
                                                     + *v56 * v47) >> 6;
          --v45;
        }
        while ( v45 );
        v26 = v51;
        v27 = a4;
        v28 = v52;
        v30 = v62;
      }
      v49 = v26 + 1;
      v26 = 0;
      if ( v49 < 2 )
        v26 = v49;
      v50 = (__int64)v26 << 6;
      v51 = v26;
      *(_BYTE *)(v30 + *((_QWORD *)&v65 + 1)) = (unsigned __int16)(v70 * *(_WORD *)&byte_1800DE848[v50]
                                                                 + v71 * *(__int16 *)((char *)&word_1800DE84A + v50)
                                                                 + v67 * *(__int16 *)((char *)&word_1800DE842 + v50)
                                                                 + v68 * *(_WORD *)&byte_1800DE844[v50]
                                                                 + v72 * *(_WORD *)((char *)&dword_1800DE84C + v50)
                                                                 + v69 * *(__int16 *)((char *)&word_1800DE846 + v50)
                                                                 + v66
                                                                 * *(_WORD *)&Binary::Policy::NewMode::OddOperation[v50]) >> 8;
      ++v30;
      ++v61;
      v62 = v30;
    }
    while ( v61 < a3[3] );
  }
  Binary::Policy::CompleteOperation::MoveVirtualAddition(a2);
}

```

## disassembly

```asm
0x180090300  mov     r11, rsp
0x180090303  mov     [r11+8], rbx
0x180090307  push    rbp
0x180090308  push    rsi
0x180090309  push    rdi
0x18009030a  push    r12
0x18009030c  push    r13
0x18009030e  push    r14
0x180090310  push    r15
0x180090312  sub     rsp, 0C0h
0x180090319  mov     rax, cs:__security_cookie
0x180090320  xor     rax, rsp
0x180090323  mov     [rsp+0F8h+var_48], rax
0x18009032b  mov     rax, rdx
0x18009032e  mov     [rsp+0F8h+var_70], rdx
0x180090336  mov     ebx, ecx
0x180090338  mov     [rsp+0F8h+var_D8], ecx
0x18009033c  xorps   xmm0, xmm0
0x18009033f  mov     [rsp+0F8h+var_90], r9
0x180090344  xor     edi, edi
0x180090346  mov     [rsp+0F8h+var_78], r8
0x18009034e  mov     rcx, rax
0x180090351  mov     [rsp+0F8h+var_D0], edi
0x180090355  lea     rdx, [r11-68h]
0x180090359  mov     r13, r9
0x18009035c  movups  xmmword ptr [r11-68h], xmm0
0x180090361  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x180090366  cmp     ebx, 1
0x180090369  jbe     short loc_18009038D
0x18009036b  and     ebx, 80000001h
0x180090371  mov     [rsp+0F8h+var_D8], ebx
0x180090375  jge     short loc_180090382
0x180090377  dec     ebx
0x180090379  or      ebx, 0FFFFFFFEh
0x18009037c  inc     ebx
0x18009037e  mov     [rsp+0F8h+var_D8], ebx
0x180090382  test    ebx, ebx
0x180090384  jns     short loc_18009038D
0x180090386  add     ebx, 2
0x180090389  mov     [rsp+0F8h+var_D8], ebx
0x18009038d  mov     r8, [r13+18h]
0x180090391  lea     rdx, cs:180000000h
0x180090398  mov     r10, [r13+10h]
0x18009039c  lea     rcx, rva byte_1800DE844[rdx]
0x1800903a3  mov     r11, [r13+20h]
0x1800903a7  lea     r12, [rsp+0F8h+var_58]
0x1800903af  mov     rsi, [r13+28h]
0x1800903b3  sub     r10, r8
0x1800903b6  mov     rbp, [r13+30h]
0x1800903ba  sub     r11, r8
0x1800903bd  mov     r14, [r13+8]
0x1800903c1  sub     rsi, r8
0x1800903c4  mov     r15, [r13+0]
0x1800903c8  sub     rbp, r8
0x1800903cb  movsxd  rax, [rsp+0F8h+arg_20]
0x1800903d3  sub     r14, r8
0x1800903d6  shl     rax, 6
0x1800903da  sub     r15, r8
0x1800903dd  add     rcx, rax
0x1800903e0  mov     r9d, 7
0x1800903e6  mov     [rsp+0F8h+var_C8], rcx
0x1800903eb  lea     rcx, rva word_1800DE846[rdx]
0x1800903f2  mov     rdi, [rsp+0F8h+var_C8]
0x1800903f7  add     rcx, rax
0x1800903fa  mov     [rsp+0F8h+var_B8], rcx
0x1800903ff  lea     rcx, rva byte_1800DE848[rdx]
0x180090406  mov     r13, [rsp+0F8h+var_B8]
0x18009040b  add     rcx, rax
0x18009040e  mov     [rsp+0F8h+var_C0], rcx
0x180090413  lea     rcx, rva word_1800DE84A[rdx]
0x18009041a  mov     rbx, [rsp+0F8h+var_C0]
0x18009041f  add     rcx, rax
0x180090422  mov     [rsp+0F8h+var_98], rcx
0x180090427  lea     rcx, rva dword_1800DE84C[rdx]
0x18009042e  add     rcx, rax
0x180090431  mov     [rsp+0F8h+var_A0], rcx
0x180090436  lea     rcx, rva word_1800DE842[rdx]
0x18009043d  add     rcx, rax
0x180090440  lea     rax, [rax+0DE840h]
0x180090447  add     rax, rdx
0x18009044a  mov     [rsp+0F8h+var_A8], rcx
0x18009044f  mov     [rsp+0F8h+var_B0], rax
0x180090454  sub     r12, r8
0x180090457  nop     word ptr [rax+rax+00000000h]
0x180090460  movzx   eax, word ptr [rax]
0x180090463  movzx   edx, word ptr [r15+r8]
0x180090468  lea     r8, [r8+2]
0x18009046c  imul    edx, eax
0x18009046f  movzx   eax, word ptr [rcx]
0x180090472  movzx   ecx, word ptr [r14+r8-2]
0x180090478  imul    ecx, eax
0x18009047b  mov     rax, [rsp+0F8h+var_A0]
0x180090480  movzx   eax, word ptr [rax]
0x180090483  add     dx, cx
0x180090486  movzx   ecx, word ptr [r8+rbp-2]
0x18009048c  imul    ecx, eax
0x18009048f  mov     rax, [rsp+0F8h+var_98]
0x180090494  movzx   eax, word ptr [rax]
0x180090497  add     dx, cx
0x18009049a  movzx   ecx, word ptr [rsi+r8-2]
0x1800904a0  imul    ecx, eax
0x1800904a3  movzx   eax, word ptr [rbx]
0x1800904a6  add     dx, cx
0x1800904a9  movzx   ecx, word ptr [r11+r8-2]
0x1800904af  imul    ecx, eax
0x1800904b2  movzx   eax, word ptr [rdi]
0x1800904b5  add     dx, cx
0x1800904b8  movzx   ecx, word ptr [r10+r8-2]
0x1800904be  imul    ecx, eax
0x1800904c1  movzx   eax, word ptr [r13+0]
0x1800904c6  add     dx, cx
0x1800904c9  movzx   ecx, word ptr [r8-2]
0x1800904ce  imul    ecx, eax
0x1800904d1  mov     rax, [rsp+0F8h+var_B0]
0x1800904d6  add     dx, cx
0x1800904d9  mov     rcx, [rsp+0F8h+var_A8]
0x1800904de  shr     dx, 6
0x1800904e2  mov     [r12+r8-2], dx
0x1800904e8  sub     r9, 1
0x1800904ec  jnz     loc_180090460
0x1800904f2  movzx   eax, [rsp+0F8h+var_58]
0x1800904fa  lea     r9, cs:180000000h
0x180090501  movsxd  rbx, [rsp+0F8h+var_D8]
0x180090506  mov     r13, [rsp+0F8h+var_90]
0x18009050b  mov     rdx, rbx
0x18009050e  mov     edi, [rsp+0F8h+var_D0]
0x180090512  shl     rdx, 6
0x180090516  movzx   r8d, word ptr [rdx+r9+0DE840h]
0x18009051f  movzx   ecx, word ptr [rdx+r9+0DE846h]
0x180090528  imul    r8d, eax
0x18009052c  movzx   eax, [rsp+0F8h+var_52]
0x180090534  imul    ecx, eax
0x180090537  movzx   eax, [rsp+0F8h+var_4C]
0x18009053f  add     r8w, cx
0x180090543  movzx   ecx, word ptr [rdx+r9+0DE84Ch]
0x18009054c  imul    ecx, eax
0x18009054f  movzx   eax, [rsp+0F8h+var_54]
0x180090557  add     r8w, cx
0x18009055b  movzx   ecx, word ptr [rdx+r9+0DE844h]
0x180090564  imul    ecx, eax
0x180090567  movzx   eax, [rsp+0F8h+var_56]
0x18009056f  add     r8w, cx
0x180090573  movzx   ecx, word ptr [rdx+r9+0DE842h]
0x18009057c  imul    ecx, eax
0x18009057f  movzx   eax, [rsp+0F8h+var_4E]
0x180090587  add     r8w, cx
0x18009058b  movzx   ecx, word ptr [rdx+r9+0DE84Ah]
0x180090594  imul    ecx, eax
0x180090597  movzx   eax, [rsp+0F8h+var_50]
0x18009059f  add     r8w, cx
0x1800905a3  movzx   ecx, word ptr [rdx+r9+0DE848h]
0x1800905ac  imul    ecx, eax
0x1800905af  mov     rax, [rsp+0F8h+var_60]
0x1800905b7  add     r8w, cx
0x1800905bb  shr     r8w, 8
0x1800905c0  mov     [rax], r8b
0x1800905c3  mov     r8d, 1
0x1800905c9  mov     rax, [rsp+0F8h+var_78]
0x1800905d1  mov     [rsp+0F8h+var_88], r8
0x1800905d6  cmp     [rax+0Ch], r8d
0x1800905da  jle     loc_18009085B
0x1800905e0  mov     r10d, r8d
0x1800905e3  mov     [rsp+0F8h+var_80], r8
0x1800905e8  nop     dword ptr [rax+rax+00000000h]
0x1800905f0  movsxd  rax, ebx
0x1800905f3  mov     ecx, 7
0x1800905f8  movsxd  rdx, ds:rva ?GlobalCase@NewMode@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B[r9+rax*4]; Data::StripedCategory<int,2> const Binary::Policy::NewMode::GlobalCase ...
0x180090600  xor     eax, eax
0x180090602  add     edi, edx
0x180090604  sub     ecx, edx
0x180090606  mov     [rsp+0F8h+var_D0], edi
0x18009060a  movsxd  r9, ecx
0x18009060d  test    ecx, ecx
0x18009060f  jle     short loc_18009063C
0x180090611  lea     r8, [rdx+rdx]
0x180090615  nop     word ptr [rax+rax+00000000h]
0x180090620  lea     rcx, [r8+rax*2]
0x180090624  movzx   edx, [rsp+rcx+0F8h+var_58]
0x18009062c  mov     [rsp+rax*2+0F8h+var_58], dx
0x180090634  inc     rax
0x180090637  cmp     rax, r9
0x18009063a  jl      short loc_180090620
0x18009063c  cmp     r9, 7
0x180090640  jge     loc_180090761
0x180090646  mov     rdx, [r13+18h]
0x18009064a  lea     r11, [rsp+0F8h+var_58]
0x180090652  mov     rax, [rsp+0F8h+var_C8]
0x180090657  mov     r10d, 7
0x18009065d  mov     rsi, [r13+20h]
0x180090661  mov     rbp, [r13+28h]
0x180090665  sub     rsi, rdx
0x180090668  mov     r14, [r13+30h]
0x18009066c  sub     rbp, rdx
0x18009066f  movzx   eax, word ptr [rax]
0x180090672  sub     r14, rdx
0x180090675  mov     r15, [r13+0]
0x180090679  mov     r12, [r13+8]
0x18009067d  sub     r15, rdx
0x180090680  mov     rbx, [rsp+0F8h+var_C0]
0x180090685  sub     r12, rdx
0x180090688  movsxd  rcx, edi
0x18009068b  mov     rdi, [r13+10h]
0x18009068f  mov     r13, [rsp+0F8h+var_B8]
0x180090694  sub     rdi, rdx
0x180090697  mov     [rsp+0F8h+var_D4], ax
0x18009069c  lea     rax, [rcx+r9]
0x1800906a0  lea     r8, [rdx+rax*2]
0x1800906a4  lea     rax, [rcx+rcx]
0x1800906a8  sub     r11, rax
0x1800906ab  sub     r11, rdx
0x1800906ae  sub     r10, r9
0x1800906b1  movzx   r9d, [rsp+0F8h+var_D4]
0x1800906b7  nop     word ptr [rax+rax+00000000h]
0x1800906c0  mov     rax, [rsp+0F8h+var_B0]
0x1800906c5  movzx   edx, word ptr [r15+r8]
0x1800906ca  movzx   ecx, word ptr [r12+r8]
0x1800906cf  lea     r8, [r8+2]
0x1800906d3  movzx   eax, word ptr [rax]
0x1800906d6  imul    edx, eax
0x1800906d9  mov     rax, [rsp+0F8h+var_A8]
0x1800906de  movzx   eax, word ptr [rax]
0x1800906e1  imul    ecx, eax
0x1800906e4  mov     rax, [rsp+0F8h+var_A0]
0x1800906e9  movzx   eax, word ptr [rax]
0x1800906ec  add     dx, cx
0x1800906ef  movzx   ecx, word ptr [r14+r8-2]
0x1800906f5  imul    ecx, eax
0x1800906f8  mov     rax, [rsp+0F8h+var_98]
0x1800906fd  movzx   eax, word ptr [rax]
0x180090700  add     dx, cx
0x180090703  movzx   ecx, word ptr [r8+rbp-2]
0x180090709  imul    ecx, eax
0x18009070c  movzx   eax, word ptr [rbx]
0x18009070f  add     dx, cx
0x180090712  movzx   ecx, word ptr [rsi+r8-2]
0x180090718  imul    ecx, eax
0x18009071b  movzx   eax, word ptr [r13+0]
0x180090720  add     dx, cx
0x180090723  movzx   ecx, word ptr [rdi+r8-2]
0x180090729  imul    ecx, r9d
0x18009072d  add     dx, cx
0x180090730  movzx   ecx, word ptr [r8-2]
0x180090735  imul    ecx, eax
0x180090738  add     dx, cx
0x18009073b  shr     dx, 6
0x18009073f  mov     [r11+r8-2], dx
0x180090745  sub     r10, 1
0x180090749  jnz     loc_1800906C0
0x18009074f  mov     ebx, [rsp+0F8h+var_D8]
0x180090753  mov     r13, [rsp+0F8h+var_90]
0x180090758  mov     edi, [rsp+0F8h+var_D0]
0x18009075c  mov     r10, [rsp+0F8h+var_80]
0x180090761  lea     r9, cs:180000000h
0x180090768  lea     eax, [rbx+1]
0x18009076b  xor     ebx, ebx
0x18009076d  cmp     eax, 2
0x180090770  cmovl   ebx, eax
0x180090773  movzx   eax, [rsp+0F8h+var_58]
0x18009077b  movsxd  rdx, ebx
0x18009077e  shl     rdx, 6
0x180090782  mov     [rsp+0F8h+var_D8], ebx
0x180090786  movzx   r8d, word ptr [rdx+r9+0DE840h]
0x18009078f  movzx   ecx, word ptr [rdx+r9+0DE846h]
0x180090798  imul    r8d, eax
0x18009079c  movzx   eax, [rsp+0F8h+var_52]
0x1800907a4  imul    ecx, eax
0x1800907a7  movzx   eax, [rsp+0F8h+var_4C]
0x1800907af  add     r8w, cx
0x1800907b3  movzx   ecx, word ptr [rdx+r9+0DE84Ch]
0x1800907bc  imul    ecx, eax
0x1800907bf  movzx   eax, [rsp+0F8h+var_54]
0x1800907c7  add     r8w, cx
0x1800907cb  movzx   ecx, word ptr [rdx+r9+0DE844h]
0x1800907d4  imul    ecx, eax
0x1800907d7  movzx   eax, [rsp+0F8h+var_56]
0x1800907df  add     r8w, cx
0x1800907e3  movzx   ecx, word ptr [rdx+r9+0DE842h]
0x1800907ec  imul    ecx, eax
0x1800907ef  movzx   eax, [rsp+0F8h+var_4E]
0x1800907f7  add     r8w, cx
0x1800907fb  movzx   ecx, word ptr [rdx+r9+0DE84Ah]
0x180090804  imul    ecx, eax
0x180090807  movzx   eax, [rsp+0F8h+var_50]
0x18009080f  add     r8w, cx
0x180090813  movzx   ecx, word ptr [rdx+r9+0DE848h]
0x18009081c  imul    ecx, eax
0x18009081f  mov     rax, [rsp+0F8h+var_60]
0x180090827  add     r8w, cx
0x18009082b  shr     r8w, 8
0x180090830  mov     [r10+rax], r8b
0x180090834  inc     r10
0x180090837  mov     r8, [rsp+0F8h+var_88]
0x18009083c  mov     rax, [rsp+0F8h+var_78]
0x180090844  inc     r8d
0x180090847  mov     [rsp+0F8h+var_88], r8
0x18009084c  mov     [rsp+0F8h+var_80], r10
0x180090851  cmp     r8d, [rax+0Ch]
0x180090855  jl      loc_1800905F0
0x18009085b  mov     rcx, [rsp+0F8h+var_70]
0x180090863  lea     rdx, [rsp+0F8h+var_68]
  ... truncated ...
```
