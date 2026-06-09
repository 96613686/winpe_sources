# FillAPOInitSystemEffectsStructure(IMMDevice *,_GUID *,_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,APOInitSystemEffects2 &)

- ea: `0x14000664c`
- end: `0x140006e29`
- name: `?FillAPOInitSystemEffectsStructure@@YAJPEAUIMMDevice@@PEAU_GUID@@U2@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@AEAUAPOInitSystemEffects2@@@Z`
- size: `2013`
- prototype: `__int64 __fastcall(struct IMMDevice *, struct _GUID *, struct _GUID *, int, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct APOInitSystemEffects2 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140006264`
- `0x140006f20`
- `0x140062bf8`

## callees

- `0x14000664c`
- `0x1400079f0`
- `0x140008124`
- `0x14000a378`
- `0x14000c33c`
- `0x140016f68`
- `0x14001d790`
- `0x140031a68`
- `0x14005d0e0`
- `0x14005e168`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006cc7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006cc7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006766`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006a22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006ad9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006b74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006bd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006c5e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006766`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006a22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006ad9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006b74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006bd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140006c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006929`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006ace`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006929`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006ace`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006bc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall FillAPOInitSystemEffectsStructure(
        struct IMMDevice *a1,
        struct _GUID *a2,
        struct _GUID *a3,
        BOOL a4,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a5,
        struct APOInitSystemEffects2 *a6)
{
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v11; // eax
  int v12; // ebx
  struct IMMDeviceVtbl *v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  bool v18; // bl
  unsigned int v19; // r14d
  GUID fmtid; // xmm0
  DWORD pid; // eax
  IPropertyStore *v22; // rax
  IPropertyStore *v23; // rcx
  IPropertyStore *v24; // rax
  IMMDeviceCollection *v25; // rax
  LPVOID *v27; // rcx
  struct KSDATAFORMAT_WAVEFORMATEX *v28; // rdx
  void *v29; // rax
  struct IMMDeviceVtbl *v30; // rax
  int v31; // eax
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, LPVOID, _QWORD, __int64); // rsi
  IMMDeviceCollection *v34; // rcx
  int v35; // eax
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  __int64 v40; // r9
  __int64 v41; // rdx
  HRESULT v42; // eax
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v44; // eax
  __int64 v45; // rax
  __int64 v46; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v50; // [rsp+58h] [rbp-A8h] BYREF
  IPropertyStore *v51; // [rsp+60h] [rbp-A0h] BYREF
  IMMDeviceCollection *v52; // [rsp+68h] [rbp-98h] BYREF
  IPropertyStore *v53; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v55; // [rsp+80h] [rbp-80h] BYREF
  UINT v56; // [rsp+88h] [rbp-78h]
  UINT v57; // [rsp+8Ch] [rbp-74h]
  struct tWAVEFORMATEX *v58; // [rsp+90h] [rbp-70h] BYREF
  LPVOID *p_pv; // [rsp+98h] [rbp-68h] BYREF
  struct KSDATAFORMAT_WAVEFORMATEX *v60; // [rsp+A0h] [rbp-60h] BYREF
  char v61; // [rsp+A8h] [rbp-58h]
  PROPVARIANT v62[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct tWAVEFORMATEX *Src; // [rsp+C0h] [rbp-40h]
  int v64[2]; // [rsp+C8h] [rbp-38h] BYREF
  char v65; // [rsp+D0h] [rbp-30h]
  PROPVARIANT pvar[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v67; // [rsp+E8h] [rbp-18h]
  PROPVARIANT *v68; // [rsp+F0h] [rbp-10h]
  char v69; // [rsp+F8h] [rbp-8h]
  GUID v70; // [rsp+100h] [rbp+0h] BYREF
  DWORD v71; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  memset_0(a6, 0, sizeof(struct APOInitSystemEffects2));
  lpVtbl = a1->lpVtbl;
  v53 = 0;
  v11 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, IPropertyStore **))lpVtbl->OpenPropertyStore)(a1, 0, &v53);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
      (const char *)(unsigned int)v11,
      ppv);
    goto LABEL_63;
  }
  v13 = a1->lpVtbl;
  v50 = 0;
  v14 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 **))v13->QueryInterface)(
          a1,
          &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21,
          &v50);
  v12 = v14;
  if ( v14 < 0 )
  {
    v40 = (unsigned int)v14;
    v41 = 48;
LABEL_70:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
      (const char *)v40,
      ppv);
    goto LABEL_62;
  }
  if ( !v50 )
  {
    v12 = -2147418113;
    v40 = 2147549183LL;
    v41 = 49;
    goto LABEL_70;
  }
  v51 = 0;
  v15 = *v50;
  v51 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, IPropertyStore **))(v15 + 40))(v50, 0, &v51);
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
      (const char *)(unsigned int)v16,
      ppv);
