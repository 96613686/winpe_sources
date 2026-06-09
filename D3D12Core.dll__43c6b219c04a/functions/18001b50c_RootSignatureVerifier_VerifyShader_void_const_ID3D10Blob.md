# RootSignatureVerifier::VerifyShader(void const *,ID3D10Blob * *)

- ea: `0x18001b50c`
- end: `0x18001bac7`
- name: `?VerifyShader@RootSignatureVerifier@@QEAAJPEBXPEAPEAUID3D10Blob@@@Z`
- size: `1467`
- prototype: `__int64 __fastcall(RootSignatureVerifier *__hidden this, const void *, struct ID3D10Blob **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001a020`

## callees

- `0x18001b50c`
- `0x18001bad0`
- `0x18001bbe0`
- `0x18001cb40`
- `0x18001cbb0`
- `0x18003b478`
- `0x18004d2a0`
- `0x18005e5f8`
- `0x1800bb480`

## string_xrefs

- `0x18001ba1e`: `A Shader is declaring a typed UAV using a register mapped to a root descriptor UAV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18001b984`: `Shader SRV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature\n`
- `0x18001b966`: `A Shader is declaring a resource object as a texture using a register mapped to a root descriptor SRV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.\n`
- `0x18001b740`: `Shader sampler descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature\n`
- `0x18001b7dd`: `Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace%u) is bound to a root constants parameter where Num32BitValues == 0. This root parameter cannot provide data to the CBV, and therefore this buffer is considered not bound.\n`
- `0x18001b7c5`: `Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature\n`
- `0x18001ba66`: `Shader UAV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature`
- `0x18001ba56`: `A Shader is declaring a structured UAV with counter using a register mapped to a root descriptor UAV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18001ba7e`: `Shader has root bindings but root signature uses a DENY flag to disallow root binding access to the shader stage.\n`

## pseudocode

