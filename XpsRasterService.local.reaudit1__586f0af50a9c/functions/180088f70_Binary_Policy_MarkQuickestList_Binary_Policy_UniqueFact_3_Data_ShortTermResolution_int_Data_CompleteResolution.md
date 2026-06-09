# Binary::Policy::MarkQuickestList<Binary::Policy::UniqueFact,3>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x180088f70`
- end: `0x180089224`
- name: `??$MarkQuickestList@VUniqueFact@Policy@Binary@@$02@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008e070`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x180088f70`
- `0x18008aae0`

## pseudocode

```c
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::UniqueFact,3>(
        _DWORD *a1,
        __int64 a2,
        __int64 *a3,
        _DWORD *a4,
        _DWORD *a5)
{
  __int64 v10; // r14
  bool v11; // zf
  int v12; // edi
  int *v13; // rax
  char v14; // cl
  int v15; // edi
  __int64 v16; // rax
  __int64 v17; // rdi
  int v18; // esi
  __int64 v20; // r9
  int v23; // edx
  __int64 v24; // rcx
  int v25; // edx
  __int64 v26; // rcx
  int v27; // edx
  __int64 v28; // rcx
  int v29; // edx
  __int64 v30; // rcx
  int v31; // edx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // ecx
  int v35; // r8d
  int v36; // ecx
  bool v37; // sf
  int v39; // [rsp+30h] [rbp-61h] BYREF
  char v40; // [rsp+34h] [rbp-5Dh]
  int v41; // [rsp+38h] [rbp-59h] BYREF
  char v42; // [rsp+3Ch] [rbp-55h]
  _BYTE v43[8]; // [rsp+40h] [rbp-51h] BYREF
  __m256 v44; // [rsp+48h] [rbp-49h]
  _QWORD v45[7]; // [rsp+68h] [rbp-29h] BYREF

  _RBX = a2;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v39, 3, 1, 0, a1[1] + 3);
  LODWORD(v10) = 0;
  v42 = 1;
  v11 = v40 == 0;
  v12 = 0;
  v40 = 1;
  if ( !v11 )
    v12 = v39;
  v41 = v12;
  v39 = 1;
  v13 = (int *)Data::FillClearSkill(v43, &v41, &v39);
  v14 = *((_BYTE *)v13 + 4);
  if ( !v14 )
    goto LABEL_6;
  v10 = v12 - (__int64)*v13;
  if ( (unsigned __int64)(v10 + 0x80000000LL) <= 0xFFFFFFFF )
  {
    v14 = 1;
LABEL_6:
    v15 = 0;
    goto LABEL_7;
  }
  v14 = 0;
  v15 = 0;
  LODWORD(v10) = 0;
