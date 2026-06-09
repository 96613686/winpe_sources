# CAvEndpointBuilder::OnDeviceInterfaceArrival(ushort const *)

- ea: `0x180050858`
- end: `0x180051251`
- name: `?OnDeviceInterfaceArrival@CAvEndpointBuilder@@QEAAJPEBG@Z`
- size: `2553`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *this, OLECHAR *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800299a0`

## callees

- `0x180006b0c`
- `0x180008404`
- `0x18000fb60`
- `0x180010da8`
- `0x180010e60`
- `0x18001ef04`
- `0x18001f374`
- `0x180020ae4`
- `0x180021030`
- `0x180021080`
- `0x180021148`
- `0x1800243c4`
- `0x180024814`
- `0x1800254e0`
- `0x18002658c`
- `0x18002d094`
- `0x18002e43c`
- `0x18002e944`
- `0x18003e920`
- `0x180050858`
- `0x180052564`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005099a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005118b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800511d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005099a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005118b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800511d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800508d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800508d3`
- `OLEAUT32!__imp_SysFreeString` at `0x180050c78`
- `OLEAUT32!__imp_SysFreeString` at `0x180050c9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180050ccf`
- `OLEAUT32!__imp_SysFreeString` at `0x180051026`
- `OLEAUT32!__imp_SysFreeString` at `0x18005117c`
- `OLEAUT32!__imp_SysFreeString` at `0x180050c78`
- `OLEAUT32!__imp_SysFreeString` at `0x180050c9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180050ccf`
- `OLEAUT32!__imp_SysFreeString` at `0x180051026`
- `OLEAUT32!__imp_SysFreeString` at `0x18005117c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800509c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ce3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800510ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800511b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800511fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800509c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ce3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800510ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800511b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800511fc`

## string_xrefs

