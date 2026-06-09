# IsStreamFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *,tWAVEFORMATEX * *)

- ea: `0x180021620`
- end: `0x1800220d6`
- name: `?IsStreamFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3PEAPEAU4@@Z`
- size: `2742`
- prototype: `int(struct EndpointCharacteristicsDescriptor *, struct _GUID *__struct_ptr, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, const struct tWAVEFORMATEX *, const struct tWAVEFORMATEX *, struct tWAVEFORMATEX **)`
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e308`
- `0x18001fb90`
- `0x1800830c0`
- `0x180083df0`

## callees

- `0x1800087dc`
- `0x18000ae1c`
- `0x1800210c4`
- `0x180021620`
- `0x1800220e0`
- `0x180022f70`
- `0x180023100`
- `0x18002318c`
- `0x1800237e0`
- `0x180024094`
- `0x180029f20`
- `0x18003eff0`
- `0x18003f090`
- `0x180098c54`
- `0x1800cddac`
- `0x1800ce75c`
- `0x1800d0598`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800220cf`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800220cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021f10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021f10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021dcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021ffe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021dcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021ffe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002208d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002208d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800216b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800216b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021cbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021cbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall IsStreamFormatSupportedForMixFormat(
        struct EndpointCharacteristicsDescriptor *a1,
        struct _GUID *a2,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a3,
        const struct tWAVEFORMATEX *a4,
        struct tWAVEFORMATEX *Src,
        struct tWAVEFORMATEX **a6)
{
  __int64 *v8; // rsi
  unsigned __int16 *v9; // rdi
  const struct tWAVEFORMATEX *v10; // r15
  __int64 cbSize; // r14
  char *v12; // rax
  char *v13; // rbx
  __int64 v14; // r14
  unsigned __int16 *v15; // rax
  __int16 v16; // ax
  BOOL v17; // r8d
  __int64 v18; // rax
  __int64 j; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  unsigned __int16 v22; // ax
  _QWORD *v23; // rsi
  __int64 v24; // r12
  __int64 v25; // r13
  __int64 v26; // rax
  HRESULT v27; // r15d
  struct _GUID v28; // xmm0
  IAudioMediaType *v29; // rax
  IAudioMediaType *v30; // r10
  int v31; // edx
  IAudioMediaType *v32; // r8
  IAudioMediaType *v33; // rcx
  int v34; // r8d
  int lpVtbl; // r11d
  __int64 v36; // r9
  int i; // eax
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v38; // r11d
  HRESULT InitializedSystemEffectInterface; // eax
  CEndpointCharacteristics **v40; // r12
  bool v41; // zf
  __int64 v42; // rax
  int v43; // eax
  struct tWAVEFORMATEX **v44; // r14
  bool v46; // r15
  void *v47; // rcx
  const struct tWAVEFORMATEX *v48; // r12
  __int64 v49; // r15
  struct tWAVEFORMATEX *v50; // rax
  struct tWAVEFORMATEX *v51; // rcx
  __int64 v52; // rcx
  unsigned __int16 v53; // ax
  IAudioMediaType *v54; // rax
  unsigned __int64 v55; // rax
  struct IAudioMediaTypeVtbl *v56; // r8
  unsigned __int64 v57; // rax
  _QWORD *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rdx
  IAudioMediaType *ppIAudioMediaType; // [rsp+68h] [rbp-A0h] BYREF
  IAudioMediaType *v63; // [rsp+70h] [rbp-98h] BYREF
  __int64 v64; // [rsp+78h] [rbp-90h] BYREF
  __int64 *v65; // [rsp+80h] [rbp-88h] BYREF
  struct tWAVEFORMATEX *v66[2]; // [rsp+88h] [rbp-80h] BYREF
  char v67; // [rsp+98h] [rbp-70h]
  IAudioMediaType *v68; // [rsp+A8h] [rbp-60h]
  IAudioMediaType *v69; // [rsp+B0h] [rbp-58h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B8h] [rbp-50h]
  struct _GUID v71; // [rsp+C8h] [rbp-40h] BYREF
  struct _GUID v72; // [rsp+D8h] [rbp-30h] BYREF
  char *v73; // [rsp+E8h] [rbp-20h]
  unsigned __int16 *v74; // [rsp+F0h] [rbp-18h]
  IAudioMediaType *v75; // [rsp+F8h] [rbp-10h]

