# ValidateHeapAndResourceCreation(TDebugOutputFunctor &,DeviceValidationInfo const &,CD3DX12_HEAP_DESC const &,unsigned __int64,CD3DX12_RESOURCE_DESC2 const &,D3D12_CLEAR_VALUE const *,uint,DXGI_FORMAT const *,unsigned __int64)

- ea: `0x18006a598`
- end: `0x18006aa5a`
- name: `?ValidateHeapAndResourceCreation@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUCD3DX12_HEAP_DESC@@_KAEBUCD3DX12_RESOURCE_DESC2@@PEBUD3D12_CLEAR_VALUE@@IPEBW4DXGI_FORMAT@@3@Z`
- size: `1218`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, const struct DeviceValidationInfo *@<rdx>, const struct CD3DX12_HEAP_DESC *@<r8>, unsigned __int64@<r9>, enum D3D12_RESOURCE_DIMENSION *, const struct D3D12_CLEAR_VALUE *, unsigned int, const enum DXGI_FORMAT *, unsigned __int64)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18002b520`
- `0x18006a314`
- `0x1800e674c`
- `0x1800e69d8`

## callees

- `0x18002ef50`
- `0x180067b6c`
- `0x18006a1e0`
- `0x18006a598`
- `0x180074dd4`
- `0x18007de6c`
- `0x1800a15c8`
- `0x1800a87c4`
- `0x1800abc10`
- `0x1800bb480`
- `0x1800fe198`
- `0x180262020`

## string_xrefs

- `0x18006aa24`: `This resource cannot be created on this heap, due to unsatisfied resource alignment requirements. The resource must be aligned to %I64u. The heap must also be aligned to a value greater to or equal than the resource. The heap is aligned to %I64u, and the resource offset in the heap is %I64u.`
- `0x18006a623`: `Resource created with D3D12_RESOURCE_FLAG_RAYTRACING_ACCELERATION_STRUCTURE bit set must also set the D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS_VIEW bit.`
- `0x18006a7ff`: `A texture resource with either D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET or D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL set cannot be created on a heap with the D3D12_HEAP_FLAG_DENY_RT_DS_TEXTURES flag.`
- `0x18006a881`: `A texture resource cannot be created on a D3D12_HEAP_TYPE_UPLOAD or D3D12_HEAP_TYPE_READBACK heap. Investigate CopyTextureRegion to copy texture data in CPU accessible buffers, or investigate D3D12_HEAP_TYPE_CUSTOM and WriteToSubresource for UMA adapter optimizations, or investigate D3D12_HEAP_TYPE_GPU_UPLOAD to create texture resource on CPU accessible heaps.`
- `0x18006a810`: `A texture resource without either D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET or D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL set cannot be created on a heap with the D3D12_HEAP_FLAG_DENY_NON_RT_DS_TEXTURES flag.`
- `0x18006a7b5`: `D3D12_RESOURCE_DESC::Layout is invalid for the current device, because it does not support standard swizzle (D3D12_FEATURE_DATA_D3D12_OPTIONS::StandardSwizzle64KBSupported is FALSE). For cross-adapter-shared textures on such devices, D3D12_TEXTURE_LAYOUT_64KB_STANDARD_SWIZZLErequires that the follow flags not be set: D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET, D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL, D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS.`
- `0x18006a8b0`: `A buffer resource cannot be created on a heap with the D3D12_HEAP_FLAG_DENY_BUFFERS flag.`
- `0x18006a89e`: `A buffer cannot be created on a D3D12_HEAP_TYPE_UPLOAD or D3D12_HEAP_TYPE_READBACK heap when either D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET or D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS is used.`

## pseudocode

```c
__int64 __fastcall ValidateHeapAndResourceCreation(
        struct TDebugOutputFunctor *a1,
        enum D3D_FEATURE_LEVEL *a2,
        const struct CD3DX12_HEAP_DESC *a3,
        __int64 a4,
        enum D3D12_RESOURCE_DIMENSION *a5,
        const struct D3D12_CLEAR_VALUE *a6,
        unsigned int a7,
        enum DXGI_FORMAT *a8,
        unsigned __int64 a9)
{
  __int64 result; // rax
  __int64 v14; // rax
  int v15; // r10d
  __int64 v16; // r9
  int v17; // ecx
  enum DXGI_FORMAT v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // rax
  const char *Name; // rax
  unsigned int v22; // r8d
  enum D3D12_RESOURCE_DIMENSION *v23; // rdx
  const char *v24; // rax
  __int64 v25; // r8
  const char *v26; // rcx
  int v27; // r9d
  bool v28; // dl
  enum DXGI_FORMAT v29; // ecx
  const char *v30; // rax
  const char *v31; // r8
  enum DXGI_FORMAT v32; // r9d
  char IsEnabled; // al
  __int64 v34; // rcx
  bool v35; // zf
  __int64 v36; // rax
  int v37; // [rsp+58h] [rbp-71h] BYREF
  __int64 v38; // [rsp+5Ch] [rbp-6Dh]
  _BYTE v39[8]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v40; // [rsp+78h] [rbp-51h]
  char v41; // [rsp+A0h] [rbp-29h]

  result = ValidateResourceDescription(
             a1,
             (const struct DeviceValidationInfo *)a2,
             (const struct CD3DX12_RESOURCE_DESC2 *)a5,
             a6,
             a7,
             a8,
             a9,
             (struct CD3DX12_RESOURCE_DESC2 *)v39,
             0);
  if ( (int)result >= 0 )
  {
    if ( (a5[12] & 0x100) != 0 )
    {
      if ( (a5[12] & 4) == 0 )
        TDebugOutputFunctor::operator()(
          a1,
          599,
          "Resource created with D3D12_RESOURCE_FLAG_RAYTRACING_ACCELERATION_STRUCTURE bit set must also set the D3D12_RE"
          "SOURCE_FLAG_ALLOW_UNORDERED_ACCESS_VIEW bit.");
      if ( *((_DWORD *)a3 + 2) != 1 )
      {
        if ( *((_DWORD *)a3 + 2) != 4 )
          goto LABEL_11;
        LODWORD(v14) = *((_DWORD *)a3 + 5);
        if ( !(_DWORD)v14 )
          LODWORD(v14) = 1;
        _BitScanForward((unsigned int *)&v14, v14);
        if ( *((_DWORD *)a3 + 4) != (a2[5 * v14] != 0) + 1 || *((_DWORD *)a3 + 3) != 1 )
LABEL_11:
          TDebugOutputFunctor::operator()(
            a1,
            638,
            "If D3D12_RESOURCE_FLAG_RAYTRACING_ACCELERATION_STRUCTURE is set, then heap type must be D3D12_HEAP_TYPE_DEFA"
            "ULT (or custom heap equivalent). ");
      }
    }
    v15 = *((_DWORD *)a3 + 10);
    v16 = v15 & 0x20;
    v17 = 0;
    if ( (v15 & 0x20) != 0 )
    {
      if ( *((_DWORD *)a5 + 11) != 1 && (unsigned int)(*((_DWORD *)a5 + 11) - 3) >= 2 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          638,
          "If D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set then the resource layout must be either D3D12_TEXTURE_LAYOUT_RO"
          "W_MAJOR or D3D12_TEXTURE_LAYOUT_64KB_STANDARD_SWIZZLE.",
          v16);
        return 2147942487LL;
      }
      if ( *((_WORD *)a5 + 15) != 1 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          722,
          "If D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set then ResourceDesc.MipLevels must be 1.  ResourceDesc.MipLevels is %u",
          *((unsigned __int16 *)a5 + 15));
        return 2147942487LL;
      }
      v17 = 1;
      if ( *((_DWORD *)a5 + 11) != 4 )
      {
        v18 = *((_DWORD *)a5 + 8);
        v19 = 0xFFFFFFFFLL;
        v20 = 0xFFFFFFFFLL;
        if ( (unsigned int)v18 < 0xC0 )
          v20 = (unsigned int)v18;
        if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v20 + 32) & 0x10) != 0 )
          goto LABEL_26;
        if ( (unsigned int)v18 < 0xC0 )
          v19 = (unsigned int)v18;
        v17 = 1;
        v19 *= 5;
        if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 8 * v19 + 32) & 8) != 0 )
        {
LABEL_26:
          Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v19);
          TDebugOutputFunctor::operator()(
            a1,
            738,
            "D3D12_RESOURCE_DESC::Format is invalid.  The value is %s.  When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set,"
            " the format cannot be YUV or planar.",
            Name);
          return 2147942487LL;
        }
      }
    }
    v22 = *((_DWORD *)a5 + 12);
    if ( v17 != ((v22 >> 4) & 1) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        599,
        "D3D12_RESOURCE_DESC::Flags is invalid.  The value is %x.  D3D12_RESOURCE_FLAG_ALLOW_CROSS_ADAPTER must be specif"
        "ied if and only if D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set.",
        v22);
      return 2147942487LL;
    }
    v23 = a5 + 11;
    if ( *((_DWORD *)a5 + 11) == 3 && !*((_BYTE *)a2 + 694) )
    {
      if ( (v15 & 0x20) == 0 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          724,
          "D3D12_RESOURCE_DESC::Layout is invalid for the current device, because it does not support standard swizzle. D"
          "3D12_TEXTURE_LAYOUT_64KB_STANDARD_SWIZZLE can only be used when either D3D12_FEATURE_DATA_D3D12_OPTIONS::Stand"
          "ardSwizzle64KBSupported is TRUE,or the D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER flag is set.",
          v16);
        return 2147942487LL;
      }
      if ( (v22 & 7) != 0 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          599,
          "D3D12_RESOURCE_DESC::Layout is invalid for the current device, because it does not support standard swizzle (D"
          "3D12_FEATURE_DATA_D3D12_OPTIONS::StandardSwizzle64KBSupported is FALSE). For cross-adapter-shared textures on "
          "such devices, D3D12_TEXTURE_LAYOUT_64KB_STANDARD_SWIZZLErequires that the follow flags not be set: D3D12_RESOU"
          "RCE_FLAG_ALLOW_RENDER_TARGET, D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL, D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS.",
          v16);
        return 2147942487LL;
      }
    }
    if ( *a5 == D3D12_RESOURCE_DIMENSION_BUFFER )
    {
      if ( (unsigned int)(*((_DWORD *)a3 + 2) - 2) <= 1 && (v41 & 5) != 0 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          638,
          "A buffer cannot be created on a D3D12_HEAP_TYPE_UPLOAD or D3D12_HEAP_TYPE_READBACK heap when either D3D12_RESO"
          "URCE_FLAG_ALLOW_RENDER_TARGET or D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS is used.",
          v16);
        return 2147942487LL;
      }
      if ( (v15 & 4) != 0 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          638,
          "A buffer resource cannot be created on a heap with the D3D12_HEAP_FLAG_DENY_BUFFERS flag.",
          v16);
        return 2147942487LL;
      }
    }
    else if ( *a5 == D3D12_RESOURCE_DIMENSION_TEXTURE1D || (unsigned int)(*a5 - 3) <= 1 )
    {
      if ( (unsigned int)(*((_DWORD *)a3 + 2) - 2) <= 1 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          638,
          "A texture resource cannot be created on a D3D12_HEAP_TYPE_UPLOAD or D3D12_HEAP_TYPE_READBACK heap. Investigate"
          " CopyTextureRegion to copy texture data in CPU accessible buffers, or investigate D3D12_HEAP_TYPE_CUSTOM and W"
          "riteToSubresource for UMA adapter optimizations, or investigate D3D12_HEAP_TYPE_GPU_UPLOAD to create texture r"
          "esource on CPU accessible heaps.",
          v16);
        return 2147942487LL;
      }
      if ( (v22 & 3) != 0 )
      {
        if ( (v15 & 0x40) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a1,
            638,
            "A texture resource with either D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET or D3D12_RESOURCE_FLAG_ALLOW_DEPTH_ST"
            "ENCIL set cannot be created on a heap with the D3D12_HEAP_FLAG_DENY_RT_DS_TEXTURES flag.",
            v16);
          return 2147942487LL;
        }
      }
      else if ( (v15 & 0x80u) != 0 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          638,
          "A texture resource without either D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET or D3D12_RESOURCE_FLAG_ALLOW_DEPTH_S"
          "TENCIL set cannot be created on a heap with the D3D12_HEAP_FLAG_DENY_NON_RT_DS_TEXTURES flag.",
          v16);
        return 2147942487LL;
      }
      if ( *v23 == D3D12_RESOURCE_DIMENSION_BUFFER && (*a5 != D3D12_RESOURCE_DIMENSION_TEXTURE2D || (v15 & 0x20) == 0) )
      {
        D3D12ToStr((const enum D3D12_TEXTURE_LAYOUT *)a5 + 11);
        v24 = D3D12ToStr(a5);
        v26 = Src;
        if ( !v27 )
          v26 = "not ";
        TDebugOutputFunctor::operator()(
          a1,
          724,
          "D3D12_RESOURCE_DESC::Layout can be D3D12_TEXTURE_LAYOUT_ROW_MAJOR only when D3D12_RESOURCE_DESC::Dimension is "
          "D3D12_RESOURCE_DIMENSION_BUFFER or when D3D12_RESOURCE_DESC::Dimension is D3D12_RESOURCE_DIMENSION_TEXTURE2D a"
          "nd the D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER flag is set.Dimension is %s.  Layout is %s. Cross adapter is %sset.",
          v24,
          v25,
          v26);
        return 2147942487LL;
      }
    }
    if ( (v15 & 8) != 0 )
    {
      if ( *a5 != D3D12_RESOURCE_DIMENSION_TEXTURE2D
        || *((_QWORD *)a5 + 1)
        || (unsigned __int16)(*((_WORD *)a5 + 14) - 1) > 1u
        || *((_WORD *)a5 + 15) != 1
        || *((_DWORD *)a5 + 9) != 1
        || *((_DWORD *)a5 + 10)
        || *v23 != ((_DWORD)v16 != 0)
        || (v22 & 0xC2) != 0 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          640,
          "When D3D12_HEAP_FLAGS has D3D12_HEAP_FLAG_ALLOW_DISPLAY set, the following D3D12_RESOURCE_DESC members must be"
          " as follows: Dimension must be D3D12_RESOURCE_DIMENSION_TEXTURE2D, Alignment must be 0, DepthOrArraySize must "
          "be 1 or 2, MipLevels must be 1, SampleDesc.Count must be 1, SampleDesc.Quality must be 0, Layout must be D3D12"
          "_TEXTURE_LAYOUT_UNKNOWN (or ROW_MAJOR for cross-adapter heaps), and Flags must not have D3D12_RESOURCE_FLAG_AL"
          "LOW_DEPTH_STENCIL or D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY or D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set.",
          v16);
        return 2147942487LL;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
      {
        v37 = *((_DWORD *)a5 + 8);
        v38 = 0;
        (*(void (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)a2 + 83) + 104LL))(*((_QWORD *)a2 + 83), 3, &v37);
        if ( (v38 & 0x80000) == 0 && (v38 & 0x1000000000000LL) == 0 )
        {
          FeatureLevelToString(a2[164]);
          v29 = *((_DWORD *)a5 + 8);
LABEL_69:
          v30 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v29, v28);
          TDebugOutputFunctor::operator()(
            a1,
            640,
            "D3D12_RESOURCE_DESC::Format is not supported with D3D12_HEAP_FLAG_ALLOW_DISPLAY at the current feature level"
            ". Format = %s, FeatureLevel is %s.",
            v30,
            v31);
          return 2147942487LL;
        }
      }
      else if ( !(unsigned __int8)CD3D11FormatHelper::IsCrossD3DAPIShareableFormat(
                                    *((unsigned int *)a5 + 8),
                                    *((unsigned int *)a2 + 165)) )
      {
        FeatureLevelToString(a2[164]);
        v29 = v32;
        goto LABEL_69;
      }
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12TightAlignment>::GetImpl'::`2'::impl);
    v34 = a4 | *((_QWORD *)a3 + 4);
    v35 = IsEnabled == 0;
    v36 = v40 - 1;
    if ( v35 )
    {
      if ( (v36 & v34) != 0 )
      {
LABEL_77:
        TDebugOutputFunctor::operator()(
          a1,
          638,
          "This resource cannot be created on this heap, due to unsatisfied resource alignment requirements. The resource"
          " must be aligned to %I64u. The heap must also be aligned to a value greater to or equal than the resource. The"
          " heap is aligned to %I64u, and the resource offset in the heap is %I64u.",
          v40,
          *((_QWORD *)a3 + 4),
          a4);
        return 2147942487LL;
      }
    }
    else if ( (v36 & v34) != 0 && (v40 || *((int *)a2 + 259) < 1) )
    {
      goto LABEL_77;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18006a598  push    rbp
0x18006a59a  push    rbx
0x18006a59b  push    rsi
0x18006a59c  push    rdi
0x18006a59d  push    r13
0x18006a59f  push    r14
0x18006a5a1  push    r15
0x18006a5a3  lea     rbp, [rsp-7]
0x18006a5a8  sub     rsp, 0D0h
0x18006a5af  mov     rax, cs:__security_cookie
0x18006a5b6  xor     rax, rsp
0x18006a5b9  mov     [rbp+37h+var_40], rax
0x18006a5bd  mov     r15, r9
0x18006a5c0  mov     rsi, r8
0x18006a5c3  mov     r14, rdx
0x18006a5c6  mov     rbx, rcx
0x18006a5c9  mov     rdi, [rbp+37h+arg_20]
0x18006a5cd  mov     r9, [rbp+37h+arg_28]; struct D3D12_CLEAR_VALUE *
0x18006a5d1  mov     rcx, [rbp+37h+arg_38]
0x18006a5d5  mov     [rsp+100h+var_C0], 0; bool
0x18006a5da  lea     rax, [rbp+37h+var_90]
0x18006a5de  mov     [rsp+100h+var_C8], rax; struct CD3DX12_RESOURCE_DESC2 *
0x18006a5e3  mov     rax, [rbp+37h+arg_40]
0x18006a5ea  mov     [rsp+100h+var_D0], rax; unsigned __int64
0x18006a5ef  mov     [rsp+100h+var_D8], rcx; enum DXGI_FORMAT *
0x18006a5f4  mov     eax, [rbp+37h+arg_30]
0x18006a5f7  mov     [rsp+100h+var_E0], eax; unsigned int
0x18006a5fb  mov     r8, rdi; struct CD3DX12_RESOURCE_DESC2 *
0x18006a5fe  mov     rcx, rbx; struct TDebugOutputFunctor *
0x18006a601  call    ?ValidateResourceDescription@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUCD3DX12_RESOURCE_DESC2@@PEBUD3D12_CLEAR_VALUE@@IPEBW4DXGI_FORMAT@@_KPEAU3@_N@Z; ValidateResourceDescription(TDebugOutputFunctor &,DeviceValidationInfo const &,CD3DX12_RESOURCE_DESC2 const &,D3D12_CLEAR_VALUE const *,uint,DXGI_FORMAT const *,unsigned __int64,CD3DX12_RESOURCE_DESC2 *,bool)
0x18006a606  test    eax, eax
0x18006a608  js      loc_18006AA3C
0x18006a60e  mov     r13d, 1
0x18006a614  test    dword ptr [rdi+30h], 100h
0x18006a61b  jz      short loc_18006A687
0x18006a61d  test    byte ptr [rdi+30h], 4
0x18006a621  jnz     short loc_18006A637
0x18006a623  lea     r8, aResourceCreate; "Resource created with D3D12_RESOURCE_FL"...
0x18006a62a  mov     edx, 257h
0x18006a62f  mov     rcx, rbx
0x18006a632  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18006a637  mov     ecx, [rsi+8]
0x18006a63a  sub     ecx, r13d
0x18006a63d  jz      short loc_18006A687
0x18006a63f  cmp     ecx, 3
0x18006a642  jnz     short loc_18006A673
0x18006a644  mov     eax, [rsi+14h]
0x18006a647  test    eax, eax
0x18006a649  cmovz   eax, r13d
0x18006a64d  mov     [rbp+37h+var_B0], 0
0x18006a654  bsf     eax, eax
0x18006a657  lea     rcx, [rax+rax*4]
0x18006a65b  mov     eax, [r14+rcx*4]
0x18006a65f  neg     eax
0x18006a661  sbb     ecx, ecx
0x18006a663  neg     ecx
0x18006a665  add     ecx, r13d
0x18006a668  cmp     [rsi+10h], ecx
0x18006a66b  jnz     short loc_18006A673
0x18006a66d  cmp     [rsi+0Ch], r13d
0x18006a671  jz      short loc_18006A687
0x18006a673  lea     r8, aIfD3d12Resourc; "If D3D12_RESOURCE_FLAG_RAYTRACING_ACCEL"...
0x18006a67a  mov     edx, 27Eh
0x18006a67f  mov     rcx, rbx
0x18006a682  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18006a687  mov     r10d, [rsi+28h]
0x18006a68b  mov     r9d, r10d
0x18006a68e  and     r9d, 20h
0x18006a692  mov     ecx, 0
0x18006a697  jz      loc_18006A761
0x18006a69d  mov     ecx, [rdi+2Ch]
0x18006a6a0  sub     ecx, r13d
0x18006a6a3  jz      short loc_18006A6CD
0x18006a6a5  sub     ecx, 2
0x18006a6a8  jz      short loc_18006A6CD
0x18006a6aa  cmp     ecx, r13d
0x18006a6ad  jz      short loc_18006A6CD
0x18006a6af  lea     r8, aIfD3d12HeapFla_4; "If D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER"...
0x18006a6b6  mov     edx, 27Eh
0x18006a6bb  mov     rcx, rbx
0x18006a6be  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18006a6c3  mov     eax, 80070057h
0x18006a6c8  jmp     loc_18006AA3C
0x18006a6cd  movzx   eax, word ptr [rdi+1Eh]
0x18006a6d1  cmp     ax, r13w
0x18006a6d5  jz      short loc_18006A6F0
0x18006a6d7  mov     r9d, eax
0x18006a6da  lea     r8, aIfD3d12HeapFla_0; "If D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER"...
0x18006a6e1  mov     edx, 2D2h
0x18006a6e6  mov     rcx, rbx
0x18006a6e9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18006a6ee  jmp     short loc_18006A6C3
0x18006a6f0  mov     ecx, r13d
0x18006a6f3  cmp     dword ptr [rdi+2Ch], 4
0x18006a6f7  jz      short loc_18006A761
0x18006a6f9  mov     r8d, [rdi+20h]
0x18006a6fd  or      edx, 0FFFFFFFFh
0x18006a700  mov     eax, edx
0x18006a702  mov     r11d, 0C0h
0x18006a708  cmp     r8d, r11d
0x18006a70b  cmovb   eax, r8d
0x18006a70f  lea     rcx, [rax+rax*4]
0x18006a713  lea     rax, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x18006a71a  test    byte ptr [rax+rcx*8+20h], 10h
0x18006a71f  jnz     short loc_18006A73D
0x18006a721  cmp     r8d, r11d
0x18006a724  cmovb   edx, r8d
0x18006a728  mov     ecx, r13d
0x18006a72b  lea     rdx, [rdx+rdx*4]; bool
0x18006a72f  lea     rax, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x18006a736  test    byte ptr [rax+rdx*8+20h], 8
0x18006a73b  jz      short loc_18006A761
0x18006a73d  mov     ecx, r8d; enum DXGI_FORMAT
0x18006a740  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x18006a745  mov     r9, rax
0x18006a748  lea     r8, aD3d12ResourceD_76; "D3D12_RESOURCE_DESC::Format is invalid."...
0x18006a74f  mov     edx, 2E2h
0x18006a754  mov     rcx, rbx
0x18006a757  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18006a75c  jmp     loc_18006A6C3
0x18006a761  mov     r8d, [rdi+30h]
0x18006a765  mov     eax, r8d
0x18006a768  shr     eax, 4
0x18006a76b  and     eax, r13d
0x18006a76e  cmp     ecx, eax
0x18006a770  jz      short loc_18006A786
0x18006a772  mov     r9d, r8d
0x18006a775  lea     r8, aD3d12ResourceD_74; "D3D12_RESOURCE_DESC::Flags is invalid. "...
0x18006a77c  mov     edx, 257h
0x18006a781  jmp     loc_18006A6E6
0x18006a786  lea     rdx, [rdi+2Ch]
0x18006a78a  cmp     dword ptr [rdx], 3
0x18006a78d  jnz     short loc_18006A7C6
0x18006a78f  cmp     byte ptr [r14+2B6h], 0
0x18006a797  jnz     short loc_18006A7C6
0x18006a799  test    r9d, r9d
0x18006a79c  jnz     short loc_18006A7AF
0x18006a79e  lea     r8, aD3d12ResourceD_7; "D3D12_RESOURCE_DESC::Layout is invalid "...
0x18006a7a5  mov     edx, 2D4h
0x18006a7aa  jmp     loc_18006A6BB
0x18006a7af  test    r8b, 7
0x18006a7b3  jz      short loc_18006A7C6
0x18006a7b5  lea     r8, aD3d12ResourceD_27; "D3D12_RESOURCE_DESC::Layout is invalid "...
0x18006a7bc  mov     edx, 257h
0x18006a7c1  jmp     loc_18006A6BB
0x18006a7c6  mov     ecx, [rdi]
0x18006a7c8  sub     ecx, r13d
0x18006a7cb  jz      loc_18006A88D
0x18006a7d1  sub     ecx, r13d
0x18006a7d4  jz      short loc_18006A7E4
0x18006a7d6  sub     ecx, r13d
0x18006a7d9  jz      short loc_18006A7E4
0x18006a7db  cmp     ecx, r13d
0x18006a7de  jnz     loc_18006A8BC
0x18006a7e4  mov     eax, [rsi+8]
0x18006a7e7  sub     eax, 2
0x18006a7ea  cmp     eax, r13d
0x18006a7ed  jbe     loc_18006A881
0x18006a7f3  test    r8b, 3
0x18006a7f7  jz      short loc_18006A80B
0x18006a7f9  test    r10b, 40h
0x18006a7fd  jz      short loc_18006A81C
0x18006a7ff  lea     r8, aATextureResour; "A texture resource with either D3D12_RE"...
0x18006a806  jmp     loc_18006A6B6
0x18006a80b  test    r10b, r10b
0x18006a80e  jns     short loc_18006A81C
0x18006a810  lea     r8, aATextureResour_0; "A texture resource without either D3D12"...
0x18006a817  jmp     loc_18006A6B6
0x18006a81c  cmp     [rdx], r13d
0x18006a81f  jnz     loc_18006A8BC
0x18006a825  cmp     dword ptr [rdi], 3
0x18006a828  jnz     short loc_18006A833
0x18006a82a  test    r9d, r9d
0x18006a82d  jnz     loc_18006A8BC
0x18006a833  mov     rcx, rdx; enum D3D12_TEXTURE_LAYOUT *
0x18006a836  call    ?D3D12ToStr@@YAPEBDAEBW4D3D12_TEXTURE_LAYOUT@@@Z; D3D12ToStr(D3D12_TEXTURE_LAYOUT const &)
0x18006a83b  mov     r8, rax
0x18006a83e  mov     rcx, rdi; enum D3D12_RESOURCE_DIMENSION *
0x18006a841  call    ?D3D12ToStr@@YAPEBDAEBW4D3D12_RESOURCE_DIMENSION@@@Z; D3D12ToStr(D3D12_RESOURCE_DIMENSION const &)
0x18006a846  lea     rdx, aNot; "not "
0x18006a84d  lea     rcx, Src
0x18006a854  test    r9d, r9d
0x18006a857  cmovz   rcx, rdx
0x18006a85b  mov     [rsp+100h+var_D8], rcx
0x18006a860  mov     qword ptr [rsp+100h+var_E0], r8
0x18006a865  mov     r9, rax
0x18006a868  lea     r8, aD3d12ResourceD_59; "D3D12_RESOURCE_DESC::Layout can be D3D1"...
0x18006a86f  mov     edx, 2D4h
0x18006a874  mov     rcx, rbx
0x18006a877  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18006a87c  jmp     loc_18006A6C3
0x18006a881  lea     r8, aATextureResour_1; "A texture resource cannot be created on"...
0x18006a888  jmp     loc_18006A6B6
0x18006a88d  mov     eax, [rsi+8]
0x18006a890  sub     eax, 2
0x18006a893  cmp     eax, r13d
0x18006a896  ja      short loc_18006A8AA
0x18006a898  test    [rbp+37h+var_60], 5
0x18006a89c  jz      short loc_18006A8AA
0x18006a89e  lea     r8, aABufferCannotB; "A buffer cannot be created on a D3D12_H"...
0x18006a8a5  jmp     loc_18006A6B6
0x18006a8aa  test    r10b, 4
0x18006a8ae  jz      short loc_18006A8BC
0x18006a8b0  lea     r8, aABufferResourc; "A buffer resource cannot be created on "...
0x18006a8b7  jmp     loc_18006A6B6
0x18006a8bc  test    r10b, 8
0x18006a8c0  jz      loc_18006A9E5
0x18006a8c6  xor     ecx, ecx
0x18006a8c8  test    r9d, r9d
0x18006a8cb  setnz   cl
0x18006a8ce  cmp     dword ptr [rdi], 3
0x18006a8d1  jnz     loc_18006A9D4
0x18006a8d7  cmp     qword ptr [rdi+8], 0
0x18006a8dc  jnz     loc_18006A9D4
0x18006a8e2  movzx   eax, word ptr [rdi+1Ch]
0x18006a8e6  sub     ax, r13w
0x18006a8ea  cmp     ax, r13w
0x18006a8ee  ja      loc_18006A9D4
0x18006a8f4  cmp     [rdi+1Eh], r13w
0x18006a8f9  jnz     loc_18006A9D4
0x18006a8ff  cmp     [rdi+24h], r13d
0x18006a903  jnz     loc_18006A9D4
0x18006a909  cmp     dword ptr [rdi+28h], 0
0x18006a90d  jnz     loc_18006A9D4
0x18006a913  cmp     [rdx], ecx
0x18006a915  jnz     loc_18006A9D4
0x18006a91b  test    r8b, 0C2h
0x18006a91f  jnz     loc_18006A9D4
0x18006a925  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12Displayable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable> `wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl(void)'::`2'::impl
0x18006a92c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(void)
0x18006a931  mov     r9d, [rdi+20h]
0x18006a935  test    al, al
0x18006a937  jz      short loc_18006A9B0
0x18006a939  mov     [rbp+37h+var_A8], r9d
0x18006a93d  mov     [rbp+37h+var_A4], 0
0x18006a945  mov     rcx, [r14+298h]
0x18006a94c  mov     rax, [rcx]
0x18006a94f  mov     r9d, 0Ch
0x18006a955  lea     r8, [rbp+37h+var_A8]
0x18006a959  lea     edx, [r9-9]
0x18006a95d  mov     rax, [rax+68h]
0x18006a961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a966  test    dword ptr [rbp+37h+var_A4], 80000h
0x18006a96d  jnz     short loc_18006A9E5
0x18006a96f  test    dword ptr [rbp+37h+var_A4+4], 10000h
0x18006a976  jnz     short loc_18006A9E5
0x18006a978  mov     ecx, [r14+290h]; enum D3D_FEATURE_LEVEL
0x18006a97f  call    ?FeatureLevelToString@@YAPEBDW4D3D_FEATURE_LEVEL@@@Z; FeatureLevelToString(D3D_FEATURE_LEVEL)
0x18006a984  mov     ecx, [rdi+20h]; enum DXGI_FORMAT
0x18006a987  mov     r8, rax
0x18006a98a  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x18006a98f  mov     r9, rax
0x18006a992  mov     qword ptr [rsp+100h+var_E0], r8
0x18006a997  lea     r8, aD3d12ResourceD_37; "D3D12_RESOURCE_DESC::Format is not supp"...
0x18006a99e  mov     edx, 280h
0x18006a9a3  mov     rcx, rbx
0x18006a9a6  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18006a9ab  jmp     loc_18006A6C3
0x18006a9b0  mov     edx, [r14+294h]
0x18006a9b7  mov     ecx, r9d
0x18006a9ba  call    ?IsCrossD3DAPIShareableFormat@CD3D11FormatHelper@@SA_NW4DXGI_FORMAT@@W4eExtendedFormatFeatures@1@@Z; CD3D11FormatHelper::IsCrossD3DAPIShareableFormat(DXGI_FORMAT,CD3D11FormatHelper::eExtendedFormatFeatures)
0x18006a9bf  test    al, al
0x18006a9c1  jnz     short loc_18006A9E5
0x18006a9c3  mov     ecx, [r14+290h]; enum D3D_FEATURE_LEVEL
0x18006a9ca  call    ?FeatureLevelToString@@YAPEBDW4D3D_FEATURE_LEVEL@@@Z; FeatureLevelToString(D3D_FEATURE_LEVEL)
0x18006a9cf  mov     ecx, r9d
0x18006a9d2  jmp     short loc_18006A987
0x18006a9d4  lea     r8, aWhenD3d12HeapF_2; "When D3D12_HEAP_FLAGS has D3D12_HEAP_FL"...
0x18006a9db  mov     edx, 280h
0x18006a9e0  jmp     loc_18006A6BB
0x18006a9e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment> `wil::Feature<__WilFeatureTraits_Feature_D3D12TightAlignment>::GetImpl(void)'::`2'::impl
0x18006a9ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment>::__private_IsEnabled(void)
0x18006a9f1  mov     rdx, [rsi+20h]
0x18006a9f5  mov     rcx, rdx
0x18006a9f8  or      rcx, r15
0x18006a9fb  mov     r9, [rbp+37h+var_88]
0x18006a9ff  test    al, al
0x18006aa01  lea     rax, [r9-1]
0x18006aa05  jz      short loc_18006AA35
0x18006aa07  test    rcx, rax
0x18006aa0a  jz      short loc_18006AA3A
0x18006aa0c  test    r9, r9
0x18006aa0f  jnz     short loc_18006AA1A
0x18006aa11  cmp     [r14+40Ch], r13d
0x18006aa18  jge     short loc_18006AA3A
0x18006aa1a  mov     [rsp+100h+var_D8], r15
0x18006aa1f  mov     qword ptr [rsp+100h+var_E0], rdx
0x18006aa24  lea     r8, aThisResourceCa; "This resource cannot be created on this"...
0x18006aa2b  mov     edx, 27Eh
0x18006aa30  jmp     loc_18006A874
0x18006aa35  test    rcx, rax
0x18006aa38  jnz     short loc_18006AA1A
0x18006aa3a  xor     eax, eax
0x18006aa3c  mov     rcx, [rbp+37h+var_40]
0x18006aa40  xor     rcx, rsp; StackCookie
0x18006aa43  call    __security_check_cookie
0x18006aa48  add     rsp, 0D0h
0x18006aa4f  pop     r15
0x18006aa51  pop     r14
0x18006aa53  pop     r13
  ... truncated ...
```
