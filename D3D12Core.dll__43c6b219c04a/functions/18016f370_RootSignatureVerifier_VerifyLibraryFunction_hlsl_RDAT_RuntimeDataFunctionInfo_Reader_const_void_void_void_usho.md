# RootSignatureVerifier::VerifyLibraryFunction(hlsl::RDAT::RuntimeDataFunctionInfo_Reader const *,void *,void (*)(void *,ushort const *,uint))

- ea: `0x18016f370`
- end: `0x18016f85f`
- name: `?VerifyLibraryFunction@RootSignatureVerifier@@QEAAXPEBVRuntimeDataFunctionInfo_Reader@RDAT@hlsl@@PEAXP6AX1PEBGI@Z@Z`
- size: `1263`
- prototype: `void __fastcall(RootSignatureVerifier *__hidden this, const struct hlsl::RDAT::RuntimeDataFunctionInfo_Reader *, void *, void (*)(void *, const unsigned __int16 *, unsigned int))`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18016c4c4`

## callees

- `0x1800437d8`
- `0x180043898`
- `0x18004d2a0`
- `0x180068518`
- `0x18006baf0`
- `0x180073074`
- `0x1800a3810`
- `0x1800c76d4`
- `0x18016f370`

## string_xrefs

- `0x18016f6f4`: `A Shader is declaring a typed UAV using a register mapped to a root descriptor UAV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18016f726`: `A Shader is declaring a structured UAV with counter using a register mapped to a root descriptor UAV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18016f75b`: `A shader is using atomic int64 operations on a descriptor heap resource (ShaderRegister=%u, RegisterSpace=%u), which the device does not support. Check the AtomicInt64OnDescriptorHeapResourceSupported capability via the CheckFeatureSupport() API.`
- `0x18016f650`: `Shader sampler descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in a root signature.`
- `0x18016f3e0`: `Shader uses sampler descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_SAMPLER_HEAP_DIRECTLY_INDEXED flag.`
- `0x18016f3b3`: `Shader uses resource descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_CBV_SRV_UAV_HEAP_DIRECTLY_INDEXED flag.`
- `0x18016f693`: `Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in a root signature.`
- `0x18016f76a`: `Shader UAV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in a root signature.`
- `0x18016f7e4`: `Shader SRV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound in a root signature.`
- `0x18016f7be`: `A Shader is declaring a resource object as a texture using a register mapped to a root descriptor SRV (ShaderRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.`
- `0x18016f82b`: `Shader has root bindings but root signature uses a DENY flag to disallow root binding access to the shader stage.`

## pseudocode

```c
void __fastcall RootSignatureVerifier::VerifyLibraryFunction(
        RootSignatureVerifier *this,
        const struct hlsl::RDAT::RuntimeDataFunctionInfo_Reader *a2,
        _DWORD *a3,
        void (*a4)(void *, const unsigned __int16 *, unsigned int))
{
  unsigned int FeatureInfo1; // ebx
  int v8; // ecx
  char v9; // r12
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  enum D3D12_SHADER_VISIBILITY v15; // r14d
  unsigned int i; // r8d
  __int64 v17; // rdx
  bool v18; // zf
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned int v25; // ecx
  unsigned int v26; // eax
  char v27; // r12
  char v28; // al
  int *v29; // rcx
  char v30; // r8
  int *v31; // rdx
  unsigned int v32; // esi
  int *v33; // rax
  unsigned int v34; // edi
  int *v35; // rax
  int v36; // ebx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  unsigned int v40; // ebx
  const char *v41; // r9
  struct RootSignatureVerifier::TreeNode *v42; // rax
  int v43; // eax
  const char *v44; // r9
  __int64 v45; // r8
  struct RootSignatureVerifier::TreeNode *RegisterRange; // rax
  int Kind; // eax
  __int64 v48; // [rsp+20h] [rbp-50h]
  __int64 v49; // [rsp+28h] [rbp-48h]
  __int64 v50; // [rsp+30h] [rbp-40h]
  unsigned int v51; // [rsp+40h] [rbp-30h]
  unsigned int v52; // [rsp+44h] [rbp-2Ch]
  __int64 v53; // [rsp+48h] [rbp-28h] BYREF
  int v54; // [rsp+50h] [rbp-20h]
  char v55[8]; // [rsp+58h] [rbp-18h] BYREF
  int *v56; // [rsp+60h] [rbp-10h]
  __int64 v57; // [rsp+68h] [rbp-8h]
  char v58; // [rsp+C0h] [rbp+50h]

  FeatureInfo1 = hlsl::RDAT::RuntimeDataFunctionInfo_Reader::getFeatureInfo1(a2);
  if ( (FeatureInfo1 & 0x2000000) != 0 && (*((_DWORD *)this + 134) & 0x400) == 0 )
    ErrorLibraryFunction(
      a3,
      StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
      3,
      "Shader uses resource descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_CBV_SRV"
      "_UAV_HEAP_DIRECTLY_INDEXED flag.");
  if ( (FeatureInfo1 & 0x4000000) != 0 && (*((_DWORD *)this + 134) & 0x800) == 0 )
    ErrorLibraryFunction(
      a3,
      StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
      3,
      "Shader uses sampler descriptor heap indexing, but root signature is missing the D3D12_ROOT_SIGNATURE_FLAG_SAMPLER_"
      "HEAP_DIRECTLY_INDEXED flag.");
  v8 = a3[6];
  v9 = 0;
  if ( v8 )
  {
    v10 = v8 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 9;
            if ( v14 )
            {
              if ( v14 == 1 )
                v15 = D3D12_SHADER_VISIBILITY_GEOMETRY|D3D12_SHADER_VISIBILITY_HULL;
              else
                v15 = D3D12_SHADER_VISIBILITY_ALL;
            }
            else
            {
              v15 = D3D12_SHADER_VISIBILITY_PIXEL|D3D12_SHADER_VISIBILITY_HULL;
            }
          }
          else
          {
            v15 = D3D12_SHADER_VISIBILITY_DOMAIN;
          }
        }
        else
        {
          v15 = D3D12_SHADER_VISIBILITY_HULL;
        }
      }
      else
      {
        v15 = D3D12_SHADER_VISIBILITY_GEOMETRY;
      }
    }
    else
    {
      v15 = D3D12_SHADER_VISIBILITY_VERTEX;
    }
  }
  else
  {
    v15 = D3D12_SHADER_VISIBILITY_PIXEL;
  }
  for ( i = 0; i < 2; ++i )
  {
    v17 = i != 0 ? 536LL : 532LL;
    if ( v15 == D3D12_SHADER_VISIBILITY_VERTEX )
    {
      if ( (*((_BYTE *)this + v17) & 2) != 0 )
        v9 = 1;
    }
    else
    {
      switch ( v15 )
      {
        case D3D12_SHADER_VISIBILITY_HULL:
          v18 = (*((_BYTE *)this + v17) & 4) == 0;
          break;
        case D3D12_SHADER_VISIBILITY_DOMAIN:
          v18 = (*((_BYTE *)this + v17) & 8) == 0;
          break;
        case D3D12_SHADER_VISIBILITY_GEOMETRY:
          v18 = (*((_BYTE *)this + v17) & 0x10) == 0;
          break;
        case D3D12_SHADER_VISIBILITY_PIXEL:
          v18 = (*((_BYTE *)this + v17) & 0x20) == 0;
          break;
        case D3D12_SHADER_VISIBILITY_GEOMETRY|D3D12_SHADER_VISIBILITY_HULL:
          v18 = (*(_DWORD *)((_BYTE *)this + v17) & 0x100) == 0;
          break;
        case D3D12_SHADER_VISIBILITY_PIXEL|D3D12_SHADER_VISIBILITY_HULL:
          v18 = (*(_DWORD *)((_BYTE *)this + v17) & 0x200) == 0;
          break;
        default:
          continue;
      }
      if ( !v18 )
        v9 = 1;
    }
  }
  v58 = v9;
  hlsl::RDAT::BaseRecordReader::operator bool(a2);
  if ( (unsigned __int8)hlsl::RDAT::BaseRecordReader::operator bool(v19) )
  {
    v21 = *(_QWORD *)a2;
    v22 = *(_DWORD *)(v20 + 8);
    v23 = v21;
    v54 = v22;
    if ( *(_DWORD *)(v21 + 60) < 0x20u )
      v23 = 0;
    v53 = v23;
    v24 = 0;
    if ( *(_DWORD *)(v21 + 60) >= 0x20u )
      v24 = v21;
    if ( v24 && v22 != -1 )
    {
      v25 = *(_DWORD *)(hlsl::RDAT::IndexTableReader::getRow(v24 + 16, v55) + 8);
      goto LABEL_51;
    }
  }
  else
  {
    v53 = 0;
    v54 = 0;
  }
  v25 = 0;
