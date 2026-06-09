# CAvEndpointBuilder::CreateAvEndpointsForPnpInterface(IPnpInterface *,ENDPOINT_DESCRIPTOR const *)

- ea: `0x18003b078`
- end: `0x18003b788`
- name: `?CreateAvEndpointsForPnpInterface@CAvEndpointBuilder@@AEAAJPEAUIPnpInterface@@PEBUENDPOINT_DESCRIPTOR@@@Z`
- size: `1808`
- prototype: `int(CAvEndpointBuilder *__hidden this, struct IPnpInterface *, const struct ENDPOINT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d094`

## callees

- `0x180006b0c`
- `0x1800071dc`
- `0x18000fb60`
- `0x180010da8`
- `0x180021030`
- `0x180024d54`
- `0x1800286e4`
- `0x18003b078`
- `0x18003b790`
- `0x18003e920`
- `0x18003f7a4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b138`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b62f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b62f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6c1`

## string_xrefs

- `0x18003b153`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18003b68f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18003b6e0`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18003b70f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CAvEndpointBuilder::CreateAvEndpointsForPnpInterface(
        CAvEndpointBuilder *this,
        struct IPnpInterface *a2,
        const struct ENDPOINT_DESCRIPTOR *a3)
{
  HRESULT v5; // eax
  int v6; // ebx
  __int64 v7; // rdx
  LPVOID v8; // rcx
  unsigned __int64 v9; // r9
  struct IMMDevice *v10; // rbx
  HRESULT (__stdcall *Activate)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rdi
  __int64 v12; // rcx
  int v13; // r12d
  HRESULT (__stdcall *v14)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rdi
  int v15; // esi
  unsigned int v16; // r15d
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, struct IConnector **); // rbx
  int v19; // eax
  int v20; // eax
  __int64 *v21; // rcx
  __int64 v22; // rax
  struct _GUID v23; // xmm0
  BOOL v24; // ebx
  __int64 v25; // rax
  int v26; // eax
  const struct ENDPOINT_DESCRIPTOR *v27; // rax
  _OWORD *v28; // rcx
  __int64 v29; // rdx
  _BYTE *v30; // rcx
  struct IConnector *v31; // rdi
  HRESULT (__stdcall *GetConnectedTo)(IConnector *, IConnector **); // rbx
  int AvEndpointForConnector; // r12d
  struct IConnector *v34; // rdi
  HRESULT (__stdcall *GetDeviceIdConnectedTo)(IConnector *, LPWSTR *); // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  int v37; // eax
  CAvEndpointBuilder *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rdx
  int *ppv; // [rsp+20h] [rbp-E0h]
  struct IConnector *v43; // [rsp+30h] [rbp-D0h] BYREF
  enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 v44; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, struct IPnpInterface **); // [rsp+50h] [rbp-B0h] BYREF
  int v48[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct IPnpInterface *v49; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v50; // [rsp+68h] [rbp-98h] BYREF
  int v51; // [rsp+6Ch] [rbp-94h] BYREF
  int v52; // [rsp+70h] [rbp-90h] BYREF
  int v53; // [rsp+74h] [rbp-8Ch] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v55; // [rsp+80h] [rbp-80h] BYREF
  struct IMMDevice *v56; // [rsp+88h] [rbp-78h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h] BYREF
  int v58; // [rsp+98h] [rbp-68h]
  struct _GUID v59; // [rsp+A0h] [rbp-60h] BYREF
  CAvEndpointBuilder *v60; // [rsp+B0h] [rbp-50h]
  _QWORD v61[2]; // [rsp+C0h] [rbp-40h] BYREF
  enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 v62; // [rsp+D0h] [rbp-30h]
  struct _GUID v63; // [rsp+D4h] [rbp-2Ch]
  _BYTE *v64; // [rsp+198h] [rbp+98h]
  BOOL v65; // [rsp+1A0h] [rbp+A0h]
  struct _GUID v66; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v67[80]; // [rsp+200h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v60 = this;
  v49 = a2;
  *(_QWORD *)v48 = 0;
  v50 = 0;
  v57 = 0;
  memset_0(v67, 0, 0x48u);
  v55 = 0;
  v56 = 0;
  v5 = wil::com_query_to_nothrow<IMMDevice,IPnpDevnode * &>(&v49, &v56);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 5127;
LABEL_7:
    v9 = (unsigned int)v5;
    goto LABEL_8;
  }
  v8 = v55;
  v55 = 0;
  if ( v8 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  v5 = CoCreateInstance(
         &GUID_06cca63e_9941_441b_b004_39f999ada412,
         0,
         0x17u,
         &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
         &v55);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 5129;
    goto LABEL_7;
  }
  v10 = v56;
  Activate = v56->lpVtbl->Activate;
  v12 = v57;
  v57 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  ppv = (int *)&v57;
  v6 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64, _QWORD))Activate)(
         v10,
         &GUID_1136a91a_2bef_45b3_91d9_0a58472ee8a7,
         23,
         0);
  if ( v6 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v57 + 24LL))(v57, v67);
    v58 = v13;
    v14 = v56->lpVtbl->Activate;
    *(_QWORD *)v48 = 0;
    ppv = v48;
    v5 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64, _QWORD))v14)(
           v56,
           &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
           23,
           0);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 5142;
      goto LABEL_7;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v48 + 24LL))(*(_QWORD *)v48, &v50);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 5145;
      goto LABEL_7;
    }
    v15 = 0;
    v16 = v50;
    while ( 1 )
    {
      if ( (--v16 & 0x80000000) != 0 )
      {
        v6 = v15;
        goto LABEL_76;
      }
      v43 = 0;
      v51 = 0;
      v17 = *(_QWORD *)v48;
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IConnector **))(**(_QWORD **)v48 + 32LL);
      wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v43);
      v19 = v18(v17, v16, &v43);
      v6 = v19;
      if ( v19 < 0 )
      {
        v40 = 5154;
        goto LABEL_73;
      }
      v19 = ((__int64 (__fastcall *)(struct IConnector *, int *))v43->lpVtbl->GetType)(v43, &v51);
      v6 = v19;
      if ( v19 < 0 )
      {
        v40 = 5157;
LABEL_73:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v19,
          (int)v48);
        goto LABEL_74;
      }
      if ( (unsigned int)(v51 - 1) <= 1 )
        break;
