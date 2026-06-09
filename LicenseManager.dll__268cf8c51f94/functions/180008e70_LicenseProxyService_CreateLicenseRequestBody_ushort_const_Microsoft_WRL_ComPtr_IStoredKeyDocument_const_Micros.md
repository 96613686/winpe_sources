# LicenseProxyService::CreateLicenseRequestBody(ushort const *,Microsoft::WRL::ComPtr<IStoredKeyDocument> const &,Microsoft::WRL::ComPtr<ILicenseRequestData> const &,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &)

- ea: `0x180008e70`
- end: `0x18000a0db`
- name: `?CreateLicenseRequestBody@LicenseProxyService@@CA?AVvalue@json@web@@PEBGAEBV?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@AEBV?$ComPtr@UILicenseRequestData@@@67@AEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@67@@Z`
- size: `4715`
- prototype: `__int64 __usercall@<rax>(web::json::value *this@<rcx>, void *Src@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `46`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180032010`

## callees

- `0x180004738`
- `0x180005364`
- `0x180007cec`
- `0x180007d64`
- `0x180008e70`
- `0x18000a0e4`
- `0x18000a110`
- `0x18000a98c`
- `0x18000aba8`
- `0x18000b7a4`
- `0x180012dc0`
- `0x180013b50`
- `0x1800171b0`
- `0x180017200`
- `0x180033dc0`
- `0x1800369e4`
- `0x180039aa4`
- `0x180039dd0`
- `0x18003fec8`
- `0x18003ffe0`
- `0x180054a54`
- `0x1800593bc`
- `0x1800683e0`
- `0x18006b49c`
- `0x18006cd80`
- `0x180075e60`
- `0x180076e64`
- `0x180076eb8`
- `0x180077220`
- `0x18007b210`
- `0x18007b370`
- `0x18007b390`
- `0x18007b630`
- `0x18007bd40`
- `0x18007bed0`
- `0x18007c360`
- `0x18007cca0`
- `0x18007cd10`
- `0x18007d1d0`
- `0x180081360`
- `0x18008251f`
- `0x18008a400`
- `0x1800983f0`
- `0x1800989ec`
- `0x1800994e0`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f43`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009f62`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009f62`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000923e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000923e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009cda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009cda`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008f03`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008fb2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800090b2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800094e8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009c11`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008f03`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008fb2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800090b2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800094e8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009c11`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180009cbe`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180009cbe`
- `ext-ms-win-core-licensemanager-l1-1-1!GetLicenseProtocolVersion` at `0x1800093c0`
- `ext-ms-win-core-licensemanager-l1-1-1!GetLicenseProtocolVersion` at `0x1800093c0`
- `ext-ms-win-core-game-streaming-l1-1-0!IsGameStreamingServer` at `0x1800096f3`
- `ext-ms-win-core-game-streaming-l1-1-0!IsGameStreamingServer` at `0x1800096f3`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180009de8`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180009de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000987d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a068`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000987d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a068`

## string_xrefs

- `0x180009a75`: `LicenseProxyService::CreateLicenseRequestBody`
- `0x180009e5d`: `LicenseProxyService::CreateLicenseRequestBody`
- `0x18000971d`: `agentType`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
web::json::value *__fastcall LicenseProxyService::CreateLicenseRequestBody(
        web::json::value *this,
        _WORD *Src,
        __int64 *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  _QWORD *v7; // rdi
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rbx
  __int64 v10; // rdi
  void *v11; // rsi
  unsigned __int64 v12; // rsi
  __int64 v13; // rbx
  WCHAR *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax
  LPCWCH *v17; // rdi
  unsigned __int64 v18; // rsi
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rax
  __m128i v22; // xmm6
  WinStoreAuth::AuthenticationInternal *v23; // rcx
  WinStoreAuth::AuthenticationInternal *v24; // rcx
  _QWORD *v25; // r12
  __int64 ClientChallenge; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  const char *v29; // r9
  WinStoreAuth::AuthenticationInternal *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  LPVOID *p_pv; // rcx
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  int LicenseProtocolVersion; // eax
  __int64 v39; // rdi
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned __int64 v43; // rsi
  LPCWCH *v44; // rdi
  __int64 v45; // rbx
  __int64 v46; // rdi
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdi
  __int64 v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rax
  int v57; // eax
  char *v58; // r13
  unsigned int v59; // esi
  unsigned int v60; // ebx
  int v61; // eax
  __int64 v62; // rax
  int v63; // eax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rbx
  web::json::value *v68; // rdi
  __int64 v69; // rax
  int v70; // eax
  __int64 v71; // rdx
  int v72; // ecx
  unsigned __int8 v73; // r15
  __int64 v74; // rbx
  __int64 v75; // rax
  int v76; // eax
  int v77; // eax
  __int64 v78; // rax
  __int64 v79; // rbx
  __int64 v80; // rax
  LPVOID v81; // rcx
  __int64 *v82; // r12
  __int64 v83; // rdx
  __int64 v84; // rbx
  __int64 v85; // rax
  __int64 v86; // rcx
  int v87; // eax
  const void *v88; // rsi
  __int64 v89; // rbx
  WCHAR *v90; // rdi
  const WCHAR *v91; // rbx
  unsigned int v92; // edi
  unsigned int v93; // esi
  char v94; // al
  const WCHAR *v95; // rcx
  int v96; // ebx
  int v97; // eax
  __int64 *v98; // rdi
  int v99; // eax
  int v100; // eax
  web::json::value *v101; // r14
  int v102; // eax
  __int64 v103; // rax
  __int64 v104; // rbx
  __int64 v105; // rax
  int LastError; // eax
  __int64 v107; // rbx
  __int64 v108; // rax
  unsigned int i; // ebx
  __int64 v110; // rdi
  __int64 v111; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  WinStoreAuth::AuthenticationInternal *v116; // [rsp+58h] [rbp-A8h] BYREF
  int v117; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v118; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v119; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v120; // [rsp+78h] [rbp-88h] BYREF
  web::json::value *v121; // [rsp+80h] [rbp-80h]
  int v122; // [rsp+88h] [rbp-78h] BYREF
  int v123; // [rsp+90h] [rbp-70h] BYREF
  HANDLE Token[2]; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v125; // [rsp+A8h] [rbp-58h]
  unsigned int v126; // [rsp+B0h] [rbp-50h] BYREF
  int v127; // [rsp+B4h] [rbp-4Ch]
  web::json::value *v128; // [rsp+B8h] [rbp-48h]
  LPCWCH lpString2[2]; // [rsp+C0h] [rbp-40h] BYREF
  int cchCount2[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v131; // [rsp+E0h] [rbp-20h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-10h]
  _BYTE v133[32]; // [rsp+100h] [rbp+0h] BYREF
  LPCWCH lpString1[2]; // [rsp+120h] [rbp+20h] BYREF
  int cchCount1[4]; // [rsp+130h] [rbp+30h]
  void *Srca[2]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v137; // [rsp+150h] [rbp+50h]
  unsigned __int64 v138; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v119 = a4;
  v118 = a3;
  v121 = this;
  v128 = this;
  v7 = a5;
  pv = a5;
  v127 = 0;
  *(_OWORD *)Srca = 0;
  v137 = 0;
  v138 = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( Src[v9] );
  if ( v9 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v9 > 7 )
  {
    v10 = std::wstring::_Calculate_growth(v9, 7);
    v11 = (void *)std::allocator<unsigned short>::allocate(Srca, v10 + 1);
    Srca[0] = v11;
    v137 = v9;
    v138 = v10;
    memcpy_0(v11, Src, 2 * v9);
    *((_WORD *)v11 + v9) = 0;
    v7 = pv;
  }
  else
  {
    v137 = v9;
    v138 = 7;
    memcpy_0(Srca, Src, 2 * v9);
    *((_WORD *)Srca + v9) = 0;
  }
  *(_OWORD *)lpString1 = 0;
  *(_OWORD *)cchCount1 = 0;
  v12 = -1;
  do
    ++v12;
  while ( Src[v12] );
  if ( v12 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v12 > 7 )
  {
    v13 = std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Calculate_growth(
            v12,
            7,
            0x7FFFFFFFFFFFFFFELL);
    v14 = (WCHAR *)std::allocator<unsigned short>::allocate(lpString1, v13 + 1);
    lpString1[0] = v14;
    *(_QWORD *)cchCount1 = v12;
    *(_QWORD *)&cchCount1[2] = v13;
    memcpy_0(v14, Src, 2 * v12);
    v14[v12] = 0;
    v7 = pv;
  }
  else
  {
    *(_QWORD *)cchCount1 = v12;
    *(_QWORD *)&cchCount1[2] = 7;
    memcpy_0(lpString1, Src, 2 * v12);
    *((_WORD *)lpString1 + v12) = 0;
  }
  if ( (unsigned __int8)IsXvcContentId(Srca) )
  {
    v15 = ParseXvcContentId(v133, Srca);
    std::wstring::operator=(Srca, v15);
    ContentIdString::~ContentIdString((ContentIdString *)v133);
  }
  web::json::value::value(this);
  v127 = 1;
  v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 56LL))(*v7);
  v17 = (LPCWCH *)v16;
  *(_OWORD *)lpString2 = 0;
  memset(cchCount2, 0, sizeof(cchCount2));
  v18 = *(_QWORD *)(v16 + 16);
  if ( *(_QWORD *)(v16 + 24) > 7u )
    v17 = *(LPCWCH **)v16;
  if ( v18 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v18 > 7 )
  {
    v19 = std::wstring::_Calculate_growth(v18, 7);
    lpString2[0] = (LPCWCH)std::allocator<unsigned short>::allocate(lpString2, v19 + 1);
    *(_QWORD *)cchCount2 = v18;
    *(_QWORD *)&cchCount2[2] = v19;
    memcpy_0((void *)lpString2[0], v17, 2 * v18 + 2);
  }
  else
  {
    *(_QWORD *)cchCount2 = *(_QWORD *)(v16 + 16);
    *(_QWORD *)&cchCount2[2] = 7;
    lpString2[0] = *v17;
    lpString2[1] = v17[1];
  }
  v20 = web::json::value::string(&v116, lpString2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(_QWORD *)&v131 = *(_QWORD *)L"market";
  *((_QWORD *)&v131 + 1) = *(unsigned int *)L"et";
  v21 = web::json::value::operator[](this, &v131);
  web::json::value::operator=(v21, v20);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v131, 2 * si128.m128i_i64[1] + 2);
  v22 = _mm_load_si128((const __m128i *)&_xmm);
  si128 = v22;
  LOWORD(v131) = 0;
  v23 = v116;
  if ( v116 )
    (*(void (__fastcall **)(WinStoreAuth::AuthenticationInternal *, __int64))(*(_QWORD *)v116 + 192LL))(v116, 1);
  if ( WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v23) )
  {
    v25 = v119;
  }
  else
  {
    SuspendImpersonationScope::SuspendImpersonationScope((SuspendImpersonationScope *)Token);
    v25 = v119;
    ClientChallenge = LicenseProxyService::GetClientChallenge(v133);
    v27 = web::json::value::string(&v116, ClientChallenge);
    std::wstring::wstring(lpString2, L"clientChallenge");
    v28 = web::json::value::operator[](this, lpString2);
    web::json::value::operator=(v28, v27);
    std::wstring::_Tidy_deallocate(lpString2);
    web::json::value::~value((web::json::value *)&v116);
    if ( Token[1] && !SetThreadToken(0, Token[1]) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\enduser\\WinStore\\inc\\RAIIHelpers.h",
        v29);
    Token[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(Token);
  }
  if ( WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v24)
    || WinStoreAuth::AuthenticationInternal::IsSandboxEnabled(v30) )
  {
    web::json::value::object(&v116, 0);
    v34 = web::json::value::array(&v123, 0);
    v35 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)pv + 32LL))(*(_QWORD *)pv);
    v36 = web::json::value::operator[](&v116, v35);
    web::json::value::operator=(v36, v34);
    web::json::value::~value((web::json::value *)&v123);
    *(__m128i *)cchCount2 = _mm_load_si128((const __m128i *)&_xmm);
    lpString2[0] = *(LPCWCH *)L"users";
    lpString2[1] = (LPCWCH)aUsers[4];
    v37 = web::json::value::operator[](this, lpString2);
    web::json::value::operator=(v37, &v116);
    std::wstring::_Tidy_deallocate(lpString2);
    p_pv = (LPVOID *)&v116;
  }
  else
  {
    v31 = LicenseProxyService::CreateUsersJSON(&pv, pv);
    *(__m128i *)cchCount2 = _mm_load_si128((const __m128i *)&_xmm);
    lpString2[0] = *(LPCWCH *)L"users";
    lpString2[1] = (LPCWCH)aUsers[4];
    v32 = web::json::value::operator[](this, lpString2);
    web::json::value::operator=(v32, v31);
    std::wstring::_Tidy_deallocate(lpString2);
    p_pv = &pv;
  }
  web::json::value::~value((web::json::value *)p_pv);
  v126 = 4;
  if ( (unsigned __int8)IsGetLicenseProtocolVersionPresent() )
  {
    LicenseProtocolVersion = GetLicenseProtocolVersion(&v126);
    if ( LicenseProtocolVersion < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6EE,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)LicenseProtocolVersion,
        bIgnoreCase);
  }
  v39 = web::json::value::number(&pv, v126);
  *(_OWORD *)lpString2 = 0;
  *(_OWORD *)cchCount2 = 0;
  v40 = std::wstring::_Calculate_growth(14, 7);
  v41 = std::allocator<unsigned short>::allocate(lpString2, v40 + 1);
  lpString2[0] = (LPCWCH)v41;
  *(_QWORD *)cchCount2 = 14;
  *(_QWORD *)&cchCount2[2] = v40;
  *(_OWORD *)v41 = *(_OWORD *)L"licenseVersion";
  *(_OWORD *)(v41 + 12) = *(_OWORD *)L"eVersion";
  *(_WORD *)(v41 + 28) = 0;
  v42 = web::json::value::operator[](this, lpString2);
  web::json::value::operator=(v42, v39);
  if ( *(_QWORD *)&cchCount2[2] > 7u )
    std::_Deallocate<16>(lpString2[0], 2LL * *(_QWORD *)&cchCount2[2] + 2);
  *(__m128i *)cchCount2 = v22;
  LOWORD(lpString2[0]) = 0;
  if ( pv )
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)pv + 192LL))(pv, 1);
  *(_OWORD *)lpString2 = 0;
  memset(cchCount2, 0, sizeof(cchCount2));
  v43 = v137;
  v44 = (LPCWCH *)Srca;
  if ( v138 > 7 )
    v44 = (LPCWCH *)Srca[0];
  if ( v137 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v137 > 7 )
  {
    v45 = std::wstring::_Calculate_growth(v137, 7);
    lpString2[0] = (LPCWCH)std::allocator<unsigned short>::allocate(lpString2, v45 + 1);
    *(_QWORD *)cchCount2 = v43;
    *(_QWORD *)&cchCount2[2] = v45;
    memcpy_0((void *)lpString2[0], v44, 2 * v43 + 2);
  }
  else
  {
    *(_QWORD *)cchCount2 = v137;
    *(_QWORD *)&cchCount2[2] = 7;
    lpString2[0] = *v44;
    lpString2[1] = v44[1];
  }
  v46 = web::json::value::string(&pv, lpString2);
  v131 = 0;
  si128 = 0;
  v47 = std::wstring::_Calculate_growth(9, 7);
  v48 = std::allocator<unsigned short>::allocate(&v131, v47 + 1);
  *(_QWORD *)&v131 = v48;
  si128.m128i_i64[0] = 9;
  si128.m128i_i64[1] = v47;
  *(_OWORD *)v48 = *(_OWORD *)L"contentId";
  *(_WORD *)(v48 + 16) = aContentid_0[8];
  *(_WORD *)(v48 + 18) = 0;
  v49 = web::json::value::operator[](this, &v131);
  web::json::value::operator=(v49, v46);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v131, 2 * si128.m128i_i64[1] + 2);
  si128 = v22;
  LOWORD(v131) = 0;
  if ( pv )
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)pv + 192LL))(pv, 1);
  v50 = LicenseProxyService::CreateDeviceContext(&pv);
  *(_OWORD *)lpString2 = 0;
  *(_OWORD *)cchCount2 = 0;
  v51 = std::wstring::_Calculate_growth(13, 7);
  v52 = std::allocator<unsigned short>::allocate(lpString2, v51 + 1);
  lpString2[0] = (LPCWCH)v52;
  *(_QWORD *)cchCount2 = 13;
  *(_QWORD *)&cchCount2[2] = v51;
  *(_OWORD *)v52 = *(_OWORD *)L"deviceContext";
  *(_OWORD *)(v52 + 10) = *(_OWORD *)L"eContext";
  *(_WORD *)(v52 + 26) = 0;
  v53 = web::json::value::operator[](this, lpString2);
  web::json::value::operator=(v53, v50);
  if ( *(_QWORD *)&cchCount2[2] > 7u )
    std::_Deallocate<16>(lpString2[0], 2LL * *(_QWORD *)&cchCount2[2] + 2);
  *(__m128i *)cchCount2 = v22;
  LOWORD(lpString2[0]) = 0;
  if ( pv )
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)pv + 192LL))(pv, 1);
  if ( (unsigned __int8)IsIsGameStreamingServerPresent() && (unsigned int)IsGameStreamingServer() )
  {
    v54 = std::wstring::wstring(v133, L"CloudStreamingDevice");
    v55 = web::json::value::string(&pv, v54);
    std::wstring::wstring(lpString2, L"agentType");
    v56 = web::json::value::operator[](this, lpString2);
    web::json::value::operator=(v56, v55);
    ContentIdString::~ContentIdString((ContentIdString *)lpString2);
    web::json::value::~value((web::json::value *)&pv);
  }
  *(_QWORD *)&v131 = 0;
  DWORD2(v131) = 0;
  v120 = 0;
  pv = 0;
  v57 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, LPVOID *))(*(_QWORD *)*v25 + 48LL))(*v25, &v120, &pv);
  if ( v57 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x702,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v57,
      bIgnoreCase);
  v58 = (char *)pv;
  *(_QWORD *)&v131 = pv;
  v59 = v120;
  DWORD2(v131) = v120;
  if ( v120 )
  {
    *(_OWORD *)Token = 0;
    v125 = 0;
    v60 = 0;
    do
    {
      v116 = 0;
      v61 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, WinStoreAuth::AuthenticationInternal **))&v58[8 * v60])(
              *(_QWORD *)&v58[8 * v60],
              &GUID_dc44f1df_dc28_4036_8f9f_30978f2ed4db,
              &v116);
      if ( v61 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x70D,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v61,
          bIgnoreCase);
      pv = 0;
      v62 = *(_QWORD *)v116;
      pv = 0;
      v63 = (*(__int64 (__fastcall **)(WinStoreAuth::AuthenticationInternal *, LPVOID *))(v62 + 104))(v116, &pv);
      if ( v63 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x710,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v63,
          bIgnoreCase);
      v64 = std::wstring::wstring(v133, pv);
      v65 = web::json::value::string(&v123, v64);
      if ( Token[1] == v125 )
        std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(Token, Token[1], v65);
      else
        std::vector<web::json::value>::_Emplace_back_with_unused_capacity<web::json::value>(Token, v65);
      web::json::value::~value((web::json::value *)&v123);
      if ( pv )
        CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v116);
      ++v60;
    }
    while ( v60 < v59 );
    v66 = std::vector<web::json::value>::vector<web::json::value>(lpString2, Token);
    v67 = web::json::value::array(&pv, v66);
    std::wstring::wstring(v133, L"roots");
    v68 = v121;
    v69 = web::json::value::operator[](v121, v133);
    web::json::value::operator=(v69, v67);
    ContentIdString::~ContentIdString((ContentIdString *)v133);
    web::json::value::~value((web::json::value *)&pv);
    std::vector<web::json::value>::_Tidy(Token);
  }
  else
  {
    v68 = v121;
  }
  v122 = 0;
  v70 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v25 + 80LL))(*v25, &v122);
  if ( v70 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v70,
      bIgnoreCase);
  v72 = v122;
  if ( v122 == 2 )
  {
    v73 = 0;
    LOBYTE(v71) = 1;
    v74 = web::json::value::boolean(&v119, v71);
    std::wstring::wstring(v133, L"preview");
    v75 = web::json::value::operator[](v68, v133);
    web::json::value::operator=(v75, v74);
    std::wstring::_Tidy_deallocate(v133);
    web::json::value::~value((web::json::value *)&v119);
LABEL_149:
    v101 = v121;
    goto LABEL_150;
  }
  if ( !v122 )
  {
    pv = 0;
    v76 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*v25 + 72LL))(*v25, &pv);
    if ( v76 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x727,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)v76,
        bIgnoreCase);
    if ( !pv )
      goto LABEL_90;
    LODWORD(v116) = 0;
    v117 = 0;
    v77 = (*(__int64 (__fastcall **)(LPVOID, WinStoreAuth::AuthenticationInternal **, int *))(*(_QWORD *)pv + 48LL))(
            pv,
            &v116,
            &v117);
    if ( v77 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)v77,
        bIgnoreCase);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      0x730u,
      "LicenseProxyService::CreateLicenseRequestBody",
      (wchar_t *)L"Checking existing lease quality (detail 0x%08x)");
    if ( (unsigned int)(v117 + 2143322012) > 0x63 )
    {
LABEL_90:
      v78 = std::wstring::wstring(lpString2, L"Rude");
      v79 = web::json::value::string(&v116, v78);
      std::wstring::wstring(v133, L"concurrencyMode");
      v80 = web::json::value::operator[](v68, v133);
      web::json::value::operator=(v80, v79);
      std::wstring::_Tidy_deallocate(v133);
      web::json::value::~value((web::json::value *)&v116);
    }
    v81 = pv;
    if ( pv )
    {
      pv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v81 + 16LL))(v81);
    }
    v72 = v122;
  }
  v82 = v118;
  if ( ((v72 - 1) & 0xFFFFFFFC) == 0
    && v72 != 2
    && !(unsigned __int8)LicenseProxyService::IsTempSignedOperatingSystemKey(v118) )
  {
    LOBYTE(v83) = 1;
    v84 = web::json::value::boolean(&pv, v83);
    std::wstring::wstring(v133, L"keyOnly");
    v85 = web::json::value::operator[](v68, v133);
    web::json::value::operator=(v85, v84);
    std::wstring::_Tidy_deallocate(v133);
    web::json::value::~value((web::json::value *)&pv);
  }
  v86 = *v82;
  if ( !*v82 )
  {
    v73 = 1;
    goto LABEL_149;
  }
  pv = 0;
  v87 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v86 + 104LL))(v86, &pv);
  if ( v87 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x74D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v87,
      bIgnoreCase);
  v88 = pv;
  *(_OWORD *)lpString2 = 0;
  *(_OWORD *)cchCount2 = 0;
  do
    ++v8;
  while ( *((_WORD *)pv + v8) );
  if ( v8 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v8 > 7 )
  {
    v89 = std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Calculate_growth(
            v8,
            7,
            0x7FFFFFFFFFFFFFFELL);
    v90 = (WCHAR *)std::allocator<unsigned short>::allocate(lpString2, v89 + 1);
    lpString2[0] = v90;
    *(_QWORD *)cchCount2 = v8;
    *(_QWORD *)&cchCount2[2] = v89;
    memcpy_0(v90, v88, 2 * v8);
    v90[v8] = 0;
  }
  else
  {
    *(_QWORD *)cchCount2 = v8;
    *(_QWORD *)&cchCount2[2] = 7;
    memcpy_0(lpString2, pv, 2 * v8);
    *((_WORD *)lpString2 + v8) = 0;
  }
  v91 = (const WCHAR *)lpString2;
  if ( *(_QWORD *)&cchCount2[2] > 7u )
    v91 = lpString2[0];
  v92 = cchCount2[0];
  v93 = cchCount1[0];
  v94 = IsCompareContentIdPresent();
  v95 = (const WCHAR *)lpString1;
  if ( v94 )
  {
    if ( *(_QWORD *)&cchCount1[2] > 7u )
      v95 = lpString1[0];
    v96 = CompareContentId(v95, v93, v91, v92);
  }
  else
  {
    if ( *(_QWORD *)&cchCount1[2] > 7u )
      v95 = lpString1[0];
    v96 = CompareStringOrdinal(v95, v93, v91, v92, 1) - 2;
  }
  if ( *(_QWORD *)&cchCount2[2] > 7u )
    std::_Deallocate<16>(lpString2[0], 2LL * *(_QWORD *)&cchCount2[2] + 2);
  v123 = 0;
  v97 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v119 + 80LL))(*v119, &v123);
  if ( v97 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x753,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v97,
      bIgnoreCase);
  LODWORD(v116) = 0;
  v117 = 0;
  v98 = v118;
  v99 = (*(__int64 (__fastcall **)(__int64, int *, WinStoreAuth::AuthenticationInternal **))(*(_QWORD *)*v118 + 48LL))(
          *v118,
          &v117,
          &v116);
  if ( v99 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x757,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v99,
      bIgnoreCase);
  if ( v117 < 1073741825 && (unsigned int)(v117 - 536870913) > 0xFFFFFFF || v96 || v123 == 3 )
  {
    if ( !(unsigned __int8)LicenseProxyService::IsTempSignedOperatingSystemKey(v98) )
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        0x772u,
        "LicenseProxyService::CreateLicenseRequestBody",
        (wchar_t *)L"Transmitting old key for content ID %s in request for content ID %s with validity %x (detail 0x%08x)");
      LODWORD(v118) = 0;
      Token[0] = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
      Token[1] = 0;
      v102 = (*(__int64 (__fastcall **)(__int64, __int64 **, HANDLE *))(*(_QWORD *)*v98 + 40LL))(*v98, &v118, &Token[1]);
      if ( v102 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x776,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v102,
          bIgnoreCasea);
      v103 = _to_base64(lpString2);
      v104 = web::json::value::string(&v119, v103);
      std::wstring::wstring(v133, L"keyToRefresh");
      v101 = v121;
      v105 = web::json::value::operator[](v121, v133);
      web::json::value::operator=(v105, v104);
      std::wstring::_Tidy_deallocate(v133);
      web::json::value::~value((web::json::value *)&v119);
      Token[0] = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
      if ( Token[1] && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::InternalClose(Token) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RaiseException(LastError, 1u, 0, 0);
        __debugbreak();
      }
      goto LABEL_144;
    }
LABEL_143:
    v101 = v121;
LABEL_144:
    v73 = 1;
    goto LABEL_145;
  }
  LODWORD(v118) = 0;
  v100 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)*v98 + 112LL))(*v98, 0x20000000, &v118);
  if ( v100 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x761,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v100,
      bIgnoreCase);
  if ( (unsigned int)XblaIsConsole(retaddr) )
  {
    if ( v117 >= 2130706432 )
      goto LABEL_134;
LABEL_133:
    if ( (_DWORD)v118 == 0x7FFFFFFF )
      goto LABEL_134;
    goto LABEL_143;
  }
  if ( v117 != 2130706432 )
    goto LABEL_133;
LABEL_134:
  v73 = 0;
  v101 = v121;
LABEL_145:
  if ( pv )
    CoTaskMemFree(pv);
  v59 = v120;
LABEL_150:
  v107 = web::json::value::boolean(&v119, v73);
  *(__m128i *)cchCount2 = _mm_load_si128((const __m128i *)&_xmm);
  lpString2[0] = *(LPCWCH *)L"needKey";
  LODWORD(lpString2[1]) = *(_DWORD *)L"Key";
  HIDWORD(lpString2[1]) = aNeedkey[6];
  v108 = web::json::value::operator[](v101, lpString2);
  web::json::value::operator=(v108, v107);
  if ( *(_QWORD *)&cchCount2[2] > 7u )
    std::_Deallocate<16>(lpString2[0], 2LL * *(_QWORD *)&cchCount2[2] + 2);
  *(__m128i *)cchCount2 = v22;
  LOWORD(lpString2[0]) = 0;
  if ( v119 )
    (*(void (__fastcall **)(_QWORD *, __int64))(*v119 + 192LL))(v119, 1);
  if ( v58 )
  {
    for ( i = 0; i < v59; ++i )
    {
      v110 = 8LL * i;
      v111 = *(_QWORD *)&v58[v110];
      if ( v111 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
      *(_QWORD *)&v58[v110] = 0;
    }
    CoTaskMemFree(v58);
  }
  if ( *(_QWORD *)&cchCount1[2] > 7u )
    std::_Deallocate<16>(lpString1[0], 2LL * *(_QWORD *)&cchCount1[2] + 2);
  *(__m128i *)cchCount1 = v22;
  LOWORD(lpString1[0]) = 0;
  if ( v138 > 7 )
    std::_Deallocate<16>(Srca[0], 2 * v138 + 2);
  return v101;
}

```