LABEL_61:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
LABEL_62:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
LABEL_63:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
    return (unsigned int)v12;
  }
  *(_OWORD *)pvar = 0;
  v67 = 0;
  *(_QWORD *)v64 = pvar;
  v65 = 1;
  v17 = ((__int64 (__fastcall *)(IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v53->lpVtbl->GetValue)(
          v53,
          &DEVPKEY_AudioEndpointPlugin_FactoryCLSID,
          pvar);
  v12 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
      (const char *)(unsigned int)v17,
      ppv);
    PropVariantClear(pvar);
    goto LABEL_61;
  }
  v18 = LOWORD(pvar[0]) == 72;
  PropVariantClear(pvar);
  v52 = 0;
  v56 = 0;
  v57 = 0;
  v19 = 3;
  if ( a5 == eKeywordDetectorConnector )
  {
    fmtid = (GUID)PKEY_AudioEngine_KeywordDetector_DeviceFormat;
    pid = 0;
  }
  else
  {
    fmtid = PKEY_AudioEngine_DeviceFormat.fmtid;
    pid = PKEY_AudioEngine_DeviceFormat.pid;
  }
  v70 = fmtid;
  v71 = pid;
  if ( (*(unsigned int (__fastcall **)(__int64 *))(*v50 + 48))(v50) || v18 )
    goto LABEL_9;
  *(_OWORD *)v62 = 0;
  Src = 0;
  v68 = v62;
  v69 = 1;
  pv = 0;
  if ( a5 != eKeywordDetectorConnector )
    v19 = 0;
  if ( ((int (__fastcall *)(IPropertyStore *, GUID *, PROPVARIANT *))v53->lpVtbl->GetValue)(v53, &v70, v62) < 0
    || LOWORD(v62[0]) != 65 )
  {
    v55 = 0;
    v42 = CoCreateInstance(
            &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
            0,
            0x17u,
            &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
            &v55);
    v12 = v42;
    if ( v42 >= 0 )
    {
      v54 = 0;
      GetId = a1->lpVtbl->GetId;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v54,
        0);
      v44 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64 *))GetId)(a1, &v54);
      v12 = v44;
      if ( v44 >= 0 )
      {
        v58 = 0;
        v45 = *(_QWORD *)v55;
        p_pv = (LPVOID *)&v58;
        v60 = 0;
        v61 = 1;
        v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(v45 + 304))(v55, v54, v19, 0);
        wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
        if ( v12 >= 0 )
        {
          p_pv = &pv;
          v60 = 0;
          v61 = 1;
          v12 = CreateKSFormatFromWFXFormat(v58, &v60);
          wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
          if ( v12 >= 0 )
          {
            wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              &v58,
              0);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
            goto LABEL_26;
          }
          v46 = 106;
        }
        else
        {
          v46 = 104;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v46,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
          (const char *)(unsigned int)v12,
          (int)&v60);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v58,
          0);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
          (const char *)(unsigned int)v44,
          ppva);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
        (const char *)(unsigned int)v42,
        ppva);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
    goto LABEL_58;
  }
  v27 = &pv;
  p_pv = &pv;
  v28 = 0;
  v60 = 0;
  v61 = 1;
  if ( LODWORD(v62[1]) < 0x12uLL || LODWORD(v62[1]) < (unsigned __int64)Src->cbSize + 18 )
  {
    v12 = -2147024809;
  }
  else
  {
    v12 = CreateKSFormatFromWFXFormat(Src, &v60);
    if ( !v61 )
      goto LABEL_25;
    v28 = v60;
    v27 = p_pv;
  }
  v29 = *v27;
  *v27 = v28;
  if ( v29 )
    CoTaskMemFree(v29);