- `0x18005097b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18005107c`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800510b3`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051134`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051165`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CAvEndpointBuilder::OnDeviceInterfaceArrival(CAvEndpointBuilder *this, OLECHAR *a2)
{
  OLECHAR *v3; // r14
  const struct _tlgProvider_t *v4; // rax
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rcx
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(__int64, OLECHAR *, struct IPnpInterface **); // rsi
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, GUID *, __int64); // rdi
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, LPVOID *); // rbx
  OLECHAR *v18; // rcx
  struct IUnknown *v19; // r9
  ULONG (__stdcall *Release)(IUnknown *); // rdi
  __int64 v21; // rcx
  OLECHAR *v22; // rbx
  int v23; // edi
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, GUID *, __int64); // rsi
  __int64 v26; // rcx
  unsigned int v27; // r12d
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 *); // rdi
  __int64 v30; // rsi
  int (__fastcall *v31)(__int64, struct _GUID *); // rdi
  __int64 v32; // rdi
  __int64 v33; // rsi
  __int64 v34; // rcx
  bool v35; // r15
  int EndpointDescriptorRoot; // eax
  __int64 v37; // rsi
  int (__fastcall *v38)(__int64, __int64 *); // rdi
  __int64 v39; // rsi
  __int64 (__fastcall *v40)(__int64, LPVOID *); // rdi
  struct IUnknown *v41; // r9
  ULONG (__stdcall *v42)(IUnknown *); // rdi
  struct IMMDevice *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rsi
  void (__fastcall *v46)(__int64, __int64 *); // rdi
  __int64 v47; // rsi
  void (__fastcall *v48)(__int64, __int64 *); // rdi
  struct IPnpInterface *v49; // rcx
  CMidiBuilder *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 *v56; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v58; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v59; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v60; // [rsp+48h] [rbp-B8h] BYREF
  struct IPnpInterface *v61; // [rsp+50h] [rbp-B0h] BYREF
  struct IMMDevice *v62; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v66; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v67; // [rsp+80h] [rbp-80h] BYREF
  int v68; // [rsp+84h] [rbp-7Ch] BYREF
  enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 v69; // [rsp+88h] [rbp-78h] BYREF
  int v70; // [rsp+8Ch] [rbp-74h] BYREF
  struct _GUID Buf1; // [rsp+90h] [rbp-70h] BYREF
  __int64 v72; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v73; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v74; // [rsp+B8h] [rbp-48h]
  __int128 v75; // [rsp+C0h] [rbp-40h]
  int v76; // [rsp+D0h] [rbp-30h]
  BSTR v77; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v78; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int128 v80; // [rsp+F8h] [rbp-8h]
  int v81; // [rsp+108h] [rbp+8h]
  BSTR v82; // [rsp+110h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+118h] [rbp+18h] BYREF
  BSTR v84[2]; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID v85; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v3 = (OLECHAR *)AvEndpointBuilder;
  v64 = 0;
  v61 = 0;
  v72 = 0;
  v63 = 0;
  pv = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 10;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 10;
  EnterCriticalSection(AvEndpointBuilder);
  v84[1] = v3;
  v4 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v4 > 4u )
  {
    v77 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)byte_180076D4B,
      v5,
      v6,
      (__int64)&v77);
  }
  v7 = v72;
  v72 = 0;
  v8 = wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v7, &v72);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1894;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v8,
      (int)v56);
LABEL_8:
    if ( v3 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v3);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v78);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v73);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_110;
  }
  v11 = *(__int64 (__fastcall **)(__int64, OLECHAR *, struct IPnpInterface **))(*(_QWORD *)v72 + 40LL);
  v61 = 0;
  v8 = v11(v72, a2, &v61);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1895;
    goto LABEL_7;
  }
  v12 = v63;
  v63 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v8 = (**(__int64 (__fastcall ***)(struct IPnpInterface *, GUID *, __int64 *))v61)(
         v61,
         &GUID_d666063f_1587_4e43_81f1_b948e807363f,
         &v63);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1896;
    goto LABEL_7;
  }
  v13 = v63;
  v14 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v63 + 24LL);
  v15 = v64;
  v64 = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v56 = &v64;
  v9 = v14(v13, &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f, 23);
  if ( v9 < 0 )
    goto LABEL_8;
  v16 = v64;
  v17 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v64 + 64LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v8 = v17(v16, &pv);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1902;
    goto LABEL_7;
  }
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&Buf1, (const unsigned __int16 *)pv);
  ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(&v73, &Buf1);
  v18 = *(OLECHAR **)&Buf1.Data1;
LABEL_74:
  SysFreeString(v18);
  if ( v74 )
  {
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveHead(&v73, &v82);
    v67 = 0;
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(&v78, &v82);
    v19 = g_DeviceEnumerator;
    Release = g_DeviceEnumerator->lpVtbl[1].Release;
    v21 = v63;
    v63 = 0;
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v19 = g_DeviceEnumerator;
    }
    v22 = v82;
    v23 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, __int64 *))Release)(v19, v82, &v63);
    if ( v23 < 0 )
    {
      v54 = 1912;
    }
    else
    {
      v24 = v63;
      v25 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v63 + 24LL);
      v26 = v64;
      v64 = 0;
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      v56 = &v64;
      v23 = v25(v24, &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f, 23);
      if ( v23 < 0 )
        goto LABEL_98;
      v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v64 + 24LL))(v64, &v67);
      if ( v23 >= 0 )
      {
        v27 = v67;
        while ( 1 )
        {
          if ( (--v27 & 0x80000000) != 0 )
          {
            v18 = v22;
            goto LABEL_74;
          }
          v58 = 0;
          v68 = 0;
          v28 = v64;
          v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v64 + 32LL);
          wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v58);
          v23 = v29(v28, v27, &v58);
          if ( v23 < 0 )
            break;
          v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v58 + 24LL))(v58, &v68);
          if ( v23 < 0 )
          {
            v53 = 1924;
            goto LABEL_93;
          }
          if ( (unsigned int)(v68 - 1) <= 1 )
          {
            v59 = 0;
            v60 = 0;
            v85 = 0;
            v69 = In;
            v23 = (*(__int64 (__fastcall **)(__int64, enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011 *))(*(_QWORD *)v58 + 32LL))(
                    v58,
                    &v69);
            if ( v23 < 0 )
            {
              v51 = 1935;
LABEL_79:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v51,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                (const char *)(unsigned int)v23,
                (int)&v64);
              goto LABEL_80;
            }
            v34 = v60;
            v60 = 0;
            if ( v34 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            v23 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v58)(
                    v58,
                    &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
                    &v60);
            if ( v23 < 0 )
            {
              v51 = 1936;
              goto LABEL_79;
            }
            v35 = 0;
            if ( (*(int (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v60 + 56LL))(v60, &v85) >= 0 )
            {
              Buf1 = v85;
              EndpointDescriptorRoot = GetEndpointDescriptorRoot(&Buf1, v69);
              if ( EndpointDescriptorRoot == -1 )
              {
                v23 = -2147418113;
                v51 = 1941;
                goto LABEL_79;
              }
              v35 = LODWORD(qword_18006A170[6 * EndpointDescriptorRoot]) == 9;
            }
            v37 = v58;
            v38 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 64LL);
            wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v59);
            if ( v38(v37, &v59) >= 0 )
            {
              v66 = 0;
              v62 = 0;
              v65 = 0;
              v70 = 0;
              v39 = v58;
              v40 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v58 + 80LL);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &v66,
                0);
              v23 = v40(v39, &v66);
              if ( v23 < 0 )
              {
                v52 = 1956;
                goto LABEL_83;
              }
              v41 = g_DeviceEnumerator;
              v42 = g_DeviceEnumerator->lpVtbl[1].Release;
              v43 = v62;
              v62 = 0;
              if ( v43 )
              {
                ((void (__fastcall *)(struct IMMDevice *))v43->lpVtbl->Release)(v43);
                v41 = g_DeviceEnumerator;
              }
              v23 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, struct IMMDevice **))v42)(v41, v66, &v62);
              if ( v23 < 0 )
              {
                v52 = 1957;
                goto LABEL_83;
              }
              v44 = v65;
              v65 = 0;
              if ( v44 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
              v23 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))v62->lpVtbl->QueryInterface)(
                      v62,
                      &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21,
                      &v65);
              if ( v23 < 0 )
              {
                v52 = 1958;
                goto LABEL_83;
              }
              if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v65 + 32LL))(v65, &v70) >= 0
                && (v70 & 0x20000000) != 0 )
              {
                wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v59);
              }
              else
              {
                v23 = CAvEndpointBuilder::SyncEndpoint((LPCRITICAL_SECTION)v3, v62);
                if ( v23 < 0 )
                {
                  v52 = 1967;
LABEL_83:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v52,
                    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                    (const char *)(unsigned int)v23,
                    (int)&v64);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v62);
                  if ( v66 )
                    CoTaskMemFree(v66);
LABEL_80:
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v59);
                  goto LABEL_81;
                }
                if ( v35 )
                {
                  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v59);
                  v45 = v58;
                  v46 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 64LL);
                  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v59);
                  v46(v45, &v59);
                }
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v62);
              if ( v66 )
                CoTaskMemFree(v66);
            }
            if ( !v59 )
            {
              if ( !v35
                || (CAvEndpointBuilder::SyncEndpoints((LPCRITICAL_SECTION)v3),
                    v47 = v58,
                    v48 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 64LL),
                    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v59),
                    v48(v47, &v59),
                    !v59) )
              {
                v49 = v61;
                v61 = 0;
                if ( v49 )
                  (*(void (__fastcall **)(struct IPnpInterface *))(*(_QWORD *)v49 + 16LL))(v49);
                v23 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IPnpInterface **))v63)(
                        v63,
                        &GUID_3ade56af_4375_4413_9c91_4c652595ab07,
                        &v61);
                if ( v23 < 0 )
                {
                  v51 = 1999;
                  goto LABEL_79;
                }
                v23 = CAvEndpointBuilder::ProcessPnpInterface((LPCRITICAL_SECTION)v3, v61);
                if ( v23 < 0 )
                {
                  v51 = 2000;
                  goto LABEL_79;
                }
              }
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v59);
          }
          else if ( v68 == 4 )
          {
            *(_QWORD *)&Buf1.Data1 = 0;
            v30 = v58;
            v31 = *(int (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v58 + 80LL);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &Buf1,
              0);
            if ( v31(v30, &Buf1) >= 0 )
            {
              ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *(const unsigned __int16 **)&Buf1.Data1);
              v32 = ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Find(&v78, &bstrString);
              SysFreeString(bstrString);
              ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v84, *(const unsigned __int16 **)&Buf1.Data1);
              v33 = ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Find(&v73, v84);
              SysFreeString(v84[0]);
              if ( !v32 && !v33 )
              {
                ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v77, *(const unsigned __int16 **)&Buf1.Data1);
                ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(&v73, &v77);
                SysFreeString(v77);
              }
            }
            if ( *(_QWORD *)&Buf1.Data1 )
              CoTaskMemFree(*(LPVOID *)&Buf1.Data1);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v58);
        }
        v53 = 1923;
LABEL_93:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v53,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v23,
          (int)&v64);
LABEL_81:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v58);
        goto LABEL_98;
      }
      v54 = 1914;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v54,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v23,
      (int)&v64);
LABEL_98:
    SysFreeString(v22);
    if ( v3 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v3);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v78);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v73);
    if ( pv )
      CoTaskMemFree(pv);
    v9 = v23;
    goto LABEL_110;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl'::`2'::impl) )
  {
    v8 = CMidiBuilder::ProcessPnpInterface(v50, v61);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 2031;
      goto LABEL_7;
    }
  }
  else
  {
    v8 = CAvEndpointBuilder::ProcessPnpInterfaceForMidi(v50, v61);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 2035;
      goto LABEL_7;
    }
  }
  if ( v3 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v3);
  ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v78);
  ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v73);
  if ( pv )
    CoTaskMemFree(pv);
  v9 = 0;