```c
__int64 __fastcall RootSignatureVerifier::VerifyShader(
        RootSignatureVerifier *this,
        unsigned int *a2,
        struct ID3D10Blob **a3)
{
  int v6; // r12d
  __int64 v7; // rax
  unsigned int v8; // ecx
  unsigned int v9; // eax
  bool v10; // di
  char v11; // r14
  int v12; // r14d
  char v13; // bl
  char v14; // al
  bool v15; // zf
  unsigned int v16; // esi
  unsigned int v17; // ebx
  unsigned int v18; // edi
  unsigned int v19; // ebx
  const char *v20; // rdx
  int v21; // eax
  unsigned int v22; // ebx
  struct RootSignatureVerifier::TreeNode *RegisterRange; // rax
  bool v24; // zf
  int v25; // ecx
  bool v26; // zf
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  unsigned int v30; // edi
  unsigned int v31; // ebx
  unsigned int v32; // esi
  unsigned int v33; // ebx
  struct RootSignatureVerifier::TreeNode *v34; // rax
  unsigned int v35; // edi
  unsigned int v36; // ebx
  unsigned int v37; // esi
  unsigned int v38; // ebx
  struct RootSignatureVerifier::TreeNode *v39; // rax
  int v40; // eax
  __int64 v42; // [rsp+20h] [rbp-E0h]
  __int64 v43; // [rsp+20h] [rbp-E0h]
  __int64 v44; // [rsp+20h] [rbp-E0h]
  bool v45; // [rsp+30h] [rbp-D0h]
  char v46; // [rsp+31h] [rbp-CFh]
  enum D3D12_SHADER_VISIBILITY VisibilityType; // [rsp+34h] [rbp-CCh]
  __int128 v48; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int *v49; // [rsp+48h] [rbp-B8h]
  _DWORD v50[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v51; // [rsp+60h] [rbp-A0h]
  unsigned int v52; // [rsp+98h] [rbp-68h]
  unsigned int v53; // [rsp+D0h] [rbp-30h]
  unsigned int v54; // [rsp+860h] [rbp+760h]
  unsigned int v55; // [rsp+864h] [rbp+764h]
  unsigned int v56; // [rsp+868h] [rbp+768h]
  unsigned int v57; // [rsp+878h] [rbp+778h]

  v49 = 0;
  v48 = 0;
  D3D10ShaderBinary::InitInstructionInfo(this);
  D3D10ShaderBinary::CInstruction::CInstruction((D3D10ShaderBinary::CInstruction *)v50);
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_139;
  }
  v7 = a2[1];
  v6 = 0;
  *((_QWORD *)&v48 + 1) = a2;
  v49 = &a2[v7];
  *(_QWORD *)&v48 = a2 + 2;
  v8 = *a2;
  v9 = *a2 & 0xF0;
  v10 = v9 > 0x50 || v9 == 80 && (v8 & 0xF) != 0;
  v45 = v10;
  VisibilityType = (unsigned int)GetVisibilityType(HIWORD(v8));
  v11 = 0;
  if ( VisibilityType == D3D12_SHADER_VISIBILITY_VERTEX )
  {
    v11 = (*((_BYTE *)this + 536) & 2) != 0;
  }
  else
  {
    if ( VisibilityType == D3D12_SHADER_VISIBILITY_HULL )
    {
      v12 = *((_DWORD *)this + 134) >> 2;
    }
    else if ( VisibilityType == D3D12_SHADER_VISIBILITY_DOMAIN )
    {
      v12 = *((_DWORD *)this + 134) >> 3;
    }
    else if ( VisibilityType == D3D12_SHADER_VISIBILITY_GEOMETRY )
    {
      v12 = *((_DWORD *)this + 134) >> 4;
    }
    else
    {
      if ( VisibilityType != D3D12_SHADER_VISIBILITY_PIXEL )
      {
        if ( VisibilityType == (D3D12_SHADER_VISIBILITY_GEOMETRY|D3D12_SHADER_VISIBILITY_HULL) )
        {
          if ( *((_BYTE *)this + 515) && (*((_DWORD *)this + 134) & 0x100) == 0 )
            goto LABEL_20;
          v11 = 1;
        }
        else if ( VisibilityType != (D3D12_SHADER_VISIBILITY_PIXEL|D3D12_SHADER_VISIBILITY_HULL) )
        {
          goto LABEL_28;
        }
        if ( !*((_BYTE *)this + 515) )
        {
LABEL_21:
          v11 = 1;
          goto LABEL_28;
        }
LABEL_20:
        if ( (*((_DWORD *)this + 134) & 0x200) == 0 )
          goto LABEL_28;
        goto LABEL_21;
      }
      v12 = *((_DWORD *)this + 134) >> 5;
    }
    v11 = v12 & 1;
  }
LABEL_28:
  v13 = 0;
  v14 = 0;
LABEL_29:
  v46 = v14;
  while ( !v14 && (unsigned __int64)v48 < (unsigned __int64)v49 )
  {
    D3D10ShaderBinary::CShaderCodeParser::ParseInstruction(
      (D3D10ShaderBinary::CShaderCodeParser *)&v48,
      (struct D3D10ShaderBinary::CInstruction *)v50);
    if ( v50[0] <= 143 )
    {
      if ( v50[0] == 143 )
        goto LABEL_54;
      if ( v50[0] > 97 )
      {
        if ( v50[0] <= 103 )
        {
          if ( v50[0] == 103 )
            goto LABEL_54;
          v27 = v50[0] - 98;
          v26 = v50[0] == 98;
          goto LABEL_83;
        }
        if ( v50[0] == 104 || v50[0] == 105 || v50[0] == 106 )
          goto LABEL_54;
        v15 = v50[0] == 113;
      }
      else
      {
        if ( v50[0] == 97 )
          goto LABEL_54;
        if ( v50[0] > 92 )
        {
          v25 = v50[0] - 93;
          v24 = v50[0] == 93;
          goto LABEL_85;
        }
        switch ( v50[0] )
        {
          case '\\':
          case '5':
            goto LABEL_54;
          case 'X':
            goto LABEL_99;
          case 'Y':
            v16 = v56;
            if ( v10 )
            {
              v22 = v53;
              v18 = v52;
            }
            else
            {
              v22 = v51;
              v18 = v51;
            }
            if ( v22 == -1 )
              v19 = 1;
            else
              v19 = v22 - v18 + 1;
            RegisterRange = RootSignatureVerifier::FindRegisterRange(
                              this,
                              D3D12_DESCRIPTOR_RANGE_TYPE_CBV,
                              VisibilityType,
                              v19,
                              v18,
                              v56);
            if ( !RegisterRange )
            {
              v20 = "Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not full"
                    "y bound in root signature\n";
              goto LABEL_51;
            }
            if ( *((_DWORD *)RegisterRange + 16) == 2 && !*((_DWORD *)RegisterRange + 21) )
            {
              v20 = "Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace%u) is bound to "
                    "a root constants parameter where Num32BitValues == 0. This root parameter cannot provide data to the"
                    " CBV, and therefore this buffer is considered not bound.\n";
LABEL_51:
              LODWORD(v42) = v16;
              v21 = ErrorRootSignature(a3, v20, v18, v19, v42);
LABEL_52:
              v6 = v21;
              if ( v21 < 0 )
                goto LABEL_139;
            }
            goto LABEL_53;
          case 'Z':
            v16 = v55;
            if ( v10 )
            {
              v17 = v53;
              v18 = v52;
            }
            else
            {
              v17 = v51;
              v18 = v51;
            }
            if ( v17 == -1 )
              v19 = 1;
            else
              v19 = v17 - v18 + 1;
            if ( !RootSignatureVerifier::FindRegisterRange(
                    this,
                    D3D12_DESCRIPTOR_RANGE_TYPE_SAMPLER,
                    VisibilityType,
                    v19,
                    v18,
                    v55) )
            {
              v20 = "Shader sampler descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not "
                    "fully bound in root signature\n";
              goto LABEL_51;
            }
            goto LABEL_53;
        }
        v15 = v50[0] == 91;
      }
LABEL_89:
      if ( !v15 )
        goto LABEL_90;
      goto LABEL_54;
    }
    if ( v50[0] > 206 )
      goto LABEL_90;
    if ( v50[0] == 206 )
      goto LABEL_54;
    if ( v50[0] <= 153 )
    {
      if ( v50[0] == 153 || v50[0] == 144 || v50[0] == 145 || v50[0] == 146 || v50[0] == 147 )
        goto LABEL_54;
      v27 = v50[0] - 148;
      v26 = v50[0] == 148;
LABEL_83:
      if ( v26 )
        goto LABEL_54;
      v25 = v27 - 1;
      v24 = v25 == 0;
LABEL_85:
      if ( v24 )
        goto LABEL_54;
      v28 = v25 - 1;
      if ( !v28 )
        goto LABEL_54;
      v29 = v28 - 1;
      if ( !v29 )
        goto LABEL_54;
      v15 = v29 == 1;
      goto LABEL_89;
    }
    if ( v50[0] != 154 && v50[0] != 155 )
    {
      if ( v50[0] == 156 || v50[0] == 157 || v50[0] == 158 )
      {
        if ( v50[0] == 156 )
        {
          v35 = v57;
        }
        else if ( v50[0] == 157 )
        {
          v35 = v55;
        }
        else
        {
          v35 = v56;
        }
        if ( v45 )
        {
          v36 = v53;
          v37 = v52;
        }
        else
        {
          v36 = v51;
          v37 = v51;
        }
        if ( v36 == -1 )
          v38 = 1;
        else
          v38 = v36 - v37 + 1;
        v39 = RootSignatureVerifier::FindRegisterRange(
                this,
                D3D12_DESCRIPTOR_RANGE_TYPE_UAV,
                VisibilityType,
                v38,
                v37,
                v35);
        if ( !v39 )
        {
          LODWORD(v44) = v35;
          v21 = ErrorRootSignature(
                  a3,
                  "Shader UAV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully "
                  "bound in root signature",
                  v37,
                  v38,
                  v44);
          goto LABEL_52;
        }
        if ( *((_DWORD *)v39 + 16) == 1 )
        {
          v40 = v50[0];
          if ( v50[0] == 156 )
          {
            v6 = ErrorRootSignature(
                   a3,
                   "A Shader is declaring a typed UAV using a register mapped to a root descriptor UAV (ShaderRegister=%u"
                   ", RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.",
                   v37,
                   v35);
            if ( v6 < 0 )
              goto LABEL_139;
            v40 = v50[0];
          }
          if ( v40 == 158 && (v55 & 0x800000) != 0 )
          {
            v21 = ErrorRootSignature(
                    a3,
                    "A Shader is declaring a structured UAV with counter using a register mapped to a root descriptor UAV"
                    " (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.",
                    v37,
                    v35);
            goto LABEL_52;
          }
        }
        goto LABEL_53;
      }
      if ( v50[0] != 159 && v50[0] != 160 )
      {
        if ( (unsigned int)(v50[0] - 161) > 1 )
        {
LABEL_90:
          v14 = 1;
          goto LABEL_29;
        }
LABEL_99:
        v30 = -1;
        switch ( v50[0] )
        {
          case 0x58:
            v30 = v57;
            break;
          case 0xA1:
            v30 = v54;
            break;
          case 0xA2:
            v30 = v55;
            break;
        }
        if ( v45 )
        {
          v31 = v53;
          v32 = v52;
        }
        else
        {
          v31 = v51;
          v32 = v51;
        }
        if ( v31 == -1 )
          v33 = 1;
        else
          v33 = v31 - v32 + 1;
        v34 = RootSignatureVerifier::FindRegisterRange(
                this,
                D3D12_DESCRIPTOR_RANGE_TYPE_SRV,
                VisibilityType,
                v33,
                v32,
                v30);
        if ( !v34 )
        {
          LODWORD(v43) = v30;
          v21 = ErrorRootSignature(
                  a3,
                  "Shader SRV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully "
                  "bound in root signature\n",
                  v32,
                  v33,
                  v43);
          goto LABEL_52;
        }
        if ( *((_DWORD *)v34 + 16) == 1 && v50[0] == 88 )
        {
          v21 = ErrorRootSignature(
                  a3,
                  "A Shader is declaring a resource object as a texture using a register mapped to a root descriptor SRV "
                  "(ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.\n",
                  v32,
                  v30);
          goto LABEL_52;
        }
LABEL_53:
        v10 = v45;
        v13 = 1;
      }
    }
LABEL_54:
    v14 = v46;
  }
  if ( v13 && v11 )
    v6 = ErrorRootSignature(
           a3,
           "Shader has root bindings but root signature uses a DENY flag to disallow root binding access to the shader stage.\n");
LABEL_139:
  D3D10ShaderBinary::CInstruction::~CInstruction((D3D10ShaderBinary::CInstruction *)v50);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b50c  mov     [rsp-8+arg_8], rbx
0x18001b511  push    rbp
0x18001b512  push    rsi
0x18001b513  push    rdi
0x18001b514  push    r12
0x18001b516  push    r13
0x18001b518  push    r14
0x18001b51a  push    r15
0x18001b51c  lea     rbp, [rsp-7A0h]
0x18001b524  sub     rsp, 8A0h
0x18001b52b  mov     rax, cs:__security_cookie
0x18001b532  xor     rax, rsp
0x18001b535  mov     [rbp+7D0h+var_40], rax
0x18001b53c  xorps   xmm0, xmm0
0x18001b53f  mov     [rsp+8D0h+var_888], 0
0x18001b548  movdqu  [rsp+8D0h+var_898], xmm0
0x18001b54e  mov     r13, r8
0x18001b551  mov     rbx, rdx
0x18001b554  mov     r15, rcx
0x18001b557  call    ?InitInstructionInfo@D3D10ShaderBinary@@YAXXZ; D3D10ShaderBinary::InitInstructionInfo(void)
0x18001b55c  lea     rcx, [rsp+8D0h+var_880]; this
0x18001b561  call    ??0CInstruction@D3D10ShaderBinary@@QEAA@XZ; D3D10ShaderBinary::CInstruction::CInstruction(void)
0x18001b566  test    rbx, rbx
0x18001b569  jnz     short loc_18001B576
0x18001b56b  mov     r12d, 80070057h
0x18001b571  jmp     loc_18001BA90
0x18001b576  mov     eax, [rbx+4]
0x18001b579  xor     r12d, r12d
0x18001b57c  mov     qword ptr [rsp+8D0h+var_898+8], rbx
0x18001b581  lea     rcx, [rbx+rax*4]
0x18001b585  lea     rax, [rbx+8]
0x18001b589  mov     [rsp+8D0h+var_888], rcx
0x18001b58e  mov     qword ptr [rsp+8D0h+var_898], rax
0x18001b593  lea     esi, [r12+1]
0x18001b598  mov     ecx, [rbx]
0x18001b59a  mov     eax, ecx
0x18001b59c  and     eax, 0F0h
0x18001b5a1  cmp     eax, 50h ; 'P'
0x18001b5a4  ja      short loc_18001B5B2
0x18001b5a6  jnz     short loc_18001B5AD
0x18001b5a8  test    cl, 0Fh
0x18001b5ab  ja      short loc_18001B5B2
0x18001b5ad  xor     dil, dil
0x18001b5b0  jmp     short loc_18001B5B5
0x18001b5b2  mov     dil, sil
0x18001b5b5  shr     ecx, 10h
0x18001b5b8  mov     [rsp+8D0h+var_8A0], dil
0x18001b5bd  call    GetVisibilityType
0x18001b5c2  mov     ecx, eax
0x18001b5c4  mov     [rsp+8D0h+var_89C], eax
0x18001b5c8  xor     r14b, r14b
0x18001b5cb  sub     ecx, esi
0x18001b5cd  jz      loc_18001B658
0x18001b5d3  sub     ecx, esi
0x18001b5d5  jz      short loc_18001B648
0x18001b5d7  sub     ecx, esi
0x18001b5d9  jz      short loc_18001B63B
0x18001b5db  sub     ecx, esi
0x18001b5dd  jz      short loc_18001B62E
0x18001b5df  sub     ecx, esi
0x18001b5e1  jz      short loc_18001B621
0x18001b5e3  sub     ecx, esi
0x18001b5e5  jz      short loc_18001B5ED
0x18001b5e7  cmp     ecx, esi
0x18001b5e9  jnz     short loc_18001B668
0x18001b5eb  jmp     short loc_18001B606
0x18001b5ed  cmp     [r15+203h], r12b
0x18001b5f4  jz      short loc_18001B603
0x18001b5f6  test    dword ptr [r15+218h], 100h
0x18001b601  jz      short loc_18001B60F
0x18001b603  mov     r14b, sil
0x18001b606  cmp     [r15+203h], r12b
0x18001b60d  jz      short loc_18001B61C
0x18001b60f  test    dword ptr [r15+218h], 200h
0x18001b61a  jz      short loc_18001B668
0x18001b61c  mov     r14b, sil
0x18001b61f  jmp     short loc_18001B668
0x18001b621  mov     r14d, [r15+218h]
0x18001b628  shr     r14d, 5
0x18001b62c  jmp     short loc_18001B653
0x18001b62e  mov     r14d, [r15+218h]
0x18001b635  shr     r14d, 4
0x18001b639  jmp     short loc_18001B653
0x18001b63b  mov     r14d, [r15+218h]
0x18001b642  shr     r14d, 3
0x18001b646  jmp     short loc_18001B653
0x18001b648  mov     r14d, [r15+218h]
0x18001b64f  shr     r14d, 2
0x18001b653  and     r14b, sil
0x18001b656  jmp     short loc_18001B668
0x18001b658  test    byte ptr [r15+218h], 2
0x18001b660  movzx   r14d, r14b
0x18001b664  cmovnz  r14d, esi
0x18001b668  xor     bl, bl
0x18001b66a  xor     al, al
0x18001b66c  mov     [rsp+8D0h+var_89F], al
0x18001b670  test    al, al
0x18001b672  jnz     loc_18001BA75
0x18001b678  mov     rax, [rsp+8D0h+var_888]
0x18001b67d  cmp     qword ptr [rsp+8D0h+var_898], rax
0x18001b682  jnb     loc_18001BA75
0x18001b688  lea     rdx, [rsp+8D0h+var_880]; struct D3D10ShaderBinary::CInstruction *
0x18001b68d  lea     rcx, [rsp+8D0h+var_898]; this
0x18001b692  call    ?ParseInstruction@CShaderCodeParser@D3D10ShaderBinary@@QEAAXPEAVCInstruction@2@@Z; D3D10ShaderBinary::CShaderCodeParser::ParseInstruction(D3D10ShaderBinary::CInstruction *)
0x18001b697  mov     ecx, [rsp+8D0h+var_880]
0x18001b69b  cmp     ecx, 8Fh
0x18001b6a1  jg      loc_18001B81E
0x18001b6a7  jz      loc_18001B771
0x18001b6ad  cmp     ecx, 61h ; 'a'
0x18001b6b0  jg      loc_18001B7EE
0x18001b6b6  jz      loc_18001B771
0x18001b6bc  cmp     ecx, 5Ch ; '\'
0x18001b6bf  jg      loc_18001B7E9
0x18001b6c5  jz      loc_18001B771
0x18001b6cb  mov     edx, ecx
0x18001b6cd  sub     edx, 35h ; '5'
0x18001b6d0  jz      loc_18001B771
0x18001b6d6  sub     edx, 23h ; '#'
0x18001b6d9  jz      loc_18001B8E4
0x18001b6df  sub     edx, 1
0x18001b6e2  jz      loc_18001B77A
0x18001b6e8  sub     edx, 1
0x18001b6eb  jz      short loc_18001B6F5
0x18001b6ed  cmp     edx, 1
0x18001b6f0  jmp     loc_18001B888
0x18001b6f5  mov     esi, [rbp+7D0h+var_6C]
0x18001b6fb  test    dil, dil
0x18001b6fe  jz      short loc_18001B708
0x18001b700  mov     ebx, [rbp+7D0h+var_800]
0x18001b703  mov     edi, [rbp+7D0h+var_838]
0x18001b706  jmp     short loc_18001B70E
0x18001b708  mov     ebx, [rsp+8D0h+var_870]
0x18001b70c  mov     edi, ebx
0x18001b70e  cmp     ebx, 0FFFFFFFFh
0x18001b711  jz      short loc_18001B719
0x18001b713  sub     ebx, edi
0x18001b715  inc     ebx
0x18001b717  jmp     short loc_18001B71E
0x18001b719  mov     ebx, 1
0x18001b71e  mov     r8d, [rsp+8D0h+var_89C]; enum D3D12_SHADER_VISIBILITY
0x18001b723  mov     r9d, ebx; unsigned int
0x18001b726  mov     [rsp+8D0h+var_8A8], esi; unsigned int
0x18001b72a  mov     edx, 3; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18001b72f  mov     rcx, r15; this
0x18001b732  mov     dword ptr [rsp+8D0h+var_8B0], edi; unsigned int
0x18001b736  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18001b73b  test    rax, rax
0x18001b73e  jnz     short loc_18001B764
0x18001b740  lea     rdx, aShaderSamplerD; "Shader sampler descriptor range (BaseSh"...
0x18001b747  mov     dword ptr [rsp+8D0h+var_8B0], esi
0x18001b74b  mov     r8d, edi
0x18001b74e  mov     r9d, ebx
0x18001b751  mov     rcx, r13
0x18001b754  call    ErrorRootSignature
0x18001b759  mov     r12d, eax
0x18001b75c  test    eax, eax
0x18001b75e  js      loc_18001BA90
0x18001b764  mov     dil, [rsp+8D0h+var_8A0]
0x18001b769  mov     esi, 1
0x18001b76e  mov     bl, sil
0x18001b771  mov     al, [rsp+8D0h+var_89F]
0x18001b775  jmp     loc_18001B670
0x18001b77a  mov     esi, [rbp+7D0h+var_68]
0x18001b780  test    dil, dil
0x18001b783  jz      short loc_18001B78D
0x18001b785  mov     ebx, [rbp+7D0h+var_800]
0x18001b788  mov     edi, [rbp+7D0h+var_838]
0x18001b78b  jmp     short loc_18001B793
0x18001b78d  mov     ebx, [rsp+8D0h+var_870]
0x18001b791  mov     edi, ebx
0x18001b793  cmp     ebx, 0FFFFFFFFh
0x18001b796  jz      short loc_18001B79E
0x18001b798  sub     ebx, edi
0x18001b79a  inc     ebx
0x18001b79c  jmp     short loc_18001B7A3
0x18001b79e  mov     ebx, 1
0x18001b7a3  mov     r8d, [rsp+8D0h+var_89C]; enum D3D12_SHADER_VISIBILITY
0x18001b7a8  mov     r9d, ebx; unsigned int
0x18001b7ab  mov     [rsp+8D0h+var_8A8], esi; unsigned int
0x18001b7af  mov     edx, 2; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18001b7b4  mov     rcx, r15; this
0x18001b7b7  mov     dword ptr [rsp+8D0h+var_8B0], edi; unsigned int
0x18001b7bb  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18001b7c0  test    rax, rax
0x18001b7c3  jnz     short loc_18001B7D1
0x18001b7c5  lea     rdx, aShaderCbvDescr; "Shader CBV descriptor range (BaseShader"...
0x18001b7cc  jmp     loc_18001B747
0x18001b7d1  cmp     dword ptr [rax+40h], 2
0x18001b7d5  jnz     short loc_18001B764
0x18001b7d7  cmp     dword ptr [rax+54h], 0
0x18001b7db  jnz     short loc_18001B764
0x18001b7dd  lea     rdx, aShaderCbvDescr_2; "Shader CBV descriptor range (BaseShader"...
0x18001b7e4  jmp     loc_18001B747
0x18001b7e9  sub     ecx, 5Dh ; ']'
0x18001b7ec  jmp     short loc_18001B86D
0x18001b7ee  cmp     ecx, 67h ; 'g'
0x18001b7f1  jg      short loc_18001B7FE
0x18001b7f3  jz      loc_18001B771
0x18001b7f9  sub     ecx, 62h ; 'b'
0x18001b7fc  jmp     short loc_18001B864
0x18001b7fe  sub     ecx, 68h ; 'h'
0x18001b801  jz      loc_18001B771
0x18001b807  sub     ecx, 1
0x18001b80a  jz      loc_18001B771
0x18001b810  sub     ecx, 1
0x18001b813  jz      loc_18001B771
0x18001b819  cmp     ecx, 7
0x18001b81c  jmp     short loc_18001B888
0x18001b81e  cmp     ecx, 0CEh
0x18001b824  jg      short loc_18001B88E
0x18001b826  jz      loc_18001B771
0x18001b82c  cmp     ecx, 99h
0x18001b832  jg      short loc_18001B896
0x18001b834  jz      loc_18001B771
0x18001b83a  sub     ecx, 90h
0x18001b840  jz      loc_18001B771
0x18001b846  sub     ecx, 1
0x18001b849  jz      loc_18001B771
0x18001b84f  sub     ecx, 1
0x18001b852  jz      loc_18001B771
0x18001b858  sub     ecx, 1
0x18001b85b  jz      loc_18001B771
0x18001b861  sub     ecx, 1
0x18001b864  jz      loc_18001B771
0x18001b86a  sub     ecx, 1
0x18001b86d  jz      loc_18001B771
0x18001b873  sub     ecx, 1
0x18001b876  jz      loc_18001B771
0x18001b87c  sub     ecx, 1
0x18001b87f  jz      loc_18001B771
0x18001b885  cmp     ecx, 1
0x18001b888  jz      loc_18001B771
0x18001b88e  mov     al, sil
0x18001b891  jmp     loc_18001B66C
0x18001b896  mov     edx, ecx
0x18001b898  sub     edx, 9Ah
0x18001b89e  jz      loc_18001B771
0x18001b8a4  sub     edx, 1
0x18001b8a7  jz      loc_18001B771
0x18001b8ad  sub     edx, 1
0x18001b8b0  jz      loc_18001B993
0x18001b8b6  sub     edx, 1
0x18001b8b9  jz      loc_18001B993
0x18001b8bf  sub     edx, 1
0x18001b8c2  jz      loc_18001B993
0x18001b8c8  sub     edx, 1
0x18001b8cb  jz      loc_18001B771
0x18001b8d1  sub     edx, 1
0x18001b8d4  jz      loc_18001B771
0x18001b8da  sub     edx, 1
0x18001b8dd  jz      short loc_18001B8E4
0x18001b8df  cmp     edx, 1
0x18001b8e2  jnz     short loc_18001B88E
0x18001b8e4  or      edx, 0FFFFFFFFh
0x18001b8e7  mov     edi, edx
0x18001b8e9  sub     ecx, 58h ; 'X'
0x18001b8ec  jz      short loc_18001B908
0x18001b8ee  sub     ecx, 49h ; 'I'
0x18001b8f1  jz      short loc_18001B900
0x18001b8f3  cmp     ecx, 1
0x18001b8f6  jnz     short loc_18001B90E
0x18001b8f8  mov     edi, [rbp+7D0h+var_6C]
0x18001b8fe  jmp     short loc_18001B90E
0x18001b900  mov     edi, [rbp+7D0h+var_70]
0x18001b906  jmp     short loc_18001B90E
0x18001b908  mov     edi, [rbp+7D0h+var_58]
0x18001b90e  cmp     [rsp+8D0h+var_8A0], 0
0x18001b913  jz      short loc_18001B91D
0x18001b915  mov     ebx, [rbp+7D0h+var_800]
0x18001b918  mov     esi, [rbp+7D0h+var_838]
0x18001b91b  jmp     short loc_18001B923
0x18001b91d  mov     ebx, [rsp+8D0h+var_870]
0x18001b921  mov     esi, ebx
0x18001b923  cmp     ebx, edx
0x18001b925  jz      short loc_18001B92D
0x18001b927  sub     ebx, esi
0x18001b929  inc     ebx
0x18001b92b  jmp     short loc_18001B932
0x18001b92d  mov     ebx, 1
0x18001b932  mov     r8d, [rsp+8D0h+var_89C]; enum D3D12_SHADER_VISIBILITY
0x18001b937  mov     r9d, ebx; unsigned int
0x18001b93a  mov     [rsp+8D0h+var_8A8], edi; unsigned int
0x18001b93e  xor     edx, edx; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18001b940  mov     rcx, r15; this
0x18001b943  mov     dword ptr [rsp+8D0h+var_8B0], esi; unsigned int
0x18001b947  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18001b94c  test    rax, rax
0x18001b94f  jz      short loc_18001B980
0x18001b951  cmp     dword ptr [rax+40h], 1
0x18001b955  jnz     loc_18001B764
0x18001b95b  cmp     [rsp+8D0h+var_880], 58h ; 'X'
0x18001b960  jnz     loc_18001B764
0x18001b966  lea     rdx, aAShaderIsDecla; "A Shader is declaring a resource object"...
0x18001b96d  mov     r8d, esi
0x18001b970  mov     r9d, edi
0x18001b973  mov     rcx, r13
0x18001b976  call    ErrorRootSignature
0x18001b97b  jmp     loc_18001B759
0x18001b980  mov     dword ptr [rsp+8D0h+var_8B0], edi
0x18001b984  lea     rdx, aShaderSrvDescr_0; "Shader SRV descriptor range (BaseShader"...
  ... truncated ...
```
