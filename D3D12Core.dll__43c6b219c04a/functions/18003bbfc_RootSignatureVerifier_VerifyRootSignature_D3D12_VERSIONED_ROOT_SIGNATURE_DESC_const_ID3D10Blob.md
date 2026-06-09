# RootSignatureVerifier::VerifyRootSignature(D3D12_VERSIONED_ROOT_SIGNATURE_DESC const *,ID3D10Blob * *)

- ea: `0x18003bbfc`
- end: `0x18003c21a`
- name: `?VerifyRootSignature@RootSignatureVerifier@@QEAAJPEBUD3D12_VERSIONED_ROOT_SIGNATURE_DESC@@PEAPEAUID3D10Blob@@@Z`
- size: `1566`
- prototype: `int(RootSignatureVerifier *__hidden this, const struct D3D12_VERSIONED_ROOT_SIGNATURE_DESC *, struct ID3D10Blob **)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003b998`
- `0x18003c49c`
- `0x1800b8180`

## callees

- `0x180039258`
- `0x1800393e0`
- `0x180039ff8`
- `0x18003af70`
- `0x18003b478`
- `0x18003bbfc`
- `0x18003c47c`
- `0x18005a1f0`

## string_xrefs

- `0x18003bcc7`: `D3D12_ROOT_SIGNATURE_FLAG_LOCAL_ROOT_SIGNATURE combined with other flag(s) that don't make sense (root signature flags %x).\n`
- `0x18003c05e`: `Sampler descriptor ranges can't specify DESCRIPTORS_STATIC_KEEPING_BUFFER_BOUNDS_CHECKS, since there are no bounds to check (descriptor range flags %x).\n`
- `0x18003c039`: `Sampler descriptor ranges can't specify DATA_* flags since there is no data pointed to by samplers (descriptor range flags %x).\n`
- `0x18003bfbc`: `Descriptor range flags cannot specify more than one DESCRIPTOR_* flag at a time (descriptor range flags %x).\n`
- `0x18003bf88`: `Unsupported bit-flag set (descriptor range flags %x).\n`
- `0x18003be36`: `Unsupported bit-flag set (root descriptor flags %x).\n`
- `0x18003c02a`: `Descriptor range flags cannot specify DESCRIPTORS_VOLATILE with the DATA_STATIC flag at the same time (descriptor range flags %x). DATA_STATIC_WHILE_SET_AT_EXECUTE is fine to combine with DESCRIPTORS_VOLATILE, since DESCRIPTORS_VOLATILE still requires descriptors don't change during execution. \n`
- `0x18003c002`: `Descriptor range flags cannot specify more than one DATA_* flag at a time (descriptor range flags %x).\n`
- `0x18003be72`: `Root descriptor flags cannot specify more than one DATA_* flag at a time (root descriptor flags %x).\n`

## pseudocode

