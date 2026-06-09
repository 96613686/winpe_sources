# CKsNotificationsMonitor::GetDeviceId(ushort * *)

- ea: `0x18005eb60`
- end: `0x18005f2e6`
- name: `?GetDeviceId@CKsNotificationsMonitor@@QEAAJPEAPEAG@Z`
- size: `1926`
- prototype: `__int64 __fastcall(CKsNotificationsMonitor *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003af20`

## callees

- `0x180006b0c`
- `0x180009650`
- `0x18000ceb0`
- `0x18000fb60`
- `0x180010da8`
- `0x180020ae4`
- `0x180021030`
- `0x180021060`
- `0x180021080`
- `0x180021148`
- `0x180024814`
- `0x1800254e0`
- `0x18005eaac`
- `0x18005eae8`
- `0x18005eb60`
- `0x18005f514`
- `0x18005f580`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ebb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ebb3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ecfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ef87`
- `OLEAUT32!__imp_SysFreeString` at `0x18005efb0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f011`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f096`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f1a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ecfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ef87`
- `OLEAUT32!__imp_SysFreeString` at `0x18005efb0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f011`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f096`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f1a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ec6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f04a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f0b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f1b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ec6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f04a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f0b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f1b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CKsNotificationsMonitor::GetDeviceId(CKsNotificationsMonitor *this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  char *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // r14
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LPVOID *); // rbx
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, __int64 *); // rdi
  __int64 v18; // rcx
  int v19; // edi
  unsigned int v20; // r15d
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rdi
  __int64 v23; // rcx
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, __int64, __int64, _QWORD); // rsi
  __int64 v26; // rcx
  __int64 v27; // rsi
  int (__fastcall *v28)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  __int64 v29; // rsi
  int (__fastcall *v30)(__int64, unsigned __int16 **); // rdi
  __int64 v31; // rdi
  __int64 v32; // rsi
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 (__fastcall ***v36)(_QWORD, GUID *, BSTR *); // rbx
  int v37; // eax
  __int64 v38; // rdx
  BSTR v39; // rdi
  __int64 (__fastcall *v40)(BSTR, char *); // rbx
  __int64 v41; // r9
  __int64 v42; // rdx
  int v43; // eax
  int *v45; // [rsp+20h] [rbp-E0h]
  BSTR v46; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v49; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v50; // [rsp+50h] [rbp-B0h] BYREF
  int v51[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v52; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v53)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 v54; // [rsp+70h] [rbp-90h] BYREF
  __int128 v55; // [rsp+78h] [rbp-88h] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h]
  __int128 v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+A0h] [rbp-60h]
  BSTR v59; // [rsp+A8h] [rbp-58h] BYREF
  BSTR v60; // [rsp+B0h] [rbp-50h] BYREF
  BSTR v61; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v62; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-30h]
  __int128 v64; // [rsp+D8h] [rbp-28h]
  int v65; // [rsp+E8h] [rbp-18h]
  __int128 v66; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v67; // [rsp+100h] [rbp+0h]
  __int128 v68; // [rsp+108h] [rbp+8h]
  int v69; // [rsp+118h] [rbp+18h]
  char *v70; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  BSTR bstrString; // [rsp+178h] [rbp+78h] BYREF
  int v73; // [rsp+180h] [rbp+80h] BYREF
  __int64 v74; // [rsp+188h] [rbp+88h] BYREF

  if ( !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14C,
      (unsigned int)"avcore\\audiocore\\server\\lib\\formatcaps\\formatcaps.cpp",
      (const char *)0x80070057LL,
      (int)v45);
    return v4;
  }
  v5 = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v70 = v5;
  v8 = (_QWORD *)((char *)this + 72);
  if ( *((_QWORD *)this + 9) )
  {
LABEL_67:
    if ( *v8 )
    {
      v43 = _AllocString<CTCoAllocPolicy>(v7, v6, *v8, a2);
      v4 = v43;
      if ( v43 >= 0 )
      {
        v4 = 0;
        goto LABEL_73;
      }
      v41 = (unsigned int)v43;
      v42 = 443;
    }
    else
    {
      v4 = -2147023728;
      v41 = 2147943568LL;
      v42 = 442;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"avcore\\audiocore\\server\\lib\\formatcaps\\formatcaps.cpp",
      (const char *)v41,
      (int)v45);
    goto LABEL_73;
  }
  if ( (unsigned int)(*((_DWORD *)this + 20) - 1) <= 1 )
  {
    v46 = 0;
    v36 = (__int64 (__fastcall ***)(_QWORD, GUID *, BSTR *))*((_QWORD *)this + 11);
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v46);
    v37 = (**v36)(v36, &GUID_9c2c4058_23f5_41de_877a_df3af236a09e, &v46);
    v4 = v37;
    if ( v37 >= 0 )
    {
      v39 = v46;
      v40 = *(__int64 (__fastcall **)(BSTR, char *))(*(_QWORD *)v46 + 80LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (char *)this + 72,
        0);
      v37 = v40(v39, (char *)this + 72);
      v4 = v37;
      if ( v37 >= 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
        goto LABEL_67;
      }
      v38 = 350;
    }
    else
    {
      v38 = 349;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"avcore\\audiocore\\server\\lib\\formatcaps\\formatcaps.cpp",
      (const char *)(unsigned int)v37,
      (int)v45);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
    goto LABEL_73;
  }
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 10;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 10;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 10;
  v74 = 0;
  pv = 0;
  v9 = (__int64 *)*((_QWORD *)this + 11);
  v10 = *v9;
  v74 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v10 + 96))(v9, &v74);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 364;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\audiocore\\server\\lib\\formatcaps\\formatcaps.cpp",
      (const char *)(unsigned int)v11,
      (int)v45);
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v66);
    ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::RemoveAll(&v62);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v55);
    goto LABEL_73;
  }
  v13 = v74;
  v14 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v74 + 64LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v11 = v14(v13, &pv);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 365;
    goto LABEL_7;
  }
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const unsigned __int16 *)pv);
  ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(&v55, &bstrString);
  SysFreeString(bstrString);
  v15 = wil::com_ptr_t<IPart,wil::err_returncode_policy>::com_ptr_t<IPart,wil::err_returncode_policy>(
          &bstrString,
          *((_QWORD *)this + 11));
  ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::AddTail(
    &v62,
    v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&bstrString);
