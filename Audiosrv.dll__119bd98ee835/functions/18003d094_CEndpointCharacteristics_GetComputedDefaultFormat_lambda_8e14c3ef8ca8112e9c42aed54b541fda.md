# CEndpointCharacteristics::GetComputedDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___

- ea: `0x18003d094`
- end: `0x18003dd71`
- name: `CEndpointCharacteristics::GetComputedDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___`
- size: `3293`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003cc58`

## callees

- `0x180001980`
- `0x180003d8c`
- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x18003d094`
- `0x1800424ec`
- `0x180044ab0`
- `0x180051b30`
- `0x180072e10`
- `0x1800cd8d0`
- `0x1800e5168`
- `0x18013b09c`
- `0x18013b204`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d5f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d7b4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003da54`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dd34`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dd3f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d5f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d7b4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003da54`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dd34`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dd3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d3df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d5c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d993`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d9b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d3df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d5c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d993`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d9b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc82`

## string_xrefs

- `0x18003d180`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d1dc`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d234`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d289`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d2ce`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d319`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d3bc`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d698`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d760`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d9fe`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003dcf4`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CEndpointCharacteristics::GetComputedDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
        __int64 a1,
        int a2,
        _OWORD *a3,
        unsigned __int16 **a4)
{
  int v6; // r15d
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  HRESULT (__stdcall *GetDevice)(IMMDeviceEnumerator *, LPCWSTR, IMMDevice **); // rbx
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // ebx
  __int64 v20; // rcx
  int v21; // eax
  void *v22; // rcx
  int v23; // eax
  __int64 v24; // r8
  int v25; // r9d
  int v26; // r8d
  int v27; // r9d
  void *v28; // rcx
  void *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  void *v32; // rcx
  __int64 v33; // r9
  __int64 v34; // rdx
  void *v35; // rcx
  char *v36; // rdx
  int FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77; // eax
  int v38; // r12d
  void *v39; // rcx
  int v40; // eax
  __int64 v41; // r8
  int v42; // r9d
  int v43; // r8d
  int v44; // r9d
  void *v45; // rcx
  void *v46; // rcx
  __int64 v47; // rax
  int v48; // esi
  __int64 v49; // rcx
  __int64 v50; // rdx
  void *v51; // rcx
  bool v52; // zf
  int v53; // eax
  __int64 v54; // r8
  int v55; // r9d
  int v56; // r8d
  int v57; // r9d
  void *v58; // rcx
  int v59; // r8d
  int v60; // r9d
  int v62; // [rsp+20h] [rbp-E0h]
  int *v63; // [rsp+20h] [rbp-E0h]
  _WORD v64[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v65; // [rsp+64h] [rbp-9Ch] BYREF
  int v66; // [rsp+68h] [rbp-98h] BYREF
  int v67; // [rsp+6Ch] [rbp-94h] BYREF
  LPVOID v68; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v69; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v70; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v71; // [rsp+88h] [rbp-78h] BYREF
  int v72[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 **v73; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v74; // [rsp+A0h] [rbp-60h] BYREF
  int v75; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v76; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v78; // [rsp+C0h] [rbp-40h] BYREF
  int *v79; // [rsp+C8h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v81; // [rsp+E0h] [rbp-20h]
  PROPVARIANT v82[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v83; // [rsp+F8h] [rbp-8h]
  _DWORD v84[6]; // [rsp+100h] [rbp+0h] BYREF
  int v85; // [rsp+118h] [rbp+18h] BYREF
  int v86; // [rsp+11Ch] [rbp+1Ch]
  int v87; // [rsp+120h] [rbp+20h]
  int v88; // [rsp+124h] [rbp+24h]
  int v89; // [rsp+128h] [rbp+28h]
  int v90[4]; // [rsp+130h] [rbp+30h] BYREF
  void *v91[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v92; // [rsp+150h] [rbp+50h]
  __int128 v93; // [rsp+160h] [rbp+60h]
  __int128 v94; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v73 = a4;
  *a4 = 0;
  v6 = 3;
  v84[0] = 590439624;
  v84[1] = 1283267372;
  v84[2] = 1907779772;
  v84[3] = 1730509416;
  v84[4] = 1;
  if ( a2 == 3 )
  {
    v85 = -1275528621;
    v86 = 1133379588;
    v87 = -1538194544;
    v88 = -56945810;
    v89 = 29;
  }
  else
  {
    v6 = 0;
    v85 = -1702713381;
    v86 = 1102331579;
    v87 = -1223116157;
    v88 = -65530063;
    v89 = 1;
  }
  *(_OWORD *)v82 = 0;
  v83 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, PROPVARIANT *))(**(_QWORD **)(a1 + 72) + 40LL))(
         *(_QWORD *)(a1 + 72),
         v84,
         v82);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A8,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v7,
      v62);
    goto LABEL_89;
  }
  if ( LOWORD(v82[0]) != 31 )
  {
    v8 = -2004287484;
    goto LABEL_89;
  }
  *(_OWORD *)pvar = 0;
  v81 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *, PROPVARIANT *))(**(_QWORD **)(a1 + 72) + 40LL))(
         *(_QWORD *)(a1 + 72),
         &v85,
         pvar);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18AD,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v9,
      v62);
LABEL_88:
    PropVariantClear(pvar);
    goto LABEL_89;
  }
  v70 = 0;
  GetDevice = g_DeviceEnumerator->lpVtbl->GetDevice;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v70);
  v11 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, PROPVARIANT, __int64 **))GetDevice)(
          g_DeviceEnumerator,
          v82[1],
          &v70);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B0,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v11,
      v62);
LABEL_87:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v70);
    goto LABEL_88;
  }
  *(_QWORD *)v72 = 0;
  v12 = *v70;
  *(_QWORD *)v72 = 0;
  v63 = v72;
  v13 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v12 + 24))(
          v70,
          &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
          23);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B3,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v13,
      (int)v72);
LABEL_86:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v72);
    goto LABEL_87;
  }
  v71 = 0;
  v14 = **(_QWORD **)v72;
  v71 = 0;
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v14 + 56))(*(_QWORD *)v72, LODWORD(pvar[1]), &v71);
  v8 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B6,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v15,
      (int)v72);
LABEL_85:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v71);
    goto LABEL_86;
  }
  v78 = 0;
  v16 = *v71;
  v78 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64 **))(v16 + 104))(
          v71,
          1,
          &GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81,
          &v78);
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18BB,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v17,
      (int)v72);
LABEL_18:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v78);
    goto LABEL_85;
  }
  pv = 0;
  v18 = *v78;
  v91[0] = &pv;
  v91[1] = 0;
  LOBYTE(v92) = 1;
  v19 = (*(__int64 (__fastcall **)(__int64 *, void **))(v18 + 32))(v78, &v91[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v91);
  if ( v19 >= 0 )
  {
    *(_OWORD *)v91 = *a3;
    v92 = a3[1];
    v93 = a3[2];
    v94 = a3[3];
    v21 = CEndpointCharacteristics::CloneDriverFormatIfMatching__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
            v20,
            v91,
            pv,
            v73);
    v8 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C0,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v21,
        (int)v72);
      v22 = pv;
      pv = 0;
      if ( v22 )
        CoTaskMemFree(v22);
      goto LABEL_18;
    }
    if ( *v73 )
    {
      v23 = **v73;
      if ( (_WORD)v23 == 0xFFFE )
      {
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v75 = *(_DWORD *)(v24 + 20);
          v69 = (LPVOID)(v24 + 24);
          v66 = *((_DWORD *)*v73 + 2);
          v67 = *((_DWORD *)*v73 + 1);
          v64[0] = (*v73)[1];
          v68 = L"WAVEFORMATEXTENSIBLE";
          v65 = v6;
          v76 = *(const wchar_t **)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v25,
            (unsigned int)byte_1801AA683,
            v24,
            v25,
            (__int64)&v76,
            (__int64)&v65,
            (__int64)&v68,
            (__int64)v64,
            (__int64)&v67,
            (__int64)&v66,
            (__int64)&v69,
            (__int64)&v75);
        }
      }
      else
      {
        *(GUID *)v90 = GUID_00000000_0000_0010_8000_00aa00389b71;
        v90[0] = v23;
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v76 = (const wchar_t *)v90;
          v65 = *((_DWORD *)*v73 + 2);
          v67 = *((_DWORD *)*v73 + 1);
          v64[0] = (*v73)[1];
          v69 = L"WAVEFORMATEX";
          v66 = v6;
          v68 = *(LPVOID *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v26,
            (unsigned int)byte_1801AA7DB,
            v26,
            v27,
            (__int64)&v68,
            (__int64)&v66,
            (__int64)&v69,
            (__int64)v64,
            (__int64)&v67,
            (__int64)&v65,
            (__int64)&v76);
        }
      }
      v28 = pv;
      pv = 0;
      if ( v28 )
        CoTaskMemFree(v28);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v78);
LABEL_34:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v71);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v72);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v70);
      PropVariantClear(pvar);
      v8 = 0;
      goto LABEL_89;
    }
  }
  v29 = pv;
  pv = 0;
  if ( v29 )
    CoTaskMemFree(v29);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v78);
  v74 = 0;
  v30 = *v71;
  v74 = 0;
  v31 = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64 **))(v30 + 104))(
          v71,
          1,
          &GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5,
          &v74);
  v8 = v31;
  if ( v31 < 0 )
  {
    v33 = (unsigned int)v31;
    v34 = 6348;
LABEL_83:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v33,
      (int)v63);
LABEL_84:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v74);
    goto LABEL_85;
  }
  v68 = 0;
  v91[0] = &v68;
  v91[1] = 0;
  LOBYTE(v92) = 1;
  v8 = CTCoAllocPolicy::Alloc(v32, 1u, 0x68u, &v91[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v91);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D3,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v8,
      (int)v72);
    v35 = v68;
    v68 = 0;
    if ( v35 )
      CoTaskMemFree(v35);
    goto LABEL_84;
  }
  *(_DWORD *)v68 = 104;
  *((GUID *)v68 + 1) = GUID_73647561_0000_0010_8000_00aa00389b71;
  *((GUID *)v68 + 3) = GUID_05589f81_c356_11ce_bf01_00aa0055595a;
  *((GUID *)v68 + 2) = GUID_00000001_0000_0010_8000_00aa00389b71;
  v36 = (char *)v68 + 64;
  *((_WORD *)v68 + 32) = -2;
  *(GUID *)(v36 + 24) = GUID_00000000_0000_0010_8000_00aa00389b71;
  *((_DWORD *)v36 + 6) = 1;
  v91[0] = &v74;
  v91[1] = &v68;
  *(_QWORD *)&v92 = a3;
  *((_QWORD *)&v92 + 1) = &v73;
  FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77 = CEndpointCharacteristics::FindFirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77___(
                                                                            a1,
                                                                            v36,
                                                                            v91);
  v38 = FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77;
  if ( FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18EF,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77,
      (int)v72);
    v39 = v68;
    v68 = 0;
    if ( v39 )
      CoTaskMemFree(v39);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v74);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v71);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v72);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v70);
    PropVariantClear(pvar);
    v8 = v38;
    goto LABEL_89;
  }
  if ( *v73 )
  {
    v40 = **v73;
    if ( (_WORD)v40 == 0xFFFE )
    {
      if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
      {
        v65 = *(_DWORD *)(v41 + 20);
        v76 = (const wchar_t *)(v41 + 24);
        v67 = *((_DWORD *)*v73 + 2);
        v66 = *((_DWORD *)*v73 + 1);
        v64[0] = (*v73)[1];
        v69 = L"WAVEFORMATEXTENSIBLE";
        v75 = v6;
        v79 = *(int **)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v42,
          (unsigned int)&word_1801AA72E,
          v41,
          v42,
          (__int64)&v79,
          (__int64)&v75,
          (__int64)&v69,
          (__int64)v64,
          (__int64)&v66,
          (__int64)&v67,
          (__int64)&v76,
          (__int64)&v65);
      }
    }
    else
    {
      *(GUID *)v90 = GUID_00000000_0000_0010_8000_00aa00389b71;
      v90[0] = v40;
      if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
      {
        v79 = v90;
        v65 = *((_DWORD *)*v73 + 2);
        v67 = *((_DWORD *)*v73 + 1);
        v64[0] = (*v73)[1];
        v76 = L"WAVEFORMATEX";
        v66 = v6;
        v69 = *(LPVOID *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v43,
          (unsigned int)word_1801AA4F2,
          v43,
          v44,
          (__int64)&v69,
          (__int64)&v66,
          (__int64)&v76,
          (__int64)v64,
          (__int64)&v67,
          (__int64)&v65,
          (__int64)&v79);
      }
    }
    v45 = v68;
    v68 = 0;
    goto LABEL_55;
  }
  v46 = v68;
  v68 = 0;
  if ( v46 )
    CoTaskMemFree(v46);
  v69 = 0;
  v47 = *v74;
  v91[0] = &v69;
  v91[1] = 0;
  LOBYTE(v92) = 1;
  v48 = (*(__int64 (__fastcall **)(__int64 *, void **))(v47 + 32))(v74, &v91[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v91);
  if ( v48 >= 0 )
  {
    *(_OWORD *)v91 = *a3;
    v92 = a3[1];
    v93 = a3[2];
    v94 = a3[3];
    v48 = CEndpointCharacteristics::CloneDriverFormatIfMatching__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
            v49,
            v91,
            v69,
            v73);
    if ( v48 >= 0 )
    {
      if ( !*v73 )
      {
        v58 = v69;
        v69 = 0;
        if ( v58 )
          CoTaskMemFree(v58);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnhancedAudioSrvTracing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnhancedAudioSrvTracing>::GetImpl'::`2'::impl)
          && **(_DWORD **)(a1 + 8288) > 2u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v65 = v6;
          *(_QWORD *)v90 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v59,
            (unsigned int)word_1801AA592,
            v59,
            v60,
            (__int64)v90,
            (__int64)&v65);
        }
        v8 = -2004287480;
        v33 = 2290679816LL;
        v34 = 6423;
        goto LABEL_83;
      }
      v53 = **v73;
      if ( (_WORD)v53 == 0xFFFE )
      {
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v65 = *(_DWORD *)(v54 + 20);
          v79 = (int *)(v54 + 24);
          v67 = *((_DWORD *)*v73 + 2);
          v66 = *((_DWORD *)*v73 + 1);
          v64[0] = (*v73)[1];
          v76 = L"WAVEFORMATEXTENSIBLE";
          v75 = v6;
          *(_QWORD *)v90 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v55,
            (unsigned int)word_1801AA442,
            v54,
            v55,
            (__int64)v90,
            (__int64)&v75,
            (__int64)&v76,
            (__int64)v64,
            (__int64)&v66,
            (__int64)&v67,
            (__int64)&v79,
            (__int64)&v65);
        }
      }
      else
      {
        *(GUID *)v91 = GUID_00000000_0000_0010_8000_00aa00389b71;
        LODWORD(v91[0]) = v53;
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          *(_QWORD *)v90 = v91;
          v65 = *((_DWORD *)*v73 + 2);
          v67 = *((_DWORD *)*v73 + 1);
          v64[0] = (*v73)[1];
          v79 = (int *)L"WAVEFORMATEX";
          v66 = v6;
          v76 = *(const wchar_t **)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v56,
            (unsigned int)&unk_1801AA5E0,
            v56,
            v57,
            (__int64)&v76,
            (__int64)&v66,
            (__int64)&v79,
            (__int64)v64,
            (__int64)&v67,
            (__int64)&v65,
            (__int64)v90);
        }
      }
      v45 = v69;
      v69 = 0;
