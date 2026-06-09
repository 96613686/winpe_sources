# CEndpointCharacteristics::GetComputedDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___

- ea: `0x18013b134`
- end: `0x18013bde4`
- name: `CEndpointCharacteristics::GetComputedDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___`
- size: `3248`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c858`

## callees

- `0x180001980`
- `0x180003b80`
- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x1800423cc`
- `0x180044f40`
- `0x180051fc0`
- `0x1800661c8`
- `0x180073310`
- `0x1800cf8c0`
- `0x1800e58e8`
- `0x18013ac6c`
- `0x18013b134`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013b67d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013b83c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013badc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013bdaa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013bdb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013b67d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013b83c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013badc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013bdaa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013bdb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b64a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b809`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ba1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ba3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013baa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bcf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b64a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b809`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ba1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ba3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013baa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bcf8`

## string_xrefs

- `0x18013b21a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b276`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b2ce`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b323`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b368`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b3b3`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b444`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b720`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b7e8`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013ba86`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013bd6a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CEndpointCharacteristics::GetComputedDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
        __int64 a1,
        int a2,
        _OWORD *a3,
        unsigned __int16 **a4)
{
  int v6; // r14d
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
  int FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710; // eax
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
  void *v90[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v91; // [rsp+140h] [rbp+40h]
  int v92[4]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

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
  v90[0] = &pv;
  v90[1] = 0;
  LOBYTE(v91) = 1;
  v19 = (*(__int64 (__fastcall **)(__int64 *, void **))(v18 + 32))(v78, &v90[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v90);
  if ( v19 >= 0 )
  {
    *(_OWORD *)v90 = *a3;
    v91 = a3[1];
    v21 = CEndpointCharacteristics::CloneDriverFormatIfMatching__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
            v20,
            v90,
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
            (unsigned int)&unk_1801A91A4,
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
        *(GUID *)v92 = GUID_00000000_0000_0010_8000_00aa00389b71;
        v92[0] = v23;
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v76 = (const wchar_t *)v92;
          v65 = *((_DWORD *)*v73 + 2);
          v67 = *((_DWORD *)*v73 + 1);
          v64[0] = (*v73)[1];
          v69 = L"WAVEFORMATEX";
          v66 = v6;
          v68 = *(LPVOID *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v26,
            (unsigned int)&unk_1801A9106,
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
  v90[0] = &v68;
  v90[1] = 0;
  LOBYTE(v91) = 1;
  v8 = CTCoAllocPolicy::Alloc(v32, 1u, 0x68u, &v90[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v90);
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
  v90[0] = &v74;
  v90[1] = &v68;
  *(_QWORD *)&v91 = a3;
  *((_QWORD *)&v91 + 1) = &v73;
  FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710 = CEndpointCharacteristics::FindFirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710___(
                                                                            a1,
                                                                            v36,
                                                                            v90);
  v38 = FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710;
  if ( FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F0,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710,
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
          (unsigned int)&unk_1801A92EF,
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
      *(GUID *)v92 = GUID_00000000_0000_0010_8000_00aa00389b71;
      v92[0] = v40;
      if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
      {
        v79 = v92;
        v65 = *((_DWORD *)*v73 + 2);
        v67 = *((_DWORD *)*v73 + 1);
        v64[0] = (*v73)[1];
        v76 = L"WAVEFORMATEX";
        v66 = v6;
        v69 = *(LPVOID *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v43,
          (unsigned int)&unk_1801A924F,
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
  v90[0] = &v69;
  v90[1] = 0;
  LOBYTE(v91) = 1;
  v48 = (*(__int64 (__fastcall **)(__int64 *, void **))(v47 + 32))(v74, &v90[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v90);
  if ( v48 >= 0 )
  {
    *(_OWORD *)v90 = *a3;
    v91 = a3[1];
    v48 = CEndpointCharacteristics::CloneDriverFormatIfMatching__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
            v49,
            v90,
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
          *(_QWORD *)v92 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v59,
            (unsigned int)&unk_1801A9015,
            v59,
            v60,
            (__int64)v92,
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
          *(_QWORD *)v92 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v55,
            (unsigned int)&unk_1801A8F65,
            v54,
            v55,
            (__int64)v92,
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
        *(GUID *)v90 = GUID_00000000_0000_0010_8000_00aa00389b71;
        LODWORD(v90[0]) = v53;
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          *(_QWORD *)v92 = v90;
          v65 = *((_DWORD *)*v73 + 2);
          v67 = *((_DWORD *)*v73 + 1);
          v64[0] = (*v73)[1];
          v79 = (int *)L"WAVEFORMATEX";
          v66 = v6;
          v76 = *(const wchar_t **)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v56,
            (unsigned int)&unk_1801A9063,
            v56,
            v57,
            (__int64)&v76,
            (__int64)&v66,
            (__int64)&v79,
            (__int64)v64,
            (__int64)&v67,
            (__int64)&v65,
            (__int64)v92);
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
0x18013b134  mov     [rsp-8+arg_8], rbx
0x18013b139  push    rbp
0x18013b13a  push    rsi
0x18013b13b  push    rdi
0x18013b13c  push    r12
0x18013b13e  push    r13
0x18013b140  push    r14
0x18013b142  push    r15
0x18013b144  lea     rbp, [rsp-70h]
0x18013b149  sub     rsp, 170h
0x18013b150  mov     rax, cs:__security_cookie
0x18013b157  xor     rax, rsp
0x18013b15a  mov     [rbp+0A0h+var_40], rax
0x18013b15e  mov     r15, r8
0x18013b161  mov     rdi, rcx
0x18013b164  mov     [rbp+0A0h+var_108], r9
0x18013b168  xor     r13d, r13d
0x18013b16b  mov     [r9], r13
0x18013b16e  lea     r12d, [r13+4]
0x18013b172  lea     r14d, [r13+3]
0x18013b176  mov     [rbp+0A0h+var_A0], 233164C8h
0x18013b17d  mov     [rbp+0A0h+var_9C], 4C7D1B2Ch
0x18013b184  mov     [rbp+0A0h+var_98], 71B668BCh
0x18013b18b  mov     [rbp+0A0h+var_94], 67257A68h
0x18013b192  lea     esi, [r13+1]
0x18013b196  mov     [rbp+0A0h+var_90], esi
0x18013b199  cmp     edx, r14d
0x18013b19c  jz      short loc_18013B1C2
0x18013b19e  mov     r14d, r13d
0x18013b1a1  mov     [rbp+0A0h+var_88], 9A82A7DBh
0x18013b1a8  mov     [rbp+0A0h+var_84], 41B43EBBh
0x18013b1af  mov     [rbp+0A0h+var_80], 0B718BA83h
0x18013b1b6  mov     [rbp+0A0h+var_7C], 0FC181731h
0x18013b1bd  mov     [rbp+0A0h+var_78], esi
0x18013b1c0  jmp     short loc_18013B1E5
0x18013b1c2  mov     [rbp+0A0h+var_88], 0B3F8FA53h
0x18013b1c9  mov     [rbp+0A0h+var_84], 438E0004h
0x18013b1d0  mov     [rbp+0A0h+var_80], 0A4510390h
0x18013b1d7  mov     [rbp+0A0h+var_7C], 0FC9B136Eh
0x18013b1de  mov     [rbp+0A0h+var_78], 1Dh
0x18013b1e5  xorps   xmm0, xmm0
0x18013b1e8  xor     eax, eax
0x18013b1ea  movups  xmmword ptr [rbp+0A0h+var_B8], xmm0
0x18013b1ee  mov     [rbp+0A0h+var_A8], rax
0x18013b1f2  mov     rcx, [rcx+48h]
0x18013b1f6  mov     rax, [rcx]
0x18013b1f9  lea     r8, [rbp+0A0h+var_B8]
0x18013b1fd  lea     rdx, [rbp+0A0h+var_A0]
0x18013b201  mov     rax, [rax+28h]
0x18013b205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b20a  mov     ebx, eax
0x18013b20c  test    eax, eax
0x18013b20e  jns     short loc_18013B230
0x18013b210  mov     rcx, [rbp+0A8h]; this
0x18013b217  mov     r9d, eax; char *
0x18013b21a  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b221  mov     edx, 18A9h; void *
0x18013b226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b22b  jmp     loc_18013BDB1
0x18013b230  cmp     word ptr [rbp+0A0h+var_B8], 1Fh
0x18013b235  jz      short loc_18013B241
0x18013b237  mov     ebx, 88890004h
0x18013b23c  jmp     loc_18013BDB1
0x18013b241  xorps   xmm0, xmm0
0x18013b244  xor     eax, eax
0x18013b246  movups  xmmword ptr [rbp+0A0h+pvar], xmm0
0x18013b24a  mov     [rbp+0A0h+var_C0], rax
0x18013b24e  mov     rcx, [rdi+48h]
0x18013b252  mov     rax, [rcx]
0x18013b255  lea     r8, [rbp+0A0h+pvar]
0x18013b259  lea     rdx, [rbp+0A0h+var_88]
0x18013b25d  mov     rax, [rax+28h]
0x18013b261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b266  mov     ebx, eax
0x18013b268  test    eax, eax
0x18013b26a  jns     short loc_18013B28C
0x18013b26c  mov     rcx, [rbp+0A8h]; this
0x18013b273  mov     r9d, eax; char *
0x18013b276  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b27d  mov     edx, 18AEh; void *
0x18013b282  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b287  jmp     loc_18013BDA6
0x18013b28c  mov     [rbp+0A0h+var_120], r13
0x18013b290  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18013b297  mov     rcx, [rax]
0x18013b29a  mov     rbx, [rcx+28h]
0x18013b29e  lea     rcx, [rbp+0A0h+var_120]
0x18013b2a2  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18013b2a7  lea     r8, [rbp+0A0h+var_120]
0x18013b2ab  mov     rdx, [rbp+0A0h+var_B8+8]
0x18013b2af  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18013b2b6  mov     rax, rbx
0x18013b2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b2be  mov     ebx, eax
0x18013b2c0  test    eax, eax
0x18013b2c2  jns     short loc_18013B2E4
0x18013b2c4  mov     rcx, [rbp+0A8h]; this
0x18013b2cb  mov     r9d, eax; char *
0x18013b2ce  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b2d5  mov     edx, 18B1h; void *
0x18013b2da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b2df  jmp     loc_18013BD9C
0x18013b2e4  mov     qword ptr [rbp+0A0h+var_110], r13
0x18013b2e8  mov     rcx, [rbp+0A0h+var_120]
0x18013b2ec  mov     rax, [rcx]
0x18013b2ef  mov     qword ptr [rbp+0A0h+var_110], r13
0x18013b2f3  lea     rdx, [rbp+0A0h+var_110]
0x18013b2f7  mov     qword ptr [rsp+1A0h+var_180], rdx; int
0x18013b2fc  xor     r9d, r9d
0x18013b2ff  lea     r8d, [r9+17h]
0x18013b303  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x18013b30a  mov     rax, [rax+18h]
0x18013b30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b313  mov     ebx, eax
0x18013b315  test    eax, eax
0x18013b317  jns     short loc_18013B339
0x18013b319  mov     rcx, [rbp+0A8h]; this
0x18013b320  mov     r9d, eax; char *
0x18013b323  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b32a  mov     edx, 18B4h; void *
0x18013b32f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b334  jmp     loc_18013BD92
0x18013b339  mov     [rbp+0A0h+var_118], r13
0x18013b33d  mov     rcx, qword ptr [rbp+0A0h+var_110]
0x18013b341  mov     rax, [rcx]
0x18013b344  mov     [rbp+0A0h+var_118], r13
0x18013b348  lea     r8, [rbp+0A0h+var_118]
0x18013b34c  mov     edx, dword ptr [rbp+0A0h+pvar+8]
0x18013b34f  mov     rax, [rax+38h]
0x18013b353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b358  mov     ebx, eax
0x18013b35a  test    eax, eax
0x18013b35c  jns     short loc_18013B37E
0x18013b35e  mov     rcx, [rbp+0A8h]; this
0x18013b365  mov     r9d, eax; char *
0x18013b368  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b36f  mov     edx, 18B7h; void *
0x18013b374  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b379  jmp     loc_18013BD88
0x18013b37e  mov     [rbp+0A0h+var_E0], r13
0x18013b382  mov     rcx, [rbp+0A0h+var_118]
0x18013b386  mov     rax, [rcx]
0x18013b389  mov     [rbp+0A0h+var_E0], r13
0x18013b38d  lea     r9, [rbp+0A0h+var_E0]
0x18013b391  lea     r8, _GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81
0x18013b398  mov     edx, esi
0x18013b39a  mov     rax, [rax+68h]
0x18013b39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b3a3  mov     ebx, eax
0x18013b3a5  test    eax, eax
0x18013b3a7  jns     short loc_18013B3D3
0x18013b3a9  mov     rcx, [rbp+0A8h]; this
0x18013b3b0  mov     r9d, eax; char *
0x18013b3b3  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b3ba  mov     edx, 18BCh; void *
0x18013b3bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b3c4  nop
0x18013b3c5  lea     rcx, [rbp+0A0h+var_E0]
0x18013b3c9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18013b3ce  jmp     loc_18013BD88
0x18013b3d3  mov     [rbp+0A0h+pv], r13
0x18013b3d7  mov     rcx, [rbp+0A0h+var_E0]
0x18013b3db  mov     rax, [rcx]
0x18013b3de  lea     rdx, [rbp+0A0h+pv]
0x18013b3e2  mov     [rbp+0A0h+var_70], rdx
0x18013b3e6  mov     [rbp+0A0h+var_70+8], r13
0x18013b3ea  mov     byte ptr [rbp+0A0h+var_60], sil
0x18013b3ee  lea     rdx, [rbp+0A0h+var_70+8]
0x18013b3f2  mov     rax, [rax+20h]
0x18013b3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b3fb  mov     ebx, eax
0x18013b3fd  lea     rcx, [rbp+0A0h+var_70]
0x18013b401  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18013b406  shr     ebx, 1Fh
0x18013b409  xor     bl, sil
0x18013b40c  jz      loc_18013B68B
0x18013b412  movups  xmm0, xmmword ptr [r15]
0x18013b416  movaps  xmmword ptr [rbp+0A0h+var_70], xmm0
0x18013b41a  movups  xmm1, xmmword ptr [r15+10h]
0x18013b41f  movaps  [rbp+0A0h+var_60], xmm1
0x18013b423  mov     r9, [rbp+0A0h+var_108]
0x18013b427  mov     r8, [rbp+0A0h+pv]
0x18013b42b  lea     rdx, [rbp+0A0h+var_70]
0x18013b42f  call    CEndpointCharacteristics__CloneDriverFormatIfMatching__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x18013b434  mov     ebx, eax
0x18013b436  test    eax, eax
0x18013b438  jns     short loc_18013B472
0x18013b43a  mov     rcx, [rbp+0A8h]; this
0x18013b441  mov     r9d, eax; char *
0x18013b444  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b44b  mov     edx, 18C1h; void *
0x18013b450  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b455  nop
0x18013b456  mov     rcx, [rbp+0A0h+pv]; pv
0x18013b45a  mov     [rbp+0A0h+pv], r13
0x18013b45e  test    rcx, rcx
0x18013b461  jz      loc_18013B3C5
0x18013b467  call    cs:__imp_CoTaskMemFree
0x18013b46d  jmp     loc_18013B3C5
0x18013b472  mov     rax, [rbp+0A0h+var_108]
0x18013b476  mov     r8, [rax]
0x18013b479  test    r8, r8
0x18013b47c  jz      loc_18013B68B
0x18013b482  movzx   eax, word ptr [r8]
0x18013b486  mov     ebx, 0FFFEh
0x18013b48b  cmp     ax, bx
0x18013b48e  jnz     loc_18013B56B
0x18013b494  mov     r9, [rdi+2060h]
0x18013b49b  mov     eax, [r9]
0x18013b49e  cmp     eax, r12d
0x18013b4a1  jbe     loc_18013B63D
0x18013b4a7  mov     edx, 10h
0x18013b4ac  mov     rcx, r9
0x18013b4af  call    _tlgKeywordOn
0x18013b4b4  test    al, al
0x18013b4b6  jz      loc_18013B63D
0x18013b4bc  mov     eax, [r8+14h]
0x18013b4c0  mov     [rbp+0A0h+var_F8], eax
0x18013b4c3  lea     rax, [r8+18h]
0x18013b4c7  mov     [rsp+1A0h+var_128], rax
0x18013b4cc  mov     rdx, [rbp+0A0h+var_108]
0x18013b4d0  mov     rax, [rdx]
0x18013b4d3  mov     ecx, [rax+8]
0x18013b4d6  mov     [rsp+1A0h+var_138], ecx
0x18013b4da  mov     rax, [rdx]
0x18013b4dd  mov     ecx, [rax+4]
0x18013b4e0  mov     [rsp+1A0h+var_134], ecx
0x18013b4e4  mov     rax, [rdx]
0x18013b4e7  movzx   ecx, word ptr [rax+2]
0x18013b4eb  mov     [rsp+1A0h+var_140], cx
0x18013b4f0  lea     rax, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x18013b4f7  mov     [rsp+1A0h+var_130], rax
0x18013b4fc  mov     [rsp+1A0h+var_13C], r14d
0x18013b501  mov     rax, [rdi+30h]
0x18013b505  mov     [rbp+0A0h+var_F0], rax
0x18013b509  lea     rax, [rbp+0A0h+var_F8]
0x18013b50d  mov     [rsp+1A0h+var_148], rax
0x18013b512  lea     rax, [rsp+1A0h+var_128]
0x18013b517  mov     [rsp+1A0h+var_150], rax
0x18013b51c  lea     rax, [rsp+1A0h+var_138]
0x18013b521  mov     [rsp+1A0h+var_158], rax
0x18013b526  lea     rax, [rsp+1A0h+var_134]
0x18013b52b  mov     [rsp+1A0h+var_160], rax
0x18013b530  lea     rax, [rsp+1A0h+var_140]
0x18013b535  mov     [rsp+1A0h+var_168], rax
0x18013b53a  lea     rax, [rsp+1A0h+var_130]
0x18013b53f  mov     [rsp+1A0h+var_170], rax
0x18013b544  lea     rax, [rsp+1A0h+var_13C]
0x18013b549  mov     [rsp+1A0h+var_178], rax
0x18013b54e  lea     rax, [rbp+0A0h+var_F0]
0x18013b552  mov     qword ptr [rsp+1A0h+var_180], rax
0x18013b557  lea     rdx, unk_1801A91A4
0x18013b55e  mov     rcx, r9
0x18013b561  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$01@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$01@@44AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18013b566  jmp     loc_18013B63D
0x18013b56b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data1
0x18013b572  movdqu  xmmword ptr [rbp+0A0h+var_50], xmm0
0x18013b577  mov     [rbp+0A0h+var_50], eax
0x18013b57a  mov     r8, [rdi+2060h]
0x18013b581  mov     eax, [r8]
0x18013b584  cmp     eax, r12d
0x18013b587  jbe     loc_18013B63D
0x18013b58d  mov     edx, 10h
0x18013b592  mov     rcx, r8
0x18013b595  call    _tlgKeywordOn
0x18013b59a  test    al, al
0x18013b59c  jz      loc_18013B63D
0x18013b5a2  lea     rax, [rbp+0A0h+var_50]
0x18013b5a6  mov     [rbp+0A0h+var_F0], rax
0x18013b5aa  mov     rdx, [rbp+0A0h+var_108]
0x18013b5ae  mov     rax, [rdx]
0x18013b5b1  mov     ecx, [rax+8]
0x18013b5b4  mov     [rsp+1A0h+var_13C], ecx
0x18013b5b8  mov     rax, [rdx]
0x18013b5bb  mov     ecx, [rax+4]
0x18013b5be  mov     [rsp+1A0h+var_134], ecx
0x18013b5c2  mov     rax, [rdx]
0x18013b5c5  movzx   ecx, word ptr [rax+2]
0x18013b5c9  mov     [rsp+1A0h+var_140], cx
0x18013b5ce  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x18013b5d5  mov     [rsp+1A0h+var_128], rax
0x18013b5da  mov     [rsp+1A0h+var_138], r14d
0x18013b5df  mov     rax, [rdi+30h]
0x18013b5e3  mov     [rsp+1A0h+var_130], rax
0x18013b5e8  lea     rax, [rbp+0A0h+var_F0]
0x18013b5ec  mov     [rsp+1A0h+var_150], rax
0x18013b5f1  lea     rax, [rsp+1A0h+var_13C]
0x18013b5f6  mov     [rsp+1A0h+var_158], rax
0x18013b5fb  lea     rax, [rsp+1A0h+var_134]
0x18013b600  mov     [rsp+1A0h+var_160], rax
0x18013b605  lea     rax, [rsp+1A0h+var_140]
0x18013b60a  mov     [rsp+1A0h+var_168], rax
0x18013b60f  lea     rax, [rsp+1A0h+var_128]
0x18013b614  mov     [rsp+1A0h+var_170], rax
0x18013b619  lea     rax, [rsp+1A0h+var_138]
0x18013b61e  mov     [rsp+1A0h+var_178], rax
0x18013b623  lea     rax, [rsp+1A0h+var_130]
0x18013b628  mov     qword ptr [rsp+1A0h+var_180], rax
0x18013b62d  lea     rdx, unk_1801A9106
0x18013b634  mov     rcx, r8
  ... truncated ...
```
