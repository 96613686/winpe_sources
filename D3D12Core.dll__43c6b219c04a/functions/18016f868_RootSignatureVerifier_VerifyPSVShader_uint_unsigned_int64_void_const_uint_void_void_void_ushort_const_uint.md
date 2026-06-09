# RootSignatureVerifier::VerifyPSVShader(uint,unsigned __int64,void const *,uint,void *,void (*)(void *,ushort const *,uint))

- ea: `0x18016f868`
- end: `0x18016fd5c`
- name: `?VerifyPSVShader@RootSignatureVerifier@@QEAAXI_KPEBXIPEAXP6AX2PEBGI@Z@Z`
- size: `1268`
- prototype: `void __usercall(RootSignatureVerifier *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, const void *@<r9>, unsigned int, void *, void (*)(void *, const unsigned __int16 *, unsigned int))`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18016c4c4`

## callees

- `0x18004d2a0`
- `0x180058f70`
- `0x180059134`
- `0x180073074`
- `0x18016f868`

## string_xrefs

- `0x18016fae6`: `A Shader is declaring a typed UAV using a register mapped to a root descriptor UAV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18016fb0d`: `A Shader is declaring a structured UAV with counter using a register mapped to a root descriptor UAV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18016fbf7`: `A shader is using atomic int64 operations on a descriptor heap resource (ShaderRegister=%u, RegisterSpace=%u), which the device does not support. Check the AtomicInt64OnDescriptorHeapResourceSupported capability via the CheckFeatureSupport() API.`
- `0x18016f96a`: `Shader uses sampler descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_SAMPLER_HEAP_DIRECTLY_INDEXED flag.`
- `0x18016f938`: `Shader uses resource descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_CBV_SRV_UAV_HEAP_DIRECTLY_INDEXED flag.`
- `0x18016fcc1`: `Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature.`
- `0x18016fc76`: `A Shader is declaring a resource object as a texture using a register mapped to a root descriptor SRV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18016fc09`: `Shader UAV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature.`
- `0x18016fc82`: `Shader SRV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u ) is not fully bound in root signature.`
- `0x18016fd1f`: `Shader sampler descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in root signature`
- `0x18016fb67`: `Shader has root bindings but root signature uses a DENY flag to disallow root binding access to the shader stage.`

## pseudocode

```c
void __fastcall RootSignatureVerifier::VerifyPSVShader(
        RootSignatureVerifier *this,
        unsigned int a2,
        int a3,
        const void *a4,
        unsigned int a5,
        void *a6)
{
  unsigned int v6; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  enum D3D12_SHADER_VISIBILITY v14; // r14d
  const void *v15; // r9
  char v16; // bp
  int v17; // ebp
  unsigned int v18; // r12d
  _DWORD *v19; // rdi
  unsigned int v20; // r15d
  unsigned int v21; // esi
  int v22; // ebx
  unsigned int v23; // ebx
  struct RootSignatureVerifier::TreeNode *v24; // rax
  const char *v25; // r9
  __int64 v26; // r8
  char v27; // di
  __int64 v28; // rcx
  const char *v29; // r9
  struct RootSignatureVerifier::TreeNode *RegisterRange; // rax
  unsigned int v31; // ebx
  __int64 v32; // [rsp+20h] [rbp-148h]
  __int64 v33; // [rsp+28h] [rbp-140h]
  __int64 v34; // [rsp+30h] [rbp-138h]
  _BYTE v35[48]; // [rsp+40h] [rbp-128h] BYREF
  unsigned int v36; // [rsp+70h] [rbp-F8h]
  unsigned int v37; // [rsp+74h] [rbp-F4h]
  __int64 v38; // [rsp+78h] [rbp-F0h]
  char v39; // [rsp+178h] [rbp+10h]
  char v41; // [rsp+1A0h] [rbp+38h]

  v6 = HIWORD(a2);
  if ( v6 )
  {
    v9 = v6 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 9;
            if ( v13 )
            {
              if ( v13 == 1 )
                v14 = D3D12_SHADER_VISIBILITY_GEOMETRY|D3D12_SHADER_VISIBILITY_HULL;
              else
                v14 = D3D12_SHADER_VISIBILITY_ALL;
            }
            else
            {
              v14 = D3D12_SHADER_VISIBILITY_PIXEL|D3D12_SHADER_VISIBILITY_HULL;
            }
          }
          else
          {
            v14 = D3D12_SHADER_VISIBILITY_DOMAIN;
          }
        }
        else
        {
          v14 = D3D12_SHADER_VISIBILITY_HULL;
        }
      }
      else
      {
        v14 = D3D12_SHADER_VISIBILITY_GEOMETRY;
      }
    }
    else
    {
      v14 = D3D12_SHADER_VISIBILITY_VERTEX;
    }
  }
  else
  {
    v14 = D3D12_SHADER_VISIBILITY_PIXEL;
  }
  DxilPipelineStateValidation::DxilPipelineStateValidation((DxilPipelineStateValidation *)v35);
  if ( !DxilPipelineStateValidation::InitFromPSV0((DxilPipelineStateValidation *)v35, v15, a5) )
    return;
  v39 = 0;
  v41 = 0;
  if ( (a3 & 0x2000000) != 0 && (*((_DWORD *)this + 134) & 0x400) == 0 )
    ErrorLibraryFunction(
      a6,
      StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
      3,
      "Shader uses resource descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_CBV_SRV"
      "_UAV_HEAP_DIRECTLY_INDEXED flag.");
  if ( (a3 & 0x4000000) != 0 && (*((_DWORD *)this + 134) & 0x800) == 0 )
    ErrorLibraryFunction(
      a6,
      StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
      3,
      "Shader uses sampler descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_SAMPLER_"
      "HEAP_DIRECTLY_INDEXED flag.");
  switch ( v14 )
  {
    case D3D12_SHADER_VISIBILITY_VERTEX:
      v16 = (*((_BYTE *)this + 536) & 2) != 0;
      goto LABEL_39;
    case D3D12_SHADER_VISIBILITY_HULL:
      v17 = *((_DWORD *)this + 134) >> 2;
      goto LABEL_33;
    case D3D12_SHADER_VISIBILITY_DOMAIN:
      v17 = *((_DWORD *)this + 134) >> 3;
      goto LABEL_33;
    case D3D12_SHADER_VISIBILITY_GEOMETRY:
      v17 = *((_DWORD *)this + 134) >> 4;
      goto LABEL_33;
    case D3D12_SHADER_VISIBILITY_PIXEL:
      v17 = *((_DWORD *)this + 134) >> 5;
      goto LABEL_33;
    case D3D12_SHADER_VISIBILITY_GEOMETRY|D3D12_SHADER_VISIBILITY_HULL:
      v17 = *((_DWORD *)this + 134) >> 8;
LABEL_33:
      v16 = v17 & 1;
      goto LABEL_39;
  }
  if ( v14 == (D3D12_SHADER_VISIBILITY_PIXEL|D3D12_SHADER_VISIBILITY_HULL) && (*((_DWORD *)this + 134) & 0x200) != 0 )
  {
    v16 = 1;
LABEL_39:
    v41 = v16;
  }
  v18 = 0;
  if ( !v36 )
    return;
  do
  {
    if ( v38 && v18 < v36 && v37 >= 0x10 && v18 * (unsigned __int64)v37 <= 0xFFFFFFFF )
      v19 = (_DWORD *)(v38 + v18 * v37);
    else
      v19 = 0;
    v20 = v19[1];
    v21 = v19[2];
    v22 = v19[3];
    switch ( *v19 )
    {
      case 1:
        v39 = 1;
        v27 = 1;
        if ( v22 == -1 )
          v31 = 1;
        else
          v31 = v22 - v21 + 1;
        if ( !RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_SAMPLER, v14, v31, v21, v20) )
          ErrorLibraryFunction(
            a6,
            StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
            1,
            "Shader sampler descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bo"
            "und in root signature",
            v21,
            v31,
            v20);
        break;
      case 2:
        v39 = 1;
        if ( v22 == -1 )
          v23 = 1;
        else
          v23 = v22 - v21 + 1;
        if ( !RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_CBV, v14, v23, v21, v20) )
        {
          v29 = "Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bo"
                "und in root signature.";
          goto LABEL_82;
        }
