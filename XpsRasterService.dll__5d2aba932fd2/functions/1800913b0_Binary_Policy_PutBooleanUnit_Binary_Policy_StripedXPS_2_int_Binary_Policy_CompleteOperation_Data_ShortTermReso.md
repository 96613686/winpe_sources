# Binary::Policy::PutBooleanUnit<Binary::Policy::StripedXPS,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[5],int)

- ea: `0x1800913b0`
- end: `0x180091816`
- name: `??$PutBooleanUnit@VStripedXPS@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY04$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1126`
- prototype: `__int64 __fastcall(int, __int64, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008f800`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x1800913b0`

## pseudocode

```c
__int64 __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::StripedXPS,2>(
        int a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5)
{
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // r10
  __int64 v11; // r11
  __int16 v12; // r12
  __int64 v13; // rsi
  __int64 v14; // r14
  __int16 v15; // r13
  char *v16; // r15
  __int16 v17; // dx
  __int16 v18; // cx
  _QWORD *v19; // rbp
  int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r10
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // ecx
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rdi
  __int64 v29; // rcx
  __int64 v30; // rsi
  __int16 v31; // r14
  __int64 v32; // rbx
  __int64 v33; // rbp
  __int16 v34; // r15
  __int16 v35; // r12
  __int16 v36; // r13
  __int16 *v37; // r8
  char *v38; // r11
  __int64 v39; // r10
  __int16 v40; // r9
  __int16 v41; // dx
  __int16 v42; // cx
  __int16 v43; // ax
  int v44; // eax
  __int64 v45; // rdx
  int v47; // [rsp+24h] [rbp-C4h]
  int v48; // [rsp+28h] [rbp-C0h]
  __int16 *v49; // [rsp+30h] [rbp-B8h]
  int v51; // [rsp+40h] [rbp-A8h]
  __int64 v52; // [rsp+48h] [rbp-A0h]
  char *v54; // [rsp+58h] [rbp-90h]
  __int16 *v55; // [rsp+60h] [rbp-88h]
  __int16 *v56; // [rsp+68h] [rbp-80h]
  char *v57; // [rsp+70h] [rbp-78h]
  __int128 v59; // [rsp+80h] [rbp-68h] BYREF
  __int16 v60; // [rsp+90h] [rbp-58h] BYREF
  __int16 v61; // [rsp+92h] [rbp-56h]
  __int16 v62; // [rsp+94h] [rbp-54h]
  __int16 v63; // [rsp+96h] [rbp-52h]
  __int16 v64; // [rsp+98h] [rbp-50h]

  v59 = 0;
  Binary::Policy::CompleteOperation::TargetDigitalRegion(a2, &v59);
  v7 = a4[3];
  v8 = 5;
  if ( a1 )
    a1 = 0;
  v9 = (__int64)a5 << 6;
  v10 = a4[2] - v7;
  v48 = a1;
  v54 = &byte_1800DE684[v9];
  v11 = a4[4] - v7;
  v57 = &Binary::Policy::StripedXPS::OddOperation[v9];
  v12 = *(_WORD *)&byte_1800DE684[v9];
  v13 = *a4 - v7;
  v56 = (__int16 *)((char *)&word_1800DE682 + v9);
  v14 = a4[1] - v7;
  v55 = (__int16 *)((char *)&word_1800DE686 + v9);
  v15 = *(__int16 *)((char *)&word_1800DE686 + v9);
  v49 = (__int16 *)((char *)qword_1800DE688 + v9);
  v16 = (char *)&v60 - v7;
  do
  {
    v17 = *(_WORD *)(v7 + v14);
    v18 = *(_WORD *)(v7 + v13);
    v7 += 2;
    *(_WORD *)&v16[v7 - 2] = (unsigned __int16)(*(_WORD *)(v7 - 2) * v15
                                              + v12 * *(_WORD *)(v7 + v10 - 2)
                                              + *(_WORD *)((char *)qword_1800DE688 + v9) * *(_WORD *)(v7 + v11 - 2)
                                              + *(_WORD *)&Binary::Policy::StripedXPS::OddOperation[v9] * v18
                                              + *(__int16 *)((char *)&word_1800DE682 + v9) * v17) >> 6;
    --v8;
  }
  while ( v8 );
  v19 = a4;
  v20 = 0;
  v21 = (__int64)a1 << 6;
  **((_BYTE **)&v59 + 1) = (unsigned __int16)(v60 * *(_WORD *)&Binary::Policy::StripedXPS::OddOperation[v21]
                                            + v62 * *(_WORD *)&byte_1800DE684[v21]
                                            + v63 * *(__int16 *)((char *)&word_1800DE686 + v21)
                                            + v64 * *(_WORD *)((char *)qword_1800DE688 + v21)
                                            + v61 * *(__int16 *)((char *)&word_1800DE682 + v21)) >> 8;
  v51 = 1;
  if ( *(int *)(a3 + 12) > 1 )
  {
    v22 = 1;
    v52 = 1;
    do
    {
      v23 = Binary::Policy::StripedXPS::GlobalCase[a1];
      v24 = 0;
      v20 += v23;
      v25 = 5 - v23;
      v47 = v20;
      v26 = 5 - (int)v23;
      if ( 5 - (int)v23 > 0 )
      {
        do
        {
          *(&v60 + v24) = *(&v60 + v23 + v24);
          ++v24;
        }
        while ( v24 < v25 );
      }
      if ( v25 < 5LL )
      {
        v27 = v19[3];
        v28 = v19[4] - v27;
        v29 = v20;
        v30 = v19[1] - v27;
        v31 = *(_WORD *)v54;
        v32 = v19[2] - v27;
        v33 = *v19 - v27;
        v34 = *v55;
        v35 = *v49;
        v36 = *v56;
        v37 = (__int16 *)(v27 + 2 * (v26 + v29));
        v38 = (char *)&v60 - v27 + -2 * v29;
        v39 = 5 - v26;
        v40 = *(_WORD *)v57;
        do
        {
          v41 = *(__int16 *)((char *)v37 + v30);
          v42 = *(__int16 *)((char *)v37 + v33);
          v43 = *v37++;
          *(__int16 *)((char *)v37 + (_QWORD)v38 - 2) = (unsigned __int16)(v43 * v34
                                                                         + v31 * *(__int16 *)((char *)v37 + v32 - 2)
                                                                         + v35 * *(__int16 *)((char *)v37 + v28 - 2)
                                                                         + v40 * v42
                                                                         + v36 * v41) >> 6;
          --v39;
        }
        while ( v39 );
        v19 = a4;
        v20 = v47;
        a1 = v48;
        v22 = v52;
      }
      v44 = a1 + 1;
      a1 = 0;
      if ( v44 < 1 )
        a1 = v44;
      v45 = (__int64)a1 << 6;
      v48 = a1;
      *(_BYTE *)(v22 + *((_QWORD *)&v59 + 1)) = (unsigned __int16)(v60
                                                                 * *(_WORD *)&Binary::Policy::StripedXPS::OddOperation[v45]
                                                                 + v62 * *(_WORD *)&byte_1800DE684[v45]
                                                                 + v63 * *(__int16 *)((char *)&word_1800DE686 + v45)
                                                                 + v64 * *(_WORD *)((char *)qword_1800DE688 + v45)
                                                                 + v61 * *(__int16 *)((char *)&word_1800DE682 + v45)) >> 8;
      ++v22;
      ++v51;
      v52 = v22;
    }
    while ( v51 < *(_DWORD *)(a3 + 12) );
  }
  return Binary::Policy::CompleteOperation::MoveVirtualAddition(a2, &v59);
}

