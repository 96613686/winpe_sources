# DataStoreCache::DelayedInitializationTasks::RefreshEdpStatusOnItem__lambda_914e5f955b5722866492a2041cef4175___

- ea: `0x180161928`
- end: `0x180161e4a`
- name: `DataStoreCache::DelayedInitializationTasks::RefreshEdpStatusOnItem__lambda_914e5f955b5722866492a2041cef4175___`
- size: `1314`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c6484`

## callees

- `0x18000ce94`
- `0x18001dac0`
- `0x180021dd8`
- `0x180022020`
- `0x18003b500`
- `0x18003d71c`
- `0x180045678`
- `0x18004a468`
- `0x1800c402c`
- `0x1800d8e48`
- `0x180122678`
- `0x180161204`
- `0x180161928`
- `0x180201e50`
- `0x1803489c0`
- `0x1803494b4`
- `0x180349d98`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801619fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161cf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161d74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801619fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161cf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161d74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161de8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180161b27`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180161b27`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180161b13`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180161b13`

## string_xrefs

- `0x1801619e6`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161a2b`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161b3b`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161b94`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161bbf`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161c8f`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161cd1`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161d1f`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161d5d`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`
- `0x180161e38`: `shellcommon\shell\datastorecache\transformers\edptransformer\lib\DelayedInitializationTasks.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall DataStoreCache::DelayedInitializationTasks::RefreshEdpStatusOnItem__lambda_914e5f955b5722866492a2041cef4175___(
        __int64 a1,
        _QWORD *a2,
        char a3,
        DataStoreCache::EdpTransformer **a4)
{
  WindowsInternal::Shell::UnifiedTile **v8; // rax
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **v9; // r8
  int Instance; // eax
  int v11; // eax
  __int64 v12; // rdi
  unsigned __int8 (__fastcall *v13)(__int64, const struct _GUID *, GUID *, __int64); // rbx
  __int64 v14; // rax
  bool v15; // r14
  const WCHAR *v16; // rdi
  const WCHAR *v17; // rbx
  const WCHAR *FileNameW; // rax
  HRESULT v19; // eax
  __int64 (__fastcall *v20)(__int64, _QWORD, _BYTE *, char *); // rbx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rdi
  unsigned __int8 (__fastcall *v24)(__int64, const struct _GUID *, GUID *, __int64); // rbx
  __int64 v25; // rax
  __int64 v26; // rdi
  unsigned __int8 (__fastcall *v27)(__int64, void *, PWSTR *); // rbx
  PWSTR v28; // rcx
  int v29; // eax
  int v30; // eax
  PCWSTR v31; // rdi
  __int64 (__fastcall *v32)(PCWSTR, PWSTR *); // rbx
  int v33; // eax
  int v34; // eax
  bool v35; // bl
  const struct DataStoreCache::DataItemIdentifier *v36; // rax
  int v37; // [rsp+20h] [rbp-E0h]
  char v38; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v39[7]; // [rsp+31h] [rbp-CFh] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR pszPathIn; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING__ v44[2]; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v46; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v47[32]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v48[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v48,
    "RefreshEdpStatusOnTile");
  v48[0] = &DataStoreTransformerTelemetry::RefreshEdpStatusOnTile::`vftable';
  DataStoreTransformerTelemetry::RefreshEdpStatusOnTile::StartActivity((DataStoreTransformerTelemetry::RefreshEdpStatusOnTile *)v48);
  v39[0] = 0;
  v38 = 0;
  if ( !a3 || !a1 )
    goto LABEL_38;
  *(_QWORD *)&v44[0].unused = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
  v8 = (WindowsInternal::Shell::UnifiedTile **)(*(__int64 (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a2 + 32LL))(
                                                 *a2,
                                                 &string);
  Instance = WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifier_CreateInstance(*v8, v44, v9);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
      (const char *)(unsigned int)Instance,
      v37);
  WindowsDeleteString(string);
  v43 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)&v44[0].unused + 48LL))(*(_QWORD *)&v44[0].unused, &v43);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
      (const char *)(unsigned int)v11,
      v37);
  if ( v43 == 2 )
  {
    v41 = 0;
    v12 = *a2;
    v13 = *(unsigned __int8 (__fastcall **)(__int64, const struct _GUID *, GUID *, __int64))(*(_QWORD *)*a2 + 48LL);
    v14 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(&v41);
    v15 = 1;
    if ( v13(v12, &c_appResolverTransformerId, &GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb, v14) )
    {
      pszPathIn = 0;
      string = 0;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, _GUID **, PCWSTR *))(*(_QWORD *)v41 + 32LL))(
             v41,
             &DataStoreCache::AppResolverProperties::AppInstallDirectory,
             &pszPathIn) )
      {
        if ( pszPathIn )
        {
          if ( (*(unsigned __int8 (__fastcall **)(__int64, _GUID **, HSTRING *))(*(_QWORD *)v41 + 32LL))(
                 v41,
                 &DataStoreCache::AppResolverProperties::AppPathEncoded,
                 &string) )
          {
            v16 = (const WCHAR *)string;
            if ( string )
            {
              v17 = pszPathIn;
              ppszPathOut = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &ppszPathOut,
                0);
              FileNameW = PathFindFileNameW(v16);
              v19 = PathAllocCombine(v17, FileNameW, 1u, &ppszPathOut);
              if ( v19 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x34,
                  (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
                  (const char *)(unsigned int)v19,
                  v37);
              v20 = *(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *, char *))(*(_QWORD *)a1 + 56LL);
              v46 = (HSTRING)ppszPathOut;
              v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, &v46);
              v22 = v20(a1, *(_QWORD *)(v21 + 24), v39, &v38);
              if ( v22 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x36,
                  (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
                  (const char *)(unsigned int)v22,
                  v37);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
            }
          }
        }
      }
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
        (const char *)0x80070490LL,
        v37);
    }
    goto LABEL_35;
  }
  v15 = 1;
  if ( v43 == 1 )
  {
    v41 = 0;
    v23 = *a2;
    v24 = *(unsigned __int8 (__fastcall **)(__int64, const struct _GUID *, GUID *, __int64))(*(_QWORD *)*a2 + 48LL);
    v25 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(&v41);
    if ( !v24(v23, &c_tileStoreTransformerId, &GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb, v25) )
    {
      pszPathIn = 0;
      v30 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
              v44,
              &pszPathIn);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
          (const char *)(unsigned int)v30,
          v37);
      ppszPathOut = 0;
      v31 = pszPathIn;
      v32 = *(__int64 (__fastcall **)(PCWSTR, PWSTR *))(*(_QWORD *)pszPathIn + 48LL);
      WindowsDeleteString(0);
      ppszPathOut = 0;
      v33 = v32(v31, &ppszPathOut);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x56,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
          (const char *)(unsigned int)v33,
          v37);
      v34 = (*(__int64 (__fastcall **)(__int64, PWSTR, _BYTE *, char *))(*(_QWORD *)a1 + 48LL))(
              a1,
              ppszPathOut,
              v39,
              &v38);
      if ( v34 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x59,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
          (const char *)(unsigned int)v34,
          v37);
      WindowsDeleteString((HSTRING)ppszPathOut);
      ppszPathOut = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pszPathIn);
      goto LABEL_35;
    }
    ppszPathOut = 0;
    v26 = v41;
    v27 = *(unsigned __int8 (__fastcall **)(__int64, void *, PWSTR *))(*(_QWORD *)v41 + 32LL);
    WindowsDeleteString(0);
    ppszPathOut = 0;
    if ( v27(v26, &DataStoreCache::TileStoreProperties::PackageFullName, &ppszPathOut) )
    {
      v28 = ppszPathOut;
      if ( !ppszPathOut )
      {
LABEL_27:
        WindowsDeleteString((HSTRING)v28);
LABEL_35:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
        goto LABEL_37;
      }
      v29 = (*(__int64 (__fastcall **)(__int64, PWSTR, _BYTE *, char *))(*(_QWORD *)a1 + 64LL))(
              a1,
              ppszPathOut,
              v39,
              &v38);
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
          (const char *)(unsigned int)v29,
          v37);
    }
    v28 = ppszPathOut;
    goto LABEL_27;
  }
  if ( v43 != 3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\edptransformer\\lib\\DelayedInitializationTasks.h",
      (const char *)0x8000FFFFLL,
      v37);
