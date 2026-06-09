# Binary::Policy::MarkQuickestList<Binary::Policy::NewMode,3>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x1800883a0`
- end: `0x180088694`
- name: `??$MarkQuickestList@VNewMode@Policy@Binary@@$02@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `756`
- prototype: `char __fastcall(_DWORD *, __int64, __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008ca80`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x1800883a0`
- `0x1800896c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::NewMode,3>(
        _DWORD *a1,
        __int64 a2,
        __int64 *a3,
        int a4,
        __int64 a5)
{
  __int64 v10; // r14
  bool v11; // zf
  int v12; // edi
  int *v13; // rax
  char v14; // cl
  __int64 v15; // rcx
  int v16; // edi
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdi
  int v20; // esi
  __int64 v22; // r9
  int v25; // edx
  __int64 v26; // rcx
  int v27; // edx
  __int64 v28; // rcx
  int v29; // edx
  __int64 v30; // rcx
  int v31; // edx
  __int64 v32; // rcx
  int v33; // edx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v36; // ecx
  int v37; // r8d
  int v38; // ecx
  bool v39; // sf
  int v41; // [rsp+30h] [rbp-61h] BYREF
  char v42; // [rsp+34h] [rbp-5Dh]
  int v43; // [rsp+38h] [rbp-59h] BYREF
  char v44; // [rsp+3Ch] [rbp-55h]
  _BYTE v45[8]; // [rsp+40h] [rbp-51h] BYREF
  __m256 v46; // [rsp+48h] [rbp-49h]
  _QWORD v47[7]; // [rsp+68h] [rbp-29h] BYREF

  _RBX = a2;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v41, 7, 2, 2, a1[1] + 3);
  LODWORD(v10) = 0;
  v44 = 1;
  v11 = v42 == 0;
  v12 = 0;
  v42 = 1;
  if ( !v11 )
    v12 = v41;
  v43 = v12;
  v41 = 2;
  v13 = (int *)Data::FillClearSkill(v45, &v43, &v41);
  v14 = *((_BYTE *)v13 + 4);
  if ( v14 )
  {
    v15 = 2LL * *v13;
    if ( (unsigned __int64)(v15 + 0x80000000LL) > 0xFFFFFFFF )
    {
      v14 = 0;
    }
    else
    {
      v10 = v12 - (__int64)(int)v15;
      if ( (unsigned __int64)(v10 + 0x80000000LL) > 0xFFFFFFFF )
      {
        v14 = 0;
        v16 = 0;
        LODWORD(v10) = 0;
        goto LABEL_10;
      }
      v14 = 1;
    }
  }
  v16 = 0;
LABEL_10:
  if ( !v14 )
    LODWORD(v10) = 0;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v43, 7, 2, 2, *a1 + 3);
  v11 = v44 == 0;
  v44 = 1;
  if ( !v11 )
    v16 = v43;
  v41 = v16;
  v43 = 2;
  v42 = 1;
  v17 = Data::FillClearSkill(v45, &v41, &v43);
  if ( *(_BYTE *)(v17 + 4)
    && (v18 = 2LL * *(int *)v17, LOBYTE(v17) = 2 * *(_DWORD *)v17, (unsigned __int64)(v18 + 0x80000000LL) <= 0xFFFFFFFF)
    && ((v19 = v16 - (__int64)(int)v18, (unsigned __int64)(v19 + 0x80000000LL) > 0xFFFFFFFF)
      ? (LOBYTE(v17) = 0, LODWORD(v19) = 0)
      : (LOBYTE(v17) = 1),
        (_BYTE)v17) )
  {
    if ( (unsigned int)v19 > 1 )
      LODWORD(v19) = (int)v19 % 2 + ((int)v19 % 2 < 0 ? 2 : 0);
  }
  else
  {
    LODWORD(v19) = 0;
  }
  v20 = 0;
  while ( v20 < *(_DWORD *)(a5 + 8) )
  {
    __asm { vmovups ymm0, ymmword ptr [rbx] }
    v22 = *a3;
    __asm { vmovups [rbp+4Fh+var_98], ymm0 }
    __asm
    {
      vpextrq rcx, xmm0, 1
      vmovd   edx, xmm0
    }
    v25 = _EDX + 1;
    v47[0] = v22 + 2 * _RCX;
    if ( v25 < SLODWORD(v46.m256_f32[6]) )
    {
      v26 = *(_QWORD *)&v46.m256_f32[4] + _RCX;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v27 = v25 + 1;
    v47[1] = v22 + 2 * v26;
    if ( v27 < SLODWORD(v46.m256_f32[6]) )
    {
      v28 = *(_QWORD *)&v46.m256_f32[4] + v26;
    }
    else
    {
      v27 = 0;
      v28 = 0;
    }
    v29 = v27 + 1;
    v47[2] = v22 + 2 * v28;
    if ( v29 < SLODWORD(v46.m256_f32[6]) )
    {
      v30 = *(_QWORD *)&v46.m256_f32[4] + v28;
    }
    else
    {
      v29 = 0;
      v30 = 0;
    }
    v31 = v29 + 1;
    v47[3] = v22 + 2 * v30;
    if ( v31 < SLODWORD(v46.m256_f32[6]) )
    {
      v32 = *(_QWORD *)&v46.m256_f32[4] + v30;
    }
    else
    {
      v31 = 0;
      v32 = 0;
    }
    v33 = v31 + 1;
    v47[4] = v22 + 2 * v32;
    if ( v33 < SLODWORD(v46.m256_f32[6]) )
    {
      v34 = *(_QWORD *)&v46.m256_f32[4] + v32;
    }
    else
    {
      v33 = 0;
      v34 = 0;
    }
    v47[5] = v22 + 2 * v34;
    if ( v33 + 1 < SLODWORD(v46.m256_f32[6]) )
      v35 = *(_QWORD *)&v46.m256_f32[4] + v34;
    else
      v35 = 0;
    v47[6] = v22 + 2 * v35;
    __asm { vzeroupper }
    Binary::Policy::PutBooleanUnit<Binary::Policy::NewMode,3>(v10, a4, a5, (unsigned int)v47, v19);
    LOBYTE(v17) = v19;
    v36 = 0;
    if ( Binary::Policy::NewMode::GlobalCase[(int)v19] > 0 )
    {
      v37 = *(_DWORD *)(_RBX + 24);
      do
      {
        if ( ++*(_DWORD *)_RBX < v37 )
        {
          v17 = *(_QWORD *)(_RBX + 16);
          *(_QWORD *)(_RBX + 8) += v17;
        }
        else
        {
          *(_DWORD *)_RBX = 0;
          *(_QWORD *)(_RBX + 8) = 0;
        }
        ++v36;
      }
      while ( v36 < Binary::Policy::NewMode::GlobalCase[(int)v19] );
    }
    v38 = v19 + 1;
    ++v20;
    v39 = (int)v19 - 1 < 0;
    LODWORD(v19) = 0;
    if ( v39 != __OFSUB__(v38, 2) )
      LODWORD(v19) = v38;
  }
  return v17;
}

```

## disassembly

```asm
0x1800883a0  mov     [rsp-8+arg_0], rbx
0x1800883a5  push    rbp
0x1800883a6  push    rsi
0x1800883a7  push    rdi
0x1800883a8  push    r12
0x1800883aa  push    r13
0x1800883ac  push    r14
0x1800883ae  push    r15
0x1800883b0  lea     rbp, [rsp-1Fh]
0x1800883b5  sub     rsp, 0B0h
0x1800883bc  mov     rax, cs:__security_cookie
0x1800883c3  xor     rax, rsp
0x1800883c6  mov     [rbp+4Fh+var_40], rax
0x1800883ca  mov     eax, [rcx+4]
0x1800883cd  mov     r12, r9
0x1800883d0  mov     r15, [rbp+4Fh+arg_20]
0x1800883d4  mov     r9d, 2
0x1800883da  add     eax, 3
0x1800883dd  mov     r13, r8
0x1800883e0  mov     rbx, rdx
0x1800883e3  mov     [rsp+0E0h+var_C0], eax
0x1800883e7  mov     rsi, rcx
0x1800883ea  mov     r8d, r9d
0x1800883ed  mov     edx, 7
0x1800883f2  lea     rcx, [rbp+4Fh+var_B0]
0x1800883f6  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x1800883fb  xor     r14d, r14d
0x1800883fe  mov     [rbp+4Fh+var_A4], 1
0x180088402  cmp     [rbp+4Fh+var_AC], r14b
0x180088406  lea     r8, [rbp+4Fh+var_B0]
0x18008840a  mov     edi, r14d
0x18008840d  mov     [rbp+4Fh+var_AC], 1
0x180088411  cmovnz  edi, [rbp+4Fh+var_B0]
0x180088415  lea     rdx, [rbp+4Fh+var_A8]
0x180088419  lea     rcx, [rbp+4Fh+var_A0]
0x18008841d  mov     [rbp+4Fh+var_A8], edi
0x180088420  mov     [rbp+4Fh+var_B0], 2
0x180088427  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008842c  mov     edx, 80000000h
0x180088431  mov     r8d, 0FFFFFFFFh
0x180088437  movzx   ecx, byte ptr [rax+4]
0x18008843b  test    cl, cl
0x18008843d  jz      short loc_18008846F
0x18008843f  movsxd  rcx, dword ptr [rax]
0x180088442  add     rcx, rcx
0x180088445  lea     rax, [rcx+rdx]
0x180088449  cmp     rax, r8
0x18008844c  ja      short loc_18008846D
0x18008844e  movsxd  rax, ecx
0x180088451  movsxd  r14, edi
0x180088454  sub     r14, rax
0x180088457  lea     rax, [r14+rdx]
0x18008845b  cmp     rax, r8
0x18008845e  ja      short loc_180088464
0x180088460  mov     cl, 1
0x180088462  jmp     short loc_18008846F
0x180088464  xor     cl, cl
0x180088466  xor     edi, edi
0x180088468  mov     r14d, edi
0x18008846b  jmp     short loc_180088471
0x18008846d  xor     cl, cl
0x18008846f  xor     edi, edi
0x180088471  mov     eax, [rsi]
0x180088473  test    cl, cl
0x180088475  mov     r9d, 2
0x18008847b  lea     rcx, [rbp+4Fh+var_A8]
0x18008847f  cmovz   r14d, edi
0x180088483  mov     edx, 7
0x180088488  add     eax, 3
0x18008848b  mov     r8d, r9d
0x18008848e  mov     [rsp+0E0h+var_C0], eax
0x180088492  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180088497  cmp     [rbp+4Fh+var_A4], 0
0x18008849b  lea     r8, [rbp+4Fh+var_A8]
0x18008849f  lea     rdx, [rbp+4Fh+var_B0]
0x1800884a3  mov     [rbp+4Fh+var_A4], 1
0x1800884a7  cmovnz  edi, [rbp+4Fh+var_A8]
0x1800884ab  lea     rcx, [rbp+4Fh+var_A0]
0x1800884af  mov     [rbp+4Fh+var_B0], edi
0x1800884b2  mov     [rbp+4Fh+var_A8], 2
0x1800884b9  mov     [rbp+4Fh+var_AC], 1
0x1800884bd  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x1800884c2  cmp     byte ptr [rax+4], 0
0x1800884c6  jz      short loc_180088524
0x1800884c8  movsxd  rcx, dword ptr [rax]
0x1800884cb  mov     edx, 80000000h
0x1800884d0  add     rcx, rcx
0x1800884d3  mov     r8d, 0FFFFFFFFh
0x1800884d9  lea     rax, [rcx+rdx]
0x1800884dd  cmp     rax, r8
0x1800884e0  ja      short loc_180088524
0x1800884e2  movsxd  rax, ecx
0x1800884e5  movsxd  rdi, edi
0x1800884e8  sub     rdi, rax
0x1800884eb  lea     rax, [rdi+rdx]
0x1800884ef  cmp     rax, r8
0x1800884f2  ja      short loc_1800884FB
0x1800884f4  mov     al, 1
0x1800884f6  xor     r11d, r11d
0x1800884f9  jmp     short loc_180088503
0x1800884fb  xor     al, al
0x1800884fd  xor     r11d, r11d
0x180088500  mov     edi, r11d
0x180088503  test    al, al
0x180088505  jz      short loc_180088527
0x180088507  cmp     edi, 1
0x18008850a  jbe     short loc_18008852A
0x18008850c  and     edi, 80000001h
0x180088512  jge     short loc_18008851B
0x180088514  dec     edi
0x180088516  or      edi, 0FFFFFFFEh
0x180088519  inc     edi
0x18008851b  test    edi, edi
0x18008851d  jns     short loc_18008852A
0x18008851f  add     edi, 2
0x180088522  jmp     short loc_18008852A
0x180088524  xor     r11d, r11d
0x180088527  mov     edi, r11d
0x18008852a  cmp     dword ptr [r15+8], 0
0x18008852f  mov     esi, r11d
0x180088532  jle     loc_18008866D
0x180088538  nop     dword ptr [rax+rax+00000000h]
0x180088540  vmovups ymm0, ymmword ptr [rbx]
0x180088544  mov     r9, [r13+0]
0x180088548  vmovups [rbp+4Fh+var_98], ymm0
0x18008854d  mov     r10d, dword ptr [rbp+4Fh+var_98+18h]
0x180088551  mov     r8, qword ptr [rbp+4Fh+var_98+10h]
0x180088555  vpextrq rcx, xmm0, 1
0x18008855b  vmovd   edx, xmm0
0x18008855f  inc     edx
0x180088561  lea     rax, [r9+rcx*2]
0x180088565  mov     [rbp+4Fh+var_78], rax
0x180088569  cmp     edx, r10d
0x18008856c  jl      short loc_180088576
0x18008856e  mov     edx, r11d
0x180088571  mov     rcx, r11
0x180088574  jmp     short loc_180088579
0x180088576  add     rcx, r8
0x180088579  inc     edx
0x18008857b  lea     rax, [r9+rcx*2]
0x18008857f  mov     [rbp+4Fh+var_70], rax
0x180088583  cmp     edx, r10d
0x180088586  jl      short loc_180088590
0x180088588  mov     edx, r11d
0x18008858b  mov     rcx, r11
0x18008858e  jmp     short loc_180088593
0x180088590  add     rcx, r8
0x180088593  inc     edx
0x180088595  lea     rax, [r9+rcx*2]
0x180088599  mov     [rbp+4Fh+var_68], rax
0x18008859d  cmp     edx, r10d
0x1800885a0  jl      short loc_1800885AA
0x1800885a2  mov     edx, r11d
0x1800885a5  mov     rcx, r11
0x1800885a8  jmp     short loc_1800885AD
0x1800885aa  add     rcx, r8
0x1800885ad  inc     edx
0x1800885af  lea     rax, [r9+rcx*2]
0x1800885b3  mov     [rbp+4Fh+var_60], rax
0x1800885b7  cmp     edx, r10d
0x1800885ba  jl      short loc_1800885C4
0x1800885bc  mov     edx, r11d
0x1800885bf  mov     rcx, r11
0x1800885c2  jmp     short loc_1800885C7
0x1800885c4  add     rcx, r8
0x1800885c7  inc     edx
0x1800885c9  lea     rax, [r9+rcx*2]
0x1800885cd  mov     [rbp+4Fh+var_58], rax
0x1800885d1  cmp     edx, r10d
0x1800885d4  jl      short loc_1800885DE
0x1800885d6  mov     edx, r11d
0x1800885d9  mov     rcx, r11
0x1800885dc  jmp     short loc_1800885E1
0x1800885de  add     rcx, r8
0x1800885e1  inc     edx
0x1800885e3  lea     rax, [r9+rcx*2]
0x1800885e7  mov     [rbp+4Fh+var_50], rax
0x1800885eb  cmp     edx, r10d
0x1800885ee  jl      short loc_1800885F5
0x1800885f0  mov     rcx, r11
0x1800885f3  jmp     short loc_1800885F8
0x1800885f5  add     rcx, r8
0x1800885f8  lea     rax, [r9+rcx*2]
0x1800885fc  mov     [rsp+0E0h+var_C0], edi
0x180088600  mov     [rbp+4Fh+var_48], rax
0x180088604  lea     r9, [rbp+4Fh+var_78]
0x180088608  mov     r8, r15
0x18008860b  mov     rdx, r12
0x18008860e  mov     ecx, r14d
0x180088611  vzeroupper
0x180088614  call    ??$PutBooleanUnit@VNewMode@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY06$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::NewMode,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[7],int)
0x180088619  xor     r11d, r11d
0x18008861c  movsxd  rax, edi
0x18008861f  lea     rdx, ?GlobalCase@NewMode@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B; Data::StripedCategory<int,2> const Binary::Policy::NewMode::GlobalCase
0x180088626  mov     ecx, r11d
0x180088629  cmp     [rdx+rax*4], r11d
0x18008862d  lea     rdx, [rdx+rax*4]
0x180088631  jle     short loc_180088655
0x180088633  mov     r8d, [rbx+18h]
0x180088637  inc     dword ptr [rbx]
0x180088639  cmp     [rbx], r8d
0x18008863c  jl      short loc_180088647
0x18008863e  mov     [rbx], r11d
0x180088641  mov     [rbx+8], r11
0x180088645  jmp     short loc_18008864F
0x180088647  mov     rax, [rbx+10h]
0x18008864b  add     [rbx+8], rax
0x18008864f  inc     ecx
0x180088651  cmp     ecx, [rdx]
0x180088653  jl      short loc_180088637
0x180088655  lea     ecx, [rdi+1]
0x180088658  inc     esi
0x18008865a  cmp     ecx, 2
0x18008865d  mov     edi, r11d
0x180088660  cmovl   edi, ecx
0x180088663  cmp     esi, [r15+8]
0x180088667  jl      loc_180088540
0x18008866d  mov     rcx, [rbp+4Fh+var_40]
0x180088671  xor     rcx, rsp; StackCookie
0x180088674  call    __security_check_cookie
0x180088679  mov     rbx, [rsp+0E0h+arg_0]
0x180088681  add     rsp, 0B0h
0x180088688  pop     r15
0x18008868a  pop     r14
0x18008868c  pop     r13
0x18008868e  pop     r12
0x180088690  pop     rdi
0x180088691  pop     rsi
0x180088692  pop     rbp
0x180088693  retn
```