LABEL_110:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v61);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v64);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180050858  push    rbp
0x18005085a  push    rbx
0x18005085b  push    rsi
0x18005085c  push    rdi
0x18005085d  push    r12
0x18005085f  push    r13
0x180050861  push    r14
0x180050863  push    r15
0x180050865  lea     rbp, [rsp-58h]
0x18005086a  sub     rsp, 158h
0x180050871  mov     rax, cs:__security_cookie
0x180050878  xor     rax, rsp
0x18005087b  mov     [rbp+90h+var_50], rax
0x18005087f  mov     rdi, rdx
0x180050882  mov     r14, cs:?AvEndpointBuilder@@3PEAVCAvEndpointBuilder@@EA; CAvEndpointBuilder * AvEndpointBuilder
0x180050889  xor     r13d, r13d
0x18005088c  mov     [rsp+190h+var_128], r13
0x180050891  mov     [rsp+190h+var_140], r13
0x180050896  mov     [rbp+90h+var_F0], r13
0x18005089a  mov     [rsp+190h+var_130], r13
0x18005089f  mov     [rsp+190h+pv], r13
0x1800508a4  xorps   xmm0, xmm0
0x1800508a7  movdqu  [rbp+90h+var_E8], xmm0
0x1800508ac  mov     [rbp+90h+var_D8], r13
0x1800508b0  xorps   xmm1, xmm1
0x1800508b3  movdqu  [rbp+90h+var_D0], xmm1
0x1800508b8  lea     eax, [r13+0Ah]
0x1800508bc  mov     [rbp+90h+var_C0], eax
0x1800508bf  movdqu  [rbp+90h+var_B0], xmm0
0x1800508c4  mov     [rbp+90h+var_A0], r13
0x1800508c8  movdqu  [rbp+90h+var_98], xmm1
0x1800508cd  mov     [rbp+90h+var_88], eax
0x1800508d0  mov     rcx, r14; lpCriticalSection
0x1800508d3  call    cs:__imp_EnterCriticalSection
0x1800508d9  mov     [rbp+90h+var_68], r14
0x1800508dd  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800508e2  mov     ecx, [rax]
0x1800508e4  cmp     ecx, 4
0x1800508e7  jbe     short loc_180050906
0x1800508e9  mov     [rbp+90h+var_B8], rdi
0x1800508ed  lea     rcx, [rbp+90h+var_B8]
0x1800508f1  mov     qword ptr [rsp+190h+var_170], rcx; int
0x1800508f6  lea     rdx, byte_180076D4B
0x1800508fd  mov     rcx, rax
0x180050900  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180050905  nop
0x180050906  mov     rcx, [rbp+90h+var_F0]
0x18005090a  mov     [rbp+90h+var_F0], r13
0x18005090e  test    rcx, rcx
0x180050911  jz      short loc_180050920
0x180050913  mov     rax, [rcx]
0x180050916  mov     rax, [rax+10h]
0x18005091a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005091f  nop
0x180050920  lea     rdx, [rbp+90h+var_F0]
0x180050924  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x180050929  mov     ebx, eax
0x18005092b  test    eax, eax
0x18005092d  jns     short loc_180050936
0x18005092f  mov     edx, 766h
0x180050934  jmp     short loc_18005097B
0x180050936  mov     rbx, [rbp+90h+var_F0]
0x18005093a  mov     rax, [rbx]
0x18005093d  mov     rsi, [rax+28h]
0x180050941  mov     rcx, [rsp+190h+var_140]
0x180050946  mov     [rsp+190h+var_140], r13
0x18005094b  test    rcx, rcx
0x18005094e  jz      short loc_18005095D
0x180050950  mov     r8, [rcx]
0x180050953  mov     rax, [r8+10h]
0x180050957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005095c  nop
0x18005095d  lea     r8, [rsp+190h+var_140]
0x180050962  mov     rdx, rdi
0x180050965  mov     rcx, rbx
0x180050968  mov     rax, rsi
0x18005096b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050970  mov     ebx, eax
0x180050972  test    eax, eax
0x180050974  jns     short loc_1800509CE
0x180050976  mov     edx, 767h; void *
0x18005097b  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180050982  mov     r9d, eax; char *
0x180050985  mov     rcx, [rbp+98h]; this
0x18005098c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050991  nop
0x180050992  test    r14, r14
0x180050995  jz      short loc_1800509A1
0x180050997  mov     rcx, r14; lpCriticalSection
0x18005099a  call    cs:__imp_LeaveCriticalSection
0x1800509a0  nop
0x1800509a1  lea     rcx, [rbp+90h+var_B0]
0x1800509a5  call    ?RemoveAll@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(void)
0x1800509aa  nop
0x1800509ab  lea     rcx, [rbp+90h+var_E8]
0x1800509af  call    ?RemoveAll@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(void)
0x1800509b4  nop
0x1800509b5  mov     rcx, [rsp+190h+pv]; pv
0x1800509ba  test    rcx, rcx
0x1800509bd  jz      loc_180051205
0x1800509c3  call    cs:__imp_CoTaskMemFree
0x1800509c9  jmp     loc_180051205
0x1800509ce  mov     rcx, [rsp+190h+var_130]
0x1800509d3  mov     [rsp+190h+var_130], r13
0x1800509d8  test    rcx, rcx
0x1800509db  jz      short loc_1800509EA
0x1800509dd  mov     rax, [rcx]
0x1800509e0  mov     rax, [rax+10h]
0x1800509e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509e9  nop
0x1800509ea  mov     rcx, [rsp+190h+var_140]
0x1800509ef  mov     rax, [rcx]
0x1800509f2  lea     r8, [rsp+190h+var_130]
0x1800509f7  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x1800509fe  mov     rax, [rax]
0x180050a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a06  mov     ebx, eax
0x180050a08  test    eax, eax
0x180050a0a  jns     short loc_180050A16
0x180050a0c  mov     edx, 768h
0x180050a11  jmp     loc_18005097B
0x180050a16  mov     rbx, [rsp+190h+var_130]
0x180050a1b  mov     rax, [rbx]
0x180050a1e  mov     rdi, [rax+18h]
0x180050a22  mov     rcx, [rsp+190h+var_128]
0x180050a27  mov     [rsp+190h+var_128], r13
0x180050a2c  test    rcx, rcx
0x180050a2f  jz      short loc_180050A3E
0x180050a31  mov     rax, [rcx]
0x180050a34  mov     rax, [rax+10h]
0x180050a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a3d  nop
0x180050a3e  lea     rax, [rsp+190h+var_128]
0x180050a43  mov     qword ptr [rsp+190h+var_170], rax
0x180050a48  xor     r9d, r9d
0x180050a4b  lea     r8d, [r9+17h]
0x180050a4f  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180050a56  mov     rcx, rbx
0x180050a59  mov     rax, rdi
0x180050a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a61  mov     ebx, eax
0x180050a63  test    eax, eax
0x180050a65  js      loc_180050992
0x180050a6b  mov     rdi, [rsp+190h+var_128]
0x180050a70  mov     rax, [rdi]
0x180050a73  mov     rbx, [rax+40h]
0x180050a77  xor     edx, edx
0x180050a79  lea     rcx, [rsp+190h+pv]
0x180050a7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180050a83  lea     rdx, [rsp+190h+pv]
0x180050a88  mov     rcx, rdi
0x180050a8b  mov     rax, rbx
0x180050a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a93  mov     ebx, eax
0x180050a95  test    eax, eax
0x180050a97  jns     short loc_180050AA3
0x180050a99  mov     edx, 76Eh
0x180050a9e  jmp     loc_18005097B
0x180050aa3  mov     rdx, [rsp+190h+pv]; unsigned __int16 *
0x180050aa8  lea     rcx, [rbp+90h+Buf1]; this
0x180050aac  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180050ab1  nop
0x180050ab2  lea     rdx, [rbp+90h+Buf1]
0x180050ab6  lea     rcx, [rbp+90h+var_E8]
0x180050aba  call    ?AddTail@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@AEBVCComBSTR@2@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(ATL::CComBSTR const &)
0x180050abf  nop
0x180050ac0  mov     rcx, qword ptr [rbp+90h+Buf1.Data1]
0x180050ac4  jmp     loc_180051026
0x180050ac9  lea     rdx, [rbp+90h+var_80]
0x180050acd  lea     rcx, [rbp+90h+var_E8]
0x180050ad1  call    ?RemoveHead@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAA?AVCComBSTR@2@XZ; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveHead(void)
0x180050ad6  nop
0x180050ad7  mov     [rbp+90h+var_110], r13d
0x180050adb  lea     rdx, [rbp+90h+var_80]
0x180050adf  lea     rcx, [rbp+90h+var_B0]
0x180050ae3  call    ?AddTail@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@AEBVCComBSTR@2@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(ATL::CComBSTR const &)
0x180050ae8  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180050aef  mov     rax, [r9]
0x180050af2  mov     rdi, [rax+28h]
0x180050af6  mov     rcx, [rsp+190h+var_130]
0x180050afb  mov     [rsp+190h+var_130], r13
0x180050b00  test    rcx, rcx
0x180050b03  jz      short loc_180050B18
0x180050b05  mov     rax, [rcx]
0x180050b08  mov     rax, [rax+10h]
0x180050b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b11  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180050b18  lea     r8, [rsp+190h+var_130]
0x180050b1d  mov     rbx, [rbp+90h+var_80]
0x180050b21  mov     rdx, rbx
0x180050b24  mov     rcx, r9
0x180050b27  mov     rax, rdi
0x180050b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b2f  mov     edi, eax
0x180050b31  test    eax, eax
0x180050b33  js      loc_18005115D
0x180050b39  mov     rdi, [rsp+190h+var_130]
0x180050b3e  mov     rax, [rdi]
0x180050b41  mov     rsi, [rax+18h]
0x180050b45  mov     rcx, [rsp+190h+var_128]
0x180050b4a  mov     [rsp+190h+var_128], r13
0x180050b4f  test    rcx, rcx
0x180050b52  jz      short loc_180050B61
0x180050b54  mov     rax, [rcx]
0x180050b57  mov     rax, [rax+10h]
0x180050b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b60  nop
0x180050b61  lea     rax, [rsp+190h+var_128]
0x180050b66  mov     qword ptr [rsp+190h+var_170], rax
0x180050b6b  xor     r9d, r9d
0x180050b6e  lea     r8d, [r9+17h]
0x180050b72  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180050b79  mov     rcx, rdi
0x180050b7c  mov     rax, rsi
0x180050b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b84  mov     edi, eax
0x180050b86  test    eax, eax
0x180050b88  js      loc_180051179
0x180050b8e  mov     rcx, [rsp+190h+var_128]
0x180050b93  mov     rax, [rcx]
0x180050b96  lea     rdx, [rbp+90h+var_110]
0x180050b9a  mov     rax, [rax+18h]
0x180050b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ba3  mov     edi, eax
0x180050ba5  test    eax, eax
0x180050ba7  js      loc_180051156
0x180050bad  mov     r12d, [rbp+90h+var_110]
0x180050bb1  jmp     loc_180051019
0x180050bb6  mov     [rsp+190h+var_158], r13
0x180050bbb  mov     [rbp+90h+var_10C], r13d
0x180050bbf  mov     rsi, [rsp+190h+var_128]
0x180050bc4  mov     rax, [rsi]
0x180050bc7  mov     rdi, [rax+20h]
0x180050bcb  lea     rcx, [rsp+190h+var_158]
0x180050bd0  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180050bd5  lea     r8, [rsp+190h+var_158]
0x180050bda  mov     edx, r12d
0x180050bdd  mov     rcx, rsi
0x180050be0  mov     rax, rdi
0x180050be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050be8  mov     edi, eax
0x180050bea  test    eax, eax
0x180050bec  js      loc_18005114F
0x180050bf2  mov     rcx, [rsp+190h+var_158]
0x180050bf7  mov     rax, [rcx]
0x180050bfa  lea     rdx, [rbp+90h+var_10C]
0x180050bfe  mov     rax, [rax+18h]
0x180050c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c07  mov     edi, eax
0x180050c09  test    eax, eax
0x180050c0b  js      loc_18005112F
0x180050c11  mov     ecx, [rbp+90h+var_10C]
0x180050c14  lea     eax, [rcx-1]
0x180050c17  cmp     eax, 1
0x180050c1a  jbe     loc_180050CEE
0x180050c20  cmp     ecx, 4
0x180050c23  jnz     loc_18005100F
0x180050c29  mov     qword ptr [rbp+90h+Buf1.Data1], r13
0x180050c2d  mov     rsi, [rsp+190h+var_158]
0x180050c32  mov     rax, [rsi]
0x180050c35  mov     rdi, [rax+50h]
0x180050c39  xor     edx, edx
0x180050c3b  lea     rcx, [rbp+90h+Buf1]
0x180050c3f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180050c44  lea     rdx, [rbp+90h+Buf1]
0x180050c48  mov     rcx, rsi
0x180050c4b  mov     rax, rdi
0x180050c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c53  test    eax, eax
0x180050c55  js      short loc_180050CD6
0x180050c57  mov     rdx, qword ptr [rbp+90h+Buf1.Data1]; unsigned __int16 *
0x180050c5b  lea     rcx, [rbp+90h+bstrString]; this
0x180050c5f  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180050c64  lea     rdx, [rbp+90h+bstrString]
0x180050c68  lea     rcx, [rbp+90h+var_B0]
0x180050c6c  call    ?Find@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@AEBVCComBSTR@2@PEAU3@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Find(ATL::CComBSTR const &,__POSITION *)
0x180050c71  mov     rdi, rax
0x180050c74  mov     rcx, [rbp+90h+bstrString]; bstrString
0x180050c78  call    cs:__imp_SysFreeString
0x180050c7e  mov     rdx, qword ptr [rbp+90h+Buf1.Data1]; unsigned __int16 *
0x180050c82  lea     rcx, [rbp+90h+var_70]; this
0x180050c86  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180050c8b  lea     rdx, [rbp+90h+var_70]
0x180050c8f  lea     rcx, [rbp+90h+var_E8]
0x180050c93  call    ?Find@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@AEBVCComBSTR@2@PEAU3@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Find(ATL::CComBSTR const &,__POSITION *)
0x180050c98  mov     rsi, rax
0x180050c9b  mov     rcx, [rbp+90h+var_70]; bstrString
0x180050c9f  call    cs:__imp_SysFreeString
0x180050ca5  test    rdi, rdi
0x180050ca8  jnz     short loc_180050CD6
0x180050caa  test    rsi, rsi
0x180050cad  jnz     short loc_180050CD6
0x180050caf  mov     rdx, qword ptr [rbp+90h+Buf1.Data1]; unsigned __int16 *
0x180050cb3  lea     rcx, [rbp+90h+var_B8]; this
0x180050cb7  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180050cbc  nop
0x180050cbd  lea     rdx, [rbp+90h+var_B8]
0x180050cc1  lea     rcx, [rbp+90h+var_E8]
0x180050cc5  call    ?AddTail@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@AEBVCComBSTR@2@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(ATL::CComBSTR const &)
0x180050cca  nop
  ... truncated ...
```