LABEL_25:
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
      (const char *)(unsigned int)v12,
      ppv);
LABEL_58:
    v38 = pv;
    pv = 0;
    if ( v38 )
      CoTaskMemFree(v38);
    PropVariantClear(v62);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
    goto LABEL_61;
  }
LABEL_26:
  v30 = a1->lpVtbl;
  *(_QWORD *)v64 = 0;
  v31 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))v30->Activate)(
          a1,
          &GUID_8bfd01ba_edf5_11e4_90ec_1681e6b88ec1,
          23);
  v12 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
      (const char *)(unsigned int)v31,
      (int)v64);
    if ( *(_QWORD *)v64 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v64 + 16LL))(*(_QWORD *)v64);
    v37 = pv;
    pv = 0;
    if ( v37 )
      CoTaskMemFree(v37);
    PropVariantClear(v62);
    if ( v52 )
      ((void (__fastcall *)(IMMDeviceCollection *))v52->lpVtbl->Release)(v52);
    if ( v51 )
      ((void (__fastcall *)(IPropertyStore *))v51->lpVtbl->Release)(v51);
    if ( v50 )
      (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
    if ( v53 )
      ((void (__fastcall *)(IPropertyStore *))v53->lpVtbl->Release)(v53);
    return (unsigned int)v12;
  }
  v32 = *(_QWORD *)v64;
  v33 = *(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, __int64))(**(_QWORD **)v64 + 120LL);
  v34 = v52;
  v52 = 0;
  if ( v34 )
    ((void (__fastcall *)(IMMDeviceCollection *))v34->lpVtbl->Release)(v34);
  v35 = v33(v32, pv, *(unsigned int *)pv, 1);
  v12 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectsutil.cpp",
      (const char *)(unsigned int)v35,
      v19);
    if ( *(_QWORD *)v64 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v64 + 16LL))(*(_QWORD *)v64);
    v36 = pv;
    pv = 0;
    if ( v36 )
      CoTaskMemFree(v36);
    PropVariantClear(v62);
    if ( v52 )
      ((void (__fastcall *)(IMMDeviceCollection *))v52->lpVtbl->Release)(v52);
    if ( v51 )
      ((void (__fastcall *)(IPropertyStore *))v51->lpVtbl->Release)(v51);
    if ( v50 )
      (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
    if ( v53 )
      ((void (__fastcall *)(IPropertyStore *))v53->lpVtbl->Release)(v53);
    return (unsigned int)v12;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v64);
  v39 = pv;
  pv = 0;
  if ( v39 )
    CoTaskMemFree(v39);
  PropVariantClear(v62);
LABEL_9:
  a6->APOInit.cbSize = 88;
  a6->APOInit.clsid = *a2;
  v22 = v53;
  v23 = 0;
  v53 = 0;
  a6->pAPOEndpointProperties = v22;
  v24 = v51;
  v51 = 0;
  a6->pAPOSystemEffectsProperties = v24;
  a6->pReserved = 0;
  v25 = v52;
  v52 = 0;
  a6->pDeviceCollection = v25;
  a6->nSoftwareIoDeviceInCollection = v56;
  a6->nSoftwareIoConnectorIndex = v57;
  a6->AudioProcessingMode = *a3;
  a6->InitializeForDiscoveryOnly = a4;
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
    v23 = v53;
  }
  if ( v23 )
    ((void (__fastcall *)(IPropertyStore *))v23->lpVtbl->Release)(v23);
  return 0;
}