## disassembly

```asm
0x180008e70  push    rbp
0x180008e72  push    rbx
0x180008e73  push    rsi
0x180008e74  push    rdi
0x180008e75  push    r12
0x180008e77  push    r13
0x180008e79  push    r14
0x180008e7b  push    r15
0x180008e7d  lea     rbp, [rsp-88h]
0x180008e85  sub     rsp, 188h
0x180008e8c  movaps  [rsp+1C0h+var_50], xmm6
0x180008e94  mov     rax, cs:__security_cookie
0x180008e9b  xor     rax, rsp
0x180008e9e  mov     [rbp+0C0h+var_60], rax
0x180008ea2  mov     [rsp+1C0h+var_150], r9
0x180008ea7  mov     [rsp+1C0h+var_158], r8
0x180008eac  mov     r15, rdx
0x180008eaf  mov     r13, rcx
0x180008eb2  mov     [rbp+0C0h+var_140], rcx
0x180008eb6  mov     [rbp+0C0h+var_108], rcx
0x180008eba  mov     rdi, [rbp+0C0h+arg_20]
0x180008ec1  mov     [rsp+1C0h+pv], rdi
0x180008ec6  xor     esi, esi
0x180008ec8  mov     [rbp+0C0h+var_10C], esi
0x180008ecb  xorps   xmm0, xmm0
0x180008ece  movups  xmmword ptr [rbp+0C0h+Src], xmm0
0x180008ed2  mov     [rbp+0C0h+var_70], rsi
0x180008ed6  mov     [rbp+0C0h+var_68], rsi
0x180008eda  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180008ee1  mov     rbx, r14
0x180008ee4  inc     rbx
0x180008ee7  cmp     [rdx+rbx*2], si
0x180008eeb  jnz     short loc_180008EE4
0x180008eed  mov     rax, 7FFFFFFFFFFFFFFEh
0x180008ef7  cmp     rbx, rax
0x180008efa  jbe     short loc_180008F0A
0x180008efc  lea     rcx, aStringTooLong; "string too long"
0x180008f03  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180008f0a  lea     r12, [rbx+rbx]
0x180008f0e  cmp     rbx, 7
0x180008f12  ja      short loc_180008F36
0x180008f14  mov     [rbp+0C0h+var_70], rbx
0x180008f18  mov     [rbp+0C0h+var_68], 7
0x180008f20  mov     r8, r12; Size
0x180008f23  lea     rcx, [rbp+0C0h+Src]; void *
0x180008f27  call    memcpy_0
0x180008f2c  mov     word ptr [rbp+r12+0C0h+Src], si
0x180008f32  xor     ebx, ebx
0x180008f34  jmp     short loc_180008F7F
0x180008f36  mov     r8, rax
0x180008f39  mov     edx, 7
0x180008f3e  mov     rcx, rbx
0x180008f41  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180008f46  mov     rdi, rax
0x180008f49  lea     rdx, [rax+1]
0x180008f4d  lea     rcx, [rbp+0C0h+Src]
0x180008f51  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180008f56  mov     rsi, rax
0x180008f59  mov     [rbp+0C0h+Src], rax
0x180008f5d  mov     [rbp+0C0h+var_70], rbx
0x180008f61  mov     [rbp+0C0h+var_68], rdi
0x180008f65  mov     r8, r12; Size
0x180008f68  mov     rdx, r15; Src
0x180008f6b  mov     rcx, rax; void *
0x180008f6e  call    memcpy_0
0x180008f73  xor     ebx, ebx
0x180008f75  mov     [r12+rsi], bx
0x180008f7a  mov     rdi, [rsp+1C0h+pv]
0x180008f7f  xorps   xmm0, xmm0
0x180008f82  movups  xmmword ptr [rbp+0C0h+lpString1], xmm0
0x180008f86  xorps   xmm1, xmm1
0x180008f89  movdqu  xmmword ptr [rbp+0C0h+cchCount1], xmm1
0x180008f8e  mov     rsi, r14
0x180008f91  inc     rsi
0x180008f94  cmp     word ptr [r15+rsi*2], 0
0x180008f9a  jnz     short loc_180008F91
0x180008f9c  mov     rax, 7FFFFFFFFFFFFFFEh
0x180008fa6  cmp     rsi, rax
0x180008fa9  jbe     short loc_180008FB9
0x180008fab  lea     rcx, aStringTooLong; "string too long"
0x180008fb2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180008fb9  lea     r12, [rsi+rsi]
0x180008fbd  cmp     rsi, 7
0x180008fc1  ja      short loc_180008FE6
0x180008fc3  mov     qword ptr [rbp+0C0h+cchCount1], rsi
0x180008fc7  mov     qword ptr [rbp+0C0h+cchCount1+8], 7
0x180008fcf  mov     r8, r12; Size
0x180008fd2  mov     rdx, r15; Src
0x180008fd5  lea     rcx, [rbp+0C0h+lpString1]; void *
0x180008fd9  call    memcpy_0
0x180008fde  mov     word ptr [rbp+r12+0C0h+lpString1], bx
0x180008fe4  jmp     short loc_18000902F
0x180008fe6  mov     r8, rax
0x180008fe9  mov     edx, 7
0x180008fee  mov     rcx, rsi
0x180008ff1  call    ?_Calculate_growth@?$basic_string@GUcontent_id_char_traits@@V?$allocator@G@std@@@std@@CA_K_K00@Z; std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>>::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180008ff6  mov     rbx, rax
0x180008ff9  lea     rdx, [rax+1]
0x180008ffd  lea     rcx, [rbp+0C0h+lpString1]
0x180009001  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180009006  mov     rdi, rax
0x180009009  mov     [rbp+0C0h+lpString1], rax
0x18000900d  mov     qword ptr [rbp+0C0h+cchCount1], rsi
0x180009011  mov     qword ptr [rbp+0C0h+cchCount1+8], rbx
0x180009015  mov     r8, r12; Size
0x180009018  mov     rdx, r15; Src
0x18000901b  mov     rcx, rax; void *
0x18000901e  call    memcpy_0
0x180009023  xor     ebx, ebx
0x180009025  mov     [r12+rdi], bx
0x18000902a  mov     rdi, [rsp+1C0h+pv]
0x18000902f  lea     rcx, [rbp+0C0h+Src]
0x180009033  call    ?IsXvcContentId@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsXvcContentId(std::wstring const &)
0x180009038  test    al, al
0x18000903a  jz      short loc_18000905E
0x18000903c  lea     rdx, [rbp+0C0h+Src]
0x180009040  lea     rcx, [rbp+0C0h+var_C0]
0x180009044  call    ?ParseXvcContentId@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; ParseXvcContentId(std::wstring const &)
0x180009049  mov     rdx, rax
0x18000904c  lea     rcx, [rbp+0C0h+Src]
0x180009050  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180009055  lea     rcx, [rbp+0C0h+var_C0]; this
0x180009059  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18000905e  mov     rcx, r13; this
0x180009061  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180009066  mov     [rbp+0C0h+var_10C], 1
0x18000906d  mov     rcx, [rdi]
0x180009070  mov     rax, [rcx]
0x180009073  mov     rax, [rax+38h]
0x180009077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000907c  mov     rdi, rax
0x18000907f  xorps   xmm0, xmm0
0x180009082  movups  xmmword ptr [rbp+0C0h+lpString2], xmm0
0x180009086  mov     qword ptr [rbp+0C0h+cchCount2], rbx
0x18000908a  mov     qword ptr [rbp+0C0h+cchCount2+8], rbx
0x18000908e  mov     rsi, [rax+10h]
0x180009092  cmp     qword ptr [rax+18h], 7
0x180009097  jbe     short loc_18000909C
0x180009099  mov     rdi, [rax]
0x18000909c  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800090a6  cmp     rsi, rax
0x1800090a9  jbe     short loc_1800090B9
0x1800090ab  lea     rcx, aStringTooLong; "string too long"
0x1800090b2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800090b9  cmp     rsi, 7
0x1800090bd  ja      short loc_1800090DC
0x1800090bf  mov     qword ptr [rbp+0C0h+cchCount2], rsi
0x1800090c3  mov     qword ptr [rbp+0C0h+cchCount2+8], 7
0x1800090cb  mov     rax, [rdi]
0x1800090ce  mov     [rbp+0C0h+lpString2], rax
0x1800090d2  mov     rax, [rdi+8]
0x1800090d6  mov     [rbp+0C0h+lpString2+8], rax
0x1800090da  jmp     short loc_18000911B
0x1800090dc  mov     r8, rax
0x1800090df  mov     edx, 7
0x1800090e4  mov     rcx, rsi
0x1800090e7  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800090ec  mov     rbx, rax
0x1800090ef  lea     rdx, [rax+1]
0x1800090f3  lea     rcx, [rbp+0C0h+lpString2]
0x1800090f7  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x1800090fc  mov     [rbp+0C0h+lpString2], rax
0x180009100  mov     qword ptr [rbp+0C0h+cchCount2], rsi
0x180009104  mov     qword ptr [rbp+0C0h+cchCount2+8], rbx
0x180009108  lea     r8, ds:2[rsi*2]; Size
0x180009110  mov     rdx, rdi; Src
0x180009113  mov     rcx, rax; void *
0x180009116  call    memcpy_0
0x18000911b  lea     rdx, [rbp+0C0h+lpString2]
0x18000911f  lea     rcx, [rsp+1C0h+var_168]
0x180009124  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x180009129  mov     rbx, rax
0x18000912c  xor     esi, esi
0x18000912e  mov     dword ptr [rbp+0C0h+var_E0+0Ch], esi
0x180009131  movdqa  xmm0, cs:__xmm@00000000000000070000000000000006
0x180009139  movdqu  [rbp+0C0h+var_D0], xmm0
0x18000913e  movsd   xmm0, qword ptr cs:aMarket; "market"
0x180009146  movsd   qword ptr [rbp+0C0h+var_E0], xmm0
0x18000914b  mov     eax, dword ptr cs:aMarket+8; "et"
0x180009151  mov     dword ptr [rbp+0C0h+var_E0+8], eax
0x180009154  mov     word ptr [rbp+0C0h+var_E0+0Ch], si
0x180009158  lea     rdx, [rbp+0C0h+var_E0]
0x18000915c  mov     rcx, r13
0x18000915f  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180009164  mov     rcx, rax
0x180009167  mov     rdx, rbx
0x18000916a  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x18000916f  nop
0x180009170  mov     rdx, qword ptr [rbp+0C0h+var_D0+8]
0x180009174  cmp     rdx, 7
0x180009178  jbe     short loc_18000918B
0x18000917a  lea     rdx, ds:2[rdx*2]
0x180009182  mov     rcx, qword ptr [rbp+0C0h+var_E0]
0x180009186  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000918b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180009193  movdqu  [rbp+0C0h+var_D0], xmm6
0x180009198  mov     word ptr [rbp+0C0h+var_E0], si
0x18000919c  mov     rcx, [rsp+1C0h+var_168]
0x1800091a1  test    rcx, rcx
0x1800091a4  jz      short loc_1800091BA
0x1800091a6  mov     rax, [rcx]
0x1800091a9  mov     edx, 1
0x1800091ae  mov     rax, [rax+0C0h]
0x1800091b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ba  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x1800091bf  test    al, al
0x1800091c1  jnz     loc_180009278
0x1800091c7  lea     rcx, [rbp+0C0h+Token]; this
0x1800091cb  call    ??0SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::SuspendImpersonationScope(void)
0x1800091d0  nop
0x1800091d1  mov     r12, [rsp+1C0h+var_150]
0x1800091d6  mov     r8, r12
0x1800091d9  mov     rdx, r15
0x1800091dc  lea     rcx, [rbp+0C0h+var_C0]; Src
0x1800091e0  call    ?GetClientChallenge@LicenseProxyService@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEBV?$ComPtr@UILicenseRequestData@@@WRL@Microsoft@@@Z; LicenseProxyService::GetClientChallenge(ushort const *,Microsoft::WRL::ComPtr<ILicenseRequestData> const &)
0x1800091e5  mov     rdx, rax
0x1800091e8  lea     rcx, [rsp+1C0h+var_168]
0x1800091ed  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800091f2  mov     rbx, rax
0x1800091f5  lea     rdx, aClientchalleng; "clientChallenge"
0x1800091fc  lea     rcx, [rbp+0C0h+lpString2]
0x180009200  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009205  nop
0x180009206  lea     rdx, [rbp+0C0h+lpString2]
0x18000920a  mov     rcx, r13
0x18000920d  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180009212  mov     rcx, rax
0x180009215  mov     rdx, rbx
0x180009218  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x18000921d  nop
0x18000921e  lea     rcx, [rbp+0C0h+lpString2]
0x180009222  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009227  nop
0x180009228  lea     rcx, [rsp+1C0h+var_168]; this
0x18000922d  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x180009232  nop
0x180009233  mov     rdx, [rbp+0C0h+Token+8]; Token
0x180009237  test    rdx, rdx
0x18000923a  jz      short loc_180009261
0x18000923c  xor     ecx, ecx; Thread
0x18000923e  call    cs:__imp_SetThreadToken
0x180009244  mov     rcx, [rbp+0C8h]; this
0x18000924b  test    eax, eax
0x18000924d  jnz     short loc_180009261
0x18000924f  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\WinStore\\inc\\RAI"...
0x180009256  mov     edx, 0BFh; void *
0x18000925b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180009261  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180009268  mov     [rbp+0C0h+Token], rax
0x18000926c  lea     rcx, [rbp+0C0h+Token]
0x180009270  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180009275  nop
0x180009276  jmp     short loc_18000927D
0x180009278  mov     r12, [rsp+1C0h+var_150]
0x18000927d  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x180009282  test    al, al
0x180009284  jnz     short loc_1800092FD
0x180009286  call    ?IsSandboxEnabled@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsSandboxEnabled(void)
0x18000928b  test    al, al
0x18000928d  jnz     short loc_1800092FD
0x18000928f  mov     rdx, [rsp+1C0h+pv]
0x180009294  lea     rcx, [rsp+1C0h+pv]
0x180009299  call    ?CreateUsersJSON@LicenseProxyService@@CA?AVvalue@json@web@@AEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@@Z; LicenseProxyService::CreateUsersJSON(Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &)
0x18000929e  mov     rbx, rax
0x1800092a1  xorps   xmm0, xmm0
0x1800092a4  movups  xmmword ptr [rbp+0C0h+lpString2], xmm0
0x1800092a8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000005
0x1800092b0  movdqu  xmmword ptr [rbp+0C0h+cchCount2], xmm1
0x1800092b5  movsd   xmm0, qword ptr cs:aUsers; "users"
0x1800092bd  movsd   [rbp+0C0h+lpString2], xmm0
0x1800092c2  movzx   eax, word ptr cs:aUsers+8; "s"
0x1800092c9  mov     word ptr [rbp+0C0h+lpString2+8], ax
0x1800092cd  mov     word ptr [rbp+0C0h+lpString2+0Ah], si
0x1800092d1  lea     rdx, [rbp+0C0h+lpString2]
0x1800092d5  mov     rcx, r13
0x1800092d8  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800092dd  mov     rcx, rax
0x1800092e0  mov     rdx, rbx
0x1800092e3  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800092e8  nop
0x1800092e9  lea     rcx, [rbp+0C0h+lpString2]
0x1800092ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800092f2  nop
0x1800092f3  lea     rcx, [rsp+1C0h+pv]
0x1800092f8  jmp     loc_1800093A7
0x1800092fd  xor     edx, edx
0x1800092ff  lea     rcx, [rsp+1C0h+var_168]
0x180009304  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x180009309  nop
0x18000930a  xor     edx, edx
0x18000930c  lea     rcx, [rbp+0C0h+var_130]
0x180009310  call    ?array@value@json@web@@SA?AV123@_K@Z; web::json::value::array(unsigned __int64)
0x180009315  mov     rbx, rax
0x180009318  mov     rcx, [rsp+1C0h+pv]
0x18000931d  mov     rcx, [rcx]
0x180009320  mov     rax, [rcx]
0x180009323  mov     rax, [rax+20h]
0x180009327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000932c  mov     rdx, rax
0x18000932f  lea     rcx, [rsp+1C0h+var_168]
  ... truncated ...
```