LABEL_63:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
    }
    v45 = 0;
    v66 = 0;
    v44 = In;
    v20 = ((__int64 (__fastcall *)(struct IConnector *, enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 *))v43->lpVtbl->GetDataFlow)(
            v43,
            &v44);
    v6 = v20;
    if ( v20 < 0 )
    {
      v39 = 5168;
LABEL_69:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v20,
        (int)v48);
LABEL_70:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
LABEL_74:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
      goto LABEL_76;
    }
    v21 = v45;
    v45 = 0;
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    v20 = ((__int64 (__fastcall *)(struct IConnector *, GUID *, __int64 **))v43->lpVtbl->QueryInterface)(
            v43,
            &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
            &v45);
    v6 = v20;
    if ( v20 < 0 )
    {
      v39 = 5171;
      goto LABEL_69;
    }
    v22 = *(_QWORD *)((char *)a3 + 20) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    if ( !v22 )
      v22 = *(_QWORD *)((char *)a3 + 28) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( v22 )
    {
      v23 = *(struct _GUID *)((char *)a3 + 20);
      v66 = v23;
    }
    else
    {
      if ( (*(int (__fastcall **)(__int64 *, struct _GUID *))(*v45 + 56))(v45, &v66) < 0 )
      {
LABEL_62:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
        goto LABEL_63;
      }
      v23 = v66;
    }
    v59 = v23;
    if ( ConnectorIsSupported(v56, v43, &v59, v44) )
    {
      v24 = 1;
      *(_QWORD *)&v59.Data1 = 0;
      v52 = 0;
      v25 = *v45;
      if ( v44 )
        v26 = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *))(v25 + 80))(v45, &v59);
      else
        v26 = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *))(v25 + 88))(v45, &v59);
      if ( v26 >= 0
        && (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)&v59.Data1 + 24LL))(*(_QWORD *)&v59.Data1, &v52) >= 0 )
      {
        v24 = v52 == 0;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v59);
      if ( !v24 )
      {
        v27 = a3;
        v28 = v61;
        v29 = 2;
        do
        {
          *v28 = *(_OWORD *)v27;
          v28[1] = *((_OWORD *)v27 + 1);
          v28[2] = *((_OWORD *)v27 + 2);
          v28[3] = *((_OWORD *)v27 + 3);
          v28[4] = *((_OWORD *)v27 + 4);
          v28[5] = *((_OWORD *)v27 + 5);
          v28[6] = *((_OWORD *)v27 + 6);
          v28[7] = *((_OWORD *)v27 + 7);
          v28 += 8;
          v27 = (const struct ENDPOINT_DESCRIPTOR *)((char *)v27 + 128);
          --v29;
        }
        while ( v29 );
        *v28 = *(_OWORD *)v27;
        v28[1] = *((_OWORD *)v27 + 1);
        *((_QWORD *)v28 + 4) = *((_QWORD *)v27 + 4);
        v61[0] = a2;
        v61[1] = v43;
        ((void (__fastcall *)(struct IConnector *, _QWORD, __int64))v43->lpVtbl->AddRef)(v43, 0, 128);
        v62 = v44;
        v65 = v44 != Out;
        v63 = v66;
        v30 = v67;
        if ( v13 )
          v30 = 0;
        v64 = v30;
        v46 = 0;
        v31 = v43;
        GetConnectedTo = v43->lpVtbl->GetConnectedTo;
        wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v46);
        AvEndpointForConnector = ((__int64 (__fastcall *)(struct IConnector *, __int64 *))GetConnectedTo)(v31, &v46);
        if ( !v46 )
          goto LABEL_58;
        pv = 0;
        v34 = v43;
        GetDeviceIdConnectedTo = v43->lpVtbl->GetDeviceIdConnectedTo;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        v15 = ((__int64 (__fastcall *)(struct IConnector *, LPVOID *))GetDeviceIdConnectedTo)(v34, &pv);
        if ( v15 >= 0 )
        {
          v47 = 0;
          lpVtbl = g_DeviceEnumerator->lpVtbl;
          v47 = 0;
          v15 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, _QWORD))lpVtbl[1].Release)(
                  g_DeviceEnumerator,
                  pv,
                  &v47);
          if ( v15 >= 0 )
          {
            v53 = 0;
            v49 = 0;
            v37 = (**v47)(v47, &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21, &v49);
            v6 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x146A,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                (const char *)(unsigned int)v37,
                (int)v48);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
              if ( pv )
                CoTaskMemFree(pv);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              goto LABEL_70;
            }
            v15 = (*(__int64 (__fastcall **)(struct IPnpInterface *, int *))(*(_QWORD *)v49 + 32LL))(v49, &v53);
            if ( v15 >= 0 && (v53 & 0x20000000) != 0 )
            {
              (*(void (__fastcall **)(LPVOID, __int64 (__fastcall ***)(_QWORD, GUID *, struct IPnpInterface **)))(*(_QWORD *)v55 + 104LL))(
                v55,
                v47);
              wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v46);
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
        }
        v38 = (CAvEndpointBuilder *)pv;
        if ( pv )
          CoTaskMemFree(pv);
        if ( !v46 )
