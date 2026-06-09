# ValidateHeapPropertiesAndFlags(TDebugOutputFunctor &,DeviceValidationInfo const &,D3D12_HEAP_PROPERTIES const *,D3D12_HEAP_FLAGS,HeapValidationIDs const &,bool,uint)

- ea: `0x180079d58`
- end: `0x18007a45b`
- name: `?ValidateHeapPropertiesAndFlags@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEBUD3D12_HEAP_PROPERTIES@@W4D3D12_HEAP_FLAGS@@AEBUHeapValidationIDs@@_NI@Z`
- size: `1795`
- prototype: `__int64 __fastcall(struct TDebugOutputFunctor *, const struct DeviceValidationInfo *, const struct D3D12_HEAP_PROPERTIES *, enum D3D12_HEAP_FLAGS, const struct HeapValidationIDs *, bool, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18002b520`
- `0x1800a8938`
- `0x1800e674c`

## callees

- `0x18002ef50`
- `0x180079d58`
- `0x18007de6c`
- `0x1800f1424`
- `0x1800f1474`

## string_xrefs

- `0x180079fae`: `D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_TOOLS_USE_MANUAL_WRITE_TRACKING when manual write tracking is not supported. Use CheckFeatureSupport(D3D12_FEATURE_D3D12_OPTIONS17) to check if ManualWriteTrackingResourceSupported returns true.`
- `0x180079ecd`: `D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_ALLOW_WRITE_WATCH for this D3D_FEATURE_LEVEL_1_0_CORE/GENERIC device. Use CheckFeatureSupport(D3D12_FEATURE_D3D12_OPTIONS20) to check if ComputeOnlyWriteWatchSupported returns true.`
- `0x18007a0ae`: `D3D12_HEAP_FLAGS has invalid flag combinations set. D3D12_HEAP_FLAG_SHARED may not be set when creating CPU accessible heaps, which is defined by D3D12_HEAP_PROPERTIES. But, some shared CPU accessible heaps can be accomplished through OpenExistingHeap. See MSDN for more details.`
- `0x18007a037`: `D3D12_HEAP_PROPERTIES is invalid. Using D3D12_CPU_PAGE_PROPERTY_WRITE_COMBINE with D3D12_MEMORY_POOL_L1 is not supported by D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices.`
- `0x180079fec`: `D3D12_HEAP_PROPERTIES is invalid. D3D12_CPU_PAGE_PROPERTY_WRITE_BACK cannot be used with D3D12_MEMORY_POOL_L1.`
- `0x18007a02e`: `D3D12_HEAP_PROPERTIES is invalid. D3D12_CPU_PAGE_PROPERTY_WRITE_COMBINE can only be used with D3D12_MEMORY_POOL_L1 if GPU upload heaps are supported. Use CheckFeatureSupport(D3D12_FEATURE_D3D12_OPTIONS16) to check if GPUUploadHeapSupported returns true. Note that GPU upload heap requires OS build version to be greater than 26080 or later, but this restriction can be bypassed by D3D12EnableExperimentalFeatures with Guid D3D12GPUUploadHeapsOnUnsupportedOS.`
- `0x18007a145`: `When creating a committed resource, D3D12_HEAP_FLAGS must not include D3D12_HEAP_FLAG_DENY_NON_RT_DS_TEXTURES, D3D12_HEAP_FLAG_DENY_RT_DS_TEXTURES, or D3D12_HEAP_FLAG_DENY_BUFFERS. These flags will be set automatically to correspond with the committed resource type.`
- `0x18007a115`: `D3D12_HEAP_FLAGS has invalid flag combinations set. D3D12_HEAP_FLAG_ALLOW_WRITE_WATCH may not be set with CPU inaccessible heaps, which is defined by D3D12_HEAP_PROPERTIES.`
- `0x18007a18b`: `D3D12_HEAP_FLAGS has invalid flag combinations set. When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set, all the following must not be set: D3D12_HEAP_FLAG_DENY_NON_RT_DS_TEXTURES = %u, D3D12_HEAP_FLAG_DENY_RT_DS_TEXTURES = %u, and D3D12_HEAP_FLAG_DENY_BUFFERS = %u.`
- `0x18007a2a4`: `If D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set then the heap type may not be D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_READBACK or D3D12_HEAP_TYPE_GPU_UPLOAD.`
- `0x18007a343`: `If D3D12_HEAP_FLAG_ALLOW_DISPLAY is set then the heap type may not be D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_READBACK or D3D12_HEAP_TYPE_GPU_UPLOAD.`
- `0x18007a219`: `D3D12_HEAP_FLAGS has invalid flag combinations set. The following flags may not all be set simultaneously. Exactly one must be left unset, or all may be left unset when the adapter supports D3D12_RESOURCE_HEAP_TIER_2 or creating a heap in conjunction with D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER: D3D12_FEATURE_DATA_D3D12_OPTIONS::ResourceHeapTier = %s, D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER = %u, D3D12_HEAP_FLAG_DENY_NON_RT_DS_TEXTURES = %u, D3D12_HEAP_FLAG_DENY_RT_DS_TEXTURES = %u, and D3D12_HEAP_FLA`
- `0x18007a38b`: `D3D12_HEAP_FLAGS may only have D3D12_HEAP_FLAG_ALLOW_DISPLAY set when used with CreateCommittedResource.`
- `0x18007a44c`: `D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMICS fails when the heap type allows CPU access; but isn't D3D12_HEAP_TYPE_CUSTOM. These properties suggest the application may be trying to use shader atomic instructions with CPU interlocked operations%s. Not all hardware supports atomics with CPU interlocked operations%s.`

