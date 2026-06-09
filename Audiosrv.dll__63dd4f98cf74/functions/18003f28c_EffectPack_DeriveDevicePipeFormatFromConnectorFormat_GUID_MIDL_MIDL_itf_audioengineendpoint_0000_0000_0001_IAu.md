# EffectPack::DeriveDevicePipeFormatFromConnectorFormat(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioMediaType *,IAudioMediaType * *)

- ea: `0x18003f28c`
- end: `0x18003f834`
- name: `?DeriveDevicePipeFormatFromConnectorFormat@EffectPack@@QEAAJU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIAudioMediaType@@PEAPEAU4@@Z`
- size: `1448`
- prototype: `__int64 __usercall@<rax>(EffectPack *__hidden this@<rcx>, struct _GUID *__struct_ptr@<rdx>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@<r8d>, struct IAudioMediaType *@<r9>, struct IAudioMediaType **)`
- caller_count: `5`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ec9c`
- `0x18001fb90`
- `0x18003f83c`
- `0x1800c62f0`
- `0x180123470`

## callees

- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x1800206e8`
- `0x1800210c4`
- `0x180023100`
- `0x180039510`
- `0x18003d040`
- `0x18003f0b8`
- `0x18003f28c`
- `0x1800424ec`
- `0x18005ace4`
- `0x180068748`
- `0x180069854`
- `0x1800cd8d0`
- `0x1800d0598`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f57f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f606`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f57f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f606`

## string_xrefs