LABEL_55:
      if ( v45 )
        CoTaskMemFree(v45);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v74);
      goto LABEL_34;
    }
    v50 = 6399;
  }
  else
  {
    v50 = 6397;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v50,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
    (const char *)(unsigned int)v48,
    (int)v72);
  v51 = v69;
  v52 = v69 == 0;
  v69 = 0;
  if ( !v52 )
    CoTaskMemFree(v51);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v74);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v71);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v72);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v70);
  PropVariantClear(pvar);
  v8 = v48;
LABEL_89:
  PropVariantClear(v82);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003d094  mov     [rsp-8+arg_8], rbx
0x18003d099  push    rbp
0x18003d09a  push    rsi
0x18003d09b  push    rdi
0x18003d09c  push    r12
0x18003d09e  push    r13
0x18003d0a0  push    r14
0x18003d0a2  push    r15
0x18003d0a4  lea     rbp, [rsp-90h]
0x18003d0ac  sub     rsp, 190h
0x18003d0b3  mov     rax, cs:__security_cookie
0x18003d0ba  xor     rax, rsp
0x18003d0bd  mov     [rbp+0C0h+var_40], rax
0x18003d0c4  mov     r14, r8
0x18003d0c7  mov     rdi, rcx
0x18003d0ca  mov     [rbp+0C0h+var_128], r9
0x18003d0ce  xor     r13d, r13d
0x18003d0d1  mov     [r9], r13
0x18003d0d4  lea     r12d, [r13+4]
0x18003d0d8  lea     r15d, [r13+3]
0x18003d0dc  mov     [rbp+0C0h+var_C0], 233164C8h
0x18003d0e3  mov     [rbp+0C0h+var_BC], 4C7D1B2Ch
0x18003d0ea  mov     [rbp+0C0h+var_B8], 71B668BCh
0x18003d0f1  mov     [rbp+0C0h+var_B4], 67257A68h
0x18003d0f8  lea     esi, [r13+1]
0x18003d0fc  mov     [rbp+0C0h+var_B0], esi
0x18003d0ff  cmp     edx, r15d
0x18003d102  jz      short loc_18003D128
0x18003d104  mov     r15d, r13d
0x18003d107  mov     [rbp+0C0h+var_A8], 9A82A7DBh
0x18003d10e  mov     [rbp+0C0h+var_A4], 41B43EBBh
0x18003d115  mov     [rbp+0C0h+var_A0], 0B718BA83h
0x18003d11c  mov     [rbp+0C0h+var_9C], 0FC181731h
0x18003d123  mov     [rbp+0C0h+var_98], esi
0x18003d126  jmp     short loc_18003D14B
0x18003d128  mov     [rbp+0C0h+var_A8], 0B3F8FA53h
0x18003d12f  mov     [rbp+0C0h+var_A4], 438E0004h
0x18003d136  mov     [rbp+0C0h+var_A0], 0A4510390h
0x18003d13d  mov     [rbp+0C0h+var_9C], 0FC9B136Eh
0x18003d144  mov     [rbp+0C0h+var_98], 1Dh
0x18003d14b  xorps   xmm0, xmm0
0x18003d14e  xor     eax, eax
0x18003d150  movups  xmmword ptr [rbp+0C0h+var_D8], xmm0
0x18003d154  mov     [rbp+0C0h+var_C8], rax
0x18003d158  mov     rcx, [rcx+48h]
0x18003d15c  mov     rax, [rcx]
0x18003d15f  lea     r8, [rbp+0C0h+var_D8]
0x18003d163  lea     rdx, [rbp+0C0h+var_C0]
0x18003d167  mov     rax, [rax+28h]
0x18003d16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d170  mov     ebx, eax
0x18003d172  test    eax, eax
0x18003d174  jns     short loc_18003D196
0x18003d176  mov     rcx, [rbp+0C8h]; this
0x18003d17d  mov     r9d, eax; char *
0x18003d180  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d187  mov     edx, 18A8h; void *
0x18003d18c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d191  jmp     loc_18003DD3B
0x18003d196  cmp     word ptr [rbp+0C0h+var_D8], 1Fh
0x18003d19b  jz      short loc_18003D1A7
0x18003d19d  mov     ebx, 88890004h
0x18003d1a2  jmp     loc_18003DD3B
0x18003d1a7  xorps   xmm0, xmm0
0x18003d1aa  xor     eax, eax
0x18003d1ac  movups  xmmword ptr [rbp+0C0h+pvar], xmm0
0x18003d1b0  mov     [rbp+0C0h+var_E0], rax
0x18003d1b4  mov     rcx, [rdi+48h]
0x18003d1b8  mov     rax, [rcx]
0x18003d1bb  lea     r8, [rbp+0C0h+pvar]
0x18003d1bf  lea     rdx, [rbp+0C0h+var_A8]
0x18003d1c3  mov     rax, [rax+28h]
0x18003d1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1cc  mov     ebx, eax
0x18003d1ce  test    eax, eax
0x18003d1d0  jns     short loc_18003D1F2
0x18003d1d2  mov     rcx, [rbp+0C8h]; this
0x18003d1d9  mov     r9d, eax; char *
0x18003d1dc  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d1e3  mov     edx, 18ADh; void *
0x18003d1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d1ed  jmp     loc_18003DD30
0x18003d1f2  mov     [rbp+0C0h+var_140], r13
0x18003d1f6  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18003d1fd  mov     rcx, [rax]
0x18003d200  mov     rbx, [rcx+28h]
0x18003d204  lea     rcx, [rbp+0C0h+var_140]
0x18003d208  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003d20d  lea     r8, [rbp+0C0h+var_140]
0x18003d211  mov     rdx, [rbp+0C0h+var_D8+8]
0x18003d215  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18003d21c  mov     rax, rbx
0x18003d21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d224  mov     ebx, eax
0x18003d226  test    eax, eax
0x18003d228  jns     short loc_18003D24A
0x18003d22a  mov     rcx, [rbp+0C8h]; this
0x18003d231  mov     r9d, eax; char *
0x18003d234  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d23b  mov     edx, 18B0h; void *
0x18003d240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d245  jmp     loc_18003DD26
0x18003d24a  mov     qword ptr [rbp+0C0h+var_130], r13
0x18003d24e  mov     rcx, [rbp+0C0h+var_140]
0x18003d252  mov     rax, [rcx]
0x18003d255  mov     qword ptr [rbp+0C0h+var_130], r13
0x18003d259  lea     rdx, [rbp+0C0h+var_130]
0x18003d25d  mov     qword ptr [rsp+1C0h+var_1A0], rdx; int
0x18003d262  xor     r9d, r9d
0x18003d265  lea     r8d, [r9+17h]
0x18003d269  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x18003d270  mov     rax, [rax+18h]
0x18003d274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d279  mov     ebx, eax
0x18003d27b  test    eax, eax
0x18003d27d  jns     short loc_18003D29F
0x18003d27f  mov     rcx, [rbp+0C8h]; this
0x18003d286  mov     r9d, eax; char *
0x18003d289  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d290  mov     edx, 18B3h; void *
0x18003d295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d29a  jmp     loc_18003DD1C
0x18003d29f  mov     [rbp+0C0h+var_138], r13
0x18003d2a3  mov     rcx, qword ptr [rbp+0C0h+var_130]
0x18003d2a7  mov     rax, [rcx]
0x18003d2aa  mov     [rbp+0C0h+var_138], r13
0x18003d2ae  lea     r8, [rbp+0C0h+var_138]
0x18003d2b2  mov     edx, dword ptr [rbp+0C0h+pvar+8]
0x18003d2b5  mov     rax, [rax+38h]
0x18003d2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2be  mov     ebx, eax
0x18003d2c0  test    eax, eax
0x18003d2c2  jns     short loc_18003D2E4
0x18003d2c4  mov     rcx, [rbp+0C8h]; this
0x18003d2cb  mov     r9d, eax; char *
0x18003d2ce  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d2d5  mov     edx, 18B6h; void *
0x18003d2da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d2df  jmp     loc_18003DD12
0x18003d2e4  mov     [rbp+0C0h+var_100], r13
0x18003d2e8  mov     rcx, [rbp+0C0h+var_138]
0x18003d2ec  mov     rax, [rcx]
0x18003d2ef  mov     [rbp+0C0h+var_100], r13
0x18003d2f3  lea     r9, [rbp+0C0h+var_100]
0x18003d2f7  lea     r8, _GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81
0x18003d2fe  mov     edx, esi
0x18003d300  mov     rax, [rax+68h]
0x18003d304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d309  mov     ebx, eax
0x18003d30b  test    eax, eax
0x18003d30d  jns     short loc_18003D339
0x18003d30f  mov     rcx, [rbp+0C8h]; this
0x18003d316  mov     r9d, eax; char *
0x18003d319  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d320  mov     edx, 18BBh; void *
0x18003d325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d32a  nop
0x18003d32b  lea     rcx, [rbp+0C0h+var_100]
0x18003d32f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003d334  jmp     loc_18003DD12
0x18003d339  mov     [rbp+0C0h+pv], r13
0x18003d33d  mov     rcx, [rbp+0C0h+var_100]
0x18003d341  mov     rax, [rcx]
0x18003d344  lea     rdx, [rbp+0C0h+pv]
0x18003d348  mov     [rbp+0C0h+var_80], rdx
0x18003d34c  mov     [rbp+0C0h+var_80+8], r13
0x18003d350  mov     byte ptr [rbp+0C0h+var_70], sil
0x18003d354  lea     rdx, [rbp+0C0h+var_80+8]
0x18003d358  mov     rax, [rax+20h]
0x18003d35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d361  mov     ebx, eax
0x18003d363  lea     rcx, [rbp+0C0h+var_80]
0x18003d367  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003d36c  shr     ebx, 1Fh
0x18003d36f  xor     bl, sil
0x18003d372  jz      loc_18003D603
0x18003d378  movups  xmm0, xmmword ptr [r14]
0x18003d37c  movaps  xmmword ptr [rbp+0C0h+var_80], xmm0
0x18003d380  movups  xmm1, xmmword ptr [r14+10h]
0x18003d385  movaps  [rbp+0C0h+var_70], xmm1
0x18003d389  movups  xmm0, xmmword ptr [r14+20h]
0x18003d38e  movaps  [rbp+0C0h+var_60], xmm0
0x18003d392  movups  xmm1, xmmword ptr [r14+30h]
0x18003d397  movaps  [rbp+0C0h+var_50], xmm1
0x18003d39b  mov     r9, [rbp+0C0h+var_128]
0x18003d39f  mov     r8, [rbp+0C0h+pv]
0x18003d3a3  lea     rdx, [rbp+0C0h+var_80]
0x18003d3a7  call    CEndpointCharacteristics__CloneDriverFormatIfMatching__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003d3ac  mov     ebx, eax
0x18003d3ae  test    eax, eax
0x18003d3b0  jns     short loc_18003D3EA
0x18003d3b2  mov     rcx, [rbp+0C8h]; this
0x18003d3b9  mov     r9d, eax; char *
0x18003d3bc  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d3c3  mov     edx, 18C0h; void *
0x18003d3c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d3cd  nop
0x18003d3ce  mov     rcx, [rbp+0C0h+pv]; pv
0x18003d3d2  mov     [rbp+0C0h+pv], r13
0x18003d3d6  test    rcx, rcx
0x18003d3d9  jz      loc_18003D32B
0x18003d3df  call    cs:__imp_CoTaskMemFree
0x18003d3e5  jmp     loc_18003D32B
0x18003d3ea  mov     rax, [rbp+0C0h+var_128]
0x18003d3ee  mov     r8, [rax]
0x18003d3f1  test    r8, r8
0x18003d3f4  jz      loc_18003D603
0x18003d3fa  movzx   eax, word ptr [r8]
0x18003d3fe  mov     ebx, 0FFFEh
0x18003d403  cmp     ax, bx
0x18003d406  jnz     loc_18003D4E3
0x18003d40c  mov     r9, [rdi+2060h]
0x18003d413  mov     eax, [r9]
0x18003d416  cmp     eax, r12d
0x18003d419  jbe     loc_18003D5B5
0x18003d41f  mov     edx, 10h
0x18003d424  mov     rcx, r9
0x18003d427  call    _tlgKeywordOn
0x18003d42c  test    al, al
0x18003d42e  jz      loc_18003D5B5
0x18003d434  mov     eax, [r8+14h]
0x18003d438  mov     [rbp+0C0h+var_118], eax
0x18003d43b  lea     rax, [r8+18h]
0x18003d43f  mov     [rsp+1C0h+var_148], rax
0x18003d444  mov     rdx, [rbp+0C0h+var_128]
0x18003d448  mov     rax, [rdx]
0x18003d44b  mov     ecx, [rax+8]
0x18003d44e  mov     [rsp+1C0h+var_158], ecx
0x18003d452  mov     rax, [rdx]
0x18003d455  mov     ecx, [rax+4]
0x18003d458  mov     [rsp+1C0h+var_154], ecx
0x18003d45c  mov     rax, [rdx]
0x18003d45f  movzx   ecx, word ptr [rax+2]
0x18003d463  mov     [rsp+1C0h+var_160], cx
0x18003d468  lea     rax, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x18003d46f  mov     [rsp+1C0h+var_150], rax
0x18003d474  mov     [rsp+1C0h+var_15C], r15d
0x18003d479  mov     rax, [rdi+30h]
0x18003d47d  mov     [rbp+0C0h+var_110], rax
0x18003d481  lea     rax, [rbp+0C0h+var_118]
0x18003d485  mov     [rsp+1C0h+var_168], rax
0x18003d48a  lea     rax, [rsp+1C0h+var_148]
0x18003d48f  mov     [rsp+1C0h+var_170], rax
0x18003d494  lea     rax, [rsp+1C0h+var_158]
0x18003d499  mov     [rsp+1C0h+var_178], rax
0x18003d49e  lea     rax, [rsp+1C0h+var_154]
0x18003d4a3  mov     [rsp+1C0h+var_180], rax
0x18003d4a8  lea     rax, [rsp+1C0h+var_160]
0x18003d4ad  mov     [rsp+1C0h+var_188], rax
0x18003d4b2  lea     rax, [rsp+1C0h+var_150]
0x18003d4b7  mov     [rsp+1C0h+var_190], rax
0x18003d4bc  lea     rax, [rsp+1C0h+var_15C]
0x18003d4c1  mov     [rsp+1C0h+var_198], rax
0x18003d4c6  lea     rax, [rbp+0C0h+var_110]
0x18003d4ca  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18003d4cf  lea     rdx, byte_1801AA683
0x18003d4d6  mov     rcx, r9
0x18003d4d9  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$01@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$01@@44AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18003d4de  jmp     loc_18003D5B5
0x18003d4e3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data1
0x18003d4ea  movdqu  xmmword ptr [rbp+0C0h+var_90], xmm0
0x18003d4ef  mov     [rbp+0C0h+var_90], eax
0x18003d4f2  mov     r8, [rdi+2060h]
0x18003d4f9  mov     eax, [r8]
0x18003d4fc  cmp     eax, r12d
0x18003d4ff  jbe     loc_18003D5B5
0x18003d505  mov     edx, 10h
0x18003d50a  mov     rcx, r8
0x18003d50d  call    _tlgKeywordOn
0x18003d512  test    al, al
0x18003d514  jz      loc_18003D5B5
0x18003d51a  lea     rax, [rbp+0C0h+var_90]
0x18003d51e  mov     [rbp+0C0h+var_110], rax
0x18003d522  mov     rdx, [rbp+0C0h+var_128]
0x18003d526  mov     rax, [rdx]
0x18003d529  mov     ecx, [rax+8]
0x18003d52c  mov     [rsp+1C0h+var_15C], ecx
0x18003d530  mov     rax, [rdx]
0x18003d533  mov     ecx, [rax+4]
0x18003d536  mov     [rsp+1C0h+var_154], ecx
0x18003d53a  mov     rax, [rdx]
0x18003d53d  movzx   ecx, word ptr [rax+2]
0x18003d541  mov     [rsp+1C0h+var_160], cx
0x18003d546  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x18003d54d  mov     [rsp+1C0h+var_148], rax
0x18003d552  mov     [rsp+1C0h+var_158], r15d
0x18003d557  mov     rax, [rdi+30h]
0x18003d55b  mov     [rsp+1C0h+var_150], rax
0x18003d560  lea     rax, [rbp+0C0h+var_110]
0x18003d564  mov     [rsp+1C0h+var_170], rax
0x18003d569  lea     rax, [rsp+1C0h+var_15C]
0x18003d56e  mov     [rsp+1C0h+var_178], rax
0x18003d573  lea     rax, [rsp+1C0h+var_154]
0x18003d578  mov     [rsp+1C0h+var_180], rax
0x18003d57d  lea     rax, [rsp+1C0h+var_160]
0x18003d582  mov     [rsp+1C0h+var_188], rax
0x18003d587  lea     rax, [rsp+1C0h+var_148]
0x18003d58c  mov     [rsp+1C0h+var_190], rax
0x18003d591  lea     rax, [rsp+1C0h+var_158]
0x18003d596  mov     [rsp+1C0h+var_198], rax
  ... truncated ...
```