LABEL_43:
  if ( !v56 || *v8 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v66);
    ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::RemoveAll(&v62);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v55);
    goto LABEL_67;
  }
  ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveHead(&v55, &v46);
  ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::RemoveHead(
    &v62,
    &v52);
  LODWORD(bstrString) = 0;
  ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(&v66, &v46);
  v16 = v52;
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 96LL);
  v18 = v74;
  v74 = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = v17(v16, &v74);
  if ( v19 < 0 )
  {
    v35 = 382;
    goto LABEL_57;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v74 + 24LL))(v74, &bstrString);
  if ( v19 < 0 )
  {
    v35 = 383;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"avcore\\audiocore\\server\\lib\\formatcaps\\formatcaps.cpp",
      (const char *)(unsigned int)v19,
      (int)v45);
    goto LABEL_58;
  }
  v20 = (unsigned int)bstrString;
  while ( 1 )
  {
    if ( (--v20 & 0x80000000) != 0 || *v8 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
      SysFreeString(v46);
      goto LABEL_43;
    }
    *(_QWORD *)v51 = 0;
    v48 = 0;
    v49 = 0;
    v73 = 0;
    v21 = v74;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v74 + 32LL);
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v48);
    v19 = v22(v21, v20, &v48);
    if ( v19 < 0 )
    {
      v34 = 394;
      goto LABEL_52;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 24LL))(v48, &v73);
    if ( v19 < 0 )
    {
      v34 = 395;
      goto LABEL_52;
    }
    v23 = v49;
    v49 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v48)(
            v48,
            &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
            &v49);
    if ( v19 < 0 )
    {
      v34 = 396;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"avcore\\audiocore\\server\\lib\\formatcaps\\formatcaps.cpp",
        (const char *)(unsigned int)v19,
        (int)v45);
      goto LABEL_50;
    }
    v24 = v74;
    v25 = *(int (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v74 + 72LL);
    v26 = *(_QWORD *)v51;
    *(_QWORD *)v51 = 0;
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v45 = v51;
    if ( v25(v24, v16, v49, 0) >= 0 )
      break;
LABEL_40:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v51);
  }
  v53 = 0;
  v50 = 0;
  v27 = v48;
  v28 = *(int (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v48 + 64LL);
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v53);
  if ( v28(v27, &v53) < 0
    || (v29 = v48,
        v30 = *(int (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v48 + 80LL),
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v50,
          0),
        v30(v29, &v50) < 0) )
  {
LABEL_37:
    if ( v50 )
      CoTaskMemFree(v50);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
    goto LABEL_40;
  }
  if ( (unsigned int)(v73 - 1) <= 1 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      v8,
      &v50);
    goto LABEL_37;
  }
  if ( v73 != 4 )
    goto LABEL_37;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v59, v50);
  v31 = ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Find(&v66, &v59);
  SysFreeString(v59);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v60, v50);
  v32 = ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Find(&v55, &v60);
  SysFreeString(v60);
  if ( v31 || v32 )
    goto LABEL_37;
  v54 = 0;
  v33 = (**v53)(v53, &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9, &v54);
  v19 = v33;
  if ( v33 >= 0 )
  {
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v61, v50);
    ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(&v55, &v61);
    SysFreeString(v61);
    ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::AddTail(
      &v62,
      &v54);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
    goto LABEL_37;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1AC,
    (unsigned int)"avcore\\audiocore\\server\\lib\\formatcaps\\formatcaps.cpp",
    (const char *)(unsigned int)v33,
    (int)v51);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  if ( v50 )
    CoTaskMemFree(v50);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
