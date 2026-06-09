# FiringAgent::FiringAgent(IUnknown *,IEventClass2 *,IEventSystemTier2 *,long &)

- ea: `0x18001cdfc`
- end: `0x18001d9b7`
- name: `??0FiringAgent@@AEAA@PEAUIUnknown@@PEAUIEventClass2@@PEAUIEventSystemTier2@@AEAJ@Z`
- size: `3003`
- prototype: `FiringAgent *__usercall@<rax>(FiringAgent *__hidden this@<rcx>, struct IUnknown *@<rdx>, struct IEventClass2 *@<r8>, struct IEventSystemTier2 *@<r9>, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001ccb0`

## callees

- `0x180003d54`
- `0x1800065b0`
- `0x18000685c`
- `0x180008938`
- `0x180018340`
- `0x18001c8f0`
- `0x18001cdfc`
- `0x18001dd60`
- `0x18002674c`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d0d9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d12a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d0d9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d12a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d436`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d844`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d964`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d972`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d980`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d436`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d844`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d964`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d972`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d980`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18001d373`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18001d373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d54a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d6da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d54a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d6da`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d15a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d16b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d495`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d882`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d15a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d16b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d495`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d7a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d7a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d8b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d8b6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001d717`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001d717`

## string_xrefs

- `0x18001cf23`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001d895`: `CoCreateInstance`

## pseudocode