LABEL_7:
  if ( !v14 )
    LODWORD(v10) = 0;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v41, 3, 1, 0, *a1 + 3);
  v11 = v42 == 0;
  v42 = 1;
  if ( !v11 )
    v15 = v41;
  v39 = v15;
  v41 = 1;
  v40 = 1;
  v16 = Data::FillClearSkill(v43, &v39, &v41);
  if ( *(_BYTE *)(v16 + 4)
    && ((v17 = v15 - (__int64)*(int *)v16, (unsigned __int64)(v17 + 0x80000000LL) > 0xFFFFFFFF)
      ? (LOBYTE(v16) = 0, LODWORD(v17) = 0)
      : (LOBYTE(v16) = 1),
        (_BYTE)v16) )
  {
    if ( (_DWORD)v17 )
      LODWORD(v17) = 0;
  }
  else
  {
    LODWORD(v17) = 0;
  }
  v18 = 0;
  while ( v18 < a5[2] )
  {
    __asm { vmovups ymm0, ymmword ptr [rbx] }
    v20 = *a3;
    __asm { vmovups [rbp+4Fh+var_98], ymm0 }
    __asm
    {
      vpextrq rcx, xmm0, 1
      vmovd   edx, xmm0
    }
    v23 = _EDX + 1;
    v45[0] = v20 + 2 * _RCX;
    if ( v23 < SLODWORD(v44.m256_f32[6]) )
    {
      v24 = *(_QWORD *)&v44.m256_f32[4] + _RCX;
    }
    else
    {
      v23 = 0;
      v24 = 0;
    }
    v25 = v23 + 1;
    v45[1] = v20 + 2 * v24;
    if ( v25 < SLODWORD(v44.m256_f32[6]) )
    {
      v26 = *(_QWORD *)&v44.m256_f32[4] + v24;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v27 = v25 + 1;
    v45[2] = v20 + 2 * v26;
    if ( v27 < SLODWORD(v44.m256_f32[6]) )
    {
      v28 = *(_QWORD *)&v44.m256_f32[4] + v26;
    }
    else
    {
      v27 = 0;
      v28 = 0;
    }
    v29 = v27 + 1;
    v45[3] = v20 + 2 * v28;
    if ( v29 < SLODWORD(v44.m256_f32[6]) )
    {
      v30 = *(_QWORD *)&v44.m256_f32[4] + v28;
    }
    else
    {
      v29 = 0;
      v30 = 0;
    }
    v31 = v29 + 1;
    v45[4] = v20 + 2 * v30;
    if ( v31 < SLODWORD(v44.m256_f32[6]) )
    {
      v32 = *(_QWORD *)&v44.m256_f32[4] + v30;
    }
    else
    {
      v31 = 0;
      v32 = 0;
    }
    v45[5] = v20 + 2 * v32;
    if ( v31 + 1 < SLODWORD(v44.m256_f32[6]) )
      v33 = *(_QWORD *)&v44.m256_f32[4] + v32;
    else
      v33 = 0;
    v45[6] = v20 + 2 * v33;
    __asm { vzeroupper }
    Binary::Policy::PutBooleanUnit<Binary::Policy::UniqueFact,3>(v10, a4, a5, v45, v17);
    LOBYTE(v16) = v17;
    v34 = 0;
    if ( Binary::Policy::UniqueFact::GlobalCase[(int)v17] > 0 )
    {
      v35 = *(_DWORD *)(_RBX + 24);
      do
      {
        if ( ++*(_DWORD *)_RBX < v35 )
        {
          v16 = *(_QWORD *)(_RBX + 16);
          *(_QWORD *)(_RBX + 8) += v16;
        }
        else
        {
          *(_DWORD *)_RBX = 0;
          *(_QWORD *)(_RBX + 8) = 0;
        }
        ++v34;
      }
      while ( v34 < Binary::Policy::UniqueFact::GlobalCase[(int)v17] );
    }
    v36 = v17 + 1;
    ++v18;
    v37 = (int)v17 < 0;
    LODWORD(v17) = 0;
    if ( v37 != __OFSUB__(v36, 1) )
      LODWORD(v17) = v36;
  }
  return v16;
}

