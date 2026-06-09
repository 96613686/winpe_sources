# EffectPack::DeriveDevicePipeFormatFromConnectorFormat(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioMediaType *,IAudioMediaType * *)

- ea: `0x18003f11c`
- end: `0x18003f6c4`
- name: `?DeriveDevicePipeFormatFromConnectorFormat@EffectPack@@QEAAJU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIAudioMediaType@@PEAPEAU4@@Z`
- size: `1448`
- prototype: `__int64 __usercall@<rax>(EffectPack *__hidden this@<rcx>, struct _GUID *__struct_ptr@<rdx>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@<r8d>, struct IAudioMediaType *@<r9>, struct IAudioMediaType **)`
- caller_count: `5`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001eb4c`
- `0x18001fa40`
- `0x18003f6cc`
- `0x1800c80e0`
- `0x180123220`

## callees

- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x180020598`
- `0x180020f74`
- `0x180022fb0`
- `0x1800393b0`
- `0x18003cee0`
- `0x18003ef48`
- `0x18003f11c`
- `0x1800423cc`
- `0x18005b174`
- `0x180068bd8`
- `0x180069ce4`
- `0x1800cf8c0`
- `0x1800d2588`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f40f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f40f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f496`

## string_xrefs

- `0x18003f175`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f1ee`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f242`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f2a4`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f34d`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f3ec`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f44d`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f501`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f5f4`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall EffectPack::DeriveDevicePipeFormatFromConnectorFormat(
        EffectPack *this,
        struct _GUID *a2,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a3,
        struct IAudioMediaType *a4,
        struct IAudioMediaType **a5)
{
  const struct tWAVEFORMATEX *v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  int EndpointEffect; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  struct IAudioProcessingObject *v15; // rbx
  HRESULT (__stdcall *IsOutputFormatSupported)(IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, IAudioMediaType **); // rdi
  struct IAudioMediaType **v17; // rcx
  int v18; // edi
  HRESULT v19; // eax
  HRESULT v20; // edi
  const struct tWAVEFORMATEX *v21; // rax
  int v22; // edi
  void *v23; // rcx
  HRESULT v24; // eax
  void *v25; // rcx
  void *v26; // rcx
  bool v27; // zf
  struct IAudioProcessingObjectVtbl *lpVtbl; // rax
  HRESULT (__stdcall *IsInputFormatSupported)(IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, IAudioMediaType **); // rdi
  __int64 v30; // rdx
  HRESULT (__stdcall *v31)(IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, IAudioMediaType **); // rdi
  struct IAudioMediaType *v32; // rdi
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // rdx
  const struct tWAVEFORMATEX *v36; // rax
  __int64 v37; // rbx
  struct IAudioProcessingObject **v38; // [rsp+20h] [rbp-61h]
  int v39; // [rsp+20h] [rbp-61h]
  IAudioMediaType *v40; // [rsp+30h] [rbp-51h] BYREF
  IAudioMediaType *ppIAudioMediaType; // [rsp+38h] [rbp-49h] BYREF
  __int64 v42; // [rsp+40h] [rbp-41h] BYREF
  struct IAudioMediaType *v43; // [rsp+48h] [rbp-39h] BYREF
  int v44; // [rsp+50h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-29h] BYREF
  struct IAudioProcessingObject *v46; // [rsp+60h] [rbp-21h] BYREF
  __int64 v47; // [rsp+68h] [rbp-19h] BYREF
  WAVEFORMATEX pAudioFormat; // [rsp+70h] [rbp-11h] BYREF
  _WORD v49[11]; // [rsp+82h] [rbp+1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v8 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(struct IAudioMediaType *, struct _GUID *))a4->lpVtbl->GetAudioFormat)(
                                       a4,
                                       a2);
  v9 = ValidateUncompressedWaveFormatEx(v8);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E36,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v9,
      (int)v38);
    return v10;
  }
  v46 = 0;
  if ( (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(this, a3) )
  {
    v46 = 0;
    EndpointEffect = EffectPack::GetEndpointEffect(this, 0, a3, 0, &v46, 0);
    v13 = EndpointEffect;
    if ( EndpointEffect < 0 )
    {
      v14 = 7744;
      goto LABEL_8;
    }
LABEL_9:
    ppIAudioMediaType = 0;
    v40 = 0;
    v15 = v46;
    if ( v10 == 1 )
    {
      memset(&pAudioFormat, 0, sizeof(pAudioFormat));
      memset(v49, 0, sizeof(v49));
      if ( !v46 )
      {
        v13 = -2004287480;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E4B,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x88890008LL,
          v39);
LABEL_12:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
        goto LABEL_54;
      }
      v47 = 0;
      IsOutputFormatSupported = v46->lpVtbl->IsOutputFormatSupported;
      wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v47);
      if ( ((unsigned int (__fastcall *)(struct IAudioProcessingObject *, _QWORD, struct IAudioMediaType *, __int64 *))IsOutputFormatSupported)(
             v15,
             0,
             a4,
             &v47) )
      {
        v13 = -2004287480;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E4F,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x88890008LL,
          v39);
        v17 = (struct IAudioMediaType **)&v47;
LABEL_15:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v17);
        goto LABEL_12;
      }
      *(_DWORD *)&pAudioFormat.wFormatTag = 196606;
      pAudioFormat.nSamplesPerSec = *(_DWORD *)(((__int64 (__fastcall *)(struct IAudioMediaType *))a4->lpVtbl->GetAudioFormat)(a4)
                                              + 4);
      v18 = (unsigned __int16)(4 * pAudioFormat.nChannels);
      pAudioFormat.nBlockAlign = 4 * pAudioFormat.nChannels;
      pAudioFormat.nAvgBytesPerSec = *(_DWORD *)(((__int64 (__fastcall *)(struct IAudioMediaType *))a4->lpVtbl->GetAudioFormat)(a4)
                                               + 4)
                                   * v18;
      *(_DWORD *)&pAudioFormat.wBitsPerSample = 1441824;
      strcpy((char *)v49, " ");
      *(_DWORD *)&v49[1] = 3;
      *(GUID *)&v49[3] = GUID_00000003_0000_0010_8000_00aa00389b71;
      wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&ppIAudioMediaType);
      v19 = CreateAudioMediaType(&pAudioFormat, 0x28u, &ppIAudioMediaType);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E60,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v19,
          v39);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
LABEL_18:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
        v13 = v20;
        goto LABEL_54;
      }
      wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(&v40, a4);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
    }
    else
    {
      pv = 0;
      *(_QWORD *)&pAudioFormat.wFormatTag = &pv;
      *(_QWORD *)&pAudioFormat.nAvgBytesPerSec = 0;
      LOBYTE(pAudioFormat.cbSize) = 1;
      v21 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(struct IAudioMediaType *))a4->lpVtbl->GetAudioFormat)(a4);
      v22 = CloneWaveFormat(v21, (struct tWAVEFORMATEX **)&pAudioFormat.nAvgBytesPerSec);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&pAudioFormat);
      if ( v22 < 0 )
      {
        v13 = -2004287480;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E68,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x88890008LL,
          v39);
        v23 = pv;
        pv = 0;
        if ( v23 )
          CoTaskMemFree(v23);
        goto LABEL_12;
      }
      ConvertPCMWfxToIEEEFloat((struct tWAVEFORMATEX *)pv);
      wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v40);
      v24 = CreateAudioMediaType((const WAVEFORMATEX *)pv, *((unsigned __int16 *)pv + 8) + 18, &v40);
      v20 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E6D,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v24,
          v39);
        v25 = pv;
        pv = 0;
        if ( v25 )
          CoTaskMemFree(v25);
        goto LABEL_18;
      }
      wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(&ppIAudioMediaType, v40);
      v26 = pv;
      pv = 0;
      if ( v26 )
        CoTaskMemFree(v26);
    }
    v43 = 0;
    if ( v15 )
    {
      v44 = 0;
      v42 = 0;
      v27 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 198) + 56LL))(*((_QWORD *)this + 198)) == 0;
      lpVtbl = v15->lpVtbl;
      if ( v27 )
      {
        IsInputFormatSupported = lpVtbl->IsInputFormatSupported;
        wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v42);
        if ( ((int (__fastcall *)(struct IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, __int64 *))IsInputFormatSupported)(
               v15,
               v40,
               ppIAudioMediaType,
               &v42) < 0 )
        {
          v30 = 7804;
LABEL_32:
          v13 = -2004287480;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)0x88890008LL,
            v39);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
LABEL_33:
          v17 = &v43;
          goto LABEL_15;
        }
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 24LL))(v42, &v44) < 0 )
        {
          v30 = 7805;
          goto LABEL_32;
        }
        if ( v44 )
        {
          v30 = 7806;
          goto LABEL_32;
        }
      }
      else
      {
        v31 = lpVtbl->IsOutputFormatSupported;
        wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v42);
        if ( ((int (__fastcall *)(struct IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, __int64 *))v31)(
               v15,
               v40,
               ppIAudioMediaType,
               &v42) < 0 )
        {
          v30 = 7811;
          goto LABEL_32;
        }
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 24LL))(v42, &v44) < 0 )
        {
          v30 = 7813;
          goto LABEL_32;
        }
        if ( v44 )
        {
          v30 = 7814;
          goto LABEL_32;
        }
      }
      wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(&v43, v42);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
    }
    else
    {
      wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(&v43, ppIAudioMediaType);
    }
    v32 = v43;
    v33 = ValidateAPOInputFormat(v43);
    v13 = v33;
    if ( v33 >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 198) + 56LL))(*((_QWORD *)this + 198))
        || (v36 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(IAudioMediaType *))v40->lpVtbl->GetAudioFormat)(v40),
            IsCompressedSpatialFormat(v36))
        || (v37 = ((__int64 (__fastcall *)(struct IAudioMediaType *))v32->lpVtbl->GetAudioFormat)(v32),
            *(_DWORD *)(v37 + 4) == *(_DWORD *)(((__int64 (__fastcall *)(struct IAudioMediaType *))a4->lpVtbl->GetAudioFormat)(a4)
                                              + 4)) )
      {
        v43 = 0;
        *a5 = v32;
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
        v13 = 0;
        goto LABEL_54;
      }
      v13 = -2004287480;
      v34 = 2290679816LL;
      v35 = 7831;
    }
    else
    {
      v34 = (unsigned int)v33;
      v35 = 7824;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v34,
      v39);
    goto LABEL_33;
  }
  v46 = 0;
  EndpointEffect = EffectPack::GetGfx(this, a3, 0, &v46, (struct IAudioSystemEffects2 **)v38);
  v13 = EndpointEffect;
  if ( EndpointEffect >= 0 )
    goto LABEL_9;
  v14 = 7740;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
    (const char *)(unsigned int)EndpointEffect,
    v39);
LABEL_54:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
  return v13;
}

```