```c
FiringAgent *__fastcall FiringAgent::FiringAgent(
        FiringAgent *this,
        struct IUnknown *a2,
        struct IEventClass2 *a3,
        struct IEventSystemTier2 *a4,
        int *a5)
{
  _QWORD *v7; // r12
  LPCOLESTR *v8; // r13
  int v9; // eax
  BSTR v10; // rax
  BSTR v11; // rax
  bool v12; // al
  int v13; // eax
  char v14; // cl
  char v15; // dl
  int v16; // eax
  ITypeLib *v17; // rax
  unsigned int v18; // r9d
  int v19; // eax
  int v20; // r8d
  int v21; // eax
  unsigned __int16 v22; // r15
  LPVOID v23; // rax
  int v24; // eax
  unsigned __int16 v25; // r15
  unsigned __int16 v26; // r12
  int v27; // eax
  int v28; // eax
  LPVOID v29; // rax
  HRESULT v30; // eax
  unsigned int v31; // r9d
  int v32; // eax
  int v33; // r8d
  const wchar_t *v34; // r14
  HRESULT v35; // eax
  unsigned int v36; // r9d
  _QWORD *v37; // r15
  HRESULT v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // r8d
  int v43; // [rsp+40h] [rbp-1E8h] BYREF
  struct ITypeInfo *v44; // [rsp+48h] [rbp-1E0h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-1D8h] BYREF
  __int16 v46; // [rsp+58h] [rbp-1D0h]
  unsigned __int16 i; // [rsp+5Ch] [rbp-1CCh]
  __int64 v48; // [rsp+60h] [rbp-1C8h] BYREF
  LPCOLESTR szFile; // [rsp+68h] [rbp-1C0h] BYREF
  int v50; // [rsp+70h] [rbp-1B8h] BYREF
  int v51; // [rsp+74h] [rbp-1B4h] BYREF
  int v52; // [rsp+78h] [rbp-1B0h] BYREF
  int v53; // [rsp+7Ch] [rbp-1ACh] BYREF
  int v54; // [rsp+80h] [rbp-1A8h] BYREF
  int v55; // [rsp+84h] [rbp-1A4h] BYREF
  int v56; // [rsp+88h] [rbp-1A0h] BYREF
  __int64 v57; // [rsp+90h] [rbp-198h] BYREF
  LPCOLESTR v58; // [rsp+98h] [rbp-190h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-188h] BYREF
  struct ITypeInfo *v60; // [rsp+A8h] [rbp-180h] BYREF
  BSTR v61; // [rsp+B0h] [rbp-178h] BYREF
  LPCOLESTR lpsz; // [rsp+B8h] [rbp-170h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-168h] BYREF
  struct ITypeInfo *v64; // [rsp+C8h] [rbp-160h] BYREF
  _QWORD v65[2]; // [rsp+D0h] [rbp-158h] BYREF
  GUID iid; // [rsp+E0h] [rbp-148h] BYREF
  GUID pclsid; // [rsp+F0h] [rbp-138h] BYREF
  unsigned __int16 v68[120]; // [rsp+100h] [rbp-128h] BYREF

  v65[1] = this;
  *(_QWORD *)this = &FiringAgent::`vftable'{for `IMultiInterfaceEventControl'};
  *((_QWORD *)this + 1) = &FiringAgent::`vftable'{for `IEventControl'};
  *((_QWORD *)this + 2) = &FiringAgent::`vftable'{for `IAmAFiringAgent'};
  *((_DWORD *)this + 6) = 1;
  *((_QWORD *)this + 4) = a4;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 17;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 10;
  v7 = (_QWORD *)((char *)this + 96);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_BYTE *)this + 112) = *((_BYTE *)this + 112) & 0xFC | 1;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 38) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 44) = 10;
  *((_QWORD *)this + 23) = a2;
  *((_QWORD *)this + 24) = &FiringAgent::XNDUnknown::`vftable';
  v8 = (LPCOLESTR *)((char *)this + 200);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 31) = 0;
  v57 = 0;
  v48 = 0;
  _InterlockedAdd(&g_tier1ActiveObjects, 1u);
  if ( !*((_QWORD *)this + 4) )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x12B1u, 0x80001203, 0x12u);
  if ( !a3 )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x12B2u, 0x80001203, 0x12u);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
  if ( !*((_QWORD *)this + 23) )
    *((_QWORD *)this + 23) = (char *)this + 192;
  szFile = 0;
  lpsz = 0;
  v58 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  ((void (__fastcall *)(struct IEventClass2 *, char *))a3->lpVtbl->get_EventClassID)(a3, (char *)this + 96);
  if ( !*v7 )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x12C4u, 0xC0001204, 0x12u);
  ((void (__fastcall *)(struct IEventClass2 *, char *))a3->lpVtbl->get_PublisherID)(a3, (char *)this + 104);
  ((void (__fastcall *)(struct IEventClass2 *, LPCOLESTR *))a3->lpVtbl->get_TypeLib)(a3, &szFile);
  ((void (__fastcall *)(struct IEventClass2 *, LPCOLESTR *))a3->lpVtbl->get_FiringInterfaceID)(a3, &lpsz);
  ((void (__fastcall *)(struct IEventClass2 *, int *))a3->lpVtbl->get_AllowInprocActivation)(a3, &v50);
  ((void (__fastcall *)(struct IEventClass2 *, int *))a3->lpVtbl->get_FireInParallel)(a3, &v51);
  ((void (__fastcall *)(struct IEventClass2 *, LPCOLESTR *))a3->lpVtbl->get_MultiInterfacePublisherFilterCLSID)(
    a3,
    &v58);
  v9 = ((__int64 (__fastcall *)(struct IEventClass2 *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
         a3,
         &IID_IEventClass3,
         &v57);
  *a5 = v9;
  if ( v9 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x12D0u, 0x12u, v9);
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v57 + 232LL))(v57, (char *)this + 200);
  if ( !*v8 )
  {
    v10 = SysAllocString(L"{00000000-0000-0000-0000-000000000000}");
    *v8 = v10;
    if ( !v10 )
      InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x12D8u, 0xC0001204, 0x12u);
  }
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v57 + 248LL))(v57, (char *)this + 208);
  if ( !*((_QWORD *)this + 26) )
  {
    v11 = SysAllocString(L"{00000000-0000-0000-0000-000000000000}");
    *((_QWORD *)this + 26) = v11;
    if ( !v11 )
      InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x12E1u, 0xC0001204, 0x12u);
  }
  CLSIDFromString(*((LPCOLESTR *)this + 12), (LPCLSID)((char *)this + 232));
  CLSIDFromString(*v8, (LPCLSID)((char *)this + 216));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  v57 = 0;
  v12 = v50 != 0;
  *((_BYTE *)this + 112) &= ~1u;
  *((_BYTE *)this + 112) |= v12;
  *((_BYTE *)this + 112) = (v51 != 0 ? 2 : 0) | *((_BYTE *)this + 112) & 0xFD;
  v13 = ((__int64 (__fastcall *)(struct IEventClass2 *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
          a3,
          &IID_IEventClassInternal,
          &v48);
  *a5 = v13;
  if ( v13 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x12EEu, 0x12u, v13);
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 24LL))(v48, &v52);
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 32LL))(v48, &v53);
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 40LL))(v48, &v54);
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 48LL))(v48, &v55);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  v48 = 0;
  v14 = v52 != 0 ? 4 : 0;
  *((_BYTE *)this + 112) &= ~4u;
  *((_BYTE *)this + 112) |= v14;
  v15 = (v53 != 0 ? 8 : 0) | *((_BYTE *)this + 112) & 0xF7;
  *((_BYTE *)this + 112) = v15;
  *((_BYTE *)this + 112) = (v54 != 0 ? 0x10 : 0) | v15 & 0xEF;
  *((_DWORD *)this + 63) = v55;
  v63 = 0;
  v16 = ((__int64 (__fastcall *)(struct IEventClass2 *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
          a3,
          &IID_IEventClassParallelFiringTimeout,
          &v63);
  *a5 = v16;
  if ( v16 < 0 )
  {
    if ( v16 == -2147467262 )
    {
      *((_DWORD *)this + 62) = 0;
      *a5 = 0;
    }
  }
  else
  {
    v43 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v63 + 24LL))(v63, (char *)this + 248, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    if ( v43 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1305u, 0x12u, v43);
  }
  if ( *a5 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x130Cu, 0x12u, *a5);
  v17 = 0;
  pptlib = 0;
  if ( szFile )
  {
    *a5 = LoadTypeLib(szFile, &pptlib);
    v17 = pptlib;
    if ( !pptlib )
    {
      bstrString = 0;
      ((void (__fastcall *)(struct IEventClass2 *, BSTR *))a3->lpVtbl->get_EventClassName)(a3, &bstrString);
      v19 = ConcatenateECID_PARTID_APPID_WSZ(
              *((LPCOLESTR *)this + 12),
              (unsigned __int16 *)*v8,
              *((LPCOLESTR *)this + 26),
              v18,
              v68);
      v20 = *a5;
      if ( v19 < 0 )
        LogMessage_HR(0x12u, 0x80001107, v20, 3u, szFile, &sz, bstrString);
      else
        LogMessage_HR(0x12u, 0x80001107, v20, 3u, szFile, v68, bstrString);
      SysFreeString(bstrString);
      v17 = pptlib;
    }
  }
  if ( v17 || (lpsz ? (*a5 = LoadTypeLibFromIID(lpsz, &pptlib), v17 = pptlib) : (ITypeLib *)(*a5 = -2147024809), v17) )
  {
    pclsid = 0;
    CLSIDFromString(*((LPCOLESTR *)this + 12), &pclsid);
    v44 = 0;
    *a5 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, struct ITypeInfo **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
            pptlib,
            &pclsid,
            &v44);
    if ( v44 )
    {
      v65[0] = 0;
      v21 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD *))v44->lpVtbl->GetTypeAttr)(v44, v65);
      *a5 = v21;
      v22 = 0;
      if ( v21 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1344u, 0x12u, v21);
      *((_WORD *)this + 20) = *(_WORD *)(v65[0] + 52LL);
      ((void (__fastcall *)(struct ITypeInfo *))v44->lpVtbl->ReleaseTypeAttr)(v44);
      v23 = CoTaskMemAlloc(saturated_mul(*((unsigned __int16 *)this + 20), 8u));
      *((_QWORD *)this + 6) = v23;
      if ( !v23 )
        InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1350u, 0xC0001204, 0x12u);
      if ( IsManagedEventClass(v44) )
      {
        v46 = 0;
        while ( v22 < *((_WORD *)this + 20) )
        {
          v56 = 0;
          v24 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, int *))v44->lpVtbl->GetImplTypeFlags)(
                  v44,
                  v22,
                  &v56);
          *a5 = v24;
          if ( v24 >= 0 && (v56 & 3) == 1 )
          {
            *((_WORD *)this + 21) = v22;
            break;
          }
          v46 = ++v22;
        }
      }
      v25 = 0;
      for ( i = 0; v25 < *((_WORD *)this + 20); i = v25 )
      {
        v26 = *((_WORD *)this + 21);
        if ( v25 )
        {
          if ( v25 == v26 )
            v26 = 0;
          else
            v26 = v25;
        }
        v43 = 0;
        v27 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, int *))v44->lpVtbl->GetRefTypeOfImplType)(
                v44,
                v26,
                &v43);
        *a5 = v27;
        if ( v27 < 0 )
          break;
        v64 = 0;
        v28 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v44->lpVtbl->GetRefTypeInfo)(
                v44,
                (unsigned int)v43,
                &v64);
        *a5 = v28;
        if ( v28 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1379u, 0x12u, v28);
        *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v26) = FiringAgent::CreateEventInterceptor(this, &v64);
        ((void (__fastcall *)(struct ITypeInfo *))v64->lpVtbl->Release)(v64);
        ++v25;
      }
      ((void (__fastcall *)(struct ITypeInfo *))v44->lpVtbl->Release)(v44);
    }
    else
    {
      *((_DWORD *)this + 10) = 1;
      v29 = CoTaskMemAlloc(8u);
      *((_QWORD *)this + 6) = v29;
      if ( !v29 )
        InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x138Au, 0xC0001204, 0x12u);
      iid = 0;
      v30 = IIDFromString(lpsz, &iid);
      *a5 = v30;
      if ( v30 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x138Eu, 0x12u, v30);
      v60 = 0;
      *a5 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, struct ITypeInfo **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
              pptlib,
              &iid,
              &v60);
      if ( v60 )
      {
        **((_QWORD **)this + 6) = FiringAgent::CreateEventInterceptor(this, &v60);
        ((void (__fastcall *)(struct ITypeInfo *))v60->lpVtbl->Release)(v60);
      }
      else
      {
        CoTaskMemFree(*((LPVOID *)this + 6));
        *((_QWORD *)this + 6) = 0;
        *((_WORD *)this + 20) = 0;
        v61 = 0;
        ((void (__fastcall *)(struct IEventClass2 *, BSTR *))a3->lpVtbl->get_EventClassName)(a3, &v61);
        v32 = ConcatenateECID_PARTID_APPID_WSZ(
                *((LPCOLESTR *)this + 12),
                *((unsigned __int16 **)this + 25),
                *((LPCOLESTR *)this + 26),
                v31,
                v68);
        v33 = *a5;
        if ( v32 < 0 )
          LogMessage_HR(0x12u, 0x80001107, v33, 3u, szFile, &sz, v61);
        else
          LogMessage_HR(0x12u, 0x80001107, v33, 3u, szFile, v68, v61);
        SysFreeString(v61);
      }
    }
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
    if ( v58 )
    {
      v34 = 0;
      iid = 0;
      v35 = CLSIDFromString(v58, &iid);
      *a5 = v35;
      v37 = (_QWORD *)((char *)this + 128);
      if ( v35 < 0
        || (v34 = L"CoCreateInstance",
            v38 = CoCreateInstance(&iid, 0, 0x17u, &IID_IMultiInterfacePublisherFilter, (LPVOID *)this + 16),
            *a5 = v38,
            v38 < 0)
        || (v34 = L"IMultiInterfacePublisherFilter::Initialize",
            v39 = (*(__int64 (__fastcall **)(_QWORD, FiringAgent *))(*(_QWORD *)*v37 + 24LL))(*v37, this),
            *a5 = v39,
            v39 < 0) )
      {
        *a5 = 0;
        if ( *v37 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v37 + 16LL))(*v37);
          *v37 = 0;
        }
        v40 = ConcatenateECID_PARTID_APPID_WSZ(
                *((LPCOLESTR *)this + 12),
                *((unsigned __int16 **)this + 25),
                *((LPCOLESTR *)this + 26),
                v36,
                v68);
        v41 = *a5;
        if ( v40 < 0 )
          LogMessage_HR(0x12u, 0xC000120F, v41, 3u, v58, &sz, v34);
        else
          LogMessage_HR(0x12u, 0xC000120F, v41, 3u, v58, v68, v34);
      }
    }
  }
  SysFreeString((BSTR)szFile);
  SysFreeString((BSTR)lpsz);
  SysFreeString((BSTR)v58);
  return this;
}

```