LABEL_37:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
  if ( !v38 )
LABEL_38:
    v15 = 0;
  v35 = v39[0] != 0;
  v36 = (const struct DataStoreCache::DataItemIdentifier *)(*(__int64 (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a2 + 32LL))(
                                                             *a2,
                                                             &v46);
  DataStoreCache::EdpTransformer::UpdateItem(*a4, v36, v35, v15);
  WindowsDeleteString(v46);
  wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v48);
  DataStoreTransformerTelemetry::RefreshEdpStatusOnTile::~RefreshEdpStatusOnTile((DataStoreTransformerTelemetry::RefreshEdpStatusOnTile *)v48);
}

```

## disassembly

```asm
0x180161928  mov     [rsp-8+arg_10], rbx
0x18016192d  push    rbp
0x18016192e  push    rsi
0x18016192f  push    rdi
0x180161930  push    r12
0x180161932  push    r13
0x180161934  push    r14
0x180161936  push    r15
0x180161938  lea     rbp, [rsp-0F0h]
0x180161940  sub     rsp, 1F0h
0x180161947  mov     rax, cs:__security_cookie
0x18016194e  xor     rax, rsp
0x180161951  mov     [rbp+120h+var_40], rax
0x180161958  mov     r12, r9
0x18016195b  mov     bl, r8b
0x18016195e  mov     r15, rdx
0x180161961  mov     rsi, rcx
0x180161964  lea     rdx, aRefreshedpstat; "RefreshEdpStatusOnTile"
0x18016196b  lea     rcx, [rbp+120h+var_190]
0x18016196f  call    ??0?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180161974  lea     rax, ??_7RefreshEdpStatusOnTile@DataStoreTransformerTelemetry@@6B@; const DataStoreTransformerTelemetry::RefreshEdpStatusOnTile::`vftable'
0x18016197b  mov     [rbp+120h+var_190], rax
0x18016197f  lea     rcx, [rbp+120h+var_190]; this
0x180161983  call    ?StartActivity@RefreshEdpStatusOnTile@DataStoreTransformerTelemetry@@QEAAXXZ; DataStoreTransformerTelemetry::RefreshEdpStatusOnTile::StartActivity(void)
0x180161988  nop
0x180161989  xor     r13d, r13d
0x18016198c  mov     [rsp+220h+var_1EF], r13b
0x180161991  mov     [rsp+220h+var_1F0], r13b
0x180161996  test    bl, bl
0x180161998  jz      loc_180161DB0
0x18016199e  test    rsi, rsi
0x1801619a1  jz      loc_180161DB0
0x1801619a7  mov     qword ptr [rsp+220h+var_1C8.unused], r13
0x1801619ac  lea     rcx, [rsp+220h+var_1C8]
0x1801619b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801619b6  mov     rcx, [r15]
0x1801619b9  mov     rax, [rcx]
0x1801619bc  lea     rdx, [rsp+220h+string]
0x1801619c1  mov     rax, [rax+20h]
0x1801619c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801619ca  nop
0x1801619cb  lea     rdx, [rsp+220h+var_1C8]; HSTRING
0x1801619d0  mov     rcx, [rax]; this
0x1801619d3  call    ?UnifiedTileIdentifier_CreateInstance@UnifiedTile@Shell@WindowsInternal@@YAJPEAUHSTRING__@@PEAPEAUIUnifiedTileIdentifier@123@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifier_CreateInstance(HSTRING__ *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *)
0x1801619d8  mov     rcx, [rbp+128h]; this
0x1801619df  test    eax, eax
0x1801619e1  jns     short loc_1801619F7
0x1801619e3  mov     r9d, eax; char *
0x1801619e6  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x1801619ed  lea     edx, [r13+1Ch]; void *
0x1801619f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801619f7  mov     rcx, [rsp+220h+string]; string
0x1801619fc  call    cs:__imp_WindowsDeleteString
0x180161a02  mov     [rsp+220h+var_1D0], r13d
0x180161a07  mov     rcx, qword ptr [rsp+220h+var_1C8.unused]
0x180161a0c  mov     rax, [rcx]
0x180161a0f  lea     rdx, [rsp+220h+var_1D0]
0x180161a14  mov     rax, [rax+30h]
0x180161a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161a1d  mov     rcx, [rbp+128h]; this
0x180161a24  test    eax, eax
0x180161a26  jns     short loc_180161A3D
0x180161a28  mov     r9d, eax; char *
0x180161a2b  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x180161a32  mov     edx, 1Fh; void *
0x180161a37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180161a3d  mov     eax, [rsp+220h+var_1D0]
0x180161a41  cmp     eax, 2
0x180161a44  jnz     loc_180161BD6
0x180161a4a  mov     [rsp+220h+var_1E0], r13
0x180161a4f  mov     rdi, [r15]
0x180161a52  mov     rax, [rdi]
0x180161a55  mov     rbx, [rax+30h]
0x180161a59  lea     rcx, [rsp+220h+var_1E0]
0x180161a5e  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>)
0x180161a63  mov     r9, rax
0x180161a66  lea     r8, _GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb
0x180161a6d  lea     rdx, c_appResolverTransformerId
0x180161a74  mov     rcx, rdi
0x180161a77  mov     rax, rbx
0x180161a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161a7f  mov     r14d, 1
0x180161a85  test    al, al
0x180161a87  jz      loc_180161BB2
0x180161a8d  mov     [rsp+220h+pszPathIn], r13
0x180161a92  mov     [rsp+220h+string], r13
0x180161a97  mov     rcx, [rsp+220h+var_1E0]
0x180161a9c  mov     rax, [rcx]
0x180161a9f  lea     r8, [rsp+220h+pszPathIn]
0x180161aa4  lea     rdx, ?AppInstallDirectory@AppResolverProperties@DataStoreCache@@3U?$DataStoreProperty@PEBG@2@B; DataStoreCache::DataStoreProperty<ushort const *> const DataStoreCache::AppResolverProperties::AppInstallDirectory
0x180161aab  mov     rax, [rax+20h]
0x180161aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161ab4  test    al, al
0x180161ab6  jz      loc_180161BD1
0x180161abc  cmp     [rsp+220h+pszPathIn], r13
0x180161ac1  jz      loc_180161BD1
0x180161ac7  mov     rcx, [rsp+220h+var_1E0]
0x180161acc  mov     rax, [rcx]
0x180161acf  lea     r8, [rsp+220h+string]
0x180161ad4  lea     rdx, ?AppPathEncoded@AppResolverProperties@DataStoreCache@@3U?$DataStoreProperty@PEBG@2@B; DataStoreCache::DataStoreProperty<ushort const *> const DataStoreCache::AppResolverProperties::AppPathEncoded
0x180161adb  mov     rax, [rax+20h]
0x180161adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161ae4  test    al, al
0x180161ae6  jz      loc_180161BD1
0x180161aec  mov     rdi, [rsp+220h+string]
0x180161af1  test    rdi, rdi
0x180161af4  jz      loc_180161BD1
0x180161afa  mov     rbx, [rsp+220h+pszPathIn]
0x180161aff  mov     [rsp+220h+ppszPathOut], r13
0x180161b04  xor     edx, edx
0x180161b06  lea     rcx, [rsp+220h+ppszPathOut]
0x180161b0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180161b10  mov     rcx, rdi; pszPath
0x180161b13  call    cs:__imp_PathFindFileNameW
0x180161b19  lea     r9, [rsp+220h+ppszPathOut]; ppszPathOut
0x180161b1e  mov     r8d, r14d; dwFlags
0x180161b21  mov     rdx, rax; pszMore
0x180161b24  mov     rcx, rbx; pszPathIn
0x180161b27  call    cs:__imp_PathAllocCombine
0x180161b2d  mov     rcx, [rbp+128h]; this
0x180161b34  test    eax, eax
0x180161b36  jns     short loc_180161B4C
0x180161b38  mov     r9d, eax; char *
0x180161b3b  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x180161b42  lea     edx, [r14+33h]; void *
0x180161b46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180161b4c  mov     rax, [rsi]
0x180161b4f  mov     rbx, [rax+38h]
0x180161b53  mov     rdx, [rsp+220h+ppszPathOut]
0x180161b58  mov     [rsp+220h+var_1B8], rdx
0x180161b5d  lea     rdx, [rsp+220h+var_1B8]
0x180161b62  lea     rcx, [rsp+220h+var_1B0]
0x180161b67  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180161b6c  nop
0x180161b6d  lea     r9, [rsp+220h+var_1F0]
0x180161b72  lea     r8, [rsp+220h+var_1EF]
0x180161b77  mov     rdx, [rax+18h]
0x180161b7b  mov     rcx, rsi
0x180161b7e  mov     rax, rbx
0x180161b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161b86  mov     rcx, [rbp+128h]; this
0x180161b8d  test    eax, eax
0x180161b8f  jns     short loc_180161BA6
0x180161b91  mov     r9d, eax; char *
0x180161b94  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x180161b9b  mov     edx, 36h ; '6'; void *
0x180161ba0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180161ba5  nop
0x180161ba6  lea     rcx, [rsp+220h+ppszPathOut]
0x180161bab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180161bb0  jmp     short loc_180161BD1
0x180161bb2  mov     rcx, [rbp+128h]; this
0x180161bb9  mov     r9d, 80070490h; char *
0x180161bbf  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x180161bc6  mov     edx, 3Ch ; '<'; void *
0x180161bcb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180161bd0  nop
0x180161bd1  jmp     loc_180161D8A
0x180161bd6  mov     r14d, 1
0x180161bdc  cmp     eax, r14d
0x180161bdf  jnz     loc_180161D96
0x180161be5  mov     [rsp+220h+var_1E0], r13
0x180161bea  mov     rdi, [r15]
0x180161bed  mov     rax, [rdi]
0x180161bf0  mov     rbx, [rax+30h]
0x180161bf4  lea     rcx, [rsp+220h+var_1E0]
0x180161bf9  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>)
0x180161bfe  mov     r9, rax
0x180161c01  lea     r8, _GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb
0x180161c08  lea     rdx, c_tileStoreTransformerId
0x180161c0f  mov     rcx, rdi
0x180161c12  mov     rax, rbx
0x180161c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161c1a  test    al, al
0x180161c1c  jz      loc_180161CAF
0x180161c22  mov     [rsp+220h+ppszPathOut], r13
0x180161c27  mov     rdi, [rsp+220h+var_1E0]
0x180161c2c  mov     rax, [rdi]
0x180161c2f  mov     rbx, [rax+20h]
0x180161c33  xor     ecx, ecx; string
0x180161c35  call    cs:__imp_WindowsDeleteString
0x180161c3b  mov     [rsp+220h+ppszPathOut], r13
0x180161c40  lea     r8, [rsp+220h+ppszPathOut]
0x180161c45  lea     rdx, ?PackageFullName@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TileStoreProperties::PackageFullName
0x180161c4c  mov     rcx, rdi
0x180161c4f  mov     rax, rbx
0x180161c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161c57  test    al, al
0x180161c59  jz      short loc_180161C9F
0x180161c5b  mov     rcx, [rsp+220h+ppszPathOut]
0x180161c60  test    rcx, rcx
0x180161c63  jz      short loc_180161CA4
0x180161c65  mov     rax, [rsi]
0x180161c68  lea     r9, [rsp+220h+var_1F0]
0x180161c6d  lea     r8, [rsp+220h+var_1EF]
0x180161c72  mov     rdx, rcx
0x180161c75  mov     rcx, rsi
0x180161c78  mov     rax, [rax+40h]
0x180161c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161c81  mov     rcx, [rbp+128h]; this
0x180161c88  test    eax, eax
0x180161c8a  jns     short loc_180161C9F
0x180161c8c  mov     r9d, eax; char *
0x180161c8f  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x180161c96  lea     edx, [r14+49h]; void *
0x180161c9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180161c9f  mov     rcx, [rsp+220h+ppszPathOut]; string
0x180161ca4  call    cs:__imp_WindowsDeleteString
0x180161caa  jmp     loc_180161D8A
0x180161caf  mov     [rsp+220h+pszPathIn], r13
0x180161cb4  lea     rdx, [rsp+220h+pszPathIn]
0x180161cb9  lea     rcx, [rsp+220h+var_1C8]
0x180161cbe  call    ??$As@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>>)
0x180161cc3  mov     rcx, [rbp+128h]; this
0x180161cca  test    eax, eax
0x180161ccc  jns     short loc_180161CE3
0x180161cce  mov     r9d, eax; char *
0x180161cd1  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x180161cd8  mov     edx, 53h ; 'S'; void *
0x180161cdd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180161ce3  mov     [rsp+220h+ppszPathOut], r13
0x180161ce8  mov     rdi, [rsp+220h+pszPathIn]
0x180161ced  mov     rax, [rdi]
0x180161cf0  mov     rbx, [rax+30h]
0x180161cf4  xor     ecx, ecx; string
0x180161cf6  call    cs:__imp_WindowsDeleteString
0x180161cfc  mov     [rsp+220h+ppszPathOut], r13
0x180161d01  lea     rdx, [rsp+220h+ppszPathOut]
0x180161d06  mov     rcx, rdi
0x180161d09  mov     rax, rbx
0x180161d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161d11  mov     rcx, [rbp+128h]; this
0x180161d18  test    eax, eax
0x180161d1a  jns     short loc_180161D31
0x180161d1c  mov     r9d, eax; char *
0x180161d1f  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x180161d26  mov     edx, 56h ; 'V'; void *
0x180161d2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180161d31  mov     rax, [rsi]
0x180161d34  lea     r9, [rsp+220h+var_1F0]
0x180161d39  lea     r8, [rsp+220h+var_1EF]
0x180161d3e  mov     rdx, [rsp+220h+ppszPathOut]
0x180161d43  mov     rcx, rsi
0x180161d46  mov     rax, [rax+30h]
0x180161d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161d4f  mov     rcx, [rbp+128h]; this
0x180161d56  test    eax, eax
0x180161d58  jns     short loc_180161D6F
0x180161d5a  mov     r9d, eax; char *
0x180161d5d  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\datastorecache\\tra"...
0x180161d64  mov     edx, 59h ; 'Y'; void *
0x180161d69  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180161d6e  nop
0x180161d6f  mov     rcx, [rsp+220h+ppszPathOut]; string
0x180161d74  call    cs:__imp_WindowsDeleteString
0x180161d7a  mov     [rsp+220h+ppszPathOut], r13
0x180161d7f  lea     rcx, [rsp+220h+pszPathIn]
0x180161d84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180161d89  nop
0x180161d8a  lea     rcx, [rsp+220h+var_1E0]
0x180161d8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180161d94  jmp     short loc_180161D9F
0x180161d96  cmp     eax, 3
0x180161d99  jnz     loc_180161E2B
0x180161d9f  lea     rcx, [rsp+220h+var_1C8]
0x180161da4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180161da9  cmp     [rsp+220h+var_1F0], r13b
0x180161dae  jnz     short loc_180161DB3
0x180161db0  mov     r14b, r13b
0x180161db3  cmp     [rsp+220h+var_1EF], r13b
0x180161db8  setnz   bl
0x180161dbb  mov     rcx, [r15]
0x180161dbe  mov     rax, [rcx]
0x180161dc1  lea     rdx, [rsp+220h+var_1B8]
0x180161dc6  mov     rax, [rax+20h]
0x180161dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161dcf  nop
0x180161dd0  mov     r9b, r14b; bool
0x180161dd3  mov     r8b, bl; bool
0x180161dd6  mov     rdx, rax; struct DataStoreCache::DataItemIdentifier *
0x180161dd9  mov     rcx, [r12]; this
0x180161ddd  call    ?UpdateItem@EdpTransformer@DataStoreCache@@AEAAXAEBVDataItemIdentifier@2@_N1@Z; DataStoreCache::EdpTransformer::UpdateItem(DataStoreCache::DataItemIdentifier const &,bool,bool)
0x180161de2  nop
0x180161de3  mov     rcx, [rsp+220h+var_1B8]; string
0x180161de8  call    cs:__imp_WindowsDeleteString
0x180161dee  lea     rcx, [rbp+120h+var_190]
0x180161df2  call    ?Stop@?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180161df7  nop
0x180161df8  lea     rcx, [rbp+120h+var_190]; this
0x180161dfc  call    ??1RefreshEdpStatusOnTile@DataStoreTransformerTelemetry@@QEAA@XZ; DataStoreTransformerTelemetry::RefreshEdpStatusOnTile::~RefreshEdpStatusOnTile(void)
0x180161e01  mov     rcx, [rbp+120h+var_40]
0x180161e08  xor     rcx, rsp; StackCookie
0x180161e0b  call    __security_check_cookie
0x180161e10  mov     rbx, [rsp+220h+arg_10]
0x180161e18  add     rsp, 1F0h
0x180161e1f  pop     r15
0x180161e21  pop     r14
0x180161e23  pop     r13
0x180161e25  pop     r12
0x180161e27  pop     rdi
  ... truncated ...
```