LABEL_96:
        v27 = 1;
        break;
      case 3:
      case 4:
      case 5:
        v39 = 1;
        if ( v22 == -1 )
          v23 = 1;
        else
          v23 = v22 - v21 + 1;
        RegisterRange = RootSignatureVerifier::FindRegisterRange(
                          this,
                          D3D12_DESCRIPTOR_RANGE_TYPE_SRV,
                          v14,
                          v23,
                          v21,
                          v20);
        if ( !RegisterRange )
        {
          v29 = "Shader SRV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u ) is not fully b"
                "ound in root signature.";
          goto LABEL_82;
        }
        if ( *((_DWORD *)RegisterRange + 16) == 1 && *v19 == 3 )
        {
          v25 = "A Shader is declaring a resource object as a texture using a register mapped to a root descriptor SRV (S"
                "haderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.";
          goto LABEL_64;
        }
        goto LABEL_96;
      default:
        if ( *v19 == 6 || *v19 == 7 || (unsigned int)(*v19 - 8) <= 1 )
        {
          v39 = 1;
          if ( v22 == -1 )
            v23 = 1;
          else
            v23 = v22 - v21 + 1;
          v24 = RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_UAV, v14, v23, v21, v20);
          if ( !v24 )
          {
            v29 = "Shader UAV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully "
                  "bound in root signature.";
LABEL_82:
            LODWORD(v34) = v20;
            LODWORD(v33) = v23;
            LODWORD(v32) = v21;
            ErrorLibraryFunction(
              a6,
              StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
              1,
              v29,
              v32,
              v33,
              v34);
            goto LABEL_66;
          }
          if ( *((_DWORD *)v24 + 16) == 1 )
          {
            if ( *v19 == 6 )
              ErrorLibraryFunction(
                a6,
                StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
                2,
                "A Shader is declaring a typed UAV using a register mapped to a root descriptor UAV (ShaderRegister=%u, R"
                "egisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.",
                v21,
                v20);
            if ( *v19 != 9 )
              goto LABEL_66;
            v25 = "A Shader is declaring a structured UAV with counter using a register mapped to a root descriptor UAV ("
                  "ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.";
LABEL_64:
            v26 = 2;
            goto LABEL_65;
          }
          if ( *((_DWORD *)v24 + 16) || !v38 || v18 >= v36 )
            goto LABEL_66;
          if ( v37 >= 0x18 && v18 * (unsigned __int64)v37 <= 0xFFFFFFFF )
          {
            v28 = v38 + v18 * v37;
            if ( v28 )
            {
              if ( (*(_BYTE *)(v28 + 20) & 1) != 0 && !*((_BYTE *)this + 516) )
              {
                v25 = "A shader is using atomic int64 operations on a descriptor heap resource (ShaderRegister=%u, Regist"
                      "erSpace=%u), which the device does not support. Check the AtomicInt64OnDescriptorHeapResourceSuppo"
                      "rted capability via the CheckFeatureSupport() API.";
                v26 = 3;
LABEL_65:
                LODWORD(v33) = v20;
                LODWORD(v32) = v21;
                ErrorLibraryFunction(
                  a6,
                  StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
                  v26,
                  v25,
                  v32,
                  v33);
LABEL_66:
                v27 = 1;
                break;
              }
            }
          }
          v27 = 1;
        }
        else
        {
          v27 = v39;
        }
        break;
    }
    ++v18;
  }
  while ( v18 < v36 );
  if ( v27 )
  {
    if ( v41 )
      ErrorLibraryFunction(
        a6,
        StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
        2,
        "Shader has root bindings but root signature uses a DENY flag to disallow root binding access to the shader stage.");
  }
}

