# CCreateShaderValidator::ValidateShader(void)

- ea: `0x1800a4f88`
- end: `0x1800a531d`
- name: `?ValidateShader@CCreateShaderValidator@@IEAAXXZ`
- size: `917`
- prototype: `void __fastcall(CCreateShaderValidator *__hidden this)`
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018070`
- `0x180018518`
- `0x18006c8bc`
- `0x18014dfc8`
- `0x18014e170`
- `0x18014e3f8`
- `0x18014e778`
- `0x18014ede8`
- `0x18014f070`

## callees

- `0x18001a12c`
- `0x18001a488`
- `0x18002ef50`
- `0x180058f70`
- `0x180059134`
- `0x1800a4f88`

## string_xrefs

- `0x1800a5153`: `Shader uses sampler descriptor heap indexing, but the device does not support this. The device must support both D3D12_RESOURCE_BINDING_TIER_3 and D3D_SHADER_MODEL_6_6. To check for support, check device caps via the CheckFeatureSupport() API`
- `0x1800a512b`: `Shader uses resource descriptor heap indexing, but the device does not support this. The device must support both D3D12_RESOURCE_BINDING_TIER_3 and D3D_SHADER_MODEL_6_6. To check for support, check device caps via the CheckFeatureSupport() API`
- `0x1800a5250`: `Shader uses features (0x%x) not recognized by this D3D version.  See D3D_SHADER_FEATURE_* in d3dcommon.h from the latest SDK.`
- `0x1800a5226`: `Shader uses RWTexture2DMS*, writeable MSAA texture, but the device doesn't support it. To check for support, check device caps for WriteableMSAATexturesSupported via the CheckFeatureSupport() API`
- `0x1800a519a`: `Shader uses atomic int64 on a descriptor heap resource, but the device does not support this. To check for support, check device caps via the CheckFeatureSupport() API`

## pseudocode

