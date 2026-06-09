# Binary::Policy::PutBooleanUnit<Binary::Policy::NewMode,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[7],int)

- ea: `0x1800896c0`
- end: `0x180089c5b`
- name: `??$PutBooleanUnit@VNewMode@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY06$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1435`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800883a0`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x1800896c0`

## pseudocode

```c
__int64 __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::NewMode,3>(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5)
{
  signed int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // r10
  __int64 v14; // r11
  __int64 v15; // rsi
  __int64 v16; // rbp
  __int64 v17; // r14
  __int64 v18; // rax
  __int64 v19; // r15
  __int64 v20; // r9
  char *v21; // rdi
  _WORD *v22; // r13
  char *v23; // rbx
  _WORD *v24; // rcx
  _WORD *v25; // rax
  char *v26; // r12
  __int16 v27; // dx
  __int16 v28; // dx
  unsigned __int16 v29; // dx
  int v30; // ebx
  _QWORD *v31; // r13
  int v32; // edi
  __int64 v33; // rdx
  __int64 v34; // r10
  __int64 v35; // rdx
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rsi
  __int64 v41; // rbp
  __int64 v42; // r14
  __int64 v43; // r15
  __int64 v44; // r12
  __int64 v45; // rcx
  __int64 v46; // rdi
  __int64 v47; // r8
  char *v48; // r11
  __int64 v49; // r10
  __int16 v50; // r9
  __int16 v51; // dx
  __int16 v52; // cx
  int v53; // eax
  __int64 v54; // rdx
  int v56; // [rsp+20h] [rbp-D8h]
  int v57; // [rsp+28h] [rbp-D0h]
  char *v58; // [rsp+30h] [rbp-C8h]
  char *v59; // [rsp+38h] [rbp-C0h]
  _WORD *v60; // [rsp+40h] [rbp-B8h]
  _WORD *v61; // [rsp+48h] [rbp-B0h]
  _WORD *v62; // [rsp+50h] [rbp-A8h]
  _WORD *v63; // [rsp+58h] [rbp-A0h]
  _WORD *v64; // [rsp+60h] [rbp-98h]
  int v66; // [rsp+70h] [rbp-88h]
  __int64 v67; // [rsp+78h] [rbp-80h]
  _BYTE v70[8]; // [rsp+90h] [rbp-68h] BYREF
  _BYTE *v71; // [rsp+98h] [rbp-60h]
  __int16 v72; // [rsp+A0h] [rbp-58h] BYREF
  __int16 v73; // [rsp+A2h] [rbp-56h]
  __int16 v74; // [rsp+A4h] [rbp-54h]
  __int16 v75; // [rsp+A6h] [rbp-52h]
  __int16 v76; // [rsp+A8h] [rbp-50h]
  __int16 v77; // [rsp+AAh] [rbp-4Eh]
  __int16 v78; // [rsp+ACh] [rbp-4Ch]

  v56 = a1;
  __asm { vpxor   xmm0, xmm0, xmm0 }
  _RDX = v70;
  __asm { vmovups xmmword ptr [r11-68h], xmm0 }
  Binary::Policy::CompleteOperation::TargetDigitalRegion(a2, v70);
  if ( a1 > 1 )
  {
    v11 = a1 & 0x80000001;
    v56 = v11;
    if ( v11 < 0 )
    {
      v11 = (((_BYTE)v11 - 1) | 0xFFFFFFFE) + 1;
      v56 = v11;
    }
    if ( v11 < 0 )
      v56 = v11 + 2;
  }
  v12 = a4[3];
  v13 = a4[2] - v12;
  v14 = a4[4] - v12;
  v15 = a4[5] - v12;
  v16 = a4[6] - v12;
  v17 = a4[1] - v12;
  v18 = (__int64)a5 << 6;
  v19 = *a4 - v12;
  v20 = 7;
  v58 = &byte_1800DE844[v18];
  v21 = &byte_1800DE844[v18];
  v60 = (__int16 *)((char *)&word_1800DE846 + v18);
  v22 = (__int16 *)((char *)&word_1800DE846 + v18);
  v59 = &byte_1800DE848[v18];
  v23 = &byte_1800DE848[v18];
  v64 = (__int16 *)((char *)&word_1800DE84A + v18);
  v63 = (_WORD *)((char *)&dword_1800DE84C + v18);
  v24 = (__int16 *)((char *)&word_1800DE842 + v18);
  v25 = (_WORD *)(0x180000000LL + v18 + 911424);
  v62 = v24;
  v61 = v25;
  v26 = (char *)&v72 - v12;
  do
  {
    v27 = *(_WORD *)(v19 + v12);
    v12 += 2;
    v28 = *v25 * v27;
    v25 = v61;
    v29 = *v22 * *(_WORD *)(v12 - 2)
        + *(_WORD *)v21 * *(_WORD *)(v13 + v12 - 2)
        + *(_WORD *)v23 * *(_WORD *)(v14 + v12 - 2)
        + *v64 * *(_WORD *)(v15 + v12 - 2)
        + *v63 * *(_WORD *)(v12 + v16 - 2)
        + *v24 * *(_WORD *)(v17 + v12 - 2)
        + v28;
    v24 = v62;
    *(_WORD *)&v26[v12 - 2] = v29 >> 6;
    --v20;
  }
  while ( v20 );
  v30 = v56;
  v31 = a4;
  v32 = 0;
  v33 = (__int64)v56 << 6;
  *v71 = (unsigned __int16)(v76 * *(_WORD *)&byte_1800DE848[v33]
                          + v77 * *(__int16 *)((char *)&word_1800DE84A + v33)
                          + v73 * *(__int16 *)((char *)&word_1800DE842 + v33)
                          + v74 * *(_WORD *)&byte_1800DE844[v33]
                          + v78 * *(_WORD *)((char *)&dword_1800DE84C + v33)
                          + v75 * *(__int16 *)((char *)&word_1800DE846 + v33)
                          + v72 * *(_WORD *)&Binary::Policy::NewMode::OddOperation[v33]) >> 8;
  v66 = 1;
  if ( *(int *)(a3 + 12) > 1 )
  {
    v34 = 1;
    v67 = 1;
    do
    {
      v35 = Binary::Policy::NewMode::GlobalCase[v30];
      v36 = 0;
      v32 += v35;
      v37 = 7 - v35;
      v57 = v32;
      v38 = 7 - (int)v35;
      if ( 7 - (int)v35 > 0 )
      {
        do
        {
          *(&v72 + v36) = *(&v72 + v35 + v36);
          ++v36;
        }
        while ( v36 < v37 );
      }
      if ( v37 < 7LL )
      {
        v39 = v31[3];
        v40 = v31[4] - v39;
        v41 = v31[5] - v39;
        v42 = v31[6] - v39;
        v43 = *v31 - v39;
        v44 = v31[1] - v39;
        v45 = v32;
        v46 = v31[2] - v39;
        v47 = v39 + 2 * (v45 + v38);
        v48 = (char *)&v72 - v39 + -2 * v45;
        v49 = 7 - v38;
        v50 = *(_WORD *)v58;
        do
        {
          v51 = *(_WORD *)(v43 + v47);
          v52 = *(_WORD *)(v44 + v47);
          v47 += 2;
          *(_WORD *)&v48[v47 - 2] = (unsigned __int16)(*v60 * *(_WORD *)(v47 - 2)
                                                     + v50 * *(_WORD *)(v46 + v47 - 2)
                                                     + *(_WORD *)v59 * *(_WORD *)(v40 + v47 - 2)
                                                     + *v64 * *(_WORD *)(v47 + v41 - 2)
                                                     + *v63 * *(_WORD *)(v42 + v47 - 2)
                                                     + *v62 * v52
                                                     + *v61 * v51) >> 6;
          --v49;
        }
        while ( v49 );
        v30 = v56;
        v31 = a4;
        v32 = v57;
        v34 = v67;
      }
      v53 = v30 + 1;
      v30 = 0;
      if ( v53 < 2 )
        v30 = v53;
      v54 = (__int64)v30 << 6;
      v56 = v30;
      v71[v34++] = (unsigned __int16)(v76 * *(_WORD *)&byte_1800DE848[v54]
                                    + v77 * *(__int16 *)((char *)&word_1800DE84A + v54)
                                    + v73 * *(__int16 *)((char *)&word_1800DE842 + v54)
                                    + v74 * *(_WORD *)&byte_1800DE844[v54]
                                    + v78 * *(_WORD *)((char *)&dword_1800DE84C + v54)
                                    + v75 * *(__int16 *)((char *)&word_1800DE846 + v54)
                                    + v72 * *(_WORD *)&Binary::Policy::NewMode::OddOperation[v54]) >> 8;
      ++v66;
      v67 = v34;
    }
    while ( v66 < *(_DWORD *)(a3 + 12) );
  }
  return Binary::Policy::CompleteOperation::MoveVirtualAddition(a2, v70);
}

```