## pseudocode

```c
__int64 __fastcall ValidateHeapPropertiesAndFlags(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        const struct D3D12_HEAP_PROPERTIES *a3,
        enum D3D12_HEAP_FLAGS a4,
        const struct HeapValidationIDs *a5,
        bool a6,
        unsigned int a7)
{
  const struct DeviceValidationInfo *v9; // r13
  D3D12_HEAP_TYPE Type; // r9d
  unsigned int v13; // ebp
  D3D12_MEMORY_POOL *p_MemoryPoolPreference; // r14
  int v15; // eax
  char v16; // r14
  const char *v17; // r8
  D3D12_HEAP_TYPE v18; // ecx
  D3D12_CPU_PAGE_PROPERTY CPUPageProperty; // ecx
  __int32 v20; // ecx
  int v21; // eax
  const char *v22; // r8
  __int64 v23; // rdx
  unsigned __int32 v24; // edx
  int v25; // r8d
  int v26; // r10d
  int v27; // edx
  const char *v28; // r9
  unsigned int CreationNodeMask; // r14d
  unsigned int VisibleNodeMask; // r13d
  D3D12_MEMORY_POOL *v31; // rax
  const char *v32; // rax
  __int64 v33; // r8
  const char *v34; // r8
  D3D12_MEMORY_POOL *v35; // rax
  __int64 v36; // r8
  int v37; // r14d
  const char *v38; // rax
  const char *v39; // r9
  __int64 v40; // [rsp+20h] [rbp-68h]
  char v42; // [rsp+A0h] [rbp+18h]

  v9 = a2;
  if ( !a3 )
  {
    TDebugOutputFunctor::operator()(a1, 634, "pHeapProperties is NULL!");
    return 2147942487LL;
  }
  Type = a3->Type;
  if ( a3->Type <= 0 || (v13 = 0, Type >= (D3D12_HEAP_TYPE_CUSTOM|D3D12_HEAP_TYPE_UPLOAD)) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *(unsigned int *)a5,
      "D3D12_HEAP_PROPERTIES::Type is unrecognized. The value is %d.",
      Type);
    v13 = -2147024809;
  }
  if ( a3->Type == D3D12_HEAP_TYPE_GPU_UPLOAD && !*((_DWORD *)v9 + 235) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 6),
      "D3D12_HEAP_TYPE_GPU_UPLOAD is invalid when GPU upload heaps are not supported. Use CheckFeatureSupport(D3D12_FEATU"
      "RE_D3D12_OPTIONS16) to check if GPUUploadHeapSupported returns true. Note that GPU upload heaps require OS build v"
      "ersion to be greater than 26080 or later, but this restriction can be bypassed by D3D12EnableExperimentalFeatures "
      "with Guid D3D12GPUUploadHeapsOnUnsupportedOS.");
    v13 = -2147024809;
  }
  if ( a3->CPUPageProperty > (unsigned int)D3D12_CPU_PAGE_PROPERTY_WRITE_BACK )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 1),
      "D3D12_HEAP_PROPERTIES::CPUPageProperty is unrecognized. The value is %d.",
      a3->CPUPageProperty);
    v13 = -2147024809;
  }
  p_MemoryPoolPreference = &a3->MemoryPoolPreference;
  if ( a3->MemoryPoolPreference > (unsigned int)D3D12_MEMORY_POOL_L1 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 2),
      "D3D12_HEAP_PROPERTIES::MemoryPoolPreference is unrecognized. The value is %d.",
      *p_MemoryPoolPreference);
    v13 = -2147024809;
  }
  if ( (a4 & 0xFFFF8012) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 3),
      "D3D12_HEAP_FLAGS has recognized flags set. The value is 0x%x, and the following flags are unrecognized: 0x%x.",
      a4,
      a4 & 0xFFFF8012);
    return 2147942487LL;
  }
  if ( (v13 & 0x80000000) != 0 )
    return v13;
  v15 = *((_DWORD *)v9 + 164);
  if ( v15 == 4096 || v15 == 256 )
  {
    v16 = 0;
    if ( (a4 & 4) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a5 + 4),
        "D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_DENY_BUFFERS for D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices.");
      v16 = 1;
    }
    if ( (a4 & 0x100) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a5 + 4),
        "D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_HARDWARE_PROTECTED for D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices.");
      v16 = 1;
    }
    if ( (a4 & 0x200) != 0 && !*((_DWORD *)v9 + 249) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a5 + 4),
        "D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_ALLOW_WRITE_WATCH for this D3D_FEATURE_LEVEL_1_0_CORE/GENERIC dev"
        "ice. Use CheckFeatureSupport(D3D12_FEATURE_D3D12_OPTIONS20) to check if ComputeOnlyWriteWatchSupported returns true.");
      v16 = 1;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
    {
      if ( (a4 & 8) == 0 || (a4 & 0x20) != 0 )
        goto LABEL_33;
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a5 + 4),
        "D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_ALLOW_DISPLAY for D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices,exce"
        "pt when D3D12_HEAP_FLAGS also specify D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER.");
    }
    else
    {
      if ( (a4 & 8) == 0 )
      {
LABEL_33:
        if ( (a4 & 0x400) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a1,
            *((unsigned int *)a5 + 4),
            "D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMICS for D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices.");
          v16 = 1;
        }
        v9 = a2;
        if ( !*((_DWORD *)a2 + 248) && a3->Type == D3D12_HEAP_TYPE_CUSTOM )
        {
          TDebugOutputFunctor::operator()(
            a1,
            *((unsigned int *)a5 + 4),
            "D3D12_HEAP_TYPE_CUSTOM is not supported by D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices.");
          v16 = 1;
        }
        if ( a3->Type == D3D12_HEAP_TYPE_GPU_UPLOAD )
        {
          v17 = "D3D12_HEAP_TYPE_GPU_UPLOAD is not supported by D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices.";
LABEL_40:
          TDebugOutputFunctor::operator()(a1, *((unsigned int *)a5 + 4), v17);
          return 2147942487LL;
        }
        if ( v16 )
          return 2147942487LL;
        p_MemoryPoolPreference = &a3->MemoryPoolPreference;
        goto LABEL_44;
      }
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a5 + 4),
        "D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_ALLOW_DISPLAY for D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices.");
    }
    v16 = 1;
    goto LABEL_33;
  }
LABEL_44:
  if ( (a4 & 0x2000) != 0 && !*((_DWORD *)v9 + 237) )
  {
    v17 = "D3D12_HEAP_FLAGS can't specify D3D12_HEAP_FLAG_TOOLS_USE_MANUAL_WRITE_TRACKING when manual write tracking is n"
          "ot supported. Use CheckFeatureSupport(D3D12_FEATURE_D3D12_OPTIONS17) to check if ManualWriteTrackingResourceSu"
          "pported returns true.";
    goto LABEL_40;
  }
  v18 = a3->Type;
  if ( a3->Type == D3D12_HEAP_TYPE_CUSTOM )
  {
    v42 = 0;
    CPUPageProperty = a3->CPUPageProperty;
    if ( CPUPageProperty )
    {
      v20 = CPUPageProperty - 2;
      if ( v20 )
      {
        if ( v20 == 1 )
        {
          v42 = 1;
          if ( *p_MemoryPoolPreference == D3D12_MEMORY_POOL_L1 )
          {
            TDebugOutputFunctor::operator()(
              a1,
              *((unsigned int *)a5 + 4),
              "D3D12_HEAP_PROPERTIES is invalid. D3D12_CPU_PAGE_PROPERTY_WRITE_BACK cannot be used with D3D12_MEMORY_POOL_L1.");
LABEL_61:
            v13 = -2147024809;
          }
        }
      }
      else
      {
        v42 = 1;
        if ( a3->MemoryPoolPreference == D3D12_MEMORY_POOL_L1 && (*((_BYTE *)v9 + 688) & 2) == 0 )
        {
          v21 = *((_DWORD *)v9 + 164);
          if ( v21 == 4096 || v21 == 256 )
          {
            TDebugOutputFunctor::operator()(
              a1,
              *((unsigned int *)a5 + 4),
              "D3D12_HEAP_PROPERTIES is invalid. Using D3D12_CPU_PAGE_PROPERTY_WRITE_COMBINE with D3D12_MEMORY_POOL_L1 is"
              " not supported by D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices.");
          }
          else
          {
            if ( *((_DWORD *)v9 + 235) )
              goto LABEL_62;
            TDebugOutputFunctor::operator()(
              a1,
              *((unsigned int *)a5 + 4),
              "D3D12_HEAP_PROPERTIES is invalid. D3D12_CPU_PAGE_PROPERTY_WRITE_COMBINE can only be used with D3D12_MEMORY"
              "_POOL_L1 if GPU upload heaps are supported. Use CheckFeatureSupport(D3D12_FEATURE_D3D12_OPTIONS16) to chec"
              "k if GPUUploadHeapSupported returns true. Note that GPU upload heap requires OS build version to be greate"
              "r than 26080 or later, but this restriction can be bypassed by D3D12EnableExperimentalFeatures with Guid D"
              "3D12GPUUploadHeapsOnUnsupportedOS.");
          }
          goto LABEL_61;
        }
      }
LABEL_62:
      if ( *p_MemoryPoolPreference )
      {
        if ( *p_MemoryPoolPreference != D3D12_MEMORY_POOL_L0 && *((_DWORD *)v9 + 5 * a7) )
        {
          v22 = "D3D12_HEAP_PROPERTIES is invalid. Only D3D12_MEMORY_POOL_L0 can be used on UMA architectures. Use CheckF"
                "eatureSupport with D3D12_FEATURE_ARCHITECTURE1 to understand architectural capabilities.";
LABEL_66:
          v23 = *((unsigned int *)a5 + 4);
LABEL_133:
          TDebugOutputFunctor::operator()(a1, v23, v22);
          return (unsigned int)-2147024809;
        }
      }
      else
      {
        TDebugOutputFunctor::operator()(
          a1,
          *((unsigned int *)a5 + 4),
          "D3D12_HEAP_PROPERTIES is invalid. D3D12_MEMORY_POOL_UNKNOWN cannot be used with D3D12_HEAP_TYPE_CUSTOM.");
        v13 = -2147024809;
      }
      goto LABEL_68;
    }
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 4),
      "D3D12_HEAP_PROPERTIES is invalid. D3D12_CPU_PAGE_PROPERTY_UNKNOWN cannot be used with D3D12_HEAP_TYPE_CUSTOM.");
    goto LABEL_61;
  }
  if ( ((v18 - 2) & 0xFFFFFFFC) != 0 || (v42 = 1, v18 == D3D12_HEAP_TYPE_CUSTOM) )
    v42 = 0;
  if ( a3->CPUPageProperty )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 4),
      "D3D12_HEAP_PROPERTIES is invalid. D3D12_CPU_PAGE_PROPERTY_UNKNOWN must be used when creating heaps that are not D3"
      "D12_HEAP_TYPE_CUSTOM.");
    v13 = -2147024809;
  }
  if ( *p_MemoryPoolPreference )
  {
    v22 = "D3D12_HEAP_PROPERTIES is invalid. D3D12_MEMORY_POOL_UNKNOWN must be used when creating heaps that are not D3D1"
          "2_HEAP_TYPE_CUSTOM.";
    goto LABEL_66;
  }
LABEL_68:
  if ( (v13 & 0x80000000) != 0 )
    return v13;
  if ( v42 )
  {
    if ( (a4 & 1) == 0 )
      goto LABEL_83;
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 5),
      "D3D12_HEAP_FLAGS has invalid flag combinations set. D3D12_HEAP_FLAG_SHARED may not be set when creating CPU access"
      "ible heaps, which is defined by D3D12_HEAP_PROPERTIES. But, some shared CPU accessible heaps can be accomplished t"
      "hrough OpenExistingHeap. See MSDN for more details.");
    goto LABEL_82;
  }
  if ( (a4 & 0x200) != 0 && (*((_BYTE *)v9 + 688) & 1) == 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 5),
      "D3D12_HEAP_FLAGS has invalid flag combinations set. D3D12_HEAP_FLAG_ALLOW_WRITE_WATCH may not be set with CPU inac"
      "cessible heaps, which is defined by D3D12_HEAP_PROPERTIES.");
LABEL_82:
    v13 = -2147024809;
  }
LABEL_83:
  v24 = a4 & 0xC4;
  if ( a6 )
  {
    if ( (a4 & 0xC4) == 0 )
      goto LABEL_101;
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 5),
      "When creating a committed resource, D3D12_HEAP_FLAGS must not include D3D12_HEAP_FLAG_DENY_NON_RT_DS_TEXTURES, D3D"
      "12_HEAP_FLAG_DENY_RT_DS_TEXTURES, or D3D12_HEAP_FLAG_DENY_BUFFERS. These flags will be set automatically to corres"
      "pond with the committed resource type.");
    goto LABEL_100;
  }
  if ( (a4 & 0x20) != 0 )
  {
    if ( (a4 & 0xC4) == 0 )
      goto LABEL_101;
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 5),
      "D3D12_HEAP_FLAGS has invalid flag combinations set. When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set, all the foll"
      "owing must not be set: D3D12_HEAP_FLAG_DENY_NON_RT_DS_TEXTURES = %u, D3D12_HEAP_FLAG_DENY_RT_DS_TEXTURES = %u, and"
      " D3D12_HEAP_FLAG_DENY_BUFFERS = %u.",
      (v24 >> 7) & 1,
      (v24 >> 6) & 1,
      (v24 >> 2) & 1);
    goto LABEL_100;
  }
  if ( (a4 & 0xC4) == 0 )
  {
    if ( *((int *)v9 + 161) >= 2 )
      goto LABEL_101;
    goto LABEL_94;
  }
  if ( ((v24 - 1) & v24) == 0 || v24 == 196 )
  {
LABEL_94:
    v25 = (v24 >> 2) & 1;
    v26 = (v24 >> 6) & 1;
    v27 = (v24 >> 7) & 1;
    if ( *((_DWORD *)v9 + 161) == 1 )
    {
      v28 = "D3D12_RESOURCE_HEAP_TIER_1";
    }
    else if ( *((_DWORD *)v9 + 161) == 2 )
    {
      v28 = "D3D12_RESOURCE_HEAP_TIER_2";
    }
    else
    {
      v28 = "Unrecognized";
    }
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 5),
      "D3D12_HEAP_FLAGS has invalid flag combinations set. The following flags may not all be set simultaneously. Exactly"
      " one must be left unset, or all may be left unset when the adapter supports D3D12_RESOURCE_HEAP_TIER_2 or creating"
      " a heap in conjunction with D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER: D3D12_FEATURE_DATA_D3D12_OPTIONS::ResourceHeapTi"
      "er = %s, D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER = %u, D3D12_HEAP_FLAG_DENY_NON_RT_DS_TEXTURES = %u, D3D12_HEAP_FLAG_"
      "DENY_RT_DS_TEXTURES = %u, and D3D12_HEAP_FLAG_DENY_BUFFERS = %u.",
      v28,
      0,
      v27,
      v26,
      v25);
LABEL_100:
    v13 = -2147024809;
  }
LABEL_101:
  CreationNodeMask = 1;
  if ( a3->CreationNodeMask )
    CreationNodeMask = a3->CreationNodeMask;
  VisibleNodeMask = 1;
  if ( a3->VisibleNodeMask )
    VisibleNodeMask = a3->VisibleNodeMask;
  if ( CreationNodeMask != (CreationNodeMask & VisibleNodeMask) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a5 + 4),
      "D3D12_HEAP_PROPERTIES is invalid. VisibleNodeMask must contain CreationNodeMask");
    v13 = -2147024809;
  }
  if ( (a4 & 0x20) != 0 )
  {
    if ( (a4 & 1) == 0 )
    {
      v17 = "If D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set then D3D12_HEAP_FLAG_SHARED must be set also.";
      goto LABEL_40;
    }
    if ( a3->Type == D3D12_HEAP_TYPE_UPLOAD || a3->Type == D3D12_HEAP_TYPE_READBACK )
    {
LABEL_114:
      v17 = "If D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set then the heap type may not be D3D12_HEAP_TYPE_UPLOAD, D3D12_H"
            "EAP_TYPE_READBACK or D3D12_HEAP_TYPE_GPU_UPLOAD.";
      goto LABEL_40;
    }
    if ( a3->Type != D3D12_HEAP_TYPE_CUSTOM )
    {
      if ( a3->Type == D3D12_HEAP_TYPE_GPU_UPLOAD )
        goto LABEL_114;
LABEL_117:
      if ( (a4 & 8) == 0 )
        return v13;
      goto LABEL_131;
    }
    if ( a3->CPUPageProperty == D3D12_CPU_PAGE_PROPERTY_NOT_AVAILABLE )
    {
      v31 = &a3->MemoryPoolPreference;
      if ( a3->MemoryPoolPreference == D3D12_MEMORY_POOL_L0 )
        goto LABEL_117;
    }
    else
    {
      v31 = &a3->MemoryPoolPreference;
    }
    D3D12ToStr(v31);
    v32 = D3D12ToStr(&a3->CPUPageProperty);
    v40 = v33;
    v34 = "If D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set and the heap type is D3D12_HEAP_TYPE_CUSTOM, then CPUPageProper"
          "ty must be D3D12_CPU_PAGE_PROPERTY_NOT_AVAILABLE and MemoryPoolPreference must be D3D12_MEMORY_POOL_L0.  CPUPa"
          "geProperty is set to %s.  MemoryPoolPreference is set to %s.";
LABEL_121:
    TDebugOutputFunctor::operator()(a1, *((unsigned int *)a5 + 4), v34, v32, v40);
    return 2147942487LL;
  }
  if ( (a4 & 8) == 0 )
  {
    if ( (a4 & 0x400) != 0 )
    {
      if ( a3->Type == D3D12_HEAP_TYPE_DEFAULT )
      {
        if ( (~CreationNodeMask & VisibleNodeMask) != 0 && !*((_BYTE *)a2 + 696) )
        {
          TDebugOutputFunctor::operator()(
            a1,
            *((unsigned int *)a5 + 5),
            "D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMICS fails when D3D12_FEATURE_DATA_CROSS_NODE::AtomicShaderInstructions is F"
            "ALSE, the heap type is D3D12_HEAP_TYPE_DEFAULT, and VisibleNodeMask contains bits not in the CreationNodeMas"
            "k. These properties suggest the application is trying to use shader atomic instructions to memory on an LDA "
            "peer. That only works when the hardware supports AtomicShaderInstructions.");
          return 2147942487LL;
        }
      }
      else if ( a3->Type == D3D12_HEAP_TYPE_CUSTOM )
      {
        return v13;
      }
      if ( v42 )
      {
        v37 = ~CreationNodeMask;
        v38 = " nor with shader atomics running on an LDA peer. See D3D12_FEATURE_DATA_CROSS_NODE::AtomicShaderInstructions";
        if ( (v37 & VisibleNodeMask) == 0 )
          v38 = Src;
        v39 = " or to memory on another LDA peer";
        if ( (v37 & VisibleNodeMask) == 0 )
          v39 = Src;
        TDebugOutputFunctor::operator()(
          a1,
          *((unsigned int *)a5 + 5),
          "D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMICS fails when the heap type allows CPU access; but isn't D3D12_HEAP_TYPE_CUS"
          "TOM. These properties suggest the application may be trying to use shader atomic instructions with CPU interlo"
          "cked operations%s. Not all hardware supports atomics with CPU interlocked operations%s.",
          v39,
          v38);
        return 2147942487LL;
      }
    }
    return v13;
  }
  switch ( a3->Type )
  {
    case D3D12_HEAP_TYPE_UPLOAD:
    case D3D12_HEAP_TYPE_READBACK:
LABEL_128:
      v17 = "If D3D12_HEAP_FLAG_ALLOW_DISPLAY is set then the heap type may not be D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYP"
            "E_READBACK or D3D12_HEAP_TYPE_GPU_UPLOAD.";
      goto LABEL_40;
    case D3D12_HEAP_TYPE_CUSTOM:
      if ( a3->CPUPageProperty == D3D12_CPU_PAGE_PROPERTY_NOT_AVAILABLE )
      {
        v35 = &a3->MemoryPoolPreference;
        if ( a3->MemoryPoolPreference == 2 - (*((_DWORD *)a2 + 5 * a7) != 0) )
          break;
      }
      else
      {
        v35 = &a3->MemoryPoolPreference;
      }
      D3D12ToStr(v35);
      v32 = D3D12ToStr(&a3->CPUPageProperty);
      v40 = v36;
      v34 = "If D3D12_HEAP_FLAG_ALLOW_DISPLAY is set, and D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is not set, and the heap t"
            "ype is D3D12_HEAP_TYPE_CUSTOM, then CPUPageProperty must be D3D12_CPU_PAGE_PROPERTY_NOT_AVAILABLE and Memory"
            "PoolPreference must be D3D12_MEMORY_POOL_L0 on UMA, or L1 otherwise.  CPUPageProperty is set to %s.  MemoryP"
            "oolPreference is set to %s.";
      goto LABEL_121;
    case D3D12_HEAP_TYPE_GPU_UPLOAD:
      goto LABEL_128;
  }
LABEL_131:
  if ( !a6 )
  {
    v22 = "D3D12_HEAP_FLAGS may only have D3D12_HEAP_FLAG_ALLOW_DISPLAY set when used with CreateCommittedResource.";
    v23 = *((unsigned int *)a5 + 5);
    goto LABEL_133;
  }
  return v13;
}

```

