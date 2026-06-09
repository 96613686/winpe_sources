# ToastSession::RaiseToastClearedCallback(INotificationCollection *)

- ea: `0x180105340`
- end: `0x180105cf5`
- name: `?RaiseToastClearedCallback@ToastSession@@UEAAJPEAUINotificationCollection@@@Z`
- size: `2485`
- prototype: `__int64 __fastcall(ToastSession *__hidden this, struct INotificationCollection *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e090`
- `0x18000e5f4`
- `0x1800117c0`
- `0x180013360`
- `0x180014120`
- `0x18004187c`
- `0x18004b4c4`
- `0x180067d58`
- `0x180067de0`
- `0x18007162c`
- `0x180082624`
- `0x180085560`
- `0x180086414`
- `0x18008a97c`
- `0x1800b99f0`
- `0x1800ba574`
- `0x180104be0`
- `0x180105340`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801057b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801057b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801057a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801057a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010552a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010552a`
- `OLEAUT32!__imp_SysAllocString` at `0x180105850`
- `OLEAUT32!__imp_SysAllocString` at `0x180105866`
- `OLEAUT32!__imp_SysAllocString` at `0x18010593c`
- `OLEAUT32!__imp_SysAllocString` at `0x180105952`
- `OLEAUT32!__imp_SysAllocString` at `0x180105850`
- `OLEAUT32!__imp_SysAllocString` at `0x180105866`
- `OLEAUT32!__imp_SysAllocString` at `0x18010593c`
- `OLEAUT32!__imp_SysAllocString` at `0x180105952`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180105789`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180105789`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1801057c8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1801057c8`

## string_xrefs

