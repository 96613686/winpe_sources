# AppInstallBroker::InstallAppsInBatchHelper(HSTRING__ *,HSTRING__ *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::EntitlementOptions,Windows::Foundation::Collections::IVector<ContentManagement::AppInstallInfoRecord *> *,ContentManagement::IAppManager *,Windows::Foundation::Collections::IVectorView<ContentManagement::AppInstallInfoRecord *> * *)

- ea: `0x180215884`
- end: `0x180215ec8`
- name: `?InstallAppsInBatchHelper@AppInstallBroker@@AEAAJPEAUHSTRING__@@0W4EntitlementOptions@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@PEAU?$IVector@PEAVAppInstallInfoRecord@ContentManagement@@@Collections@Foundation@Windows@@PEAUIAppManager@ContentManagement@@PEAPEAU?$IVectorView@PEAVAppInstallInfoRecord@ContentManagement@@@9Foundation@Windows@@@Z`
- size: `1604`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1802157a0`
- `0x180215ed0`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180035a98`
- `0x1800dab70`
- `0x1801e6adc`
- `0x180201e50`
- `0x18020e780`
- `0x18020ec08`
- `0x18020ecf0`
- `0x18020fcb0`
- `0x18021033c`
- `0x180215884`
- `0x1802168fc`
- `0x180218014`
- `0x180218444`
- `0x18021a0c0`
- `0x18021a120`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215a67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215c03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215c13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215ce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215cf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215a67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215c03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215c13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215ce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180215cf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802158e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802158e2`

## string_xrefs

- `0x18021594b`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x18021598c`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x1802159d3`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180215c45`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180215c7f`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180215cb7`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180215d69`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180215df0`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x1802158eb`: `InstallAppsInBatch`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppInstallBroker::InstallAppsInBatchHelper(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  int v7; // r12d
  const unsigned __int16 *StringRawBuffer; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  int v21; // esi
  int v22; // r15d
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING *); // rbx
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // edi
  __int64 v31; // rdx
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdx
  __int64 (__fastcall *v35)(__int64, __int64, __int64 *); // rbx
  int v36; // eax
  __int64 v37; // rdx
  unsigned __int64 v38; // r9
  int v39; // r14d
  __int64 v40; // rdi
  unsigned int i; // ebx
  int v42; // eax
  unsigned int v43; // esi
  int v45; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v47; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h] BYREF
  int v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  int v54; // [rsp+80h] [rbp-80h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h] BYREF
  int v56; // [rsp+90h] [rbp-70h] BYREF
  int *v57; // [rsp+98h] [rbp-68h]
  int v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h] BYREF
  int v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v62; // [rsp+C0h] [rbp-40h]
  _QWORD *v63; // [rsp+C8h] [rbp-38h]
  _BYTE v64[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v65; // [rsp+D8h] [rbp-28h]
  _BYTE v66[16]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v67[42]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v60 = a4;
  v61 = a3;
  v7 = (int)a2;
  v63 = a7;
  *a7 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  wil::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v67);
  v67[0] = &AppInstallationTelemetry::InstallAppsInBatch::`vftable';
  AppInstallationTelemetry::InstallAppsInBatch::StartActivity(
    (AppInstallationTelemetry::InstallAppsInBatch *)v67,
    StringRawBuffer);
  v54 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a5 + 56LL))(a5, &v54);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( !v54 )
    {
      v11 = -2147418113;
      v12 = 2147549183LL;
      v13 = 488;
      goto LABEL_5;
    }
    v49 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<ContentManagement::AppInstallInfoRecord,Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>>(
            v14,
            &v49);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)(unsigned int)v15,
        v45);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      goto LABEL_56;
    }
    v50 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    v17 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<ContentManagement::AppInstallInfoRecord,Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>>(
            v16,
            &v50);
    v11 = v17;
    if ( v17 < 0 )
    {
      v18 = (unsigned int)v17;
      v19 = 494;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)v18,
        v45);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      goto LABEL_8;
    }
    v52 = 0;
    v55 = a5;
    v57 = &v52;
    v58 = 0;
    v59 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a5 + 56LL))(a5, &v56);
    *v57 = v20;
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(
      &v55,
      0);
    v21 = 0;
    v22 = v56;
    while ( *v57 >= 0 && v21 != v22 )
    {
      v48 = 0;
      string = 0;
      v47 = 0;
      v23 = v59;
      v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v59 + 48LL);
      WindowsDeleteString(0);
      v48 = 0;
      v25 = v24(v23, &v48);
      v11 = v25;
      if ( v25 < 0 )
      {
        v31 = 506;
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
          (const char *)(unsigned int)v25,
          v45);
