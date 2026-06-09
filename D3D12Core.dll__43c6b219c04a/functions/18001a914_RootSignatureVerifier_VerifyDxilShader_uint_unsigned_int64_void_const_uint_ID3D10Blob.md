# RootSignatureVerifier::VerifyDxilShader(uint,unsigned __int64,void const *,uint,ID3D10Blob * *)

- ea: `0x18001a914`
- end: `0x18001ad7f`
- name: `?VerifyDxilShader@RootSignatureVerifier@@QEAAJI_KPEBXIPEAPEAUID3D10Blob@@@Z`
- size: `1131`
- prototype: `__int64 __usercall@<rax>(RootSignatureVerifier *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, const void *@<r9>, unsigned int, struct ID3D10Blob **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a020`

## callees

- `0x18001a914`
- `0x18003b478`
- `0x18004d2a0`
- `0x180058f70`
- `0x180059134`
- `0x18005e5f8`

## string_xrefs

- `0x18001ab48`: `A Shader is declaring a typed UAV using a register mapped to a root descriptor UAV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18001ac59`: `A Shader is declaring a resource object as a texture using a register mapped to a root descriptor SRV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.\n`
- `0x18001ad0c`: `Shader sampler descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature\n`
- `0x18001acc3`: `Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace%u) is bound to a root constants parameter where Num32BitValues == 0. This root parameter cannot provide data to the CBV, and therefore this buffer is considered not bound.\n`
- `0x18001aca3`: `Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature\n`
- `0x18001abe2`: `Shader UAV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature`
- `0x18001ab6d`: `A Shader is declaring a structured UAV with counter using a register mapped to a root descriptor UAV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18001ac65`: `Shader SRV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u ) is not fully bound in root signature\n`
- `0x18001a9bc`: `Shader uses sampler descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_SAMPLER_HEAP_DIRECTLY_INDEXED flag.\n`
- `0x18001a98a`: `Shader uses resource descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_CBV_SRV_UAV_HEAP_DIRECTLY_INDEXED flag.\n`
- `0x18001ad5b`: `Shader has root bindings but root signature uses a DENY flag to disallow root binding access to the shader stage.\n`
- `0x18001abd9`: `A shader is using atomic int64 operations on a descriptor heap resource (ShaderRegister=%u, RegisterSpace=%u), which the device does not support. Check the AtomicInt64OnDescriptorHeapResourceSupported capability via the CheckFeatureSupport() API.`

## pseudocode

