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
  __int64 v10; // rdx
  HRESULT (__stdcall *GetDevice)(IMMDeviceEnumerator *, LPCWSTR, IMMDevice **); // rbx
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // ebx
  __int64 v21; // rcx
  int v22; // eax
  void *v23; // rcx
  int v24; // eax
  __int64 v25; // r8
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  void *v29; // rcx
  void *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  void *v33; // rcx
  __int64 v34; // r9
  __int64 v35; // rdx
  void *v36; // rcx
  char *v37; // rdx
  int FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77; // eax
  int v39; // r12d
  void *v40; // rcx
  int v41; // eax
  __int64 v42; // r8
  int v43; // r9d
  int v44; // r8d
  int v45; // r9d
  void *v46; // rcx
  void *v47; // rcx
  __int64 v48; // rax
  int v49; // esi
  __int64 v50; // rcx
  __int64 v51; // rdx
  void *v52; // rcx
  bool v53; // zf
  int v54; // eax
  __int64 v55; // r8
  int v56; // r9d
  int v57; // r8d
  int v58; // r9d
  void *v59; // rcx
  int v60; // r8d
  int v61; // r9d
  int v63; // [rsp+20h] [rbp-E0h]
  int *v64; // [rsp+20h] [rbp-E0h]
  _WORD v65[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v66; // [rsp+64h] [rbp-9Ch] BYREF
  int v67; // [rsp+68h] [rbp-98h] BYREF
  int v68; // [rsp+6Ch] [rbp-94h] BYREF
  LPVOID v69; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v70; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v71; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v72; // [rsp+88h] [rbp-78h] BYREF
  int v73[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 **v74; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v75; // [rsp+A0h] [rbp-60h] BYREF
  int v76; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v77; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v79; // [rsp+C0h] [rbp-40h] BYREF
  int *v80; // [rsp+C8h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v82; // [rsp+E0h] [rbp-20h]
  PROPVARIANT v83[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v84; // [rsp+F8h] [rbp-8h]
  _DWORD v85[6]; // [rsp+100h] [rbp+0h] BYREF
  int v86; // [rsp+118h] [rbp+18h] BYREF
  int v87; // [rsp+11Ch] [rbp+1Ch]
  int v88; // [rsp+120h] [rbp+20h]
  int v89; // [rsp+124h] [rbp+24h]
  int v90; // [rsp+128h] [rbp+28h]
  int v91[4]; // [rsp+130h] [rbp+30h] BYREF
  void *v92[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v93; // [rsp+150h] [rbp+50h]
  __int128 v94; // [rsp+160h] [rbp+60h]
  __int128 v95; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v74 = a4;
  *a4 = 0;
  v6 = 3;
  v85[0] = 590439624;
  v85[1] = 1283267372;
  v85[2] = 1907779772;
  v85[3] = 1730509416;
  v85[4] = 1;
  if ( a2 == 3 )
  {
    v86 = -1275528621;
    v87 = 1133379588;
    v88 = -1538194544;
    v89 = -56945810;
    v90 = 29;
  }
  else
  {
    v6 = 0;
    v86 = -1702713381;
    v87 = 1102331579;
    v88 = -1223116157;
    v89 = -65530063;
    v90 = 1;
  }
  *(_OWORD *)v83 = 0;
  v84 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, PROPVARIANT *))(**(_QWORD **)(a1 + 72) + 40LL))(
         *(_QWORD *)(a1 + 72),
         v85,
         v83);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A8,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v7,
      v63);
    goto LABEL_89;
  }
  if ( LOWORD(v83[0]) != 31 )
  {
    v8 = -2004287484;
    goto LABEL_89;
  }
  *(_OWORD *)pvar = 0;
  v82 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *, PROPVARIANT *))(**(_QWORD **)(a1 + 72) + 40LL))(
         *(_QWORD *)(a1 + 72),
         &v86,
         pvar);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18AD,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v9,
      v63);
LABEL_88:
    PropVariantClear(pvar);
    goto LABEL_89;
  }
  v71 = 0;
  GetDevice = g_DeviceEnumerator->lpVtbl->GetDevice;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v71, v10);
  v12 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, PROPVARIANT, __int64 **))GetDevice)(
          g_DeviceEnumerator,
          v83[1],
          &v71);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B0,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v12,
      v63);
LABEL_87:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v71);
    goto LABEL_88;
  }
  *(_QWORD *)v73 = 0;
  v13 = *v71;
  *(_QWORD *)v73 = 0;
  v64 = v73;
  v14 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v13 + 24))(
          v71,
          &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
          23);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B3,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v14,
      (int)v73);
LABEL_86:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v73);
    goto LABEL_87;
  }
  v72 = 0;
  v15 = **(_QWORD **)v73;
  v72 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v15 + 56))(*(_QWORD *)v73, LODWORD(pvar[1]), &v72);
  v8 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B6,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v16,
      (int)v73);
LABEL_85:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v72);
    goto LABEL_86;
  }
  v79 = 0;
  v17 = *v72;
  v79 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64 **))(v17 + 104))(
          v72,
          1,
          &GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81,
          &v79);
  v8 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18BB,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v18,
      (int)v73);