LABEL_37:
        WindowsDeleteString(v47);
        goto LABEL_38;
      }
      v26 = v59;
      v27 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v59 + 64LL);
      WindowsDeleteString(string);
      string = 0;
      v25 = v27(v26, &string);
      v11 = v25;
      if ( v25 < 0 )
      {
        v31 = 507;
        goto LABEL_36;
      }
      v28 = v59;
      v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v59 + 80LL);
      WindowsDeleteString(v47);
      v47 = 0;
      v25 = v29(v28, &v47);
      v11 = v25;
      if ( v25 < 0 )
      {
        v31 = 508;
        goto LABEL_36;
      }
      v45 = v7;
      v30 = AppInstallBroker::PerformAppInstallPrecheck(a1, v48, string, v47);
      if ( v30 < 0 )
      {
        v51 = 0;
        v32 = Microsoft::WRL::Details::MakeAndInitialize<ContentManagement::AppInstallInfoRecordImpl,ContentManagement::AppInstallInfoRecordImpl,>(&v51);
        v11 = v32;
        if ( v32 < 0 )
        {
          v34 = 518;
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v34,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
            (const char *)(unsigned int)v32,
            v7);
          Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(&v51);
          WindowsDeleteString(v47);
LABEL_38:
          v47 = 0;
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v48);
          v48 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
          goto LABEL_12;
        }
        v32 = ContentManagement::AppInstallInfoRecordImpl::put_ProductId(
                (ContentManagement::AppInstallInfoRecordImpl *)(v51 + 48),
                v48);
        v11 = v32;
        if ( v32 < 0 )
        {
          v34 = 520;
          goto LABEL_32;
        }
        v32 = ContentManagement::AppInstallInfoRecordImpl::put_SkuId(
                (ContentManagement::AppInstallInfoRecordImpl *)(v51 + 48),
                string);
        v11 = v32;
        if ( v32 < 0 )
        {
          v34 = 521;
          goto LABEL_32;
        }
        *(_DWORD *)(v51 + 104) = v30;
        v33 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 104LL))(
                v49,
                (v51 + 48) & -(__int64)(v51 != 0));
        v11 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
            (const char *)(unsigned int)v33,
            v7);
          Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(&v51);
          goto LABEL_37;
        }
        Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(&v51);
      }
      else
      {
        v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 104LL))(v50, v59);
        v11 = v25;
        if ( v25 < 0 )
        {
          v31 = 513;
          goto LABEL_36;
        }
      }
      WindowsDeleteString(v47);
      v47 = 0;
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v48);
      wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(
        &v55,
        (unsigned int)++v21);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    v11 = v52;
    if ( v52 < 0 )
    {
      v18 = (unsigned int)v52;
      v19 = 527;
      goto LABEL_11;
    }
    v53 = 0;
    v35 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a6 + 96LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    v36 = v35(a6, v50, &v53);
    v11 = v36;
    if ( v36 >= 0 )
    {
      wil::GetRangeNoThrow<ContentManagement::AppInstallInfoRecord *>(v64, v53, &v52);
      wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::TileVerb *>>::begin(
        v64,
        &v61);
      v39 = v65;
      v40 = v61;
      for ( i = v62;
            **(int **)(v40 + 16) >= 0 && i != v39;
            wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(
              v40,
              i) )
      {
        v42 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 104LL))(v49, *(_QWORD *)(v40 + 32));
        v43 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x216,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
            (const char *)(unsigned int)v42,
            v45);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v66);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
          v11 = v43;
          goto LABEL_56;
        }
        ++i;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v66);
      v11 = v52;
      if ( v52 < 0 )
      {
        v38 = (unsigned int)v52;
        v37 = 536;
        goto LABEL_44;
      }
      v36 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v49 + 64LL))(v49, v63);
      v11 = v36;
      if ( v36 >= 0 )
      {
        wil::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v67,
          0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        v11 = 0;
        goto LABEL_56;
      }
      v37 = 538;
    }
    else
    {
      v37 = 530;
    }
    v38 = (unsigned int)v36;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
      (const char *)v38,
      v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    goto LABEL_12;
  }
  v12 = (unsigned int)v10;
  v13 = 487;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
    (const char *)v12,
    v45);