## disassembly

```asm
0x18001cdfc  mov     [rsp+arg_8], rbx
0x18001ce01  mov     [rsp+arg_18], rsi
0x18001ce06  push    rdi
0x18001ce07  push    r12
0x18001ce09  push    r13
0x18001ce0b  push    r14
0x18001ce0d  push    r15
0x18001ce0f  sub     rsp, 200h
0x18001ce16  mov     rax, cs:__security_cookie
0x18001ce1d  xor     rax, rsp
0x18001ce20  mov     [rsp+228h+var_38], rax
0x18001ce28  mov     r15, r8
0x18001ce2b  mov     rbx, rcx
0x18001ce2e  mov     [rsp+228h+var_150], rcx
0x18001ce36  mov     rsi, [rsp+228h+arg_20]
0x18001ce3e  lea     rax, ??_7FiringAgent@@6BIMultiInterfaceEventControl@@@; const FiringAgent::`vftable'{for `IMultiInterfaceEventControl'}
0x18001ce45  mov     [rcx], rax
0x18001ce48  lea     rax, ??_7FiringAgent@@6BIEventControl@@@; const FiringAgent::`vftable'{for `IEventControl'}
0x18001ce4f  mov     [rcx+8], rax
0x18001ce53  lea     rax, ??_7FiringAgent@@6BIAmAFiringAgent@@@; const FiringAgent::`vftable'{for `IAmAFiringAgent'}
0x18001ce5a  mov     [rcx+10h], rax
0x18001ce5e  mov     r10d, 1
0x18001ce64  mov     [rcx+18h], r10d
0x18001ce68  mov     [rcx+20h], r9
0x18001ce6c  xor     r8d, r8d
0x18001ce6f  mov     [rcx+28h], r8d
0x18001ce73  mov     [rcx+30h], r8
0x18001ce77  mov     [rcx+38h], r8
0x18001ce7b  mov     qword ptr [rcx+40h], 11h
0x18001ce83  mov     [rcx+48h], r8
0x18001ce87  mov     [rcx+50h], r8
0x18001ce8b  lea     ecx, [r10+9]
0x18001ce8f  mov     [rbx+58h], ecx
0x18001ce92  lea     r12, [rbx+60h]
0x18001ce96  mov     [r12], r8
0x18001ce9a  mov     [rbx+68h], r8
0x18001ce9e  mov     al, [rbx+70h]
0x18001cea1  and     al, 0FDh
0x18001cea3  or      al, r10b
0x18001cea6  mov     [rbx+70h], al
0x18001cea9  mov     [rbx+78h], r8
0x18001cead  mov     [rbx+80h], r8
0x18001ceb4  mov     [rbx+98h], r8d
0x18001cebb  mov     [rbx+0A0h], r8
0x18001cec2  mov     [rbx+90h], r8
0x18001cec9  mov     [rbx+88h], r8
0x18001ced0  mov     [rbx+0A8h], r8
0x18001ced7  mov     [rbx+0B0h], ecx
0x18001cedd  mov     [rbx+0B8h], rdx
0x18001cee4  lea     rax, ??_7XNDUnknown@FiringAgent@@6B@; const FiringAgent::XNDUnknown::`vftable'
0x18001ceeb  mov     [rbx+0C0h], rax
0x18001cef2  lea     r13, [rbx+0C8h]
0x18001cef9  mov     [r13+0], r8
0x18001cefd  mov     [rbx+0D0h], r8
0x18001cf04  mov     [rbx+0F8h], r8
0x18001cf0b  mov     [rsp+228h+var_198], r8
0x18001cf13  mov     [rsp+228h+var_1C8], r8
0x18001cf18  lock add cs:?g_tier1ActiveObjects@@3JA, r10d; long g_tier1ActiveObjects
0x18001cf20  lea     edi, [rcx+8]
0x18001cf23  lea     r14, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18001cf2a  cmp     [rbx+20h], r8
0x18001cf2e  jnz     short loc_18001CF46
0x18001cf30  mov     r9d, edi; unsigned __int16
0x18001cf33  mov     edx, 12B1h; unsigned int
0x18001cf38  mov     r8d, 80001203h; unsigned int
0x18001cf3e  mov     rcx, r14; unsigned __int16 *
0x18001cf41  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001cf46  test    r15, r15
0x18001cf49  jnz     short loc_18001CF61
0x18001cf4b  mov     r9d, edi; unsigned __int16
0x18001cf4e  mov     edx, 12B2h; unsigned int
0x18001cf53  mov     r8d, 80001203h; unsigned int
0x18001cf59  mov     rcx, r14; unsigned __int16 *
0x18001cf5c  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001cf61  mov     rcx, [rbx+20h]
0x18001cf65  mov     rax, [rcx]
0x18001cf68  mov     rax, [rax+8]
0x18001cf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf71  xor     ecx, ecx
0x18001cf73  cmp     [rbx+0B8h], rcx
0x18001cf7a  jnz     short loc_18001CF8A
0x18001cf7c  lea     rax, [rbx+0C0h]
0x18001cf83  mov     [rbx+0B8h], rax
0x18001cf8a  mov     [rsp+228h+szFile], rcx
0x18001cf8f  mov     [rsp+228h+lpsz], rcx
0x18001cf97  mov     [rsp+228h+var_190], rcx
0x18001cf9f  mov     [rsp+228h+var_1B8], ecx
0x18001cfa3  mov     [rsp+228h+var_1B4], ecx
0x18001cfa7  mov     [rsp+228h+var_1B0], ecx
0x18001cfab  mov     [rsp+228h+var_1AC], ecx
0x18001cfaf  mov     [rsp+228h+var_1A8], ecx
0x18001cfb6  mov     [rsp+228h+var_1A4], ecx
0x18001cfbd  mov     rax, [r15]
0x18001cfc0  mov     rdx, r12
0x18001cfc3  mov     rcx, r15
0x18001cfc6  mov     rax, [rax+38h]
0x18001cfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfcf  cmp     qword ptr [r12], 0
0x18001cfd4  mov     r12d, 0C0001204h
0x18001cfda  jnz     short loc_18001CFEF
0x18001cfdc  mov     r9d, edi; unsigned __int16
0x18001cfdf  mov     r8d, r12d; unsigned int
0x18001cfe2  mov     edx, 12C4h; unsigned int
0x18001cfe7  mov     rcx, r14; unsigned __int16 *
0x18001cfea  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001cfef  mov     rax, [r15]
0x18001cff2  lea     rdx, [rbx+68h]
0x18001cff6  mov     rcx, r15
0x18001cff9  mov     rax, [rax+0A8h]
0x18001d000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d005  mov     rax, [r15]
0x18001d008  lea     rdx, [rsp+228h+szFile]
0x18001d00d  mov     rcx, r15
0x18001d010  mov     rax, [rax+98h]
0x18001d017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d01c  mov     rax, [r15]
0x18001d01f  lea     rdx, [rsp+228h+lpsz]
0x18001d027  mov     rcx, r15
0x18001d02a  mov     rax, [rax+68h]
0x18001d02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d033  mov     rax, [r15]
0x18001d036  lea     rdx, [rsp+228h+var_1B8]
0x18001d03b  mov     rcx, r15
0x18001d03e  mov     rax, [rax+0C8h]
0x18001d045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d04a  mov     rax, [r15]
0x18001d04d  lea     rdx, [rsp+228h+var_1B4]
0x18001d052  mov     rcx, r15
0x18001d055  mov     rax, [rax+0D8h]
0x18001d05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d061  mov     rax, [r15]
0x18001d064  lea     rdx, [rsp+228h+var_190]
0x18001d06c  mov     rcx, r15
0x18001d06f  mov     rax, [rax+0B8h]
0x18001d076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d07b  mov     rax, [r15]
0x18001d07e  lea     r8, [rsp+228h+var_198]
0x18001d086  lea     rdx, IID_IEventClass3
0x18001d08d  mov     rcx, r15
0x18001d090  mov     rax, [rax]
0x18001d093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d098  mov     [rsi], eax
0x18001d09a  test    eax, eax
0x18001d09c  jns     short loc_18001D0B1
0x18001d09e  mov     r8d, edi; unsigned __int16
0x18001d0a1  mov     r9d, eax; int
0x18001d0a4  mov     edx, 12D0h; unsigned int
0x18001d0a9  mov     rcx, r14; unsigned __int16 *
0x18001d0ac  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001d0b1  mov     rcx, [rsp+228h+var_198]
0x18001d0b9  mov     rax, [rcx]
0x18001d0bc  mov     rdx, r13
0x18001d0bf  mov     rax, [rax+0E8h]
0x18001d0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0cb  cmp     qword ptr [r13+0], 0
0x18001d0d0  jnz     short loc_18001D0FB
0x18001d0d2  lea     rcx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18001d0d9  call    cs:__imp_SysAllocString
0x18001d0df  mov     [r13+0], rax
0x18001d0e3  test    rax, rax
0x18001d0e6  jnz     short loc_18001D0FB
0x18001d0e8  mov     r9d, edi; unsigned __int16
0x18001d0eb  mov     r8d, r12d; unsigned int
0x18001d0ee  mov     edx, 12D8h; unsigned int
0x18001d0f3  mov     rcx, r14; unsigned __int16 *
0x18001d0f6  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001d0fb  mov     rcx, [rsp+228h+var_198]
0x18001d103  mov     rax, [rcx]
0x18001d106  lea     rdx, [rbx+0D0h]
0x18001d10d  mov     rax, [rax+0F8h]
0x18001d114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d119  cmp     qword ptr [rbx+0D0h], 0
0x18001d121  jnz     short loc_18001D14F
0x18001d123  lea     rcx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18001d12a  call    cs:__imp_SysAllocString
0x18001d130  mov     [rbx+0D0h], rax
0x18001d137  test    rax, rax
0x18001d13a  jnz     short loc_18001D14F
0x18001d13c  mov     r9d, edi; unsigned __int16
0x18001d13f  mov     r8d, r12d; unsigned int
0x18001d142  mov     edx, 12E1h; unsigned int
0x18001d147  mov     rcx, r14; unsigned __int16 *
0x18001d14a  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001d14f  lea     rdx, [rbx+0E8h]; pclsid
0x18001d156  mov     rcx, [rbx+60h]; lpsz
0x18001d15a  call    cs:__imp_CLSIDFromString
0x18001d160  lea     rdx, [rbx+0D8h]; pclsid
0x18001d167  mov     rcx, [r13+0]; lpsz
0x18001d16b  call    cs:__imp_CLSIDFromString
0x18001d171  mov     rcx, [rsp+228h+var_198]
0x18001d179  mov     rax, [rcx]
0x18001d17c  mov     rax, [rax+10h]
0x18001d180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d185  xor     eax, eax
0x18001d187  mov     [rsp+228h+var_198], rax
0x18001d18f  cmp     [rsp+228h+var_1B8], eax
0x18001d193  setnz   al
0x18001d196  and     byte ptr [rbx+70h], 0FEh
0x18001d19a  or      [rbx+70h], al
0x18001d19d  mov     dl, [rbx+70h]
0x18001d1a0  mov     eax, [rsp+228h+var_1B4]
0x18001d1a4  neg     eax
0x18001d1a6  sbb     cl, cl
0x18001d1a8  and     cl, 2
0x18001d1ab  and     dl, 0FDh
0x18001d1ae  or      dl, cl
0x18001d1b0  mov     [rbx+70h], dl
0x18001d1b3  mov     rax, [r15]
0x18001d1b6  lea     r8, [rsp+228h+var_1C8]
0x18001d1bb  lea     rdx, IID_IEventClassInternal
0x18001d1c2  mov     rcx, r15
0x18001d1c5  mov     rax, [rax]
0x18001d1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1cd  mov     [rsi], eax
0x18001d1cf  test    eax, eax
0x18001d1d1  jns     short loc_18001D1E6
0x18001d1d3  mov     r8d, edi; unsigned __int16
0x18001d1d6  mov     r9d, eax; int
0x18001d1d9  mov     edx, 12EEh; unsigned int
0x18001d1de  mov     rcx, r14; unsigned __int16 *
0x18001d1e1  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18001d1e6  mov     rcx, [rsp+228h+var_1C8]
0x18001d1eb  mov     rax, [rcx]
0x18001d1ee  lea     rdx, [rsp+228h+var_1B0]
0x18001d1f3  mov     rax, [rax+18h]
0x18001d1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1fc  mov     rcx, [rsp+228h+var_1C8]
0x18001d201  mov     rax, [rcx]
0x18001d204  lea     rdx, [rsp+228h+var_1AC]
0x18001d209  mov     rax, [rax+20h]
0x18001d20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d212  mov     rcx, [rsp+228h+var_1C8]
0x18001d217  mov     rax, [rcx]
0x18001d21a  lea     rdx, [rsp+228h+var_1A8]
0x18001d222  mov     rax, [rax+28h]
0x18001d226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d22b  mov     rcx, [rsp+228h+var_1C8]
0x18001d230  mov     rax, [rcx]
0x18001d233  lea     rdx, [rsp+228h+var_1A4]
0x18001d23b  mov     rax, [rax+30h]
0x18001d23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d244  mov     rcx, [rsp+228h+var_1C8]
0x18001d249  mov     rax, [rcx]
0x18001d24c  mov     rax, [rax+10h]
0x18001d250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d255  xor     r8d, r8d
0x18001d258  mov     [rsp+228h+var_1C8], r8
0x18001d25d  mov     eax, [rsp+228h+var_1B0]
0x18001d261  neg     eax
0x18001d263  sbb     cl, cl
0x18001d265  and     cl, 4
0x18001d268  and     byte ptr [rbx+70h], 0FBh
0x18001d26c  or      [rbx+70h], cl
0x18001d26f  mov     dl, [rbx+70h]
0x18001d272  mov     eax, [rsp+228h+var_1AC]
0x18001d276  neg     eax
0x18001d278  sbb     cl, cl
0x18001d27a  and     cl, 8
0x18001d27d  and     dl, 0F7h
0x18001d280  or      dl, cl
0x18001d282  mov     [rbx+70h], dl
0x18001d285  mov     eax, [rsp+228h+var_1A8]
0x18001d28c  neg     eax
0x18001d28e  sbb     cl, cl
0x18001d290  and     cl, 10h
0x18001d293  and     dl, 0EFh
0x18001d296  or      dl, cl
0x18001d298  mov     [rbx+70h], dl
0x18001d29b  mov     eax, [rsp+228h+var_1A4]
0x18001d2a2  mov     [rbx+0FCh], eax
0x18001d2a8  mov     [rsp+228h+var_168], r8
0x18001d2b0  mov     rax, [r15]
0x18001d2b3  lea     r8, [rsp+228h+var_168]
0x18001d2bb  lea     rdx, IID_IEventClassParallelFiringTimeout
0x18001d2c2  mov     rcx, r15
0x18001d2c5  mov     rax, [rax]
0x18001d2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2cd  mov     [rsi], eax
0x18001d2cf  xor     r8d, r8d
0x18001d2d2  test    eax, eax
0x18001d2d4  js      short loc_18001D32C
0x18001d2d6  mov     rcx, [rsp+228h+var_168]
0x18001d2de  mov     rax, [rcx]
0x18001d2e1  lea     rdx, [rbx+0F8h]
0x18001d2e8  mov     rax, [rax+18h]
0x18001d2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2f1  mov     [rsp+228h+var_1E8], eax
0x18001d2f5  mov     rcx, [rsp+228h+var_168]
0x18001d2fd  mov     rax, [rcx]
0x18001d300  mov     rax, [rax+10h]
0x18001d304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d309  mov     eax, [rsp+228h+var_1E8]
0x18001d30d  xor     r8d, r8d
0x18001d310  test    eax, eax
0x18001d312  jns     short loc_18001D33D
0x18001d314  mov     r8d, edi; unsigned __int16
0x18001d317  mov     r9d, eax; int
0x18001d31a  mov     edx, 1305h; unsigned int
0x18001d31f  mov     rcx, r14; unsigned __int16 *
0x18001d322  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
  ... truncated ...
```