```

## disassembly

```asm
0x14000664c  push    rbp
0x14000664e  push    rbx
0x14000664f  push    rsi
0x140006650  push    rdi
0x140006651  push    r12
0x140006653  push    r13
0x140006655  push    r14
0x140006657  push    r15
0x140006659  lea     rbp, [rsp-28h]
0x14000665e  sub     rsp, 128h
0x140006665  mov     rax, cs:__security_cookie
0x14000666c  xor     rax, rsp
0x14000666f  mov     [rbp+60h+var_48], rax
0x140006673  mov     r15d, r9d
0x140006676  mov     r12, r8
0x140006679  mov     r13, rdx
0x14000667c  mov     rsi, rcx
0x14000667f  mov     rdi, [rbp+60h+arg_28]
0x140006686  xor     edx, edx; Val
0x140006688  lea     r8d, [rdx+58h]; Size
0x14000668c  mov     rcx, rdi; void *
0x14000668f  call    memset_0
0x140006694  nop
0x140006695  mov     rax, [rsi]
0x140006698  xor     r14d, r14d
0x14000669b  mov     [rsp+160h+var_F0], r14
0x1400066a0  lea     r8, [rsp+160h+var_F0]
0x1400066a5  xor     edx, edx
0x1400066a7  mov     rcx, rsi
0x1400066aa  mov     rax, [rax+20h]
0x1400066ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066b3  mov     ebx, eax
0x1400066b5  test    eax, eax
0x1400066b7  js      loc_140006BDE
0x1400066bd  mov     rax, [rsi]
0x1400066c0  mov     [rsp+160h+var_108], r14
0x1400066c5  lea     r8, [rsp+160h+var_108]
0x1400066ca  lea     rdx, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21
0x1400066d1  mov     rcx, rsi
0x1400066d4  mov     rax, [rax]
0x1400066d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066dc  mov     ebx, eax
0x1400066de  test    eax, eax
0x1400066e0  js      loc_140006BF8
0x1400066e6  mov     rcx, [rsp+160h+var_108]
0x1400066eb  test    rcx, rcx
0x1400066ee  jz      loc_140006C02
0x1400066f4  mov     [rsp+160h+var_100], r14
0x1400066f9  mov     rax, [rcx]
0x1400066fc  mov     [rsp+160h+var_100], r14
0x140006701  lea     r8, [rsp+160h+var_100]
0x140006706  xor     edx, edx
0x140006708  mov     rax, [rax+28h]
0x14000670c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006711  mov     ebx, eax
0x140006713  test    eax, eax
0x140006715  js      loc_140006C24
0x14000671b  xorps   xmm0, xmm0
0x14000671e  xor     eax, eax
0x140006720  movups  xmmword ptr [rbp+60h+pvar], xmm0
0x140006724  mov     [rbp+60h+var_78], rax
0x140006728  lea     rax, [rbp+60h+pvar]
0x14000672c  mov     qword ptr [rbp+60h+var_98], rax
0x140006730  mov     [rbp+60h+var_90], 1
0x140006734  mov     rcx, [rsp+160h+var_F0]
0x140006739  mov     rax, [rcx]
0x14000673c  lea     r8, [rbp+60h+pvar]
0x140006740  lea     rdx, DEVPKEY_AudioEndpointPlugin_FactoryCLSID
0x140006747  mov     rax, [rax+28h]
0x14000674b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006750  mov     ebx, eax
0x140006752  test    eax, eax
0x140006754  js      loc_140006C41
0x14000675a  cmp     word ptr [rbp+60h+pvar], 48h ; 'H'
0x14000675f  setz    bl
0x140006762  lea     rcx, [rbp+60h+pvar]; pvar
0x140006766  call    cs:__imp_PropVariantClear
0x14000676c  mov     [rsp+160h+var_F8], r14
0x140006771  mov     [rbp+60h+var_D8], r14d
0x140006775  mov     [rbp+60h+var_D4], r14d
0x140006779  mov     r14d, 3
0x14000677f  cmp     [rbp+60h+arg_20], r14d
0x140006786  jz      loc_140006C69
0x14000678c  movups  xmm0, xmmword ptr cs:PKEY_AudioEngine_DeviceFormat.fmtid.Data1
0x140006793  mov     eax, cs:PKEY_AudioEngine_DeviceFormat.pid
0x140006799  movups  [rbp+60h+var_60], xmm0
0x14000679d  mov     [rbp+60h+var_50], eax
0x1400067a0  mov     rcx, [rsp+160h+var_108]
0x1400067a5  mov     rax, [rcx]
0x1400067a8  mov     rax, [rax+30h]
0x1400067ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067b1  test    eax, eax
0x1400067b3  jz      loc_140006865
0x1400067b9  mov     dword ptr [rdi], 58h ; 'X'
0x1400067bf  movups  xmm0, xmmword ptr [r13+0]
0x1400067c4  movdqu  xmmword ptr [rdi+4], xmm0
0x1400067c9  mov     rax, [rsp+160h+var_F0]
0x1400067ce  xor     ecx, ecx
0x1400067d0  mov     [rsp+160h+var_F0], rcx
0x1400067d5  mov     [rdi+18h], rax
0x1400067d9  mov     rax, [rsp+160h+var_100]
0x1400067de  mov     [rsp+160h+var_100], rcx
0x1400067e3  mov     [rdi+20h], rax
0x1400067e7  mov     [rdi+28h], rcx
0x1400067eb  mov     rax, [rsp+160h+var_F8]
0x1400067f0  mov     [rsp+160h+var_F8], rcx
0x1400067f5  mov     [rdi+30h], rax
0x1400067f9  mov     eax, [rbp+60h+var_D8]
0x1400067fc  mov     [rdi+38h], eax
0x1400067ff  mov     eax, [rbp+60h+var_D4]
0x140006802  mov     [rdi+3Ch], eax
0x140006805  movaps  xmm0, xmmword ptr [r12]
0x14000680a  movdqu  xmmword ptr [rdi+40h], xmm0
0x14000680f  mov     [rdi+50h], r15d
0x140006813  mov     rdx, [rsp+160h+var_108]
0x140006818  test    rdx, rdx
0x14000681b  jz      short loc_140006831
0x14000681d  mov     rax, [rdx]
0x140006820  mov     rcx, rdx
0x140006823  mov     rax, [rax+10h]
0x140006827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000682c  mov     rcx, [rsp+160h+var_F0]
0x140006831  test    rcx, rcx
0x140006834  jz      short loc_140006843
0x140006836  mov     rax, [rcx]
0x140006839  mov     rax, [rax+10h]
0x14000683d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006842  nop
0x140006843  xor     eax, eax
0x140006845  mov     rcx, [rbp+60h+var_48]
0x140006849  xor     rcx, rsp; StackCookie
0x14000684c  call    __security_check_cookie
0x140006851  add     rsp, 128h
0x140006858  pop     r15
0x14000685a  pop     r14
0x14000685c  pop     r13
0x14000685e  pop     r12
0x140006860  pop     rdi
0x140006861  pop     rsi
0x140006862  pop     rbx
0x140006863  pop     rbp
0x140006864  retn
0x140006865  test    bl, bl
0x140006867  jnz     loc_1400067B9
0x14000686d  xorps   xmm0, xmm0
0x140006870  xor     eax, eax
0x140006872  movups  xmmword ptr [rbp+60h+var_B0], xmm0
0x140006876  mov     [rbp+60h+Src], rax
0x14000687a  lea     rax, [rbp+60h+var_B0]
0x14000687e  mov     [rbp+60h+var_70], rax
0x140006882  mov     [rbp+60h+var_68], 1
0x140006886  mov     [rsp+160h+pv], 0
0x14000688f  xor     eax, eax
0x140006891  cmp     [rbp+60h+arg_20], r14d
0x140006898  cmovnz  r14d, eax
0x14000689c  mov     rcx, [rsp+160h+var_F0]
0x1400068a1  mov     rax, [rcx]
0x1400068a4  lea     r8, [rbp+60h+var_B0]
0x1400068a8  lea     rdx, [rbp+60h+var_60]
0x1400068ac  mov     rax, [rax+28h]
0x1400068b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068b5  test    eax, eax
0x1400068b7  js      loc_140006CA2
0x1400068bd  cmp     word ptr [rbp+60h+var_B0], 41h ; 'A'
0x1400068c2  jnz     loc_140006CA2
0x1400068c8  lea     rcx, [rsp+160h+pv]
0x1400068cd  mov     [rbp+60h+var_C8], rcx
0x1400068d1  xor     edx, edx
0x1400068d3  mov     [rbp+60h+var_C0], rdx
0x1400068d7  mov     [rbp+60h+var_B8], 1
0x1400068db  mov     r8d, dword ptr [rbp+60h+var_B0+8]
0x1400068df  cmp     r8, 12h
0x1400068e3  jb      loc_140006C7B
0x1400068e9  mov     r9, [rbp+60h+Src]
0x1400068ed  movzx   eax, word ptr [r9+10h]
0x1400068f2  add     rax, 12h
0x1400068f6  cmp     r8, rax
0x1400068f9  jb      loc_140006C7B
0x1400068ff  lea     rdx, [rbp+60h+var_C0]; struct KSDATAFORMAT_WAVEFORMATEX **
0x140006903  mov     rcx, r9; Src
0x140006906  call    ?CreateKSFormatFromWFXFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAUKSDATAFORMAT_WAVEFORMATEX@@@Z; CreateKSFormatFromWFXFormat(tWAVEFORMATEX const *,KSDATAFORMAT_WAVEFORMATEX * *)
0x14000690b  mov     ebx, eax
0x14000690d  cmp     [rbp+60h+var_B8], 0
0x140006911  jz      short loc_14000692F
0x140006913  mov     rdx, [rbp+60h+var_C0]
0x140006917  mov     rcx, [rbp+60h+var_C8]
0x14000691b  mov     rax, [rcx]
0x14000691e  mov     [rcx], rdx
0x140006921  test    rax, rax
0x140006924  jz      short loc_14000692F
0x140006926  mov     rcx, rax; pv
0x140006929  call    cs:__imp_CoTaskMemFree
0x14000692f  test    ebx, ebx
0x140006931  js      loc_140006C85
0x140006937  mov     rax, [rsi]
0x14000693a  mov     qword ptr [rbp+60h+var_98], 0
0x140006942  lea     rcx, [rbp+60h+var_98]
0x140006946  mov     [rsp+160h+ppv], rcx; int
0x14000694b  xor     r9d, r9d
0x14000694e  lea     r8d, [r9+17h]
0x140006952  lea     rdx, _GUID_8bfd01ba_edf5_11e4_90ec_1681e6b88ec1
0x140006959  mov     rcx, rsi
0x14000695c  mov     rax, [rax+18h]
0x140006960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006965  mov     ebx, eax
0x140006967  test    eax, eax
0x140006969  js      loc_140006A8C
0x14000696f  mov     rbx, qword ptr [rbp+60h+var_98]
0x140006973  mov     rax, [rbx]
0x140006976  mov     rsi, [rax+78h]
0x14000697a  mov     rcx, [rsp+160h+var_F8]
0x14000697f  mov     [rsp+160h+var_F8], 0
0x140006988  test    rcx, rcx
0x14000698b  jnz     loc_140006E17
0x140006991  mov     rdx, [rsp+160h+pv]
0x140006996  lea     rax, [rbp+60h+var_D4]
0x14000699a  mov     [rsp+160h+var_128], rax
0x14000699f  lea     rax, [rbp+60h+var_D8]
0x1400069a3  mov     [rsp+160h+var_130], rax
0x1400069a8  lea     rax, [rsp+160h+var_F8]
0x1400069ad  mov     [rsp+160h+var_138], rax
0x1400069b2  mov     dword ptr [rsp+160h+ppv], r14d; int
0x1400069b7  mov     r9d, 1
0x1400069bd  mov     r8d, [rdx]
0x1400069c0  mov     rcx, rbx
0x1400069c3  mov     rax, rsi
0x1400069c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069cb  mov     ebx, eax
0x1400069cd  test    eax, eax
0x1400069cf  jns     loc_140006BAB
0x1400069d5  mov     rcx, [rbp+68h]; this
0x1400069d9  mov     r9d, eax; char *
0x1400069dc  lea     r8, aAvcoreAudiocor_51; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400069e3  mov     edx, 72h ; 'r'; void *
0x1400069e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400069ed  nop
0x1400069ee  mov     rcx, qword ptr [rbp+60h+var_98]
0x1400069f2  test    rcx, rcx
0x1400069f5  jz      short loc_140006A04
0x1400069f7  mov     rax, [rcx]
0x1400069fa  mov     rax, [rax+10h]
0x1400069fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a03  nop
0x140006a04  mov     rcx, [rsp+160h+pv]; pv
0x140006a09  mov     [rsp+160h+pv], 0
0x140006a12  test    rcx, rcx
0x140006a15  jz      short loc_140006A1E
0x140006a17  call    cs:__imp_CoTaskMemFree
0x140006a1d  nop
0x140006a1e  lea     rcx, [rbp+60h+var_B0]; pvar
0x140006a22  call    cs:__imp_PropVariantClear
0x140006a28  nop
0x140006a29  mov     rcx, [rsp+160h+var_F8]
0x140006a2e  test    rcx, rcx
0x140006a31  jz      short loc_140006A40
0x140006a33  mov     rax, [rcx]
0x140006a36  mov     rax, [rax+10h]
0x140006a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a3f  nop
0x140006a40  mov     rcx, [rsp+160h+var_100]
0x140006a45  test    rcx, rcx
0x140006a48  jz      short loc_140006A57
0x140006a4a  mov     rax, [rcx]
0x140006a4d  mov     rax, [rax+10h]
0x140006a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a56  nop
0x140006a57  mov     rcx, [rsp+160h+var_108]
0x140006a5c  test    rcx, rcx
0x140006a5f  jz      short loc_140006A6E
0x140006a61  mov     rax, [rcx]
0x140006a64  mov     rax, [rax+10h]
0x140006a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a6d  nop
0x140006a6e  mov     rcx, [rsp+160h+var_F0]
0x140006a73  test    rcx, rcx
0x140006a76  jz      short loc_140006A85
0x140006a78  mov     rax, [rcx]
0x140006a7b  mov     rax, [rax+10h]
0x140006a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a84  nop
0x140006a85  mov     eax, ebx
0x140006a87  jmp     loc_140006845
0x140006a8c  mov     rcx, [rbp+68h]; this
0x140006a90  mov     r9d, ebx; char *
0x140006a93  lea     r8, aAvcoreAudiocor_51; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140006a9a  mov     edx, 6Fh ; 'o'; void *
0x140006a9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006aa4  nop
0x140006aa5  mov     rcx, qword ptr [rbp+60h+var_98]
0x140006aa9  test    rcx, rcx
0x140006aac  jz      short loc_140006ABB
0x140006aae  mov     rax, [rcx]
0x140006ab1  mov     rax, [rax+10h]
0x140006ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006aba  nop
0x140006abb  mov     rcx, [rsp+160h+pv]; pv
0x140006ac0  mov     [rsp+160h+pv], 0
0x140006ac9  test    rcx, rcx
0x140006acc  jz      short loc_140006AD5
0x140006ace  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