- `0x18003f2e5`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f35e`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f3b2`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f414`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f4bd`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f55c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f5bd`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f671`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003f764`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
  __int64 v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  struct IAudioProcessingObject *v16; // rbx
  HRESULT (__stdcall *IsOutputFormatSupported)(IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, IAudioMediaType **); // rdi
  struct IAudioMediaType **v18; // rcx
  int v19; // edi
  __int64 v20; // rdx
  HRESULT v21; // eax
  HRESULT v22; // edi
  const struct tWAVEFORMATEX *v23; // rax
  int v24; // edi
  void *v25; // rcx
  __int64 v26; // rdx
  HRESULT v27; // eax
  void *v28; // rcx
  void *v29; // rcx
  bool v30; // zf
  __int64 v31; // rdx
  struct IAudioProcessingObjectVtbl *lpVtbl; // rax
  HRESULT (__stdcall *IsInputFormatSupported)(IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, IAudioMediaType **); // rdi
  __int64 v34; // rdx
  HRESULT (__stdcall *v35)(IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, IAudioMediaType **); // rdi
  struct IAudioMediaType *v36; // rdi
  int v37; // eax
  __int64 v38; // r9
  __int64 v39; // rdx
  const struct tWAVEFORMATEX *v40; // rax
  __int64 v41; // rbx
  struct IAudioProcessingObject **v42; // [rsp+20h] [rbp-61h]
  int v43; // [rsp+20h] [rbp-61h]
  IAudioMediaType *v44; // [rsp+30h] [rbp-51h] BYREF
  IAudioMediaType *ppIAudioMediaType; // [rsp+38h] [rbp-49h] BYREF
  __int64 v46; // [rsp+40h] [rbp-41h] BYREF
  struct IAudioMediaType *v47; // [rsp+48h] [rbp-39h] BYREF
  int v48; // [rsp+50h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-29h] BYREF
  struct IAudioProcessingObject *v50; // [rsp+60h] [rbp-21h] BYREF
  __int64 v51; // [rsp+68h] [rbp-19h] BYREF
  WAVEFORMATEX pAudioFormat; // [rsp+70h] [rbp-11h] BYREF
  _WORD v53[11]; // [rsp+82h] [rbp+1h] BYREF
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
      (void *)0x1E35,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v9,
      (int)v42);
    return v10;
  }
  v50 = 0;
  if ( (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(this, a3) )
  {
    v50 = 0;
    EndpointEffect = EffectPack::GetEndpointEffect(this, 0, a3, 0, &v50, 0);
    v14 = EndpointEffect;
    if ( EndpointEffect < 0 )
    {
      v15 = 7743;
      goto LABEL_8;
    }
LABEL_9:
    ppIAudioMediaType = 0;
    v44 = 0;
    v16 = v50;
    if ( v10 == 1 )
    {
      memset(&pAudioFormat, 0, sizeof(pAudioFormat));
      memset(v53, 0, sizeof(v53));
      if ( !v50 )
      {
        v14 = -2004287480;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E4A,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x88890008LL,
          v43);
LABEL_12:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
        goto LABEL_54;
      }
      v51 = 0;
      IsOutputFormatSupported = v50->lpVtbl->IsOutputFormatSupported;
      wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v51, v13);
      if ( ((unsigned int (__fastcall *)(struct IAudioProcessingObject *, _QWORD, struct IAudioMediaType *, __int64 *))IsOutputFormatSupported)(
             v16,
             0,
             a4,
             &v51) )
      {
        v14 = -2004287480;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E4E,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x88890008LL,
          v43);
        v18 = (struct IAudioMediaType **)&v51;
LABEL_15:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v18);
        goto LABEL_12;
      }
      *(_DWORD *)&pAudioFormat.wFormatTag = 196606;
      pAudioFormat.nSamplesPerSec = *(_DWORD *)(((__int64 (__fastcall *)(struct IAudioMediaType *))a4->lpVtbl->GetAudioFormat)(a4)
                                              + 4);
      v19 = (unsigned __int16)(4 * pAudioFormat.nChannels);
      pAudioFormat.nBlockAlign = 4 * pAudioFormat.nChannels;
      pAudioFormat.nAvgBytesPerSec = *(_DWORD *)(((__int64 (__fastcall *)(struct IAudioMediaType *))a4->lpVtbl->GetAudioFormat)(a4)
                                               + 4)
                                   * v19;
      *(_DWORD *)&pAudioFormat.wBitsPerSample = 1441824;
      strcpy((char *)v53, " ");
      *(_DWORD *)&v53[1] = 3;
      *(GUID *)&v53[3] = GUID_00000003_0000_0010_8000_00aa00389b71;
      wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&ppIAudioMediaType, v20);
      v21 = CreateAudioMediaType(&pAudioFormat, 0x28u, &ppIAudioMediaType);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E5F,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v21,
          v43);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v51);
LABEL_18:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
        v14 = v22;
        goto LABEL_54;
      }
      wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(&v44, a4);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v51);
    }
    else
    {
      pv = 0;
      *(_QWORD *)&pAudioFormat.wFormatTag = &pv;
      *(_QWORD *)&pAudioFormat.nAvgBytesPerSec = 0;
      LOBYTE(pAudioFormat.cbSize) = 1;
      v23 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(struct IAudioMediaType *))a4->lpVtbl->GetAudioFormat)(a4);
      v24 = CloneWaveFormat(v23, (struct tWAVEFORMATEX **)&pAudioFormat.nAvgBytesPerSec);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&pAudioFormat);
      if ( v24 < 0 )
      {
        v14 = -2004287480;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E67,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x88890008LL,
          v43);
        v25 = pv;
        pv = 0;
        if ( v25 )
          CoTaskMemFree(v25);
        goto LABEL_12;
      }
      ConvertPCMWfxToIEEEFloat((struct tWAVEFORMATEX *)pv);
      wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v44, v26);
      v27 = CreateAudioMediaType((const WAVEFORMATEX *)pv, *((unsigned __int16 *)pv + 8) + 18, &v44);
      v22 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E6C,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v27,
          v43);
        v28 = pv;
        pv = 0;
        if ( v28 )
          CoTaskMemFree(v28);
        goto LABEL_18;
      }
      wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(&ppIAudioMediaType, v44);
      v29 = pv;
      pv = 0;
      if ( v29 )
        CoTaskMemFree(v29);
    }
    v47 = 0;
    if ( v16 )
    {
      v48 = 0;
      v46 = 0;
      v30 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 198) + 56LL))(*((_QWORD *)this + 198)) == 0;
      lpVtbl = v16->lpVtbl;
      if ( v30 )
      {
        IsInputFormatSupported = lpVtbl->IsInputFormatSupported;
        wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v46, v31);
        if ( ((int (__fastcall *)(struct IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, __int64 *))IsInputFormatSupported)(
               v16,
               v44,
               ppIAudioMediaType,
               &v46) < 0 )
        {
          v34 = 7803;
LABEL_32:
          v14 = -2004287480;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v34,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)0x88890008LL,
            v43);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
LABEL_33:
          v18 = &v47;
          goto LABEL_15;
        }
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 24LL))(v46, &v48) < 0 )
        {
          v34 = 7804;
          goto LABEL_32;
        }
        if ( v48 )
        {
          v34 = 7805;
          goto LABEL_32;
        }
      }
      else
      {
        v35 = lpVtbl->IsOutputFormatSupported;
        wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v46, v31);
        if ( ((int (__fastcall *)(struct IAudioProcessingObject *, IAudioMediaType *, IAudioMediaType *, __int64 *))v35)(
               v16,
               v44,
               ppIAudioMediaType,
               &v46) < 0 )
        {
          v34 = 7810;
          goto LABEL_32;
        }
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 24LL))(v46, &v48) < 0 )
        {
          v34 = 7812;
          goto LABEL_32;
        }
        if ( v48 )
        {
          v34 = 7813;
          goto LABEL_32;
        }
      }
      wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(&v47, v46);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
    }
    else
    {
      wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(&v47, ppIAudioMediaType);
    }
    v36 = v47;
    v37 = ValidateAPOInputFormat(v47);
    v14 = v37;
    if ( v37 >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 198) + 56LL))(*((_QWORD *)this + 198))
        || (v40 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(IAudioMediaType *))v44->lpVtbl->GetAudioFormat)(v44),
            IsCompressedSpatialFormat(v40))
        || (v41 = ((__int64 (__fastcall *)(struct IAudioMediaType *))v36->lpVtbl->GetAudioFormat)(v36),
            *(_DWORD *)(v41 + 4) == *(_DWORD *)(((__int64 (__fastcall *)(struct IAudioMediaType *))a4->lpVtbl->GetAudioFormat)(a4)
                                              + 4)) )
      {
        v47 = 0;
        *a5 = v36;
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
        v14 = 0;
        goto LABEL_54;
      }
      v14 = -2004287480;
      v38 = 2290679816LL;
      v39 = 7830;
    }
    else
    {
      v38 = (unsigned int)v37;
      v39 = 7823;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v38,
      v43);
    goto LABEL_33;
  }
  v50 = 0;
  EndpointEffect = EffectPack::GetGfx(this, a3, 0, &v50, (struct IAudioSystemEffects2 **)v42);
  v14 = EndpointEffect;
  if ( EndpointEffect >= 0 )
    goto LABEL_9;
  v15 = 7739;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
    (const char *)(unsigned int)EndpointEffect,
    v43);
LABEL_54:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v50);
  return v14;
}

```

