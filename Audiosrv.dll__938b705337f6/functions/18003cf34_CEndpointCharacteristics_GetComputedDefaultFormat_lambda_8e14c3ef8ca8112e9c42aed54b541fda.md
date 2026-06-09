# CEndpointCharacteristics::GetComputedDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___

- ea: `0x18003cf34`
- end: `0x18003dc11`
- name: `CEndpointCharacteristics::GetComputedDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___`
- size: `3293`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003caf8`

## callees

- `0x180001980`
- `0x180003b80`
- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x18003cf34`
- `0x1800423cc`
- `0x180044f40`
- `0x180051fc0`
- `0x180073310`
- `0x1800cf8c0`
- `0x1800e58e8`
- `0x18013adac`
- `0x18013af14`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d495`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d654`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d8f4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dbd4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dbdf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d495`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d654`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d8f4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dbd4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003dbdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d27f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d462`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d4b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d8c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d27f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d462`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d4b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d8c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db22`

## string_xrefs

- `0x18003d020`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d07c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d0d4`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d129`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d16e`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d1b9`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d25c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d538`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d600`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003d89e`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003db94`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
      (void *)0x18A9,
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
      (void *)0x18AE,
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
      (void *)0x18B1,
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
      (void *)0x18B4,
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
      (void *)0x18B7,
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
      (void *)0x18BC,
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
        (void *)0x18C1,
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
            (unsigned int)&unk_1801A8EBA,
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
            (unsigned int)&unk_1801A8CCC,
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
    v34 = 6349;
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
      (void *)0x18D4,
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
      (void *)0x18F0,
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
          (unsigned int)&unk_1801A8C1F,
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
          (unsigned int)&unk_1801A8E1A,
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
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnhancedAudioSrvTracing>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnhancedAudioSrvTracing>::GetImpl'::`2'::impl)
          && **(_DWORD **)(a1 + 8288) > 2u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v65 = v6;
          *(_QWORD *)v90 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v59,
            (unsigned int)&unk_1801A8B2E,
            v59,
            v60,
            (__int64)v90,
            (__int64)&v65);
        }
        v8 = -2004287480;
        v33 = 2290679816LL;
        v34 = 6424;
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
            (unsigned int)&unk_1801A8D6A,
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
            (unsigned int)&unk_1801A8B7C,
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
    v50 = 6400;
  }
  else
  {
    v50 = 6398;
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
0x18003cf34  mov     [rsp-8+arg_8], rbx
0x18003cf39  push    rbp
0x18003cf3a  push    rsi
0x18003cf3b  push    rdi
0x18003cf3c  push    r12
0x18003cf3e  push    r13
0x18003cf40  push    r14
0x18003cf42  push    r15
0x18003cf44  lea     rbp, [rsp-90h]
0x18003cf4c  sub     rsp, 190h
0x18003cf53  mov     rax, cs:__security_cookie
0x18003cf5a  xor     rax, rsp
0x18003cf5d  mov     [rbp+0C0h+var_40], rax
0x18003cf64  mov     r14, r8
0x18003cf67  mov     rdi, rcx
0x18003cf6a  mov     [rbp+0C0h+var_128], r9
0x18003cf6e  xor     r13d, r13d
0x18003cf71  mov     [r9], r13
0x18003cf74  lea     r12d, [r13+4]
0x18003cf78  lea     r15d, [r13+3]
0x18003cf7c  mov     [rbp+0C0h+var_C0], 233164C8h
0x18003cf83  mov     [rbp+0C0h+var_BC], 4C7D1B2Ch
0x18003cf8a  mov     [rbp+0C0h+var_B8], 71B668BCh
0x18003cf91  mov     [rbp+0C0h+var_B4], 67257A68h
0x18003cf98  lea     esi, [r13+1]
0x18003cf9c  mov     [rbp+0C0h+var_B0], esi
0x18003cf9f  cmp     edx, r15d
0x18003cfa2  jz      short loc_18003CFC8
0x18003cfa4  mov     r15d, r13d
0x18003cfa7  mov     [rbp+0C0h+var_A8], 9A82A7DBh
0x18003cfae  mov     [rbp+0C0h+var_A4], 41B43EBBh
0x18003cfb5  mov     [rbp+0C0h+var_A0], 0B718BA83h
0x18003cfbc  mov     [rbp+0C0h+var_9C], 0FC181731h
0x18003cfc3  mov     [rbp+0C0h+var_98], esi
0x18003cfc6  jmp     short loc_18003CFEB
0x18003cfc8  mov     [rbp+0C0h+var_A8], 0B3F8FA53h
0x18003cfcf  mov     [rbp+0C0h+var_A4], 438E0004h
0x18003cfd6  mov     [rbp+0C0h+var_A0], 0A4510390h
0x18003cfdd  mov     [rbp+0C0h+var_9C], 0FC9B136Eh
0x18003cfe4  mov     [rbp+0C0h+var_98], 1Dh
0x18003cfeb  xorps   xmm0, xmm0
0x18003cfee  xor     eax, eax
0x18003cff0  movups  xmmword ptr [rbp+0C0h+var_D8], xmm0
0x18003cff4  mov     [rbp+0C0h+var_C8], rax
0x18003cff8  mov     rcx, [rcx+48h]
0x18003cffc  mov     rax, [rcx]
0x18003cfff  lea     r8, [rbp+0C0h+var_D8]
0x18003d003  lea     rdx, [rbp+0C0h+var_C0]
0x18003d007  mov     rax, [rax+28h]
0x18003d00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d010  mov     ebx, eax
0x18003d012  test    eax, eax
0x18003d014  jns     short loc_18003D036
0x18003d016  mov     rcx, [rbp+0C8h]; this
0x18003d01d  mov     r9d, eax; char *
0x18003d020  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d027  mov     edx, 18A9h; void *
0x18003d02c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d031  jmp     loc_18003DBDB
0x18003d036  cmp     word ptr [rbp+0C0h+var_D8], 1Fh
0x18003d03b  jz      short loc_18003D047
0x18003d03d  mov     ebx, 88890004h
0x18003d042  jmp     loc_18003DBDB
0x18003d047  xorps   xmm0, xmm0
0x18003d04a  xor     eax, eax
0x18003d04c  movups  xmmword ptr [rbp+0C0h+pvar], xmm0
0x18003d050  mov     [rbp+0C0h+var_E0], rax
0x18003d054  mov     rcx, [rdi+48h]
0x18003d058  mov     rax, [rcx]
0x18003d05b  lea     r8, [rbp+0C0h+pvar]
0x18003d05f  lea     rdx, [rbp+0C0h+var_A8]
0x18003d063  mov     rax, [rax+28h]
0x18003d067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d06c  mov     ebx, eax
0x18003d06e  test    eax, eax
0x18003d070  jns     short loc_18003D092
0x18003d072  mov     rcx, [rbp+0C8h]; this
0x18003d079  mov     r9d, eax; char *
0x18003d07c  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d083  mov     edx, 18AEh; void *
0x18003d088  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d08d  jmp     loc_18003DBD0
0x18003d092  mov     [rbp+0C0h+var_140], r13
0x18003d096  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18003d09d  mov     rcx, [rax]
0x18003d0a0  mov     rbx, [rcx+28h]
0x18003d0a4  lea     rcx, [rbp+0C0h+var_140]
0x18003d0a8  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18003d0ad  lea     r8, [rbp+0C0h+var_140]
0x18003d0b1  mov     rdx, [rbp+0C0h+var_D8+8]
0x18003d0b5  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18003d0bc  mov     rax, rbx
0x18003d0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0c4  mov     ebx, eax
0x18003d0c6  test    eax, eax
0x18003d0c8  jns     short loc_18003D0EA
0x18003d0ca  mov     rcx, [rbp+0C8h]; this
0x18003d0d1  mov     r9d, eax; char *
0x18003d0d4  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d0db  mov     edx, 18B1h; void *
0x18003d0e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d0e5  jmp     loc_18003DBC6
0x18003d0ea  mov     qword ptr [rbp+0C0h+var_130], r13
0x18003d0ee  mov     rcx, [rbp+0C0h+var_140]
0x18003d0f2  mov     rax, [rcx]
0x18003d0f5  mov     qword ptr [rbp+0C0h+var_130], r13
0x18003d0f9  lea     rdx, [rbp+0C0h+var_130]
0x18003d0fd  mov     qword ptr [rsp+1C0h+var_1A0], rdx; int
0x18003d102  xor     r9d, r9d
0x18003d105  lea     r8d, [r9+17h]
0x18003d109  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x18003d110  mov     rax, [rax+18h]
0x18003d114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d119  mov     ebx, eax
0x18003d11b  test    eax, eax
0x18003d11d  jns     short loc_18003D13F
0x18003d11f  mov     rcx, [rbp+0C8h]; this
0x18003d126  mov     r9d, eax; char *
0x18003d129  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d130  mov     edx, 18B4h; void *
0x18003d135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d13a  jmp     loc_18003DBBC
0x18003d13f  mov     [rbp+0C0h+var_138], r13
0x18003d143  mov     rcx, qword ptr [rbp+0C0h+var_130]
0x18003d147  mov     rax, [rcx]
0x18003d14a  mov     [rbp+0C0h+var_138], r13
0x18003d14e  lea     r8, [rbp+0C0h+var_138]
0x18003d152  mov     edx, dword ptr [rbp+0C0h+pvar+8]
0x18003d155  mov     rax, [rax+38h]
0x18003d159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d15e  mov     ebx, eax
0x18003d160  test    eax, eax
0x18003d162  jns     short loc_18003D184
0x18003d164  mov     rcx, [rbp+0C8h]; this
0x18003d16b  mov     r9d, eax; char *
0x18003d16e  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d175  mov     edx, 18B7h; void *
0x18003d17a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d17f  jmp     loc_18003DBB2
0x18003d184  mov     [rbp+0C0h+var_100], r13
0x18003d188  mov     rcx, [rbp+0C0h+var_138]
0x18003d18c  mov     rax, [rcx]
0x18003d18f  mov     [rbp+0C0h+var_100], r13
0x18003d193  lea     r9, [rbp+0C0h+var_100]
0x18003d197  lea     r8, _GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81
0x18003d19e  mov     edx, esi
0x18003d1a0  mov     rax, [rax+68h]
0x18003d1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1a9  mov     ebx, eax
0x18003d1ab  test    eax, eax
0x18003d1ad  jns     short loc_18003D1D9
0x18003d1af  mov     rcx, [rbp+0C8h]; this
0x18003d1b6  mov     r9d, eax; char *
0x18003d1b9  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d1c0  mov     edx, 18BCh; void *
0x18003d1c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d1ca  nop
0x18003d1cb  lea     rcx, [rbp+0C0h+var_100]
0x18003d1cf  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003d1d4  jmp     loc_18003DBB2
0x18003d1d9  mov     [rbp+0C0h+pv], r13
0x18003d1dd  mov     rcx, [rbp+0C0h+var_100]
0x18003d1e1  mov     rax, [rcx]
0x18003d1e4  lea     rdx, [rbp+0C0h+pv]
0x18003d1e8  mov     [rbp+0C0h+var_80], rdx
0x18003d1ec  mov     [rbp+0C0h+var_80+8], r13
0x18003d1f0  mov     byte ptr [rbp+0C0h+var_70], sil
0x18003d1f4  lea     rdx, [rbp+0C0h+var_80+8]
0x18003d1f8  mov     rax, [rax+20h]
0x18003d1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d201  mov     ebx, eax
0x18003d203  lea     rcx, [rbp+0C0h+var_80]
0x18003d207  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003d20c  shr     ebx, 1Fh
0x18003d20f  xor     bl, sil
0x18003d212  jz      loc_18003D4A3
0x18003d218  movups  xmm0, xmmword ptr [r14]
0x18003d21c  movaps  xmmword ptr [rbp+0C0h+var_80], xmm0
0x18003d220  movups  xmm1, xmmword ptr [r14+10h]
0x18003d225  movaps  [rbp+0C0h+var_70], xmm1
0x18003d229  movups  xmm0, xmmword ptr [r14+20h]
0x18003d22e  movaps  [rbp+0C0h+var_60], xmm0
0x18003d232  movups  xmm1, xmmword ptr [r14+30h]
0x18003d237  movaps  [rbp+0C0h+var_50], xmm1
0x18003d23b  mov     r9, [rbp+0C0h+var_128]
0x18003d23f  mov     r8, [rbp+0C0h+pv]
0x18003d243  lea     rdx, [rbp+0C0h+var_80]
0x18003d247  call    CEndpointCharacteristics__CloneDriverFormatIfMatching__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003d24c  mov     ebx, eax
0x18003d24e  test    eax, eax
0x18003d250  jns     short loc_18003D28A
0x18003d252  mov     rcx, [rbp+0C8h]; this
0x18003d259  mov     r9d, eax; char *
0x18003d25c  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003d263  mov     edx, 18C1h; void *
0x18003d268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d26d  nop
0x18003d26e  mov     rcx, [rbp+0C0h+pv]; pv
0x18003d272  mov     [rbp+0C0h+pv], r13
0x18003d276  test    rcx, rcx
0x18003d279  jz      loc_18003D1CB
0x18003d27f  call    cs:__imp_CoTaskMemFree
0x18003d285  jmp     loc_18003D1CB
0x18003d28a  mov     rax, [rbp+0C0h+var_128]
0x18003d28e  mov     r8, [rax]
0x18003d291  test    r8, r8
0x18003d294  jz      loc_18003D4A3
0x18003d29a  movzx   eax, word ptr [r8]
0x18003d29e  mov     ebx, 0FFFEh
0x18003d2a3  cmp     ax, bx
0x18003d2a6  jnz     loc_18003D383
0x18003d2ac  mov     r9, [rdi+2060h]
0x18003d2b3  mov     eax, [r9]
0x18003d2b6  cmp     eax, r12d
0x18003d2b9  jbe     loc_18003D455
0x18003d2bf  mov     edx, 10h
0x18003d2c4  mov     rcx, r9
0x18003d2c7  call    _tlgKeywordOn
0x18003d2cc  test    al, al
0x18003d2ce  jz      loc_18003D455
0x18003d2d4  mov     eax, [r8+14h]
0x18003d2d8  mov     [rbp+0C0h+var_118], eax
0x18003d2db  lea     rax, [r8+18h]
0x18003d2df  mov     [rsp+1C0h+var_148], rax
0x18003d2e4  mov     rdx, [rbp+0C0h+var_128]
0x18003d2e8  mov     rax, [rdx]
0x18003d2eb  mov     ecx, [rax+8]
0x18003d2ee  mov     [rsp+1C0h+var_158], ecx
0x18003d2f2  mov     rax, [rdx]
0x18003d2f5  mov     ecx, [rax+4]
0x18003d2f8  mov     [rsp+1C0h+var_154], ecx
0x18003d2fc  mov     rax, [rdx]
0x18003d2ff  movzx   ecx, word ptr [rax+2]
0x18003d303  mov     [rsp+1C0h+var_160], cx
0x18003d308  lea     rax, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x18003d30f  mov     [rsp+1C0h+var_150], rax
0x18003d314  mov     [rsp+1C0h+var_15C], r15d
0x18003d319  mov     rax, [rdi+30h]
0x18003d31d  mov     [rbp+0C0h+var_110], rax
0x18003d321  lea     rax, [rbp+0C0h+var_118]
0x18003d325  mov     [rsp+1C0h+var_168], rax
0x18003d32a  lea     rax, [rsp+1C0h+var_148]
0x18003d32f  mov     [rsp+1C0h+var_170], rax
0x18003d334  lea     rax, [rsp+1C0h+var_158]
0x18003d339  mov     [rsp+1C0h+var_178], rax
0x18003d33e  lea     rax, [rsp+1C0h+var_154]
0x18003d343  mov     [rsp+1C0h+var_180], rax
0x18003d348  lea     rax, [rsp+1C0h+var_160]
0x18003d34d  mov     [rsp+1C0h+var_188], rax
0x18003d352  lea     rax, [rsp+1C0h+var_150]
0x18003d357  mov     [rsp+1C0h+var_190], rax
0x18003d35c  lea     rax, [rsp+1C0h+var_15C]
0x18003d361  mov     [rsp+1C0h+var_198], rax
0x18003d366  lea     rax, [rbp+0C0h+var_110]
0x18003d36a  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18003d36f  lea     rdx, unk_1801A8EBA
0x18003d376  mov     rcx, r9
0x18003d379  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$01@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$01@@44AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18003d37e  jmp     loc_18003D455
0x18003d383  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data1
0x18003d38a  movdqu  xmmword ptr [rbp+0C0h+var_90], xmm0
0x18003d38f  mov     [rbp+0C0h+var_90], eax
0x18003d392  mov     r8, [rdi+2060h]
0x18003d399  mov     eax, [r8]
0x18003d39c  cmp     eax, r12d
0x18003d39f  jbe     loc_18003D455
0x18003d3a5  mov     edx, 10h
0x18003d3aa  mov     rcx, r8
0x18003d3ad  call    _tlgKeywordOn
0x18003d3b2  test    al, al
0x18003d3b4  jz      loc_18003D455
0x18003d3ba  lea     rax, [rbp+0C0h+var_90]
0x18003d3be  mov     [rbp+0C0h+var_110], rax
0x18003d3c2  mov     rdx, [rbp+0C0h+var_128]
0x18003d3c6  mov     rax, [rdx]
0x18003d3c9  mov     ecx, [rax+8]
0x18003d3cc  mov     [rsp+1C0h+var_15C], ecx
0x18003d3d0  mov     rax, [rdx]
0x18003d3d3  mov     ecx, [rax+4]
0x18003d3d6  mov     [rsp+1C0h+var_154], ecx
0x18003d3da  mov     rax, [rdx]
0x18003d3dd  movzx   ecx, word ptr [rax+2]
0x18003d3e1  mov     [rsp+1C0h+var_160], cx
0x18003d3e6  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x18003d3ed  mov     [rsp+1C0h+var_148], rax
0x18003d3f2  mov     [rsp+1C0h+var_158], r15d
0x18003d3f7  mov     rax, [rdi+30h]
0x18003d3fb  mov     [rsp+1C0h+var_150], rax
0x18003d400  lea     rax, [rbp+0C0h+var_110]
0x18003d404  mov     [rsp+1C0h+var_170], rax
0x18003d409  lea     rax, [rsp+1C0h+var_15C]
0x18003d40e  mov     [rsp+1C0h+var_178], rax
0x18003d413  lea     rax, [rsp+1C0h+var_154]
0x18003d418  mov     [rsp+1C0h+var_180], rax
0x18003d41d  lea     rax, [rsp+1C0h+var_160]
0x18003d422  mov     [rsp+1C0h+var_188], rax
0x18003d427  lea     rax, [rsp+1C0h+var_148]
0x18003d42c  mov     [rsp+1C0h+var_190], rax
0x18003d431  lea     rax, [rsp+1C0h+var_158]
0x18003d436  mov     [rsp+1C0h+var_198], rax
  ... truncated ...
```