LABEL_18:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v79);
    goto LABEL_85;
  }
  pv = 0;
  v19 = *v79;
  v92[0] = &pv;
  v92[1] = 0;
  LOBYTE(v93) = 1;
  v20 = (*(__int64 (__fastcall **)(__int64 *, void **))(v19 + 32))(v79, &v92[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v92);
  if ( v20 >= 0 )
  {
    *(_OWORD *)v92 = *a3;
    v93 = a3[1];
    v94 = a3[2];
    v95 = a3[3];
    v22 = CEndpointCharacteristics::CloneDriverFormatIfMatching__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
            v21,
            v92,
            pv,
            v74);
    v8 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C0,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v22,
        (int)v73);
      v23 = pv;
      pv = 0;
      if ( v23 )
        CoTaskMemFree(v23);
      goto LABEL_18;
    }
    if ( *v74 )
    {
      v24 = **v74;
      if ( (_WORD)v24 == 0xFFFE )
      {
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v76 = *(_DWORD *)(v25 + 20);
          v70 = (LPVOID)(v25 + 24);
          v67 = *((_DWORD *)*v74 + 2);
          v68 = *((_DWORD *)*v74 + 1);
          v65[0] = (*v74)[1];
          v69 = L"WAVEFORMATEXTENSIBLE";
          v66 = v6;
          v77 = *(const wchar_t **)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)byte_1801AA683,
            v25,
            v26,
            (__int64)&v77,
            (__int64)&v66,
            (__int64)&v69,
            (__int64)v65,
            (__int64)&v68,
            (__int64)&v67,
            (__int64)&v70,
            (__int64)&v76);
        }
      }
      else
      {
        *(GUID *)v91 = GUID_00000000_0000_0010_8000_00aa00389b71;
        v91[0] = v24;
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v77 = (const wchar_t *)v91;
          v66 = *((_DWORD *)*v74 + 2);
          v68 = *((_DWORD *)*v74 + 1);
          v65[0] = (*v74)[1];
          v70 = L"WAVEFORMATEX";
          v67 = v6;
          v69 = *(LPVOID *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v27,
            (unsigned int)byte_1801AA7DB,
            v27,
            v28,
            (__int64)&v69,
            (__int64)&v67,
            (__int64)&v70,
            (__int64)v65,
            (__int64)&v68,
            (__int64)&v66,
            (__int64)&v77);
        }
      }
      v29 = pv;
      pv = 0;
      if ( v29 )
        CoTaskMemFree(v29);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v79);
LABEL_34:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v72);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v73);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v71);
      PropVariantClear(pvar);
      v8 = 0;
      goto LABEL_89;
    }
  }
  v30 = pv;
  pv = 0;
  if ( v30 )
    CoTaskMemFree(v30);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v79);
  v75 = 0;
  v31 = *v72;
  v75 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64 **))(v31 + 104))(
          v72,
          1,
          &GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5,
          &v75);
  v8 = v32;
  if ( v32 < 0 )
  {
    v34 = (unsigned int)v32;
    v35 = 6348;
LABEL_83:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v34,
      (int)v64);