- `0x1801058d3`: `AdaptiveJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ToastSession::RaiseToastClearedCallback(
        ToastSession *this,
        struct INotificationCollection *a2,
        __int64 a3)
{
  unsigned int v5; // r13d
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  unsigned int i; // r15d
  __int64 (__fastcall *v11)(struct INotificationCollection *, _QWORD, WpnDatabaseHelpers **); // rbx
  int v12; // eax
  WpnDatabaseHelpers *v13; // rdi
  __int64 (__fastcall *v14)(WpnDatabaseHelpers *, LPCWCH *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  const WCHAR *v17; // rcx
  int v18; // eax
  unsigned __int16 **v19; // r8
  int AppUserModelId; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  WpnDatabaseHelpers *v24; // rdi
  __int64 (__fastcall *v25)(WpnDatabaseHelpers *, OLECHAR **); // rbx
  int v26; // eax
  WpnDatabaseHelpers *v27; // rdi
  __int64 (__fastcall *v28)(WpnDatabaseHelpers *, OLECHAR **); // rbx
  int v29; // eax
  WpnDatabaseHelpers *v30; // rdi
  __int64 (__fastcall *v31)(WpnDatabaseHelpers *, IStream **); // rbx
  int v32; // eax
  HRESULT v33; // eax
  SIZE_T QuadPart; // rbx
  HANDLE ProcessHeap; // rax
  void *v36; // r14
  HRESULT v37; // eax
  WpnDatabaseHelpers *v38; // rdi
  __int64 (__fastcall *v39)(WpnDatabaseHelpers *, __int64 *); // rbx
  int v40; // eax
  __int64 v41; // rbx
  _QWORD *v42; // rax
  __int64 v43; // r9
  __int64 v44; // rdx
  int v45; // eax
  int v46; // eax
  __int64 v47; // r8
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  wil *v51; // rcx
  unsigned int v53; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-218h]
  WpnDatabaseHelpers *v55; // [rsp+30h] [rbp-208h] BYREF
  int v56; // [rsp+38h] [rbp-200h] BYREF
  int v57[2]; // [rsp+40h] [rbp-1F8h] BYREF
  __int64 v58; // [rsp+48h] [rbp-1F0h] BYREF
  unsigned int v59; // [rsp+50h] [rbp-1E8h] BYREF
  IStream *pstm; // [rsp+58h] [rbp-1E0h] BYREF
  ULARGE_INTEGER pui; // [rsp+60h] [rbp-1D8h] BYREF
  LPCWCH lpString1; // [rsp+68h] [rbp-1D0h] BYREF
  __int64 v63; // [rsp+70h] [rbp-1C8h]
  __int64 v64; // [rsp+78h] [rbp-1C0h]
  OLECHAR *v65; // [rsp+80h] [rbp-1B8h] BYREF
  __int64 v66; // [rsp+88h] [rbp-1B0h]
  __int64 v67; // [rsp+90h] [rbp-1A8h]
  OLECHAR *psz; // [rsp+98h] [rbp-1A0h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-198h]
  __int64 v70; // [rsp+A8h] [rbp-190h]
  __int64 v71; // [rsp+B0h] [rbp-188h] BYREF
  __int64 v72; // [rsp+B8h] [rbp-180h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-178h]
  __int64 v74; // [rsp+C8h] [rbp-170h]
  OLECHAR *v75; // [rsp+D0h] [rbp-168h] BYREF
  __int64 v76; // [rsp+D8h] [rbp-160h]
  __int64 v77; // [rsp+E0h] [rbp-158h]
  OLECHAR *v78; // [rsp+E8h] [rbp-150h] BYREF
  __int64 v79; // [rsp+F0h] [rbp-148h]
  __int64 v80; // [rsp+F8h] [rbp-140h]
  __int128 v81; // [rsp+100h] [rbp-138h] BYREF
  __int64 v82; // [rsp+110h] [rbp-128h]
  __int128 *v83; // [rsp+118h] [rbp-120h] BYREF
  char v84; // [rsp+120h] [rbp-118h]
  _QWORD v85[2]; // [rsp+130h] [rbp-108h] BYREF
  int v86; // [rsp+140h] [rbp-F8h]
  int v87; // [rsp+144h] [rbp-F4h]
  __int64 v88; // [rsp+148h] [rbp-F0h]
  __int64 v89; // [rsp+150h] [rbp-E8h]
  void *v90; // [rsp+158h] [rbp-E0h]
  DWORD LowPart; // [rsp+160h] [rbp-D8h]
  int v92; // [rsp+164h] [rbp-D4h]
  __int64 v93; // [rsp+168h] [rbp-D0h]
  GUID v94; // [rsp+170h] [rbp-C8h]
  BSTR v95; // [rsp+180h] [rbp-B8h]
  BSTR v96; // [rsp+188h] [rbp-B0h]
  __int64 v97; // [rsp+190h] [rbp-A8h]
  __int64 v98; // [rsp+198h] [rbp-A0h]
  _BYTE v99[64]; // [rsp+1A0h] [rbp-98h] BYREF
  _BYTE v100[32]; // [rsp+1E0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  try
  {
    v5 = 0;
    v81 = 0;
    v82 = 0;
    v71 = 0;
    v83 = &v81;
    v84 = 1;
    if ( !*((_QWORD *)this + 2) || !*((_DWORD *)this + 3) || !*((_QWORD *)this + 3) )
    {
      v53 = wil::verify_hresult<long>(2147500037LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2BE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)v53,
        bIgnoreCase);
    }
    if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x200000000000LL, a3) )
    {
      v58 = *((_QWORD *)this + 7);
      *(_QWORD *)v57 = *((_QWORD *)this + 4);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned int)&unk_18013AB08,
        v7,
        v8,
        (__int64)v57,
        (__int64)&v58);
    }
    v59 = 0;
    v9 = (*(__int64 (__fastcall **)(struct INotificationCollection *, unsigned int *))(*(_QWORD *)a2 + 32LL))(a2, &v59);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
    for ( i = 0; i < v59; ++i )
    {
      v55 = 0;
      v11 = *(__int64 (__fastcall **)(struct INotificationCollection *, _QWORD, WpnDatabaseHelpers **))(*(_QWORD *)a2 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
      v12 = v11(a2, i, &v55);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2D0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
      lpString1 = 0;
      v63 = 0;
      v64 = 0;
      v13 = v55;
      v14 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, LPCWCH *))(*(_QWORD *)v55 + 40LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
      v63 = -1;
      v64 = -1;
      v15 = v14(v13, &lpString1);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2D3,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v15,
          bIgnoreCase);
      LODWORD(v16) = v63;
      if ( v63 == -1 )
      {
        if ( lpString1 )
        {
          v16 = -1;
          do
            ++v16;
          while ( lpString1[v16] );
        }
        else
        {
          LODWORD(v16) = 0;
        }
      }
      v17 = &word_180124798;
      if ( lpString1 )
        v17 = lpString1;
      if ( CompareStringOrdinal(v17, v16, L"toast", -1, 0) == 2 )
      {
        v56 = 0;
        *(_QWORD *)v57 = 0;
        v58 = 0;
        psz = 0;
        v69 = 0;
        v70 = 0;
        v65 = 0;
        v66 = 0;
        v67 = 0;
        v78 = 0;
        v79 = 0;
        v80 = 0;
        v75 = 0;
        v76 = 0;
        v77 = 0;
        v18 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, int *))(*(_QWORD *)v55 + 24LL))(v55, &v56);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2DD,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v18,
            bIgnoreCase);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&psz);
        v69 = -1;
        v70 = -1;
        AppUserModelId = WpnDatabaseHelpers::GetAppUserModelId(v55, (struct IWpnNotification *)&psz, v19);
        if ( AppUserModelId < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2DE,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)AppUserModelId,
            bIgnoreCase);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v65);
        v66 = -1;
        v67 = -1;
        v21 = ToastSession::PopulatePFN((ToastSession *)((char *)this - 8), psz, &v65);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2DF,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v21,
            bIgnoreCase);
        v22 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, int *))(*(_QWORD *)v55 + 88LL))(v55, v57);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E0,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v22,
            bIgnoreCase);
        v23 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, __int64 *))(*(_QWORD *)v55 + 72LL))(v55, &v58);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E1,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v23,
            bIgnoreCase);
        v24 = v55;
        v25 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, OLECHAR **))(*(_QWORD *)v55 + 56LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
        v79 = -1;
        v80 = -1;
        v26 = v25(v24, &v78);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E2,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v26,
            bIgnoreCase);
        v27 = v55;
        v28 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, OLECHAR **))(*(_QWORD *)v55 + 64LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
        v76 = -1;
        v77 = -1;
        v29 = v28(v27, &v75);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E3,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v29,
            bIgnoreCase);
        pui.QuadPart = 0;
        pstm = 0;
        v30 = v55;
        v31 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, IStream **))(*(_QWORD *)v55 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
        v32 = v31(v30, &pstm);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E8,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v32,
            bIgnoreCase);
        v33 = IStream_Size(pstm, &pui);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E9,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v33,
            bIgnoreCase);
        QuadPart = pui.QuadPart;
        ProcessHeap = GetProcessHeap();
        v36 = HeapAlloc(ProcessHeap, 0, QuadPart);
        v37 = IStream_Read(pstm, v36, pui.LowPart);
        if ( v37 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2F0,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v37,
            bIgnoreCase);
        v72 = 0;
        v73 = 0;
        v74 = 0;
        v38 = v55;
        v39 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, __int64 *))(*(_QWORD *)v55 + 120LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v72);
        v73 = -1;
        v74 = -1;
        v40 = v39(v38, &v72);
        if ( v40 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2F3,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v40,
            bIgnoreCase);
        v85[0] = SysAllocString(psz);
        v85[1] = SysAllocString(v65);
        v86 = v56;
        v87 = 0;
        v88 = *(_QWORD *)v57;
        v89 = v58;
        v90 = v36;
        LowPart = pui.LowPart;
        v41 = v72;
        v42 = (_QWORD *)std::wstring::wstring(v100, L"AdaptiveJson");
        v43 = -1;
        do
          ++v43;
        while ( *(_WORD *)(v41 + 2 * v43) );
        v44 = v42[2];
        if ( v42[3] > 7u )
          v42 = (_QWORD *)*v42;
        v92 = (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v42, v44, v41, v43);
        v93 = 0;
        v94 = GUID_NULL;
        v95 = SysAllocString(v78);
        v96 = SysAllocString(v75);
        v97 = 0;
        v98 = 0;
        memset_0(v99, 0, sizeof(v99));
        std::vector<_WPN_TOAST_NOTIFICATION>::_Emplace_one_at_back<_WPN_TOAST_NOTIFICATION>(&v81, v85);
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v100);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v72);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v75);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v78);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v65);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&psz);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
    }
    v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 *))(**((_QWORD **)this + 3) + 40LL))(
            *((_QWORD *)this + 3),
            *((unsigned int *)this + 3),
            &GUID_904a654e_bee8_4654_bbba_e78766776239,
            &v71);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v45,
        bIgnoreCase);
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)&v65, 0x2710u);
    v46 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v71 + 40LL))(
            v71,
            *((unsigned int *)this + 2),
            v81,
            0x2E8BA2E8BA2E8BA3LL * ((__int64)(*((_QWORD *)&v81 + 1) - v81) >> 4));
    if ( v46 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x311,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v46,
        bIgnoreCase);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&v65);
    if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x200000000000LL, v47) )
    {
      v58 = *((_QWORD *)this + 7);
      *(_QWORD *)v57 = *((_QWORD *)this + 4);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v48,
        (unsigned int)byte_18013ABE1,
        v49,
        v50,
        (__int64)v57,
        (__int64)&v58);
    }
    v84 = 0;
    lambda_c2e0af7d8e6782135b121b13317cc1ae_::operator()(&v83);
    v51 = (wil *)v81;
    if ( (_QWORD)v81 )
      std::_Deallocate<16>((void *)v81, 16 * ((v82 - (__int64)v81) >> 4));
  }
  catch ( ... )
  {
    return (unsigned int)wil::ResultFromCaughtException(v51);
  }
  return v5;
}

```