```c
void __fastcall CCreateShaderValidator::ValidateShader(CCreateShaderValidator *this)
{
  __int64 v2; // rbx
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // eax
  _BYTE v8[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h]
  __int64 v10; // [rsp+140h] [rbp+40h] BYREF
  void *v11; // [rsp+148h] [rbp+48h] BYREF

  v10 = 0;
  if ( (int)DXBCGetShaderFeatureInfo(*((const void **)this + 2), (struct SShaderFeatureInfo *)&v10) >= 0 )
  {
    v2 = v10;
    if ( (v10 & 0x800) != 0 && !*((_BYTE *)this + 78) )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses new Typed UAV Load formats, but the device does not support this. To check for support, check device"
        " caps via the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x4000) != 0 && !*((_BYTE *)this + 79) )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses wave ops, but the device does not support this. To check for support, check device caps via the Chec"
        "kFeatureSupport() API");
    }
    if ( (v2 & 0x8000) != 0 && (*((_BYTE *)this + 72) & 0x10) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses Int64 ops, but the device does not support this. To check for support, check device caps via the Che"
        "ckFeatureSupport() API");
    }
    if ( (v2 & 0x40000) != 0 && (*((_BYTE *)this + 72) & 0x40) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses native 16bit ops, but the device does not support this. To check for support, check device caps via "
        "the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x200000) != 0 && (*((_DWORD *)this + 18) & 0x100) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses sampler feedback, but the device does not support this. To check for support, check device caps via "
        "the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x100000) != 0 && *((int *)this + 11) < 11 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses raytracing tier 1.1 features, but the device does not support this. To check for support, check devi"
        "ce caps via the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x400000) != 0 && (*((_DWORD *)this + 18) & 0x200) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses atomic int64 on typed resources, but the device does not support this. To check for support, check d"
        "evice caps via the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x800000) != 0 && (*((_DWORD *)this + 18) & 0x400) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses atomic int64 on group shared, but the device does not support this. To check for support, check devi"
        "ce caps via the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x1000000) != 0 && (*((_DWORD *)this + 18) & 0x800) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses derivatives in mesh/amplification shaders, but the device does not support this. To check for suppor"
        "t, check device caps via the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x2000000) != 0 && (*((int *)this + 10) < 3 || *((int *)this + 13) < 102) )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses resource descriptor heap indexing, but the device does not support this. The device must support bot"
        "h D3D12_RESOURCE_BINDING_TIER_3 and D3D_SHADER_MODEL_6_6. To check for support, check device caps via the CheckF"
        "eatureSupport() API");
    }
    if ( (v2 & 0x4000000) != 0 && (*((int *)this + 10) < 3 || *((int *)this + 13) < 102) )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses sampler descriptor heap indexing, but the device does not support this. The device must support both"
        " D3D12_RESOURCE_BINDING_TIER_3 and D3D_SHADER_MODEL_6_6. To check for support, check device caps via the CheckFe"
        "atureSupport() API");
    }
    if ( (v2 & 0x8000000) != 0 && *((int *)this + 16) < 10 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses WaveMMA, but the device does not support this. To check for support, check device caps via the Check"
        "FeatureSupport() API");
    }
    if ( (v2 & 0x10000000) != 0 && (*((_DWORD *)this + 18) & 0x4000) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses atomic int64 on a descriptor heap resource, but the device does not support this. To check for suppo"
        "rt, check device caps via the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x80000000) != 0 && (*((_DWORD *)this + 18) & 0x8000) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses SampleCmpGradient or SampleCmpBias, but the device does not support this. To check for support, chec"
        "k device caps via the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x100000000LL) != 0 && (*((_DWORD *)this + 18) & 0x10000) == 0 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses SV_StartVertexLocation or SV_StartInstanceLocation, but the device does not support this. To check f"
        "or support, check device caps via the CheckFeatureSupport() API");
    }
    if ( (v2 & 0x20000000) != 0 && (*((_DWORD *)this + 18) & 0x20000) == 0 )
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses features that are part of shader model 6.7's optional advanced texture operations feature set that t"
        "he device doesn't support. To check for support, check device caps for AdvancedTexureOpsSupported via the CheckF"
        "eatureSupport() API");
    if ( (v2 & 0x40000000) != 0 && (*((_DWORD *)this + 18) & 0x40000) == 0 )
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        622,
        "Shader uses RWTexture2DMS*, writeable MSAA texture, but the device doesn't support it. To check for support, che"
        "ck device caps for WriteableMSAATexturesSupported via the CheckFeatureSupport() API");
    if ( !*((_BYTE *)this + 68) )
    {
      v3 = v2 & 0xFE00000000LL;
      if ( v3 )
      {
        ++*((_DWORD *)this + 8);
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          622,
          "Shader uses features (0x%x) not recognized by this D3D version.  See D3D_SHADER_FEATURE_* in d3dcommon.h from the latest SDK.",
          v3);
      }
    }
  }
  if ( *((int *)this + 13) >= 96 )
  {
    v4 = *((_QWORD *)this + 2);
    v11 = 0;
    LODWORD(v10) = 0;
    if ( (int)DXBCGetNamedBlob(v4, 810963792, &v11, &v10) >= 0 )
    {
      DxilPipelineStateValidation::DxilPipelineStateValidation((DxilPipelineStateValidation *)v8);
      if ( (unsigned __int8)DxilPipelineStateValidation::InitFromPSV0((DxilPipelineStateValidation *)v8, v11, v10) )
      {
        v5 = v9;
        v6 = *((_DWORD *)this + 14);
        if ( *(_DWORD *)(v9 + 16) > v6 )
        {
          ++*((_DWORD *)this + 8);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            622,
            "Shader wants wave lane count of %d but maximum wave lane count for device is %d. To check for support, check"
            " device caps via the CheckFeatureSupport() API",
            *(_DWORD *)(v5 + 16),
            v6);
        }
        v7 = *((_DWORD *)this + 15);
        if ( *(_DWORD *)(v5 + 20) < v7 )
        {
          ++*((_DWORD *)this + 8);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            622,
            "Shader wants wave lane count of %d but minimum wave lane count for device is %d. To check for support, check"
            " device caps via the CheckFeatureSupport() API",
            *(_DWORD *)(v5 + 20),
            v7);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800a4f88  mov     [rsp-8+arg_10], rbx
0x1800a4f8d  push    rbp
0x1800a4f8e  push    rsi
0x1800a4f8f  push    rdi
0x1800a4f90  push    r14
0x1800a4f92  push    r15
0x1800a4f94  lea     rbp, [rsp-10h]
0x1800a4f99  sub     rsp, 110h
0x1800a4fa0  mov     rdi, rcx
0x1800a4fa3  mov     [rbp+30h+arg_0], 0
0x1800a4fab  mov     rcx, [rcx+10h]; void *
0x1800a4faf  lea     rdx, [rbp+30h+arg_0]; struct SShaderFeatureInfo *
0x1800a4fb3  call    ?DXBCGetShaderFeatureInfo@@YAJPEBXPEAUSShaderFeatureInfo@@@Z; DXBCGetShaderFeatureInfo(void const *,SShaderFeatureInfo *)
0x1800a4fb8  lea     r14, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x1800a4fbf  mov     esi, 26Eh
0x1800a4fc4  mov     r15d, 1
0x1800a4fca  test    eax, eax
0x1800a4fcc  js      loc_1800A5264
0x1800a4fd2  mov     rbx, [rbp+30h+arg_0]
0x1800a4fd6  bt      rbx, 0Bh
0x1800a4fdb  jnb     short loc_1800A4FF8
0x1800a4fdd  cmp     byte ptr [rdi+4Eh], 0
0x1800a4fe1  jnz     short loc_1800A4FF8
0x1800a4fe3  add     [rdi+20h], r15d
0x1800a4fe7  lea     r8, aShaderUsesNewT; "Shader uses new Typed UAV Load formats,"...
0x1800a4fee  mov     edx, esi
0x1800a4ff0  mov     rcx, r14
0x1800a4ff3  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a4ff8  bt      rbx, 0Eh
0x1800a4ffd  jnb     short loc_1800A501A
0x1800a4fff  cmp     byte ptr [rdi+4Fh], 0
0x1800a5003  jnz     short loc_1800A501A
0x1800a5005  add     [rdi+20h], r15d
0x1800a5009  lea     r8, aShaderUsesWave; "Shader uses wave ops, but the device do"...
0x1800a5010  mov     edx, esi
0x1800a5012  mov     rcx, r14
0x1800a5015  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a501a  bt      rbx, 0Fh
0x1800a501f  jnb     short loc_1800A503C
0x1800a5021  test    byte ptr [rdi+48h], 10h
0x1800a5025  jnz     short loc_1800A503C
0x1800a5027  add     [rdi+20h], r15d
0x1800a502b  lea     r8, aShaderUsesInt6; "Shader uses Int64 ops, but the device d"...
0x1800a5032  mov     edx, esi
0x1800a5034  mov     rcx, r14
0x1800a5037  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a503c  bt      rbx, 12h
0x1800a5041  jnb     short loc_1800A505E
0x1800a5043  test    byte ptr [rdi+48h], 40h
0x1800a5047  jnz     short loc_1800A505E
0x1800a5049  add     [rdi+20h], r15d
0x1800a504d  lea     r8, aShaderUsesNati; "Shader uses native 16bit ops, but the d"...
0x1800a5054  mov     edx, esi
0x1800a5056  mov     rcx, r14
0x1800a5059  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a505e  bt      rbx, 15h
0x1800a5063  jnb     short loc_1800A5083
0x1800a5065  test    dword ptr [rdi+48h], 100h
0x1800a506c  jnz     short loc_1800A5083
0x1800a506e  add     [rdi+20h], r15d
0x1800a5072  lea     r8, aShaderUsesSamp_3; "Shader uses sampler feedback, but the d"...
0x1800a5079  mov     edx, esi
0x1800a507b  mov     rcx, r14
0x1800a507e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a5083  bt      rbx, 14h
0x1800a5088  jnb     short loc_1800A50A5
0x1800a508a  cmp     dword ptr [rdi+2Ch], 0Bh
0x1800a508e  jge     short loc_1800A50A5
0x1800a5090  add     [rdi+20h], r15d
0x1800a5094  lea     r8, aShaderUsesRayt; "Shader uses raytracing tier 1.1 feature"...
0x1800a509b  mov     edx, esi
0x1800a509d  mov     rcx, r14
0x1800a50a0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a50a5  bt      rbx, 16h
0x1800a50aa  jnb     short loc_1800A50CA
0x1800a50ac  test    dword ptr [rdi+48h], 200h
0x1800a50b3  jnz     short loc_1800A50CA
0x1800a50b5  add     [rdi+20h], r15d
0x1800a50b9  lea     r8, aShaderUsesAtom; "Shader uses atomic int64 on typed resou"...
0x1800a50c0  mov     edx, esi
0x1800a50c2  mov     rcx, r14
0x1800a50c5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a50ca  bt      rbx, 17h
0x1800a50cf  jnb     short loc_1800A50EF
0x1800a50d1  test    dword ptr [rdi+48h], 400h
0x1800a50d8  jnz     short loc_1800A50EF
0x1800a50da  add     [rdi+20h], r15d
0x1800a50de  lea     r8, aShaderUsesAtom_1; "Shader uses atomic int64 on group share"...
0x1800a50e5  mov     edx, esi
0x1800a50e7  mov     rcx, r14
0x1800a50ea  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a50ef  bt      rbx, 18h
0x1800a50f4  jnb     short loc_1800A5114
0x1800a50f6  test    dword ptr [rdi+48h], 800h
0x1800a50fd  jnz     short loc_1800A5114
0x1800a50ff  add     [rdi+20h], r15d
0x1800a5103  lea     r8, aShaderUsesDeri; "Shader uses derivatives in mesh/amplifi"...
0x1800a510a  mov     edx, esi
0x1800a510c  mov     rcx, r14
0x1800a510f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a5114  bt      rbx, 19h
0x1800a5119  jnb     short loc_1800A513C
0x1800a511b  cmp     dword ptr [rdi+28h], 3
0x1800a511f  jl      short loc_1800A5127
0x1800a5121  cmp     dword ptr [rdi+34h], 66h ; 'f'
0x1800a5125  jge     short loc_1800A513C
0x1800a5127  add     [rdi+20h], r15d
0x1800a512b  lea     r8, aShaderUsesReso; "Shader uses resource descriptor heap in"...
0x1800a5132  mov     edx, esi
0x1800a5134  mov     rcx, r14
0x1800a5137  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a513c  bt      rbx, 1Ah
0x1800a5141  jnb     short loc_1800A5164
0x1800a5143  cmp     dword ptr [rdi+28h], 3
0x1800a5147  jl      short loc_1800A514F
0x1800a5149  cmp     dword ptr [rdi+34h], 66h ; 'f'
0x1800a514d  jge     short loc_1800A5164
0x1800a514f  add     [rdi+20h], r15d
0x1800a5153  lea     r8, aShaderUsesSamp_0; "Shader uses sampler descriptor heap ind"...
0x1800a515a  mov     edx, esi
0x1800a515c  mov     rcx, r14
0x1800a515f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a5164  bt      rbx, 1Bh
0x1800a5169  jnb     short loc_1800A5186
0x1800a516b  cmp     dword ptr [rdi+40h], 0Ah
0x1800a516f  jge     short loc_1800A5186
0x1800a5171  add     [rdi+20h], r15d
0x1800a5175  lea     r8, aShaderUsesWave_0; "Shader uses WaveMMA, but the device doe"...
0x1800a517c  mov     edx, esi
0x1800a517e  mov     rcx, r14
0x1800a5181  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a5186  bt      rbx, 1Ch
0x1800a518b  jnb     short loc_1800A51AB
0x1800a518d  test    dword ptr [rdi+48h], 4000h
0x1800a5194  jnz     short loc_1800A51AB
0x1800a5196  add     [rdi+20h], r15d
0x1800a519a  lea     r8, aShaderUsesAtom_0; "Shader uses atomic int64 on a descripto"...
0x1800a51a1  mov     edx, esi
0x1800a51a3  mov     rcx, r14
0x1800a51a6  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a51ab  bt      rbx, 1Fh
0x1800a51b0  jnb     short loc_1800A51D0
0x1800a51b2  test    dword ptr [rdi+48h], 8000h
0x1800a51b9  jnz     short loc_1800A51D0
0x1800a51bb  add     [rdi+20h], r15d
0x1800a51bf  lea     r8, aShaderUsesSamp_2; "Shader uses SampleCmpGradient or Sample"...
0x1800a51c6  mov     edx, esi
0x1800a51c8  mov     rcx, r14
0x1800a51cb  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a51d0  bt      rbx, 20h ; ' '
0x1800a51d5  jnb     short loc_1800A51F5
0x1800a51d7  test    dword ptr [rdi+48h], 10000h
0x1800a51de  jnz     short loc_1800A51F5
0x1800a51e0  add     [rdi+20h], r15d
0x1800a51e4  lea     r8, aShaderUsesSvSt; "Shader uses SV_StartVertexLocation or S"...
0x1800a51eb  mov     edx, esi
0x1800a51ed  mov     rcx, r14
0x1800a51f0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a51f5  bt      rbx, 1Dh
0x1800a51fa  jnb     short loc_1800A5216
0x1800a51fc  test    dword ptr [rdi+48h], 20000h
0x1800a5203  jnz     short loc_1800A5216
0x1800a5205  lea     r8, aShaderUsesFeat_0; "Shader uses features that are part of s"...
0x1800a520c  mov     edx, esi
0x1800a520e  mov     rcx, r14
0x1800a5211  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a5216  bt      rbx, 1Eh
0x1800a521b  jnb     short loc_1800A5237
0x1800a521d  test    dword ptr [rdi+48h], 40000h
0x1800a5224  jnz     short loc_1800A5237
0x1800a5226  lea     r8, aShaderUsesRwte; "Shader uses RWTexture2DMS*, writeable M"...
0x1800a522d  mov     edx, esi
0x1800a522f  mov     rcx, r14
0x1800a5232  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a5237  cmp     byte ptr [rdi+44h], 0
0x1800a523b  jnz     short loc_1800A5264
0x1800a523d  mov     rax, 0FE00000000h
0x1800a5247  and     rbx, rax
0x1800a524a  jz      short loc_1800A5264
0x1800a524c  add     [rdi+20h], r15d
0x1800a5250  lea     r8, aShaderUsesFeat; "Shader uses features (0x%x) not recogni"...
0x1800a5257  mov     r9, rbx
0x1800a525a  mov     edx, esi
0x1800a525c  mov     rcx, r14
0x1800a525f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a5264  cmp     dword ptr [rdi+34h], 60h ; '`'
0x1800a5268  jl      loc_1800A5306
0x1800a526e  mov     rcx, [rdi+10h]
0x1800a5272  lea     r9, [rbp+30h+arg_0]
0x1800a5276  lea     r8, [rbp+30h+arg_8]
0x1800a527a  mov     [rbp+30h+arg_8], 0
0x1800a5282  mov     edx, 30565350h
0x1800a5287  mov     dword ptr [rbp+30h+arg_0], 0
0x1800a528e  call    ?DXBCGetNamedBlob@@YAJPEBXW4DXBCFourCC@@PEAPEBIPEAI@Z; DXBCGetNamedBlob(void const *,DXBCFourCC,uint const * *,uint *)
0x1800a5293  test    eax, eax
0x1800a5295  js      short loc_1800A5306
0x1800a5297  lea     rcx, [rsp+130h+var_100]; this
0x1800a529c  call    ??0DxilPipelineStateValidation@@QEAA@XZ; DxilPipelineStateValidation::DxilPipelineStateValidation(void)
0x1800a52a1  mov     r8d, dword ptr [rbp+30h+arg_0]; unsigned int
0x1800a52a5  lea     rcx, [rsp+130h+var_100]; this
0x1800a52aa  mov     rdx, [rbp+30h+arg_8]; void *
0x1800a52ae  call    ?InitFromPSV0@DxilPipelineStateValidation@@QEAA_NPEBXI@Z; DxilPipelineStateValidation::InitFromPSV0(void const *,uint)
0x1800a52b3  test    al, al
0x1800a52b5  jz      short loc_1800A5306
0x1800a52b7  mov     rbx, [rsp+130h+var_F8]
0x1800a52bc  mov     eax, [rdi+38h]
0x1800a52bf  cmp     [rbx+10h], eax
0x1800a52c2  jbe     short loc_1800A52E1
0x1800a52c4  add     [rdi+20h], r15d
0x1800a52c8  lea     r8, aShaderWantsWav_0; "Shader wants wave lane count of %d but "...
0x1800a52cf  mov     r9d, [rbx+10h]
0x1800a52d3  mov     edx, esi
0x1800a52d5  mov     rcx, r14
0x1800a52d8  mov     [rsp+130h+var_110], eax
0x1800a52dc  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a52e1  mov     eax, [rdi+3Ch]
0x1800a52e4  cmp     [rbx+14h], eax
0x1800a52e7  jnb     short loc_1800A5306
0x1800a52e9  add     [rdi+20h], r15d
0x1800a52ed  lea     r8, aShaderWantsWav; "Shader wants wave lane count of %d but "...
0x1800a52f4  mov     r9d, [rbx+14h]
0x1800a52f8  mov     edx, esi
0x1800a52fa  mov     rcx, r14
0x1800a52fd  mov     [rsp+130h+var_110], eax
0x1800a5301  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800a5306  mov     rbx, [rsp+130h+arg_10]
0x1800a530e  add     rsp, 110h
0x1800a5315  pop     r15
0x1800a5317  pop     r14
0x1800a5319  pop     rdi
0x1800a531a  pop     rsi
0x1800a531b  pop     rbp
0x1800a531c  retn
```