LABEL_84:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v75);
    goto LABEL_85;
  }
  v69 = 0;
  v92[0] = &v69;
  v92[1] = 0;
  LOBYTE(v93) = 1;
  v8 = CTCoAllocPolicy::Alloc(v33, 1u, 0x68u, &v92[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v92);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D3,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v8,
      (int)v73);
    v36 = v69;
    v69 = 0;
    if ( v36 )
      CoTaskMemFree(v36);
    goto LABEL_84;
  }
  *(_DWORD *)v69 = 104;
  *((GUID *)v69 + 1) = GUID_73647561_0000_0010_8000_00aa00389b71;
  *((GUID *)v69 + 3) = GUID_05589f81_c356_11ce_bf01_00aa0055595a;
  *((GUID *)v69 + 2) = GUID_00000001_0000_0010_8000_00aa00389b71;
  v37 = (char *)v69 + 64;
  *((_WORD *)v69 + 32) = -2;
  *(GUID *)(v37 + 24) = GUID_00000000_0000_0010_8000_00aa00389b71;
  *((_DWORD *)v37 + 6) = 1;
  v92[0] = &v75;
  v92[1] = &v69;
  *(_QWORD *)&v93 = a3;
  *((_QWORD *)&v93 + 1) = &v74;
  FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77 = CEndpointCharacteristics::FindFirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77___(
                                                                            a1,
                                                                            v37,
                                                                            v92);
  v39 = FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77;
  if ( FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18EF,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)FirstMatchingPreferredFormat__lambda_c7c9c295e9eb20a9e0b33ea00abada77,
      (int)v73);
    v40 = v69;
    v69 = 0;
    if ( v40 )
      CoTaskMemFree(v40);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v75);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v72);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v73);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v71);
    PropVariantClear(pvar);
    v8 = v39;
    goto LABEL_89;
  }
  if ( *v74 )
  {
    v41 = **v74;
    if ( (_WORD)v41 == 0xFFFE )
    {
      if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
      {
        v66 = *(_DWORD *)(v42 + 20);
        v77 = (const wchar_t *)(v42 + 24);
        v68 = *((_DWORD *)*v74 + 2);
        v67 = *((_DWORD *)*v74 + 1);
        v65[0] = (*v74)[1];
        v70 = L"WAVEFORMATEXTENSIBLE";
        v76 = v6;
        v80 = *(int **)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v43,
          (unsigned int)&word_1801AA72E,
          v42,
          v43,
          (__int64)&v80,
          (__int64)&v76,
          (__int64)&v70,
          (__int64)v65,
          (__int64)&v67,
          (__int64)&v68,
          (__int64)&v77,
          (__int64)&v66);
      }
    }
    else
    {
      *(GUID *)v91 = GUID_00000000_0000_0010_8000_00aa00389b71;
      v91[0] = v41;
      if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
      {
        v80 = v91;
        v66 = *((_DWORD *)*v74 + 2);
        v68 = *((_DWORD *)*v74 + 1);
        v65[0] = (*v74)[1];
        v77 = L"WAVEFORMATEX";
        v67 = v6;
        v70 = *(LPVOID *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v44,
          (unsigned int)word_1801AA4F2,
          v44,
          v45,
          (__int64)&v70,
          (__int64)&v67,
          (__int64)&v77,
          (__int64)v65,
          (__int64)&v68,
          (__int64)&v66,
          (__int64)&v80);
      }
    }
    v46 = v69;
    v69 = 0;
    goto LABEL_55;
  }
  v47 = v69;
  v69 = 0;
  if ( v47 )
    CoTaskMemFree(v47);
  v70 = 0;
  v48 = *v75;
  v92[0] = &v70;
  v92[1] = 0;
  LOBYTE(v93) = 1;
  v49 = (*(__int64 (__fastcall **)(__int64 *, void **))(v48 + 32))(v75, &v92[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v92);
  if ( v49 >= 0 )
  {
    *(_OWORD *)v92 = *a3;
    v93 = a3[1];
    v94 = a3[2];
    v95 = a3[3];
    v49 = CEndpointCharacteristics::CloneDriverFormatIfMatching__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
            v50,
            v92,
            v70,
            v74);
    if ( v49 >= 0 )
    {
      if ( !*v74 )
      {
        v59 = v70;
        v70 = 0;
        if ( v59 )
          CoTaskMemFree(v59);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnhancedAudioSrvTracing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnhancedAudioSrvTracing>::GetImpl'::`2'::impl)
          && **(_DWORD **)(a1 + 8288) > 2u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v66 = v6;
          *(_QWORD *)v91 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v60,
            (unsigned int)word_1801AA592,
            v60,
            v61,
            (__int64)v91,
            (__int64)&v66);
        }
        v8 = -2004287480;
        v34 = 2290679816LL;
        v35 = 6423;
        goto LABEL_83;
      }
      v54 = **v74;
      if ( (_WORD)v54 == 0xFFFE )
      {
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v66 = *(_DWORD *)(v55 + 20);
          v80 = (int *)(v55 + 24);
          v68 = *((_DWORD *)*v74 + 2);
          v67 = *((_DWORD *)*v74 + 1);
          v65[0] = (*v74)[1];
          v77 = L"WAVEFORMATEXTENSIBLE";
          v76 = v6;
          *(_QWORD *)v91 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v56,
            (unsigned int)word_1801AA442,
            v55,
            v56,
            (__int64)v91,
            (__int64)&v76,
            (__int64)&v77,
            (__int64)v65,
            (__int64)&v67,
            (__int64)&v68,
            (__int64)&v80,
            (__int64)&v66);
        }
      }
      else
      {
        *(GUID *)v92 = GUID_00000000_0000_0010_8000_00aa00389b71;
        LODWORD(v92[0]) = v54;
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          *(_QWORD *)v91 = v92;
          v66 = *((_DWORD *)*v74 + 2);
          v68 = *((_DWORD *)*v74 + 1);
          v65[0] = (*v74)[1];
          v80 = (int *)L"WAVEFORMATEX";
          v67 = v6;
          v77 = *(const wchar_t **)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v57,
            (unsigned int)&unk_1801AA5E0,
            v57,
            v58,
            (__int64)&v77,
            (__int64)&v67,
            (__int64)&v80,
            (__int64)v65,
            (__int64)&v68,
            (__int64)&v66,
            (__int64)v91);
        }
      }
      v46 = v70;
      v70 = 0;
LABEL_55:
      if ( v46 )
        CoTaskMemFree(v46);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v75);
      goto LABEL_34;
    }
    v51 = 6399;
  }
  else
  {
    v51 = 6397;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v51,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
    (const char *)(unsigned int)v49,
    (int)v73);
  v52 = v70;
  v53 = v70 == 0;
  v70 = 0;
  if ( !v53 )
    CoTaskMemFree(v52);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v75);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v72);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v73);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v71);
  PropVariantClear(pvar);
  v8 = v49;
LABEL_89:
  PropVariantClear(v83);
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