LABEL_56:
  AppInstallationTelemetry::InstallAppsInBatch::~InstallAppsInBatch((AppInstallationTelemetry::InstallAppsInBatch *)v67);
  return v11;
}

```

## disassembly

```asm
0x180215884  push    rbp
0x180215886  push    rbx
0x180215887  push    rsi
0x180215888  push    rdi
0x180215889  push    r12
0x18021588b  push    r13
0x18021588d  push    r14
0x18021588f  push    r15
0x180215891  lea     rbp, [rsp-168h]
0x180215899  sub     rsp, 268h
0x1802158a0  mov     rax, cs:__security_cookie
0x1802158a7  xor     rax, rsp
0x1802158aa  mov     [rbp+1A0h+var_50], rax
0x1802158b1  mov     [rbp+1A0h+var_1F0], r9d
0x1802158b5  mov     [rbp+1A0h+var_1E8], r8
0x1802158b9  mov     r12, rdx
0x1802158bc  mov     r13, rcx
0x1802158bf  mov     rdi, [rbp+1A0h+arg_20]
0x1802158c6  mov     r14, [rbp+1A0h+arg_28]
0x1802158cd  mov     rax, [rbp+1A0h+arg_30]
0x1802158d4  mov     [rbp+1A0h+var_1D8], rax
0x1802158d8  xor     esi, esi
0x1802158da  mov     [rax], rsi
0x1802158dd  xor     edx, edx; length
0x1802158df  mov     rcx, r12; string
0x1802158e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1802158e8  mov     rbx, rax
0x1802158eb  lea     rdx, aInstallappsinb; "InstallAppsInBatch"
0x1802158f2  lea     rcx, [rbp+1A0h+var_1A0]; struct wil::details::IFailureCallback *
0x1802158f6  call    ??0?$ActivityBase@VShellAppInstallationTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1802158fb  lea     rax, ??_7InstallAppsInBatch@AppInstallationTelemetry@@6B@; const AppInstallationTelemetry::InstallAppsInBatch::`vftable'
0x180215902  mov     [rbp+1A0h+var_1A0], rax
0x180215906  mov     rdx, rbx; unsigned __int16 *
0x180215909  lea     rcx, [rbp+1A0h+var_1A0]; this
0x18021590d  call    ?StartActivity@InstallAppsInBatch@AppInstallationTelemetry@@QEAAXPEBG@Z; AppInstallationTelemetry::InstallAppsInBatch::StartActivity(ushort const *)
0x180215912  nop
0x180215913  mov     [rbp+1A0h+var_220], esi
0x180215916  mov     rax, [rdi]
0x180215919  lea     rdx, [rbp+1A0h+var_220]
0x18021591d  mov     rcx, rdi
0x180215920  mov     rax, [rax+38h]
0x180215924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215929  mov     ebx, eax
0x18021592b  test    eax, eax
0x18021592d  jns     short loc_180215939
0x18021592f  mov     r9d, eax
0x180215932  mov     edx, 1E7h
0x180215937  jmp     short loc_18021594B
0x180215939  cmp     [rbp+1A0h+var_220], esi
0x18021593c  jnz     short loc_180215963
0x18021593e  mov     ebx, 8000FFFFh
0x180215943  mov     r9d, ebx; char *
0x180215946  mov     edx, 1E8h; void *
0x18021594b  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180215952  mov     rcx, [rbp+1A8h]; this
0x180215959  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021595e  jmp     loc_180215E9A
0x180215963  mov     [rsp+2A0h+var_248], rsi
0x180215968  lea     rcx, [rsp+2A0h+var_248]
0x18021596d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180215972  lea     rdx, [rsp+2A0h+var_248]
0x180215977  call    ??$CreateExternalObjectVector@VAppInstallInfoRecord@ContentManagement@@V?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<ContentManagement::AppInstallInfoRecord,Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0> * *)
0x18021597c  mov     ebx, eax
0x18021597e  test    eax, eax
0x180215980  jns     short loc_1802159AC
0x180215982  mov     rcx, [rbp+1A8h]; this
0x180215989  mov     r9d, eax; char *
0x18021598c  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180215993  mov     edx, 1EBh; void *
0x180215998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021599d  lea     rcx, [rsp+2A0h+var_248]
0x1802159a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802159a7  jmp     loc_180215E9A
0x1802159ac  mov     [rsp+2A0h+var_240], rsi
0x1802159b1  lea     rcx, [rsp+2A0h+var_240]
0x1802159b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802159bb  lea     rdx, [rsp+2A0h+var_240]
0x1802159c0  call    ??$CreateExternalObjectVector@VAppInstallInfoRecord@ContentManagement@@V?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<ContentManagement::AppInstallInfoRecord,Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0> * *)
0x1802159c5  mov     ebx, eax
0x1802159c7  test    eax, eax
0x1802159c9  jns     short loc_1802159F2
0x1802159cb  mov     r9d, eax; char *
0x1802159ce  mov     edx, 1EEh; void *
0x1802159d3  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1802159da  mov     rcx, [rbp+1A8h]; this
0x1802159e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802159e6  lea     rcx, [rsp+2A0h+var_240]
0x1802159eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802159f0  jmp     short loc_18021599D
0x1802159f2  mov     [rsp+2A0h+var_230], esi
0x1802159f6  mov     [rbp+1A0h+var_218], rdi
0x1802159fa  lea     rax, [rsp+2A0h+var_230]
0x1802159ff  mov     [rbp+1A0h+var_208], rax
0x180215a03  mov     [rbp+1A0h+var_200], esi
0x180215a06  mov     [rbp+1A0h+var_1F8], rsi
0x180215a0a  mov     rax, [rdi]
0x180215a0d  lea     rdx, [rbp+1A0h+var_210]
0x180215a11  mov     rcx, rdi
0x180215a14  mov     rax, [rax+38h]
0x180215a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215a1d  mov     rcx, [rbp+1A0h+var_208]
0x180215a21  mov     [rcx], eax
0x180215a23  xor     edx, edx
0x180215a25  lea     rcx, [rbp+1A0h+var_218]
0x180215a29  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVStoreAvailability@Store@Services@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(uint)
0x180215a2e  xor     edi, edi
0x180215a30  mov     esi, edi
0x180215a32  mov     r15d, [rbp+1A0h+var_210]
0x180215a36  mov     rax, [rbp+1A0h+var_208]
0x180215a3a  cmp     [rax], edi
0x180215a3c  jl      loc_180215D0B
0x180215a42  cmp     esi, r15d
0x180215a45  jz      loc_180215D0B
0x180215a4b  mov     [rsp+2A0h+var_250], rdi
0x180215a50  mov     [rsp+2A0h+string], rdi
0x180215a55  mov     [rsp+2A0h+var_258], rdi
0x180215a5a  mov     rdi, [rbp+1A0h+var_1F8]
0x180215a5e  mov     rax, [rdi]
0x180215a61  mov     rbx, [rax+30h]
0x180215a65  xor     ecx, ecx; string
0x180215a67  call    cs:__imp_WindowsDeleteString
0x180215a6d  mov     [rsp+2A0h+var_250], 0
0x180215a76  lea     rdx, [rsp+2A0h+var_250]
0x180215a7b  mov     rcx, rdi
0x180215a7e  mov     rax, rbx
0x180215a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215a86  mov     ebx, eax
0x180215a88  xor     edi, edi
0x180215a8a  test    eax, eax
0x180215a8c  js      loc_180215CB2
0x180215a92  mov     rdi, [rbp+1A0h+var_1F8]
0x180215a96  mov     rax, [rdi]
0x180215a99  mov     rbx, [rax+40h]
0x180215a9d  mov     rcx, [rsp+2A0h+string]; string
0x180215aa2  call    cs:__imp_WindowsDeleteString
0x180215aa8  mov     [rsp+2A0h+string], 0
0x180215ab1  lea     rdx, [rsp+2A0h+string]
0x180215ab6  mov     rcx, rdi
0x180215ab9  mov     rax, rbx
0x180215abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215ac1  mov     ebx, eax
0x180215ac3  xor     edi, edi
0x180215ac5  test    eax, eax
0x180215ac7  js      loc_180215CAB
0x180215acd  mov     rdi, [rbp+1A0h+var_1F8]
0x180215ad1  mov     rax, [rdi]
0x180215ad4  mov     rbx, [rax+50h]
0x180215ad8  mov     rcx, [rsp+2A0h+var_258]; string
0x180215add  call    cs:__imp_WindowsDeleteString
0x180215ae3  mov     [rsp+2A0h+var_258], 0
0x180215aec  lea     rdx, [rsp+2A0h+var_258]
0x180215af1  mov     rcx, rdi
0x180215af4  mov     rax, rbx
0x180215af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215afc  mov     ebx, eax
0x180215afe  xor     edi, edi
0x180215b00  test    eax, eax
0x180215b02  js      loc_180215CA4
0x180215b08  mov     [rsp+2A0h+var_268], r14
0x180215b0d  mov     eax, [rbp+1A0h+var_1F0]
0x180215b10  mov     [rsp+2A0h+var_270], eax
0x180215b14  mov     rax, [rbp+1A0h+var_1E8]
0x180215b18  mov     [rsp+2A0h+var_278], rax
0x180215b1d  mov     qword ptr [rsp+2A0h+var_280], r12; int
0x180215b22  mov     r9, [rsp+2A0h+var_258]
0x180215b27  mov     r8, [rsp+2A0h+string]
0x180215b2c  mov     rdx, [rsp+2A0h+var_250]
0x180215b31  mov     rcx, r13
0x180215b34  call    ?PerformAppInstallPrecheck@AppInstallBroker@@AEAAJPEAUHSTRING__@@0000W4EntitlementOptions@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@PEAUIAppManager@ContentManagement@@@Z; AppInstallBroker::PerformAppInstallPrecheck(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::EntitlementOptions,ContentManagement::IAppManager *)
0x180215b39  mov     edi, eax
0x180215b3b  test    eax, eax
0x180215b3d  js      short loc_180215B6A
0x180215b3f  mov     rcx, [rsp+2A0h+var_240]
0x180215b44  mov     rax, [rcx]
0x180215b47  mov     rdx, [rbp+1A0h+var_1F8]
0x180215b4b  mov     rax, [rax+68h]
0x180215b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215b54  mov     ebx, eax
0x180215b56  xor     edi, edi
0x180215b58  test    eax, eax
0x180215b5a  jns     loc_180215BFE
0x180215b60  mov     edx, 201h
0x180215b65  jmp     loc_180215CB7
0x180215b6a  mov     [rsp+2A0h+var_238], 0
0x180215b73  lea     rcx, [rsp+2A0h+var_238]
0x180215b78  call    ??$MakeAndInitialize@VAppInstallInfoRecordImpl@ContentManagement@@V12@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppInstallInfoRecordImpl@ContentManagement@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<ContentManagement::AppInstallInfoRecordImpl,ContentManagement::AppInstallInfoRecordImpl,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>>)
0x180215b7d  mov     ebx, eax
0x180215b7f  test    eax, eax
0x180215b81  js      loc_180215C70
0x180215b87  mov     rcx, [rsp+2A0h+var_238]
0x180215b8c  add     rcx, 30h ; '0'; this
0x180215b90  mov     rdx, [rsp+2A0h+var_250]; HSTRING
0x180215b95  call    ?put_ProductId@AppInstallInfoRecordImpl@ContentManagement@@UEAAJPEAUHSTRING__@@@Z; ContentManagement::AppInstallInfoRecordImpl::put_ProductId(HSTRING__ *)
0x180215b9a  mov     ebx, eax
0x180215b9c  test    eax, eax
0x180215b9e  js      loc_180215C69
0x180215ba4  mov     rcx, [rsp+2A0h+var_238]
0x180215ba9  add     rcx, 30h ; '0'; this
0x180215bad  mov     rdx, [rsp+2A0h+string]; HSTRING
0x180215bb2  call    ?put_SkuId@AppInstallInfoRecordImpl@ContentManagement@@UEAAJPEAUHSTRING__@@@Z; ContentManagement::AppInstallInfoRecordImpl::put_SkuId(HSTRING__ *)
0x180215bb7  mov     ebx, eax
0x180215bb9  test    eax, eax
0x180215bbb  js      loc_180215C62
0x180215bc1  mov     rax, [rsp+2A0h+var_238]
0x180215bc6  mov     [rax+68h], edi
0x180215bc9  mov     rcx, [rsp+2A0h+var_248]
0x180215bce  mov     rdx, [rsp+2A0h+var_238]
0x180215bd3  mov     r8, [rcx]
0x180215bd6  lea     rax, [rdx+30h]
0x180215bda  neg     rdx
0x180215bdd  sbb     rdx, rdx
0x180215be0  and     rdx, rax
0x180215be3  mov     rax, [r8+68h]
0x180215be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215bec  mov     ebx, eax
0x180215bee  xor     edi, edi
0x180215bf0  test    eax, eax
0x180215bf2  js      short loc_180215C3B
0x180215bf4  lea     rcx, [rsp+2A0h+var_238]
0x180215bf9  call    ?InternalRelease@?$ComPtr@VAppInstallInfoRecordImpl@ContentManagement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(void)
0x180215bfe  mov     rcx, [rsp+2A0h+var_258]; string
0x180215c03  call    cs:__imp_WindowsDeleteString
0x180215c09  mov     [rsp+2A0h+var_258], rdi
0x180215c0e  mov     rcx, [rsp+2A0h+string]; string
0x180215c13  call    cs:__imp_WindowsDeleteString
0x180215c19  mov     [rsp+2A0h+string], rdi
0x180215c1e  mov     rcx, [rsp+2A0h+var_250]; string
0x180215c23  call    cs:__imp_WindowsDeleteString
0x180215c29  inc     esi
0x180215c2b  mov     edx, esi
0x180215c2d  lea     rcx, [rbp+1A0h+var_218]
0x180215c31  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVStoreAvailability@Store@Services@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(uint)
0x180215c36  jmp     loc_180215A36
0x180215c3b  mov     rcx, [rbp+1A8h]; this
0x180215c42  mov     r9d, eax; char *
0x180215c45  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180215c4c  mov     edx, 20Ch; void *
0x180215c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180215c56  lea     rcx, [rsp+2A0h+var_238]
0x180215c5b  call    ?InternalRelease@?$ComPtr@VAppInstallInfoRecordImpl@ContentManagement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(void)
0x180215c60  jmp     short loc_180215CCD
0x180215c62  mov     edx, 209h
0x180215c67  jmp     short loc_180215C75
0x180215c69  mov     edx, 208h
0x180215c6e  jmp     short loc_180215C75
0x180215c70  mov     edx, 206h; void *
0x180215c75  mov     rcx, [rbp+1A8h]; this
0x180215c7c  mov     r9d, eax; char *
0x180215c7f  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180215c86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180215c8b  lea     rcx, [rsp+2A0h+var_238]
0x180215c90  call    ?InternalRelease@?$ComPtr@VAppInstallInfoRecordImpl@ContentManagement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(void)
0x180215c95  mov     rcx, [rsp+2A0h+var_258]; string
0x180215c9a  call    cs:__imp_WindowsDeleteString
0x180215ca0  xor     edi, edi
0x180215ca2  jmp     short loc_180215CD8
0x180215ca4  mov     edx, 1FCh
0x180215ca9  jmp     short loc_180215CB7
0x180215cab  mov     edx, 1FBh
0x180215cb0  jmp     short loc_180215CB7
0x180215cb2  mov     edx, 1FAh; void *
0x180215cb7  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180215cbe  mov     r9d, eax; char *
0x180215cc1  mov     rcx, [rbp+1A8h]; this
0x180215cc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180215ccd  mov     rcx, [rsp+2A0h+var_258]; string
0x180215cd2  call    cs:__imp_WindowsDeleteString
0x180215cd8  mov     [rsp+2A0h+var_258], rdi
0x180215cdd  mov     rcx, [rsp+2A0h+string]; string
0x180215ce2  call    cs:__imp_WindowsDeleteString
0x180215ce8  mov     [rsp+2A0h+string], rdi
0x180215ced  mov     rcx, [rsp+2A0h+var_250]; string
0x180215cf2  call    cs:__imp_WindowsDeleteString
0x180215cf8  mov     [rsp+2A0h+var_250], rdi
0x180215cfd  lea     rcx, [rbp+1A0h+var_1F8]
0x180215d01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180215d06  jmp     loc_1802159E6
0x180215d0b  lea     rcx, [rbp+1A0h+var_1F8]
0x180215d0f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180215d14  mov     ebx, [rsp+2A0h+var_230]
0x180215d18  test    ebx, ebx
0x180215d1a  jns     short loc_180215D29
0x180215d1c  mov     r9d, ebx
0x180215d1f  mov     edx, 20Fh
0x180215d24  jmp     loc_1802159D3
0x180215d29  mov     [rsp+2A0h+var_228], rdi
0x180215d2e  mov     rax, [r14]
0x180215d31  mov     rbx, [rax+60h]
0x180215d35  lea     rcx, [rsp+2A0h+var_228]
0x180215d3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180215d3f  lea     r8, [rsp+2A0h+var_228]
0x180215d44  mov     rdx, [rsp+2A0h+var_240]
0x180215d49  mov     rcx, r14
0x180215d4c  mov     rax, rbx
0x180215d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215d54  mov     ebx, eax
0x180215d56  test    eax, eax
0x180215d58  jns     short loc_180215D84
0x180215d5a  mov     edx, 212h; void *
0x180215d5f  mov     r9d, eax; char *
  ... truncated ...
```