## disassembly

```asm
0x180079d58  mov     [rsp+arg_0], rbx
0x180079d5d  mov     [rsp+arg_8], rdx
0x180079d62  push    rbp
0x180079d63  push    rsi
0x180079d64  push    rdi
0x180079d65  push    r12
0x180079d67  push    r13
0x180079d69  push    r14
0x180079d6b  push    r15
0x180079d6d  sub     rsp, 50h
0x180079d71  mov     r15d, r9d
0x180079d74  mov     r12, r8
0x180079d77  mov     r13, rdx
0x180079d7a  mov     rbx, rcx
0x180079d7d  test    r8, r8
0x180079d80  jnz     short loc_180079D9D
0x180079d82  lea     r8, aPheappropertie; "pHeapProperties is NULL!"
0x180079d89  mov     edx, 27Ah
0x180079d8e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079d93  mov     eax, 80070057h
0x180079d98  jmp     loc_18007A2CF
0x180079d9d  mov     r9d, [r8]
0x180079da0  mov     esi, 80070057h
0x180079da5  mov     rdi, [rsp+88h+arg_20]
0x180079dad  test    r9d, r9d
0x180079db0  jle     short loc_180079DBA
0x180079db2  xor     ebp, ebp
0x180079db4  cmp     r9d, 6
0x180079db8  jl      short loc_180079DCA
0x180079dba  lea     r8, aD3d12HeapPrope_9; "D3D12_HEAP_PROPERTIES::Type is unrecogn"...
0x180079dc1  mov     edx, [rdi]
0x180079dc3  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079dc8  mov     ebp, esi
0x180079dca  cmp     dword ptr [r12], 5
0x180079dcf  jnz     short loc_180079DEF
0x180079dd1  cmp     dword ptr [r13+3ACh], 0
0x180079dd9  jnz     short loc_180079DEF
0x180079ddb  lea     r8, aD3d12HeapTypeG; "D3D12_HEAP_TYPE_GPU_UPLOAD is invalid w"...
0x180079de2  mov     edx, [rdi+18h]
0x180079de5  mov     rcx, rbx
0x180079de8  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079ded  mov     ebp, esi
0x180079def  cmp     dword ptr [r12+4], 3
0x180079df5  jbe     short loc_180079E10
0x180079df7  mov     r9d, [r12+4]
0x180079dfc  lea     r8, aD3d12HeapPrope_10; "D3D12_HEAP_PROPERTIES::CPUPageProperty "...
0x180079e03  mov     edx, [rdi+4]
0x180079e06  mov     rcx, rbx
0x180079e09  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079e0e  mov     ebp, esi
0x180079e10  lea     r14, [r12+8]
0x180079e15  mov     [rsp+88h+var_40], r14
0x180079e1a  cmp     dword ptr [r14], 2
0x180079e1e  jbe     short loc_180079E37
0x180079e20  mov     r9d, [r14]
0x180079e23  lea     r8, aD3d12HeapPrope_4; "D3D12_HEAP_PROPERTIES::MemoryPoolPrefer"...
0x180079e2a  mov     edx, [rdi+8]
0x180079e2d  mov     rcx, rbx
0x180079e30  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079e35  mov     ebp, esi
0x180079e37  mov     eax, r15d
0x180079e3a  and     eax, 0FFFF8012h
0x180079e3f  jz      short loc_180079E61
0x180079e41  mov     dword ptr [rsp+88h+var_68], eax
0x180079e45  mov     r9d, r15d
0x180079e48  lea     r8, aD3d12HeapFlags_4; "D3D12_HEAP_FLAGS has recognized flags s"...
0x180079e4f  mov     edx, [rdi+0Ch]
0x180079e52  mov     rcx, rbx
0x180079e55  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079e5a  mov     eax, esi
0x180079e5c  jmp     loc_18007A2CF
0x180079e61  test    ebp, ebp
0x180079e63  js      loc_18007A2CD
0x180079e69  mov     eax, [r13+290h]
0x180079e70  cmp     eax, 1000h
0x180079e75  jz      short loc_180079E82
0x180079e77  cmp     eax, 100h
0x180079e7c  jnz     loc_180079F9D
0x180079e82  xor     r14b, r14b
0x180079e85  test    r15b, 4
0x180079e89  jz      short loc_180079EA0
0x180079e8b  lea     r8, aD3d12HeapFlags_8; "D3D12_HEAP_FLAGS can't specify D3D12_HE"...
0x180079e92  mov     edx, [rdi+10h]
0x180079e95  mov     rcx, rbx
0x180079e98  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079e9d  mov     r14b, 1
0x180079ea0  bt      r15d, 8
0x180079ea5  jnb     short loc_180079EBC
0x180079ea7  lea     r8, aD3d12HeapFlags_11; "D3D12_HEAP_FLAGS can't specify D3D12_HE"...
0x180079eae  mov     edx, [rdi+10h]
0x180079eb1  mov     rcx, rbx
0x180079eb4  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079eb9  mov     r14b, 1
0x180079ebc  bt      r15d, 9
0x180079ec1  jnb     short loc_180079EE2
0x180079ec3  cmp     dword ptr [r13+3E4h], 0
0x180079ecb  jnz     short loc_180079EE2
0x180079ecd  lea     r8, aD3d12HeapFlags_9; "D3D12_HEAP_FLAGS can't specify D3D12_HE"...
0x180079ed4  mov     edx, [rdi+10h]
0x180079ed7  mov     rcx, rbx
0x180079eda  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079edf  mov     r14b, 1
0x180079ee2  mov     r13d, r15d
0x180079ee5  and     r13d, 8
0x180079ee9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12Displayable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable> `wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl(void)'::`2'::impl
0x180079ef0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(void)
0x180079ef5  test    al, al
0x180079ef7  jz      short loc_180079F0D
0x180079ef9  test    r13d, r13d
0x180079efc  jz      short loc_180079F27
0x180079efe  test    r15b, 20h
0x180079f02  jnz     short loc_180079F27
0x180079f04  lea     r8, aD3d12HeapFlags_2; "D3D12_HEAP_FLAGS can't specify D3D12_HE"...
0x180079f0b  jmp     short loc_180079F19
0x180079f0d  test    r13d, r13d
0x180079f10  jz      short loc_180079F27
0x180079f12  lea     r8, aD3d12HeapFlags_6; "D3D12_HEAP_FLAGS can't specify D3D12_HE"...
0x180079f19  mov     edx, [rdi+10h]
0x180079f1c  mov     rcx, rbx
0x180079f1f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079f24  mov     r14b, 1
0x180079f27  bt      r15d, 0Ah
0x180079f2c  jnb     short loc_180079F43
0x180079f2e  lea     r8, aD3d12HeapFlags_7; "D3D12_HEAP_FLAGS can't specify D3D12_HE"...
0x180079f35  mov     edx, [rdi+10h]
0x180079f38  mov     rcx, rbx
0x180079f3b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079f40  mov     r14b, 1
0x180079f43  mov     r13, [rsp+88h+arg_8]
0x180079f4b  cmp     dword ptr [r13+3E0h], 0
0x180079f53  jnz     short loc_180079F71
0x180079f55  cmp     dword ptr [r12], 4
0x180079f5a  jnz     short loc_180079F71
0x180079f5c  lea     r8, aD3d12HeapTypeC; "D3D12_HEAP_TYPE_CUSTOM is not supported"...
0x180079f63  mov     edx, [rdi+10h]
0x180079f66  mov     rcx, rbx
0x180079f69  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079f6e  mov     r14b, 1
0x180079f71  cmp     dword ptr [r12], 5
0x180079f76  jnz     short loc_180079F8F
0x180079f78  lea     r8, aD3d12HeapTypeG_0; "D3D12_HEAP_TYPE_GPU_UPLOAD is not suppo"...
0x180079f7f  mov     edx, [rdi+10h]
0x180079f82  mov     rcx, rbx
0x180079f85  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180079f8a  jmp     loc_180079E5A
0x180079f8f  test    r14b, r14b
0x180079f92  jnz     loc_180079E5A
0x180079f98  lea     r14, [r12+8]
0x180079f9d  bt      r15d, 0Dh
0x180079fa2  jnb     short loc_180079FB7
0x180079fa4  cmp     dword ptr [r13+3B4h], 0
0x180079fac  jnz     short loc_180079FB7
0x180079fae  lea     r8, aD3d12HeapFlags_5; "D3D12_HEAP_FLAGS can't specify D3D12_HE"...
0x180079fb5  jmp     short loc_180079F7F
0x180079fb7  mov     ecx, [r12]
0x180079fbb  cmp     ecx, 4
0x180079fbe  jnz     loc_18007A0B7
0x180079fc4  mov     [rsp+88h+arg_10], 0
0x180079fcc  mov     ecx, [r12+4]
0x180079fd1  test    ecx, ecx
0x180079fd3  jz      short loc_18007A040
0x180079fd5  sub     ecx, 2
0x180079fd8  jz      short loc_180079FF5
0x180079fda  cmp     ecx, 1
0x180079fdd  jnz     short loc_18007A054
0x180079fdf  mov     [rsp+88h+arg_10], cl
0x180079fe6  cmp     dword ptr [r14], 2
0x180079fea  jnz     short loc_18007A054
0x180079fec  lea     r8, aD3d12HeapPrope_3; "D3D12_HEAP_PROPERTIES is invalid. D3D12"...
0x180079ff3  jmp     short loc_18007A047
0x180079ff5  mov     [rsp+88h+arg_10], 1
0x180079ffd  cmp     dword ptr [r12+8], 2
0x18007a003  jnz     short loc_18007A054
0x18007a005  test    byte ptr [r13+2B0h], 2
0x18007a00d  jnz     short loc_18007A054
0x18007a00f  mov     eax, [r13+290h]
0x18007a016  cmp     eax, 1000h
0x18007a01b  jz      short loc_18007A037
0x18007a01d  cmp     eax, 100h
0x18007a022  jz      short loc_18007A037
0x18007a024  cmp     dword ptr [r13+3ACh], 0
0x18007a02c  jnz     short loc_18007A054
0x18007a02e  lea     r8, aD3d12HeapPrope_0; "D3D12_HEAP_PROPERTIES is invalid. D3D12"...
0x18007a035  jmp     short loc_18007A047
0x18007a037  lea     r8, aD3d12HeapPrope_5; "D3D12_HEAP_PROPERTIES is invalid. Using"...
0x18007a03e  jmp     short loc_18007A047
0x18007a040  lea     r8, aD3d12HeapPrope_6; "D3D12_HEAP_PROPERTIES is invalid. D3D12"...
0x18007a047  mov     edx, [rdi+10h]
0x18007a04a  mov     rcx, rbx
0x18007a04d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18007a052  mov     ebp, esi
0x18007a054  mov     ecx, [r14]
0x18007a057  test    ecx, ecx
0x18007a059  jz      short loc_18007A082
0x18007a05b  cmp     ecx, 1
0x18007a05e  jz      short loc_18007A096
0x18007a060  mov     eax, [rsp+88h+arg_30]
0x18007a067  lea     rcx, [rax+rax*4]
0x18007a06b  cmp     dword ptr [r13+rcx*4+0], 0
0x18007a071  jz      short loc_18007A096
0x18007a073  lea     r8, aD3d12HeapPrope_1; "D3D12_HEAP_PROPERTIES is invalid. Only "...
0x18007a07a  mov     edx, [rdi+10h]
0x18007a07d  jmp     loc_18007A395
0x18007a082  lea     r8, aD3d12HeapPrope; "D3D12_HEAP_PROPERTIES is invalid. D3D12"...
0x18007a089  mov     edx, [rdi+10h]
0x18007a08c  mov     rcx, rbx
0x18007a08f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18007a094  mov     ebp, esi
0x18007a096  test    ebp, ebp
0x18007a098  js      loc_18007A2CD
0x18007a09e  cmp     [rsp+88h+arg_10], 0
0x18007a0a6  jz      short loc_18007A104
0x18007a0a8  test    r15b, 1
0x18007a0ac  jz      short loc_18007A129
0x18007a0ae  lea     r8, aD3d12HeapFlags_10; "D3D12_HEAP_FLAGS has invalid flag combi"...
0x18007a0b5  jmp     short loc_18007A11C
0x18007a0b7  lea     eax, [rcx-2]
0x18007a0ba  test    eax, 0FFFFFFFCh
0x18007a0bf  jnz     short loc_18007A0CE
0x18007a0c1  cmp     ecx, 4
0x18007a0c4  mov     [rsp+88h+arg_10], 1
0x18007a0cc  jnz     short loc_18007A0D6
0x18007a0ce  mov     [rsp+88h+arg_10], 0
0x18007a0d6  cmp     dword ptr [r12+4], 0
0x18007a0dc  jz      short loc_18007A0F2
0x18007a0de  lea     r8, aD3d12HeapPrope_7; "D3D12_HEAP_PROPERTIES is invalid. D3D12"...
0x18007a0e5  mov     edx, [rdi+10h]
0x18007a0e8  mov     rcx, rbx
0x18007a0eb  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18007a0f0  mov     ebp, esi
0x18007a0f2  cmp     dword ptr [r14], 0
0x18007a0f6  jz      short loc_18007A096
0x18007a0f8  lea     r8, aD3d12HeapPrope_8; "D3D12_HEAP_PROPERTIES is invalid. D3D12"...
0x18007a0ff  jmp     loc_18007A07A
0x18007a104  bt      r15d, 9
0x18007a109  jnb     short loc_18007A129
0x18007a10b  test    byte ptr [r13+2B0h], 1
0x18007a113  jnz     short loc_18007A129
0x18007a115  lea     r8, aD3d12HeapFlags; "D3D12_HEAP_FLAGS has invalid flag combi"...
0x18007a11c  mov     edx, [rdi+14h]
0x18007a11f  mov     rcx, rbx
0x18007a122  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18007a127  mov     ebp, esi
0x18007a129  mov     edx, r15d
0x18007a12c  mov     ecx, 0C4h
0x18007a131  and     edx, ecx
0x18007a133  cmp     [rsp+88h+arg_28], 0
0x18007a13b  jz      short loc_18007A15C
0x18007a13d  test    edx, edx
0x18007a13f  jz      loc_18007A22D
0x18007a145  lea     r8, aWhenCreatingAC; "When creating a committed resource, D3D"...
0x18007a14c  mov     edx, [rdi+14h]
0x18007a14f  mov     rcx, rbx
0x18007a152  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18007a157  jmp     loc_18007A22B
0x18007a15c  test    r15b, 20h
0x18007a160  jz      short loc_18007A1A2
0x18007a162  test    edx, edx
0x18007a164  jz      loc_18007A22D
0x18007a16a  mov     ecx, edx
0x18007a16c  shr     ecx, 2
0x18007a16f  and     ecx, 1
0x18007a172  mov     eax, edx
0x18007a174  shr     eax, 6
0x18007a177  and     eax, 1
0x18007a17a  shr     edx, 7
0x18007a17d  and     edx, 1
0x18007a180  mov     [rsp+88h+var_60], ecx
0x18007a184  mov     dword ptr [rsp+88h+var_68], eax
0x18007a188  mov     r9d, edx
0x18007a18b  lea     r8, aD3d12HeapFlags_3; "D3D12_HEAP_FLAGS has invalid flag combi"...
0x18007a192  mov     edx, [rdi+14h]
0x18007a195  mov     rcx, rbx
0x18007a198  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18007a19d  jmp     loc_18007A22B
0x18007a1a2  test    edx, edx
0x18007a1a4  jnz     short loc_18007A1B2
0x18007a1a6  cmp     dword ptr [r13+284h], 2
0x18007a1ae  jge     short loc_18007A22D
0x18007a1b0  jmp     short loc_18007A1BD
0x18007a1b2  lea     eax, [rdx-1]
0x18007a1b5  test    edx, eax
0x18007a1b7  jz      short loc_18007A1BD
0x18007a1b9  cmp     edx, ecx
0x18007a1bb  jnz     short loc_18007A22D
0x18007a1bd  mov     r8d, edx
0x18007a1c0  shr     r8d, 2
0x18007a1c4  and     r8d, 1
0x18007a1c8  mov     r10d, edx
0x18007a1cb  shr     r10d, 6
0x18007a1cf  and     r10d, 1
0x18007a1d3  shr     edx, 7
0x18007a1d6  and     edx, 1
0x18007a1d9  mov     ecx, [r13+284h]
0x18007a1e0  sub     ecx, 1
0x18007a1e3  jz      short loc_18007A1FC
0x18007a1e5  cmp     ecx, 1
0x18007a1e8  jz      short loc_18007A1F3
0x18007a1ea  lea     r9, aUnrecognized; "Unrecognized"
0x18007a1f1  jmp     short loc_18007A203
  ... truncated ...
```
