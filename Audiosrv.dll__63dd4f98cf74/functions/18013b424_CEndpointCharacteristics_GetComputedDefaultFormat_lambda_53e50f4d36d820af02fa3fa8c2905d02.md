# CEndpointCharacteristics::GetComputedDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___

- ea: `0x18013b424`
- end: `0x18013c0d4`
- name: `CEndpointCharacteristics::GetComputedDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___`
- size: `3248`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c9b8`

## callees

- `0x180001980`
- `0x180003d8c`
- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x1800424ec`
- `0x180044ab0`
- `0x180051b30`
- `0x180065d38`
- `0x180072e10`
- `0x1800cd8d0`
- `0x1800e5168`
- `0x18013af5c`
- `0x18013b424`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013b96d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013bb2c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013bdcc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013c09a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013c0a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013b96d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013bb2c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013bdcc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013c09a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18013c0a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ba35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013baf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bd0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bd2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bd99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bfe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013b988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ba35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013baf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bd0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bd2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bd99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013bfe8`

## string_xrefs

- `0x18013b50a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b566`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b5be`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b613`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b658`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b6a3`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013b734`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013ba10`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013bad8`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013bd76`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18013c05a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
  int FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710; // eax
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
  void *v91[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v92; // [rsp+140h] [rbp+40h]
  int v93[4]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

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
  v91[0] = &pv;
  v91[1] = 0;
  LOBYTE(v92) = 1;
  v20 = (*(__int64 (__fastcall **)(__int64 *, void **))(v19 + 32))(v79, &v91[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v91);
  if ( v20 >= 0 )
  {
    *(_OWORD *)v91 = *a3;
    v92 = a3[1];
    v22 = CEndpointCharacteristics::CloneDriverFormatIfMatching__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
            v21,
            v91,
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
            (unsigned int)byte_1801AAC05,
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
        *(GUID *)v93 = GUID_00000000_0000_0010_8000_00aa00389b71;
        v93[0] = v24;
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          v77 = (const wchar_t *)v93;
          v66 = *((_DWORD *)*v74 + 2);
          v68 = *((_DWORD *)*v74 + 1);
          v65[0] = (*v74)[1];
          v70 = L"WAVEFORMATEX";
          v67 = v6;
          v69 = *(LPVOID *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v27,
            (unsigned int)&byte_1801AAAC7,
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
  v91[0] = &v69;
  v91[1] = 0;
  LOBYTE(v92) = 1;
  v8 = CTCoAllocPolicy::Alloc(v33, 1u, 0x68u, &v91[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v91);
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
  v91[0] = &v75;
  v91[1] = &v69;
  *(_QWORD *)&v92 = a3;
  *((_QWORD *)&v92 + 1) = &v74;
  FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710 = CEndpointCharacteristics::FindFirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710___(
                                                                            a1,
                                                                            v37,
                                                                            v91);
  v39 = FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710;
  if ( FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18EF,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)FirstMatchingPreferredFormat__lambda_2d57628cd8490ef0d12835f9ba011710,
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
          (unsigned int)word_1801AAA1A,
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
      *(GUID *)v93 = GUID_00000000_0000_0010_8000_00aa00389b71;
      v93[0] = v41;
      if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
      {
        v80 = v93;
        v66 = *((_DWORD *)*v74 + 2);
        v68 = *((_DWORD *)*v74 + 1);
        v65[0] = (*v74)[1];
        v77 = L"WAVEFORMATEX";
        v67 = v6;
        v70 = *(LPVOID *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v44,
          (unsigned int)byte_1801AAB65,
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
  v91[0] = &v70;
  v91[1] = 0;
  LOBYTE(v92) = 1;
  v49 = (*(__int64 (__fastcall **)(__int64 *, void **))(v48 + 32))(v75, &v91[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v91);
  if ( v49 >= 0 )
  {
    *(_OWORD *)v91 = *a3;
    v92 = a3[1];
    v49 = CEndpointCharacteristics::CloneDriverFormatIfMatching__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
            v50,
            v91,
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
          *(_QWORD *)v93 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v60,
            (unsigned int)&dword_1801AA9CC,
            v60,
            v61,
            (__int64)v93,
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
          *(_QWORD *)v93 = *(_QWORD *)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v56,
            (unsigned int)&dword_1801AA91C,
            v55,
            v56,
            (__int64)v93,
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
        *(GUID *)v91 = GUID_00000000_0000_0010_8000_00aa00389b71;
        LODWORD(v91[0]) = v54;
        if ( **(_DWORD **)(a1 + 8288) > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(a1 + 8288), 16) )
        {
          *(_QWORD *)v93 = v91;
          v66 = *((_DWORD *)*v74 + 2);
          v68 = *((_DWORD *)*v74 + 1);
          v65[0] = (*v74)[1];
          v80 = (int *)L"WAVEFORMATEX";
          v67 = v6;
          v77 = *(const wchar_t **)(a1 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v57,
            (unsigned int)byte_1801AA879,
            v57,
            v58,
            (__int64)&v77,
            (__int64)&v67,
            (__int64)&v80,
            (__int64)v65,
            (__int64)&v68,
            (__int64)&v66,
            (__int64)v93);
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
0x18013b424  mov     [rsp-8+arg_8], rbx
0x18013b429  push    rbp
0x18013b42a  push    rsi
0x18013b42b  push    rdi
0x18013b42c  push    r12
0x18013b42e  push    r13
0x18013b430  push    r14
0x18013b432  push    r15
0x18013b434  lea     rbp, [rsp-70h]
0x18013b439  sub     rsp, 170h
0x18013b440  mov     rax, cs:__security_cookie
0x18013b447  xor     rax, rsp
0x18013b44a  mov     [rbp+0A0h+var_40], rax
0x18013b44e  mov     r15, r8
0x18013b451  mov     rdi, rcx
0x18013b454  mov     [rbp+0A0h+var_108], r9
0x18013b458  xor     r13d, r13d
0x18013b45b  mov     [r9], r13
0x18013b45e  lea     r12d, [r13+4]
0x18013b462  lea     r14d, [r13+3]
0x18013b466  mov     [rbp+0A0h+var_A0], 233164C8h
0x18013b46d  mov     [rbp+0A0h+var_9C], 4C7D1B2Ch
0x18013b474  mov     [rbp+0A0h+var_98], 71B668BCh
0x18013b47b  mov     [rbp+0A0h+var_94], 67257A68h
0x18013b482  lea     esi, [r13+1]
0x18013b486  mov     [rbp+0A0h+var_90], esi
0x18013b489  cmp     edx, r14d
0x18013b48c  jz      short loc_18013B4B2
0x18013b48e  mov     r14d, r13d
0x18013b491  mov     [rbp+0A0h+var_88], 9A82A7DBh
0x18013b498  mov     [rbp+0A0h+var_84], 41B43EBBh
0x18013b49f  mov     [rbp+0A0h+var_80], 0B718BA83h
0x18013b4a6  mov     [rbp+0A0h+var_7C], 0FC181731h
0x18013b4ad  mov     [rbp+0A0h+var_78], esi
0x18013b4b0  jmp     short loc_18013B4D5
0x18013b4b2  mov     [rbp+0A0h+var_88], 0B3F8FA53h
0x18013b4b9  mov     [rbp+0A0h+var_84], 438E0004h
0x18013b4c0  mov     [rbp+0A0h+var_80], 0A4510390h
0x18013b4c7  mov     [rbp+0A0h+var_7C], 0FC9B136Eh
0x18013b4ce  mov     [rbp+0A0h+var_78], 1Dh
0x18013b4d5  xorps   xmm0, xmm0
0x18013b4d8  xor     eax, eax
0x18013b4da  movups  xmmword ptr [rbp+0A0h+var_B8], xmm0
0x18013b4de  mov     [rbp+0A0h+var_A8], rax
0x18013b4e2  mov     rcx, [rcx+48h]
0x18013b4e6  mov     rax, [rcx]
0x18013b4e9  lea     r8, [rbp+0A0h+var_B8]
0x18013b4ed  lea     rdx, [rbp+0A0h+var_A0]
0x18013b4f1  mov     rax, [rax+28h]
0x18013b4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b4fa  mov     ebx, eax
0x18013b4fc  test    eax, eax
0x18013b4fe  jns     short loc_18013B520
0x18013b500  mov     rcx, [rbp+0A8h]; this
0x18013b507  mov     r9d, eax; char *
0x18013b50a  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b511  mov     edx, 18A8h; void *
0x18013b516  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b51b  jmp     loc_18013C0A1
0x18013b520  cmp     word ptr [rbp+0A0h+var_B8], 1Fh
0x18013b525  jz      short loc_18013B531
0x18013b527  mov     ebx, 88890004h
0x18013b52c  jmp     loc_18013C0A1
0x18013b531  xorps   xmm0, xmm0
0x18013b534  xor     eax, eax
0x18013b536  movups  xmmword ptr [rbp+0A0h+pvar], xmm0
0x18013b53a  mov     [rbp+0A0h+var_C0], rax
0x18013b53e  mov     rcx, [rdi+48h]
0x18013b542  mov     rax, [rcx]
0x18013b545  lea     r8, [rbp+0A0h+pvar]
0x18013b549  lea     rdx, [rbp+0A0h+var_88]
0x18013b54d  mov     rax, [rax+28h]
0x18013b551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b556  mov     ebx, eax
0x18013b558  test    eax, eax
0x18013b55a  jns     short loc_18013B57C
0x18013b55c  mov     rcx, [rbp+0A8h]; this
0x18013b563  mov     r9d, eax; char *
0x18013b566  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b56d  mov     edx, 18ADh; void *
0x18013b572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b577  jmp     loc_18013C096
0x18013b57c  mov     [rbp+0A0h+var_120], r13
0x18013b580  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18013b587  mov     rcx, [rax]
0x18013b58a  mov     rbx, [rcx+28h]
0x18013b58e  lea     rcx, [rbp+0A0h+var_120]
0x18013b592  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18013b597  lea     r8, [rbp+0A0h+var_120]
0x18013b59b  mov     rdx, [rbp+0A0h+var_B8+8]
0x18013b59f  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18013b5a6  mov     rax, rbx
0x18013b5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b5ae  mov     ebx, eax
0x18013b5b0  test    eax, eax
0x18013b5b2  jns     short loc_18013B5D4
0x18013b5b4  mov     rcx, [rbp+0A8h]; this
0x18013b5bb  mov     r9d, eax; char *
0x18013b5be  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b5c5  mov     edx, 18B0h; void *
0x18013b5ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b5cf  jmp     loc_18013C08C
0x18013b5d4  mov     qword ptr [rbp+0A0h+var_110], r13
0x18013b5d8  mov     rcx, [rbp+0A0h+var_120]
0x18013b5dc  mov     rax, [rcx]
0x18013b5df  mov     qword ptr [rbp+0A0h+var_110], r13
0x18013b5e3  lea     rdx, [rbp+0A0h+var_110]
0x18013b5e7  mov     qword ptr [rsp+1A0h+var_180], rdx; int
0x18013b5ec  xor     r9d, r9d
0x18013b5ef  lea     r8d, [r9+17h]
0x18013b5f3  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x18013b5fa  mov     rax, [rax+18h]
0x18013b5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b603  mov     ebx, eax
0x18013b605  test    eax, eax
0x18013b607  jns     short loc_18013B629
0x18013b609  mov     rcx, [rbp+0A8h]; this
0x18013b610  mov     r9d, eax; char *
0x18013b613  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b61a  mov     edx, 18B3h; void *
0x18013b61f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b624  jmp     loc_18013C082
0x18013b629  mov     [rbp+0A0h+var_118], r13
0x18013b62d  mov     rcx, qword ptr [rbp+0A0h+var_110]
0x18013b631  mov     rax, [rcx]
0x18013b634  mov     [rbp+0A0h+var_118], r13
0x18013b638  lea     r8, [rbp+0A0h+var_118]
0x18013b63c  mov     edx, dword ptr [rbp+0A0h+pvar+8]
0x18013b63f  mov     rax, [rax+38h]
0x18013b643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b648  mov     ebx, eax
0x18013b64a  test    eax, eax
0x18013b64c  jns     short loc_18013B66E
0x18013b64e  mov     rcx, [rbp+0A8h]; this
0x18013b655  mov     r9d, eax; char *
0x18013b658  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b65f  mov     edx, 18B6h; void *
0x18013b664  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b669  jmp     loc_18013C078
0x18013b66e  mov     [rbp+0A0h+var_E0], r13
0x18013b672  mov     rcx, [rbp+0A0h+var_118]
0x18013b676  mov     rax, [rcx]
0x18013b679  mov     [rbp+0A0h+var_E0], r13
0x18013b67d  lea     r9, [rbp+0A0h+var_E0]
0x18013b681  lea     r8, _GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81
0x18013b688  mov     edx, esi
0x18013b68a  mov     rax, [rax+68h]
0x18013b68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b693  mov     ebx, eax
0x18013b695  test    eax, eax
0x18013b697  jns     short loc_18013B6C3
0x18013b699  mov     rcx, [rbp+0A8h]; this
0x18013b6a0  mov     r9d, eax; char *
0x18013b6a3  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b6aa  mov     edx, 18BBh; void *
0x18013b6af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b6b4  nop
0x18013b6b5  lea     rcx, [rbp+0A0h+var_E0]
0x18013b6b9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18013b6be  jmp     loc_18013C078
0x18013b6c3  mov     [rbp+0A0h+pv], r13
0x18013b6c7  mov     rcx, [rbp+0A0h+var_E0]
0x18013b6cb  mov     rax, [rcx]
0x18013b6ce  lea     rdx, [rbp+0A0h+pv]
0x18013b6d2  mov     [rbp+0A0h+var_70], rdx
0x18013b6d6  mov     [rbp+0A0h+var_70+8], r13
0x18013b6da  mov     byte ptr [rbp+0A0h+var_60], sil
0x18013b6de  lea     rdx, [rbp+0A0h+var_70+8]
0x18013b6e2  mov     rax, [rax+20h]
0x18013b6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b6eb  mov     ebx, eax
0x18013b6ed  lea     rcx, [rbp+0A0h+var_70]
0x18013b6f1  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18013b6f6  shr     ebx, 1Fh
0x18013b6f9  xor     bl, sil
0x18013b6fc  jz      loc_18013B97B
0x18013b702  movups  xmm0, xmmword ptr [r15]
0x18013b706  movaps  xmmword ptr [rbp+0A0h+var_70], xmm0
0x18013b70a  movups  xmm1, xmmword ptr [r15+10h]
0x18013b70f  movaps  [rbp+0A0h+var_60], xmm1
0x18013b713  mov     r9, [rbp+0A0h+var_108]
0x18013b717  mov     r8, [rbp+0A0h+pv]
0x18013b71b  lea     rdx, [rbp+0A0h+var_70]
0x18013b71f  call    CEndpointCharacteristics__CloneDriverFormatIfMatching__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x18013b724  mov     ebx, eax
0x18013b726  test    eax, eax
0x18013b728  jns     short loc_18013B762
0x18013b72a  mov     rcx, [rbp+0A8h]; this
0x18013b731  mov     r9d, eax; char *
0x18013b734  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18013b73b  mov     edx, 18C0h; void *
0x18013b740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b745  nop
0x18013b746  mov     rcx, [rbp+0A0h+pv]; pv
0x18013b74a  mov     [rbp+0A0h+pv], r13
0x18013b74e  test    rcx, rcx
0x18013b751  jz      loc_18013B6B5
0x18013b757  call    cs:__imp_CoTaskMemFree
0x18013b75d  jmp     loc_18013B6B5
0x18013b762  mov     rax, [rbp+0A0h+var_108]
0x18013b766  mov     r8, [rax]
0x18013b769  test    r8, r8
0x18013b76c  jz      loc_18013B97B
0x18013b772  movzx   eax, word ptr [r8]
0x18013b776  mov     ebx, 0FFFEh
0x18013b77b  cmp     ax, bx
0x18013b77e  jnz     loc_18013B85B
0x18013b784  mov     r9, [rdi+2060h]
0x18013b78b  mov     eax, [r9]
0x18013b78e  cmp     eax, r12d
0x18013b791  jbe     loc_18013B92D
0x18013b797  mov     edx, 10h
0x18013b79c  mov     rcx, r9
0x18013b79f  call    _tlgKeywordOn
0x18013b7a4  test    al, al
0x18013b7a6  jz      loc_18013B92D
0x18013b7ac  mov     eax, [r8+14h]
0x18013b7b0  mov     [rbp+0A0h+var_F8], eax
0x18013b7b3  lea     rax, [r8+18h]
0x18013b7b7  mov     [rsp+1A0h+var_128], rax
0x18013b7bc  mov     rdx, [rbp+0A0h+var_108]
0x18013b7c0  mov     rax, [rdx]
0x18013b7c3  mov     ecx, [rax+8]
0x18013b7c6  mov     [rsp+1A0h+var_138], ecx
0x18013b7ca  mov     rax, [rdx]
0x18013b7cd  mov     ecx, [rax+4]
0x18013b7d0  mov     [rsp+1A0h+var_134], ecx
0x18013b7d4  mov     rax, [rdx]
0x18013b7d7  movzx   ecx, word ptr [rax+2]
0x18013b7db  mov     [rsp+1A0h+var_140], cx
0x18013b7e0  lea     rax, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x18013b7e7  mov     [rsp+1A0h+var_130], rax
0x18013b7ec  mov     [rsp+1A0h+var_13C], r14d
0x18013b7f1  mov     rax, [rdi+30h]
0x18013b7f5  mov     [rbp+0A0h+var_F0], rax
0x18013b7f9  lea     rax, [rbp+0A0h+var_F8]
0x18013b7fd  mov     [rsp+1A0h+var_148], rax
0x18013b802  lea     rax, [rsp+1A0h+var_128]
0x18013b807  mov     [rsp+1A0h+var_150], rax
0x18013b80c  lea     rax, [rsp+1A0h+var_138]
0x18013b811  mov     [rsp+1A0h+var_158], rax
0x18013b816  lea     rax, [rsp+1A0h+var_134]
0x18013b81b  mov     [rsp+1A0h+var_160], rax
0x18013b820  lea     rax, [rsp+1A0h+var_140]
0x18013b825  mov     [rsp+1A0h+var_168], rax
0x18013b82a  lea     rax, [rsp+1A0h+var_130]
0x18013b82f  mov     [rsp+1A0h+var_170], rax
0x18013b834  lea     rax, [rsp+1A0h+var_13C]
0x18013b839  mov     [rsp+1A0h+var_178], rax
0x18013b83e  lea     rax, [rbp+0A0h+var_F0]
0x18013b842  mov     qword ptr [rsp+1A0h+var_180], rax
0x18013b847  lea     rdx, byte_1801AAC05
0x18013b84e  mov     rcx, r9
0x18013b851  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$01@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$01@@44AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18013b856  jmp     loc_18013B92D
0x18013b85b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data1
0x18013b862  movdqu  xmmword ptr [rbp+0A0h+var_50], xmm0
0x18013b867  mov     [rbp+0A0h+var_50], eax
0x18013b86a  mov     r8, [rdi+2060h]
0x18013b871  mov     eax, [r8]
0x18013b874  cmp     eax, r12d
0x18013b877  jbe     loc_18013B92D
0x18013b87d  mov     edx, 10h
0x18013b882  mov     rcx, r8
0x18013b885  call    _tlgKeywordOn
0x18013b88a  test    al, al
0x18013b88c  jz      loc_18013B92D
0x18013b892  lea     rax, [rbp+0A0h+var_50]
0x18013b896  mov     [rbp+0A0h+var_F0], rax
0x18013b89a  mov     rdx, [rbp+0A0h+var_108]
0x18013b89e  mov     rax, [rdx]
0x18013b8a1  mov     ecx, [rax+8]
0x18013b8a4  mov     [rsp+1A0h+var_13C], ecx
0x18013b8a8  mov     rax, [rdx]
0x18013b8ab  mov     ecx, [rax+4]
0x18013b8ae  mov     [rsp+1A0h+var_134], ecx
0x18013b8b2  mov     rax, [rdx]
0x18013b8b5  movzx   ecx, word ptr [rax+2]
0x18013b8b9  mov     [rsp+1A0h+var_140], cx
0x18013b8be  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x18013b8c5  mov     [rsp+1A0h+var_128], rax
0x18013b8ca  mov     [rsp+1A0h+var_138], r14d
0x18013b8cf  mov     rax, [rdi+30h]
0x18013b8d3  mov     [rsp+1A0h+var_130], rax
0x18013b8d8  lea     rax, [rbp+0A0h+var_F0]
0x18013b8dc  mov     [rsp+1A0h+var_150], rax
0x18013b8e1  lea     rax, [rsp+1A0h+var_13C]
0x18013b8e6  mov     [rsp+1A0h+var_158], rax
0x18013b8eb  lea     rax, [rsp+1A0h+var_134]
0x18013b8f0  mov     [rsp+1A0h+var_160], rax
0x18013b8f5  lea     rax, [rsp+1A0h+var_140]
0x18013b8fa  mov     [rsp+1A0h+var_168], rax
0x18013b8ff  lea     rax, [rsp+1A0h+var_128]
0x18013b904  mov     [rsp+1A0h+var_170], rax
0x18013b909  lea     rax, [rsp+1A0h+var_138]
0x18013b90e  mov     [rsp+1A0h+var_178], rax
0x18013b913  lea     rax, [rsp+1A0h+var_130]
0x18013b918  mov     qword ptr [rsp+1A0h+var_180], rax
0x18013b91d  lea     rdx, byte_1801AAAC7
0x18013b924  mov     rcx, r8
  ... truncated ...
```