LABEL_51:
  v26 = 0;
  v52 = v25;
  v51 = 0;
  if ( !v25 )
    return;
  v27 = 0;
  while ( 2 )
  {
    hlsl::RDAT::RecordArrayReader<hlsl::RDAT::RuntimeDataResourceInfo_Reader>::operator[](&v53, v55, v26);
    v28 = hlsl::RDAT::BaseRecordReader::operator bool(v55);
    v29 = v56;
    v30 = v28;
    if ( v28 && (unsigned int)v57 >= 0x20 )
    {
      v31 = v56;
      goto LABEL_57;
    }
    v32 = 0;
    v31 = 0;
    if ( v28 )
    {
LABEL_57:
      v32 = v31[3];
      if ( (unsigned int)v57 >= 0x20 )
      {
        v33 = v56;
        goto LABEL_60;
      }
    }
    v34 = 0;
    v33 = 0;
    if ( v30 )
    {
LABEL_60:
      v34 = v33[4];
      if ( (unsigned int)v57 >= 0x20 )
      {
        v35 = v56;
        goto LABEL_63;
      }
    }
    v36 = 0;
    v35 = 0;
    if ( !v30 )
    {
LABEL_64:
      v29 = 0;
      if ( v30 )
        goto LABEL_65;
LABEL_94:
      v27 = 1;
      if ( v36 == -1 )
        v40 = 1;
      else
        v40 = v36 - v34 + 1;
      RegisterRange = RootSignatureVerifier::FindRegisterRange(
                        this,
                        D3D12_DESCRIPTOR_RANGE_TYPE_SRV,
                        v15,
                        v40,
                        v34,
                        v32);
      if ( !RegisterRange )
      {
        v41 = "Shader SRV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully boun"
              "d in a root signature.";
        goto LABEL_105;
      }
      if ( *((_DWORD *)RegisterRange + 16) != 1 )
        goto LABEL_106;
      Kind = hlsl::RDAT::RuntimeDataResourceInfo_Reader::getKind(v55);
      if ( Kind != 10 && (unsigned int)(Kind - 1) > 8 )
        goto LABEL_106;
      v44 = "A Shader is declaring a resource object as a texture using a register mapped to a root descriptor SRV (Shade"
            "rRegister=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.";
      goto LABEL_102;
    }
LABEL_63:
    v36 = v35[5];
    if ( (unsigned int)v57 < 0x20 )
      goto LABEL_64;
LABEL_65:
    v37 = *v29;
    if ( !v37 )
      goto LABEL_94;
    v38 = v37 - 1;
    if ( !v38 )
    {
      v27 = 1;
      if ( v36 == -1 )
        v40 = 1;
      else
        v40 = v36 - v34 + 1;
      v42 = RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_UAV, v15, v40, v34, v32);
      if ( !v42 )
      {
        v41 = "Shader UAV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully boun"
              "d in a root signature.";
        goto LABEL_105;
      }
      if ( *((_DWORD *)v42 + 16) != 1 )
      {
        if ( *((_DWORD *)v42 + 16)
          || (hlsl::RDAT::RuntimeDataResourceInfo_Reader::getFlags((hlsl::RDAT::RuntimeDataResourceInfo_Reader *)v55)
            & 0x10) == 0
          || *((_BYTE *)this + 516) )
        {
          goto LABEL_106;
        }
        v44 = "A shader is using atomic int64 operations on a descriptor heap resource (ShaderRegister=%u, RegisterSpace="
              "%u), which the device does not support. Check the AtomicInt64OnDescriptorHeapResourceSupported capability "
              "via the CheckFeatureSupport() API.";
        v45 = 3;
LABEL_103:
        LODWORD(v49) = v32;
        LODWORD(v48) = v34;
        ErrorLibraryFunction(
          a3,
          StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
          v45,
          v44,
          v48,
          v49);
        goto LABEL_106;
      }
      v43 = hlsl::RDAT::RuntimeDataResourceInfo_Reader::getKind(v55);
      if ( v43 == 10 || (unsigned int)(v43 - 1) <= 8 )
        ErrorLibraryFunction(
          a3,
          StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
          2,
          "A Shader is declaring a typed UAV using a register mapped to a root descriptor UAV (ShaderRegister=%u, Registe"
          "rSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.",
          v34,
          v32);
      if ( hlsl::RDAT::RuntimeDataResourceInfo_Reader::getFlags((hlsl::RDAT::RuntimeDataResourceInfo_Reader *)v55) != 2 )
        goto LABEL_106;
      v44 = "A Shader is declaring a structured UAV with counter using a register mapped to a root descriptor UAV (Shader"
            "Register=%u, RegisterSpace=%u).  SRV or UAV root descriptors can only be Raw or Structured buffers.";
LABEL_102:
      v45 = 2;
      goto LABEL_103;
    }
    v39 = v38 - 1;
    if ( !v39 )
    {
      v27 = 1;
      if ( v36 == -1 )
        v40 = 1;
      else
        v40 = v36 - v34 + 1;
      if ( RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_CBV, v15, v40, v34, v32) )
        goto LABEL_106;
      v41 = "Shader CBV descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully bound "
            "in a root signature.";
