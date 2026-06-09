# CActivationErrorPopup::CreateAndShowStoreSACDialog(ushort const *)

- ea: `0x18016b8ac`
- end: `0x18016bc87`
- name: `?CreateAndShowStoreSACDialog@CActivationErrorPopup@@AEAAJPEBG@Z`
- size: `987`
- prototype: `int(CActivationErrorPopup *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18016aba0`

## callees

- `0x180009dfc`
- `0x18002fb8c`
- `0x180041f54`
- `0x180142e10`
- `0x180145275`
- `0x1801682a4`
- `0x180168334`
- `0x1801683e8`
- `0x180169dd8`
- `0x180169e98`
- `0x18016a10c`
- `0x18016b8ac`
- `0x18016d2b4`
- `0x18016d7c8`
- `0x18016edf4`
- `0x1801704b0`
- `0x180170a2c`
- `0x1801728c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18016bad9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18016bad9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18016bae5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18016bae5`
- `SHDOCVW!__imp_ShowStoreAppRecommendation` at `0x18016bb15`
- `SHDOCVW!__imp_ShowStoreAppRecommendation` at `0x18016bb15`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016b959`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016bb3d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016bbc6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016b959`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016bb3d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016bbc6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016b96c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016bb50`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016bbd9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016b96c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016bb50`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016bbd9`

## string_xrefs

- `0x18016bc13`: `SHOW_STORE_APP_RECOMMENDATION_FAILURE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CActivationErrorPopup::CreateAndShowStoreSACDialog(CActivationErrorPopup *this, WCHAR *a2)
{
  _QWORD *v4; // rax
  const WCHAR *v5; // r14
  __int64 v6; // rbx
  LPWSTR v7; // rax
  __int64 v8; // rax
  const char *v9; // r9
  __int64 result; // rax
  const wchar_t *v11; // r15
  int v12; // eax
  unsigned __int16 *v13; // rcx
  __int64 v14; // rbx
  const unsigned __int16 *SACErrorCodeAsString; // rbx
  HWND ForegroundWindow; // rax
  int v17; // ebx
  __int64 v18; // r8
  __int64 v19; // rsi
  LPWSTR v20; // rax
  LPWSTR FileNameW; // rax
  __int64 v22; // r8
  __int64 v23; // rdi
  const WCHAR *v24; // rax
  const WCHAR *v25; // rbx
  __int64 v26; // [rsp+40h] [rbp-158h] BYREF
  int v27; // [rsp+48h] [rbp-150h] BYREF
  unsigned __int128 Buf1; // [rsp+50h] [rbp-148h] BYREF
  __int64 v29; // [rsp+60h] [rbp-138h]
  LPVOID ppv; // [rsp+70h] [rbp-128h] BYREF
  LPCWSTR v31; // [rsp+78h] [rbp-120h] BYREF
  unsigned __int16 *v32; // [rsp+80h] [rbp-118h] BYREF
  CActivationErrorPopup *v33; // [rsp+88h] [rbp-110h]
  unsigned __int16 v34[112]; // [rsp+90h] [rbp-108h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v33 = this;
  v31 = a2;
  v26 = 0;
  v4 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::ensure_data(&v26);
  tip2::details::shared_data<1,0,0>::start(*v4 + 8LL, &Buf1);
  try
  {
    v5 = &pszDefault;
    v32 = (unsigned __int16 *)&pszDefault;
    Buf1 = *(_OWORD *)(*((_QWORD *)this + 3) + 100LL);
    if ( ShouldShowStoreSACDialog((struct _GUID *)&Buf1, (const unsigned __int16 **)&v32) )
    {
      v11 = L"feedback-hub:?contextid=1271&newfeedback=true&feedbacktype=2";
      if ( a2 && **((_DWORD **)this + 3) != -2147020340 )
      {
        Buf1 = 0u;
        v29 = 0;
        if ( (int)MakeFileTokenFromPath(a2, &Buf1) >= 0 )
        {
          v12 = StringCchPrintfW(
                  v34,
                  0x6Bu,
                  L"%ws%ws",
                  L"feedback-hub:?contextid=1271&newfeedback=true&feedbacktype=2&files=",
                  (_QWORD)Buf1);
          v13 = v34;
          if ( v12 < 0 )
            v13 = L"feedback-hub:?contextid=1271&newfeedback=true&feedbacktype=2";
          v11 = v13;
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&Buf1);
      }
      v14 = *((_QWORD *)this + 3);
      Buf1 = *(_OWORD *)(v14 + 100);
      if ( memcmp_0(&Buf1, qword_1804179E8, 0x10u) )
        v5 = *(const WCHAR **)(v14 + 56);
      SACErrorCodeAsString = GetSACErrorCodeAsString(*(_DWORD *)v14);
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      CoCreateInstance(
        &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
        0,
        0x404u,
        &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
        &ppv);
      ForegroundWindow = GetForegroundWindow();
      v17 = ShowStoreAppRecommendation(ForegroundWindow, a2, L"SmartAppControl", SACErrorCodeAsString, v11, v5, ppv);
      v27 = v17;
      v19 = *((_QWORD *)this + 3);
      if ( v17 < 0 )
      {
        FileNameW = 0;
        if ( a2 )
        {
          if ( PathIsFileSpecW(a2) )
            FileNameW = a2;
          else
            FileNameW = PathFindFileNameW(a2);
        }
        *(_QWORD *)&Buf1 = FileNameW;
        ActivationErrorTelemetry::StoreSACDialogFailed<unsigned short const *,long const &,unsigned short const (&)[38],long &>(
          &Buf1,
          v19,
          v18,
          &v27);
        *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(
                                 &v26,
                                 &Buf1)
                  + 280LL) = L"SHOW_STORE_APP_RECOMMENDATION_FAILURE";
        tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(&Buf1);
        tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v26);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(&v26);
        result = (unsigned int)v17;
      }
      else
      {
        v20 = 0;
        if ( a2 )
        {
          if ( PathIsFileSpecW(a2) )
            v20 = a2;
          else
            v20 = PathFindFileNameW(a2);
        }
        *(_QWORD *)&Buf1 = v20;
        ActivationErrorTelemetry::StoreSACDialogDisplayed<unsigned short const *,long const &>(&Buf1, v19);
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(
                                &v26,
                                &Buf1)
                 + 272LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(&Buf1);
        tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v26);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(&v26);
        result = 0;
      }
    }
    else
    {
      v27 = -2147467259;
      v6 = *((_QWORD *)this + 3);
      v7 = 0;
      if ( a2 )
      {
        if ( PathIsFileSpecW(a2) )
          v7 = a2;
        else
          v7 = PathFindFileNameW(a2);
      }
      *(_QWORD *)&Buf1 = v7;
      ActivationErrorTelemetry::StoreSACDialogFailed<unsigned short const *,long const &,unsigned short const * &,long>(
        &Buf1,
        v6,
        &v32,
        &v27);
      v8 = tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(
             &v26,
             &Buf1);
      *(_QWORD *)(*(_QWORD *)v8 + 280LL) = v32;
      tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(&Buf1);
      tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v26);
      wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(&v26);
      result = 2147500037LL;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1637,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\activationerrorpopup.cpp",
      v9);
    v27 = -2147467259;
    v23 = *((_QWORD *)v33 + 3);
    v24 = 0;
    v25 = v31;
    if ( v31 )
    {
      if ( PathIsFileSpecW(v31) )
        v24 = v25;
      else
        v24 = PathFindFileNameW(v25);
    }
    v31 = v24;
    ActivationErrorTelemetry::StoreSACDialogFailed<unsigned short const *,long const &,unsigned short const (&)[14],long>(
      &v31,
      v23,
      v22,
      &v27);
    *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(
                             &v26,
                             &v31)
              + 280LL) = L"UNKNOWN_ERROR";
    tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(&v31);
    tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v26);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(&v26);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18016b8ac  mov     [rsp+arg_10], rbx