## disassembly

```asm
0x18003f28c  push    rbp
0x18003f28e  push    rbx
0x18003f28f  push    rsi
0x18003f290  push    rdi
0x18003f291  push    r12
0x18003f293  push    r14
0x18003f295  push    r15
0x18003f297  lea     rbp, [rsp-1Fh]
0x18003f29c  sub     rsp, 0A0h
0x18003f2a3  mov     rax, cs:__security_cookie
0x18003f2aa  xor     rax, rsp
0x18003f2ad  mov     [rbp+4Fh+var_38], rax
0x18003f2b1  mov     rsi, r9
0x18003f2b4  mov     ebx, r8d
0x18003f2b7  mov     r14, rcx
0x18003f2ba  mov     r15, [rbp+4Fh+arg_20]
0x18003f2be  mov     rax, [r9]
0x18003f2c1  mov     rcx, r9
0x18003f2c4  mov     rax, [rax+28h]
0x18003f2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2cd  mov     rcx, rax; struct tWAVEFORMATEX *
0x18003f2d0  call    ?ValidateUncompressedWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x18003f2d5  mov     edi, eax
0x18003f2d7  xor     r12d, r12d
0x18003f2da  test    eax, eax
0x18003f2dc  jns     short loc_18003F2FD
0x18003f2de  mov     rcx, [rbp+57h]; this
0x18003f2e2  mov     r9d, eax; char *
0x18003f2e5  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f2ec  mov     edx, 1E35h; void *
0x18003f2f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f2f6  mov     eax, edi
0x18003f2f8  jmp     loc_18003F816
0x18003f2fd  mov     [rbp+4Fh+var_70], r12
0x18003f301  mov     edx, ebx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003f303  mov     rcx, r14; this
0x18003f306  call    ?EndpointConnectorSupportsProcessingModes@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::EndpointConnectorSupportsProcessingModes(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18003f30b  test    eax, eax
0x18003f30d  jnz     short loc_18003F331
0x18003f30f  mov     [rbp+4Fh+var_70], r12
0x18003f313  lea     r9, [rbp+4Fh+var_70]; struct IAudioProcessingObject **
0x18003f317  xor     r8d, r8d; struct ICompositeSystemEffect **
0x18003f31a  mov     edx, ebx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003f31c  mov     rcx, r14; this
0x18003f31f  call    ?GetGfx@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetGfx(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x18003f324  mov     ebx, eax
0x18003f326  test    eax, eax
0x18003f328  jns     short loc_18003F376
0x18003f32a  mov     edx, 1E3Bh
0x18003f32f  jmp     short loc_18003F35E
0x18003f331  mov     [rbp+4Fh+var_70], r12
0x18003f335  mov     [rsp+0D0h+var_A8], r12; struct IAudioSystemEffects2 **
0x18003f33a  lea     rax, [rbp+4Fh+var_70]
0x18003f33e  mov     [rsp+0D0h+var_B0], rax; int
0x18003f343  xor     r9d, r9d; struct ICompositeSystemEffect **
0x18003f346  mov     r8d, ebx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003f349  xor     edx, edx; int
0x18003f34b  mov     rcx, r14; this
0x18003f34e  call    ?GetEndpointEffect@EffectPack@@QEAAJHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetEndpointEffect(int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x18003f353  mov     ebx, eax
0x18003f355  test    eax, eax
0x18003f357  jns     short loc_18003F376
0x18003f359  mov     edx, 1E3Fh; void *
0x18003f35e  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f365  mov     r9d, eax; char *
0x18003f368  mov     rcx, [rbp+57h]; this
0x18003f36c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f371  jmp     loc_18003F80B
0x18003f376  mov     [rbp+4Fh+ppIAudioMediaType], r12
0x18003f37a  mov     [rbp+4Fh+var_A0], r12
0x18003f37e  mov     rbx, [rbp+4Fh+var_70]
0x18003f382  cmp     edi, 1
0x18003f385  jnz     loc_18003F50E
0x18003f38b  mov     [rbp+4Fh+pAudioFormat.wFormatTag], r12w
0x18003f390  xorps   xmm0, xmm0
0x18003f393  xor     eax, eax
0x18003f395  movups  xmmword ptr [rbp+4Fh+pAudioFormat.nChannels], xmm0
0x18003f399  movups  xmmword ptr [rbp+4Fh+var_4E], xmm0
0x18003f39d  mov     qword ptr [rbp+4Fh+var_4E+0Eh], rax
0x18003f3a1  test    rbx, rbx
0x18003f3a4  jnz     short loc_18003F3DC
0x18003f3a6  mov     rcx, [rbp+57h]; this
0x18003f3aa  mov     ebx, 88890008h
0x18003f3af  mov     r9d, ebx; char *
0x18003f3b2  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f3b9  mov     edx, 1E4Ah; void *
0x18003f3be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f3c3  nop
0x18003f3c4  lea     rcx, [rbp+4Fh+var_A0]
0x18003f3c8  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f3cd  nop
0x18003f3ce  lea     rcx, [rbp+4Fh+ppIAudioMediaType]
0x18003f3d2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f3d7  jmp     loc_18003F80B
0x18003f3dc  mov     [rbp+4Fh+var_68], r12
0x18003f3e0  mov     rax, [rbx]
0x18003f3e3  mov     rdi, [rax+40h]
0x18003f3e7  lea     rcx, [rbp+4Fh+var_68]
0x18003f3eb  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f3f0  lea     r9, [rbp+4Fh+var_68]
0x18003f3f4  mov     r8, rsi
0x18003f3f7  xor     edx, edx
0x18003f3f9  mov     rcx, rbx
0x18003f3fc  mov     rax, rdi
0x18003f3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f404  test    eax, eax
0x18003f406  jz      short loc_18003F431
0x18003f408  mov     rcx, [rbp+57h]; this
0x18003f40c  mov     ebx, 88890008h
0x18003f411  mov     r9d, ebx; char *
0x18003f414  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f41b  mov     edx, 1E4Eh; void *
0x18003f420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f425  nop
0x18003f426  lea     rcx, [rbp+4Fh+var_68]
0x18003f42a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f42f  jmp     short loc_18003F3C4
0x18003f431  mov     dword ptr [rbp+4Fh+pAudioFormat.wFormatTag], 2FFFEh
0x18003f438  mov     rax, [rsi]
0x18003f43b  mov     rcx, rsi
0x18003f43e  mov     rax, [rax+28h]
0x18003f442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f447  mov     ecx, [rax+4]
0x18003f44a  mov     [rbp+4Fh+pAudioFormat.nSamplesPerSec], ecx
0x18003f44d  movzx   eax, [rbp+4Fh+pAudioFormat.nChannels]
0x18003f451  shl     ax, 2
0x18003f455  movzx   edi, ax
0x18003f458  mov     [rbp+4Fh+pAudioFormat.nBlockAlign], di
0x18003f45c  mov     rax, [rsi]
0x18003f45f  mov     rcx, rsi
0x18003f462  mov     rax, [rax+28h]
0x18003f466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f46b  imul    edi, [rax+4]
0x18003f46f  mov     [rbp+4Fh+pAudioFormat.nAvgBytesPerSec], edi
0x18003f472  mov     ecx, 20h ; ' '
0x18003f477  mov     dword ptr [rbp+4Fh+pAudioFormat.wBitsPerSample], 160020h
0x18003f47e  mov     word ptr [rbp+4Fh+var_4E], cx
0x18003f482  mov     dword ptr [rbp+4Fh+var_4E+2], 3
0x18003f489  movups  xmm0, xmmword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1
0x18003f490  movdqu  xmmword ptr [rbp+4Fh+var_4E+6], xmm0
0x18003f495  lea     rcx, [rbp+4Fh+ppIAudioMediaType]
0x18003f499  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f49e  lea     r8, [rbp+4Fh+ppIAudioMediaType]; ppIAudioMediaType
0x18003f4a2  mov     edx, 28h ; '('; cbAudioFormatSize
0x18003f4a7  lea     rcx, [rbp+4Fh+pAudioFormat]; pAudioFormat
0x18003f4ab  call    CreateAudioMediaType
0x18003f4b0  mov     edi, eax
0x18003f4b2  test    eax, eax
0x18003f4b4  jns     short loc_18003F4F3
0x18003f4b6  mov     rcx, [rbp+57h]; this
0x18003f4ba  mov     r9d, eax; char *
0x18003f4bd  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f4c4  mov     edx, 1E5Fh; void *
0x18003f4c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f4ce  nop
0x18003f4cf  lea     rcx, [rbp+4Fh+var_68]
0x18003f4d3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f4d8  nop
0x18003f4d9  lea     rcx, [rbp+4Fh+var_A0]
0x18003f4dd  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f4e2  nop
0x18003f4e3  lea     rcx, [rbp+4Fh+ppIAudioMediaType]
0x18003f4e7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f4ec  mov     ebx, edi
0x18003f4ee  jmp     loc_18003F80B
0x18003f4f3  mov     rdx, rsi
0x18003f4f6  lea     rcx, [rbp+4Fh+var_A0]
0x18003f4fa  call    ??4?$com_ptr_t@UIAudioMediaType@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIAudioMediaType@@@Z; wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(IAudioMediaType *)
0x18003f4ff  nop
0x18003f500  lea     rcx, [rbp+4Fh+var_68]
0x18003f504  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f509  jmp     loc_18003F60C
0x18003f50e  mov     [rbp+4Fh+pv], r12
0x18003f512  lea     rax, [rbp+4Fh+pv]
0x18003f516  mov     qword ptr [rbp+4Fh+pAudioFormat.wFormatTag], rax
0x18003f51a  mov     qword ptr [rbp+4Fh+pAudioFormat.nAvgBytesPerSec], r12
0x18003f51e  mov     byte ptr [rbp+4Fh+pAudioFormat.cbSize], 1
0x18003f522  mov     rax, [rsi]
0x18003f525  mov     rcx, rsi
0x18003f528  mov     rax, [rax+28h]
0x18003f52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f531  lea     rdx, [rbp+4Fh+pAudioFormat.nAvgBytesPerSec]; struct tWAVEFORMATEX **
0x18003f535  mov     rcx, rax; Src
0x18003f538  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18003f53d  mov     edi, eax
0x18003f53f  lea     rcx, [rbp+4Fh+pAudioFormat]
0x18003f543  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003f548  shr     edi, 1Fh
0x18003f54b  test    dil, dil
0x18003f54e  jz      short loc_18003F58A
0x18003f550  mov     rcx, [rbp+57h]; this
0x18003f554  mov     ebx, 88890008h
0x18003f559  mov     r9d, ebx; char *
0x18003f55c  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f563  mov     edx, 1E67h; void *
0x18003f568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f56d  nop
0x18003f56e  mov     rcx, [rbp+4Fh+pv]; pv
0x18003f572  mov     [rbp+4Fh+pv], r12
0x18003f576  test    rcx, rcx
0x18003f579  jz      loc_18003F3C4
0x18003f57f  call    cs:__imp_CoTaskMemFree
0x18003f585  jmp     loc_18003F3C4
0x18003f58a  mov     rcx, [rbp+4Fh+pv]; struct tWAVEFORMATEX *
0x18003f58e  call    ?ConvertPCMWfxToIEEEFloat@@YAXPEAUtWAVEFORMATEX@@@Z; ConvertPCMWfxToIEEEFloat(tWAVEFORMATEX *)
0x18003f593  lea     rcx, [rbp+4Fh+var_A0]
0x18003f597  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f59c  mov     rcx, [rbp+4Fh+pv]; pAudioFormat
0x18003f5a0  movzx   edx, word ptr [rcx+10h]
0x18003f5a4  add     edx, 12h; cbAudioFormatSize
0x18003f5a7  lea     r8, [rbp+4Fh+var_A0]; ppIAudioMediaType
0x18003f5ab  call    CreateAudioMediaType
0x18003f5b0  mov     edi, eax
0x18003f5b2  test    eax, eax
0x18003f5b4  jns     short loc_18003F5EB
0x18003f5b6  mov     rcx, [rbp+57h]; this
0x18003f5ba  mov     r9d, eax; char *
0x18003f5bd  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f5c4  mov     edx, 1E6Ch; void *
0x18003f5c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f5ce  nop
0x18003f5cf  mov     rcx, [rbp+4Fh+pv]; pv
0x18003f5d3  mov     [rbp+4Fh+pv], r12
0x18003f5d7  test    rcx, rcx
0x18003f5da  jz      loc_18003F4D9
0x18003f5e0  call    cs:__imp_CoTaskMemFree
0x18003f5e6  jmp     loc_18003F4D9
0x18003f5eb  mov     rdx, [rbp+4Fh+var_A0]
0x18003f5ef  lea     rcx, [rbp+4Fh+ppIAudioMediaType]
0x18003f5f3  call    ??4?$com_ptr_t@UIAudioMediaType@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIAudioMediaType@@@Z; wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::operator=(IAudioMediaType *)
0x18003f5f8  nop
0x18003f5f9  mov     rcx, [rbp+4Fh+pv]; pv
0x18003f5fd  mov     [rbp+4Fh+pv], r12
0x18003f601  test    rcx, rcx
0x18003f604  jz      short loc_18003F60C
0x18003f606  call    cs:__imp_CoTaskMemFree
0x18003f60c  mov     [rbp+4Fh+var_88], r12
0x18003f610  test    rbx, rbx
0x18003f613  jz      loc_18003F73D
0x18003f619  mov     [rbp+4Fh+var_80], r12d
0x18003f61d  mov     [rbp+4Fh+var_90], r12
0x18003f621  mov     rcx, [r14+630h]
0x18003f628  mov     rax, [rcx]
0x18003f62b  mov     rax, [rax+38h]
0x18003f62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f634  lea     rcx, [rbp+4Fh+var_90]
0x18003f638  test    eax, eax
0x18003f63a  mov     rax, [rbx]
0x18003f63d  jnz     loc_18003F6C4
0x18003f643  mov     rdi, [rax+38h]
0x18003f647  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f64c  lea     r9, [rbp+4Fh+var_90]
0x18003f650  mov     r8, [rbp+4Fh+ppIAudioMediaType]
0x18003f654  mov     rdx, [rbp+4Fh+var_A0]
0x18003f658  mov     rcx, rbx
0x18003f65b  mov     rax, rdi
0x18003f65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f663  test    eax, eax
0x18003f665  jns     short loc_18003F698
0x18003f667  mov     edx, 1E7Bh; void *
0x18003f66c  mov     ebx, 88890008h
0x18003f671  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003f678  mov     r9d, ebx; char *
0x18003f67b  mov     rcx, [rbp+57h]; this
0x18003f67f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f684  nop
0x18003f685  lea     rcx, [rbp+4Fh+var_90]
0x18003f689  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f68e  nop
0x18003f68f  lea     rcx, [rbp+4Fh+var_88]
0x18003f693  jmp     loc_18003F42A
0x18003f698  mov     rcx, [rbp+4Fh+var_90]
0x18003f69c  mov     rax, [rcx]
0x18003f69f  lea     rdx, [rbp+4Fh+var_80]
0x18003f6a3  mov     rax, [rax+18h]
0x18003f6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6ac  test    eax, eax
0x18003f6ae  jns     short loc_18003F6B7
0x18003f6b0  mov     edx, 1E7Ch
0x18003f6b5  jmp     short loc_18003F66C
0x18003f6b7  cmp     [rbp+4Fh+var_80], r12d
0x18003f6bb  jz      short loc_18003F724
0x18003f6bd  mov     edx, 1E7Dh
0x18003f6c2  jmp     short loc_18003F66C
0x18003f6c4  mov     rdi, [rax+40h]
0x18003f6c8  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003f6cd  lea     r9, [rbp+4Fh+var_90]
0x18003f6d1  mov     r8, [rbp+4Fh+ppIAudioMediaType]
0x18003f6d5  mov     rdx, [rbp+4Fh+var_A0]
0x18003f6d9  mov     rcx, rbx
0x18003f6dc  mov     rax, rdi
0x18003f6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6e4  test    eax, eax
0x18003f6e6  jns     short loc_18003F6F2
0x18003f6e8  mov     edx, 1E82h
0x18003f6ed  jmp     loc_18003F66C
0x18003f6f2  mov     rcx, [rbp+4Fh+var_90]
0x18003f6f6  mov     rax, [rcx]
0x18003f6f9  lea     rdx, [rbp+4Fh+var_80]
0x18003f6fd  mov     rax, [rax+18h]
  ... truncated ...
```