## disassembly

```asm
0x18003f11c  push    rbp
0x18003f11e  push    rbx
0x18003f11f  push    rsi
0x18003f120  push    rdi
0x18003f121  push    r12
0x18003f123  push    r14
0x18003f125  push    r15
0x18003f127  lea     rbp, [rsp-1Fh]
0x18003f12c  sub     rsp, 0A0h
0x18003f133  mov     rax, cs:__security_cookie
0x18003f13a  xor     rax, rsp
0x18003f13d  mov     [rbp+4Fh+var_38], rax
0x18003f141  mov     rsi, r9
0x18003f144  mov     ebx, r8d
0x18003f147  mov     r14, rcx
0x18003f14a  mov     r15, [rbp+4Fh+arg_20]
0x18003f14e  mov     rax, [r9]
0x18003f151  mov     rcx, r9
0x18003f154  mov     rax, [rax+28h]
0x18003f158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f15d  mov     rcx, rax; struct tWAVEFORMATEX *
0x18003f160  call    ?ValidateUncompressedWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x18003f165  mov     edi, eax
0x18003f167  xor     r12d, r12d
0x18003f16a  test    eax, eax
0x18003f16c  jns     short loc_18003F18D
0x18003f16e  mov     rcx, [rbp+57h]; this
0x18003f172  mov     r9d, eax; char *
0x18003f175  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f17c  mov     edx, 1E36h; void *
0x18003f181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f186  mov     eax, edi
0x18003f188  jmp     loc_18003F6A6
0x18003f18d  mov     [rbp+4Fh+var_70], r12
0x18003f191  mov     edx, ebx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003f193  mov     rcx, r14; this
0x18003f196  call    ?EndpointConnectorSupportsProcessingModes@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::EndpointConnectorSupportsProcessingModes(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18003f19b  test    eax, eax
0x18003f19d  jnz     short loc_18003F1C1
0x18003f19f  mov     [rbp+4Fh+var_70], r12
0x18003f1a3  lea     r9, [rbp+4Fh+var_70]; struct IAudioProcessingObject **
0x18003f1a7  xor     r8d, r8d; struct ICompositeSystemEffect **
0x18003f1aa  mov     edx, ebx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003f1ac  mov     rcx, r14; this
0x18003f1af  call    ?GetGfx@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetGfx(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x18003f1b4  mov     ebx, eax
0x18003f1b6  test    eax, eax
0x18003f1b8  jns     short loc_18003F206
0x18003f1ba  mov     edx, 1E3Ch
0x18003f1bf  jmp     short loc_18003F1EE
0x18003f1c1  mov     [rbp+4Fh+var_70], r12
0x18003f1c5  mov     [rsp+0D0h+var_A8], r12; struct IAudioSystemEffects2 **
0x18003f1ca  lea     rax, [rbp+4Fh+var_70]
0x18003f1ce  mov     [rsp+0D0h+var_B0], rax; int
0x18003f1d3  xor     r9d, r9d; struct ICompositeSystemEffect **
0x18003f1d6  mov     r8d, ebx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003f1d9  xor     edx, edx; int
0x18003f1db  mov     rcx, r14; this
0x18003f1de  call    ?GetEndpointEffect@EffectPack@@QEAAJHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetEndpointEffect(int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x18003f1e3  mov     ebx, eax
0x18003f1e5  test    eax, eax
0x18003f1e7  jns     short loc_18003F206
0x18003f1e9  mov     edx, 1E40h; void *
0x18003f1ee  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f1f5  mov     r9d, eax; char *
0x18003f1f8  mov     rcx, [rbp+57h]; this
0x18003f1fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f201  jmp     loc_18003F69B
0x18003f206  mov     [rbp+4Fh+ppIAudioMediaType], r12
0x18003f20a  mov     [rbp+4Fh+var_A0], r12
0x18003f20e  mov     rbx, [rbp+4Fh+var_70]
0x18003f212  cmp     edi, 1
0x18003f215  jnz     loc_18003F39E
0x18003f21b  mov     [rbp+4Fh+pAudioFormat.wFormatTag], r12w
0x18003f220  xorps   xmm0, xmm0
0x18003f223  xor     eax, eax
0x18003f225  movups  xmmword ptr [rbp+4Fh+pAudioFormat.nChannels], xmm0
0x18003f229  movups  xmmword ptr [rbp+4Fh+var_4E], xmm0
0x18003f22d  mov     qword ptr [rbp+4Fh+var_4E+0Eh], rax
0x18003f231  test    rbx, rbx
0x18003f234  jnz     short loc_18003F26C
0x18003f236  mov     rcx, [rbp+57h]; this
0x18003f23a  mov     ebx, 88890008h
0x18003f23f  mov     r9d, ebx; char *
0x18003f242  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f249  mov     edx, 1E4Bh; void *
0x18003f24e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f253  nop
0x18003f254  lea     rcx, [rbp+4Fh+var_A0]
0x18003f258  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f25d  nop
0x18003f25e  lea     rcx, [rbp+4Fh+ppIAudioMediaType]
0x18003f262  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f267  jmp     loc_18003F69B
0x18003f26c  mov     [rbp+4Fh+var_68], r12
0x18003f270  mov     rax, [rbx]
0x18003f273  mov     rdi, [rax+40h]
0x18003f277  lea     rcx, [rbp+4Fh+var_68]
0x18003f27b  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f280  lea     r9, [rbp+4Fh+var_68]
0x18003f284  mov     r8, rsi
0x18003f287  xor     edx, edx
0x18003f289  mov     rcx, rbx
0x18003f28c  mov     rax, rdi
0x18003f28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f294  test    eax, eax
0x18003f296  jz      short loc_18003F2C1
0x18003f298  mov     rcx, [rbp+57h]; this
0x18003f29c  mov     ebx, 88890008h
0x18003f2a1  mov     r9d, ebx; char *
0x18003f2a4  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f2ab  mov     edx, 1E4Fh; void *
0x18003f2b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f2b5  nop
0x18003f2b6  lea     rcx, [rbp+4Fh+var_68]
0x18003f2ba  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f2bf  jmp     short loc_18003F254
0x18003f2c1  mov     dword ptr [rbp+4Fh+pAudioFormat.wFormatTag], 2FFFEh
0x18003f2c8  mov     rax, [rsi]
0x18003f2cb  mov     rcx, rsi
0x18003f2ce  mov     rax, [rax+28h]
0x18003f2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2d7  mov     ecx, [rax+4]
0x18003f2da  mov     [rbp+4Fh+pAudioFormat.nSamplesPerSec], ecx
0x18003f2dd  movzx   eax, [rbp+4Fh+pAudioFormat.nChannels]
0x18003f2e1  shl     ax, 2
0x18003f2e5  movzx   edi, ax
0x18003f2e8  mov     [rbp+4Fh+pAudioFormat.nBlockAlign], di
0x18003f2ec  mov     rax, [rsi]
0x18003f2ef  mov     rcx, rsi
0x18003f2f2  mov     rax, [rax+28h]
0x18003f2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2fb  imul    edi, [rax+4]
0x18003f2ff  mov     [rbp+4Fh+pAudioFormat.nAvgBytesPerSec], edi
0x18003f302  mov     ecx, 20h ; ' '
0x18003f307  mov     dword ptr [rbp+4Fh+pAudioFormat.wBitsPerSample], 160020h
0x18003f30e  mov     word ptr [rbp+4Fh+var_4E], cx
0x18003f312  mov     dword ptr [rbp+4Fh+var_4E+2], 3
0x18003f319  movups  xmm0, xmmword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1
0x18003f320  movdqu  xmmword ptr [rbp+4Fh+var_4E+6], xmm0
0x18003f325  lea     rcx, [rbp+4Fh+ppIAudioMediaType]
0x18003f329  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f32e  lea     r8, [rbp+4Fh+ppIAudioMediaType]; ppIAudioMediaType
0x18003f332  mov     edx, 28h ; '('; cbAudioFormatSize
0x18003f337  lea     rcx, [rbp+4Fh+pAudioFormat]; pAudioFormat
0x18003f33b  call    CreateAudioMediaType
0x18003f340  mov     edi, eax
0x18003f342  test    eax, eax
0x18003f344  jns     short loc_18003F383
0x18003f346  mov     rcx, [rbp+57h]; this
0x18003f34a  mov     r9d, eax; char *
0x18003f34d  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f354  mov     edx, 1E60h; void *
0x18003f359  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f35e  nop
0x18003f35f  lea     rcx, [rbp+4Fh+var_68]
0x18003f363  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f368  nop
0x18003f369  lea     rcx, [rbp+4Fh+var_A0]
0x18003f36d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f372  nop
0x18003f373  lea     rcx, [rbp+4Fh+ppIAudioMediaType]
0x18003f377  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f37c  mov     ebx, edi
0x18003f37e  jmp     loc_18003F69B
0x18003f383  mov     rdx, rsi
0x18003f386  lea     rcx, [rbp+4Fh+var_A0]
0x18003f38a  call    ??4?$com_ptr_t@UIAudioMediaType@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIAudioMediaType@@@Z; wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(IAudioMediaType *)
0x18003f38f  nop
0x18003f390  lea     rcx, [rbp+4Fh+var_68]
0x18003f394  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f399  jmp     loc_18003F49C
0x18003f39e  mov     [rbp+4Fh+pv], r12
0x18003f3a2  lea     rax, [rbp+4Fh+pv]
0x18003f3a6  mov     qword ptr [rbp+4Fh+pAudioFormat.wFormatTag], rax
0x18003f3aa  mov     qword ptr [rbp+4Fh+pAudioFormat.nAvgBytesPerSec], r12
0x18003f3ae  mov     byte ptr [rbp+4Fh+pAudioFormat.cbSize], 1
0x18003f3b2  mov     rax, [rsi]
0x18003f3b5  mov     rcx, rsi
0x18003f3b8  mov     rax, [rax+28h]
0x18003f3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3c1  lea     rdx, [rbp+4Fh+pAudioFormat.nAvgBytesPerSec]; struct tWAVEFORMATEX **
0x18003f3c5  mov     rcx, rax; Src
0x18003f3c8  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18003f3cd  mov     edi, eax
0x18003f3cf  lea     rcx, [rbp+4Fh+pAudioFormat]
0x18003f3d3  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003f3d8  shr     edi, 1Fh
0x18003f3db  test    dil, dil
0x18003f3de  jz      short loc_18003F41A
0x18003f3e0  mov     rcx, [rbp+57h]; this
0x18003f3e4  mov     ebx, 88890008h
0x18003f3e9  mov     r9d, ebx; char *
0x18003f3ec  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f3f3  mov     edx, 1E68h; void *
0x18003f3f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f3fd  nop
0x18003f3fe  mov     rcx, [rbp+4Fh+pv]; pv
0x18003f402  mov     [rbp+4Fh+pv], r12
0x18003f406  test    rcx, rcx
0x18003f409  jz      loc_18003F254
0x18003f40f  call    cs:__imp_CoTaskMemFree
0x18003f415  jmp     loc_18003F254
0x18003f41a  mov     rcx, [rbp+4Fh+pv]; struct tWAVEFORMATEX *
0x18003f41e  call    ?ConvertPCMWfxToIEEEFloat@@YAXPEAUtWAVEFORMATEX@@@Z; ConvertPCMWfxToIEEEFloat(tWAVEFORMATEX *)
0x18003f423  lea     rcx, [rbp+4Fh+var_A0]
0x18003f427  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f42c  mov     rcx, [rbp+4Fh+pv]; pAudioFormat
0x18003f430  movzx   edx, word ptr [rcx+10h]
0x18003f434  add     edx, 12h; cbAudioFormatSize
0x18003f437  lea     r8, [rbp+4Fh+var_A0]; ppIAudioMediaType
0x18003f43b  call    CreateAudioMediaType
0x18003f440  mov     edi, eax
0x18003f442  test    eax, eax
0x18003f444  jns     short loc_18003F47B
0x18003f446  mov     rcx, [rbp+57h]; this
0x18003f44a  mov     r9d, eax; char *
0x18003f44d  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f454  mov     edx, 1E6Dh; void *
0x18003f459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f45e  nop
0x18003f45f  mov     rcx, [rbp+4Fh+pv]; pv
0x18003f463  mov     [rbp+4Fh+pv], r12
0x18003f467  test    rcx, rcx
0x18003f46a  jz      loc_18003F369
0x18003f470  call    cs:__imp_CoTaskMemFree
0x18003f476  jmp     loc_18003F369
0x18003f47b  mov     rdx, [rbp+4Fh+var_A0]
0x18003f47f  lea     rcx, [rbp+4Fh+ppIAudioMediaType]
0x18003f483  call    ??4?$com_ptr_t@UIAudioMediaType@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIAudioMediaType@@@Z; wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(IAudioMediaType *)
0x18003f488  nop
0x18003f489  mov     rcx, [rbp+4Fh+pv]; pv
0x18003f48d  mov     [rbp+4Fh+pv], r12
0x18003f491  test    rcx, rcx
0x18003f494  jz      short loc_18003F49C
0x18003f496  call    cs:__imp_CoTaskMemFree
0x18003f49c  mov     [rbp+4Fh+var_88], r12
0x18003f4a0  test    rbx, rbx
0x18003f4a3  jz      loc_18003F5CD
0x18003f4a9  mov     [rbp+4Fh+var_80], r12d
0x18003f4ad  mov     [rbp+4Fh+var_90], r12
0x18003f4b1  mov     rcx, [r14+630h]
0x18003f4b8  mov     rax, [rcx]
0x18003f4bb  mov     rax, [rax+38h]
0x18003f4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4c4  lea     rcx, [rbp+4Fh+var_90]
0x18003f4c8  test    eax, eax
0x18003f4ca  mov     rax, [rbx]
0x18003f4cd  jnz     loc_18003F554
0x18003f4d3  mov     rdi, [rax+38h]
0x18003f4d7  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f4dc  lea     r9, [rbp+4Fh+var_90]
0x18003f4e0  mov     r8, [rbp+4Fh+ppIAudioMediaType]
0x18003f4e4  mov     rdx, [rbp+4Fh+var_A0]
0x18003f4e8  mov     rcx, rbx
0x18003f4eb  mov     rax, rdi
0x18003f4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4f3  test    eax, eax
0x18003f4f5  jns     short loc_18003F528
0x18003f4f7  mov     edx, 1E7Ch; void *
0x18003f4fc  mov     ebx, 88890008h
0x18003f501  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f508  mov     r9d, ebx; char *
0x18003f50b  mov     rcx, [rbp+57h]; this
0x18003f50f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f514  nop
0x18003f515  lea     rcx, [rbp+4Fh+var_90]
0x18003f519  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f51e  nop
0x18003f51f  lea     rcx, [rbp+4Fh+var_88]
0x18003f523  jmp     loc_18003F2BA
0x18003f528  mov     rcx, [rbp+4Fh+var_90]
0x18003f52c  mov     rax, [rcx]
0x18003f52f  lea     rdx, [rbp+4Fh+var_80]
0x18003f533  mov     rax, [rax+18h]
0x18003f537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f53c  test    eax, eax
0x18003f53e  jns     short loc_18003F547
0x18003f540  mov     edx, 1E7Dh
0x18003f545  jmp     short loc_18003F4FC
0x18003f547  cmp     [rbp+4Fh+var_80], r12d
0x18003f54b  jz      short loc_18003F5B4
0x18003f54d  mov     edx, 1E7Eh
0x18003f552  jmp     short loc_18003F4FC
0x18003f554  mov     rdi, [rax+40h]
0x18003f558  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f55d  lea     r9, [rbp+4Fh+var_90]
0x18003f561  mov     r8, [rbp+4Fh+ppIAudioMediaType]
0x18003f565  mov     rdx, [rbp+4Fh+var_A0]
0x18003f569  mov     rcx, rbx
0x18003f56c  mov     rax, rdi
0x18003f56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f574  test    eax, eax
0x18003f576  jns     short loc_18003F582
0x18003f578  mov     edx, 1E83h
0x18003f57d  jmp     loc_18003F4FC
0x18003f582  mov     rcx, [rbp+4Fh+var_90]
0x18003f586  mov     rax, [rcx]
0x18003f589  lea     rdx, [rbp+4Fh+var_80]
0x18003f58d  mov     rax, [rax+18h]
  ... truncated ...
```