```

## disassembly

```asm
0x180088f70  mov     [rsp-8+arg_0], rbx
0x180088f75  push    rbp
0x180088f76  push    rsi
0x180088f77  push    rdi
0x180088f78  push    r12
0x180088f7a  push    r13
0x180088f7c  push    r14
0x180088f7e  push    r15
0x180088f80  lea     rbp, [rsp-1Fh]
0x180088f85  sub     rsp, 0B0h
0x180088f8c  mov     rax, cs:__security_cookie
0x180088f93  xor     rax, rsp
0x180088f96  mov     [rbp+4Fh+var_40], rax
0x180088f9a  mov     eax, [rcx+4]
0x180088f9d  mov     r12, r9
0x180088fa0  mov     r15, [rbp+4Fh+arg_20]
0x180088fa4  xor     r9d, r9d
0x180088fa7  mov     r13, r8
0x180088faa  mov     rbx, rdx
0x180088fad  mov     rsi, rcx
0x180088fb0  add     eax, 3
0x180088fb3  lea     rcx, [rbp+4Fh+var_B0]
0x180088fb7  mov     [rsp+0E0h+var_C0], eax
0x180088fbb  lea     edx, [r9+3]
0x180088fbf  lea     r8d, [r9+1]
0x180088fc3  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180088fc8  xor     r14d, r14d
0x180088fcb  mov     [rbp+4Fh+var_A4], 1
0x180088fcf  cmp     [rbp+4Fh+var_AC], r14b
0x180088fd3  lea     r8, [rbp+4Fh+var_B0]
0x180088fd7  mov     edi, r14d
0x180088fda  mov     [rbp+4Fh+var_AC], 1
0x180088fde  cmovnz  edi, [rbp+4Fh+var_B0]
0x180088fe2  lea     rdx, [rbp+4Fh+var_A8]
0x180088fe6  lea     rcx, [rbp+4Fh+var_A0]
0x180088fea  mov     [rbp+4Fh+var_A8], edi
0x180088fed  mov     [rbp+4Fh+var_B0], 1
0x180088ff4  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180088ff9  mov     edx, 80000000h
0x180088ffe  mov     r8d, 0FFFFFFFFh
0x180089004  movzx   ecx, byte ptr [rax+4]
0x180089008  test    cl, cl
0x18008900a  jz      short loc_180089020
0x18008900c  movsxd  rax, dword ptr [rax]
0x18008900f  movsxd  r14, edi
0x180089012  sub     r14, rax
0x180089015  lea     rax, [r14+rdx]
0x180089019  cmp     rax, r8
0x18008901c  ja      short loc_180089098
0x18008901e  mov     cl, 1
0x180089020  xor     edi, edi
0x180089022  mov     eax, [rsi]
0x180089024  test    cl, cl
0x180089026  lea     rcx, [rbp+4Fh+var_A8]
0x18008902a  cmovz   r14d, edi
0x18008902e  xor     r9d, r9d
0x180089031  add     eax, 3
0x180089034  mov     [rsp+0E0h+var_C0], eax
0x180089038  lea     edx, [r9+3]
0x18008903c  lea     r8d, [r9+1]
0x180089040  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180089045  cmp     [rbp+4Fh+var_A4], 0
0x180089049  lea     r8, [rbp+4Fh+var_A8]
0x18008904d  lea     rdx, [rbp+4Fh+var_B0]
0x180089051  mov     [rbp+4Fh+var_A4], 1
0x180089055  cmovnz  edi, [rbp+4Fh+var_A8]
0x180089059  lea     rcx, [rbp+4Fh+var_A0]
0x18008905d  mov     [rbp+4Fh+var_B0], edi
0x180089060  mov     [rbp+4Fh+var_A8], 1
0x180089067  mov     [rbp+4Fh+var_AC], 1
0x18008906b  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180089070  cmp     byte ptr [rax+4], 0
0x180089074  jz      short loc_1800890B5
0x180089076  movsxd  rax, dword ptr [rax]
0x180089079  mov     ecx, 0FFFFFFFFh
0x18008907e  movsxd  rdi, edi
0x180089081  sub     rdi, rax
0x180089084  mov     eax, 80000000h
0x180089089  add     rax, rdi
0x18008908c  cmp     rax, rcx
0x18008908f  ja      short loc_1800890A1
0x180089091  mov     al, 1
0x180089093  xor     r11d, r11d
0x180089096  jmp     short loc_1800890A9
0x180089098  xor     cl, cl
0x18008909a  xor     edi, edi
0x18008909c  mov     r14d, edi
0x18008909f  jmp     short loc_180089022
0x1800890a1  xor     al, al
0x1800890a3  xor     r11d, r11d
0x1800890a6  mov     edi, r11d
0x1800890a9  test    al, al
0x1800890ab  jz      short loc_1800890B8
0x1800890ad  test    edi, edi
0x1800890af  cmovnz  edi, r11d
0x1800890b3  jmp     short loc_1800890BB
0x1800890b5  xor     r11d, r11d
0x1800890b8  mov     edi, r11d
0x1800890bb  cmp     dword ptr [r15+8], 0
0x1800890c0  mov     esi, r11d
0x1800890c3  jle     loc_1800891FD
0x1800890c9  nop     dword ptr [rax+00000000h]
0x1800890d0  vmovups ymm0, ymmword ptr [rbx]
0x1800890d4  mov     r9, [r13+0]
0x1800890d8  vmovups [rbp+4Fh+var_98], ymm0
0x1800890dd  mov     r10d, dword ptr [rbp+4Fh+var_98+18h]
0x1800890e1  mov     r8, qword ptr [rbp+4Fh+var_98+10h]
0x1800890e5  vpextrq rcx, xmm0, 1
0x1800890eb  vmovd   edx, xmm0
0x1800890ef  inc     edx
0x1800890f1  lea     rax, [r9+rcx*2]
0x1800890f5  mov     [rbp+4Fh+var_78], rax
0x1800890f9  cmp     edx, r10d
0x1800890fc  jl      short loc_180089106
0x1800890fe  mov     edx, r11d
0x180089101  mov     rcx, r11
0x180089104  jmp     short loc_180089109
0x180089106  add     rcx, r8
0x180089109  inc     edx
0x18008910b  lea     rax, [r9+rcx*2]
0x18008910f  mov     [rbp+4Fh+var_70], rax
0x180089113  cmp     edx, r10d
0x180089116  jl      short loc_180089120
0x180089118  mov     edx, r11d
0x18008911b  mov     rcx, r11
0x18008911e  jmp     short loc_180089123
0x180089120  add     rcx, r8
0x180089123  inc     edx
0x180089125  lea     rax, [r9+rcx*2]
0x180089129  mov     [rbp+4Fh+var_68], rax
0x18008912d  cmp     edx, r10d
0x180089130  jl      short loc_18008913A
0x180089132  mov     edx, r11d
0x180089135  mov     rcx, r11
0x180089138  jmp     short loc_18008913D
0x18008913a  add     rcx, r8
0x18008913d  inc     edx
0x18008913f  lea     rax, [r9+rcx*2]
0x180089143  mov     [rbp+4Fh+var_60], rax
0x180089147  cmp     edx, r10d
0x18008914a  jl      short loc_180089154
0x18008914c  mov     edx, r11d
0x18008914f  mov     rcx, r11
0x180089152  jmp     short loc_180089157
0x180089154  add     rcx, r8
0x180089157  inc     edx
0x180089159  lea     rax, [r9+rcx*2]
0x18008915d  mov     [rbp+4Fh+var_58], rax
0x180089161  cmp     edx, r10d
0x180089164  jl      short loc_18008916E
0x180089166  mov     edx, r11d
0x180089169  mov     rcx, r11
0x18008916c  jmp     short loc_180089171
0x18008916e  add     rcx, r8
0x180089171  inc     edx
0x180089173  lea     rax, [r9+rcx*2]
0x180089177  mov     [rbp+4Fh+var_50], rax
0x18008917b  cmp     edx, r10d
0x18008917e  jl      short loc_180089185
0x180089180  mov     rcx, r11
0x180089183  jmp     short loc_180089188
0x180089185  add     rcx, r8
0x180089188  lea     rax, [r9+rcx*2]
0x18008918c  mov     [rsp+0E0h+var_C0], edi
0x180089190  mov     [rbp+4Fh+var_48], rax
0x180089194  lea     r9, [rbp+4Fh+var_78]
0x180089198  mov     r8, r15
0x18008919b  mov     rdx, r12
0x18008919e  mov     ecx, r14d
0x1800891a1  vzeroupper
0x1800891a4  call    ??$PutBooleanUnit@VUniqueFact@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY06$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::UniqueFact,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[7],int)
0x1800891a9  xor     r11d, r11d
0x1800891ac  movsxd  rax, edi
0x1800891af  lea     rdx, ?GlobalCase@UniqueFact@Policy@Binary@@2V?$StripedCategory@H$00@Data@@B; Data::StripedCategory<int,1> const Binary::Policy::UniqueFact::GlobalCase
0x1800891b6  mov     ecx, r11d
0x1800891b9  cmp     [rdx+rax*4], r11d
0x1800891bd  lea     rdx, [rdx+rax*4]
0x1800891c1  jle     short loc_1800891E5
0x1800891c3  mov     r8d, [rbx+18h]
0x1800891c7  inc     dword ptr [rbx]
0x1800891c9  cmp     [rbx], r8d
0x1800891cc  jl      short loc_1800891D7
0x1800891ce  mov     [rbx], r11d
0x1800891d1  mov     [rbx+8], r11
0x1800891d5  jmp     short loc_1800891DF
0x1800891d7  mov     rax, [rbx+10h]
0x1800891db  add     [rbx+8], rax
0x1800891df  inc     ecx
0x1800891e1  cmp     ecx, [rdx]
0x1800891e3  jl      short loc_1800891C7
0x1800891e5  lea     ecx, [rdi+1]
0x1800891e8  inc     esi
0x1800891ea  cmp     ecx, 1
0x1800891ed  mov     edi, r11d
0x1800891f0  cmovl   edi, ecx
0x1800891f3  cmp     esi, [r15+8]
0x1800891f7  jl      loc_1800890D0
0x1800891fd  mov     rcx, [rbp+4Fh+var_40]
0x180089201  xor     rcx, rsp; StackCookie
0x180089204  call    __security_check_cookie
0x180089209  mov     rbx, [rsp+0E0h+arg_0]
0x180089211  add     rsp, 0B0h
0x180089218  pop     r15
0x18008921a  pop     r14
0x18008921c  pop     r13
0x18008921e  pop     r12
0x180089220  pop     rdi
0x180089221  pop     rsi
0x180089222  pop     rbp
0x180089223  retn
```
