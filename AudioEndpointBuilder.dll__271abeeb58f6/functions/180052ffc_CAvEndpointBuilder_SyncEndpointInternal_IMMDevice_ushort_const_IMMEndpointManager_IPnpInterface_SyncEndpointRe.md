# CAvEndpointBuilder::SyncEndpointInternal(IMMDevice *,ushort const *,IMMEndpointManager *,IPnpInterface * *,SyncEndpointReturnType &,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009 &)

- ea: `0x180052ffc`
- end: `0x180054078`
- name: `?SyncEndpointInternal@CAvEndpointBuilder@@QEAAJPEAUIMMDevice@@PEBGPEAUIMMEndpointManager@@PEAPEAUIPnpInterface@@AEAW4SyncEndpointReturnType@@AEAW4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009@@@Z`
- size: `4220`
- prototype: `__int64 __usercall@<rax>(CAvEndpointBuilder *__hidden this@<rcx>, struct IMMDevice *@<rdx>, const unsigned __int16 *@<r8>, struct IMMEndpointManager *@<r9>, struct IPnpInterface **, enum SyncEndpointReturnType *, enum __MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009 *)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e43c`

## callees

- `0x1800018d0`
- `0x1800035d0`
- `0x180006b0c`
- `0x1800076f0`
- `0x180008404`
- `0x180009650`
- `0x18000ecf0`
- `0x18000fb60`
- `0x1800105c0`
- `0x180010da8`
- `0x18001ef04`
- `0x18001f374`
- `0x180020c30`
- `0x180021030`
- `0x180023c10`
- `0x180023d28`
- `0x180024ca0`
- `0x180024d54`
- `0x180025340`
- `0x180029024`
- `0x180029cd0`
- `0x18002a824`
- `0x18002aa54`
- `0x18002ab90`
- `0x18002eb80`
- `0x180034c5c`
- `0x18003e920`
- `0x18004907c`
- `0x18004a344`
- `0x18004f474`
- `0x180052ffc`
- `0x18005419c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005317e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053241`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053b9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053c6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053f2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053faf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005317e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053241`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053b9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053c6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053f2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053faf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800530bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800530bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005319f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800531ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800531b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800531c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800531cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053262`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005326e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053279`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053284`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005328f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053bbc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053bc8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053bd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053bde`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053be9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053c90`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053c9c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053ca7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053cb2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053cbd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f4f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f5b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f66`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f71`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f7c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053fd0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053fdc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053fe7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053ff2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053ffd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005319f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800531ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800531b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800531c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800531cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053262`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005326e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053279`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053284`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005328f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053bbc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053bc8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053bd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053bde`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053be9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053c90`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053c9c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053ca7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053cb2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053cbd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f4f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f5b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f66`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f71`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f7c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053fd0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053fdc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053fe7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053ff2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053ffd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800531ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800532af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800537fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053c05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800531ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800532af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800537fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053c05`

## string_xrefs