```c
__int64 __fastcall RootSignatureVerifier::VerifyRootSignature(
        RootSignatureVerifier *this,
        const struct D3D12_VERSIONED_ROOT_SIGNATURE_DESC *a2,
        struct ID3D10Blob **a3)
{
  const struct D3D12_VERSIONED_ROOT_SIGNATURE_DESC *v4; // rsi
  int v6; // ebx
  int v7; // eax
  struct D3D12_VERSIONED_ROOT_SIGNATURE_DESC *v8; // r15
  __int64 v9; // rax
  int v10; // ecx
  D3D12_ROOT_SIGNATURE_FLAGS Flags; // r8d
  D3D12_ROOT_SIGNATURE_FLAGS v12; // eax
  char v13; // r12
  unsigned int i; // ebp
  const D3D12_ROOT_PARAMETER *pParameters; // r13
  __int64 v16; // rsi
  __int64 ShaderVisibility; // rdx
  D3D12_ROOT_PARAMETER_TYPE ParameterType; // r12d
  int v19; // eax
  __int64 v20; // rax
  int v21; // ecx
  UINT Num32BitValues; // ebp
  int v23; // ecx
  unsigned int v24; // eax
  int RangeType; // eax
  unsigned int NumDescriptorRanges; // r8d
  const struct D3D12_DESCRIPTOR_RANGE1 *pDescriptorRanges; // rdx
  int *v28; // rax
  int v29; // ecx
  __int64 k; // r12
  __int64 v31; // rbp
  const D3D12_DESCRIPTOR_RANGE *v32; // r12
  int v33; // r8d
  int v34; // r8d
  unsigned int v35; // eax
  unsigned int v36; // r8d
  int v37; // ecx
  unsigned int v38; // eax
  int v39; // eax
  int v40; // eax
  UINT j; // esi
  __int64 v42; // r13
  unsigned int v43; // ebp
  char v44; // r8
  enum D3D_SHADER_MODEL v45; // edx
  int v47; // [rsp+30h] [rbp-68h]
  int v48; // [rsp+38h] [rbp-60h]
  int v49; // [rsp+40h] [rbp-58h]
  D3D12_SHADER_VISIBILITY v50; // [rsp+50h] [rbp-48h]
  unsigned int v51; // [rsp+54h] [rbp-44h]
  unsigned int v52; // [rsp+58h] [rbp-40h]
  int v53[15]; // [rsp+5Ch] [rbp-3Ch] BYREF
  struct D3D12_VERSIONED_ROOT_SIGNATURE_DESC *v55; // [rsp+B8h] [rbp+20h] BYREF

  v55 = 0;
  v4 = a2;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( a3 )
    *a3 = 0;
  v7 = ConvertRootSignature(
         a2,
         D3D_ROOT_SIGNATURE_VERSION_1_1|D3D_ROOT_SIGNATURE_VERSION_1_0,
         (const struct D3D12_VERSIONED_ROOT_SIGNATURE_DESC **)&v55);
  v8 = v55;
  v6 = v7;
  if ( v7 >= 0 )
  {
    v9 = *((_QWORD *)this + 68);
    v10 = v9 ? *(_DWORD *)(v9 + 8) : 2147479552;
    Flags = v55->Desc_1_0.Flags;
    if ( (Flags & v10) == 0
      || (v6 = ErrorRootSignature(a3, "Unsupported bit-flag set (root signature flags %x).\n", Flags), v6 >= 0) )
    {
      v12 = v8->Desc_1_0.Flags;
      v13 = 0;
      LOBYTE(v55) = 0;
      if ( (v12 & 0x80u) == 0 )
      {
        *((_DWORD *)this + 134) = v12;
      }
      else
      {
        if ( *((_BYTE *)this + 514) )
        {
          if ( (v12 & 0xFFFFFF7F) != 0 )
          {
            v6 = ErrorRootSignature(
                   a3,
                   "D3D12_ROOT_SIGNATURE_FLAG_LOCAL_ROOT_SIGNATURE combined with other flag(s) that don't make sense (roo"
                   "t signature flags %x).\n",
                   v12);
            if ( v6 < 0 )
              goto LABEL_91;
          }
          v13 = 1;
          LOBYTE(v55) = 1;
        }
        else
        {
          v6 = ErrorRootSignature(
                 a3,
                 "D3D12_ROOT_SIGNATURE_FLAG_LOCAL_ROOT_SIGNATURE not supported if device does not support raytracing or w"
                 "ork graphs (root signature flags %x).\n",
                 v12);
          if ( v6 < 0 )
            goto LABEL_91;
        }
        *((_DWORD *)this + 133) = v8->Desc_1_0.Flags;
      }
      for ( i = 0; ; ++i )
      {
        v51 = i;
        if ( i >= v8->Desc_1_0.NumParameters )
        {
          for ( j = 0; j < v8->Desc_1_0.NumStaticSamplers; ++j )
          {
            v42 = (__int64)v8->Desc_1_0.pStaticSamplers + 56 * j;
            v43 = *(_DWORD *)(v42 + 48);
            if ( v43 >= 6 && (v43 - 6 > 1 || !*((_BYTE *)this + 515)) )
            {
              v6 = ErrorRootSignature(a3, "Unsupported ShaderVisibility value %u (static sampler [%u]).\n", v43, j);
              if ( v6 < 0 )
                break;
            }
            if ( v13 )
            {
              if ( v43 )
              {
                v6 = ErrorRootSignature(
                       a3,
                       "Local root signatures only support shader visibility flag D3D12_SHADER_VISIBILITY_ALL.  ShaderVis"
                       "ibility value: %u (static sampler [%u]).\n",
                       v43,
                       j);
                if ( v6 < 0 )
                  break;
              }
            }
            v44 = *((_BYTE *)this + 524);
            v45 = *((_DWORD *)this + 130);
            LOBYTE(v55) = 1;
            v6 = StaticSamplerVerifier::Verify(
                   (StaticSamplerVerifier *)&v55,
                   v45,
                   v44,
                   (const struct D3D12_STATIC_SAMPLER_DESC1 *)v42,
                   a3);
            if ( v6 < 0 )
              break;
            v6 = RootSignatureVerifier::AddRegisterRange(
                   this,
                   j,
                   3,
                   0xFFFFFFFFLL,
                   3,
                   v43,
                   1,
                   *(_DWORD *)(v42 + 40),
                   *(_DWORD *)(v42 + 44),
                   a3);
            if ( v6 < 0 )
              break;
          }
          goto LABEL_90;
        }
        pParameters = v8->Desc_1_0.pParameters;
        v16 = i;
        ShaderVisibility = (unsigned int)pParameters[v16].ShaderVisibility;
        v50 = pParameters[v16].ShaderVisibility;
        if ( (unsigned int)ShaderVisibility >= 6
          && ((unsigned int)(ShaderVisibility - 6) > 1 || !*((_BYTE *)this + 515)) )
        {
          v6 = ErrorRootSignature(
                 a3,
                 "Unsupported ShaderVisibility value %u (root parameter [%u]).\n",
                 ShaderVisibility,
                 i);
          if ( v6 < 0 )
            goto LABEL_90;
          ShaderVisibility = (unsigned int)v50;
        }
        if ( v13 )
        {
          if ( (_DWORD)ShaderVisibility )
          {
            v6 = ErrorRootSignature(
                   a3,
                   "Local root signatures only support shader visibility flag D3D12_SHADER_VISIBILITY_ALL.  ShaderVisibil"
                   "ity value: %u (root parameter [%u]).\n",
                   ShaderVisibility,
                   i);
            if ( v6 < 0 )
              goto LABEL_90;
          }
        }
        ParameterType = pParameters[v16].ParameterType;
        if ( ParameterType == D3D12_ROOT_PARAMETER_TYPE_DESCRIPTOR_TABLE )
          break;
        if ( ParameterType == D3D12_ROOT_PARAMETER_TYPE_32BIT_CONSTANTS )
        {
          if ( !pParameters[v16].Constants.Num32BitValues )
            ErrorRootSignature(a3, "Root constants Num32BitValues should be > 0.\n");
          v19 = RootSignatureVerifier::AddRegisterRange(
                  this,
                  i,
                  2,
                  pParameters[v16].Constants.Num32BitValues,
                  2,
                  v50,
                  1,
                  pParameters[v16].DescriptorTable.NumDescriptorRanges,
                  pParameters[v16].Constants.RegisterSpace,
                  a3);
        }
        else if ( ParameterType == D3D12_ROOT_PARAMETER_TYPE_CBV || (unsigned int)(ParameterType - 3) < 2 )
        {
          v20 = *((_QWORD *)this + 68);
          if ( v20 )
            v21 = *(_DWORD *)(v20 + 4);
          else
            v21 = -15;
          Num32BitValues = pParameters[v16].Constants.Num32BitValues;
          if ( (Num32BitValues & v21) != 0 )
          {
            v6 = ErrorRootSignature(a3, "Unsupported bit-flag set (root descriptor flags %x).\n", Num32BitValues);
            if ( v6 < 0 )
              goto LABEL_90;
          }
          v23 = ((Num32BitValues >> 1) & 1) + 1;
          if ( (Num32BitValues & 8) == 0 )
            v23 = (Num32BitValues >> 1) & 1;
          v24 = v23 + 1;
          if ( (Num32BitValues & 4) == 0 )
            v24 = v23;
          if ( v24 > 1 )
          {
            v6 = ErrorRootSignature(
                   a3,
                   "Root descriptor flags cannot specify more than one DATA_* flag at a time (root descriptor flags %x).\n",
                   Num32BitValues);
            if ( v6 < 0 )
              goto LABEL_90;
          }
          RangeType = GetRangeType((unsigned int)ParameterType, ShaderVisibility);
          i = v51;
          v19 = RootSignatureVerifier::AddRegisterRange(
                  this,
                  v51,
                  1,
                  0xFFFFFFFFLL,
                  RangeType,
                  v50,
                  1,
                  pParameters[v16].DescriptorTable.NumDescriptorRanges,
                  pParameters[v16].Constants.RegisterSpace,
                  a3);
        }
        else
        {
          v19 = ErrorRootSignature(a3, "Unsupported ParameterType value %u (root parameter %u)\n", ParameterType, i);
        }
        v6 = v19;
        if ( v19 < 0 )
          goto LABEL_90;
LABEL_35:
        v13 = (char)v55;
      }
      NumDescriptorRanges = pParameters[v16].DescriptorTable.NumDescriptorRanges;
      pDescriptorRanges = (const struct D3D12_DESCRIPTOR_RANGE1 *)pParameters[v16].DescriptorTable.pDescriptorRanges;
      v53[0] = *((_DWORD *)this + 132);
      v6 = DescriptorTableVerifier::Verify(
             (DescriptorTableVerifier *)v53,
             pDescriptorRanges,
             NumDescriptorRanges,
             i,
             a3);
      if ( v6 >= 0 )
      {
        v28 = (int *)*((_QWORD *)this + 68);
        if ( v28 )
          v29 = *v28;
        else
          v29 = -65552;
        v53[0] = v29;
        for ( k = 0; ; k = v52 + 1 )
        {
          v52 = k;
          if ( (unsigned int)k >= pParameters[v16].DescriptorTable.NumDescriptorRanges )
            goto LABEL_35;
          v31 = 3 * k;
          v32 = pParameters[v16].DescriptorTable.pDescriptorRanges;
          v33 = *(&v32->OffsetInDescriptorsFromTableStart + 2 * v31);
          if ( (v33 & v29) != 0 )
          {
            v6 = ErrorRootSignature(a3, "Unsupported bit-flag set (descriptor range flags %x).\n", v33);
            if ( v6 < 0 )
              break;
          }
          v34 = *(&v32->OffsetInDescriptorsFromTableStart + 2 * v31);
          v35 = (v34 & 1) + 1;
          if ( (v34 & 0x10000) == 0 )
            v35 = *(&v32->OffsetInDescriptorsFromTableStart + 2 * v31) & 1;
          if ( v35 > 1 )
          {
            v6 = ErrorRootSignature(
                   a3,
                   "Descriptor range flags cannot specify more than one DESCRIPTOR_* flag at a time (descriptor range flags %x).\n",
                   v34);
            if ( v6 < 0 )
              break;
          }
          v36 = *(&v32->OffsetInDescriptorsFromTableStart + 2 * v31);
          if ( *((_DWORD *)&v32->RangeType + 2 * v31) == 3 )
          {
            if ( (v36 & 0xE) != 0 )
            {
              v6 = ErrorRootSignature(
                     a3,
                     "Sampler descriptor ranges can't specify DATA_* flags since there is no data pointed to by samplers "
                     "(descriptor range flags %x).\n",
                     v36);
              if ( v6 < 0 )
                break;
            }
            if ( (*(&v32->OffsetInDescriptorsFromTableStart + 2 * v31) & 0x10000) != 0 )
            {
              v39 = ErrorRootSignature(
                      a3,
                      "Sampler descriptor ranges can't specify DESCRIPTORS_STATIC_KEEPING_BUFFER_BOUNDS_CHECKS, since the"
                      "re are no bounds to check (descriptor range flags %x).\n");
LABEL_76:
              v6 = v39;
              if ( v39 < 0 )
                break;
            }
          }
          else
          {
            v37 = ((v36 >> 1) & 1) + 1;
            if ( (v36 & 8) == 0 )
              v37 = (v36 >> 1) & 1;
            v38 = v37 + 1;
            if ( (v36 & 4) == 0 )
              v38 = v37;
            if ( v38 > 1 )
            {
              v6 = ErrorRootSignature(
                     a3,
                     "Descriptor range flags cannot specify more than one DATA_* flag at a time (descriptor range flags %x).\n",
                     v36);
              if ( v6 < 0 )
                break;
            }
            if ( (*(_BYTE *)(&v32->OffsetInDescriptorsFromTableStart + 2 * v31) & 9) == 9 )
            {
              v39 = ErrorRootSignature(
                      a3,
                      "Descriptor range flags cannot specify DESCRIPTORS_VOLATILE with the DATA_STATIC flag at the same t"
                      "ime (descriptor range flags %x). DATA_STATIC_WHILE_SET_AT_EXECUTE is fine to combine with DESCRIPT"
                      "ORS_VOLATILE, since DESCRIPTORS_VOLATILE still requires descriptors don't change during execution. \n");
              goto LABEL_76;
            }
          }
          v49 = *(&v32->RegisterSpace + 2 * v31);
          v48 = *(&v32->BaseShaderRegister + 2 * v31);
          v47 = *(&v32->NumDescriptors + 2 * v31);
          v40 = *((_DWORD *)&v32->RangeType + 2 * v31);
          i = v51;
          v6 = RootSignatureVerifier::AddRegisterRange(this, v51, 0, v52, v40, v50, v47, v48, v49, a3);
          if ( v6 < 0 )
            break;
          v29 = v53[0];
        }
      }
LABEL_90:
      v4 = a2;
    }
  }
LABEL_91:
  if ( v8 && v8->Version != v4->Version )
    DeleteRootSignature(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003bbfc  mov     rax, rsp
0x18003bbff  mov     [rax+8], rbx
0x18003bc03  mov     [rax+10h], rdx
0x18003bc07  push    rbp
0x18003bc08  push    rsi
0x18003bc09  push    rdi
0x18003bc0a  push    r12
0x18003bc0c  push    r13
0x18003bc0e  push    r14
0x18003bc10  push    r15
0x18003bc12  sub     rsp, 60h
0x18003bc16  mov     qword ptr [rax+20h], 0
0x18003bc1e  mov     rdi, r8
0x18003bc21  mov     rsi, rdx
0x18003bc24  mov     r14, rcx
0x18003bc27  test    rdx, rdx
0x18003bc2a  jnz     short loc_18003BC36
0x18003bc2c  mov     ebx, 80070057h
0x18003bc31  jmp     loc_18003C200
0x18003bc36  test    rdi, rdi
0x18003bc39  jz      short loc_18003BC42
0x18003bc3b  mov     qword ptr [r8], 0
0x18003bc42  lea     r8, [rsp+98h+arg_18]; struct D3D12_VERSIONED_ROOT_SIGNATURE_DESC **
0x18003bc4a  mov     edx, 3; enum D3D_ROOT_SIGNATURE_VERSION
0x18003bc4f  mov     rcx, rsi; struct D3D12_VERSIONED_ROOT_SIGNATURE_DESC *
0x18003bc52  call    ?ConvertRootSignature@@YAJPEBUD3D12_VERSIONED_ROOT_SIGNATURE_DESC@@W4D3D_ROOT_SIGNATURE_VERSION@@PEAPEBU1@@Z; ConvertRootSignature(D3D12_VERSIONED_ROOT_SIGNATURE_DESC const *,D3D_ROOT_SIGNATURE_VERSION,D3D12_VERSIONED_ROOT_SIGNATURE_DESC const * *)
0x18003bc57  mov     r15, [rsp+98h+arg_18]
0x18003bc5f  mov     ebx, eax
0x18003bc61  test    eax, eax
0x18003bc63  js      loc_18003C1EC
0x18003bc69  mov     rax, [r14+220h]
0x18003bc70  test    rax, rax
0x18003bc73  jz      short loc_18003BC7A
0x18003bc75  mov     ecx, [rax+8]
0x18003bc78  jmp     short loc_18003BC7F
0x18003bc7a  mov     ecx, 7FFFF000h
0x18003bc7f  mov     r8d, [r15+28h]
0x18003bc83  test    ecx, r8d
0x18003bc86  jz      short loc_18003BCA1
0x18003bc88  lea     rdx, aUnsupportedBit_2; "Unsupported bit-flag set (root signatur"...
0x18003bc8f  mov     rcx, rdi
0x18003bc92  call    ErrorRootSignature
0x18003bc97  mov     ebx, eax
0x18003bc99  test    eax, eax
0x18003bc9b  js      loc_18003C1EC
0x18003bca1  mov     eax, [r15+28h]
0x18003bca5  xor     r12b, r12b
0x18003bca8  mov     byte ptr [rsp+98h+arg_18], r12b
0x18003bcb0  test    al, al
0x18003bcb2  jns     short loc_18003BD16
0x18003bcb4  cmp     [r14+202h], r12b
0x18003bcbb  jz      short loc_18003BCED
0x18003bcbd  test    eax, 0FFFFFF7Fh
0x18003bcc2  jz      short loc_18003BCE0
0x18003bcc4  mov     r8d, eax
0x18003bcc7  lea     rdx, aD3d12RootSigna_0; "D3D12_ROOT_SIGNATURE_FLAG_LOCAL_ROOT_SI"...
0x18003bcce  mov     rcx, rdi
0x18003bcd1  call    ErrorRootSignature
0x18003bcd6  mov     ebx, eax
0x18003bcd8  test    eax, eax
0x18003bcda  js      loc_18003C1EC
0x18003bce0  mov     r12b, 1
0x18003bce3  mov     byte ptr [rsp+98h+arg_18], r12b
0x18003bceb  jmp     short loc_18003BD09
0x18003bced  mov     r8d, eax
0x18003bcf0  lea     rdx, aD3d12RootSigna; "D3D12_ROOT_SIGNATURE_FLAG_LOCAL_ROOT_SI"...
0x18003bcf7  mov     rcx, rdi
0x18003bcfa  call    ErrorRootSignature
0x18003bcff  mov     ebx, eax
0x18003bd01  test    eax, eax
0x18003bd03  js      loc_18003C1EC
0x18003bd09  mov     eax, [r15+28h]
0x18003bd0d  mov     [r14+214h], eax
0x18003bd14  jmp     short loc_18003BD1D
0x18003bd16  mov     [r14+218h], eax
0x18003bd1d  xor     ebp, ebp
0x18003bd1f  mov     [rsp+98h+var_44], ebp
0x18003bd23  cmp     ebp, [r15+8]
0x18003bd27  jnb     loc_18003C0D6
0x18003bd2d  mov     r13, [r15+10h]
0x18003bd31  mov     esi, ebp
0x18003bd33  shl     rsi, 5
0x18003bd37  mov     edx, [rsi+r13+18h]
0x18003bd3c  mov     ecx, edx
0x18003bd3e  mov     [rsp+98h+var_48], edx
0x18003bd42  test    edx, edx
0x18003bd44  jz      short loc_18003BD96
0x18003bd46  sub     ecx, 1
0x18003bd49  jz      short loc_18003BD96
0x18003bd4b  sub     ecx, 1
0x18003bd4e  jz      short loc_18003BD96
0x18003bd50  sub     ecx, 1
0x18003bd53  jz      short loc_18003BD96
0x18003bd55  sub     ecx, 1
0x18003bd58  jz      short loc_18003BD96
0x18003bd5a  sub     ecx, 1
0x18003bd5d  jz      short loc_18003BD96
0x18003bd5f  sub     ecx, 1
0x18003bd62  jz      short loc_18003BD69
0x18003bd64  cmp     ecx, 1
0x18003bd67  jnz     short loc_18003BD73
0x18003bd69  cmp     byte ptr [r14+203h], 0
0x18003bd71  jnz     short loc_18003BD96
0x18003bd73  mov     r8d, edx
0x18003bd76  mov     r9d, ebp
0x18003bd79  lea     rdx, aUnsupportedSha; "Unsupported ShaderVisibility value %u ("...
0x18003bd80  mov     rcx, rdi
0x18003bd83  call    ErrorRootSignature
0x18003bd88  mov     ebx, eax
0x18003bd8a  test    eax, eax
0x18003bd8c  js      loc_18003C1E4
0x18003bd92  mov     edx, [rsp+98h+var_48]
0x18003bd96  test    r12b, r12b
0x18003bd99  jz      short loc_18003BDBE
0x18003bd9b  test    edx, edx
0x18003bd9d  jz      short loc_18003BDBE
0x18003bd9f  mov     r8d, edx
0x18003bda2  mov     r9d, ebp
0x18003bda5  lea     rdx, aLocalRootSigna; "Local root signatures only support shad"...
0x18003bdac  mov     rcx, rdi
0x18003bdaf  call    ErrorRootSignature
0x18003bdb4  mov     ebx, eax
0x18003bdb6  test    eax, eax
0x18003bdb8  js      loc_18003C1E4
0x18003bdbe  mov     r12d, [rsi+r13]
0x18003bdc2  mov     ecx, r12d
0x18003bdc5  test    r12d, r12d
0x18003bdc8  jz      loc_18003BF18
0x18003bdce  sub     ecx, 1
0x18003bdd1  jz      loc_18003BEBA
0x18003bdd7  sub     ecx, 1
0x18003bdda  jz      short loc_18003BE14
0x18003bddc  sub     ecx, 1
0x18003bddf  jz      short loc_18003BE14
0x18003bde1  cmp     ecx, 1
0x18003bde4  jz      short loc_18003BE14
0x18003bde6  mov     r9d, ebp
0x18003bde9  lea     rdx, aUnsupportedPar; "Unsupported ParameterType value %u (roo"...
0x18003bdf0  mov     r8d, r12d
0x18003bdf3  mov     rcx, rdi
0x18003bdf6  call    ErrorRootSignature
0x18003bdfb  mov     ebx, eax
0x18003bdfd  test    eax, eax
0x18003bdff  js      loc_18003C1E4
0x18003be05  mov     r12b, byte ptr [rsp+98h+arg_18]
0x18003be0d  inc     ebp
0x18003be0f  jmp     loc_18003BD1F
0x18003be14  mov     rax, [r14+220h]
0x18003be1b  test    rax, rax
0x18003be1e  jz      short loc_18003BE25
0x18003be20  mov     ecx, [rax+4]
0x18003be23  jmp     short loc_18003BE2A
0x18003be25  mov     ecx, 0FFFFFFF1h
0x18003be2a  mov     ebp, [rsi+r13+10h]
0x18003be2f  test    ecx, ebp
0x18003be31  jz      short loc_18003BE4F
0x18003be33  mov     r8d, ebp
0x18003be36  lea     rdx, aUnsupportedBit_0; "Unsupported bit-flag set (root descript"...
0x18003be3d  mov     rcx, rdi
0x18003be40  call    ErrorRootSignature
0x18003be45  mov     ebx, eax
0x18003be47  test    eax, eax
0x18003be49  js      loc_18003C1E4
0x18003be4f  mov     eax, ebp
0x18003be51  shr     eax, 1
0x18003be53  and     eax, 1
0x18003be56  test    bpl, 8
0x18003be5a  lea     ecx, [rax+1]
0x18003be5d  cmovz   ecx, eax
0x18003be60  test    bpl, 4
0x18003be64  lea     eax, [rcx+1]
0x18003be67  cmovz   eax, ecx
0x18003be6a  cmp     eax, 1
0x18003be6d  jbe     short loc_18003BE8B
0x18003be6f  mov     r8d, ebp
0x18003be72  lea     rdx, aRootDescriptor_0; "Root descriptor flags cannot specify mo"...
0x18003be79  mov     rcx, rdi
0x18003be7c  call    ErrorRootSignature
0x18003be81  mov     ebx, eax
0x18003be83  test    eax, eax
0x18003be85  js      loc_18003C1E4
0x18003be8b  mov     ecx, r12d
0x18003be8e  call    GetRangeType
0x18003be93  mov     ecx, [rsi+r13+0Ch]
0x18003be98  or      r9d, 0FFFFFFFFh
0x18003be9c  mov     ebp, [rsp+98h+var_44]
0x18003bea0  mov     r8d, 1
0x18003bea6  mov     [rsp+98h+var_50], rdi
0x18003beab  mov     [rsp+98h+var_58], ecx
0x18003beaf  mov     ecx, [rsi+r13+8]
0x18003beb4  mov     [rsp+98h+var_60], ecx
0x18003beb8  jmp     short loc_18003BEF5
0x18003beba  cmp     dword ptr [rsi+r13+10h], 0
0x18003bec0  jnz     short loc_18003BED1
0x18003bec2  lea     rdx, aRootConstantsN; "Root constants Num32BitValues should be"...
0x18003bec9  mov     rcx, rdi
0x18003becc  call    ErrorRootSignature
0x18003bed1  mov     eax, [rsi+r13+0Ch]
0x18003bed6  mov     r9d, [rsi+r13+10h]
0x18003bedb  mov     [rsp+98h+var_50], rdi
0x18003bee0  mov     [rsp+98h+var_58], eax
0x18003bee4  mov     eax, [rsi+r13+8]
0x18003bee9  mov     [rsp+98h+var_60], eax
0x18003beed  mov     eax, 2
0x18003bef2  mov     r8d, eax
0x18003bef5  mov     ecx, [rsp+98h+var_48]
0x18003bef9  mov     edx, ebp
0x18003befb  mov     [rsp+98h+var_68], 1
0x18003bf03  mov     [rsp+98h+var_70], ecx
0x18003bf07  mov     rcx, r14
0x18003bf0a  mov     dword ptr [rsp+98h+var_78], eax
0x18003bf0e  call    ?AddRegisterRange@RootSignatureVerifier@@AEAAJIW4NODE_TYPE@1@IW4D3D12_DESCRIPTOR_RANGE_TYPE@@W4D3D12_SHADER_VISIBILITY@@IIIPEAPEAUID3D10Blob@@@Z; RootSignatureVerifier::AddRegisterRange(uint,RootSignatureVerifier::NODE_TYPE,uint,D3D12_DESCRIPTOR_RANGE_TYPE,D3D12_SHADER_VISIBILITY,uint,uint,uint,ID3D10Blob * *)
0x18003bf13  jmp     loc_18003BDFB
0x18003bf18  mov     eax, [r14+210h]
0x18003bf1f  lea     rcx, [rsp+98h+var_3C]; this
0x18003bf24  mov     r8d, [rsi+r13+8]; unsigned int
0x18003bf29  mov     r9d, ebp; unsigned int
0x18003bf2c  mov     rdx, [rsi+r13+10h]; struct D3D12_DESCRIPTOR_RANGE1 *
0x18003bf31  mov     [rsp+98h+var_3C], eax
0x18003bf35  mov     [rsp+98h+var_78], rdi; struct ID3D10Blob **
0x18003bf3a  call    ?Verify@DescriptorTableVerifier@@QEAAJPEBUD3D12_DESCRIPTOR_RANGE1@@IIPEAPEAUID3D10Blob@@@Z; DescriptorTableVerifier::Verify(D3D12_DESCRIPTOR_RANGE1 const *,uint,uint,ID3D10Blob * *)
0x18003bf3f  mov     ebx, eax
0x18003bf41  test    eax, eax
0x18003bf43  js      loc_18003C1E4
0x18003bf49  mov     rax, [r14+220h]
0x18003bf50  test    rax, rax
0x18003bf53  jz      short loc_18003BF59
0x18003bf55  mov     ecx, [rax]
0x18003bf57  jmp     short loc_18003BF5E
0x18003bf59  mov     ecx, 0FFFEFFF0h
0x18003bf5e  mov     [rsp+98h+var_3C], ecx
0x18003bf62  xor     r12d, r12d
0x18003bf65  mov     [rsp+98h+var_40], r12d
0x18003bf6a  cmp     r12d, [rsi+r13+8]
0x18003bf6f  jnb     loc_18003BE05
0x18003bf75  lea     rbp, [r12+r12*2]
0x18003bf79  mov     r12, [rsi+r13+10h]
0x18003bf7e  mov     r8d, [r12+rbp*8+10h]
0x18003bf83  test    ecx, r8d
0x18003bf86  jz      short loc_18003BFA1
0x18003bf88  lea     rdx, aUnsupportedBit; "Unsupported bit-flag set (descriptor ra"...
0x18003bf8f  mov     rcx, rdi
0x18003bf92  call    ErrorRootSignature
0x18003bf97  mov     ebx, eax
0x18003bf99  test    eax, eax
0x18003bf9b  js      loc_18003C1E4
0x18003bfa1  mov     r8d, [r12+rbp*8+10h]
0x18003bfa6  mov     ecx, r8d
0x18003bfa9  and     ecx, 1
0x18003bfac  bt      r8d, 10h
0x18003bfb1  lea     eax, [rcx+1]
0x18003bfb4  cmovnb  eax, ecx
0x18003bfb7  cmp     eax, 1
0x18003bfba  jbe     short loc_18003BFD5
0x18003bfbc  lea     rdx, aDescriptorRang_2; "Descriptor range flags cannot specify m"...
0x18003bfc3  mov     rcx, rdi
0x18003bfc6  call    ErrorRootSignature
0x18003bfcb  mov     ebx, eax
0x18003bfcd  test    eax, eax
0x18003bfcf  js      loc_18003C1E4
0x18003bfd5  cmp     dword ptr [r12+rbp*8], 3
0x18003bfda  mov     r8d, [r12+rbp*8+10h]
0x18003bfdf  jz      short loc_18003C033
0x18003bfe1  mov     eax, r8d
0x18003bfe4  shr     eax, 1
0x18003bfe6  and     eax, 1
0x18003bfe9  test    r8b, 8
0x18003bfed  lea     ecx, [rax+1]
0x18003bff0  cmovz   ecx, eax
0x18003bff3  test    r8b, 4
0x18003bff7  lea     eax, [rcx+1]
0x18003bffa  cmovz   eax, ecx
0x18003bffd  cmp     eax, 1
0x18003c000  jbe     short loc_18003C01B
0x18003c002  lea     rdx, aDescriptorRang_1; "Descriptor range flags cannot specify m"...
0x18003c009  mov     rcx, rdi
0x18003c00c  call    ErrorRootSignature
0x18003c011  mov     ebx, eax
0x18003c013  test    eax, eax
0x18003c015  js      loc_18003C1E4
0x18003c01b  mov     r8d, [r12+rbp*8+10h]
0x18003c020  mov     eax, r8d
0x18003c023  and     eax, 9
0x18003c026  cmp     al, 9
0x18003c028  jnz     short loc_18003C077
0x18003c02a  lea     rdx, aDescriptorRang_0; "Descriptor range flags cannot specify D"...
0x18003c031  jmp     short loc_18003C065
0x18003c033  test    r8b, 0Eh
0x18003c037  jz      short loc_18003C052
0x18003c039  lea     rdx, aSamplerDescrip; "Sampler descriptor ranges can't specify"...
0x18003c040  mov     rcx, rdi
0x18003c043  call    ErrorRootSignature
0x18003c048  mov     ebx, eax
0x18003c04a  test    eax, eax
0x18003c04c  js      loc_18003C1E4
0x18003c052  mov     r8d, [r12+rbp*8+10h]
0x18003c057  bt      r8d, 10h
0x18003c05c  jnb     short loc_18003C077
0x18003c05e  lea     rdx, aSamplerDescrip_0; "Sampler descriptor ranges can't specify"...
0x18003c065  mov     rcx, rdi
  ... truncated ...
```