  LODWORD(ppIAudioMediaType) = 0;
  v8 = 0;
  v65 = 0;
  if ( a6 )
    *a6 = 0;
  v9 = 0;
  v10 = Src;
  cbSize = Src->cbSize;
  v12 = (char *)CoTaskMemAlloc(cbSize + 18);
  v13 = v12;
  if ( !v12 )
  {
    v13 = 0;
    v27 = -2147024882;
    goto LABEL_70;
  }
  memcpy_0(v12, v10, cbSize + 18);
  v73 = v13;
  v14 = a4->cbSize;
  v15 = (unsigned __int16 *)CoTaskMemAlloc(v14 + 18);
  v9 = v15;
  if ( !v15 )
  {
    v9 = 0;
    v27 = -2147024882;
    goto LABEL_70;
  }
  memcpy_0(v15, a4, v14 + 18);
  v74 = v9;
  if ( (*((_WORD *)v13 + 7) & 0xFFF8u) > 0x100 )
  {
    v27 = -2004287480;
    goto LABEL_70;
  }
  v16 = *(_WORD *)v13;
  if ( *(_WORD *)v13 != 0xFFFE )
  {
    v17 = 1;
    LODWORD(v64) = 1;
    if ( v16 != 1 )
    {
LABEL_8:
      v18 = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1;
      j = *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4;
      goto LABEL_9;
    }
    *(_WORD *)v13 = 3;
LABEL_98:
    *((_WORD *)v13 + 7) = 32;
    v53 = 4 * *((_WORD *)v13 + 1);
    *((_WORD *)v13 + 6) = v53;
    *((_DWORD *)v13 + 2) = *((_DWORD *)v13 + 1) * v53;
    goto LABEL_8;
  }
  v17 = (v13[18] & 7) == 0;
  LODWORD(v64) = v17;
  v18 = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1;
  j = *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4;
  v52 = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 - *((_QWORD *)v13 + 3);
  if ( *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 == *((_QWORD *)v13 + 3) )
    v52 = *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4 - *((_QWORD *)v13 + 4);
  if ( !v52 && (v13[18] & 7) == 0 )
  {
    *(GUID *)(v13 + 24) = GUID_00000003_0000_0010_8000_00aa00389b71;
    *((_WORD *)v13 + 9) = 32;
    goto LABEL_98;
  }
LABEL_9:
  v20 = *v9;
  if ( (_WORD)v20 == 1 )
  {
    *v9 = 3;
    LODWORD(v64) = v17;
    goto LABEL_16;
  }
  if ( (_WORD)v20 != 0xFFFE )
    goto LABEL_17;
  v21 = v18 - *((_QWORD *)v9 + 3);
  if ( !v21 )
    v21 = j - *((_QWORD *)v9 + 4);
  if ( v21 )
    goto LABEL_17;
  if ( (v9[9] & 7) == 0 )
  {
    *(GUID *)(v9 + 12) = GUID_00000003_0000_0010_8000_00aa00389b71;
    v9[9] = 32;
LABEL_16:
    v9[7] = 32;
    v22 = 4 * v9[1];
    v9[6] = v22;
    v20 = *((_DWORD *)v9 + 1) * (unsigned int)v22;
    *((_DWORD *)v9 + 2) = v20;
    goto LABEL_17;
  }
  LODWORD(v64) = v17;
LABEL_17:
  v23 = (_QWORD *)*((_QWORD *)a1 + 1);
  if ( (unsigned __int64)(int)a3 >= v23[180] )
    goto LABEL_163;
  v24 = 96LL * (int)a3;
  SystemEffectDescriptor::ResolveAllOverridingChains((SystemEffectDescriptor *)(v24 + v23[181]));
  if ( (unsigned __int64)(int)a3 >= v23[182] )
    goto LABEL_163;
  SystemEffectDescriptor::ResolveAllOverridingChains((SystemEffectDescriptor *)(v24 + v23[183]));
  if ( (unsigned __int64)(int)a3 >= v23[184] )
    goto LABEL_163;
  SystemEffectDescriptor::ResolveAllOverridingChains((SystemEffectDescriptor *)(v24 + v23[185]));
  if ( (unsigned __int64)(int)a3 >= v23[202] )
    goto LABEL_163;
  v25 = *((_QWORD *)a1 + 1);
  v26 = v23[203];
  v8 = 0;
  v65 = 0;
  if ( !*(_DWORD *)(v26 + 4LL * (int)a3) )
  {
    if ( a3 == eKeywordDetectorConnector
      || (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes((EffectPack *)v25, a3) )
    {
      v27 = 0;
      goto LABEL_54;
    }
    *(GUID *)v66 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3;
    v61 = gsl::span<SystemEffectDescriptor,-1>::operator[](v25 + 1440, a3);
    InitializedSystemEffectInterface = EffectPack::GetInitializedSystemEffectInterface(
                                         v25,
                                         v61,
                                         1,
                                         0,
                                         v66,
                                         0,
                                         1,
                                         a3,
                                         0,
                                         &v65,
                                         0);
LABEL_53:
    v8 = v65;
    v27 = InitializedSystemEffectInterface;
    goto LABEL_54;
  }
  if ( (unsigned __int64)(int)a3 >= *(_QWORD *)(v25 + 1440) )
    goto LABEL_163;
  SystemEffectDescriptor::ResolveAllOverridingChains((SystemEffectDescriptor *)(v24 + *(_QWORD *)(v25 + 1448)));
  if ( (unsigned __int64)(int)a3 >= *(_QWORD *)(v25 + 1456) )
    goto LABEL_163;
  SystemEffectDescriptor::ResolveAllOverridingChains((SystemEffectDescriptor *)(v24 + *(_QWORD *)(v25 + 1464)));
  if ( (unsigned __int64)(int)a3 >= *(_QWORD *)(v25 + 1472) )
    goto LABEL_163;
  SystemEffectDescriptor::ResolveAllOverridingChains((SystemEffectDescriptor *)(v24 + *(_QWORD *)(v25 + 1480)));
  if ( (unsigned __int64)(int)a3 >= *(_QWORD *)(v25 + 1616) )
    goto LABEL_163;
  v27 = 0;
  if ( !*(_DWORD *)(*(_QWORD *)(v25 + 1624) + 4LL * (int)a3) )
    goto LABEL_54;
  if ( (unsigned __int64)(int)a3 >= *(_QWORD *)(v25 + 1440) )
  {
LABEL_163:
    _o_terminate(v20, j);
    JUMPOUT(0x1800220D5LL);
  }
  v63 = (IAudioMediaType *)(*(_QWORD *)(v25 + 1448) + 96LL * (int)a3);
  if ( !(unsigned int)CEndpointCharacteristics::AreEnhancementsEnabled(*(CEndpointCharacteristics **)(v25 + 1584)) )
  {
    v38 = a3;
    if ( a3 != eKeywordDetectorConnector )
    {
      *(struct _GUID *)v66 = *a2;
      j = 0;
      v54 = v63;
      while ( (int)j < SLODWORD(v63[1].lpVtbl) )
      {
        v20 = (__int64)v54->lpVtbl + 16 * (int)j;
        v55 = *(_QWORD *)v20 - (unsigned __int64)v66[0];
        if ( *(struct tWAVEFORMATEX **)v20 == v66[0] )
          v55 = *(_QWORD *)(v20 + 8) - (unsigned __int64)v66[1];
        if ( !v55 )
          goto LABEL_105;
        j = (unsigned int)(j + 1);
        v54 = v63;
      }
      j = 0xFFFFFFFFLL;
LABEL_105:
      if ( (_DWORD)j == -1 )
        goto LABEL_54;
      goto LABEL_51;
    }
  }
  v28 = *a2;
  v29 = v63;
  v72 = *a2;
  v30 = v63 + 4;
  if ( !BYTE4(v63[6].lpVtbl) )
  {
    *(struct _GUID *)v66 = v28;
    v33 = v63 + 5;
LABEL_37:
    v34 = 0;
    lpVtbl = (int)v33->lpVtbl;
    while ( 1 )
    {
      if ( v34 >= lpVtbl )
        goto LABEL_110;
      if ( v34 < 0 )
        goto LABEL_159;
      v36 = *((_QWORD *)&v30->lpVtbl->QueryInterface + 2 * v34);
      for ( i = 0; ; ++i )
      {
        if ( i >= *(_DWORD *)(v36 + 8) )
          goto LABEL_123;
        j = *(_QWORD *)v36 + 16LL * i;
        v20 = *(_QWORD *)j - *(_QWORD *)&v72.Data1;
        if ( *(_QWORD *)j == *(_QWORD *)&v72.Data1 )
          v20 = *(_QWORD *)(j + 8) - *(_QWORD *)v72.Data4;
        if ( !v20 )
          break;
      }
      if ( i != -1 )
        break;
LABEL_123:
      ++v34;
    }
    if ( v34 >= SLODWORD(v30[1].lpVtbl) )
    {
LABEL_159:
      RaiseException(0xC000008C, 1u, 0, 0);
      __debugbreak();
    }
    if ( !v36 )
      goto LABEL_54;
LABEL_50:
    v38 = a3;
LABEL_51:
    if ( (unsigned __int64)(int)a3 < *(_QWORD *)(v25 + 1440) )
    {
      v71 = *a2;
      InitializedSystemEffectInterface = EffectPack::GetInitializedSystemEffectInterface(
                                           v25,
                                           v24 + *(_QWORD *)(v25 + 1448),
                                           1,
                                           0,
                                           &v71,
                                           0,
                                           0,
                                           v38,
                                           0,
                                           &v65,
                                           0);
      goto LABEL_53;
    }
    goto LABEL_163;
  }
  *(struct _GUID *)v66 = v28;
  v31 = 0;
  v32 = v63 + 5;
  v69 = v63 + 5;
  while ( 1 )
  {
    LODWORD(ppIAudioMediaType) = v31;
    if ( v31 >= SLODWORD(v32->lpVtbl) )
      goto LABEL_36;
    if ( v31 < 0 )
      goto LABEL_159;
    v30 = v29 + 4;
    v68 = v29 + 4;
    if ( *(_BYTE *)(*((_QWORD *)&v29[4].lpVtbl->QueryInterface + 2 * v31) + 20LL) )
      break;
LABEL_34:
    ++v31;
    v29 = v63;
  }
  v58 = (_QWORD *)ATL::CSimpleArray<std::shared_ptr<SystemEffectChainDescriptor>,ATL::CSimpleArrayEqualHelper<std::shared_ptr<SystemEffectChainDescriptor>>>::operator[](v30);
  if ( (unsigned int)ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::Find(*v58, &v72) == -1 )
  {
    v31 = (int)ppIAudioMediaType;
    v32 = v69;
    v30 = v68;
    goto LABEL_34;
  }
  lpCriticalSection = (LPCRITICAL_SECTION)&v63[7];
  EnterCriticalSection((LPCRITICAL_SECTION)&v63[7]);
  v75 = v63 + 7;
  v59 = ATL::CSimpleArray<std::shared_ptr<SystemEffectChainDescriptor>,ATL::CSimpleArrayEqualHelper<std::shared_ptr<SystemEffectChainDescriptor>>>::operator[](v68);
  v60 = *(_QWORD *)(v59 + 8);
  if ( v60 )
    _InterlockedIncrement((volatile signed __int32 *)(v60 + 8));
  *(_QWORD *)&v71.Data1 = *(_QWORD *)v59;
  ppIAudioMediaType = *(IAudioMediaType **)(v59 + 8);
  *(_QWORD *)v71.Data4 = ppIAudioMediaType;
  if ( (int)SystemEffectChainDescriptor::Resolve(
              *(SystemEffectChainDescriptor **)&v71.Data1,
              (struct SystemEffectDescriptor *)v63) >= 0 )
  {
    if ( ppIAudioMediaType )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)ppIAudioMediaType);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v30 = v68;
LABEL_36:
    v33 = v69;
    goto LABEL_37;
  }
  if ( ppIAudioMediaType )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)ppIAudioMediaType);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