LABEL_58:
          AvEndpointForConnector = CAvEndpointBuilder::CreateAvEndpointForConnector(
                                     (struct _RTL_CRITICAL_SECTION *)v60,
                                     (const struct ENDPOINT_DESCRIPTOR *)v61);
        if ( AvEndpointForConnector >= 0 )
          CAvEndpointBuilder::LogDeviceSQMInformation(v38, a2, a3);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
        v13 = v58;
      }
    }
    goto LABEL_62;
  }
  if ( v6 == -2147024893 )
  {
    v6 = -2147024893;
    goto LABEL_76;
  }
  v9 = (unsigned int)v6;
  v7 = 5135;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)v9,
    (int)ppv);
LABEL_76:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v56);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v48);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003b078  mov     [rsp-8+arg_18], rbx
0x18003b07d  push    rbp
0x18003b07e  push    rsi
0x18003b07f  push    rdi
0x18003b080  push    r12
0x18003b082  push    r13
0x18003b084  push    r14
0x18003b086  push    r15
0x18003b088  lea     rbp, [rsp-160h]
0x18003b090  sub     rsp, 260h
0x18003b097  mov     rax, cs:__security_cookie
0x18003b09e  xor     rax, rsp
0x18003b0a1  mov     [rbp+190h+var_40], rax
0x18003b0a8  mov     r14, r8
0x18003b0ab  mov     r13, rdx
0x18003b0ae  mov     [rbp+190h+var_1E0], rcx
0x18003b0b2  mov     [rsp+290h+var_230], rdx
0x18003b0b7  xor     esi, esi
0x18003b0b9  mov     qword ptr [rsp+290h+var_238], rsi
0x18003b0be  mov     [rsp+290h+var_228], esi
0x18003b0c2  mov     [rbp+190h+var_200], rsi
0x18003b0c6  xor     edx, edx; Val
0x18003b0c8  lea     r8d, [rsi+48h]; Size
0x18003b0cc  lea     rcx, [rbp+190h+var_90]; void *
0x18003b0d3  call    memset_0
0x18003b0d8  nop
0x18003b0d9  mov     [rbp+190h+var_210], rsi
0x18003b0dd  mov     [rbp+190h+var_208], rsi
0x18003b0e1  lea     rdx, [rbp+190h+var_208]
0x18003b0e5  lea     rcx, [rsp+290h+var_230]
0x18003b0ea  call    ??$com_query_to_nothrow@UIMMDevice@@AEAPEAUIPnpDevnode@@@wil@@YAJAEAPEAUIPnpDevnode@@PEAPEAUIMMDevice@@@Z; wil::com_query_to_nothrow<IMMDevice,IPnpDevnode * &>(IPnpDevnode * &,IMMDevice * *)
0x18003b0ef  mov     ebx, eax
0x18003b0f1  test    eax, eax
0x18003b0f3  jns     short loc_18003B0FC
0x18003b0f5  mov     edx, 1407h
0x18003b0fa  jmp     short loc_18003B149
0x18003b0fc  mov     rcx, [rbp+190h+var_210]
0x18003b100  mov     [rbp+190h+var_210], rsi
0x18003b104  test    rcx, rcx
0x18003b107  jz      short loc_18003B116
0x18003b109  mov     rax, [rcx]
0x18003b10c  mov     rax, [rax+10h]
0x18003b110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b115  nop
0x18003b116  lea     rax, [rbp+190h+var_210]
0x18003b11a  mov     [rsp+290h+ppv], rax; int
0x18003b11f  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x18003b126  mov     r15d, 17h
0x18003b12c  mov     r8d, r15d; dwClsContext
0x18003b12f  xor     edx, edx; pUnkOuter
0x18003b131  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x18003b138  call    cs:__imp_CoCreateInstance
0x18003b13e  mov     ebx, eax
0x18003b140  test    eax, eax
0x18003b142  jns     short loc_18003B164
0x18003b144  mov     edx, 1409h; void *
0x18003b149  mov     r9d, eax; char *
0x18003b14c  mov     rcx, [rbp+198h]; this
0x18003b153  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18003b15a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b15f  jmp     loc_18003B734
0x18003b164  mov     rbx, [rbp+190h+var_208]
0x18003b168  mov     rax, [rbx]
0x18003b16b  mov     rdi, [rax+18h]
0x18003b16f  mov     rcx, [rbp+190h+var_200]
0x18003b173  mov     [rbp+190h+var_200], rsi
0x18003b177  test    rcx, rcx
0x18003b17a  jz      short loc_18003B189
0x18003b17c  mov     rax, [rcx]
0x18003b17f  mov     rax, [rax+10h]
0x18003b183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b188  nop
0x18003b189  lea     rax, [rbp+190h+var_200]
0x18003b18d  mov     [rsp+290h+ppv], rax
0x18003b192  xor     r9d, r9d
0x18003b195  mov     r8d, r15d
0x18003b198  lea     rdx, _GUID_1136a91a_2bef_45b3_91d9_0a58472ee8a7
0x18003b19f  mov     rcx, rbx
0x18003b1a2  mov     rax, rdi
0x18003b1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1aa  mov     ebx, eax
0x18003b1ac  test    eax, eax
0x18003b1ae  jns     short loc_18003B1CA
0x18003b1b0  mov     eax, 80070003h
0x18003b1b5  cmp     ebx, eax
0x18003b1b7  jnz     short loc_18003B1C0
0x18003b1b9  mov     ebx, eax
0x18003b1bb  jmp     loc_18003B734
0x18003b1c0  mov     r9d, ebx
0x18003b1c3  mov     edx, 140Fh
0x18003b1c8  jmp     short loc_18003B14C
0x18003b1ca  mov     rcx, [rbp+190h+var_200]
0x18003b1ce  mov     rax, [rcx]
0x18003b1d1  lea     rdx, [rbp+190h+var_90]
0x18003b1d8  mov     rax, [rax+18h]
0x18003b1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1e1  mov     r12d, eax
0x18003b1e4  mov     [rbp+190h+var_1F8], eax
0x18003b1e7  mov     rbx, [rbp+190h+var_208]
0x18003b1eb  mov     rcx, [rbx]
0x18003b1ee  mov     rdi, [rcx+18h]
0x18003b1f2  mov     rcx, qword ptr [rsp+290h+var_238]
0x18003b1f7  mov     qword ptr [rsp+290h+var_238], rsi
0x18003b1fc  test    rcx, rcx
0x18003b1ff  jz      short loc_18003B20E
0x18003b201  mov     rdx, [rcx]
0x18003b204  mov     rax, [rdx+10h]
0x18003b208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b20d  nop
0x18003b20e  lea     rax, [rsp+290h+var_238]
0x18003b213  mov     [rsp+290h+ppv], rax; int
0x18003b218  xor     r9d, r9d
0x18003b21b  mov     r8d, r15d
0x18003b21e  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x18003b225  mov     rcx, rbx
0x18003b228  mov     rax, rdi
0x18003b22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b230  mov     ebx, eax
0x18003b232  xor     edi, edi
0x18003b234  test    eax, eax
0x18003b236  jns     short loc_18003B242
0x18003b238  mov     edx, 1416h
0x18003b23d  jmp     loc_18003B149
0x18003b242  mov     rcx, qword ptr [rsp+290h+var_238]
0x18003b247  mov     rax, [rcx]
0x18003b24a  lea     rdx, [rsp+290h+var_228]
0x18003b24f  mov     rax, [rax+18h]
0x18003b253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b258  mov     ebx, eax
0x18003b25a  test    eax, eax
0x18003b25c  jns     short loc_18003B268
0x18003b25e  mov     edx, 1419h
0x18003b263  jmp     loc_18003B149
0x18003b268  mov     esi, edi
0x18003b26a  mov     r15d, [rsp+290h+var_228]
0x18003b26f  dec     r15d
0x18003b272  test    r15d, r15d
0x18003b275  js      loc_18003B732
0x18003b27b  mov     [rsp+290h+var_260], rdi
0x18003b280  mov     [rsp+290h+var_224], edi
0x18003b284  mov     rdi, qword ptr [rsp+290h+var_238]
0x18003b289  mov     rax, [rdi]
0x18003b28c  mov     rbx, [rax+20h]
0x18003b290  lea     rcx, [rsp+290h+var_260]
0x18003b295  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18003b29a  lea     r8, [rsp+290h+var_260]
0x18003b29f  mov     edx, r15d
0x18003b2a2  mov     rcx, rdi
0x18003b2a5  mov     rax, rbx
0x18003b2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2ad  mov     ebx, eax
0x18003b2af  xor     edi, edi
0x18003b2b1  test    eax, eax
0x18003b2b3  js      loc_18003B70A
0x18003b2b9  mov     rcx, [rsp+290h+var_260]
0x18003b2be  mov     rax, [rcx]
0x18003b2c1  lea     rdx, [rsp+290h+var_224]
0x18003b2c6  mov     rax, [rax+18h]
0x18003b2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2cf  mov     ebx, eax
0x18003b2d1  test    eax, eax
0x18003b2d3  js      loc_18003B703
0x18003b2d9  mov     eax, [rsp+290h+var_224]
0x18003b2dd  dec     eax
0x18003b2df  cmp     eax, 1
0x18003b2e2  ja      loc_18003B676
0x18003b2e8  mov     [rsp+290h+var_250], rdi
0x18003b2ed  xorps   xmm0, xmm0
0x18003b2f0  movups  [rbp+190h+var_A0], xmm0
0x18003b2f7  mov     [rsp+290h+var_258], edi
0x18003b2fb  mov     rcx, [rsp+290h+var_260]
0x18003b300  mov     rax, [rcx]
0x18003b303  lea     rdx, [rsp+290h+var_258]
0x18003b308  mov     rax, [rax+20h]
0x18003b30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b311  mov     ebx, eax
0x18003b313  test    eax, eax
0x18003b315  js      loc_18003B6DB
0x18003b31b  mov     rcx, [rsp+290h+var_250]
0x18003b320  mov     [rsp+290h+var_250], rdi
0x18003b325  test    rcx, rcx
0x18003b328  jz      short loc_18003B337
0x18003b32a  mov     rax, [rcx]
0x18003b32d  mov     rax, [rax+10h]
0x18003b331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b336  nop
0x18003b337  mov     rcx, [rsp+290h+var_260]
0x18003b33c  mov     rax, [rcx]
0x18003b33f  lea     r8, [rsp+290h+var_250]
0x18003b344  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x18003b34b  mov     rax, [rax]
0x18003b34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b353  mov     ebx, eax
0x18003b355  test    eax, eax
0x18003b357  js      loc_18003B6D4
0x18003b35d  mov     rax, [r14+14h]
0x18003b361  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003b368  jnz     short loc_18003B375
0x18003b36a  mov     rax, [r14+1Ch]
0x18003b36e  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18003b375  test    rax, rax
0x18003b378  jnz     short loc_18003B3A3
0x18003b37a  mov     rcx, [rsp+290h+var_250]
0x18003b37f  mov     rax, [rcx]
0x18003b382  lea     rdx, [rbp+190h+var_A0]
0x18003b389  mov     rax, [rax+38h]
0x18003b38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b392  test    eax, eax
0x18003b394  js      loc_18003B66B
0x18003b39a  movaps  xmm0, [rbp+190h+var_A0]
0x18003b3a1  jmp     short loc_18003B3AF
0x18003b3a3  movups  xmm0, xmmword ptr [r14+14h]
0x18003b3a8  movaps  [rbp+190h+var_A0], xmm0
0x18003b3af  movdqa  xmmword ptr [rbp+190h+var_1F0.Data1], xmm0
0x18003b3b4  mov     r9d, [rsp+290h+var_258]; enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011
0x18003b3b9  lea     r8, [rbp+190h+var_1F0]; struct _GUID
0x18003b3bd  mov     rdx, [rsp+290h+var_260]; struct IConnector *
0x18003b3c2  mov     rcx, [rbp+190h+var_208]; struct IMMDevice *
0x18003b3c6  call    ?ConnectorIsSupported@@YAHPEAUIMMDevice@@PEAUIConnector@@U_GUID@@W4__MIDL___MIDL_itf_devicetopology_0000_0000_0011@@@Z; ConnectorIsSupported(IMMDevice *,IConnector *,_GUID,__MIDL___MIDL_itf_devicetopology_0000_0000_0011)
0x18003b3cb  test    eax, eax
0x18003b3cd  jz      loc_18003B66B
0x18003b3d3  mov     rcx, [rsp+290h+var_250]
0x18003b3d8  mov     ebx, 1
0x18003b3dd  mov     qword ptr [rbp+190h+var_1F0.Data1], rdi
0x18003b3e1  mov     [rsp+290h+var_220], edi
0x18003b3e5  mov     rax, [rcx]
0x18003b3e8  lea     rdx, [rbp+190h+var_1F0]
0x18003b3ec  cmp     [rsp+290h+var_258], edi
0x18003b3f0  jnz     short loc_18003B3F8
0x18003b3f2  mov     rax, [rax+58h]
0x18003b3f6  jmp     short loc_18003B3FC
0x18003b3f8  mov     rax, [rax+50h]
0x18003b3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b401  test    eax, eax
0x18003b403  js      short loc_18003B427
0x18003b405  mov     rcx, qword ptr [rbp+190h+var_1F0.Data1]
0x18003b409  mov     rax, [rcx]
0x18003b40c  lea     rdx, [rsp+290h+var_220]
0x18003b411  mov     rax, [rax+18h]
0x18003b415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b41a  test    eax, eax
0x18003b41c  js      short loc_18003B427
0x18003b41e  mov     ebx, edi
0x18003b420  cmp     [rsp+290h+var_220], edi
0x18003b424  setz    bl
0x18003b427  lea     rcx, [rbp+190h+var_1F0]
0x18003b42b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b430  test    ebx, ebx
0x18003b432  jnz     loc_18003B66B
0x18003b438  mov     rax, r14
0x18003b43b  lea     rcx, [rbp+190h+var_1D0]
0x18003b43f  lea     edx, [rbx+2]
0x18003b442  lea     r8d, [rdx+7Eh]
0x18003b446  movups  xmm0, xmmword ptr [rax]
0x18003b449  movups  xmmword ptr [rcx], xmm0
0x18003b44c  movups  xmm1, xmmword ptr [rax+10h]
0x18003b450  movups  xmmword ptr [rcx+10h], xmm1
0x18003b454  movups  xmm0, xmmword ptr [rax+20h]
0x18003b458  movups  xmmword ptr [rcx+20h], xmm0
0x18003b45c  movups  xmm1, xmmword ptr [rax+30h]
0x18003b460  movups  xmmword ptr [rcx+30h], xmm1
0x18003b464  movups  xmm0, xmmword ptr [rax+40h]
0x18003b468  movups  xmmword ptr [rcx+40h], xmm0
0x18003b46c  movups  xmm1, xmmword ptr [rax+50h]
0x18003b470  movups  xmmword ptr [rcx+50h], xmm1
0x18003b474  movups  xmm0, xmmword ptr [rax+60h]
0x18003b478  movups  xmmword ptr [rcx+60h], xmm0
0x18003b47c  movups  xmm1, xmmword ptr [rax+70h]
0x18003b480  movups  xmmword ptr [rcx+70h], xmm1
0x18003b484  add     rcx, r8
0x18003b487  add     rax, r8
0x18003b48a  sub     rdx, 1
0x18003b48e  jnz     short loc_18003B446
0x18003b490  movups  xmm0, xmmword ptr [rax]
0x18003b493  movups  xmmword ptr [rcx], xmm0
0x18003b496  movups  xmm1, xmmword ptr [rax+10h]
0x18003b49a  movups  xmmword ptr [rcx+10h], xmm1
0x18003b49e  mov     rax, [rax+20h]
0x18003b4a2  mov     [rcx+20h], rax
0x18003b4a6  mov     [rbp+190h+var_1D0], r13
0x18003b4aa  mov     rcx, [rsp+290h+var_260]
0x18003b4af  mov     [rbp+190h+var_1C8], rcx
0x18003b4b3  mov     rax, [rcx]
0x18003b4b6  mov     rax, [rax+8]
0x18003b4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4bf  mov     eax, [rsp+290h+var_258]
0x18003b4c3  mov     [rbp+190h+var_1C0], eax
0x18003b4c6  mov     ecx, edi
0x18003b4c8  cmp     eax, 1
0x18003b4cb  setnz   cl
0x18003b4ce  mov     [rbp+190h+var_F0], ecx
0x18003b4d4  movaps  xmm0, [rbp+190h+var_A0]
0x18003b4db  movdqu  [rbp+190h+var_1BC], xmm0
0x18003b4e0  lea     rcx, [rbp+190h+var_90]
0x18003b4e7  test    r12d, r12d
0x18003b4ea  cmovnz  rcx, rdi
0x18003b4ee  mov     [rbp+190h+var_F8], rcx
0x18003b4f5  mov     [rsp+290h+var_248], rdi
0x18003b4fa  mov     rdi, [rsp+290h+var_260]
0x18003b4ff  mov     rax, [rdi]
  ... truncated ...
```