0x18016b8b1  mov     [rsp+arg_18], rsi
0x18016b8b6  push    rdi
0x18016b8b7  push    r14
0x18016b8b9  push    r15
0x18016b8bb  sub     rsp, 180h
0x18016b8c2  mov     rax, cs:__security_cookie
0x18016b8c9  xor     rax, rsp
0x18016b8cc  mov     [rsp+198h+var_28], rax
0x18016b8d4  mov     rdi, rdx
0x18016b8d7  mov     rsi, rcx
0x18016b8da  mov     [rsp+198h+var_110], rcx
0x18016b8e2  mov     [rsp+198h+var_120], rdx
0x18016b8e7  mov     [rsp+198h+var_158], 0
0x18016b8f0  lea     rcx, [rsp+198h+var_158]
0x18016b8f5  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::ensure_data(void)
0x18016b8fa  mov     rcx, [rax]
0x18016b8fd  add     rcx, 8
0x18016b901  lea     rdx, [rsp+198h+Buf1]
0x18016b906  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18016b90b  nop
0x18016b90c  lea     r14, pszDefault
0x18016b913  mov     [rsp+198h+var_118], r14
0x18016b91b  mov     rax, [rsi+18h]
0x18016b91f  movups  xmm0, xmmword ptr [rax+64h]
0x18016b923  movdqu  [rsp+198h+Buf1], xmm0
0x18016b929  lea     rdx, [rsp+198h+var_118]; unsigned __int16 **
0x18016b931  lea     rcx, [rsp+198h+Buf1]; struct _GUID
0x18016b936  call    ?ShouldShowStoreSACDialog@@YA_NU_GUID@@PEAPEBG@Z; ShouldShowStoreSACDialog(_GUID,ushort const * *)
0x18016b93b  test    al, al
0x18016b93d  jnz     loc_18016B9E6
0x18016b943  mov     [rsp+198h+var_150], 80004005h
0x18016b94b  mov     rbx, [rsi+18h]
0x18016b94f  xor     eax, eax
0x18016b951  test    rdi, rdi
0x18016b954  jz      short loc_18016B97D
0x18016b956  mov     rcx, rdi; pszPath
0x18016b959  call    cs:__imp_PathIsFileSpecW
0x18016b960  nop     dword ptr [rax+rax+00h]
0x18016b965  test    eax, eax
0x18016b967  jnz     short loc_18016B97A
0x18016b969  mov     rcx, rdi; pszPath
0x18016b96c  call    cs:__imp_PathFindFileNameW
0x18016b973  nop     dword ptr [rax+rax+00h]
0x18016b978  jmp     short loc_18016B97D
0x18016b97a  mov     rax, rdi
0x18016b97d  mov     qword ptr [rsp+198h+Buf1], rax
0x18016b982  lea     r9, [rsp+198h+var_150]
0x18016b987  lea     r8, [rsp+198h+var_118]
0x18016b98f  mov     rdx, rbx
0x18016b992  lea     rcx, [rsp+198h+Buf1]
0x18016b997  call    ??$StoreSACDialogFailed@PEBGAEBJAEAPEBGJ@ActivationErrorTelemetry@@SAX$$QEAPEBGAEBJAEAPEBG$$QEAJ@Z; ActivationErrorTelemetry::StoreSACDialogFailed<ushort const *,long const &,ushort const * &,long>(ushort const * &&,long const &,ushort const * &,long &&)
0x18016b99c  lea     rdx, [rsp+198h+Buf1]
0x18016b9a1  lea     rcx, [rsp+198h+var_158]
0x18016b9a6  call    ??C?$tip_test@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(void)
0x18016b9ab  mov     rdx, [rax]
0x18016b9ae  mov     rcx, [rsp+198h+var_118]
0x18016b9b6  mov     [rdx+118h], rcx
0x18016b9bd  lea     rcx, [rsp+198h+Buf1]
0x18016b9c2  call    ??1?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(void)
0x18016b9c7  lea     rcx, [rsp+198h+var_158]
0x18016b9cc  call    ?complete@?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(void)
0x18016b9d1  nop
0x18016b9d2  lea     rcx, [rsp+198h+var_158]
0x18016b9d7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(void)
0x18016b9dc  mov     eax, 80004005h
0x18016b9e1  jmp     loc_18016BC5D
0x18016b9e6  lea     r15, aFeedbackHubCon; "feedback-hub:?contextid=1271&newfeedbac"...
0x18016b9ed  test    rdi, rdi
0x18016b9f0  jz      short loc_18016BA6F
0x18016b9f2  mov     rax, [rsi+18h]
0x18016b9f6  cmp     dword ptr [rax], 800711CCh
0x18016b9fc  jz      short loc_18016BA6F
0x18016b9fe  mov     qword ptr [rsp+198h+Buf1], 0
0x18016ba07  mov     qword ptr [rsp+198h+Buf1+8], 0
0x18016ba10  mov     [rsp+198h+var_138], 0
0x18016ba19  lea     rdx, [rsp+198h+Buf1]
0x18016ba1e  mov     rcx, rdi
0x18016ba21  call    ?MakeFileTokenFromPath@@YAJPEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; MakeFileTokenFromPath(ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18016ba26  test    eax, eax
0x18016ba28  js      short loc_18016BA65
0x18016ba2a  mov     rax, qword ptr [rsp+198h+Buf1]
0x18016ba2f  mov     [rsp+198h+ppv], rax
0x18016ba34  lea     r9, aFeedbackHubCon_0; "feedback-hub:?contextid=1271&newfeedbac"...
0x18016ba3b  lea     r8, aWsWs; "%ws%ws"
0x18016ba42  mov     edx, 6Bh ; 'k'; unsigned __int64
0x18016ba47  lea     rcx, [rsp+198h+var_108]; unsigned __int16 *
0x18016ba4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18016ba54  lea     rcx, [rsp+198h+var_108]
0x18016ba5c  test    eax, eax
0x18016ba5e  cmovs   rcx, r15
0x18016ba62  mov     r15, rcx
0x18016ba65  lea     rcx, [rsp+198h+Buf1]
0x18016ba6a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18016ba6f  mov     rbx, [rsi+18h]
0x18016ba73  movups  xmm0, xmmword ptr [rbx+64h]
0x18016ba77  movdqu  [rsp+198h+Buf1], xmm0
0x18016ba7d  mov     r8d, 10h; Size
0x18016ba83  lea     rdx, qword_1804179E8; Buf2
0x18016ba8a  lea     rcx, [rsp+198h+Buf1]; Buf1
0x18016ba8f  call    memcmp_0
0x18016ba94  test    eax, eax
0x18016ba96  jz      short loc_18016BA9C
0x18016ba98  mov     r14, [rbx+38h]
0x18016ba9c  mov     ecx, [rbx]; int
0x18016ba9e  call    ?GetSACErrorCodeAsString@@YAPEBGJ@Z; GetSACErrorCodeAsString(long)
0x18016baa3  mov     rbx, rax
0x18016baa6  mov     [rsp+198h+var_128], 0
0x18016baaf  lea     rcx, [rsp+198h+var_128]
0x18016bab4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016bab9  lea     rax, [rsp+198h+var_128]
0x18016babe  mov     [rsp+198h+ppv], rax; ppv
0x18016bac3  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18016baca  xor     edx, edx; pUnkOuter
0x18016bacc  mov     r8d, 404h; dwClsContext
0x18016bad2  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x18016bad9  call    cs:__imp_CoCreateInstance
0x18016bae0  nop     dword ptr [rax+rax+00h]
0x18016bae5  call    cs:__imp_GetForegroundWindow
0x18016baec  nop     dword ptr [rax+rax+00h]
0x18016baf1  mov     rcx, [rsp+198h+var_128]
0x18016baf6  mov     [rsp+198h+var_168], rcx
0x18016bafb  mov     [rsp+198h+var_170], r14
0x18016bb00  mov     [rsp+198h+ppv], r15
0x18016bb05  mov     r9, rbx
0x18016bb08  lea     r8, aSmartappcontro; "SmartAppControl"
0x18016bb0f  mov     rdx, rdi
0x18016bb12  mov     rcx, rax
0x18016bb15  call    cs:__imp_ShowStoreAppRecommendation
0x18016bb1c  nop     dword ptr [rax+rax+00h]
0x18016bb21  mov     ebx, eax
0x18016bb23  mov     [rsp+198h+var_150], eax
0x18016bb27  mov     rsi, [rsi+18h]
0x18016bb2b  test    eax, eax
0x18016bb2d  js      loc_18016BBBC
0x18016bb33  xor     eax, eax
0x18016bb35  test    rdi, rdi
0x18016bb38  jz      short loc_18016BB61
0x18016bb3a  mov     rcx, rdi; pszPath
0x18016bb3d  call    cs:__imp_PathIsFileSpecW
0x18016bb44  nop     dword ptr [rax+rax+00h]
0x18016bb49  test    eax, eax
0x18016bb4b  jnz     short loc_18016BB5E
0x18016bb4d  mov     rcx, rdi; pszPath
0x18016bb50  call    cs:__imp_PathFindFileNameW
0x18016bb57  nop     dword ptr [rax+rax+00h]
0x18016bb5c  jmp     short loc_18016BB61
0x18016bb5e  mov     rax, rdi
0x18016bb61  mov     qword ptr [rsp+198h+Buf1], rax
0x18016bb66  mov     rdx, rsi
0x18016bb69  lea     rcx, [rsp+198h+Buf1]
0x18016bb6e  call    ??$StoreSACDialogDisplayed@PEBGAEBJ@ActivationErrorTelemetry@@SAX$$QEAPEBGAEBJ@Z; ActivationErrorTelemetry::StoreSACDialogDisplayed<ushort const *,long const &>(ushort const * &&,long const &)
0x18016bb73  lea     rdx, [rsp+198h+Buf1]
0x18016bb78  lea     rcx, [rsp+198h+var_158]
0x18016bb7d  call    ??C?$tip_test@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(void)
0x18016bb82  mov     rcx, [rax]
0x18016bb85  mov     byte ptr [rcx+110h], 1
0x18016bb8c  lea     rcx, [rsp+198h+Buf1]
0x18016bb91  call    ??1?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(void)
0x18016bb96  lea     rcx, [rsp+198h+var_158]
0x18016bb9b  call    ?complete@?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(void)
0x18016bba0  lea     rcx, [rsp+198h+var_128]
0x18016bba5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016bbaa  nop
0x18016bbab  lea     rcx, [rsp+198h+var_158]
0x18016bbb0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(void)
0x18016bbb5  xor     eax, eax
0x18016bbb7  jmp     loc_18016BC5D
0x18016bbbc  xor     eax, eax
0x18016bbbe  test    rdi, rdi
0x18016bbc1  jz      short loc_18016BBEA
0x18016bbc3  mov     rcx, rdi; pszPath
0x18016bbc6  call    cs:__imp_PathIsFileSpecW
0x18016bbcd  nop     dword ptr [rax+rax+00h]
0x18016bbd2  test    eax, eax
0x18016bbd4  jnz     short loc_18016BBE7
0x18016bbd6  mov     rcx, rdi; pszPath
0x18016bbd9  call    cs:__imp_PathFindFileNameW
0x18016bbe0  nop     dword ptr [rax+rax+00h]
0x18016bbe5  jmp     short loc_18016BBEA
0x18016bbe7  mov     rax, rdi
0x18016bbea  mov     qword ptr [rsp+198h+Buf1], rax
0x18016bbef  lea     r9, [rsp+198h+var_150]
0x18016bbf4  mov     rdx, rsi
0x18016bbf7  lea     rcx, [rsp+198h+Buf1]
0x18016bbfc  call    ??$StoreSACDialogFailed@PEBGAEBJAEAY0CG@$$CBGAEAJ@ActivationErrorTelemetry@@SAX$$QEAPEBGAEBJAEAY0CG@$$CBGAEAJ@Z; ActivationErrorTelemetry::StoreSACDialogFailed<ushort const *,long const &,ushort const (&)[38],long &>(ushort const * &&,long const &,ushort const (&)[38],long &)
0x18016bc01  lea     rdx, [rsp+198h+Buf1]
0x18016bc06  lea     rcx, [rsp+198h+var_158]
0x18016bc0b  call    ??C?$tip_test@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(void)
0x18016bc10  mov     rcx, [rax]
0x18016bc13  lea     rax, aShowStoreAppRe; "SHOW_STORE_APP_RECOMMENDATION_FAILURE"
0x18016bc1a  mov     [rcx+118h], rax
0x18016bc21  lea     rcx, [rsp+198h+Buf1]
0x18016bc26  call    ??1?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(void)
0x18016bc2b  lea     rcx, [rsp+198h+var_158]
0x18016bc30  call    ?complete@?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(void)
0x18016bc35  lea     rcx, [rsp+198h+var_128]
0x18016bc3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016bc3f  nop
0x18016bc40  lea     rcx, [rsp+198h+var_158]
0x18016bc45  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(void)
0x18016bc4a  mov     eax, ebx
0x18016bc4c  jmp     short loc_18016BC5D
0x18016bc4e  lea     rcx, [rsp+198h+var_158]
0x18016bc53  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(void)
0x18016bc58  mov     eax, 80004005h
0x18016bc5d  mov     rcx, [rsp+198h+var_28]
0x18016bc65  xor     rcx, rsp; StackCookie
0x18016bc68  call    __security_check_cookie
0x18016bc6d  lea     r11, [rsp+198h+var_18]
0x18016bc75  mov     rbx, [r11+30h]
0x18016bc79  mov     rsi, [r11+38h]
0x18016bc7d  mov     rsp, r11
0x18016bc80  pop     r15
0x18016bc82  pop     r14
0x18016bc84  pop     rdi
0x18016bc85  retn
```