## disassembly

```asm
0x180105340  mov     r11, rsp
0x180105343  mov     [r11+18h], rbx
0x180105347  mov     [r11+20h], rsi
0x18010534b  push    rdi
0x18010534c  push    r12
0x18010534e  push    r13
0x180105350  push    r14
0x180105352  push    r15
0x180105354  sub     rsp, 210h
0x18010535b  mov     rax, cs:__security_cookie
0x180105362  xor     rax, rsp
0x180105365  mov     [rsp+238h+var_38], rax
0x18010536d  mov     r12, rdx
0x180105370  mov     rsi, rcx
0x180105373  xor     r14d, r14d
0x180105376  mov     r13d, r14d
0x180105379  xorps   xmm0, xmm0
0x18010537c  movdqu  [rsp+238h+var_138], xmm0
0x180105385  mov     [r11-128h], r14
0x18010538c  mov     [r11-188h], r14
0x180105393  lea     rax, [r11-138h]
0x18010539a  mov     [r11-120h], rax
0x1801053a1  mov     [rsp+238h+var_118], 1
0x1801053a9  cmp     [rcx+10h], r14
0x1801053ad  jz      loc_180105CCD
0x1801053b3  cmp     [rcx+0Ch], r14d
0x1801053b7  jz      loc_180105CCD
0x1801053bd  cmp     [rcx+18h], r14
0x1801053c1  jz      loc_180105CCD
0x1801053c7  mov     eax, cs:dword_18015C038
0x1801053cd  cmp     eax, 5
0x1801053d0  jbe     short loc_18010541E
0x1801053d2  mov     rdx, 200000000000h
0x1801053dc  lea     rcx, dword_18015C038
0x1801053e3  call    _tlgKeywordOn
0x1801053e8  test    al, al
0x1801053ea  jz      short loc_18010541E
0x1801053ec  mov     rax, [rsi+38h]
0x1801053f0  mov     [rsp+238h+var_1F0], rax
0x1801053f5  mov     rax, [rsi+20h]
0x1801053f9  mov     qword ptr [rsp+238h+var_1F8], rax
0x1801053fe  lea     rax, [rsp+238h+var_1F0]
0x180105403  mov     [rsp+238h+var_210], rax
0x180105408  lea     rax, [rsp+238h+var_1F8]
0x18010540d  mov     qword ptr [rsp+238h+bIgnoreCase], rax; int
0x180105412  lea     rdx, unk_18013AB08
0x180105419  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18010541e  mov     [rsp+238h+var_1E8], r14d
0x180105423  mov     rax, [r12]
0x180105427  lea     rdx, [rsp+238h+var_1E8]
0x18010542c  mov     rcx, r12
0x18010542f  mov     rax, [rax+20h]
0x180105433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105438  mov     rcx, [rsp+238h]; this
0x180105440  test    eax, eax
0x180105442  js      loc_180105B85
0x180105448  mov     r15d, r14d
0x18010544b  cmp     r15d, [rsp+238h+var_1E8]
0x180105450  jnb     loc_180105A15
0x180105456  mov     [rsp+238h+var_208], r14
0x18010545b  mov     rax, [r12]
0x18010545f  mov     rbx, [rax+18h]
0x180105463  lea     rcx, [rsp+238h+var_208]
0x180105468  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18010546d  lea     r8, [rsp+238h+var_208]
0x180105472  mov     edx, r15d
0x180105475  mov     rcx, r12
0x180105478  mov     rax, rbx
0x18010547b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105480  mov     rcx, [rsp+238h]; this
0x180105488  test    eax, eax
0x18010548a  js      loc_180105B9A
0x180105490  mov     [rsp+238h+lpString1], r14
0x180105495  mov     [rsp+238h+var_1C8], r14
0x18010549a  mov     [rsp+238h+var_1C0], r14
0x18010549f  mov     rdi, [rsp+238h+var_208]
0x1801054a4  mov     rax, [rdi]
0x1801054a7  mov     rbx, [rax+28h]
0x1801054ab  lea     rcx, [rsp+238h+lpString1]
0x1801054b0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801054b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801054b9  mov     [rsp+238h+var_1C8], rax
0x1801054be  mov     [rsp+238h+var_1C0], rax
0x1801054c3  lea     rdx, [rsp+238h+lpString1]
0x1801054c8  mov     rcx, rdi
0x1801054cb  mov     rax, rbx
0x1801054ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801054d3  mov     rcx, [rsp+238h]; this
0x1801054db  test    eax, eax
0x1801054dd  js      loc_180105BAF
0x1801054e3  mov     rdx, [rsp+238h+var_1C8]
0x1801054e8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801054ec  mov     rax, [rsp+238h+lpString1]
0x1801054f1  cmp     rdx, rbx
0x1801054f4  jnz     short loc_18010550D
0x1801054f6  test    rax, rax
0x1801054f9  jz      short loc_18010550A
0x1801054fb  mov     rdx, rbx
0x1801054fe  inc     rdx
0x180105501  cmp     [rax+rdx*2], r14w
0x180105506  jnz     short loc_1801054FE
0x180105508  jmp     short loc_18010550D
0x18010550a  mov     rdx, r14; cchCount1
0x18010550d  lea     rcx, word_180124798
0x180105514  test    rax, rax
0x180105517  cmovnz  rcx, rax; lpString1
0x18010551b  mov     [rsp+238h+bIgnoreCase], r14d; int
0x180105520  mov     r9d, ebx; cchCount2
0x180105523  lea     r8, aToast_0; "toast"
0x18010552a  call    cs:__imp_CompareStringOrdinal
0x180105530  cmp     eax, 2
0x180105533  jnz     loc_1801059F8
0x180105539  mov     [rsp+238h+var_200], r14d
0x18010553e  mov     qword ptr [rsp+238h+var_1F8], r14
0x180105543  mov     [rsp+238h+var_1F0], r14
0x180105548  mov     [rsp+238h+psz], r14
0x180105550  mov     [rsp+238h+var_198], r14
0x180105558  mov     [rsp+238h+var_190], r14
0x180105560  mov     [rsp+238h+var_1B8], r14
0x180105568  mov     [rsp+238h+var_1B0], r14
0x180105570  mov     [rsp+238h+var_1A8], r14
0x180105578  mov     [rsp+238h+var_150], r14
0x180105580  mov     [rsp+238h+var_148], r14
0x180105588  mov     [rsp+238h+var_140], r14
0x180105590  mov     [rsp+238h+var_168], r14
0x180105598  mov     [rsp+238h+var_160], r14
0x1801055a0  mov     [rsp+238h+var_158], r14
0x1801055a8  mov     rcx, [rsp+238h+var_208]
0x1801055ad  mov     rax, [rcx]
0x1801055b0  lea     rdx, [rsp+238h+var_200]
0x1801055b5  mov     rax, [rax+18h]
0x1801055b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801055be  mov     rcx, [rsp+238h]; this
0x1801055c6  test    eax, eax
0x1801055c8  js      loc_180105BC4
0x1801055ce  lea     rcx, [rsp+238h+psz]
0x1801055d6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801055db  mov     [rsp+238h+var_198], rbx
0x1801055e3  mov     [rsp+238h+var_190], rbx
0x1801055eb  lea     rdx, [rsp+238h+psz]; struct IWpnNotification *
0x1801055f3  mov     rcx, [rsp+238h+var_208]; this
0x1801055f8  call    ?GetAppUserModelId@WpnDatabaseHelpers@@YAJPEAUIWpnNotification@@PEAPEAG@Z; WpnDatabaseHelpers::GetAppUserModelId(IWpnNotification *,ushort * *)
0x1801055fd  mov     rcx, [rsp+238h]; this
0x180105605  test    eax, eax
0x180105607  js      loc_180105BD8
0x18010560d  lea     rcx, [rsp+238h+var_1B8]
0x180105615  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18010561a  mov     [rsp+238h+var_1B0], rbx
0x180105622  mov     [rsp+238h+var_1A8], rbx
0x18010562a  lea     rcx, [rsi-8]; this
0x18010562e  lea     r8, [rsp+238h+var_1B8]; unsigned __int16 **
0x180105636  mov     rdx, [rsp+238h+psz]; unsigned __int16 *
0x18010563e  call    ?PopulatePFN@ToastSession@@AEAAJPEBGPEAPEAG@Z; ToastSession::PopulatePFN(ushort const *,ushort * *)
0x180105643  mov     rcx, [rsp+238h]; this
0x18010564b  test    eax, eax
0x18010564d  js      loc_180105BEC
0x180105653  mov     rcx, [rsp+238h+var_208]
0x180105658  mov     rax, [rcx]
0x18010565b  lea     rdx, [rsp+238h+var_1F8]
0x180105660  mov     rax, [rax+58h]
0x180105664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105669  mov     rcx, [rsp+238h]; this
0x180105671  test    eax, eax
0x180105673  js      loc_180105C00
0x180105679  mov     rcx, [rsp+238h+var_208]
0x18010567e  mov     rax, [rcx]
0x180105681  lea     rdx, [rsp+238h+var_1F0]
0x180105686  mov     rax, [rax+48h]
0x18010568a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010568f  mov     rcx, [rsp+238h]; this
0x180105697  test    eax, eax
0x180105699  js      loc_180105C14
0x18010569f  mov     rdi, [rsp+238h+var_208]
0x1801056a4  mov     rax, [rdi]
0x1801056a7  mov     rbx, [rax+38h]
0x1801056ab  lea     rcx, [rsp+238h+var_150]
0x1801056b3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801056b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801056bc  mov     [rsp+238h+var_148], rax
0x1801056c4  mov     [rsp+238h+var_140], rax
0x1801056cc  lea     rdx, [rsp+238h+var_150]
0x1801056d4  mov     rcx, rdi
0x1801056d7  mov     rax, rbx
0x1801056da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801056df  mov     rcx, [rsp+238h]; this
0x1801056e7  test    eax, eax
0x1801056e9  js      loc_180105C28
0x1801056ef  mov     rdi, [rsp+238h+var_208]
0x1801056f4  mov     rax, [rdi]
0x1801056f7  mov     rbx, [rax+40h]
0x1801056fb  lea     rcx, [rsp+238h+var_168]
0x180105703  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180105708  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010570c  mov     [rsp+238h+var_160], rax
0x180105714  mov     [rsp+238h+var_158], rax
0x18010571c  lea     rdx, [rsp+238h+var_168]
0x180105724  mov     rcx, rdi
0x180105727  mov     rax, rbx
0x18010572a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010572f  mov     rcx, [rsp+238h]; this
0x180105737  test    eax, eax
0x180105739  js      loc_180105C3C
0x18010573f  mov     qword ptr [rsp+238h+pui], r14
0x180105744  mov     [rsp+238h+pstm], r14
0x180105749  mov     rdi, [rsp+238h+var_208]
0x18010574e  mov     rax, [rdi]
0x180105751  mov     rbx, [rax+30h]
0x180105755  lea     rcx, [rsp+238h+pstm]
0x18010575a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18010575f  lea     rdx, [rsp+238h+pstm]
0x180105764  mov     rcx, rdi
0x180105767  mov     rax, rbx
0x18010576a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010576f  mov     rcx, [rsp+238h]; this
0x180105777  test    eax, eax
0x180105779  js      loc_180105C51
0x18010577f  lea     rdx, [rsp+238h+pui]; pui
0x180105784  mov     rcx, [rsp+238h+pstm]; pstm
0x180105789  call    cs:__imp_IStream_Size
0x18010578f  mov     rcx, [rsp+238h]; this
0x180105797  test    eax, eax
0x180105799  js      loc_180105C65
0x18010579f  mov     rbx, qword ptr [rsp+238h+pui]
0x1801057a4  call    cs:__imp_GetProcessHeap
0x1801057aa  mov     r8, rbx; dwBytes
0x1801057ad  xor     edx, edx; dwFlags
0x1801057af  mov     rcx, rax; hHeap
0x1801057b2  call    cs:__imp_HeapAlloc
0x1801057b8  mov     r14, rax
0x1801057bb  mov     r8d, dword ptr [rsp+238h+pui]; cb
0x1801057c0  mov     rdx, rax; pv
0x1801057c3  mov     rcx, [rsp+238h+pstm]; pstm
0x1801057c8  call    cs:__imp_IStream_Read
0x1801057ce  mov     rcx, [rsp+238h]; this
0x1801057d6  xor     edx, edx
0x1801057d8  test    eax, eax
0x1801057da  js      loc_180105C79
0x1801057e0  mov     [rsp+238h+var_180], rdx
0x1801057e8  mov     [rsp+238h+var_178], rdx
0x1801057f0  mov     [rsp+238h+var_170], rdx
0x1801057f8  mov     rdi, [rsp+238h+var_208]
0x1801057fd  mov     rax, [rdi]
0x180105800  mov     rbx, [rax+78h]
0x180105804  lea     rcx, [rsp+238h+var_180]
0x18010580c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180105811  or      rax, 0FFFFFFFFFFFFFFFFh
0x180105815  mov     [rsp+238h+var_178], rax
0x18010581d  mov     [rsp+238h+var_170], rax
0x180105825  lea     rdx, [rsp+238h+var_180]
0x18010582d  mov     rcx, rdi
0x180105830  mov     rax, rbx
0x180105833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105838  mov     rcx, [rsp+238h]; this
0x180105840  test    eax, eax
0x180105842  js      loc_180105C8E
0x180105848  mov     rcx, [rsp+238h+psz]; psz
0x180105850  call    cs:__imp_SysAllocString
0x180105856  mov     [rsp+238h+var_108], rax
0x18010585e  mov     rcx, [rsp+238h+var_1B8]; psz
0x180105866  call    cs:__imp_SysAllocString
0x18010586c  mov     [rsp+238h+var_100], rax
0x180105874  mov     eax, [rsp+238h+var_200]
0x180105878  mov     [rsp+238h+var_F8], eax
0x18010587f  mov     [rsp+238h+var_F4], 0
0x18010588a  mov     ecx, [rsp+238h+var_1F8+4]
0x18010588e  shl     rcx, 20h
0x180105892  mov     eax, [rsp+238h+var_1F8]
0x180105896  or      rcx, rax
0x180105899  mov     [rsp+238h+var_F0], rcx
0x1801058a1  mov     ecx, dword ptr [rsp+238h+var_1F0+4]
0x1801058a5  shl     rcx, 20h
0x1801058a9  mov     eax, dword ptr [rsp+238h+var_1F0]
0x1801058ad  or      rcx, rax
0x1801058b0  mov     [rsp+238h+var_E8], rcx
0x1801058b8  mov     [rsp+238h+var_E0], r14
0x1801058c0  mov     eax, dword ptr [rsp+238h+pui]
0x1801058c4  mov     [rsp+238h+var_D8], eax
0x1801058cb  mov     rbx, [rsp+238h+var_180]
0x1801058d3  lea     rdx, aAdaptivejson; "AdaptiveJson"
0x1801058da  lea     rcx, [rsp+238h+var_58]
0x1801058e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801058e7  nop
0x1801058e8  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801058ec  xor     r14d, r14d
0x1801058ef  inc     r9
0x1801058f2  cmp     [rbx+r9*2], r14w
0x1801058f7  jnz     short loc_1801058EF
0x1801058f9  mov     rdx, [rax+10h]
0x1801058fd  cmp     qword ptr [rax+18h], 7
0x180105902  jbe     short loc_180105907
0x180105904  mov     rax, [rax]
0x180105907  mov     r8, rbx
0x18010590a  mov     rcx, rax
0x18010590d  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180105912  movzx   eax, al
0x180105915  mov     [rsp+238h+var_D4], eax
0x18010591c  mov     [rsp+238h+var_D0], r14
0x180105924  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18010592b  movdqu  [rsp+238h+var_C8], xmm0
0x180105934  mov     rcx, [rsp+238h+var_150]; psz
  ... truncated ...
```
