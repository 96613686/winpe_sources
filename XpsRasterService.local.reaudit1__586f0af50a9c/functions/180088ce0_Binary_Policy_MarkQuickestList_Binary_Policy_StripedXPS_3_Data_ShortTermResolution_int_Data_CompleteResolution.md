# Binary::Policy::MarkQuickestList<Binary::Policy::StripedXPS,3>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x180088ce0`
- end: `0x180088f64`
- name: `??$MarkQuickestList@VStripedXPS@Policy@Binary@@$02@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008e6d0`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x180088ce0`
- `0x18008a670`

## pseudocode

```c
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::StripedXPS,3>(
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
  int *v16; // rax
  __int64 v17; // rdi
  int v18; // esi
  __int64 v20; // r9
  int v23; // edx
  __int64 v24; // rcx
  int v25; // edx
  __int64 v26; // rcx
  int v27; // edx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // ecx
  int v31; // r8d
  int v32; // ecx
  bool v33; // sf
  int v35; // [rsp+30h] [rbp-51h] BYREF
  char v36; // [rsp+34h] [rbp-4Dh]
  int v37; // [rsp+38h] [rbp-49h] BYREF
  char v38; // [rsp+3Ch] [rbp-45h]
  _BYTE v39[8]; // [rsp+40h] [rbp-41h] BYREF
  __m256 v40; // [rsp+48h] [rbp-39h]
  _QWORD v41[5]; // [rsp+68h] [rbp-19h] BYREF

  _RBX = a2;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v35, 2, 1, 0, a1[1] + 2);
  LODWORD(v10) = 0;
  v38 = 1;
  v11 = v36 == 0;
  v12 = 0;
  v36 = 1;
  if ( !v11 )
    v12 = v35;
  v37 = v12;
  v35 = 1;
  v13 = (int *)Data::FillClearSkill(v39, &v37, &v35);
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
  Binary::Definition::GenerateAsyncServer((unsigned int)&v37, 2, 1, 0, *a1 + 2);
  v11 = v38 == 0;
  v38 = 1;
  if ( !v11 )
    v15 = v37;
  v35 = v15;
  v37 = 1;
  v36 = 1;
  v16 = (int *)Data::FillClearSkill(v39, &v35, &v37);
  if ( *((_BYTE *)v16 + 4)
    && ((v17 = v15 - (__int64)*v16, (unsigned __int64)(v17 + 0x80000000LL) > 0xFFFFFFFF)
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
    __asm { vmovups [rbp+4Fh+var_88], ymm0 }
    __asm
    {
      vpextrq rcx, xmm0, 1
      vmovd   edx, xmm0
    }
    v23 = _EDX + 1;
    v41[0] = v20 + 2 * _RCX;
    if ( v23 < SLODWORD(v40.m256_f32[6]) )
    {
      v24 = *(_QWORD *)&v40.m256_f32[4] + _RCX;
    }
    else
    {
      v23 = 0;
      v24 = 0;
    }
    v25 = v23 + 1;
    v41[1] = v20 + 2 * v24;
    if ( v25 < SLODWORD(v40.m256_f32[6]) )
    {
      v26 = *(_QWORD *)&v40.m256_f32[4] + v24;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v27 = v25 + 1;
    v41[2] = v20 + 2 * v26;
    if ( v27 < SLODWORD(v40.m256_f32[6]) )
    {
      v28 = *(_QWORD *)&v40.m256_f32[4] + v26;
    }
    else
    {
      v27 = 0;
      v28 = 0;
    }
    v41[3] = v20 + 2 * v28;
    if ( v27 + 1 < SLODWORD(v40.m256_f32[6]) )
      v29 = *(_QWORD *)&v40.m256_f32[4] + v28;
    else
      v29 = 0;
    v41[4] = v20 + 2 * v29;
    __asm { vzeroupper }
    Binary::Policy::PutBooleanUnit<Binary::Policy::StripedXPS,3>(v10, a4, a5, v41, v17);
    LOBYTE(v16) = v17;
    v30 = 0;
    if ( Binary::Policy::StripedXPS::GlobalCase[(int)v17] > 0 )
    {
      v31 = *(_DWORD *)(_RBX + 24);
      do
      {
        if ( ++*(_DWORD *)_RBX < v31 )
        {
          v16 = (int *)(*(_QWORD *)(_RBX + 16) + *(_QWORD *)(_RBX + 8));
          *(_QWORD *)(_RBX + 8) = v16;
        }
        else
        {
          *(_DWORD *)_RBX = 0;
          *(_QWORD *)(_RBX + 8) = 0;
        }
        ++v30;
      }
      while ( v30 < Binary::Policy::StripedXPS::GlobalCase[(int)v17] );
    }
    v32 = v17 + 1;
    ++v18;
    v33 = (int)v17 < 0;
    LODWORD(v17) = 0;
    if ( v33 != __OFSUB__(v32, 1) )
      LODWORD(v17) = v32;
  }
  return (char)v16;
}

```

## disassembly

```asm
0x180088ce0  mov     [rsp-8+arg_0], rbx
0x180088ce5  push    rbp
0x180088ce6  push    rsi
0x180088ce7  push    rdi
0x180088ce8  push    r12
0x180088cea  push    r13
0x180088cec  push    r14
0x180088cee  push    r15
0x180088cf0  lea     rbp, [rsp-1Fh]
0x180088cf5  sub     rsp, 0A0h
0x180088cfc  mov     rax, cs:__security_cookie
0x180088d03  xor     rax, rsp
0x180088d06  mov     [rbp+4Fh+var_40], rax
0x180088d0a  mov     eax, [rcx+4]
0x180088d0d  mov     r12, r9
0x180088d10  mov     r15, [rbp+4Fh+arg_20]
0x180088d14  xor     r9d, r9d
0x180088d17  mov     r13, r8
0x180088d1a  mov     rbx, rdx
0x180088d1d  mov     rsi, rcx
0x180088d20  add     eax, 2
0x180088d23  lea     rcx, [rbp+4Fh+var_A0]
0x180088d27  mov     [rsp+0D0h+var_B0], eax
0x180088d2b  lea     edx, [r9+2]
0x180088d2f  lea     r8d, [r9+1]
0x180088d33  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180088d38  xor     r14d, r14d
0x180088d3b  mov     [rbp+4Fh+var_94], 1
0x180088d3f  cmp     [rbp+4Fh+var_9C], r14b
0x180088d43  lea     r8, [rbp+4Fh+var_A0]
0x180088d47  mov     edi, r14d
0x180088d4a  mov     [rbp+4Fh+var_9C], 1
0x180088d4e  cmovnz  edi, [rbp+4Fh+var_A0]
0x180088d52  lea     rdx, [rbp+4Fh+var_98]
0x180088d56  lea     rcx, [rbp+4Fh+var_90]
0x180088d5a  mov     [rbp+4Fh+var_98], edi
0x180088d5d  mov     [rbp+4Fh+var_A0], 1
0x180088d64  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180088d69  mov     edx, 80000000h
0x180088d6e  mov     r8d, 0FFFFFFFFh
0x180088d74  movzx   ecx, byte ptr [rax+4]
0x180088d78  test    cl, cl
0x180088d7a  jz      short loc_180088D90
0x180088d7c  movsxd  rax, dword ptr [rax]
0x180088d7f  movsxd  r14, edi
0x180088d82  sub     r14, rax
0x180088d85  lea     rax, [r14+rdx]
0x180088d89  cmp     rax, r8
0x180088d8c  ja      short loc_180088E08
0x180088d8e  mov     cl, 1
0x180088d90  xor     edi, edi
0x180088d92  mov     eax, [rsi]
0x180088d94  test    cl, cl
0x180088d96  lea     rcx, [rbp+4Fh+var_98]
0x180088d9a  cmovz   r14d, edi
0x180088d9e  xor     r9d, r9d
0x180088da1  add     eax, 2
0x180088da4  mov     [rsp+0D0h+var_B0], eax
0x180088da8  lea     edx, [r9+2]
0x180088dac  lea     r8d, [r9+1]
0x180088db0  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180088db5  cmp     [rbp+4Fh+var_94], 0
0x180088db9  lea     r8, [rbp+4Fh+var_98]
0x180088dbd  lea     rdx, [rbp+4Fh+var_A0]
0x180088dc1  mov     [rbp+4Fh+var_94], 1
0x180088dc5  cmovnz  edi, [rbp+4Fh+var_98]
0x180088dc9  lea     rcx, [rbp+4Fh+var_90]
0x180088dcd  mov     [rbp+4Fh+var_A0], edi
0x180088dd0  mov     [rbp+4Fh+var_98], 1
0x180088dd7  mov     [rbp+4Fh+var_9C], 1
0x180088ddb  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180088de0  cmp     byte ptr [rax+4], 0
0x180088de4  jz      short loc_180088E25
0x180088de6  movsxd  rax, dword ptr [rax]
0x180088de9  mov     ecx, 0FFFFFFFFh
0x180088dee  movsxd  rdi, edi
0x180088df1  sub     rdi, rax
0x180088df4  mov     eax, 80000000h
0x180088df9  add     rax, rdi
0x180088dfc  cmp     rax, rcx
0x180088dff  ja      short loc_180088E11
0x180088e01  mov     al, 1
0x180088e03  xor     r11d, r11d
0x180088e06  jmp     short loc_180088E19
0x180088e08  xor     cl, cl
0x180088e0a  xor     edi, edi
0x180088e0c  mov     r14d, edi
0x180088e0f  jmp     short loc_180088D92
0x180088e11  xor     al, al
0x180088e13  xor     r11d, r11d
0x180088e16  mov     edi, r11d
0x180088e19  test    al, al
0x180088e1b  jz      short loc_180088E28
0x180088e1d  test    edi, edi
0x180088e1f  cmovnz  edi, r11d
0x180088e23  jmp     short loc_180088E2B
0x180088e25  xor     r11d, r11d
0x180088e28  mov     edi, r11d
0x180088e2b  cmp     dword ptr [r15+8], 0
0x180088e30  mov     esi, r11d
0x180088e33  jle     loc_180088F3D
0x180088e39  nop     dword ptr [rax+00000000h]
0x180088e40  vmovups ymm0, ymmword ptr [rbx]
0x180088e44  mov     r9, [r13+0]
0x180088e48  vmovups [rbp+4Fh+var_88], ymm0
0x180088e4d  mov     r10d, dword ptr [rbp+4Fh+var_88+18h]
0x180088e51  mov     r8, qword ptr [rbp+4Fh+var_88+10h]
0x180088e55  vpextrq rcx, xmm0, 1
0x180088e5b  vmovd   edx, xmm0
0x180088e5f  inc     edx
0x180088e61  lea     rax, [r9+rcx*2]
0x180088e65  mov     [rbp+4Fh+var_68], rax
0x180088e69  cmp     edx, r10d
0x180088e6c  jl      short loc_180088E76
0x180088e6e  mov     edx, r11d
0x180088e71  mov     rcx, r11
0x180088e74  jmp     short loc_180088E79
0x180088e76  add     rcx, r8
0x180088e79  inc     edx
0x180088e7b  lea     rax, [r9+rcx*2]
0x180088e7f  mov     [rbp+4Fh+var_60], rax
0x180088e83  cmp     edx, r10d
0x180088e86  jl      short loc_180088E90
0x180088e88  mov     edx, r11d
0x180088e8b  mov     rcx, r11
0x180088e8e  jmp     short loc_180088E93
0x180088e90  add     rcx, r8
0x180088e93  inc     edx
0x180088e95  lea     rax, [r9+rcx*2]
0x180088e99  mov     [rbp+4Fh+var_58], rax
0x180088e9d  cmp     edx, r10d
0x180088ea0  jl      short loc_180088EAA
0x180088ea2  mov     edx, r11d
0x180088ea5  mov     rcx, r11
0x180088ea8  jmp     short loc_180088EAD
0x180088eaa  add     rcx, r8
0x180088ead  inc     edx
0x180088eaf  lea     rax, [r9+rcx*2]
0x180088eb3  mov     [rbp+4Fh+var_50], rax
0x180088eb7  cmp     edx, r10d
0x180088eba  jl      short loc_180088EC1
0x180088ebc  mov     rcx, r11
0x180088ebf  jmp     short loc_180088EC4
0x180088ec1  add     rcx, r8
0x180088ec4  lea     rax, [r9+rcx*2]
0x180088ec8  mov     [rsp+0D0h+var_B0], edi
0x180088ecc  mov     [rbp+4Fh+var_48], rax
0x180088ed0  lea     r9, [rbp+4Fh+var_68]
0x180088ed4  mov     r8, r15
0x180088ed7  mov     rdx, r12
0x180088eda  mov     ecx, r14d
0x180088edd  vzeroupper
0x180088ee0  call    ??$PutBooleanUnit@VStripedXPS@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY04$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::StripedXPS,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[5],int)
0x180088ee5  xor     r11d, r11d
0x180088ee8  movsxd  rax, edi
0x180088eeb  lea     rdx, ?GlobalCase@StripedXPS@Policy@Binary@@2V?$StripedCategory@H$00@Data@@B; Data::StripedCategory<int,1> const Binary::Policy::StripedXPS::GlobalCase
0x180088ef2  mov     ecx, r11d
0x180088ef5  cmp     [rdx+rax*4], r11d
0x180088ef9  lea     rdx, [rdx+rax*4]
0x180088efd  jle     short loc_180088F25
0x180088eff  mov     r8d, [rbx+18h]
0x180088f03  inc     dword ptr [rbx]
0x180088f05  cmp     [rbx], r8d
0x180088f08  jl      short loc_180088F13
0x180088f0a  mov     [rbx], r11d
0x180088f0d  mov     [rbx+8], r11
0x180088f11  jmp     short loc_180088F1F
0x180088f13  mov     rax, [rbx+8]
0x180088f17  add     rax, [rbx+10h]
0x180088f1b  mov     [rbx+8], rax
0x180088f1f  inc     ecx
0x180088f21  cmp     ecx, [rdx]
0x180088f23  jl      short loc_180088F03
0x180088f25  lea     ecx, [rdi+1]
0x180088f28  inc     esi
0x180088f2a  cmp     ecx, 1
0x180088f2d  mov     edi, r11d
0x180088f30  cmovl   edi, ecx
0x180088f33  cmp     esi, [r15+8]
0x180088f37  jl      loc_180088E40
0x180088f3d  mov     rcx, [rbp+4Fh+var_40]
0x180088f41  xor     rcx, rsp; StackCookie
0x180088f44  call    __security_check_cookie
0x180088f49  mov     rbx, [rsp+0D0h+arg_0]
0x180088f51  add     rsp, 0A0h
0x180088f58  pop     r15
0x180088f5a  pop     r14
0x180088f5c  pop     r13
0x180088f5e  pop     r12
0x180088f60  pop     rdi
0x180088f61  pop     rsi
0x180088f62  pop     rbp
0x180088f63  retn
```