- `0x180053164`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18005322c`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180053317`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18005388c`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180053968`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800539b2`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180053c50`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180053e46`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180053f0a`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CAvEndpointBuilder::SyncEndpointInternal(
        struct _RTL_CRITICAL_SECTION *this,
        struct IMMDevice *a2,
        unsigned __int16 *a3,
        struct IMMEndpointManager *a4,
        struct IPnpInterface **a5,
        enum SyncEndpointReturnType *a6,
        enum __MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009 *a7)
{
  const struct _tlgProvider_t *v10; // rax
  int v11; // r8d
  int v12; // r9d
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  struct IPropertyStore *v14; // rdx
  int v15; // eax
  int v16; // edi
  unsigned int v17; // ebx
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  wil::details::in1diag3 *v21; // rcx
  const struct _tlgProvider_t *v22; // rax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rcx
  LPVOID v27; // rcx
  LPVOID v28; // rbx
  __int64 (__fastcall *v29)(LPVOID, _QWORD, int *); // r12
  __int64 v30; // rcx
  const struct _tlgProvider_t *v31; // rax
  __int64 v32; // rcx
  const struct _tlgProvider_t *v33; // rax
  int v34; // r8d
  int v35; // r9d
  HRESULT (__stdcall *Activate)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rbx
  __int64 v37; // rcx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, _QWORD, struct IConnector **); // rbx
  int v40; // r15d
  struct IConnector *v41; // rdi
  HRESULT (__stdcall *GetDeviceIdConnectedTo)(IConnector *, LPWSTR *); // rbx
  struct IUnknown *v43; // r9
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  struct IMMDevice *v45; // rcx
  unsigned __int16 *v46; // rbx
  int v47; // eax
  const struct _tlgProvider_t *v48; // rax
  int v49; // r9d
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, struct IPnpDevnode **); // rbx
  struct IMMDevice *v52; // rdi
  int v53; // eax
  __int64 v54; // rdx
  struct IConnector *v55; // rdi
  HRESULT (__stdcall *GetConnectedTo)(IConnector *, IConnector **); // rbx
  int v57; // eax
  __int64 v58; // rdx
  struct IMMDevice *v59; // r12
  __int64 v60; // rcx
  const struct _tlgProvider_t *v61; // rax
  int v62; // eax
  unsigned int v63; // r14d
  int *v65; // [rsp+20h] [rbp-E0h]
  int v66; // [rsp+20h] [rbp-E0h]
  bool v67; // [rsp+40h] [rbp-C0h] BYREF
  struct IPropertyStore *v68; // [rsp+48h] [rbp-B8h] BYREF
  struct IMMDevice *v69; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v72; // [rsp+68h] [rbp-98h] BYREF
  int v73[2]; // [rsp+70h] [rbp-90h] BYREF
  PROPVARIANT v74[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v75; // [rsp+88h] [rbp-78h]
  PROPVARIANT pvar[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v77; // [rsp+A0h] [rbp-60h]
  PROPVARIANT v78[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v79; // [rsp+B8h] [rbp-48h]
  PROPVARIANT v80[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-30h]
  PROPVARIANT v82[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v83; // [rsp+E8h] [rbp-18h]
  int v84; // [rsp+F0h] [rbp-10h] BYREF
  struct IPnpInterface *v85; // [rsp+F8h] [rbp-8h] BYREF
  struct IConnector *v86; // [rsp+100h] [rbp+0h] BYREF
  struct IConnector *v87; // [rsp+108h] [rbp+8h] BYREF
  struct IPnpDevnode *v88; // [rsp+110h] [rbp+10h] BYREF
  __int64 v89; // [rsp+118h] [rbp+18h] BYREF
  __int64 v90; // [rsp+120h] [rbp+20h] BYREF
  int v91[2]; // [rsp+128h] [rbp+28h] BYREF
  struct IMMDevice *v92; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v93; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 *v94; // [rsp+140h] [rbp+40h] BYREF
  struct IMMEndpointManager *v95; // [rsp+148h] [rbp+48h]
  struct _RTL_CRITICAL_SECTION *v96; // [rsp+150h] [rbp+50h]
  __int128 v97; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v95 = a4;
  v93 = a3;
  v92 = a2;
  v72 = a2;
  v94 = (unsigned __int16 *)a5;
  v85 = a7;
  *(_QWORD *)v91 = 0;
  v87 = 0;
  v86 = 0;
  v88 = 0;
  v90 = 0;
  v89 = 0;
  pv = 0;
  v69 = 0;
  v84 = 0;
  *(_OWORD *)v80 = 0;
  v81 = 0;
  *(_OWORD *)v78 = 0;
  v79 = 0;
  *(_OWORD *)v82 = 0;
  v83 = 0;
  *(_OWORD *)v74 = 0;
  v75 = 0;
  *(_OWORD *)pvar = 0;
  v77 = 0;
  v68 = 0;
  v97 = 0;
  v71 = 0;
  EnterCriticalSection(this);
  v96 = this;
  v10 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v10 > 4u )
  {
    *(_QWORD *)v73 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v10,
      (unsigned int)&unk_180076348,
      v11,
      v12,
      (__int64)v73);
  }
  *(_DWORD *)a6 = 3;
  OpenPropertyStore = a2->lpVtbl->OpenPropertyStore;
  v14 = v68;
  v68 = 0;
  if ( v14 )
    ((void (__fastcall *)(struct IPropertyStore *))v14->lpVtbl->Release)(v14);
  v15 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, struct IPropertyStore **))OpenPropertyStore)(a2, 2, &v68);
  v16 = v15;
  v17 = -2147024894;
  if ( v15 == -2147024894 )
  {
    *(_DWORD *)a6 = 0;
    v18 = 2147942402LL;
    v19 = 4502;
LABEL_16:
    v21 = retaddr;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      v21,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)v18,
      (int)v65);
LABEL_18:
    if ( this )
      LeaveCriticalSection(this);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
    PropVariantClear(pvar);
    PropVariantClear(v74);
    PropVariantClear(v82);
    PropVariantClear(v78);
    PropVariantClear(v80);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_191;
  }
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1197,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v15,
      (int)v65);
LABEL_9:
    if ( this )
      LeaveCriticalSection(this);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
    PropVariantClear(pvar);
    PropVariantClear(v74);
    PropVariantClear(v82);
    PropVariantClear(v78);
    PropVariantClear(v80);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
    if ( pv )
      CoTaskMemFree(pv);