```

## disassembly

```asm
0x18016f868  push    rbx
0x18016f86a  push    rbp
0x18016f86b  push    rsi
0x18016f86c  push    rdi
0x18016f86d  push    r12
0x18016f86f  push    r13
0x18016f871  push    r14
0x18016f873  push    r15
0x18016f875  sub     rsp, 128h
0x18016f87c  mov     esi, 1
0x18016f881  shr     edx, 10h
0x18016f884  mov     rbx, r8
0x18016f887  mov     r13, rcx
0x18016f88a  lea     r15d, [rsi+2]
0x18016f88e  test    edx, edx
0x18016f890  jz      short loc_18016F8DA
0x18016f892  sub     edx, esi
0x18016f894  jz      short loc_18016F8D5
0x18016f896  sub     edx, esi
0x18016f898  jz      short loc_18016F8CD
0x18016f89a  sub     edx, esi
0x18016f89c  jz      short loc_18016F8C5
0x18016f89e  sub     edx, esi
0x18016f8a0  jz      short loc_18016F8C0
0x18016f8a2  sub     edx, 9
0x18016f8a5  jz      short loc_18016F8B8
0x18016f8a7  cmp     edx, esi
0x18016f8a9  jz      short loc_18016F8B0
0x18016f8ab  xor     r14d, r14d
0x18016f8ae  jmp     short loc_18016F8E0
0x18016f8b0  mov     r14d, 6
0x18016f8b6  jmp     short loc_18016F8E0
0x18016f8b8  mov     r14d, 7
0x18016f8be  jmp     short loc_18016F8E0
0x18016f8c0  mov     r14d, r15d
0x18016f8c3  jmp     short loc_18016F8E0
0x18016f8c5  mov     r14d, 2
0x18016f8cb  jmp     short loc_18016F8E0
0x18016f8cd  mov     r14d, 4
0x18016f8d3  jmp     short loc_18016F8E0
0x18016f8d5  mov     r14d, esi
0x18016f8d8  jmp     short loc_18016F8E0
0x18016f8da  mov     r14d, 5
0x18016f8e0  lea     rcx, [rsp+168h+var_128]; this
0x18016f8e5  call    ??0DxilPipelineStateValidation@@QEAA@XZ; DxilPipelineStateValidation::DxilPipelineStateValidation(void)
0x18016f8ea  mov     r8d, [rsp+168h+arg_20]; unsigned int
0x18016f8f2  lea     rcx, [rsp+168h+var_128]; this
0x18016f8f7  mov     rdx, r9; void *
0x18016f8fa  call    ?InitFromPSV0@DxilPipelineStateValidation@@QEAA_NPEBXI@Z; DxilPipelineStateValidation::InitFromPSV0(void const *,uint)
0x18016f8ff  test    al, al
0x18016f901  jz      loc_18016FB80
0x18016f907  xor     dil, dil
0x18016f90a  xor     bpl, bpl
0x18016f90d  mov     [rsp+168h+arg_8], dil
0x18016f915  mov     dword ptr [rsp+168h+arg_30], ebp
0x18016f91c  bt      rbx, 19h
0x18016f921  jnb     short loc_18016F94E
0x18016f923  test    dword ptr [r13+218h], 400h
0x18016f92e  jnz     short loc_18016F94E
0x18016f930  mov     rcx, [rsp+168h+arg_28]
0x18016f938  lea     r9, aShaderUsesReso_0; "Shader uses resource descriptor heap in"...
0x18016f93f  mov     r8d, r15d
0x18016f942  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016f949  call    ErrorLibraryFunction
0x18016f94e  bt      rbx, 1Ah
0x18016f953  jnb     short loc_18016F980
0x18016f955  test    dword ptr [r13+218h], 800h
0x18016f960  jnz     short loc_18016F980
0x18016f962  mov     rcx, [rsp+168h+arg_28]
0x18016f96a  lea     r9, aShaderUsesSamp_1; "Shader uses sampler descriptor heap ind"...
0x18016f971  mov     r8d, r15d
0x18016f974  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016f97b  call    ErrorLibraryFunction
0x18016f980  mov     ecx, r14d
0x18016f983  sub     ecx, esi
0x18016f985  jz      short loc_18016F9F0
0x18016f987  sub     ecx, esi
0x18016f989  jz      short loc_18016F9E4
0x18016f98b  sub     ecx, esi
0x18016f98d  jz      short loc_18016F9D8
0x18016f98f  sub     ecx, esi
0x18016f991  jz      short loc_18016F9CC
0x18016f993  sub     ecx, esi
0x18016f995  jz      short loc_18016F9C0
0x18016f997  sub     ecx, esi
0x18016f999  jz      short loc_18016F9B1
0x18016f99b  cmp     ecx, esi
0x18016f99d  jnz     short loc_18016FA06
0x18016f99f  test    dword ptr [r13+218h], 200h
0x18016f9aa  jz      short loc_18016FA06
0x18016f9ac  mov     bpl, sil
0x18016f9af  jmp     short loc_18016F9FF
0x18016f9b1  mov     ebp, [r13+218h]
0x18016f9b8  shr     ebp, 8
0x18016f9bb  and     bpl, sil
0x18016f9be  jmp     short loc_18016F9FF
0x18016f9c0  mov     ebp, [r13+218h]
0x18016f9c7  shr     ebp, 5
0x18016f9ca  jmp     short loc_18016F9BB
0x18016f9cc  mov     ebp, [r13+218h]
0x18016f9d3  shr     ebp, 4
0x18016f9d6  jmp     short loc_18016F9BB
0x18016f9d8  mov     ebp, [r13+218h]
0x18016f9df  shr     ebp, 3
0x18016f9e2  jmp     short loc_18016F9BB
0x18016f9e4  mov     ebp, [r13+218h]
0x18016f9eb  shr     ebp, 2
0x18016f9ee  jmp     short loc_18016F9BB
0x18016f9f0  test    byte ptr [r13+218h], 2
0x18016f9f8  movzx   ebp, bpl
0x18016f9fc  cmovnz  ebp, esi
0x18016f9ff  mov     dword ptr [rsp+168h+arg_30], ebp
0x18016fa06  xor     r12d, r12d
0x18016fa09  cmp     [rsp+168h+var_F8], r12d
0x18016fa0e  jbe     loc_18016FB80
0x18016fa14  mov     ebp, esi
0x18016fa16  mov     r9d, 0FFFFFFFFh
0x18016fa1c  mov     r8, [rsp+168h+var_F0]
0x18016fa21  test    r8, r8
0x18016fa24  jz      short loc_18016FA4F
0x18016fa26  cmp     r12d, [rsp+168h+var_F8]
0x18016fa2b  jnb     short loc_18016FA4F
0x18016fa2d  mov     edx, [rsp+168h+var_F4]
0x18016fa31  cmp     edx, 10h
0x18016fa34  jb      short loc_18016FA4F
0x18016fa36  mov     ecx, edx
0x18016fa38  mov     eax, r12d
0x18016fa3b  imul    rcx, rax
0x18016fa3f  cmp     rcx, r9
0x18016fa42  ja      short loc_18016FA4F
0x18016fa44  imul    edx, r12d
0x18016fa48  mov     edi, edx
0x18016fa4a  add     rdi, r8
0x18016fa4d  jmp     short loc_18016FA51
0x18016fa4f  xor     edi, edi
0x18016fa51  mov     ecx, [rdi]
0x18016fa53  mov     r15d, [rdi+4]
0x18016fa57  mov     esi, [rdi+8]
0x18016fa5a  mov     ebx, [rdi+0Ch]
0x18016fa5d  sub     ecx, ebp
0x18016fa5f  jz      loc_18016FCDA
0x18016fa65  sub     ecx, ebp
0x18016fa67  jz      loc_18016FC8B
0x18016fa6d  sub     ecx, ebp
0x18016fa6f  jz      loc_18016FC39
0x18016fa75  sub     ecx, ebp
0x18016fa77  jz      loc_18016FC39
0x18016fa7d  sub     ecx, ebp
0x18016fa7f  jz      loc_18016FC39
0x18016fa85  sub     ecx, ebp
0x18016fa87  jz      short loc_18016FA99
0x18016fa89  sub     ecx, ebp
0x18016fa8b  jz      short loc_18016FA99
0x18016fa8d  sub     ecx, ebp
0x18016fa8f  jz      short loc_18016FA99
0x18016fa91  cmp     ecx, ebp
0x18016fa93  jnz     loc_18016FD47
0x18016fa99  mov     [rsp+168h+arg_8], bpl
0x18016faa1  cmp     ebx, r9d
0x18016faa4  jz      short loc_18016FAAC
0x18016faa6  sub     ebx, esi
0x18016faa8  add     ebx, ebp
0x18016faaa  jmp     short loc_18016FAAE
0x18016faac  mov     ebx, ebp
0x18016faae  mov     dword ptr [rsp+168h+var_140], r15d; unsigned int
0x18016fab3  mov     r9d, ebx; unsigned int
0x18016fab6  mov     r8d, r14d; enum D3D12_SHADER_VISIBILITY
0x18016fab9  mov     dword ptr [rsp+168h+var_148], esi; unsigned int
0x18016fabd  mov     edx, ebp; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18016fabf  mov     rcx, r13; this
0x18016fac2  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18016fac7  test    rax, rax
0x18016faca  jz      loc_18016FC09
0x18016fad0  cmp     [rax+40h], ebp
0x18016fad3  jnz     loc_18016FB94
0x18016fad9  cmp     dword ptr [rdi], 6
0x18016fadc  jnz     short loc_18016FB08
0x18016fade  mov     rcx, [rsp+168h+arg_28]
0x18016fae6  lea     r9, aAShaderIsDecla_2; "A Shader is declaring a typed UAV using"...
0x18016faed  mov     dword ptr [rsp+168h+var_140], r15d
0x18016faf2  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016faf9  mov     r8d, 2
0x18016faff  mov     dword ptr [rsp+168h+var_148], esi
0x18016fb03  call    ErrorLibraryFunction
0x18016fb08  cmp     dword ptr [rdi], 9
0x18016fb0b  jnz     short loc_18016FB37
0x18016fb0d  lea     r9, aAShaderIsDecla_0; "A Shader is declaring a structured UAV "...
0x18016fb14  mov     r8d, 2
0x18016fb1a  mov     rcx, [rsp+168h+arg_28]
0x18016fb22  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016fb29  mov     dword ptr [rsp+168h+var_140], r15d
0x18016fb2e  mov     dword ptr [rsp+168h+var_148], esi
0x18016fb32  call    ErrorLibraryFunction
0x18016fb37  mov     dil, bpl
0x18016fb3a  mov     r9d, 0FFFFFFFFh
0x18016fb40  add     r12d, ebp
0x18016fb43  cmp     r12d, [rsp+168h+var_F8]
0x18016fb48  jb      loc_18016FA1C
0x18016fb4e  mov     ebp, dword ptr [rsp+168h+arg_30]
0x18016fb55  test    dil, dil
0x18016fb58  jz      short loc_18016FB80
0x18016fb5a  test    bpl, bpl
0x18016fb5d  jz      short loc_18016FB80
0x18016fb5f  mov     rcx, [rsp+168h+arg_28]
0x18016fb67  lea     r9, aShaderHasRootB_0; "Shader has root bindings but root signa"...
0x18016fb6e  mov     r8d, 2
0x18016fb74  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016fb7b  call    ErrorLibraryFunction
0x18016fb80  add     rsp, 128h
0x18016fb87  pop     r15
0x18016fb89  pop     r14
0x18016fb8b  pop     r13
0x18016fb8d  pop     r12
0x18016fb8f  pop     rdi
0x18016fb90  pop     rsi
0x18016fb91  pop     rbp
0x18016fb92  pop     rbx
0x18016fb93  retn
0x18016fb94  cmp     dword ptr [rax+40h], 0
0x18016fb98  jnz     short loc_18016FB37
0x18016fb9a  mov     r8, [rsp+168h+var_F0]
0x18016fb9f  test    r8, r8
0x18016fba2  jz      short loc_18016FB37
0x18016fba4  cmp     r12d, [rsp+168h+var_F8]
0x18016fba9  jnb     short loc_18016FB37
0x18016fbab  mov     edx, [rsp+168h+var_F4]
0x18016fbaf  mov     r9d, 0FFFFFFFFh
0x18016fbb5  cmp     edx, 18h
0x18016fbb8  jb      loc_18016FD54
0x18016fbbe  mov     ecx, edx
0x18016fbc0  mov     eax, r12d
0x18016fbc3  imul    rcx, rax
0x18016fbc7  cmp     rcx, r9
0x18016fbca  ja      loc_18016FD54
0x18016fbd0  imul    edx, r12d
0x18016fbd4  mov     ecx, edx
0x18016fbd6  add     rcx, r8
0x18016fbd9  jz      loc_18016FD54
0x18016fbdf  test    [rcx+14h], bpl
0x18016fbe3  jz      loc_18016FD54
0x18016fbe9  cmp     byte ptr [r13+204h], 0
0x18016fbf1  jnz     loc_18016FD54
0x18016fbf7  lea     r9, aAShaderIsUsing; "A shader is using atomic int64 operatio"...
0x18016fbfe  mov     r8d, 3
0x18016fc04  jmp     loc_18016FB1A
0x18016fc09  lea     r9, aShaderUavDescr_0; "Shader UAV descriptor range (BaseShader"...
0x18016fc10  mov     rcx, [rsp+168h+arg_28]
0x18016fc18  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016fc1f  mov     [rsp+168h+var_138], r15d
0x18016fc24  mov     r8d, ebp
0x18016fc27  mov     dword ptr [rsp+168h+var_140], ebx
0x18016fc2b  mov     dword ptr [rsp+168h+var_148], esi
0x18016fc2f  call    ErrorLibraryFunction
0x18016fc34  jmp     loc_18016FB37
0x18016fc39  mov     [rsp+168h+arg_8], bpl
0x18016fc41  cmp     ebx, r9d
0x18016fc44  jz      short loc_18016FC4C
0x18016fc46  sub     ebx, esi
0x18016fc48  add     ebx, ebp
0x18016fc4a  jmp     short loc_18016FC4E
0x18016fc4c  mov     ebx, ebp
0x18016fc4e  mov     dword ptr [rsp+168h+var_140], r15d; unsigned int
0x18016fc53  mov     r9d, ebx; unsigned int
0x18016fc56  mov     r8d, r14d; enum D3D12_SHADER_VISIBILITY
0x18016fc59  mov     dword ptr [rsp+168h+var_148], esi; unsigned int
0x18016fc5d  xor     edx, edx; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18016fc5f  mov     rcx, r13; this
0x18016fc62  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18016fc67  test    rax, rax
0x18016fc6a  jz      short loc_18016FC82
0x18016fc6c  cmp     [rax+40h], ebp
0x18016fc6f  jnz     short loc_18016FCCD
0x18016fc71  cmp     dword ptr [rdi], 3
0x18016fc74  jnz     short loc_18016FCCD
0x18016fc76  lea     r9, aAShaderIsDecla_1; "A Shader is declaring a resource object"...
0x18016fc7d  jmp     loc_18016FB14
0x18016fc82  lea     r9, aShaderSrvDescr_1; "Shader SRV descriptor range (BaseShader"...
0x18016fc89  jmp     short loc_18016FC10
0x18016fc8b  mov     [rsp+168h+arg_8], bpl
0x18016fc93  cmp     ebx, r9d
0x18016fc96  jz      short loc_18016FC9E
0x18016fc98  sub     ebx, esi
0x18016fc9a  add     ebx, ebp
0x18016fc9c  jmp     short loc_18016FCA0
0x18016fc9e  mov     ebx, ebp
0x18016fca0  mov     dword ptr [rsp+168h+var_140], r15d; unsigned int
0x18016fca5  mov     r9d, ebx; unsigned int
0x18016fca8  mov     r8d, r14d; enum D3D12_SHADER_VISIBILITY
0x18016fcab  mov     dword ptr [rsp+168h+var_148], esi; unsigned int
0x18016fcaf  mov     edx, 2; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18016fcb4  mov     rcx, r13; this
0x18016fcb7  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18016fcbc  test    rax, rax
0x18016fcbf  jnz     short loc_18016FCCD
0x18016fcc1  lea     r9, aShaderCbvDescr_0; "Shader CBV descriptor range (BaseShader"...
0x18016fcc8  jmp     loc_18016FC10
0x18016fccd  mov     dil, [rsp+168h+arg_8]
0x18016fcd5  jmp     loc_18016FB3A
0x18016fcda  mov     [rsp+168h+arg_8], bpl
0x18016fce2  mov     dil, bpl
  ... truncated ...
```