LABEL_110:
  v56 = v63[2].lpVtbl;
  if ( v56 )
  {
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (int)j >= SLODWORD(v56->AddRef) )
        goto LABEL_54;
      v20 = (__int64)v56->QueryInterface + 16 * (int)j;
      v57 = *(_QWORD *)v20 - (unsigned __int64)v66[0];
      if ( *(struct tWAVEFORMATEX **)v20 == v66[0] )
        v57 = *(_QWORD *)(v20 + 8) - (unsigned __int64)v66[1];
      if ( !v57 )
        break;
    }
    if ( (_DWORD)j != -1 )
      goto LABEL_50;
  }
LABEL_54:
  if ( v27 >= 0 )
  {
    if ( v8 )
    {
      ppIAudioMediaType = 0;
      v63 = 0;
      v64 = 0;
      v27 = CreateAudioMediaType((const WAVEFORMATEX *)v9, v9[8] + 18, &ppIAudioMediaType);
      if ( v27 < 0 )
      {
        if ( v64 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
        if ( v63 )
          ((void (__fastcall *)(IAudioMediaType *))v63->lpVtbl->Release)(v63);
        if ( ppIAudioMediaType )
          ((void (__fastcall *)(IAudioMediaType *))ppIAudioMediaType->lpVtbl->Release)(ppIAudioMediaType);
      }
      else
      {
        v27 = CreateAudioMediaType((const WAVEFORMATEX *)v13, *((unsigned __int16 *)v13 + 8) + 18, &v63);
        if ( v27 < 0 )
        {
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v64);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v63);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
        }
        else
        {
          v40 = (CEndpointCharacteristics **)a1;
          v41 = (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 56LL))(*(_QWORD *)a1) == 0;
          v42 = *v8;
          if ( v41 )
            v43 = (*(__int64 (__fastcall **)(__int64 *, IAudioMediaType *, IAudioMediaType *, __int64 *))(v42 + 56))(
                    v8,
                    ppIAudioMediaType,
                    v63,
                    &v64);
          else
            v43 = (*(__int64 (__fastcall **)(__int64 *, IAudioMediaType *, IAudioMediaType *, __int64 *))(v42 + 64))(
                    v8,
                    ppIAudioMediaType,
                    v63,
                    &v64);
          v27 = v43;
          if ( v43 < 0 )
          {
            if ( v64 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
            if ( v63 )
              ((void (__fastcall *)(IAudioMediaType *))v63->lpVtbl->Release)(v63);
            if ( ppIAudioMediaType )
              ((void (__fastcall *)(IAudioMediaType *))ppIAudioMediaType->lpVtbl->Release)(ppIAudioMediaType);
          }
          else
          {
            if ( v43 == 1 || ValidateWaveFormatEx(Src) )
              v27 = 1;
            if ( v64 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
            if ( v63 )
              ((void (__fastcall *)(IAudioMediaType *))v63->lpVtbl->Release)(v63);
            if ( ppIAudioMediaType )
              ((void (__fastcall *)(IAudioMediaType *))ppIAudioMediaType->lpVtbl->Release)(ppIAudioMediaType);
LABEL_69:
            v44 = a6;
            if ( a6 && v27 )
            {
              Src = 0;
              v66[0] = (struct tWAVEFORMATEX *)&Src;
              v66[1] = 0;
              v67 = 1;
              LODWORD(ppIAudioMediaType) = 1;
              v71 = *a2;
              v46 = CEndpointCharacteristics::TryGetOverridingMixFormat(*v40, a3, &v71, &v66[1]) >= 0 && Src;
              if ( v67 )
              {
                v47 = *(void **)v66[0];
                *(_QWORD *)v66[0] = v66[1];
                if ( v47 )
                  CoTaskMemFree(v47);
              }
              v48 = a4;
              if ( v46 )
                v48 = Src;
              v49 = v48->cbSize;
              v50 = (struct tWAVEFORMATEX *)operator new[](v49 + 18, (const struct std::nothrow_t *)&std::nothrow);
              *v44 = v50;
              if ( v50 )
              {
                memcpy_0(v50, v48, v49 + 18);
                v27 = 1;
              }
              else
              {
                v27 = -2147024882;
              }
              v51 = Src;
              Src = 0;
              if ( v51 )
                CoTaskMemFree(v51);
            }
          }
        }
      }
    }
    else if ( (unsigned int)ValidateUncompressedWaveFormatEx((const struct tWAVEFORMATEX *)v13) )
    {
      v27 = -2004287480;
    }
    else
    {
      if ( *((_DWORD *)v13 + 1) != *((_DWORD *)v9 + 1)
        || *((_WORD *)v13 + 1) != v9[1]
        || !(_BYTE)v64
        || ValidateWaveFormatEx(Src) )
      {
        v27 = 1;
        v40 = (CEndpointCharacteristics **)a1;
        goto LABEL_69;
      }
      v27 = 0;
    }
  }