LABEL_190:
    v17 = v16;
    goto LABEL_191;
  }
  v20 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v68->lpVtbl->GetValue)(
          v68,
          &DEVPKEY_AudioEndpointPlugin_FactoryCLSID,
          v82);
  v17 = v20;
  if ( v20 < 0 )
  {
    v19 = 4507;
LABEL_15:
    v18 = (unsigned int)v20;
    goto LABEL_16;
  }
  if ( LOWORD(v82[0]) == 72 )
  {
    v72 = 0;
    *(_QWORD *)v73 = 0;
    v22 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v22 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v22,
        &word_18007630E);
    v23 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v68->lpVtbl->GetValue)(
            v68,
            &DEVPKEY_AudioEndpointPlugin_PnPInterface,
            v80);
    v17 = v23;
    if ( v23 < 0 )
    {
      v24 = 4523;
LABEL_27:
      v25 = (unsigned int)v23;
LABEL_28:
      *(_DWORD *)a6 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)v25,
        (int)v65);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v73);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
      goto LABEL_18;
    }
    if ( LOWORD(v80[0]) != 31 )
    {
      v17 = -2147418113;
      v25 = 2147549183LL;
      v24 = 4524;
      goto LABEL_28;
    }
    v26 = v90;
    v90 = 0;
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v26, &v90);
    v23 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT, struct IPnpInterface **))(*(_QWORD *)v90 + 40LL))(
            v90,
            v80[1],
            a5);
    v17 = v23;
    if ( v23 < 0 )
    {
      v24 = 4531;
      goto LABEL_27;
    }
    v27 = v72;
    v72 = 0;
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    v23 = wil::com_query_to_nothrow<IMMDevice,IPnpDevnode * &>(a5, &v72);
    v17 = v23;
    if ( v23 < 0 )
    {
      v24 = 4533;
      goto LABEL_27;
    }
    v28 = v72;
    v29 = *(__int64 (__fastcall **)(LPVOID, _QWORD, int *))(*(_QWORD *)v72 + 32LL);
    v30 = *(_QWORD *)v73;
    *(_QWORD *)v73 = 0;
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v23 = v29(v28, 0, v73);
    v17 = v23;
    if ( v23 < 0 )
    {
      v24 = 4536;
      goto LABEL_27;
    }
    v23 = (*(__int64 (__fastcall **)(_QWORD, const DEVPROPKEY *, PROPVARIANT *))(**(_QWORD **)v73 + 40LL))(
            *(_QWORD *)v73,
            &DEVPKEY_DeviceInterface_Enabled,
            v74);
    v17 = v23;
    if ( v23 < 0 )
    {
      v24 = 4541;
      goto LABEL_27;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    CAvEndpointBuilder::MigrateUpgradeProperties((CAvEndpointBuilder *)this, a2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    if ( LOWORD(v74[0]) != 11 || !LOWORD(v74[1]) )
    {
      *(_DWORD *)a6 = 1;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v73);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
      goto LABEL_9;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v73);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
LABEL_187:
    if ( this )
      LeaveCriticalSection(this);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
    PropVariantClear(pvar);
    PropVariantClear(v74);
    PropVariantClear(v82);
    PropVariantClear(v78);
    PropVariantClear(v80);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    goto LABEL_190;
  }
  v31 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v31 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v31,
      &dword_1800762D4);
  v32 = v89;
  v89 = 0;
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  v20 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
          &v72,
          &v89);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4562;
    goto LABEL_15;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v89 + 32LL))(v89, &v84);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4565;
    goto LABEL_15;
  }
  if ( (v84 & 0x40000000) != 0 )
  {
    v33 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v33 > 2u )
    {
      v73[0] = 4582;
      v93 = (unsigned __int16 *)"CAvEndpointBuilder::SyncEndpointInternal";
      v92 = (struct IMMDevice *)a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v33,
        (unsigned int)word_18007627A,
        v34,
        v35,
        (__int64)&v92,
        (__int64)&v93,
        (__int64)v73);
    }
    *(_DWORD *)a6 = 0;
    v17 = -2147467259;
    v18 = 2147500037LL;
    v19 = 4586;
    goto LABEL_16;
  }
  Activate = a2->lpVtbl->Activate;
  v37 = *(_QWORD *)v91;
  *(_QWORD *)v91 = 0;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  v65 = v91;
  v20 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))Activate)(
          a2,
          &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
          23);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 0;
    v19 = 4590;
    goto LABEL_15;
  }
  v38 = *(_QWORD *)v91;
  v39 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IConnector **))(**(_QWORD **)v91 + 32LL);
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v87);
  v20 = v39(v38, 0, &v87);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 0;
    v19 = 4593;
    goto LABEL_15;
  }
  v20 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v68->lpVtbl->GetValue)(
          v68,
          &PKEY_AudioEndpoint_FormFactor,
          pvar);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4595;
    goto LABEL_15;
  }
  if ( LOWORD(pvar[0]) != 19 )
  {
    *(_DWORD *)a6 = 0;
    v17 = -2147467259;
    v18 = 2147500037LL;
    v19 = 4596;
    goto LABEL_16;
  }
  v40 = (int)pvar[1];
  v73[0] = (int)pvar[1];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  v41 = v87;
  GetDeviceIdConnectedTo = v87->lpVtbl->GetDeviceIdConnectedTo;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v20 = ((__int64 (__fastcall *)(struct IConnector *, LPVOID *))GetDeviceIdConnectedTo)(v41, &pv);
  v17 = v20;
  if ( v20 < 0 )
  {
    if ( v40 != 9 )
    {
      *(_DWORD *)a6 = 0;
      v19 = 4611;
      goto LABEL_15;
    }
    v20 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v68->lpVtbl->GetValue)(
            v68,
            PKEY_Endpoint_DeviceIdSaveConnectedTo,
            v78);
    v17 = v20;
    if ( v20 < 0 )
    {
      *(_DWORD *)a6 = 0;
      v19 = 4614;
      goto LABEL_15;
    }
    if ( LOWORD(v78[0]) != 31 )
    {
      *(_DWORD *)a6 = 0;
      v17 = -2147418113;
      v18 = 2147549183LL;
      v19 = 4615;
      goto LABEL_16;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v72,
      v78[1],
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pv,
      &v72);
    if ( v72 )
      CoTaskMemFree(v72);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, pv);
  }
  v43 = g_DeviceEnumerator;
  Release = g_DeviceEnumerator->lpVtbl[1].Release;
  v45 = v69;
  v69 = 0;
  if ( v45 )
  {
    ((void (__fastcall *)(struct IMMDevice *))v45->lpVtbl->Release)(v45);
    v43 = g_DeviceEnumerator;
  }
  v20 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, struct IMMDevice **))Release)(v43, pv, &v69);
  v17 = v20;
  if ( v20 == -536870363 )
  {
    v21 = retaddr;
    v17 = -536870363;
    v18 = 3758096933LL;
    if ( v40 == 9 )
    {
      *(_DWORD *)a6 = 2;
      *(_DWORD *)v85 = 16;
      v19 = 4630;
    }
    else
    {
      *(_DWORD *)a6 = 0;
      v19 = 4629;
    }
    goto LABEL_17;
  }
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4631;
    goto LABEL_15;
  }
  v46 = v94;
  wil::com_query_to_nothrow<IPnpInterface,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(&v69, v94);
  if ( !*(_QWORD *)v46 )
  {
    *(_DWORD *)a6 = 1;
    if ( !*(_QWORD *)v46 )
    {
      v17 = -2147467262;
      v18 = 2147500034LL;
      v19 = 4635;
      goto LABEL_16;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  v47 = ((__int64 (__fastcall *)(struct IMMDevice *, int *))v69->lpVtbl->GetState)(v69, &v84);
  LODWORD(v72) = v47;
  if ( v47 == -536870363 )
  {
    v21 = retaddr;
    v17 = -536870363;
    v18 = 3758096933LL;
    if ( v73[0] == 9 )
    {
      *(_DWORD *)a6 = 2;
      *(_DWORD *)v85 = 16;
      v19 = 4643;
    }
    else
    {
      *(_DWORD *)a6 = 0;
      v19 = 4642;
    }
    goto LABEL_17;
  }
  if ( v47 < 0 )
  {
    *(_DWORD *)a6 = 1;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1224,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v47,
      (int)v91);
LABEL_141:
    if ( this )
      LeaveCriticalSection(this);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
    PropVariantClear(pvar);
    PropVariantClear(v74);
    PropVariantClear(v82);
    PropVariantClear(v78);
    PropVariantClear(v80);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
    if ( pv )
      CoTaskMemFree(pv);
    v17 = (unsigned int)v72;
    goto LABEL_191;
  }
  if ( v84 != 1 )
  {
    v48 = AudioEndpointBuilderTelemetryProvider::Provider();
    v17 = (unsigned int)v72;
    if ( *(_DWORD *)v48 > 4u )
    {
      v73[0] = (int)v72;
      LODWORD(v72) = v84;
      v94 = v93;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v48,
        (unsigned int)&dword_18007620C,
        (_DWORD)v93,
        v49,
        (__int64)&v94,
        (__int64)&v72,
        (__int64)v73);
    }
    *(_DWORD *)a6 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    goto LABEL_18;
  }
  v50 = *(_QWORD *)v46;
  v51 = *(__int64 (__fastcall **)(__int64, struct IPnpDevnode **))(**(_QWORD **)v46 + 24LL);
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v88);
  v20 = v51(v50, &v88);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4664;
    goto LABEL_15;
  }
  v67 = 1;
  v52 = v92;
  v20 = CheckDriverStrongNamesMatch(v92, v88, &v67);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4672;
    goto LABEL_15;
  }
  if ( !v67 )
    goto LABEL_129;
  v20 = CheckDriverInstallTimesMatch(v52, v88, &v67);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4683;
    goto LABEL_15;
  }
  if ( !v67 )
  {
LABEL_129:
    *(_DWORD *)a6 = 2;
    *(_DWORD *)v85 = 8;
    goto LABEL_141;
  }
  v20 = CAvEndpointBuilder::CheckEndpointVersionMatch((CAvEndpointBuilder *)this, v52, &v67);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4687;
    goto LABEL_15;
  }
  if ( !v67 )
  {
    *(_DWORD *)a6 = 2;
    *(_DWORD *)v85 = 2;
    goto LABEL_141;
  }
  v20 = CheckUSBDriverRevisionMatch(v52, v88, &v67);
  v17 = v20;
  if ( v20 < 0 )
  {
    *(_DWORD *)a6 = 1;
    v19 = 4690;
    goto LABEL_15;
  }
  if ( !v67 )
  {
    *(_DWORD *)a6 = 2;
    *(_DWORD *)v85 = 4;
    goto LABEL_141;
  }
  if ( v73[0] == 9 )
  {
    v53 = CAvEndpointBuilder::VerifyDisplayDeviceConnectorState((CAvEndpointBuilder *)this, v52, v87, v69);
    v17 = v53;
    if ( v53 != -2005139373 && v53 < 0 )
    {
      v54 = 4706;
LABEL_150:
      *(_DWORD *)a6 = 1;
LABEL_151:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v54,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v53,
        (int)v91);
LABEL_152:
      if ( this )
        LeaveCriticalSection(this);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
      PropVariantClear(pvar);
      PropVariantClear(v74);
      PropVariantClear(v82);
      PropVariantClear(v78);
      PropVariantClear(v80);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
      goto LABEL_191;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  v55 = v87;
  GetConnectedTo = v87->lpVtbl->GetConnectedTo;
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v86);
  v53 = ((__int64 (__fastcall *)(struct IConnector *, struct IConnector **))GetConnectedTo)(v55, &v86);
  v17 = v53;
  if ( v53 < 0 )
  {
    v54 = 4713;
    goto LABEL_150;
  }
  v57 = VerifyConnectorsAreMutuallyConnected(v87, v86);
  v16 = v57;
  if ( v73[0] == 9 )
  {
    if ( v57 < 0 )
    {
      *(_DWORD *)a6 = 1;
      v58 = 4722;
      goto LABEL_177;
    }
  }
  else if ( v57 < 0 )
  {
    *(_DWORD *)a6 = 0;
    v58 = 4726;
    goto LABEL_177;
  }
  v59 = v92;
  v53 = VerifyFlowAndTypesMatch(v92, v86);
  v17 = v53;
  if ( v53 < 0 )
  {
    *(_DWORD *)a6 = 0;
    v54 = 4732;
    goto LABEL_151;
  }
  v60 = v71;
  v71 = 0;
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  ((void (__fastcall *)(struct IConnector *, GUID *, __int64 *))v86->lpVtbl->QueryInterface)(
    v86,
    &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
    &v71);
  v53 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v71 + 56LL))(v71, &v97);
  v17 = v53;
  if ( v53 < 0 )
  {
    v54 = 4735;
    goto LABEL_150;
  }
  v53 = CheckEndpointConfigIdMatch(v59, &v67);
  v17 = v53;
  if ( v53 < 0 )
  {
    v54 = 4741;
    goto LABEL_150;
  }
  if ( !v67 )
  {
    *(_DWORD *)a6 = 2;
    *(_DWORD *)v85 = 32;
    if ( v16 >= 0 )
      goto LABEL_187;
    v58 = 4743;
LABEL_177:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v58,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v16,
      (int)v91);
    goto LABEL_187;
  }
  VerifyAdapterFriendlyName(v59, v69);
  v85 = 0;
  ((void (__fastcall *)(struct IMMDevice *, GUID *, struct IPnpInterface **))v69->lpVtbl->QueryInterface)(
    v69,
    &GUID_3ade56af_4375_4413_9c91_4c652595ab07,
    &v85);
  v61 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v61 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v61,
      byte_1800761C5);
  v62 = CAvEndpointBuilder::EndpointRTM((CAvEndpointBuilder *)this, v59, v93, v68, v86, v85, v95, a6);
  v63 = v62;
  if ( v62 >= 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v85);
    goto LABEL_187;
  }
  v17 = -2147023728;
  if ( v62 == -2147023728 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v85);
    goto LABEL_152;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12A5,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v62,
    v66);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v85);
  if ( this )
    LeaveCriticalSection(this);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
  PropVariantClear(pvar);
  PropVariantClear(v74);
  PropVariantClear(v82);
  PropVariantClear(v78);
  PropVariantClear(v80);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
  v17 = v63;
