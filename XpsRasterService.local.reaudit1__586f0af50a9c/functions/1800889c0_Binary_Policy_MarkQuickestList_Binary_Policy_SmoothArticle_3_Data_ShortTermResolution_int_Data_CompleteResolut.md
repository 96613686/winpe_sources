# Binary::Policy::MarkQuickestList<Binary::Policy::SmoothArticle,3>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x1800889c0`
- end: `0x180088cd2`
- name: `??$MarkQuickestList@VSmoothArticle@Policy@Binary@@$02@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008bc80`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x1800889c0`
- `0x18008a170`

## pseudocode

```c
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::SmoothArticle,3>(
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
  __int64 v15; // rcx
  int v16; // edi
  int *v17; // rax
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
  int v35; // edx
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38; // ecx
  int v39; // r8d
  int v40; // ecx
  bool v41; // sf
  int v43; // [rsp+30h] [rbp-71h] BYREF
  char v44; // [rsp+34h] [rbp-6Dh]
  int v45; // [rsp+38h] [rbp-69h] BYREF
  char v46; // [rsp+3Ch] [rbp-65h]
  _BYTE v47[8]; // [rsp+40h] [rbp-61h] BYREF
  __m256 v48; // [rsp+48h] [rbp-59h]
  _QWORD v49[8]; // [rsp+70h] [rbp-31h] BYREF

  _RBX = a2;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v43, 5, 2, 2, a1[1] + 3);
  LODWORD(v10) = 0;
  v46 = 1;
  v11 = v44 == 0;
  v12 = 0;
  v44 = 1;
  if ( !v11 )
    v12 = v43;
  v45 = v12;
  v43 = 2;
  v13 = (int *)Data::FillClearSkill(v47, &v45, &v43);
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
  Binary::Definition::GenerateAsyncServer((unsigned int)&v45, 5, 2, 2, *a1 + 3);
  v11 = v46 == 0;
  v46 = 1;
  if ( !v11 )
    v16 = v45;
  v43 = v16;
  v45 = 2;
  v44 = 1;
  v17 = (int *)Data::FillClearSkill(v47, &v43, &v45);
  if ( *((_BYTE *)v17 + 4)
    && (v18 = 2LL * *v17, LOBYTE(v17) = 2 * *v17, (unsigned __int64)(v18 + 0x80000000LL) <= 0xFFFFFFFF)
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
  while ( v20 < a5[2] )
  {
    __asm { vmovups ymm0, ymmword ptr [rbx] }
    v22 = *a3;
    __asm { vmovups [rbp+4Fh+var_A8], ymm0 }
    __asm
    {
      vpextrq rcx, xmm0, 1
      vmovd   edx, xmm0
    }
    v25 = _EDX + 1;
    v49[0] = v22 + 2 * _RCX;
    if ( v25 < SLODWORD(v48.m256_f32[6]) )
    {
      v26 = *(_QWORD *)&v48.m256_f32[4] + _RCX;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v27 = v25 + 1;
    v49[1] = v22 + 2 * v26;
    if ( v27 < SLODWORD(v48.m256_f32[6]) )
    {
      v28 = *(_QWORD *)&v48.m256_f32[4] + v26;
    }
    else
    {
      v27 = 0;
      v28 = 0;
    }
    v29 = v27 + 1;
    v49[2] = v22 + 2 * v28;
    if ( v29 < SLODWORD(v48.m256_f32[6]) )
    {
      v30 = *(_QWORD *)&v48.m256_f32[4] + v28;
    }
    else
    {
      v29 = 0;
      v30 = 0;
    }
    v31 = v29 + 1;
    v49[3] = v22 + 2 * v30;
    if ( v31 < SLODWORD(v48.m256_f32[6]) )
    {
      v32 = *(_QWORD *)&v48.m256_f32[4] + v30;
    }
    else
    {
      v31 = 0;
      v32 = 0;
    }
    v33 = v31 + 1;
    v49[4] = v22 + 2 * v32;
    if ( v33 < SLODWORD(v48.m256_f32[6]) )
    {
      v34 = *(_QWORD *)&v48.m256_f32[4] + v32;
    }
    else
    {
      v33 = 0;
      v34 = 0;
    }
    v35 = v33 + 1;
    v49[5] = v22 + 2 * v34;
    if ( v35 < SLODWORD(v48.m256_f32[6]) )
    {
      v36 = *(_QWORD *)&v48.m256_f32[4] + v34;
    }
    else
    {
      v35 = 0;
      v36 = 0;
    }
    v49[6] = v22 + 2 * v36;
    if ( v35 + 1 < SLODWORD(v48.m256_f32[6]) )
      v37 = *(_QWORD *)&v48.m256_f32[4] + v36;
    else
      v37 = 0;
    v49[7] = v22 + 2 * v37;
    __asm { vzeroupper }
    Binary::Policy::PutBooleanUnit<Binary::Policy::SmoothArticle,3>(v10, a4, a5, v49, v19);
    LOBYTE(v17) = v19;
    v38 = 0;
    if ( Binary::Policy::SmoothArticle::GlobalCase[(int)v19] > 0 )
    {
      v39 = *(_DWORD *)(_RBX + 24);
      do
      {
        if ( ++*(_DWORD *)_RBX < v39 )
        {
          v17 = (int *)(*(_QWORD *)(_RBX + 16) + *(_QWORD *)(_RBX + 8));
          *(_QWORD *)(_RBX + 8) = v17;
        }
        else
        {
          *(_DWORD *)_RBX = 0;
          *(_QWORD *)(_RBX + 8) = 0;
        }
        ++v38;
      }
      while ( v38 < Binary::Policy::SmoothArticle::GlobalCase[(int)v19] );
    }
    v40 = v19 + 1;
    ++v20;
    v41 = (int)v19 - 1 < 0;
    LODWORD(v19) = 0;
    if ( v41 != __OFSUB__(v40, 2) )
      LODWORD(v19) = v40;
  }
  return (char)v17;
}

```

## disassembly

```asm
0x1800889c0  mov     [rsp-8+arg_0], rbx
0x1800889c5  push    rbp
0x1800889c6  push    rsi
0x1800889c7  push    rdi
0x1800889c8  push    r12
0x1800889ca  push    r13
0x1800889cc  push    r14
0x1800889ce  push    r15
0x1800889d0  lea     rbp, [rsp-1Fh]
0x1800889d5  sub     rsp, 0C0h
0x1800889dc  mov     rax, cs:__security_cookie
0x1800889e3  xor     rax, rsp
0x1800889e6  mov     [rbp+4Fh+var_40], rax
0x1800889ea  mov     eax, [rcx+4]
0x1800889ed  mov     r12, r9
0x1800889f0  mov     r15, [rbp+4Fh+arg_20]
0x1800889f4  mov     r9d, 2
0x1800889fa  add     eax, 3
0x1800889fd  mov     r13, r8
0x180088a00  mov     rbx, rdx
0x180088a03  mov     [rsp+0F0h+var_D0], eax
0x180088a07  mov     rsi, rcx
0x180088a0a  mov     r8d, r9d
0x180088a0d  mov     edx, 5
0x180088a12  lea     rcx, [rbp+4Fh+var_C0]
0x180088a16  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180088a1b  xor     r14d, r14d
0x180088a1e  mov     [rbp+4Fh+var_B4], 1
0x180088a22  cmp     [rbp+4Fh+var_BC], r14b
0x180088a26  lea     r8, [rbp+4Fh+var_C0]
0x180088a2a  mov     edi, r14d
0x180088a2d  mov     [rbp+4Fh+var_BC], 1
0x180088a31  cmovnz  edi, [rbp+4Fh+var_C0]
0x180088a35  lea     rdx, [rbp+4Fh+var_B8]
0x180088a39  lea     rcx, [rbp+4Fh+var_B0]
0x180088a3d  mov     [rbp+4Fh+var_B8], edi
0x180088a40  mov     [rbp+4Fh+var_C0], 2
0x180088a47  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180088a4c  mov     edx, 80000000h
0x180088a51  mov     r8d, 0FFFFFFFFh
0x180088a57  movzx   ecx, byte ptr [rax+4]
0x180088a5b  test    cl, cl
0x180088a5d  jz      short loc_180088A8F
0x180088a5f  movsxd  rcx, dword ptr [rax]
0x180088a62  add     rcx, rcx
0x180088a65  lea     rax, [rcx+rdx]
0x180088a69  cmp     rax, r8
0x180088a6c  ja      short loc_180088A8D
0x180088a6e  movsxd  rax, ecx
0x180088a71  movsxd  r14, edi
0x180088a74  sub     r14, rax
0x180088a77  lea     rax, [r14+rdx]
0x180088a7b  cmp     rax, r8
0x180088a7e  ja      short loc_180088A84
0x180088a80  mov     cl, 1
0x180088a82  jmp     short loc_180088A8F
0x180088a84  xor     cl, cl
0x180088a86  xor     edi, edi
0x180088a88  mov     r14d, edi
0x180088a8b  jmp     short loc_180088A91
0x180088a8d  xor     cl, cl
0x180088a8f  xor     edi, edi
0x180088a91  mov     eax, [rsi]
0x180088a93  test    cl, cl
0x180088a95  mov     r9d, 2
0x180088a9b  lea     rcx, [rbp+4Fh+var_B8]
0x180088a9f  cmovz   r14d, edi
0x180088aa3  mov     edx, 5
0x180088aa8  add     eax, 3
0x180088aab  mov     r8d, r9d
0x180088aae  mov     [rsp+0F0h+var_D0], eax
0x180088ab2  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180088ab7  cmp     [rbp+4Fh+var_B4], 0
0x180088abb  lea     r8, [rbp+4Fh+var_B8]
0x180088abf  lea     rdx, [rbp+4Fh+var_C0]
0x180088ac3  mov     [rbp+4Fh+var_B4], 1
0x180088ac7  cmovnz  edi, [rbp+4Fh+var_B8]
0x180088acb  lea     rcx, [rbp+4Fh+var_B0]
0x180088acf  mov     [rbp+4Fh+var_C0], edi
0x180088ad2  mov     [rbp+4Fh+var_B8], 2
0x180088ad9  mov     [rbp+4Fh+var_BC], 1
0x180088add  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180088ae2  cmp     byte ptr [rax+4], 0
0x180088ae6  jz      short loc_180088B44
0x180088ae8  movsxd  rcx, dword ptr [rax]
0x180088aeb  mov     edx, 80000000h
0x180088af0  add     rcx, rcx
0x180088af3  mov     r8d, 0FFFFFFFFh
0x180088af9  lea     rax, [rcx+rdx]
0x180088afd  cmp     rax, r8
0x180088b00  ja      short loc_180088B44
0x180088b02  movsxd  rax, ecx
0x180088b05  movsxd  rdi, edi
0x180088b08  sub     rdi, rax
0x180088b0b  lea     rax, [rdi+rdx]
0x180088b0f  cmp     rax, r8
0x180088b12  ja      short loc_180088B1B
0x180088b14  mov     al, 1
0x180088b16  xor     r11d, r11d
0x180088b19  jmp     short loc_180088B23
0x180088b1b  xor     al, al
0x180088b1d  xor     r11d, r11d
0x180088b20  mov     edi, r11d
0x180088b23  test    al, al
0x180088b25  jz      short loc_180088B47
0x180088b27  cmp     edi, 1
0x180088b2a  jbe     short loc_180088B4A
0x180088b2c  and     edi, 80000001h
0x180088b32  jge     short loc_180088B3B
0x180088b34  dec     edi
0x180088b36  or      edi, 0FFFFFFFEh
0x180088b39  inc     edi
0x180088b3b  test    edi, edi
0x180088b3d  jns     short loc_180088B4A
0x180088b3f  add     edi, 2
0x180088b42  jmp     short loc_180088B4A
0x180088b44  xor     r11d, r11d
0x180088b47  mov     edi, r11d
0x180088b4a  cmp     dword ptr [r15+8], 0
0x180088b4f  mov     esi, r11d
0x180088b52  jle     loc_180088CAB
0x180088b58  nop     dword ptr [rax+rax+00000000h]
0x180088b60  vmovups ymm0, ymmword ptr [rbx]
0x180088b64  mov     r9, [r13+0]
0x180088b68  vmovups [rbp+4Fh+var_A8], ymm0
0x180088b6d  mov     r10d, dword ptr [rbp+4Fh+var_A8+18h]
0x180088b71  mov     r8, qword ptr [rbp+4Fh+var_A8+10h]
0x180088b75  vpextrq rcx, xmm0, 1
0x180088b7b  vmovd   edx, xmm0
0x180088b7f  inc     edx
0x180088b81  lea     rax, [r9+rcx*2]
0x180088b85  mov     [rbp+4Fh+var_80], rax
0x180088b89  cmp     edx, r10d
0x180088b8c  jl      short loc_180088B96
0x180088b8e  mov     edx, r11d
0x180088b91  mov     rcx, r11
0x180088b94  jmp     short loc_180088B99
0x180088b96  add     rcx, r8
0x180088b99  inc     edx
0x180088b9b  lea     rax, [r9+rcx*2]
0x180088b9f  mov     [rbp+4Fh+var_78], rax
0x180088ba3  cmp     edx, r10d
0x180088ba6  jl      short loc_180088BB0
0x180088ba8  mov     edx, r11d
0x180088bab  mov     rcx, r11
0x180088bae  jmp     short loc_180088BB3
0x180088bb0  add     rcx, r8
0x180088bb3  inc     edx
0x180088bb5  lea     rax, [r9+rcx*2]
0x180088bb9  mov     [rbp+4Fh+var_70], rax
0x180088bbd  cmp     edx, r10d
0x180088bc0  jl      short loc_180088BCA
0x180088bc2  mov     edx, r11d
0x180088bc5  mov     rcx, r11
0x180088bc8  jmp     short loc_180088BCD
0x180088bca  add     rcx, r8
0x180088bcd  inc     edx
0x180088bcf  lea     rax, [r9+rcx*2]
0x180088bd3  mov     [rbp+4Fh+var_68], rax
0x180088bd7  cmp     edx, r10d
0x180088bda  jl      short loc_180088BE4
0x180088bdc  mov     edx, r11d
0x180088bdf  mov     rcx, r11
0x180088be2  jmp     short loc_180088BE7
0x180088be4  add     rcx, r8
0x180088be7  inc     edx
0x180088be9  lea     rax, [r9+rcx*2]
0x180088bed  mov     [rbp+4Fh+var_60], rax
0x180088bf1  cmp     edx, r10d
0x180088bf4  jl      short loc_180088BFE
0x180088bf6  mov     edx, r11d
0x180088bf9  mov     rcx, r11
0x180088bfc  jmp     short loc_180088C01
0x180088bfe  add     rcx, r8
0x180088c01  inc     edx
0x180088c03  lea     rax, [r9+rcx*2]
0x180088c07  mov     [rbp+4Fh+var_58], rax
0x180088c0b  cmp     edx, r10d
0x180088c0e  jl      short loc_180088C18
0x180088c10  mov     edx, r11d
0x180088c13  mov     rcx, r11
0x180088c16  jmp     short loc_180088C1B
0x180088c18  add     rcx, r8
0x180088c1b  inc     edx
0x180088c1d  lea     rax, [r9+rcx*2]
0x180088c21  mov     [rbp+4Fh+var_50], rax
0x180088c25  cmp     edx, r10d
0x180088c28  jl      short loc_180088C2F
0x180088c2a  mov     rcx, r11
0x180088c2d  jmp     short loc_180088C32
0x180088c2f  add     rcx, r8
0x180088c32  lea     rax, [r9+rcx*2]
0x180088c36  mov     [rsp+0F0h+var_D0], edi
0x180088c3a  mov     [rbp+4Fh+var_48], rax
0x180088c3e  lea     r9, [rbp+4Fh+var_80]
0x180088c42  mov     r8, r15
0x180088c45  mov     rdx, r12
0x180088c48  mov     ecx, r14d
0x180088c4b  vzeroupper
0x180088c4e  call    ??$PutBooleanUnit@VSmoothArticle@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY07$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::SmoothArticle,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[8],int)
0x180088c53  xor     r11d, r11d
0x180088c56  movsxd  rax, edi
0x180088c59  lea     rdx, ?GlobalCase@SmoothArticle@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B; Data::StripedCategory<int,2> const Binary::Policy::SmoothArticle::GlobalCase
0x180088c60  mov     ecx, r11d
0x180088c63  cmp     [rdx+rax*4], r11d
0x180088c67  lea     rdx, [rdx+rax*4]
0x180088c6b  jle     short loc_180088C93
0x180088c6d  mov     r8d, [rbx+18h]
0x180088c71  inc     dword ptr [rbx]
0x180088c73  cmp     [rbx], r8d
0x180088c76  jl      short loc_180088C81
0x180088c78  mov     [rbx], r11d
0x180088c7b  mov     [rbx+8], r11
0x180088c7f  jmp     short loc_180088C8D
0x180088c81  mov     rax, [rbx+8]
0x180088c85  add     rax, [rbx+10h]
0x180088c89  mov     [rbx+8], rax
0x180088c8d  inc     ecx
0x180088c8f  cmp     ecx, [rdx]
0x180088c91  jl      short loc_180088C71
0x180088c93  lea     ecx, [rdi+1]
0x180088c96  inc     esi
0x180088c98  cmp     ecx, 2
0x180088c9b  mov     edi, r11d
0x180088c9e  cmovl   edi, ecx
0x180088ca1  cmp     esi, [r15+8]
0x180088ca5  jl      loc_180088B60
0x180088cab  mov     rcx, [rbp+4Fh+var_40]
0x180088caf  xor     rcx, rsp; StackCookie
0x180088cb2  call    __security_check_cookie
0x180088cb7  mov     rbx, [rsp+0F0h+arg_0]
0x180088cbf  add     rsp, 0C0h
0x180088cc6  pop     r15
0x180088cc8  pop     r14
0x180088cca  pop     r13
0x180088ccc  pop     r12
0x180088cce  pop     rdi
0x180088ccf  pop     rsi
0x180088cd0  pop     rbp
0x180088cd1  retn
```