LABEL_70:
  CoTaskMemFree(v9);
  CoTaskMemFree(v13);
  if ( v8 )
    (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x180021620  mov     rax, rsp
0x180021623  mov     [rax+20h], r9
0x180021627  mov     [rax+18h], r8d
0x18002162b  mov     [rax+10h], rdx
0x18002162f  mov     [rax+8], rcx
0x180021633  push    rbp
0x180021634  push    rbx
0x180021635  push    rsi
0x180021636  push    rdi
0x180021637  push    r12
0x180021639  push    r13
0x18002163b  push    r14
0x18002163d  push    r15
0x18002163f  lea     rbp, [rax-58h]
0x180021643  sub     rsp, 118h
0x18002164a  movaps  xmmword ptr [rax-58h], xmm6
0x18002164e  mov     r12, r9
0x180021651  mov     r13, rcx
0x180021654  xor     ecx, ecx
0x180021656  mov     dword ptr [rsp+150h+ppIAudioMediaType], ecx
0x18002165a  mov     esi, ecx
0x18002165c  mov     [rsp+150h+var_D8], rcx
0x180021661  mov     rax, [rbp+50h+arg_28]
0x180021668  test    rax, rax
0x18002166b  jz      short loc_180021670
0x18002166d  mov     [rax], rcx
0x180021670  mov     rdi, rcx
0x180021673  mov     r15, [rbp+50h+Src]
0x18002167a  movzx   r14d, word ptr [r15+10h]
0x18002167f  lea     rcx, [r14+12h]; cb
0x180021683  call    cs:__imp_CoTaskMemAlloc
0x180021689  mov     rbx, rax
0x18002168c  test    rax, rax
0x18002168f  jz      loc_180021E70
0x180021695  lea     r8, [r14+12h]; Size
0x180021699  mov     rdx, r15; Src
0x18002169c  mov     rcx, rax; void *
0x18002169f  call    memcpy_0
0x1800216a4  mov     [rbp+50h+var_70], rbx
0x1800216a8  movzx   r14d, word ptr [r12+10h]
0x1800216ae  lea     rcx, [r14+12h]; cb
0x1800216b2  call    cs:__imp_CoTaskMemAlloc
0x1800216b8  mov     rdi, rax
0x1800216bb  test    rax, rax
0x1800216be  jz      loc_180021FD6
0x1800216c4  lea     r8, [r14+12h]; Size
0x1800216c8  mov     rdx, r12; Src
0x1800216cb  mov     rcx, rax; void *
0x1800216ce  call    memcpy_0
0x1800216d3  mov     [rbp+50h+var_68], rdi
0x1800216d7  movzx   eax, word ptr [rbx+0Eh]
0x1800216db  mov     ecx, 0FFF8h
0x1800216e0  and     ax, cx
0x1800216e3  mov     ecx, 100h
0x1800216e8  cmp     cx, ax
0x1800216eb  jb      loc_180022094
0x1800216f1  movzx   eax, word ptr [rbx]
0x1800216f4  mov     esi, 1
0x1800216f9  mov     r9d, 0FFFEh
0x1800216ff  mov     r10d, 20h ; ' '
0x180021705  mov     r11d, 3
0x18002170b  cmp     r9w, ax
0x18002170f  jz      loc_180021CC9
0x180021715  movzx   r8d, sil
0x180021719  mov     dword ptr [rsp+150h+var_E0], r8d
0x18002171e  cmp     si, ax
0x180021721  jz      loc_180021E51
0x180021727  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data1
0x18002172e  mov     rdx, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data4
0x180021735  movzx   ecx, word ptr [rdi]
0x180021738  cmp     si, cx
0x18002173b  jz      loc_180021E5A
0x180021741  cmp     r9w, cx
0x180021745  jnz     short loc_18002178E
0x180021747  sub     rax, [rdi+18h]
0x18002174b  jnz     short loc_180021754
0x18002174d  mov     rax, rdx
0x180021750  sub     rax, [rdi+20h]
0x180021754  test    rax, rax
0x180021757  jnz     short loc_18002178E
0x180021759  test    byte ptr [rdi+12h], 7
0x18002175d  jnz     loc_180021E7D
0x180021763  movups  xmm0, xmmword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1
0x18002176a  movups  xmmword ptr [rdi+18h], xmm0
0x18002176e  mov     [rdi+12h], r10w
0x180021773  mov     [rdi+0Eh], r10w
0x180021778  movzx   eax, word ptr [rdi+2]
0x18002177c  shl     ax, 2
0x180021780  movzx   ecx, ax
0x180021783  mov     [rdi+0Ch], cx
0x180021787  imul    ecx, [rdi+4]
0x18002178b  mov     [rdi+8], ecx
0x18002178e  mov     rsi, [r13+8]
0x180021792  movsxd  r15, [rbp+50h+arg_10]
0x180021796  mov     r14, r15
0x180021799  cmp     r15, [rsi+5A0h]
0x1800217a0  jnb     loc_1800220CF
0x1800217a6  lea     r12, [r15+r15*2]
0x1800217aa  shl     r12, 5
0x1800217ae  mov     rcx, [rsi+5A8h]
0x1800217b5  add     rcx, r12; this
0x1800217b8  call    ?ResolveAllOverridingChains@SystemEffectDescriptor@@QEAAJXZ; SystemEffectDescriptor::ResolveAllOverridingChains(void)
0x1800217bd  cmp     r15, [rsi+5B0h]
0x1800217c4  jnb     loc_1800220CF
0x1800217ca  mov     rcx, [rsi+5B8h]
0x1800217d1  add     rcx, r12; this
0x1800217d4  call    ?ResolveAllOverridingChains@SystemEffectDescriptor@@QEAAJXZ; SystemEffectDescriptor::ResolveAllOverridingChains(void)
0x1800217d9  cmp     r15, [rsi+5C0h]
0x1800217e0  jnb     loc_1800220CF
0x1800217e6  mov     rcx, [rsi+5C8h]
0x1800217ed  add     rcx, r12; this
0x1800217f0  call    ?ResolveAllOverridingChains@SystemEffectDescriptor@@QEAAJXZ; SystemEffectDescriptor::ResolveAllOverridingChains(void)
0x1800217f5  cmp     r15, [rsi+650h]
0x1800217fc  jnb     loc_1800220CF
0x180021802  mov     r13, [r13+8]
0x180021806  mov     rax, [rsi+658h]
0x18002180d  xor     esi, esi
0x18002180f  mov     [rsp+150h+var_D8], rsi
0x180021814  cmp     [rax+r15*4], esi
0x180021818  jz      loc_180021DB8
0x18002181e  cmp     r15, [r13+5A0h]
0x180021825  jnb     loc_1800220CF
0x18002182b  mov     rcx, [r13+5A8h]
0x180021832  add     rcx, r12; this
0x180021835  call    ?ResolveAllOverridingChains@SystemEffectDescriptor@@QEAAJXZ; SystemEffectDescriptor::ResolveAllOverridingChains(void)
0x18002183a  cmp     r15, [r13+5B0h]
0x180021841  jnb     loc_1800220CF
0x180021847  mov     rcx, [r13+5B8h]
0x18002184e  add     rcx, r12; this
0x180021851  call    ?ResolveAllOverridingChains@SystemEffectDescriptor@@QEAAJXZ; SystemEffectDescriptor::ResolveAllOverridingChains(void)
0x180021856  cmp     r15, [r13+5C0h]
0x18002185d  jnb     loc_1800220CF
0x180021863  mov     rcx, [r13+5C8h]
0x18002186a  add     rcx, r12; this
0x18002186d  call    ?ResolveAllOverridingChains@SystemEffectDescriptor@@QEAAJXZ; SystemEffectDescriptor::ResolveAllOverridingChains(void)
0x180021872  cmp     r15, [r13+650h]
0x180021879  jnb     loc_1800220CF
0x18002187f  xor     r15d, r15d
0x180021882  mov     rax, [r13+658h]
0x180021889  cmp     [rax+r14*4], esi
0x18002188d  jz      loc_180021A1E
0x180021893  cmp     r14, [r13+5A0h]
0x18002189a  jnb     loc_1800220CF
0x1800218a0  lea     rax, [r14+r14*2]
0x1800218a4  shl     rax, 5
0x1800218a8  add     rax, [r13+5A8h]
0x1800218af  mov     [rsp+150h+var_E8], rax
0x1800218b4  mov     rcx, [r13+630h]; this
0x1800218bb  call    ?AreEnhancementsEnabled@CEndpointCharacteristics@@QEAAHXZ; CEndpointCharacteristics::AreEnhancementsEnabled(void)
0x1800218c0  test    eax, eax
0x1800218c2  jz      loc_180021D44
0x1800218c8  mov     rcx, [rbp+50h+arg_8]
0x1800218cc  movaps  xmm0, xmmword ptr [rcx]
0x1800218cf  mov     rax, [rsp+150h+var_E8]
0x1800218d4  movdqa  [rbp+50h+var_80], xmm0
0x1800218d9  lea     r10, [rax+20h]
0x1800218dd  cmp     [rax+34h], sil
0x1800218e1  jz      loc_180021DAA
0x1800218e7  movaps  xmmword ptr [rbp+50h+var_D0], xmm0
0x1800218eb  xor     edx, edx
0x1800218ed  lea     r8, [rax+28h]
0x1800218f1  mov     [rbp+50h+var_A8], r8
0x1800218f5  mov     dword ptr [rsp+150h+ppIAudioMediaType], edx
0x1800218f9  cmp     edx, [r8]
0x1800218fc  jge     short loc_180021932
0x1800218fe  test    edx, edx
0x180021900  js      loc_18002207D
0x180021906  lea     r10, [rax+20h]
0x18002190a  mov     [rbp+50h+var_B0], r10
0x18002190e  movsxd  rcx, edx
0x180021911  add     rcx, rcx
0x180021914  mov     rax, [r10]
0x180021917  mov     rcx, [rax+rcx*8]
0x18002191b  cmp     [rcx+14h], sil
0x18002191f  jnz     loc_180021EE3
0x180021925  inc     edx
0x180021927  mov     rax, [rsp+150h+var_E8]
0x18002192c  jmp     short loc_1800218F5
0x18002192e  mov     r10, [rbp+50h+var_B0]
0x180021932  mov     rcx, [rbp+50h+var_A8]
0x180021936  xor     r8d, r8d
0x180021939  mov     r11d, [rcx]
0x18002193c  cmp     r8d, r11d
0x18002193f  jge     loc_180021DD3
0x180021945  test    r8d, r8d
0x180021948  js      loc_18002207D
0x18002194e  movsxd  rcx, r8d
0x180021951  add     rcx, rcx
0x180021954  mov     rax, [r10]
0x180021957  mov     r9, [rax+rcx*8]
0x18002195b  xor     eax, eax
0x18002195d  cmp     eax, [r9+8]
0x180021961  jge     loc_180021E68
0x180021967  movsxd  rdx, eax
0x18002196a  shl     rdx, 4
0x18002196e  add     rdx, [r9]
0x180021971  mov     rcx, [rdx]
0x180021974  sub     rcx, qword ptr [rbp+50h+var_80]
0x180021978  jnz     short loc_180021982
0x18002197a  mov     rcx, [rdx+8]
0x18002197e  sub     rcx, qword ptr [rbp+50h+var_80+8]
0x180021982  test    rcx, rcx
0x180021985  jnz     loc_180021BD9
0x18002198b  cmp     eax, 0FFFFFFFFh
0x18002198e  jz      loc_180021E68
0x180021994  cmp     r8d, [r10+8]
0x180021998  jge     loc_18002207D
0x18002199e  mov     eax, dword ptr [rsp+150h+var_E0]
0x1800219a2  mov     dword ptr [rsp+150h+var_E0], eax
0x1800219a6  test    r9, r9
0x1800219a9  jz      short loc_180021A1E
0x1800219ab  jmp     short loc_1800219B2
0x1800219ad  cmp     edx, 0FFFFFFFFh
0x1800219b0  jz      short loc_180021A1E
0x1800219b2  mov     r11d, [rbp+50h+arg_10]
0x1800219b6  cmp     r14, [r13+5A0h]
0x1800219bd  jnb     loc_1800220CF
0x1800219c3  mov     rax, [rbp+50h+arg_8]
0x1800219c7  movaps  xmm0, xmmword ptr [rax]
0x1800219ca  movdqa  xmmword ptr [rbp+50h+var_90.Data1], xmm0
0x1800219cf  mov     rdx, [r13+5A8h]
0x1800219d6  add     rdx, r12
0x1800219d9  xor     ecx, ecx
0x1800219db  mov     [rsp+50h], rcx
0x1800219e0  lea     rax, [rsp+150h+var_D8]
0x1800219e5  mov     [rsp+150h+var_108], rax
0x1800219ea  mov     [rsp+150h+var_110], rcx
0x1800219ef  mov     dword ptr [rsp+150h+var_118], r11d
0x1800219f4  mov     [rsp+150h+var_120], ecx
0x1800219f8  mov     [rsp+150h+var_128], ecx
0x1800219fc  lea     rax, [rbp+50h+var_90]
0x180021a00  mov     qword ptr [rsp+150h+var_130], rax
0x180021a05  xor     r9d, r9d
0x180021a08  mov     r8d, 1
0x180021a0e  mov     rcx, r13
0x180021a11  call    ?GetInitializedSystemEffectInterface@EffectPack@@QEAAJPEAVSystemEffectDescriptor@@W4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@W4SystemEffectPosition@@U_GUID@@HHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetInitializedSystemEffectInterface(SystemEffectDescriptor *,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,SystemEffectPosition,_GUID,int,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180021a16  mov     rsi, [rsp+150h+var_D8]
0x180021a1b  mov     r15d, eax
0x180021a1e  test    r15d, r15d
0x180021a21  js      loc_180021B40
0x180021a27  test    rsi, rsi
0x180021a2a  jz      loc_180021B88
0x180021a30  mov     [rsp+150h+ppIAudioMediaType], 0
0x180021a39  mov     [rsp+150h+var_E8], 0
0x180021a42  mov     [rsp+150h+var_E0], 0
0x180021a4b  movzx   edx, word ptr [rdi+10h]
0x180021a4f  add     edx, 12h; cbAudioFormatSize
0x180021a52  lea     r8, [rsp+150h+ppIAudioMediaType]; ppIAudioMediaType
0x180021a57  mov     rcx, rdi; pAudioFormat
0x180021a5a  call    CreateAudioMediaType
0x180021a5f  mov     r15d, eax
0x180021a62  test    eax, eax
0x180021a64  js      loc_180021F8C
0x180021a6a  movzx   edx, word ptr [rbx+10h]
0x180021a6e  add     edx, 12h; cbAudioFormatSize
0x180021a71  lea     r8, [rsp+150h+var_E8]; ppIAudioMediaType
0x180021a76  mov     rcx, rbx; pAudioFormat
0x180021a79  call    CreateAudioMediaType
0x180021a7e  mov     r15d, eax
0x180021a81  test    eax, eax
0x180021a83  js      loc_18002209F
0x180021a89  mov     r12, [rbp+50h+arg_0]
0x180021a8d  mov     rcx, [r12]
0x180021a91  mov     rax, [rcx]
0x180021a94  mov     rax, [rax+38h]
0x180021a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a9d  lea     r9, [rsp+150h+var_E0]
0x180021aa2  mov     r8, [rsp+150h+var_E8]
0x180021aa7  mov     rdx, [rsp+150h+ppIAudioMediaType]
0x180021aac  mov     rcx, rsi
0x180021aaf  test    eax, eax
0x180021ab1  mov     rax, [rsi]
0x180021ab4  jnz     loc_180021E48
0x180021aba  mov     rax, [rax+38h]
0x180021abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ac3  mov     r15d, eax
0x180021ac6  test    eax, eax
0x180021ac8  js      loc_180021E8F
0x180021ace  cmp     eax, 1
0x180021ad1  jz      loc_180021E31
0x180021ad7  mov     rcx, [rbp+50h+Src]; struct tWAVEFORMATEX *
0x180021ade  call    ?ValidateWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateWaveFormatEx(tWAVEFORMATEX const *)
0x180021ae3  test    eax, eax
0x180021ae5  jnz     loc_180021E31
0x180021aeb  mov     rcx, [rsp+150h+var_E0]
0x180021af0  test    rcx, rcx
0x180021af3  jz      short loc_180021B02
0x180021af5  mov     rax, [rcx]
0x180021af8  mov     rax, [rax+10h]
0x180021afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b01  nop
0x180021b02  mov     rcx, [rsp+150h+var_E8]
0x180021b07  test    rcx, rcx
0x180021b0a  jz      short loc_180021B19
0x180021b0c  mov     rax, [rcx]
0x180021b0f  mov     rax, [rax+10h]
0x180021b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b18  nop
0x180021b19  mov     rcx, [rsp+150h+ppIAudioMediaType]
0x180021b1e  test    rcx, rcx
  ... truncated ...
```