LABEL_191:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v89);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v90);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v88);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v86);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v87);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v91);
  return v17;
}

```

## disassembly

```asm
0x180052ffc  push    rbp
0x180052ffe  push    rbx
0x180052fff  push    rsi
0x180053000  push    rdi
0x180053001  push    r12
0x180053003  push    r13
0x180053005  push    r14
0x180053007  push    r15
0x180053009  lea     rbp, [rsp-78h]
0x18005300e  sub     rsp, 178h
0x180053015  mov     rax, cs:__security_cookie
0x18005301c  xor     rax, rsp
0x18005301f  mov     [rbp+0B0h+var_48], rax
0x180053023  mov     [rbp+0B0h+var_68], r9
0x180053027  mov     r13, r8
0x18005302a  mov     [rbp+0B0h+var_78], r8
0x18005302e  mov     r15, rdx
0x180053031  mov     [rbp+0B0h+var_80], rdx
0x180053035  mov     rsi, rcx
0x180053038  mov     [rsp+1B0h+var_148], rdx
0x18005303d  mov     r12, [rbp+0B0h+arg_20]
0x180053044  mov     [rbp+0B0h+var_70], r12
0x180053048  mov     r14, [rbp+0B0h+arg_28]
0x18005304f  mov     rax, [rbp+0B0h+arg_30]
0x180053056  mov     [rbp+0B0h+var_B8], rax
0x18005305a  xor     edi, edi
0x18005305c  mov     qword ptr [rbp+0B0h+var_88], rdi
0x180053060  mov     [rbp+0B0h+var_A8], rdi
0x180053064  mov     [rbp+0B0h+var_B0], rdi
0x180053068  mov     [rbp+0B0h+var_A0], rdi
0x18005306c  mov     [rbp+0B0h+var_90], rdi
0x180053070  mov     [rbp+0B0h+var_98], rdi
0x180053074  mov     [rsp+1B0h+pv], rdi
0x180053079  mov     [rsp+1B0h+var_160], rdi
0x18005307e  mov     [rbp+0B0h+var_C0], edi
0x180053081  xorps   xmm0, xmm0
0x180053084  xor     eax, eax
0x180053086  movups  xmmword ptr [rbp+0B0h+var_F0], xmm0
0x18005308a  mov     [rbp+0B0h+var_E0], rax
0x18005308e  movups  xmmword ptr [rbp+0B0h+var_108], xmm0
0x180053092  mov     [rbp+0B0h+var_F8], rax
0x180053096  movups  xmmword ptr [rbp+0B0h+var_D8], xmm0
0x18005309a  mov     [rbp+0B0h+var_C8], rax
0x18005309e  movups  xmmword ptr [rsp+1B0h+var_138], xmm0
0x1800530a3  mov     [rbp+0B0h+var_128], rax
0x1800530a7  movups  xmmword ptr [rbp+0B0h+pvar], xmm0
0x1800530ab  mov     [rbp+0B0h+var_110], rax
0x1800530af  mov     [rsp+1B0h+var_168], rdi
0x1800530b4  movups  [rbp+0B0h+var_58], xmm0
0x1800530b8  mov     [rsp+1B0h+var_150], rdi
0x1800530bd  call    cs:__imp_EnterCriticalSection
0x1800530c3  mov     [rbp+0B0h+var_60], rsi
0x1800530c7  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800530cc  mov     ecx, [rax]
0x1800530ce  cmp     ecx, 4
0x1800530d1  jbe     short loc_1800530F1
0x1800530d3  mov     qword ptr [rsp+1B0h+var_140], r13
0x1800530d8  lea     rcx, [rsp+1B0h+var_140]
0x1800530dd  mov     [rsp+1B0h+var_190], rcx; int
0x1800530e2  lea     rdx, unk_180076348
0x1800530e9  mov     rcx, rax
0x1800530ec  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800530f1  mov     dword ptr [r14], 3
0x1800530f8  mov     rax, [r15]
0x1800530fb  mov     rbx, [rax+20h]
0x1800530ff  mov     rdx, [rsp+1B0h+var_168]
0x180053104  mov     [rsp+1B0h+var_168], rdi
0x180053109  test    rdx, rdx
0x18005310c  jz      short loc_18005311E
0x18005310e  mov     rcx, [rdx]
0x180053111  mov     rax, [rcx+10h]
0x180053115  mov     rcx, rdx
0x180053118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005311d  nop
0x18005311e  lea     r8, [rsp+1B0h+var_168]
0x180053123  mov     edx, 2
0x180053128  mov     rcx, r15
0x18005312b  mov     rax, rbx
0x18005312e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053133  mov     edi, eax
0x180053135  mov     ebx, 80070002h
0x18005313a  cmp     eax, ebx
0x18005313c  jnz     short loc_180053152
0x18005313e  mov     dword ptr [r14], 0
0x180053145  mov     r9d, ebx
0x180053148  mov     edx, 1196h
0x18005314d  jmp     loc_180053225
0x180053152  test    edi, edi
0x180053154  jns     loc_1800531F7
0x18005315a  mov     rcx, [rbp+0B8h]; this
0x180053161  mov     r9d, edi; char *
0x180053164  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18005316b  mov     edx, 1197h; void *
0x180053170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053175  nop
0x180053176  test    rsi, rsi
0x180053179  jz      short loc_180053185
0x18005317b  mov     rcx, rsi; lpCriticalSection
0x18005317e  call    cs:__imp_LeaveCriticalSection
0x180053184  nop
0x180053185  lea     rcx, [rsp+1B0h+var_150]
0x18005318a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005318f  nop
0x180053190  lea     rcx, [rsp+1B0h+var_168]
0x180053195  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005319a  nop
0x18005319b  lea     rcx, [rbp+0B0h+pvar]; pvar
0x18005319f  call    cs:__imp_PropVariantClear
0x1800531a5  nop
0x1800531a6  lea     rcx, [rsp+1B0h+var_138]; pvar
0x1800531ab  call    cs:__imp_PropVariantClear
0x1800531b1  nop
0x1800531b2  lea     rcx, [rbp+0B0h+var_D8]; pvar
0x1800531b6  call    cs:__imp_PropVariantClear
0x1800531bc  nop
0x1800531bd  lea     rcx, [rbp+0B0h+var_108]; pvar
0x1800531c1  call    cs:__imp_PropVariantClear
0x1800531c7  nop
0x1800531c8  lea     rcx, [rbp+0B0h+var_F0]; pvar
0x1800531cc  call    cs:__imp_PropVariantClear
0x1800531d2  nop
0x1800531d3  lea     rcx, [rsp+1B0h+var_160]
0x1800531d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800531dd  nop
0x1800531de  mov     rcx, [rsp+1B0h+pv]; pv
0x1800531e3  test    rcx, rcx
0x1800531e6  jz      loc_180054019
0x1800531ec  call    cs:__imp_CoTaskMemFree
0x1800531f2  jmp     loc_180054019
0x1800531f7  mov     rcx, [rsp+1B0h+var_168]
0x1800531fc  mov     rax, [rcx]
0x1800531ff  lea     r8, [rbp+0B0h+var_D8]
0x180053203  lea     rdx, DEVPKEY_AudioEndpointPlugin_FactoryCLSID
0x18005320a  mov     rax, [rax+28h]
0x18005320e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053213  mov     ebx, eax
0x180053215  test    eax, eax
0x180053217  jns     loc_1800532BA
0x18005321d  mov     edx, 119Bh; void *
0x180053222  mov     r9d, eax; char *
0x180053225  mov     rcx, [rbp+0B8h]; this
0x18005322c  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180053233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053238  nop
0x180053239  test    rsi, rsi
0x18005323c  jz      short loc_180053248
0x18005323e  mov     rcx, rsi; lpCriticalSection
0x180053241  call    cs:__imp_LeaveCriticalSection
0x180053247  nop
0x180053248  lea     rcx, [rsp+1B0h+var_150]
0x18005324d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180053252  nop
0x180053253  lea     rcx, [rsp+1B0h+var_168]
0x180053258  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005325d  nop
0x18005325e  lea     rcx, [rbp+0B0h+pvar]; pvar
0x180053262  call    cs:__imp_PropVariantClear
0x180053268  nop
0x180053269  lea     rcx, [rsp+1B0h+var_138]; pvar
0x18005326e  call    cs:__imp_PropVariantClear
0x180053274  nop
0x180053275  lea     rcx, [rbp+0B0h+var_D8]; pvar
0x180053279  call    cs:__imp_PropVariantClear
0x18005327f  nop
0x180053280  lea     rcx, [rbp+0B0h+var_108]; pvar
0x180053284  call    cs:__imp_PropVariantClear
0x18005328a  nop
0x18005328b  lea     rcx, [rbp+0B0h+var_F0]; pvar
0x18005328f  call    cs:__imp_PropVariantClear
0x180053295  nop
0x180053296  lea     rcx, [rsp+1B0h+var_160]
0x18005329b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800532a0  nop
0x1800532a1  mov     rcx, [rsp+1B0h+pv]; pv
0x1800532a6  test    rcx, rcx
0x1800532a9  jz      loc_18005401B
0x1800532af  call    cs:__imp_CoTaskMemFree
0x1800532b5  jmp     loc_18005401B
0x1800532ba  cmp     word ptr [rbp+0B0h+var_D8], 48h ; 'H'
0x1800532bf  jnz     loc_180053525
0x1800532c5  xor     r13d, r13d
0x1800532c8  mov     [rsp+1B0h+var_148], r13
0x1800532cd  mov     qword ptr [rsp+1B0h+var_140], r13
0x1800532d2  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800532d7  mov     ecx, [rax]
0x1800532d9  cmp     ecx, 4
0x1800532dc  jbe     short loc_1800532ED
0x1800532de  lea     rdx, word_18007630E
0x1800532e5  mov     rcx, rax
0x1800532e8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800532ed  mov     rcx, [rsp+1B0h+var_168]
0x1800532f2  mov     rax, [rcx]
0x1800532f5  lea     r8, [rbp+0B0h+var_F0]
0x1800532f9  lea     rdx, DEVPKEY_AudioEndpointPlugin_PnPInterface
0x180053300  mov     rax, [rax+28h]
0x180053304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053309  mov     ebx, eax
0x18005330b  test    eax, eax
0x18005330d  jns     short loc_180053348
0x18005330f  mov     edx, 11ABh; void *
0x180053314  mov     r9d, eax; char *
0x180053317  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18005331e  mov     rcx, [rbp+0B8h]; this
0x180053325  mov     [r14], r13d
0x180053328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005332d  nop
0x18005332e  lea     rcx, [rsp+1B0h+var_140]
0x180053333  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180053338  nop
0x180053339  lea     rcx, [rsp+1B0h+var_148]
0x18005333e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180053343  jmp     loc_180053239
0x180053348  mov     eax, 1Fh
0x18005334d  cmp     word ptr [rbp+0B0h+var_F0], ax
0x180053351  jz      short loc_180053362
0x180053353  mov     ebx, 8000FFFFh
0x180053358  mov     r9d, ebx
0x18005335b  mov     edx, 11ACh
0x180053360  jmp     short loc_180053317
0x180053362  mov     rcx, [rbp+0B0h+var_90]
0x180053366  mov     [rbp+0B0h+var_90], r13
0x18005336a  test    rcx, rcx
0x18005336d  jz      short loc_18005337C
0x18005336f  mov     rax, [rcx]
0x180053372  mov     rax, [rax+10h]
0x180053376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005337b  nop
0x18005337c  lea     rdx, [rbp+0B0h+var_90]
0x180053380  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x180053385  mov     rcx, [rbp+0B0h+var_90]
0x180053389  mov     rax, [rcx]
0x18005338c  mov     r8, r12
0x18005338f  mov     rdx, [rbp+0B0h+var_F0+8]
0x180053393  mov     rax, [rax+28h]
0x180053397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005339c  mov     ebx, eax
0x18005339e  test    eax, eax
0x1800533a0  jns     short loc_1800533AC
0x1800533a2  mov     edx, 11B3h
0x1800533a7  jmp     loc_180053314
0x1800533ac  mov     rcx, [rsp+1B0h+var_148]
0x1800533b1  mov     [rsp+1B0h+var_148], r13
0x1800533b6  test    rcx, rcx
0x1800533b9  jz      short loc_1800533C8
0x1800533bb  mov     rax, [rcx]
0x1800533be  mov     rax, [rax+10h]
0x1800533c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533c7  nop
0x1800533c8  lea     rdx, [rsp+1B0h+var_148]
0x1800533cd  mov     rcx, r12
0x1800533d0  call    ??$com_query_to_nothrow@UIMMDevice@@AEAPEAUIPnpDevnode@@@wil@@YAJAEAPEAUIPnpDevnode@@PEAPEAUIMMDevice@@@Z; wil::com_query_to_nothrow<IMMDevice,IPnpDevnode * &>(IPnpDevnode * &,IMMDevice * *)
0x1800533d5  mov     ebx, eax
0x1800533d7  test    eax, eax
0x1800533d9  jns     short loc_1800533E5
0x1800533db  mov     edx, 11B5h
0x1800533e0  jmp     loc_180053314
0x1800533e5  mov     rbx, [rsp+1B0h+var_148]
0x1800533ea  mov     rax, [rbx]
0x1800533ed  mov     r12, [rax+20h]
0x1800533f1  mov     rcx, qword ptr [rsp+1B0h+var_140]
0x1800533f6  mov     qword ptr [rsp+1B0h+var_140], r13
0x1800533fb  test    rcx, rcx
0x1800533fe  jz      short loc_18005340D
0x180053400  mov     rdx, [rcx]
0x180053403  mov     rax, [rdx+10h]
0x180053407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005340c  nop
0x18005340d  lea     r8, [rsp+1B0h+var_140]
0x180053412  xor     edx, edx
0x180053414  mov     rcx, rbx
0x180053417  mov     rax, r12
0x18005341a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005341f  mov     ebx, eax
0x180053421  test    eax, eax
0x180053423  jns     short loc_18005342F
0x180053425  mov     edx, 11B8h
0x18005342a  jmp     loc_180053314
0x18005342f  mov     rcx, qword ptr [rsp+1B0h+var_140]
0x180053434  mov     rax, [rcx]
0x180053437  lea     r8, [rsp+1B0h+var_138]
0x18005343c  lea     rdx, DEVPKEY_DeviceInterface_Enabled
0x180053443  mov     rax, [rax+28h]
0x180053447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005344c  mov     ebx, eax
0x18005344e  test    eax, eax
0x180053450  jns     short loc_18005345C
0x180053452  mov     edx, 11BDh
0x180053457  jmp     loc_180053314
0x18005345c  lea     r13, WPP_GLOBAL_Control
0x180053463  mov     r12d, 80000h
0x180053469  mov     rcx, cs:WPP_GLOBAL_Control
0x180053470  cmp     rcx, r13
0x180053473  jz      short loc_18005349B
0x180053475  test    [rcx+1Ch], r12d
0x180053479  jz      short loc_18005349B
0x18005347b  cmp     byte ptr [rcx+19h], 4
0x18005347f  jb      short loc_18005349B
0x180053481  movsx   r9d, word ptr [rbp+0B0h+var_138+8]
0x180053486  mov     edx, 29h ; ')'
0x18005348b  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
  ... truncated ...
```