LABEL_50:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v51);
LABEL_58:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  SysFreeString(v46);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
  ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v66);
  ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::RemoveAll(&v62);
  ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(&v55);
  v4 = v19;
LABEL_73:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v70);
  return v4;
}

```

## disassembly

```asm
0x18005eb60  mov     [rsp-8+arg_0], rbx
0x18005eb65  push    rbp
0x18005eb66  push    rsi
0x18005eb67  push    rdi
0x18005eb68  push    r12
0x18005eb6a  push    r13
0x18005eb6c  push    r14
0x18005eb6e  push    r15
0x18005eb70  lea     rbp, [rsp-30h]
0x18005eb75  sub     rsp, 130h
0x18005eb7c  mov     r12, rdx
0x18005eb7f  mov     rsi, rcx
0x18005eb82  xor     r13d, r13d
0x18005eb85  test    rdx, rdx
0x18005eb88  jnz     short loc_18005EBAC
0x18005eb8a  mov     rcx, [rbp+68h]; this
0x18005eb8e  mov     ebx, 80070057h
0x18005eb93  mov     r9d, ebx; char *
0x18005eb96  lea     r8, aAvcoreAudiocor_3; "avcore\\audiocore\\server\\lib\\formatc"...
0x18005eb9d  mov     edx, 14Ch; void *
0x18005eba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eba7  jmp     loc_18005F2C9
0x18005ebac  lea     rbx, [rcx+20h]
0x18005ebb0  mov     rcx, rbx; lpCriticalSection
0x18005ebb3  call    cs:__imp_EnterCriticalSection
0x18005ebb9  mov     [rbp+60h+var_40], rbx
0x18005ebbd  lea     r14, [rsi+48h]
0x18005ebc1  cmp     [r14], r13
0x18005ebc4  jnz     loc_18005F27E
0x18005ebca  mov     eax, [rsi+50h]
0x18005ebcd  dec     eax
0x18005ebcf  cmp     eax, 1
0x18005ebd2  jbe     loc_18005F1EB
0x18005ebd8  xorps   xmm0, xmm0
0x18005ebdb  movdqu  [rsp+160h+var_E8], xmm0
0x18005ebe1  mov     [rbp+60h+var_D8], r13
0x18005ebe5  xorps   xmm1, xmm1
0x18005ebe8  movdqu  [rbp+60h+var_D0], xmm1
0x18005ebed  mov     eax, 0Ah
0x18005ebf2  mov     [rbp+60h+var_C0], eax
0x18005ebf5  movdqu  [rbp+60h+var_A0], xmm0
0x18005ebfa  mov     [rbp+60h+var_90], r13
0x18005ebfe  movdqu  [rbp+60h+var_88], xmm1
0x18005ec03  mov     [rbp+60h+var_78], eax
0x18005ec06  movdqu  [rbp+60h+var_70], xmm0
0x18005ec0b  mov     [rbp+60h+var_60], r13
0x18005ec0f  movdqu  [rbp+60h+var_58], xmm1
0x18005ec14  mov     [rbp+60h+var_48], eax
0x18005ec17  mov     [rbp+60h+arg_18], r13
0x18005ec1e  mov     [rsp+160h+pv], r13
0x18005ec23  mov     rcx, [rsi+58h]
0x18005ec27  mov     rax, [rcx]
0x18005ec2a  mov     [rbp+60h+arg_18], r13
0x18005ec31  lea     rdx, [rbp+60h+arg_18]
0x18005ec38  mov     rax, [rax+60h]
0x18005ec3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec41  mov     ebx, eax
0x18005ec43  test    eax, eax
0x18005ec45  jns     short loc_18005ECA1
0x18005ec47  mov     edx, 16Ch; void *
0x18005ec4c  mov     r9d, eax; char *
0x18005ec4f  lea     r8, aAvcoreAudiocor_3; "avcore\\audiocore\\server\\lib\\formatc"...
0x18005ec56  mov     rcx, [rbp+68h]; this
0x18005ec5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ec5f  nop
0x18005ec60  mov     rcx, [rsp+160h+pv]; pv
0x18005ec65  test    rcx, rcx
0x18005ec68  jz      short loc_18005EC71
0x18005ec6a  call    cs:__imp_CoTaskMemFree
0x18005ec70  nop
0x18005ec71  lea     rcx, [rbp+60h+arg_18]
0x18005ec78  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005ec7d  nop
0x18005ec7e  lea     rcx, [rbp+60h+var_70]
0x18005ec82  call    ?RemoveAll@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(void)
0x18005ec87  nop
0x18005ec88  lea     rcx, [rbp+60h+var_A0]
0x18005ec8c  call    ?RemoveAll@?$CAtlList@V?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@V?$CElementTraits@V?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::RemoveAll(void)
0x18005ec91  nop
0x18005ec92  lea     rcx, [rsp+160h+var_E8]
0x18005ec97  call    ?RemoveAll@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveAll(void)
0x18005ec9c  jmp     loc_18005F2C0
0x18005eca1  mov     rdi, [rbp+60h+arg_18]
0x18005eca8  mov     rax, [rdi]
0x18005ecab  mov     rbx, [rax+40h]
0x18005ecaf  xor     edx, edx
0x18005ecb1  lea     rcx, [rsp+160h+pv]
0x18005ecb6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005ecbb  lea     rdx, [rsp+160h+pv]
0x18005ecc0  mov     rcx, rdi
0x18005ecc3  mov     rax, rbx
0x18005ecc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eccb  mov     ebx, eax
0x18005eccd  test    eax, eax
0x18005eccf  jns     short loc_18005ECDB
0x18005ecd1  mov     edx, 16Dh
0x18005ecd6  jmp     loc_18005EC4C
0x18005ecdb  mov     rdx, [rsp+160h+pv]; unsigned __int16 *
0x18005ece0  lea     rcx, [rbp+60h+bstrString]; this
0x18005ece4  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18005ece9  nop
0x18005ecea  lea     rdx, [rbp+60h+bstrString]
0x18005ecee  lea     rcx, [rsp+160h+var_E8]
0x18005ecf3  call    ?AddTail@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@AEBVCComBSTR@2@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(ATL::CComBSTR const &)
0x18005ecf8  nop
0x18005ecf9  mov     rcx, [rbp+60h+bstrString]; bstrString
0x18005ecfd  call    cs:__imp_SysFreeString
0x18005ed03  mov     rdx, [rsi+58h]
0x18005ed07  lea     rcx, [rbp+60h+bstrString]
0x18005ed0b  call    ??0?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIPart@@@Z; wil::com_ptr_t<IPart,wil::err_returncode_policy>::com_ptr_t<IPart,wil::err_returncode_policy>(IPart *)
0x18005ed10  nop
0x18005ed11  mov     rdx, rax
0x18005ed14  lea     rcx, [rbp+60h+var_A0]
0x18005ed18  call    ?AddTail@?$CAtlList@V?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@V?$CElementTraits@V?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBV?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@@Z; ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::AddTail(wil::com_ptr_t<IPart,wil::err_returncode_policy> const &)
0x18005ed1d  nop
0x18005ed1e  lea     rcx, [rbp+60h+bstrString]
0x18005ed22  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005ed27  jmp     loc_18005F09C
0x18005ed2c  cmp     [r14], r13
0x18005ed2f  jnz     loc_18005F0A6
0x18005ed35  lea     rdx, [rsp+160h+var_130]
0x18005ed3a  lea     rcx, [rsp+160h+var_E8]
0x18005ed3f  call    ?RemoveHead@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAA?AVCComBSTR@2@XZ; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::RemoveHead(void)
0x18005ed44  nop
0x18005ed45  lea     rdx, [rsp+160h+var_100]
0x18005ed4a  lea     rcx, [rbp+60h+var_A0]
0x18005ed4e  call    ?RemoveHead@?$CAtlList@V?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@V?$CElementTraits@V?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@@ATL@@@ATL@@QEAA?AV?$com_ptr_t@UIPart@@Uerr_returncode_policy@wil@@@wil@@XZ; ATL::CAtlList<wil::com_ptr_t<IPart,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IPart,wil::err_returncode_policy>>>::RemoveHead(void)
0x18005ed53  nop
0x18005ed54  mov     dword ptr [rbp+60h+bstrString], r13d
0x18005ed58  lea     rdx, [rsp+160h+var_130]
0x18005ed5d  lea     rcx, [rbp+60h+var_70]
0x18005ed61  call    ?AddTail@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@AEBVCComBSTR@2@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(ATL::CComBSTR const &)
0x18005ed66  mov     rbx, [rsp+160h+var_100]
0x18005ed6b  mov     rax, [rbx]
0x18005ed6e  mov     rdi, [rax+60h]
0x18005ed72  mov     rcx, [rbp+60h+arg_18]
0x18005ed79  mov     [rbp+60h+arg_18], r13
0x18005ed80  test    rcx, rcx
0x18005ed83  jz      short loc_18005ED92
0x18005ed85  mov     rdx, [rcx]
0x18005ed88  mov     rax, [rdx+10h]
0x18005ed8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed91  nop
0x18005ed92  lea     rdx, [rbp+60h+arg_18]
0x18005ed99  mov     rcx, rbx
0x18005ed9c  mov     rax, rdi
0x18005ed9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eda4  mov     edi, eax
0x18005eda6  test    eax, eax
0x18005eda8  js      loc_18005F178
0x18005edae  mov     rcx, [rbp+60h+arg_18]
0x18005edb5  mov     rax, [rcx]
0x18005edb8  lea     rdx, [rbp+60h+bstrString]
0x18005edbc  mov     rax, [rax+18h]
0x18005edc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005edc5  mov     edi, eax
0x18005edc7  test    eax, eax
0x18005edc9  js      loc_18005F171
0x18005edcf  mov     r15d, dword ptr [rbp+60h+bstrString]
0x18005edd3  jmp     loc_18005F07C
0x18005edd8  cmp     [r14], r13
0x18005eddb  jnz     loc_18005F086
0x18005ede1  mov     qword ptr [rsp+160h+var_108], r13
0x18005ede6  mov     [rsp+160h+var_120], r13
0x18005edeb  mov     [rsp+160h+var_118], r13
0x18005edf0  mov     [rbp+60h+arg_10], r13d
0x18005edf7  mov     rsi, [rbp+60h+arg_18]
0x18005edfe  mov     rax, [rsi]
0x18005ee01  mov     rdi, [rax+20h]
0x18005ee05  lea     rcx, [rsp+160h+var_120]
0x18005ee0a  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18005ee0f  lea     r8, [rsp+160h+var_120]
0x18005ee14  mov     edx, r15d
0x18005ee17  mov     rcx, rsi
0x18005ee1a  mov     rax, rdi
0x18005ee1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee22  mov     edi, eax
0x18005ee24  test    eax, eax
0x18005ee26  js      loc_18005F16A
0x18005ee2c  mov     rcx, [rsp+160h+var_120]
0x18005ee31  mov     rax, [rcx]
0x18005ee34  lea     rdx, [rbp+60h+arg_10]
0x18005ee3b  mov     rax, [rax+18h]
0x18005ee3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee44  mov     edi, eax
0x18005ee46  test    eax, eax
0x18005ee48  js      loc_18005F163
0x18005ee4e  mov     rcx, [rsp+160h+var_118]
0x18005ee53  mov     [rsp+160h+var_118], r13
0x18005ee58  test    rcx, rcx
0x18005ee5b  jz      short loc_18005EE6A
0x18005ee5d  mov     rax, [rcx]
0x18005ee60  mov     rax, [rax+10h]
0x18005ee64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee69  nop
0x18005ee6a  mov     rcx, [rsp+160h+var_120]
0x18005ee6f  mov     rax, [rcx]
0x18005ee72  lea     r8, [rsp+160h+var_118]
0x18005ee77  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x18005ee7e  mov     rax, [rax]
0x18005ee81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee86  mov     edi, eax
0x18005ee88  test    eax, eax
0x18005ee8a  js      loc_18005F149
0x18005ee90  mov     rdi, [rbp+60h+arg_18]
0x18005ee97  mov     rax, [rdi]
0x18005ee9a  mov     rsi, [rax+48h]
0x18005ee9e  mov     rcx, qword ptr [rsp+160h+var_108]
0x18005eea3  mov     qword ptr [rsp+160h+var_108], r13
0x18005eea8  test    rcx, rcx
0x18005eeab  jz      short loc_18005EEBA
0x18005eead  mov     rax, [rcx]
0x18005eeb0  mov     rax, [rax+10h]
0x18005eeb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eeb9  nop
0x18005eeba  lea     rax, [rsp+160h+var_108]
0x18005eebf  mov     qword ptr [rsp+160h+var_140], rax; int
0x18005eec4  xor     r9d, r9d
0x18005eec7  mov     r8, [rsp+160h+var_118]
0x18005eecc  mov     rdx, rbx
0x18005eecf  mov     rcx, rdi
0x18005eed2  mov     rax, rsi
0x18005eed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eeda  test    eax, eax
0x18005eedc  js      loc_18005F05C
0x18005eee2  mov     [rsp+160h+var_F8], r13
0x18005eee7  mov     [rsp+160h+var_110], r13
0x18005eeec  mov     rsi, [rsp+160h+var_120]
0x18005eef1  mov     rax, [rsi]
0x18005eef4  mov     rdi, [rax+40h]
0x18005eef8  lea     rcx, [rsp+160h+var_F8]
0x18005eefd  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18005ef02  lea     rdx, [rsp+160h+var_F8]
0x18005ef07  mov     rcx, rsi
0x18005ef0a  mov     rax, rdi
0x18005ef0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef12  test    eax, eax
0x18005ef14  js      loc_18005F040
0x18005ef1a  mov     rsi, [rsp+160h+var_120]
0x18005ef1f  mov     rax, [rsi]
0x18005ef22  mov     rdi, [rax+50h]
0x18005ef26  xor     edx, edx
0x18005ef28  lea     rcx, [rsp+160h+var_110]
0x18005ef2d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005ef32  lea     rdx, [rsp+160h+var_110]
0x18005ef37  mov     rcx, rsi
0x18005ef3a  mov     rax, rdi
0x18005ef3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef42  test    eax, eax
0x18005ef44  js      loc_18005F040
0x18005ef4a  mov     ecx, [rbp+60h+arg_10]
0x18005ef50  lea     eax, [rcx-1]
0x18005ef53  cmp     eax, 1
0x18005ef56  jbe     loc_18005F032
0x18005ef5c  cmp     ecx, 4
0x18005ef5f  jnz     loc_18005F040
0x18005ef65  mov     rdx, [rsp+160h+var_110]; unsigned __int16 *
0x18005ef6a  lea     rcx, [rbp+60h+var_B8]; this
0x18005ef6e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18005ef73  lea     rdx, [rbp+60h+var_B8]
0x18005ef77  lea     rcx, [rbp+60h+var_70]
0x18005ef7b  call    ?Find@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@AEBVCComBSTR@2@PEAU3@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Find(ATL::CComBSTR const &,__POSITION *)
0x18005ef80  mov     rdi, rax
0x18005ef83  mov     rcx, [rbp+60h+var_B8]; bstrString
0x18005ef87  call    cs:__imp_SysFreeString
0x18005ef8d  mov     rdx, [rsp+160h+var_110]; unsigned __int16 *
0x18005ef92  lea     rcx, [rbp+60h+var_B0]; this
0x18005ef96  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18005ef9b  lea     rdx, [rbp+60h+var_B0]
0x18005ef9f  lea     rcx, [rsp+160h+var_E8]
0x18005efa4  call    ?Find@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@AEBVCComBSTR@2@PEAU3@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Find(ATL::CComBSTR const &,__POSITION *)
0x18005efa9  mov     rsi, rax
0x18005efac  mov     rcx, [rbp+60h+var_B0]; bstrString
0x18005efb0  call    cs:__imp_SysFreeString
0x18005efb6  test    rdi, rdi
0x18005efb9  jnz     loc_18005F040
0x18005efbf  test    rsi, rsi
0x18005efc2  jnz     short loc_18005F040
0x18005efc4  mov     [rsp+160h+var_F0], r13
0x18005efc9  mov     rcx, [rsp+160h+var_F8]
0x18005efce  mov     rax, [rcx]
0x18005efd1  lea     r8, [rsp+160h+var_F0]
0x18005efd6  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x18005efdd  mov     rax, [rax]
0x18005efe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efe5  mov     edi, eax
0x18005efe7  test    eax, eax
0x18005efe9  js      loc_18005F0E7
0x18005efef  mov     rdx, [rsp+160h+var_110]; unsigned __int16 *
0x18005eff4  lea     rcx, [rbp+60h+var_A8]; this
0x18005eff8  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18005effd  nop
0x18005effe  lea     rdx, [rbp+60h+var_A8]
0x18005f002  lea     rcx, [rsp+160h+var_E8]
0x18005f007  call    ?AddTail@?$CAtlList@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@AEBVCComBSTR@2@@Z; ATL::CAtlList<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::AddTail(ATL::CComBSTR const &)
0x18005f00c  nop
0x18005f00d  mov     rcx, [rbp+60h+var_A8]; bstrString
0x18005f011  call    cs:__imp_SysFreeString
0x18005f017  lea     rdx, [rsp+160h+var_F0]
0x18005f01c  lea     rcx, [rbp+60h+var_A0]
  ... truncated ...
```