LABEL_105:
      LODWORD(v50) = v32;
      LODWORD(v49) = v40;
      LODWORD(v48) = v34;
      ErrorLibraryFunction(
        a3,
        StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
        1,
        v41,
        v48,
        v49,
        v50);
      goto LABEL_106;
    }
    if ( v39 == 1 )
    {
      v27 = 1;
      v40 = v36 == -1 ? 1 : v36 - v34 + 1;
      if ( !RootSignatureVerifier::FindRegisterRange(this, D3D12_DESCRIPTOR_RANGE_TYPE_SAMPLER, v15, v40, v34, v32) )
      {
        v41 = "Shader sampler descriptor range (BaseShaderRegister=%u, NumDescriptors=%u, RegisterSpace=%u) is not fully "
              "bound in a root signature.";
        goto LABEL_105;
      }
    }
LABEL_106:
    v26 = v51 + 1;
    v51 = v26;
    if ( v26 < v52 )
      continue;
    break;
  }
  if ( v27 )
  {
    if ( v58 )
      ErrorLibraryFunction(
        a3,
        StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback,
        2,
        "Shader has root bindings but root signature uses a DENY flag to disallow root binding access to the shader stage.");
  }
}

```

## disassembly

```asm
0x18016f370  mov     [rsp-38h+arg_0], rbx
0x18016f375  push    rbp
0x18016f376  push    rsi
0x18016f377  push    rdi
0x18016f378  push    r12
0x18016f37a  push    r13
0x18016f37c  push    r14
0x18016f37e  push    r15
0x18016f380  mov     rbp, rsp
0x18016f383  sub     rsp, 70h
0x18016f387  mov     r15, rcx
0x18016f38a  mov     r13, r8
0x18016f38d  mov     rcx, rdx; this
0x18016f390  mov     rdi, rdx
0x18016f393  call    ?getFeatureInfo1@RuntimeDataFunctionInfo_Reader@RDAT@hlsl@@QEBAIXZ; hlsl::RDAT::RuntimeDataFunctionInfo_Reader::getFeatureInfo1(void)
0x18016f398  mov     ebx, eax
0x18016f39a  mov     esi, 3
0x18016f39f  bt      rbx, 19h
0x18016f3a4  jnb     short loc_18016F3CC
0x18016f3a6  test    dword ptr [r15+218h], 400h
0x18016f3b1  jnz     short loc_18016F3CC
0x18016f3b3  lea     r9, aShaderUsesReso_0; "Shader uses resource descriptor heap in"...
0x18016f3ba  mov     r8d, esi
0x18016f3bd  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016f3c4  mov     rcx, r13
0x18016f3c7  call    ErrorLibraryFunction
0x18016f3cc  bt      rbx, 1Ah
0x18016f3d1  jnb     short loc_18016F3F9
0x18016f3d3  test    dword ptr [r15+218h], 800h
0x18016f3de  jnz     short loc_18016F3F9
0x18016f3e0  lea     r9, aShaderUsesSamp_1; "Shader uses sampler descriptor heap ind"...
0x18016f3e7  mov     r8d, esi
0x18016f3ea  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016f3f1  mov     rcx, r13
0x18016f3f4  call    ErrorLibraryFunction
0x18016f3f9  mov     ecx, [r13+18h]
0x18016f3fd  xor     r12b, r12b
0x18016f400  mov     [rbp+arg_10], r12d
0x18016f404  mov     r9d, 1
0x18016f40a  test    ecx, ecx
0x18016f40c  jz      short loc_18016F45B
0x18016f40e  sub     ecx, r9d
0x18016f411  jz      short loc_18016F456
0x18016f413  sub     ecx, r9d
0x18016f416  jz      short loc_18016F44E
0x18016f418  sub     ecx, r9d
0x18016f41b  jz      short loc_18016F446
0x18016f41d  sub     ecx, r9d
0x18016f420  jz      short loc_18016F441
0x18016f422  sub     ecx, 9
0x18016f425  jz      short loc_18016F439
0x18016f427  cmp     ecx, r9d
0x18016f42a  jz      short loc_18016F431
0x18016f42c  xor     r14d, r14d
0x18016f42f  jmp     short loc_18016F461
0x18016f431  mov     r14d, 6
0x18016f437  jmp     short loc_18016F461
0x18016f439  mov     r14d, 7
0x18016f43f  jmp     short loc_18016F461
0x18016f441  mov     r14d, esi
0x18016f444  jmp     short loc_18016F461
0x18016f446  mov     r14d, 2
0x18016f44c  jmp     short loc_18016F461
0x18016f44e  mov     r14d, 4
0x18016f454  jmp     short loc_18016F461
0x18016f456  mov     r14d, r9d
0x18016f459  jmp     short loc_18016F461
0x18016f45b  mov     r14d, 5
0x18016f461  xor     r8d, r8d
0x18016f464  mov     eax, r8d
0x18016f467  mov     ecx, r14d
0x18016f46a  neg     eax
0x18016f46c  sbb     rdx, rdx
0x18016f46f  and     edx, 4
0x18016f472  add     rdx, 214h
0x18016f479  sub     ecx, r9d
0x18016f47c  jz      short loc_18016F4D1
0x18016f47e  sub     ecx, r9d
0x18016f481  jz      short loc_18016F4CA
0x18016f483  sub     ecx, r9d
0x18016f486  jz      short loc_18016F4C3
0x18016f488  sub     ecx, r9d
0x18016f48b  jz      short loc_18016F4BC
0x18016f48d  sub     ecx, r9d
0x18016f490  jz      short loc_18016F4B5
0x18016f492  sub     ecx, r9d
0x18016f495  jz      short loc_18016F4AB
0x18016f497  cmp     ecx, r9d
0x18016f49a  jnz     short loc_18016F4DE
0x18016f49c  test    dword ptr [rdx+r15], 200h
0x18016f4a4  jz      short loc_18016F4DE
0x18016f4a6  mov     r12b, r9b
0x18016f4a9  jmp     short loc_18016F4DE
0x18016f4ab  test    dword ptr [rdx+r15], 100h
0x18016f4b3  jmp     short loc_18016F4A4
0x18016f4b5  test    byte ptr [rdx+r15], 20h
0x18016f4ba  jmp     short loc_18016F4A4
0x18016f4bc  test    byte ptr [rdx+r15], 10h
0x18016f4c1  jmp     short loc_18016F4A4
0x18016f4c3  test    byte ptr [rdx+r15], 8
0x18016f4c8  jmp     short loc_18016F4A4
0x18016f4ca  test    byte ptr [rdx+r15], 4
0x18016f4cf  jmp     short loc_18016F4A4
0x18016f4d1  test    byte ptr [rdx+r15], 2
0x18016f4d6  movzx   r12d, r12b
0x18016f4da  cmovnz  r12d, r9d
0x18016f4de  add     r8d, r9d
0x18016f4e1  cmp     r8d, 2
0x18016f4e5  jb      loc_18016F464
0x18016f4eb  mov     rcx, rdi
0x18016f4ee  mov     [rbp+arg_10], r12d
0x18016f4f2  call    ??BBaseRecordReader@RDAT@hlsl@@QEBA_NXZ; hlsl::RDAT::BaseRecordReader::operator bool(void)
0x18016f4f7  test    al, al
0x18016f4f9  jz      short loc_18016F507
0x18016f4fb  cmp     dword ptr [rdi+10h], 2Ch ; ','
0x18016f4ff  jb      short loc_18016F507
0x18016f501  mov     r8, [rdi+8]
0x18016f505  jmp     short loc_18016F50A
0x18016f507  xor     r8d, r8d
0x18016f50a  call    ??BBaseRecordReader@RDAT@hlsl@@QEBA_NXZ; hlsl::RDAT::BaseRecordReader::operator bool(void)
0x18016f50f  test    al, al
0x18016f511  jz      short loc_18016F556
0x18016f513  mov     rdx, [rdi]
0x18016f516  xor     eax, eax
0x18016f518  mov     r8d, [r8+8]
0x18016f51c  mov     rcx, rdx
0x18016f51f  mov     [rbp+var_20], r8d
0x18016f523  cmp     dword ptr [rdx+3Ch], 20h ; ' '
0x18016f527  cmovb   rcx, rax
0x18016f52b  mov     [rbp+var_28], rcx
0x18016f52f  xor     ecx, ecx
0x18016f531  cmp     dword ptr [rdx+3Ch], 20h ; ' '
0x18016f535  cmovnb  rcx, rdx
0x18016f539  test    rcx, rcx
0x18016f53c  jz      short loc_18016F565
0x18016f53e  cmp     r8d, 0FFFFFFFFh
0x18016f542  jnb     short loc_18016F565
0x18016f544  add     rcx, 10h
0x18016f548  lea     rdx, [rbp+var_18]
0x18016f54c  call    ?getRow@IndexTableReader@RDAT@hlsl@@QEBA?AVIndexRow@123@I@Z; hlsl::RDAT::IndexTableReader::getRow(uint)
0x18016f551  mov     ecx, [rax+8]
0x18016f554  jmp     short loc_18016F567
0x18016f556  mov     [rbp+var_28], 0
0x18016f55e  mov     [rbp+var_20], 0
0x18016f565  xor     ecx, ecx
0x18016f567  xor     eax, eax
0x18016f569  mov     [rbp+var_2C], ecx
0x18016f56c  mov     [rbp+var_30], eax
0x18016f56f  test    ecx, ecx
0x18016f571  jz      loc_18016F847
0x18016f577  mov     r12b, al
0x18016f57a  mov     r8d, eax
0x18016f57d  lea     rdx, [rbp+var_18]
0x18016f581  lea     rcx, [rbp+var_28]
0x18016f585  call    ??A?$RecordArrayReader@VRuntimeDataResourceInfo_Reader@RDAT@hlsl@@@RDAT@hlsl@@QEBA?BVRuntimeDataResourceInfo_Reader@12@I@Z; hlsl::RDAT::RecordArrayReader<hlsl::RDAT::RuntimeDataResourceInfo_Reader>::operator[](uint)
0x18016f58a  lea     rcx, [rbp+var_18]
0x18016f58e  call    ??BBaseRecordReader@RDAT@hlsl@@QEBA_NXZ; hlsl::RDAT::BaseRecordReader::operator bool(void)
0x18016f593  mov     rcx, [rbp+var_10]
0x18016f597  mov     r8b, al
0x18016f59a  mov     r9, [rbp+var_8]
0x18016f59e  test    al, al
0x18016f5a0  jz      short loc_18016F5AD
0x18016f5a2  cmp     r9d, 20h ; ' '
0x18016f5a6  jb      short loc_18016F5AD
0x18016f5a8  mov     rdx, rcx
0x18016f5ab  jmp     short loc_18016F5B6
0x18016f5ad  xor     esi, esi
0x18016f5af  xor     edx, edx
0x18016f5b1  test    r8b, r8b
0x18016f5b4  jz      short loc_18016F5C4
0x18016f5b6  mov     esi, [rdx+0Ch]
0x18016f5b9  cmp     r9d, 20h ; ' '
0x18016f5bd  jb      short loc_18016F5C4
0x18016f5bf  mov     rax, rcx
0x18016f5c2  jmp     short loc_18016F5CD
0x18016f5c4  xor     edi, edi
0x18016f5c6  xor     eax, eax
0x18016f5c8  test    r8b, r8b
0x18016f5cb  jz      short loc_18016F5DB
0x18016f5cd  mov     edi, [rax+10h]
0x18016f5d0  cmp     r9d, 20h ; ' '
0x18016f5d4  jb      short loc_18016F5DB
0x18016f5d6  mov     rax, rcx
0x18016f5d9  jmp     short loc_18016F5E4
0x18016f5db  xor     ebx, ebx
0x18016f5dd  xor     eax, eax
0x18016f5df  test    r8b, r8b
0x18016f5e2  jz      short loc_18016F5ED
0x18016f5e4  mov     ebx, [rax+14h]
0x18016f5e7  cmp     r9d, 20h ; ' '
0x18016f5eb  jnb     short loc_18016F5F8
0x18016f5ed  xor     ecx, ecx
0x18016f5ef  test    r8b, r8b
0x18016f5f2  jz      loc_18016F773
0x18016f5f8  mov     ecx, [rcx]
0x18016f5fa  test    ecx, ecx
0x18016f5fc  jz      loc_18016F773
0x18016f602  sub     ecx, 1
0x18016f605  jz      loc_18016F69F
0x18016f60b  sub     ecx, 1
0x18016f60e  jz      short loc_18016F65C
0x18016f610  cmp     ecx, 1
0x18016f613  jnz     loc_18016F80C
0x18016f619  mov     r12b, cl
0x18016f61c  cmp     ebx, 0FFFFFFFFh
0x18016f61f  jz      short loc_18016F627
0x18016f621  sub     ebx, edi
0x18016f623  inc     ebx
0x18016f625  jmp     short loc_18016F62C
0x18016f627  mov     ebx, 1
0x18016f62c  mov     dword ptr [rsp+70h+var_48], esi; unsigned int
0x18016f630  mov     r9d, ebx; unsigned int
0x18016f633  mov     r8d, r14d; enum D3D12_SHADER_VISIBILITY
0x18016f636  mov     dword ptr [rsp+70h+var_50], edi; unsigned int
0x18016f63a  mov     edx, 3; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18016f63f  mov     rcx, r15; this
0x18016f642  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18016f647  test    rax, rax
0x18016f64a  jnz     loc_18016F80C
0x18016f650  lea     r9, aShaderSamplerD_0; "Shader sampler descriptor range (BaseSh"...
0x18016f657  jmp     loc_18016F7EB
0x18016f65c  mov     r12b, 1
0x18016f65f  cmp     ebx, 0FFFFFFFFh
0x18016f662  jz      short loc_18016F66A
0x18016f664  sub     ebx, edi
0x18016f666  inc     ebx
0x18016f668  jmp     short loc_18016F66F
0x18016f66a  mov     ebx, 1
0x18016f66f  mov     dword ptr [rsp+70h+var_48], esi; unsigned int
0x18016f673  mov     r9d, ebx; unsigned int
0x18016f676  mov     r8d, r14d; enum D3D12_SHADER_VISIBILITY
0x18016f679  mov     dword ptr [rsp+70h+var_50], edi; unsigned int
0x18016f67d  mov     edx, 2; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18016f682  mov     rcx, r15; this
0x18016f685  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18016f68a  test    rax, rax
0x18016f68d  jnz     loc_18016F80C
0x18016f693  lea     r9, aShaderCbvDescr_1; "Shader CBV descriptor range (BaseShader"...
0x18016f69a  jmp     loc_18016F7EB
0x18016f69f  mov     eax, 1
0x18016f6a4  mov     r12b, al
0x18016f6a7  cmp     ebx, 0FFFFFFFFh
0x18016f6aa  jz      short loc_18016F6B2
0x18016f6ac  sub     ebx, edi
0x18016f6ae  add     ebx, eax
0x18016f6b0  jmp     short loc_18016F6B4
0x18016f6b2  mov     ebx, eax
0x18016f6b4  mov     dword ptr [rsp+70h+var_48], esi; unsigned int
0x18016f6b8  mov     r9d, ebx; unsigned int
0x18016f6bb  mov     r8d, r14d; enum D3D12_SHADER_VISIBILITY
0x18016f6be  mov     dword ptr [rsp+70h+var_50], edi; unsigned int
0x18016f6c2  mov     edx, eax; enum D3D12_DESCRIPTOR_RANGE_TYPE
0x18016f6c4  mov     rcx, r15; this
0x18016f6c7  call    ?FindRegisterRange@RootSignatureVerifier@@AEAAPEAUTreeNode@1@W4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@III@Z; RootSignatureVerifier::FindRegisterRange(D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint)
0x18016f6cc  test    rax, rax
0x18016f6cf  jz      loc_18016F76A
0x18016f6d5  cmp     dword ptr [rax+40h], 1
0x18016f6d9  jnz     short loc_18016F732
0x18016f6db  lea     rcx, [rbp+var_18]
0x18016f6df  call    ?getKind@RuntimeDataResourceInfo_Reader@RDAT@hlsl@@QEBA?AW4ResourceKind@DXIL@3@XZ; hlsl::RDAT::RuntimeDataResourceInfo_Reader::getKind(void)
0x18016f6e4  cmp     eax, 0Ah
0x18016f6e7  jz      short loc_18016F6F0
0x18016f6e9  dec     eax
0x18016f6eb  cmp     eax, 8
0x18016f6ee  ja      short loc_18016F714
0x18016f6f0  mov     dword ptr [rsp+70h+var_48], esi
0x18016f6f4  lea     r9, aAShaderIsDecla_2; "A Shader is declaring a typed UAV using"...
0x18016f6fb  mov     r8d, 2
0x18016f701  mov     dword ptr [rsp+70h+var_50], edi
0x18016f705  lea     rdx, ?ReportLibraryFunctionErrorCallback@CStateObjectInfo@StateObjectInfo@@CAXPEAXPEBGI@Z; StateObjectInfo::CStateObjectInfo::ReportLibraryFunctionErrorCallback(void *,ushort const *,uint)
0x18016f70c  mov     rcx, r13
0x18016f70f  call    ErrorLibraryFunction
0x18016f714  lea     rcx, [rbp+var_18]; this
0x18016f718  call    ?getFlags@RuntimeDataResourceInfo_Reader@RDAT@hlsl@@QEBAIXZ; hlsl::RDAT::RuntimeDataResourceInfo_Reader::getFlags(void)
0x18016f71d  cmp     eax, 2
0x18016f720  jnz     loc_18016F80C
0x18016f726  lea     r9, aAShaderIsDecla_0; "A Shader is declaring a structured UAV "...
0x18016f72d  jmp     loc_18016F7C5
0x18016f732  cmp     dword ptr [rax+40h], 0
0x18016f736  jnz     loc_18016F80C
0x18016f73c  lea     rcx, [rbp+var_18]; this
0x18016f740  call    ?getFlags@RuntimeDataResourceInfo_Reader@RDAT@hlsl@@QEBAIXZ; hlsl::RDAT::RuntimeDataResourceInfo_Reader::getFlags(void)
0x18016f745  test    al, 10h
0x18016f747  jz      loc_18016F80C
0x18016f74d  cmp     byte ptr [r15+204h], 0
0x18016f755  jnz     loc_18016F80C
0x18016f75b  lea     r9, aAShaderIsUsing; "A shader is using atomic int64 operatio"...
0x18016f762  mov     r8d, 3
0x18016f768  jmp     short loc_18016F7CB
0x18016f76a  lea     r9, aShaderUavDescr_1; "Shader UAV descriptor range (BaseShader"...
0x18016f771  jmp     short loc_18016F7EB
0x18016f773  mov     r12b, 1
0x18016f776  cmp     ebx, 0FFFFFFFFh
0x18016f779  jz      short loc_18016F781
0x18016f77b  sub     ebx, edi
0x18016f77d  inc     ebx
0x18016f77f  jmp     short loc_18016F786
0x18016f781  mov     ebx, 1
0x18016f786  mov     dword ptr [rsp+70h+var_48], esi; unsigned int
0x18016f78a  mov     r9d, ebx; unsigned int
  ... truncated ...
```