```

## disassembly

```asm
0x1800913b0  mov     r11, rsp
0x1800913b3  mov     [r11+8], rbx
0x1800913b7  push    rbp
0x1800913b8  push    rsi
0x1800913b9  push    rdi
0x1800913ba  push    r12
0x1800913bc  push    r13
0x1800913be  push    r14
0x1800913c0  push    r15
0x1800913c2  sub     rsp, 0B0h
0x1800913c9  mov     rax, cs:__security_cookie
0x1800913d0  xor     rax, rsp
0x1800913d3  mov     [rsp+0E8h+var_48], rax
0x1800913db  mov     rbp, r9
0x1800913de  mov     [rsp+0E8h+var_B0], r9
0x1800913e3  mov     r9, rdx
0x1800913e6  mov     [rsp+0E8h+var_70], rdx
0x1800913eb  mov     edi, ecx
0x1800913ed  mov     [rsp+0E8h+var_98], r8
0x1800913f2  xorps   xmm0, xmm0
0x1800913f5  lea     rdx, [r11-68h]
0x1800913f9  xor     esi, esi
0x1800913fb  mov     rcx, r9
0x1800913fe  mov     [rsp+0E8h+var_C4], esi
0x180091402  movups  xmmword ptr [r11-68h], xmm0
0x180091407  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18009140c  mov     r8, [rbp+18h]
0x180091410  lea     rdx, cs:180000000h
0x180091417  mov     r10, [rbp+10h]
0x18009141b  lea     rcx, rva byte_1800DE684[rdx]
0x180091422  mov     r11, [rbp+20h]
0x180091426  lea     rbx, rva word_1800DE682[rdx]
0x18009142d  mov     r14, [rbp+8]
0x180091431  lea     r15, [rsp+0E8h+var_58]
0x180091439  movsxd  rax, [rsp+0E8h+arg_20]
0x180091441  test    edi, edi
0x180091443  mov     r9d, 5
0x180091449  cmovnz  edi, esi
0x18009144c  mov     rsi, [rbp+0]
0x180091450  shl     rax, 6
0x180091454  sub     r10, r8
0x180091457  add     rcx, rax
0x18009145a  mov     [rsp+0E8h+var_C0], edi
0x18009145e  mov     [rsp+0E8h+var_90], rcx
0x180091463  lea     rdi, rva ?OddOperation@StripedXPS@Policy@Binary@@2V?$OneContext@V?$OneContext@G$04$00$0A@$09@Data@@$00$00$0A@$0EA@@Data@@B[rdx]; Data::OneContext<Data::OneContext<ushort,5,1,0,10>,1,1,0,64> const Binary::Policy::StripedXPS::OddOperation ...
0x18009146a  add     rdi, rax
0x18009146d  add     rbx, rax
0x180091470  sub     r11, r8
0x180091473  mov     [rsp+0E8h+var_78], rdi
0x180091478  movzx   r12d, word ptr [rcx]
0x18009147c  sub     rsi, r8
0x18009147f  lea     rcx, rva word_1800DE686[rdx]
0x180091486  mov     [rsp+0E8h+var_80], rbx
0x18009148b  add     rcx, rax
0x18009148e  sub     r14, r8
0x180091491  mov     [rsp+0E8h+var_88], rcx
0x180091496  movzx   r13d, word ptr [rcx]
0x18009149a  lea     rcx, rva qword_1800DE688[rdx]
0x1800914a1  add     rcx, rax
0x1800914a4  mov     [rsp+0E8h+var_B8], rcx
0x1800914a9  sub     r15, r8
0x1800914ac  mov     rbp, rcx
0x1800914af  nop
0x1800914b0  movzx   eax, word ptr [rbx]
0x1800914b3  movzx   edx, word ptr [r8+r14]
0x1800914b8  movzx   ecx, word ptr [r8+rsi]
0x1800914bd  lea     r8, [r8+2]
0x1800914c1  imul    edx, eax
0x1800914c4  movzx   eax, word ptr [rdi]
0x1800914c7  imul    ecx, eax
0x1800914ca  movzx   eax, word ptr [rbp+0]
0x1800914ce  add     dx, cx
0x1800914d1  movzx   ecx, word ptr [r8+r11-2]
0x1800914d7  imul    ecx, eax
0x1800914da  movzx   eax, word ptr [r8-2]
0x1800914df  add     dx, cx
0x1800914e2  movzx   ecx, word ptr [r8+r10-2]
0x1800914e8  imul    ecx, r12d
0x1800914ec  add     dx, cx
0x1800914ef  mov     ecx, r13d
0x1800914f2  imul    ecx, eax
0x1800914f5  add     dx, cx
0x1800914f8  shr     dx, 6
0x1800914fc  mov     [r8+r15-2], dx
0x180091502  sub     r9, 1
0x180091506  jnz     short loc_1800914B0
0x180091508  movzx   eax, [rsp+0E8h+var_56]
0x180091510  lea     r9, cs:180000000h
0x180091517  movsxd  rdi, [rsp+0E8h+var_C0]
0x18009151c  mov     rbp, [rsp+0E8h+var_B0]
0x180091521  mov     rdx, rdi
0x180091524  mov     ebx, [rsp+0E8h+var_C4]
0x180091528  shl     rdx, 6
0x18009152c  movzx   r8d, word ptr [rdx+r9+0DE682h]
0x180091535  movzx   ecx, word ptr [rdx+r9+0DE688h]
0x18009153e  imul    r8d, eax
0x180091542  movzx   eax, [rsp+0E8h+var_50]
0x18009154a  imul    ecx, eax
0x18009154d  movzx   eax, [rsp+0E8h+var_52]
0x180091555  add     r8w, cx
0x180091559  movzx   ecx, word ptr [rdx+r9+0DE686h]
0x180091562  imul    ecx, eax
0x180091565  movzx   eax, [rsp+0E8h+var_54]
0x18009156d  add     r8w, cx
0x180091571  movzx   ecx, word ptr [rdx+r9+0DE684h]
0x18009157a  imul    ecx, eax
0x18009157d  movzx   eax, [rsp+0E8h+var_58]
0x180091585  add     r8w, cx
0x180091589  movzx   ecx, word ptr [rdx+r9+0DE680h]
0x180091592  imul    ecx, eax
0x180091595  mov     rax, [rsp+0E8h+var_60]
0x18009159d  add     r8w, cx
0x1800915a1  shr     r8w, 8
0x1800915a6  mov     [rax], r8b
0x1800915a9  mov     r8d, 1
0x1800915af  mov     rax, [rsp+0E8h+var_98]
0x1800915b4  mov     [rsp+0E8h+var_A8], r8
0x1800915b9  cmp     [rax+0Ch], r8d
0x1800915bd  jle     loc_1800917D9
0x1800915c3  mov     r10d, r8d
0x1800915c6  mov     [rsp+0E8h+var_A0], r8
0x1800915cb  nop     dword ptr [rax+rax+00h]
0x1800915d0  movsxd  rax, edi
0x1800915d3  mov     ecx, 5
0x1800915d8  movsxd  rdx, ds:rva ?GlobalCase@StripedXPS@Policy@Binary@@2V?$StripedCategory@H$00@Data@@B[r9+rax*4]; Data::StripedCategory<int,1> const Binary::Policy::StripedXPS::GlobalCase ...
0x1800915e0  xor     eax, eax
0x1800915e2  add     ebx, edx
0x1800915e4  sub     ecx, edx
0x1800915e6  mov     [rsp+0E8h+var_C4], ebx
0x1800915ea  movsxd  r9, ecx
0x1800915ed  test    ecx, ecx
0x1800915ef  jle     short loc_18009161C
0x1800915f1  lea     r8, [rdx+rdx]
0x1800915f5  nop     word ptr [rax+rax+00000000h]
0x180091600  lea     rcx, [r8+rax*2]
0x180091604  movzx   edx, [rsp+rcx+0E8h+var_58]
0x18009160c  mov     [rsp+rax*2+0E8h+var_58], dx
0x180091614  inc     rax
0x180091617  cmp     rax, r9
0x18009161a  jl      short loc_180091600
0x18009161c  cmp     r9, 5
0x180091620  jge     loc_180091712
0x180091626  mov     rdx, [rbp+18h]
0x18009162a  lea     r11, [rsp+0E8h+var_58]
0x180091632  mov     rax, [rsp+0E8h+var_90]
0x180091637  mov     r10d, 5
0x18009163d  mov     rdi, [rbp+20h]
0x180091641  mov     rsi, [rbp+8]
0x180091645  sub     rdi, rdx
0x180091648  movsxd  rcx, ebx
0x18009164b  sub     rsi, rdx
0x18009164e  movzx   r14d, word ptr [rax]
0x180091652  mov     rbx, [rbp+10h]
0x180091656  mov     rax, [rsp+0E8h+var_88]
0x18009165b  sub     rbx, rdx
0x18009165e  mov     rbp, [rbp+0]
0x180091662  sub     rbp, rdx
0x180091665  movzx   r15d, word ptr [rax]
0x180091669  mov     rax, [rsp+0E8h+var_B8]
0x18009166e  movzx   r12d, word ptr [rax]
0x180091672  mov     rax, [rsp+0E8h+var_80]
0x180091677  movzx   r13d, word ptr [rax]
0x18009167b  mov     rax, [rsp+0E8h+var_78]
0x180091680  movzx   eax, word ptr [rax]
0x180091683  mov     [rsp+0E8h+var_C8], ax
0x180091688  lea     rax, [r9+rcx]
0x18009168c  lea     r8, [rdx+rax*2]
0x180091690  lea     rax, [rcx+rcx]
0x180091694  sub     r11, rax
0x180091697  sub     r11, rdx
0x18009169a  sub     r10, r9
0x18009169d  movzx   r9d, [rsp+0E8h+var_C8]
0x1800916a3  nop     dword ptr [rax+00h]
0x1800916a7  nop     word ptr [rax+rax+00000000h]
0x1800916b0  movzx   edx, word ptr [r8+rsi]
0x1800916b5  movzx   ecx, word ptr [r8+rbp]
0x1800916ba  movzx   eax, word ptr [r8]
0x1800916be  lea     r8, [r8+2]
0x1800916c2  imul    ecx, r9d
0x1800916c6  imul    edx, r13d
0x1800916ca  add     dx, cx
0x1800916cd  movzx   ecx, word ptr [r8+rdi-2]
0x1800916d3  imul    ecx, r12d
0x1800916d7  add     dx, cx
0x1800916da  movzx   ecx, word ptr [r8+rbx-2]
0x1800916e0  imul    ecx, r14d
0x1800916e4  add     dx, cx
0x1800916e7  mov     ecx, r15d
0x1800916ea  imul    ecx, eax
0x1800916ed  add     dx, cx
0x1800916f0  shr     dx, 6
0x1800916f4  mov     [r11+r8-2], dx
0x1800916fa  sub     r10, 1
0x1800916fe  jnz     short loc_1800916B0
0x180091700  mov     rbp, [rsp+0E8h+var_B0]
0x180091705  mov     ebx, [rsp+0E8h+var_C4]
0x180091709  mov     edi, [rsp+0E8h+var_C0]
0x18009170d  mov     r10, [rsp+0E8h+var_A0]
0x180091712  lea     eax, [rdi+1]
0x180091715  xor     edi, edi
0x180091717  cmp     eax, 1
0x18009171a  lea     r9, cs:180000000h
0x180091721  cmovl   edi, eax
0x180091724  movzx   eax, [rsp+0E8h+var_56]
0x18009172c  movsxd  rdx, edi
0x18009172f  shl     rdx, 6
0x180091733  mov     [rsp+0E8h+var_C0], edi
0x180091737  movzx   r8d, word ptr [rdx+r9+0DE682h]
0x180091740  movzx   ecx, word ptr [rdx+r9+0DE688h]
0x180091749  imul    r8d, eax
0x18009174d  movzx   eax, [rsp+0E8h+var_50]
0x180091755  imul    ecx, eax
0x180091758  movzx   eax, [rsp+0E8h+var_52]
0x180091760  add     r8w, cx
0x180091764  movzx   ecx, word ptr [rdx+r9+0DE686h]
0x18009176d  imul    ecx, eax
0x180091770  movzx   eax, [rsp+0E8h+var_54]
0x180091778  add     r8w, cx
0x18009177c  movzx   ecx, word ptr [rdx+r9+0DE684h]
0x180091785  imul    ecx, eax
0x180091788  movzx   eax, [rsp+0E8h+var_58]
0x180091790  add     r8w, cx
0x180091794  movzx   ecx, word ptr [rdx+r9+0DE680h]
0x18009179d  imul    ecx, eax
0x1800917a0  mov     rax, [rsp+0E8h+var_60]
0x1800917a8  add     r8w, cx
0x1800917ac  shr     r8w, 8
0x1800917b1  mov     [r10+rax], r8b
0x1800917b5  inc     r10
0x1800917b8  mov     r8, [rsp+0E8h+var_A8]
0x1800917bd  mov     rax, [rsp+0E8h+var_98]
0x1800917c2  inc     r8d
0x1800917c5  mov     [rsp+0E8h+var_A8], r8
0x1800917ca  mov     [rsp+0E8h+var_A0], r10
0x1800917cf  cmp     r8d, [rax+0Ch]
0x1800917d3  jl      loc_1800915D0
0x1800917d9  mov     rcx, [rsp+0E8h+var_70]
0x1800917de  lea     rdx, [rsp+0E8h+var_68]
0x1800917e6  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x1800917eb  mov     rcx, [rsp+0E8h+var_48]
0x1800917f3  xor     rcx, rsp; StackCookie
0x1800917f6  call    __security_check_cookie
0x1800917fb  mov     rbx, [rsp+0E8h+arg_0]
0x180091803  add     rsp, 0B0h
0x18009180a  pop     r15
0x18009180c  pop     r14
0x18009180e  pop     r13
0x180091810  pop     r12
0x180091812  pop     rdi
0x180091813  pop     rsi
0x180091814  pop     rbp
0x180091815  retn
```