```c
__int64 __fastcall RootSignatureVerifier::VerifyDxilShader(
        RootSignatureVerifier *this,
        unsigned int a2,
        int a3,
        const void *a4,
        unsigned int a5,
        struct ID3D10Blob **a6)
{
  const void *v8; // r9
  int v10; // edi
  enum D3D12_SHADER_VISIBILITY v11; // r10d
  char v12; // r12
  char v13; // bp
  int v14; // ebp
  unsigned int i; // ebx
  _DWORD *v16; // rsi
  unsigned int v17; // r13d
  unsigned int v18; // r14d
  int v19; // ebx
  unsigned int v20; // ebx
  struct RootSignatureVerifier::TreeNode *v21; // rax
  int v22; // eax
  __int64 v23; // rcx
  const char *v24; // rdx
  struct RootSignatureVerifier::TreeNode *v25; // rax
  struct RootSignatureVerifier::TreeNode *RegisterRange; // rax
  unsigned int v27; // ebx
  __int64 v28; // [rsp+20h] [rbp-148h]
  unsigned int v29; // [rsp+30h] [rbp-138h]
  _BYTE v30[48]; // [rsp+40h] [rbp-128h] BYREF
  unsigned int v31; // [rsp+70h] [rbp-F8h]
  unsigned int v32; // [rsp+74h] [rbp-F4h]
  __int64 v33; // [rsp+78h] [rbp-F0h]
  D3D12_SHADER_VISIBILITY VisibilityType; // [rsp+178h] [rbp+10h]

  VisibilityType = (unsigned int)GetVisibilityType(HIWORD(a2));
  DxilPipelineStateValidation::DxilPipelineStateValidation((DxilPipelineStateValidation *)v30);
  if ( !DxilPipelineStateValidation::InitFromPSV0((DxilPipelineStateValidation *)v30, v8, a5) )
    return 2147942487LL;
  v10 = 0;
  if ( (a3 & 0x2000000) != 0 && (*((_DWORD *)this + 134) & 0x400) == 0 )
  {
    v10 = ErrorRootSignature(
            a6,
            "Shader uses resource descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_C"
            "BV_SRV_UAV_HEAP_DIRECTLY_INDEXED flag.\n");
    if ( v10 < 0 )
      return (unsigned int)v10;
  }
  if ( (a3 & 0x4000000) != 0 && (*((_DWORD *)this + 134) & 0x800) == 0 )
  {
    v10 = ErrorRootSignature(
            a6,
            "Shader uses sampler descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_SA"
            "MPLER_HEAP_DIRECTLY_INDEXED flag.\n");
    if ( v10 < 0 )
      return (unsigned int)v10;
  }
  v11 = VisibilityType;
  v12 = 0;
  v13 = 0;
  if ( VisibilityType == D3D12_SHADER_VISIBILITY_VERTEX )
  {
    v13 = (*((_BYTE *)this + 536) & 2) != 0;
  }
  else
  {
    if ( VisibilityType == D3D12_SHADER_VISIBILITY_HULL )
    {
      v14 = *((_DWORD *)this + 134) >> 2;
    }
    else if ( VisibilityType == D3D12_SHADER_VISIBILITY_DOMAIN )
    {
      v14 = *((_DWORD *)this + 134) >> 3;
    }
    else if ( VisibilityType == D3D12_SHADER_VISIBILITY_GEOMETRY )
    {
      v14 = *((_DWORD *)this + 134) >> 4;
    }
    else if ( VisibilityType == D3D12_SHADER_VISIBILITY_PIXEL )
    {
      v14 = *((_DWORD *)this + 134) >> 5;
    }
    else
    {
      if ( VisibilityType != (D3D12_SHADER_VISIBILITY_GEOMETRY|D3D12_SHADER_VISIBILITY_HULL) )
      {
        if ( VisibilityType == (D3D12_SHADER_VISIBILITY_PIXEL|D3D12_SHADER_VISIBILITY_HULL) )
          v13 = (*((_DWORD *)this + 134) & 0x200) != 0;
        goto LABEL_24;
      }
      v14 = *((_DWORD *)this + 134) >> 8;
    }
    v13 = v14 & 1;
  }
LABEL_24:
  for ( i = 0; ; i = v29 + 1 )
  {
    v29 = i;
    if ( i >= v31 )
      break;
    if ( v33 && v32 >= 0x10 && i * (unsigned __int64)v32 <= 0xFFFFFFFF )
      v16 = (_DWORD *)(v33 + i * v32);
    else
      v16 = 0;
    v17 = v16[1];
    v18 = v16[2];
    v19 = v16[3];
    switch ( *v16 )
    {
      case 1:
        v12 = 1;
        if ( v19 == -1 )
          v27 = 1;
        else
          v27 = v19 - v18 + 1;
        if ( !RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_SAMPLER, v11, v27, v18, v16[1]) )
        {
          v10 = ErrorRootSignature(
                  a6,
                  "Shader sampler descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fu"
                  "lly bound in root signature\n",
                  v18,
                  v27,
                  v17);
          if ( v10 < 0 )
            return (unsigned int)v10;
        }
        goto LABEL_82;
      case 2:
        if ( v19 == -1 )
          v20 = 1;
        else
          v20 = v19 - v18 + 1;
        RegisterRange = RootSignatureVerifier::FindRegisterRange(
                          this,
                          D3D12_DESCRIPTOR_RANGE_TYPE_CBV,
                          v11,
                          v20,
                          v18,
                          v16[1]);
        if ( !RegisterRange )
        {
          v24 = "Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bo"
                "und in root signature\n";
          goto LABEL_58;
        }
        if ( *((_DWORD *)RegisterRange + 16) == 2 && !*((_DWORD *)RegisterRange + 21) )
        {
          v24 = "Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace%u) is bound to a ro"
                "ot constants parameter where Num32BitValues == 0. This root parameter cannot provide data to the CBV, an"
                "d therefore this buffer is considered not bound.\n";
LABEL_58:
          LODWORD(v28) = v17;
          v22 = ErrorRootSignature(a6, v24, v18, v20, v28);
LABEL_59:
          v10 = v22;
          if ( v22 < 0 )
            return (unsigned int)v10;
        }
LABEL_60:
        v12 = 1;
LABEL_82:
        v11 = VisibilityType;
        continue;
      case 3:
      case 4:
      case 5:
        if ( v19 == -1 )
          v20 = 1;
        else
          v20 = v19 - v18 + 1;
        v25 = RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_SRV, v11, v20, v18, v16[1]);
        if ( !v25 )
        {
          v24 = "Shader SRV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u ) is not fully b"
                "ound in root signature\n";
          goto LABEL_58;
        }
        if ( *((_DWORD *)v25 + 16) == 1 && *v16 == 3 )
        {
          v22 = ErrorRootSignature(
                  a6,
                  "A Shader is declaring a resource object as a texture using a register mapped to a root descriptor SRV "
                  "(ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.\n",
                  v18,
                  v17);
          goto LABEL_59;
        }
        goto LABEL_60;
    }
    if ( *v16 == 6 || *v16 == 7 || (unsigned int)(*v16 - 8) <= 1 )
    {
      if ( v19 == -1 )
        v20 = 1;
      else
        v20 = v19 - v18 + 1;
      v21 = RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_UAV, v11, v20, v18, v16[1]);
      if ( !v21 )
      {
        v24 = "Shader UAV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully boun"
              "d in root signature";
        goto LABEL_58;
      }
      if ( *((_DWORD *)v21 + 16) == 1 )
      {
        if ( *v16 == 6 )
        {
          v10 = ErrorRootSignature(
                  a6,
                  "A Shader is declaring a typed UAV using a register mapped to a root descriptor UAV (ShaderRegister=%u,"
                  " RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.",
                  v18,
                  v17);
          if ( v10 < 0 )
            return (unsigned int)v10;
        }
        if ( *v16 == 9 )
        {
          v22 = ErrorRootSignature(
                  a6,
                  "A Shader is declaring a structured UAV with counter using a register mapped to a root descriptor UAV ("
                  "ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.",
                  v18,
                  v17);
          goto LABEL_59;
        }
      }
      else if ( !*((_DWORD *)v21 + 16) )
      {
        if ( v33 )
        {
          if ( v29 < v31 && v32 >= 0x18 && v29 * (unsigned __int64)v32 <= 0xFFFFFFFF )
          {
            v23 = v33 + v29 * v32;
            if ( v23 )
            {
              if ( (*(_BYTE *)(v23 + 20) & 1) != 0 && !*((_BYTE *)this + 516) )
              {
                v22 = ErrorRootSignature(
                        a6,
                        "A shader is using atomic int64 operations on a descriptor heap resource (ShaderRegister=%u, Regi"
                        "sterSpace=%u), which the device does not support. Check the AtomicInt64OnDescriptorHeapResourceS"
                        "upported capability via the CheckFeatureSupport() API.",
                        v18,
                        v17);
                goto LABEL_59;
              }
            }
          }
        }
      }
      goto LABEL_60;
    }
  }
  if ( v12 && v13 )
    return (unsigned int)ErrorRootSignature(
                           a6,
                           "Shader has root bindings but root signature uses a DENY flag to disallow root binding access "
                           "to the shader stage.\n");
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001a914  push    rbx
0x18001a916  push    rbp
0x18001a917  push    rsi
0x18001a918  push    rdi
0x18001a919  push    r12
0x18001a91b  push    r13
0x18001a91d  push    r14
0x18001a91f  push    r15
0x18001a921  sub     rsp, 128h
0x18001a928  mov     r15, rcx
0x18001a92b  shr     edx, 10h
0x18001a92e  mov     ecx, edx
0x18001a930  mov     rbx, r8
0x18001a933  call    GetVisibilityType
0x18001a938  lea     rcx, [rsp+168h+var_128]; this
0x18001a93d  mov     [rsp+168h+arg_8], eax
0x18001a944  call    ??0DxilPipelineStateValidation@@QEAA@XZ; DxilPipelineStateValidation::DxilPipelineStateValidation(void)
0x18001a949  mov     r8d, [rsp+168h+arg_20]; unsigned int
0x18001a951  lea     rcx, [rsp+168h+var_128]; this
0x18001a956  mov     rdx, r9; void *
0x18001a959  call    ?InitFromPSV0@DxilPipelineStateValidation@@QEAA_NPEBXI@Z; DxilPipelineStateValidation::InitFromPSV0(void const *,uint)
0x18001a95e  test    al, al
0x18001a960  jnz     short loc_18001A96C
0x18001a962  mov     eax, 80070057h
0x18001a967  jmp     loc_18001AD6B
0x18001a96c  xor     edi, edi
0x18001a96e  bt      rbx, 19h
0x18001a973  jnb     short loc_18001A9A0
0x18001a975  test    dword ptr [r15+218h], 400h
0x18001a980  jnz     short loc_18001A9A0
0x18001a982  mov     rcx, [rsp+168h+arg_28]
0x18001a98a  lea     rdx, aShaderUsesReso_1; "Shader uses resource descriptor heap in"...
0x18001a991  call    ErrorRootSignature
0x18001a996  mov     edi, eax
0x18001a998  test    eax, eax
0x18001a99a  js      loc_18001AD69
0x18001a9a0  bt      rbx, 1Ah
0x18001a9a5  jnb     short loc_18001A9D2
0x18001a9a7  test    dword ptr [r15+218h], 800h
0x18001a9b2  jnz     short loc_18001A9D2
0x18001a9b4  mov     rcx, [rsp+168h+arg_28]
0x18001a9bc  lea     rdx, aShaderUsesSamp; "Shader uses sampler descriptor heap ind"...
0x18001a9c3  call    ErrorRootSignature
0x18001a9c8  mov     edi, eax
0x18001a9ca  test    eax, eax
0x18001a9cc  js      loc_18001AD69
0x18001a9d2  mov     r10d, [rsp+168h+arg_8]
0x18001a9da  xor     r12b, r12b
0x18001a9dd  mov     ecx, r10d
0x18001a9e0  xor     bpl, bpl
0x18001a9e3  mov     r11d, 1
0x18001a9e9  sub     ecx, r11d
0x18001a9ec  jz      short loc_18001AA5D
0x18001a9ee  sub     ecx, r11d
0x18001a9f1  jz      short loc_18001AA4E
0x18001a9f3  sub     ecx, r11d
0x18001a9f6  jz      short loc_18001AA42
0x18001a9f8  sub     ecx, r11d
0x18001a9fb  jz      short loc_18001AA36
0x18001a9fd  sub     ecx, r11d
0x18001aa00  jz      short loc_18001AA2A
0x18001aa02  sub     ecx, r11d
0x18001aa05  jz      short loc_18001AA1E
0x18001aa07  cmp     ecx, r11d
0x18001aa0a  jnz     short loc_18001AA6D
0x18001aa0c  test    dword ptr [r15+218h], 200h
0x18001aa17  jz      short loc_18001AA6D
0x18001aa19  mov     bpl, r11b
0x18001aa1c  jmp     short loc_18001AA6D
0x18001aa1e  mov     ebp, [r15+218h]
0x18001aa25  shr     ebp, 8
0x18001aa28  jmp     short loc_18001AA58
0x18001aa2a  mov     ebp, [r15+218h]
0x18001aa31  shr     ebp, 5
0x18001aa34  jmp     short loc_18001AA58
0x18001aa36  mov     ebp, [r15+218h]
0x18001aa3d  shr     ebp, 4
0x18001aa40  jmp     short loc_18001AA58
0x18001aa42  mov     ebp, [r15+218h]
0x18001aa49  shr     ebp, 3
0x18001aa4c  jmp     short loc_18001AA58
0x18001aa4e  mov     ebp, [r15+218h]
0x18001aa55  shr     ebp, 2
0x18001aa58  and     bpl, r11b
0x18001aa5b  jmp     short loc_18001AA6D
0x18001aa5d  test    byte ptr [r15+218h], 2
0x18001aa65  movzx   ebp, bpl
0x18001aa69  cmovnz  ebp, r11d
0x18001aa6d  xor     ebx, ebx
0x18001aa6f  mov     r9d, 0FFFFFFFFh
0x18001aa75  mov     [rsp+168h+var_138], ebx
0x18001aa79  cmp     ebx, [rsp+168h+var_F8]
0x18001aa7d  jnb     loc_18001AD49
0x18001aa83  mov     r8, [rsp+168h+var_F0]
0x18001aa88  test    r8, r8
0x18001aa8b  jz      short loc_18001AAAD
0x18001aa8d  mov     edx, [rsp+168h+var_F4]
0x18001aa91  cmp     edx, 10h
0x18001aa94  jb      short loc_18001AAAD
0x18001aa96  mov     ecx, edx
0x18001aa98  mov     eax, ebx
0x18001aa9a  imul    rcx, rax
0x18001aa9e  cmp     rcx, r9
0x18001aaa1  ja      short loc_18001AAAD
0x18001aaa3  imul    edx, ebx
0x18001aaa6  mov     esi, edx
0x18001aaa8  add     rsi, r8
0x18001aaab  jmp     short loc_18001AAAF
0x18001aaad  xor     esi, esi
0x18001aaaf  mov     ecx, [rsi]
0x18001aab1  mov     r13d, [rsi+4]
0x18001aab5  mov     r14d, [rsi+8]
0x18001aab9  mov     ebx, [rsi+0Ch]
0x18001aabc  sub     ecx, 1
0x18001aabf  jz      loc_18001ACCF
0x18001aac5  sub     ecx, 1
0x18001aac8  jz      loc_18001AC71
0x18001aace  sub     ecx, 1
0x18001aad1  jz      loc_18001AC19
0x18001aad7  sub     ecx, 1
0x18001aada  jz      loc_18001AC19
0x18001aae0  sub     ecx, 1
0x18001aae3  jz      loc_18001AC19
0x18001aae9  sub     ecx, 1
0x18001aaec  jz      short loc_18001AB01
0x18001aaee  sub     ecx, 1
0x18001aaf1  jz      short loc_18001AB01
0x18001aaf3  sub     ecx, 1
0x18001aaf6  jz      short loc_18001AB01
0x18001aaf8  cmp     ecx, 1
0x18001aafb  jnz     loc_18001AD3D
0x18001ab01  cmp     ebx, r9d
0x18001ab04  jz      short loc_18001AB0E
0x18001ab06  sub     ebx, r14d
0x18001ab09  add     ebx, r11d
0x18001ab0c  jmp     short loc_18001AB11
0x18001ab0e  mov     ebx, r11d
0x18001ab11  mov     [rsp+168h+var_140], r13d; unsigned int
0x18001ab16  mov     r9d, ebx; unsigned int
0x18001ab19  mov     r8d, r10d; enum D3D12_SHADER_VISIBILITY
0x18001ab1c  mov     dword ptr [rsp+168h+var_148], r14d; unsigned int
0x18001ab21  mov     edx, r11d; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18001ab24  mov     rcx, r15; this
0x18001ab27  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18001ab2c  test    rax, rax
0x18001ab2f  jz      loc_18001ABE2
0x18001ab35  cmp     dword ptr [rax+40h], 1
0x18001ab39  jnz     short loc_18001AB89
0x18001ab3b  cmp     dword ptr [rsi], 6
0x18001ab3e  jnz     short loc_18001AB64
0x18001ab40  mov     rcx, [rsp+168h+arg_28]
0x18001ab48  lea     rdx, aAShaderIsDecla_2; "A Shader is declaring a typed UAV using"...
0x18001ab4f  mov     r9d, r13d
0x18001ab52  mov     r8d, r14d
0x18001ab55  call    ErrorRootSignature
0x18001ab5a  mov     edi, eax
0x18001ab5c  test    eax, eax
0x18001ab5e  js      loc_18001AD69
0x18001ab64  cmp     dword ptr [rsi], 9
0x18001ab67  jnz     loc_18001AC0B
0x18001ab6d  lea     rdx, aAShaderIsDecla_0; "A Shader is declaring a structured UAV "...
0x18001ab74  mov     rcx, [rsp+168h+arg_28]
0x18001ab7c  mov     r9d, r13d
0x18001ab7f  mov     r8d, r14d
0x18001ab82  call    ErrorRootSignature
0x18001ab87  jmp     short loc_18001AC01
0x18001ab89  cmp     dword ptr [rax+40h], 0
0x18001ab8d  jnz     short loc_18001AC0B
0x18001ab8f  mov     r8, [rsp+168h+var_F0]
0x18001ab94  test    r8, r8
0x18001ab97  jz      short loc_18001AC0B
0x18001ab99  mov     r9d, [rsp+168h+var_138]
0x18001ab9e  cmp     r9d, [rsp+168h+var_F8]
0x18001aba3  jnb     short loc_18001AC0B
0x18001aba5  mov     edx, [rsp+168h+var_F4]
0x18001aba9  cmp     edx, 18h
0x18001abac  jb      short loc_18001AC0B
0x18001abae  mov     ecx, edx
0x18001abb0  mov     eax, 0FFFFFFFFh
0x18001abb5  imul    rcx, r9
0x18001abb9  cmp     rcx, rax
0x18001abbc  ja      short loc_18001AC0B
0x18001abbe  imul    edx, r9d
0x18001abc2  mov     ecx, edx
0x18001abc4  add     rcx, r8
0x18001abc7  jz      short loc_18001AC0B
0x18001abc9  test    byte ptr [rcx+14h], 1
0x18001abcd  jz      short loc_18001AC0B
0x18001abcf  cmp     byte ptr [r15+204h], 0
0x18001abd7  jnz     short loc_18001AC0B
0x18001abd9  lea     rdx, aAShaderIsUsing; "A shader is using atomic int64 operatio"...
0x18001abe0  jmp     short loc_18001AB74
0x18001abe2  lea     rdx, aShaderUavDescr; "Shader UAV descriptor range (BaseShader"...
0x18001abe9  mov     rcx, [rsp+168h+arg_28]
0x18001abf1  mov     r8d, r14d
0x18001abf4  mov     r9d, ebx
0x18001abf7  mov     dword ptr [rsp+168h+var_148], r13d
0x18001abfc  call    ErrorRootSignature
0x18001ac01  mov     edi, eax
0x18001ac03  test    eax, eax
0x18001ac05  js      loc_18001AD69
0x18001ac0b  mov     r11d, 1
0x18001ac11  mov     r12b, r11b
0x18001ac14  jmp     loc_18001AD2F
0x18001ac19  cmp     ebx, r9d
0x18001ac1c  jz      short loc_18001AC26
0x18001ac1e  sub     ebx, r14d
0x18001ac21  add     ebx, r11d
0x18001ac24  jmp     short loc_18001AC29
0x18001ac26  mov     ebx, r11d
0x18001ac29  mov     [rsp+168h+var_140], r13d; unsigned int
0x18001ac2e  mov     r9d, ebx; unsigned int
0x18001ac31  mov     r8d, r10d; enum D3D12_SHADER_VISIBILITY
0x18001ac34  mov     dword ptr [rsp+168h+var_148], r14d; unsigned int
0x18001ac39  xor     edx, edx; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18001ac3b  mov     rcx, r15; this
0x18001ac3e  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18001ac43  test    rax, rax
0x18001ac46  jz      short loc_18001AC65
0x18001ac48  mov     r11d, 1
0x18001ac4e  cmp     [rax+40h], r11d
0x18001ac52  jnz     short loc_18001AC11
0x18001ac54  cmp     dword ptr [rsi], 3
0x18001ac57  jnz     short loc_18001AC11
0x18001ac59  lea     rdx, aAShaderIsDecla; "A Shader is declaring a resource object"...
0x18001ac60  jmp     loc_18001AB74
0x18001ac65  lea     rdx, aShaderSrvDescr_2; "Shader SRV descriptor range (BaseShader"...
0x18001ac6c  jmp     loc_18001ABE9
0x18001ac71  cmp     ebx, r9d
0x18001ac74  jz      short loc_18001AC7E
0x18001ac76  sub     ebx, r14d
0x18001ac79  add     ebx, r11d
0x18001ac7c  jmp     short loc_18001AC81
0x18001ac7e  mov     ebx, r11d
0x18001ac81  mov     [rsp+168h+var_140], r13d; unsigned int
0x18001ac86  mov     r9d, ebx; unsigned int
0x18001ac89  mov     r8d, r10d; enum D3D12_SHADER_VISIBILITY
0x18001ac8c  mov     dword ptr [rsp+168h+var_148], r14d; unsigned int
0x18001ac91  mov     edx, 2; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18001ac96  mov     rcx, r15; this
0x18001ac99  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18001ac9e  test    rax, rax
0x18001aca1  jnz     short loc_18001ACAF
0x18001aca3  lea     rdx, aShaderCbvDescr; "Shader CBV descriptor range (BaseShader"...
0x18001acaa  jmp     loc_18001ABE9
0x18001acaf  cmp     dword ptr [rax+40h], 2
0x18001acb3  jnz     loc_18001AC0B
0x18001acb9  cmp     dword ptr [rax+54h], 0
0x18001acbd  jnz     loc_18001AC0B
0x18001acc3  lea     rdx, aShaderCbvDescr_2; "Shader CBV descriptor range (BaseShader"...
0x18001acca  jmp     loc_18001ABE9
0x18001accf  mov     r12b, r11b
0x18001acd2  cmp     ebx, r9d
0x18001acd5  jz      short loc_18001ACDF
0x18001acd7  sub     ebx, r14d
0x18001acda  add     ebx, r11d
0x18001acdd  jmp     short loc_18001ACE2
0x18001acdf  mov     ebx, r11d
0x18001ace2  mov     [rsp+168h+var_140], r13d; unsigned int
0x18001ace7  mov     r9d, ebx; unsigned int
0x18001acea  mov     r8d, r10d; enum D3D12_SHADER_VISIBILITY
0x18001aced  mov     dword ptr [rsp+168h+var_148], r14d; unsigned int
0x18001acf2  mov     edx, 3; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18001acf7  mov     rcx, r15; this
0x18001acfa  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18001acff  test    rax, rax
0x18001ad02  jnz     short loc_18001AD29
0x18001ad04  mov     rcx, [rsp+168h+arg_28]
0x18001ad0c  lea     rdx, aShaderSamplerD; "Shader sampler descriptor range (BaseSh"...
0x18001ad13  mov     r9d, ebx
0x18001ad16  mov     dword ptr [rsp+168h+var_148], r13d
0x18001ad1b  mov     r8d, r14d
0x18001ad1e  call    ErrorRootSignature
0x18001ad23  mov     edi, eax
0x18001ad25  test    eax, eax
0x18001ad27  js      short loc_18001AD69
0x18001ad29  mov     r11d, 1
0x18001ad2f  mov     r10d, [rsp+168h+arg_8]
0x18001ad37  mov     r9d, 0FFFFFFFFh
0x18001ad3d  mov     ebx, [rsp+168h+var_138]
0x18001ad41  add     ebx, r11d
0x18001ad44  jmp     loc_18001AA75
0x18001ad49  test    r12b, r12b
0x18001ad4c  jz      short loc_18001AD69
0x18001ad4e  test    bpl, bpl
0x18001ad51  jz      short loc_18001AD69
0x18001ad53  mov     rcx, [rsp+168h+arg_28]
0x18001ad5b  lea     rdx, aShaderHasRootB; "Shader has root bindings but root signa"...
0x18001ad62  call    ErrorRootSignature
0x18001ad67  mov     edi, eax
0x18001ad69  mov     eax, edi
0x18001ad6b  add     rsp, 128h
0x18001ad72  pop     r15
0x18001ad74  pop     r14
0x18001ad76  pop     r13
0x18001ad78  pop     r12
0x18001ad7a  pop     rdi
0x18001ad7b  pop     rsi
0x18001ad7c  pop     rbp
0x18001ad7d  pop     rbx
  ... truncated ...
```