## disassembly

```asm
0x1800896c0  mov     r11, rsp
0x1800896c3  mov     [r11+8], rbx
0x1800896c7  push    rbp
0x1800896c8  push    rsi
0x1800896c9  push    rdi
0x1800896ca  push    r12
0x1800896cc  push    r13
0x1800896ce  push    r14
0x1800896d0  push    r15
0x1800896d2  sub     rsp, 0C0h
0x1800896d9  mov     rax, cs:__security_cookie
0x1800896e0  xor     rax, rsp
0x1800896e3  mov     [rsp+0F8h+var_48], rax
0x1800896eb  mov     rax, rdx
0x1800896ee  mov     [rsp+0F8h+var_70], rdx
0x1800896f6  mov     ebx, ecx
0x1800896f8  mov     [rsp+0F8h+var_D8], ecx
0x1800896fc  vpxor   xmm0, xmm0, xmm0
0x180089700  xor     edi, edi
0x180089702  mov     [rsp+0F8h+var_90], r9
0x180089707  mov     rcx, rax
0x18008970a  mov     [rsp+0F8h+var_78], r8
0x180089712  lea     rdx, [r11-68h]
0x180089716  mov     [rsp+0F8h+var_D0], edi
0x18008971a  mov     r13, r9
0x18008971d  vmovups xmmword ptr [r11-68h], xmm0
0x180089723  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x180089728  cmp     ebx, 1
0x18008972b  jbe     short loc_18008974F
0x18008972d  and     ebx, 80000001h
0x180089733  mov     [rsp+0F8h+var_D8], ebx
0x180089737  jge     short loc_180089744
0x180089739  dec     ebx
0x18008973b  or      ebx, 0FFFFFFFEh
0x18008973e  inc     ebx
0x180089740  mov     [rsp+0F8h+var_D8], ebx
0x180089744  test    ebx, ebx
0x180089746  jns     short loc_18008974F
0x180089748  add     ebx, 2
0x18008974b  mov     [rsp+0F8h+var_D8], ebx
0x18008974f  mov     r8, [r13+18h]
0x180089753  lea     rdx, cs:180000000h
0x18008975a  mov     r10, [r13+10h]
0x18008975e  lea     rcx, rva byte_1800DE844[rdx]
0x180089765  mov     r11, [r13+20h]
0x180089769  lea     r12, [rsp+0F8h+var_58]
0x180089771  mov     rsi, [r13+28h]
0x180089775  sub     r10, r8
0x180089778  mov     rbp, [r13+30h]
0x18008977c  sub     r11, r8
0x18008977f  mov     r14, [r13+8]
0x180089783  sub     rsi, r8
0x180089786  mov     r15, [r13+0]
0x18008978a  sub     rbp, r8
0x18008978d  movsxd  rax, [rsp+0F8h+arg_20]
0x180089795  sub     r14, r8
0x180089798  shl     rax, 6
0x18008979c  sub     r15, r8
0x18008979f  add     rcx, rax
0x1800897a2  mov     r9d, 7
0x1800897a8  mov     [rsp+0F8h+var_C8], rcx
0x1800897ad  lea     rcx, rva word_1800DE846[rdx]
0x1800897b4  mov     rdi, [rsp+0F8h+var_C8]
0x1800897b9  add     rcx, rax
0x1800897bc  mov     [rsp+0F8h+var_B8], rcx
0x1800897c1  lea     rcx, rva byte_1800DE848[rdx]
0x1800897c8  mov     r13, [rsp+0F8h+var_B8]
0x1800897cd  add     rcx, rax
0x1800897d0  mov     [rsp+0F8h+var_C0], rcx
0x1800897d5  lea     rcx, rva word_1800DE84A[rdx]
0x1800897dc  mov     rbx, [rsp+0F8h+var_C0]
0x1800897e1  add     rcx, rax
0x1800897e4  mov     [rsp+0F8h+var_98], rcx
0x1800897e9  lea     rcx, rva dword_1800DE84C[rdx]
0x1800897f0  add     rcx, rax
0x1800897f3  mov     [rsp+0F8h+var_A0], rcx
0x1800897f8  lea     rcx, rva word_1800DE842[rdx]
0x1800897ff  add     rcx, rax
0x180089802  lea     rax, [rax+0DE840h]
0x180089809  add     rax, rdx
0x18008980c  mov     [rsp+0F8h+var_A8], rcx
0x180089811  mov     [rsp+0F8h+var_B0], rax
0x180089816  sub     r12, r8
0x180089819  nop     dword ptr [rax+00000000h]
0x180089820  movzx   eax, word ptr [rax]
0x180089823  movzx   edx, word ptr [r15+r8]
0x180089828  lea     r8, [r8+2]
0x18008982c  imul    edx, eax
0x18008982f  movzx   eax, word ptr [rcx]
0x180089832  movzx   ecx, word ptr [r14+r8-2]
0x180089838  imul    ecx, eax
0x18008983b  mov     rax, [rsp+0F8h+var_A0]
0x180089840  movzx   eax, word ptr [rax]
0x180089843  add     dx, cx
0x180089846  movzx   ecx, word ptr [r8+rbp-2]
0x18008984c  imul    ecx, eax
0x18008984f  mov     rax, [rsp+0F8h+var_98]
0x180089854  movzx   eax, word ptr [rax]
0x180089857  add     dx, cx
0x18008985a  movzx   ecx, word ptr [rsi+r8-2]
0x180089860  imul    ecx, eax
0x180089863  movzx   eax, word ptr [rbx]
0x180089866  add     dx, cx
0x180089869  movzx   ecx, word ptr [r11+r8-2]
0x18008986f  imul    ecx, eax
0x180089872  movzx   eax, word ptr [rdi]
0x180089875  add     dx, cx
0x180089878  movzx   ecx, word ptr [r10+r8-2]
0x18008987e  imul    ecx, eax
0x180089881  movzx   eax, word ptr [r13+0]
0x180089886  add     dx, cx
0x180089889  movzx   ecx, word ptr [r8-2]
0x18008988e  imul    ecx, eax
0x180089891  mov     rax, [rsp+0F8h+var_B0]
0x180089896  add     dx, cx
0x180089899  mov     rcx, [rsp+0F8h+var_A8]
0x18008989e  shr     dx, 6
0x1800898a2  mov     [r12+r8-2], dx
0x1800898a8  sub     r9, 1
0x1800898ac  jnz     loc_180089820
0x1800898b2  movzx   eax, [rsp+0F8h+var_58]
0x1800898ba  lea     r9, cs:180000000h
0x1800898c1  movsxd  rbx, [rsp+0F8h+var_D8]
0x1800898c6  mov     r13, [rsp+0F8h+var_90]
0x1800898cb  mov     rdx, rbx
0x1800898ce  mov     edi, [rsp+0F8h+var_D0]
0x1800898d2  shl     rdx, 6
0x1800898d6  movzx   r8d, word ptr [rdx+r9+0DE840h]
0x1800898df  movzx   ecx, word ptr [rdx+r9+0DE846h]
0x1800898e8  imul    r8d, eax
0x1800898ec  movzx   eax, [rsp+0F8h+var_52]
0x1800898f4  imul    ecx, eax
0x1800898f7  movzx   eax, [rsp+0F8h+var_4C]
0x1800898ff  add     r8w, cx
0x180089903  movzx   ecx, word ptr [rdx+r9+0DE84Ch]
0x18008990c  imul    ecx, eax
0x18008990f  movzx   eax, [rsp+0F8h+var_54]
0x180089917  add     r8w, cx
0x18008991b  movzx   ecx, word ptr [rdx+r9+0DE844h]
0x180089924  imul    ecx, eax
0x180089927  movzx   eax, [rsp+0F8h+var_56]
0x18008992f  add     r8w, cx
0x180089933  movzx   ecx, word ptr [rdx+r9+0DE842h]
0x18008993c  imul    ecx, eax
0x18008993f  movzx   eax, [rsp+0F8h+var_4E]
0x180089947  add     r8w, cx
0x18008994b  movzx   ecx, word ptr [rdx+r9+0DE84Ah]
0x180089954  imul    ecx, eax
0x180089957  movzx   eax, [rsp+0F8h+var_50]
0x18008995f  add     r8w, cx
0x180089963  movzx   ecx, word ptr [rdx+r9+0DE848h]
0x18008996c  imul    ecx, eax
0x18008996f  mov     rax, [rsp+0F8h+var_60]
0x180089977  add     r8w, cx
0x18008997b  shr     r8w, 8
0x180089980  mov     [rax], r8b
0x180089983  mov     r8d, 1
0x180089989  mov     rax, [rsp+0F8h+var_78]
0x180089991  mov     [rsp+0F8h+var_88], r8
0x180089996  cmp     [rax+0Ch], r8d
0x18008999a  jle     loc_180089C1B
0x1800899a0  mov     r10d, r8d
0x1800899a3  mov     [rsp+0F8h+var_80], r8
0x1800899a8  nop     dword ptr [rax+rax+00000000h]
0x1800899b0  movsxd  rax, ebx
0x1800899b3  mov     ecx, 7
0x1800899b8  movsxd  rdx, ds:rva ?GlobalCase@NewMode@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B[r9+rax*4]; Data::StripedCategory<int,2> const Binary::Policy::NewMode::GlobalCase ...
0x1800899c0  xor     eax, eax
0x1800899c2  add     edi, edx
0x1800899c4  sub     ecx, edx
0x1800899c6  mov     [rsp+0F8h+var_D0], edi
0x1800899ca  movsxd  r9, ecx
0x1800899cd  test    ecx, ecx
0x1800899cf  jle     short loc_1800899FC
0x1800899d1  lea     r8, [rdx+rdx]
0x1800899d5  nop     word ptr [rax+rax+00000000h]
0x1800899e0  lea     rcx, [r8+rax*2]
0x1800899e4  movzx   edx, [rsp+rcx+0F8h+var_58]
0x1800899ec  mov     [rsp+rax*2+0F8h+var_58], dx
0x1800899f4  inc     rax
0x1800899f7  cmp     rax, r9
0x1800899fa  jl      short loc_1800899E0
0x1800899fc  cmp     r9, 7
0x180089a00  jge     loc_180089B21
0x180089a06  mov     rdx, [r13+18h]
0x180089a0a  lea     r11, [rsp+0F8h+var_58]
0x180089a12  mov     rax, [rsp+0F8h+var_C8]
0x180089a17  mov     r10d, 7
0x180089a1d  mov     rsi, [r13+20h]
0x180089a21  mov     rbp, [r13+28h]
0x180089a25  sub     rsi, rdx
0x180089a28  mov     r14, [r13+30h]
0x180089a2c  sub     rbp, rdx
0x180089a2f  movzx   eax, word ptr [rax]
0x180089a32  sub     r14, rdx
0x180089a35  mov     r15, [r13+0]
0x180089a39  mov     r12, [r13+8]
0x180089a3d  sub     r15, rdx
0x180089a40  mov     rbx, [rsp+0F8h+var_C0]
0x180089a45  sub     r12, rdx
0x180089a48  movsxd  rcx, edi
0x180089a4b  mov     rdi, [r13+10h]
0x180089a4f  mov     r13, [rsp+0F8h+var_B8]
0x180089a54  sub     rdi, rdx
0x180089a57  mov     [rsp+0F8h+var_D4], ax
0x180089a5c  lea     rax, [rcx+r9]
0x180089a60  lea     r8, [rdx+rax*2]
0x180089a64  lea     rax, [rcx+rcx]
0x180089a68  sub     r11, rax
0x180089a6b  sub     r11, rdx
0x180089a6e  sub     r10, r9
0x180089a71  movzx   r9d, [rsp+0F8h+var_D4]
0x180089a77  nop     word ptr [rax+rax+00000000h]
0x180089a80  mov     rax, [rsp+0F8h+var_B0]
0x180089a85  movzx   edx, word ptr [r15+r8]
0x180089a8a  movzx   ecx, word ptr [r12+r8]
0x180089a8f  lea     r8, [r8+2]
0x180089a93  movzx   eax, word ptr [rax]
0x180089a96  imul    edx, eax
0x180089a99  mov     rax, [rsp+0F8h+var_A8]
0x180089a9e  movzx   eax, word ptr [rax]
0x180089aa1  imul    ecx, eax
0x180089aa4  mov     rax, [rsp+0F8h+var_A0]
0x180089aa9  movzx   eax, word ptr [rax]
0x180089aac  add     dx, cx
0x180089aaf  movzx   ecx, word ptr [r14+r8-2]
0x180089ab5  imul    ecx, eax
0x180089ab8  mov     rax, [rsp+0F8h+var_98]
0x180089abd  movzx   eax, word ptr [rax]
0x180089ac0  add     dx, cx
0x180089ac3  movzx   ecx, word ptr [r8+rbp-2]
0x180089ac9  imul    ecx, eax
0x180089acc  movzx   eax, word ptr [rbx]
0x180089acf  add     dx, cx
0x180089ad2  movzx   ecx, word ptr [rsi+r8-2]
0x180089ad8  imul    ecx, eax
0x180089adb  movzx   eax, word ptr [r13+0]
0x180089ae0  add     dx, cx
0x180089ae3  movzx   ecx, word ptr [rdi+r8-2]
0x180089ae9  imul    ecx, r9d
0x180089aed  add     dx, cx
0x180089af0  movzx   ecx, word ptr [r8-2]
0x180089af5  imul    ecx, eax
0x180089af8  add     dx, cx
0x180089afb  shr     dx, 6
0x180089aff  mov     [r11+r8-2], dx
0x180089b05  sub     r10, 1
0x180089b09  jnz     loc_180089A80
0x180089b0f  mov     ebx, [rsp+0F8h+var_D8]
0x180089b13  mov     r13, [rsp+0F8h+var_90]
0x180089b18  mov     edi, [rsp+0F8h+var_D0]
0x180089b1c  mov     r10, [rsp+0F8h+var_80]
0x180089b21  lea     r9, cs:180000000h
0x180089b28  lea     eax, [rbx+1]
0x180089b2b  xor     ebx, ebx
0x180089b2d  cmp     eax, 2
0x180089b30  cmovl   ebx, eax
0x180089b33  movzx   eax, [rsp+0F8h+var_58]
0x180089b3b  movsxd  rdx, ebx
0x180089b3e  shl     rdx, 6
0x180089b42  mov     [rsp+0F8h+var_D8], ebx
0x180089b46  movzx   r8d, word ptr [rdx+r9+0DE840h]
0x180089b4f  movzx   ecx, word ptr [rdx+r9+0DE846h]
0x180089b58  imul    r8d, eax
0x180089b5c  movzx   eax, [rsp+0F8h+var_52]
0x180089b64  imul    ecx, eax
0x180089b67  movzx   eax, [rsp+0F8h+var_4C]
0x180089b6f  add     r8w, cx
0x180089b73  movzx   ecx, word ptr [rdx+r9+0DE84Ch]
0x180089b7c  imul    ecx, eax
0x180089b7f  movzx   eax, [rsp+0F8h+var_54]
0x180089b87  add     r8w, cx
0x180089b8b  movzx   ecx, word ptr [rdx+r9+0DE844h]
0x180089b94  imul    ecx, eax
0x180089b97  movzx   eax, [rsp+0F8h+var_56]
0x180089b9f  add     r8w, cx
0x180089ba3  movzx   ecx, word ptr [rdx+r9+0DE842h]
0x180089bac  imul    ecx, eax
0x180089baf  movzx   eax, [rsp+0F8h+var_4E]
0x180089bb7  add     r8w, cx
0x180089bbb  movzx   ecx, word ptr [rdx+r9+0DE84Ah]
0x180089bc4  imul    ecx, eax
0x180089bc7  movzx   eax, [rsp+0F8h+var_50]
0x180089bcf  add     r8w, cx
0x180089bd3  movzx   ecx, word ptr [rdx+r9+0DE848h]
0x180089bdc  imul    ecx, eax
0x180089bdf  mov     rax, [rsp+0F8h+var_60]
0x180089be7  add     r8w, cx
0x180089beb  shr     r8w, 8
0x180089bf0  mov     [r10+rax], r8b
0x180089bf4  inc     r10
0x180089bf7  mov     r8, [rsp+0F8h+var_88]
0x180089bfc  mov     rax, [rsp+0F8h+var_78]
0x180089c04  inc     r8d
0x180089c07  mov     [rsp+0F8h+var_88], r8
0x180089c0c  mov     [rsp+0F8h+var_80], r10
0x180089c11  cmp     r8d, [rax+0Ch]
0x180089c15  jl      loc_1800899B0
0x180089c1b  mov     rcx, [rsp+0F8h+var_70]
0x180089c23  lea     rdx, [rsp+0F8h+var_68]
  ... truncated ...
```
