# ConnectedStorage::UserManager::GetAuthHeaderForUser(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)

- ea: `0x18002b0b0`
- end: `0x18002b5a3`
- name: `?GetAuthHeaderForUser@UserManager@ConnectedStorage@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVSimpleHStringWrapper@2@00@Z`
- size: `1267`
- prototype: `__int64 __usercall@<rax>(ConnectedStorage::UserManager *this@<rcx>, struct ConnectedStorage::SimpleHStringWrapper *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180010e6c`
- `0x180012c98`
- `0x1800136e8`
- `0x18001c090`
- `0x18001c63c`
- `0x180020084`
- `0x180020898`
- `0x180022dec`
- `0x1800294dc`
- `0x1800298cc`
- `0x180029e84`
- `0x18002ad94`
- `0x18002afdc`
- `0x18002b0b0`
- `0x18002c358`
- `0x18002d880`
- `0x18002da8c`
- `0x180085038`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b2ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b2ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b139`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b139`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b2c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b2d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b2c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b2d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002b34d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002b4bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002b34d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002b4bb`

## string_xrefs

- `0x18002b143`: `CoCreateInstance( __uuidof(XblAuthManager), nullptr, CLSCTX_LOCAL_SERVER, IID_PPV_ARGS(&authManager))`
- `0x18002b3b8`: `GetTokenAndSignatureByUserContextToken`
- `0x18002b3cf`: `GetTokenAndSignatureByUserContextToken succeeded but returned null token`
- `0x18002b516`: `GetAccessTokenAndPKSignature`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ConnectedStorage::UserManager::GetAuthHeaderForUser(
        ConnectedStorage::UserManager *this,
        __int64 a2,
        HSTRING *a3,
        IUnknown *a4,
        struct ConnectedStorage::SimpleHStringWrapper *a5)
{
  __int64 v6; // r15
  HRESULT v8; // eax
  const unsigned __int16 *v9; // r8
  ConnectedStorage *v10; // rcx
  char *v11; // r8
  char v12; // si
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // r8
  HSTRING *AddressOf; // rbx
  HSTRING *v17; // rax
  HSTRING *v18; // r8
  unsigned __int64 v19; // rbx
  __int64 AuthHeaderForCachedUser; // rax
  const unsigned __int16 *v21; // r8
  struct IUnknown *v22; // rdx
  ConnectedStorage *v23; // rcx
  unsigned __int64 v24; // rsi
  LPVOID v25; // rdi
  __int64 (__fastcall *v26)(LPVOID, unsigned __int64, unsigned __int64, const wchar_t *, PCWSTR, const WCHAR *, _QWORD, _DWORD, __int64 *, __int64 *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v28; // eax
  const unsigned __int16 *v29; // r8
  ConnectedStorage::ScopedCallContext *p_ppOldObject; // rcx
  ConnectedStorage *v31; // rcx
  __int64 v32; // rax
  struct IUnknown *v33; // rdx
  LPVOID v34; // rdi
  __int64 (__fastcall *v35)(LPVOID, _QWORD, const wchar_t *, const wchar_t *, PCWSTR, const WCHAR *, _QWORD, _DWORD, __int64 *, __int64 *); // rbx
  PCWSTR v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // r8
  __int64 v40; // [rsp+60h] [rbp-128h] BYREF
  __int64 v41; // [rsp+68h] [rbp-120h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-118h] BYREF
  HSTRING v43; // [rsp+78h] [rbp-110h] BYREF
  HSTRING string; // [rsp+80h] [rbp-108h] BYREF
  unsigned __int64 v45; // [rsp+88h] [rbp-100h] BYREF
  int v46; // [rsp+90h] [rbp-F8h]
  __int64 v47; // [rsp+98h] [rbp-F0h]
  IUnknown *ppOldObject; // [rsp+A0h] [rbp-E8h] BYREF
  HSTRING *v49; // [rsp+A8h] [rbp-E0h]
  _BYTE v50[8]; // [rsp+B0h] [rbp-D8h] BYREF
  _BYTE v51[8]; // [rsp+B8h] [rbp-D0h] BYREF
  _QWORD v52[4]; // [rsp+C0h] [rbp-C8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[4]; // [rsp+E0h] [rbp-A8h] BYREF
  _BYTE v54[64]; // [rsp+100h] [rbp-88h] BYREF

  ppOldObject = a4;
  v6 = a2;
  v49 = a3;
  v47 = a2;
  v46 = 1;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  v8 = CoCreateInstance(
         &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
         0,
         4u,
         &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
         &ppv);
  if ( v8 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v8,
      (int)L"CoCreateInstance( __uuidof(XblAuthManager), nullptr, CLSCTX_LOCAL_SERVER, IID_PPV_ARGS(&authManager))",
      v9);
  v40 = 0;
  v41 = 0;
  std::wstring::wstring(v6);
  v46 = 1;
  if ( (*(unsigned __int8 (__fastcall **)(ConnectedStorage::UserManager *, IUnknown *, struct ConnectedStorage::SimpleHStringWrapper *))(*(_QWORD *)this + 32LL))(
         this,
         a4,
         a5) )
  {
    v12 = 0;
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 168),
      v11);
    std::vector<ConnectedStorage::BlobRecord>::end((char *)this + 216, v50);
    v14 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v13, v51);
    v52[0] = a4;
    v52[1] = a5;
    std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ConnectedStorage::UserManager::UserInfo_______lambda_a717a87f1fe21e15a1e5700b403a2f5e___(
      &v45,
      *v14,
      v15,
      v52);
    v45 = *(_QWORD *)v45;
    v43 = 0;
    string = 0;
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&string);
    v17 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v43);
    v18 = AddressOf;
    v19 = v45;
    ConnectedStorage::UserManager::GetUserSidAndXuidFromContext(v45, v17, v18);
    if ( (unsigned int)ConnectedStorage::SimpleHStringWrapper::Compare(
                         (ConnectedStorage::SimpleHStringWrapper *)&string,
                         a5) )
    {
      ConnectedStorage::UserManager::FireUserSignOut(this, v19);
      AuthHeaderForCachedUser = ConnectedStorage::UserManager::GetAuthHeaderForCachedUser(this, v52, a4, a5);
      std::wstring::operator=(v6, AuthHeaderForCachedUser);
      std::wstring::_Tidy_deallocate(v52);
      if ( !*(_QWORD *)(v6 + 16) )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x8083000DLL, (int)L"GamerAccount Changed", v21);
      v12 = 1;
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v43);
    v43 = 0;
    LeaveCriticalSection(lpCriticalSection[0]);
    if ( !v12 )
    {
      ConnectedStorage::ScopedCallContext::ScopedCallContext((IUnknown **)&v43, v22);
      v24 = (unsigned __int64)L"49312658" & -(__int64)ConnectedStorage::IsRunningOnConsole(v23);
      v25 = ppv;
      v26 = *(__int64 (__fastcall **)(LPVOID, unsigned __int64, unsigned __int64, const wchar_t *, PCWSTR, const WCHAR *, _QWORD, _DWORD, __int64 *, __int64 *))(*(_QWORD *)ppv + 464LL);
      ConnectedStorage::TaskMem<unsigned short>::Release(&v41);
      ConnectedStorage::TaskMem<unsigned short>::Release(&v40);
      StringRawBuffer = WindowsGetStringRawBuffer(*v49, 0);
      v28 = v26(v25, v45, v24, L"GET", StringRawBuffer, &dword_1800983B4, 0, 0, &v40, &v41);
      if ( v28 == -2015559661 )
      {
        v28 = -2138890239;
        goto LABEL_12;
      }
      if ( v28 < 0 )
LABEL_12:
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)v28,
          (int)L"GetTokenAndSignatureByUserContextToken",
          v29);
      if ( !v40 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)0x8000FFFFLL,
          (int)L"GetTokenAndSignatureByUserContextToken succeeded but returned null token",
          v29);
      std::wstring::append(v6, L"Authorization: ");
      std::wstring::append(v6, v40);
      std::wstring::append(v6, L"\r\n");
      ConnectedStorage::UserManager::UpdateAuthHeaderCache(this, ppOldObject, a5, v6);
      p_ppOldObject = (ConnectedStorage::ScopedCallContext *)&v43;
      goto LABEL_21;
    }
  }
  else
  {
    if ( !ConnectedStorage::IsRunningOnConsole(v10) )
    {
      try
      {
        v32 = ConnectedStorage::UserManager::GetAuthHeaderForCachedUser(this, lpCriticalSection, a4, a5);
        std::wstring::operator=(v6, v32);
        std::wstring::_Tidy_deallocate(lpCriticalSection);
      }
      catch ( ConnectedStorage::ComError v54 )
      {
        ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v54);
        v6 = v47;
      }
      catch ( std::bad_alloc )
      {
        v6 = v47;
      }
      catch ( ... )
      {
        v6 = v47;
      }
    }
    if ( ConnectedStorage::IsRunningOnConsole(v31) )
    {
      ConnectedStorage::ScopedCallContext::ScopedCallContext(&ppOldObject, v33);
      v34 = ppv;
      v35 = *(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, const wchar_t *, PCWSTR, const WCHAR *, _QWORD, _DWORD, __int64 *, __int64 *))(*(_QWORD *)ppv + 104LL);
      ConnectedStorage::TaskMem<unsigned short>::Release(&v41);
      ConnectedStorage::TaskMem<unsigned short>::Release(&v40);
      v36 = WindowsGetStringRawBuffer(*v49, 0);
      v37 = v35(v34, 0, L"49312658", L"GET", v36, &dword_1800983B4, 0, 0, &v40, &v41);
      if ( v37 < 0 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)v37,
          (int)L"GetAccessTokenAndPKSignature",
          v38);
      std::wstring::append(v6, L"Authorization: ");
      std::wstring::append(v6, v40);
      std::wstring::append(v6, L"\r\n");
      p_ppOldObject = (ConnectedStorage::ScopedCallContext *)&ppOldObject;
LABEL_21:
      ConnectedStorage::ScopedCallContext::~ScopedCallContext(p_ppOldObject);
    }
  }
  ConnectedStorage::TaskMem<unsigned short>::Release(&v41);
  ConnectedStorage::TaskMem<unsigned short>::Release(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return v6;
}

```

## disassembly

```asm
0x18002b0b0  push    rbx
0x18002b0b2  push    rsi
0x18002b0b3  push    rdi
0x18002b0b4  push    r12
0x18002b0b6  push    r13
0x18002b0b8  push    r15
0x18002b0ba  sub     rsp, 158h
0x18002b0c1  mov     rax, cs:__security_cookie
0x18002b0c8  xor     rax, rsp
0x18002b0cb  mov     [rsp+188h+var_48], rax
0x18002b0d3  mov     rdi, r9
0x18002b0d6  mov     [rsp+188h+ppOldObject], r9
0x18002b0de  mov     r15, rdx
0x18002b0e1  mov     r12, rcx
0x18002b0e4  mov     [rsp+188h+var_E0], r8
0x18002b0ec  mov     [rsp+188h+var_F0], rdx
0x18002b0f4  mov     r13, [rsp+188h+arg_20]
0x18002b0fc  mov     ebx, 1
0x18002b101  mov     [rsp+188h+var_F8], ebx
0x18002b108  mov     [rsp+188h+var_118], 0
0x18002b111  lea     rcx, [rsp+188h+var_118]
0x18002b116  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b11b  lea     rax, [rsp+188h+var_118]
0x18002b120  mov     [rsp+188h+ppv], rax; ppv
0x18002b125  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x18002b12c  xor     edx, edx; pUnkOuter
0x18002b12e  lea     r8d, [rbx+3]; dwClsContext
0x18002b132  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x18002b139  call    cs:__imp_CoCreateInstance
0x18002b13f  test    eax, eax
0x18002b141  jns     short loc_18002B152
0x18002b143  lea     rdx, aCocreateinstan_0; "CoCreateInstance( __uuidof(XblAuthManag"...
0x18002b14a  mov     ecx, eax; this
0x18002b14c  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b152  mov     [rsp+188h+var_128], 0
0x18002b15b  mov     [rsp+188h+var_120], 0
0x18002b164  mov     rcx, r15
0x18002b167  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b16c  nop
0x18002b16d  mov     [rsp+188h+var_F8], ebx
0x18002b174  mov     rax, [r12]
0x18002b178  mov     r8, r13
0x18002b17b  mov     rdx, rdi
0x18002b17e  mov     rcx, r12
0x18002b181  mov     rax, [rax+20h]
0x18002b185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b18a  test    al, al
0x18002b18c  jz      loc_18002B42D
0x18002b192  xor     sil, sil
0x18002b195  lea     rdx, [r12+0A8h]; struct ConnectedStorage::Mutex *
0x18002b19d  lea     rcx, [rsp+188h+lpCriticalSection]; this
0x18002b1a5  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18002b1aa  nop
0x18002b1ab  lea     rcx, [r12+0D8h]
0x18002b1b3  lea     rdx, [rsp+188h+var_D8]
0x18002b1bb  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002b1c0  mov     r8, [rax]
0x18002b1c3  lea     rdx, [rsp+188h+var_D0]
0x18002b1cb  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002b1d0  mov     [rsp+188h+var_C8], rdi
0x18002b1d8  mov     [rsp+188h+var_C0], r13
0x18002b1e0  lea     r9, [rsp+188h+var_C8]
0x18002b1e8  mov     rdx, [rax]
0x18002b1eb  lea     rcx, [rsp+188h+var_100]
0x18002b1f3  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ConnectedStorage__UserManager__UserInfo_______lambda_a717a87f1fe21e15a1e5700b403a2f5e___
0x18002b1f8  mov     rax, [rsp+188h+var_100]
0x18002b200  mov     rax, [rax]
0x18002b203  mov     [rsp+188h+var_100], rax
0x18002b20b  mov     [rsp+188h+var_110], 0
0x18002b214  mov     [rsp+188h+string], 0
0x18002b220  lea     rcx, [rsp+188h+string]; this
0x18002b228  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002b22d  mov     rbx, rax
0x18002b230  lea     rcx, [rsp+188h+var_110]; this
0x18002b235  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002b23a  mov     r8, rbx; HSTRING *
0x18002b23d  mov     rdx, rax; HSTRING *
0x18002b240  mov     rbx, [rsp+188h+var_100]
0x18002b248  mov     rcx, rbx; unsigned __int64
0x18002b24b  call    ?GetUserSidAndXuidFromContext@UserManager@ConnectedStorage@@SAX_KPEAPEAUHSTRING__@@1@Z; ConnectedStorage::UserManager::GetUserSidAndXuidFromContext(unsigned __int64,HSTRING__ * *,HSTRING__ * *)
0x18002b250  mov     rdx, r13; struct ConnectedStorage::SimpleHStringWrapper *
0x18002b253  lea     rcx, [rsp+188h+string]; this
0x18002b25b  call    ?Compare@SimpleHStringWrapper@ConnectedStorage@@QEBAHAEBV12@@Z; ConnectedStorage::SimpleHStringWrapper::Compare(ConnectedStorage::SimpleHStringWrapper const &)
0x18002b260  test    eax, eax
0x18002b262  jz      short loc_18002B2B9
0x18002b264  mov     rdx, rbx; unsigned __int64
0x18002b267  mov     rcx, r12; this
0x18002b26a  call    ?FireUserSignOut@UserManager@ConnectedStorage@@AEBAX_K@Z; ConnectedStorage::UserManager::FireUserSignOut(unsigned __int64)
0x18002b26f  mov     r9, r13
0x18002b272  mov     r8, rdi
0x18002b275  lea     rdx, [rsp+188h+var_C8]
0x18002b27d  mov     rcx, r12
0x18002b280  call    ?GetAuthHeaderForCachedUser@UserManager@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVSimpleHStringWrapper@2@0@Z; ConnectedStorage::UserManager::GetAuthHeaderForCachedUser(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x18002b285  mov     rdx, rax
0x18002b288  mov     rcx, r15
0x18002b28b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b290  lea     rcx, [rsp+188h+var_C8]
0x18002b298  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b29d  cmp     qword ptr [r15+10h], 0
0x18002b2a2  jnz     short loc_18002B2B6
0x18002b2a4  lea     rdx, aGameraccountCh_0; "GamerAccount Changed"
0x18002b2ab  mov     ecx, 8083000Dh; this
0x18002b2b0  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b2b6  mov     sil, 1
0x18002b2b9  mov     rcx, [rsp+188h+string]; string
0x18002b2c1  call    cs:__imp_WindowsDeleteString
0x18002b2c7  mov     [rsp+188h+string], 0
0x18002b2d3  mov     rcx, [rsp+188h+var_110]; string
0x18002b2d8  call    cs:__imp_WindowsDeleteString
0x18002b2de  mov     [rsp+188h+var_110], 0
0x18002b2e7  mov     rcx, [rsp+188h+lpCriticalSection]; lpCriticalSection
0x18002b2ef  call    cs:__imp_LeaveCriticalSection
0x18002b2f5  test    sil, sil
0x18002b2f8  jnz     loc_18002B55F
0x18002b2fe  lea     rcx, [rsp+188h+var_110]; ppOldObject
0x18002b303  call    ??0ScopedCallContext@ConnectedStorage@@QEAA@PEAUIUnknown@@@Z; ConnectedStorage::ScopedCallContext::ScopedCallContext(IUnknown *)
0x18002b308  nop
0x18002b309  call    ?IsRunningOnConsole@ConnectedStorage@@YA_NXZ; ConnectedStorage::IsRunningOnConsole(void)
0x18002b30e  lea     r8, a49312658; "49312658"
0x18002b315  neg     al
0x18002b317  sbb     rsi, rsi
0x18002b31a  and     rsi, r8
0x18002b31d  mov     rdi, [rsp+188h+var_118]
0x18002b322  mov     rax, [rdi]
0x18002b325  mov     rbx, [rax+1D0h]
0x18002b32c  lea     rcx, [rsp+188h+var_120]
0x18002b331  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002b336  lea     rcx, [rsp+188h+var_128]
0x18002b33b  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002b340  xor     edx, edx; length
0x18002b342  mov     rcx, [rsp+188h+var_E0]
0x18002b34a  mov     rcx, [rcx]; string
0x18002b34d  call    cs:__imp_WindowsGetStringRawBuffer
0x18002b353  lea     rcx, [rsp+188h+var_120]
0x18002b358  mov     [rsp+188h+var_140], rcx
0x18002b35d  lea     rcx, [rsp+188h+var_128]
0x18002b362  mov     [rsp+188h+var_148], rcx
0x18002b367  mov     [rsp+188h+var_150], 0
0x18002b36f  mov     [rsp+188h+var_158], 0
0x18002b378  lea     rcx, dword_1800983B4
0x18002b37f  mov     [rsp+188h+var_160], rcx
0x18002b384  mov     [rsp+188h+ppv], rax
0x18002b389  lea     r9, aGet; "GET"
0x18002b390  mov     r8, rsi
0x18002b393  mov     rdx, [rsp+188h+var_100]
0x18002b39b  mov     rcx, rdi
0x18002b39e  mov     rax, rbx
0x18002b3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3a6  cmp     eax, 87DD0013h
0x18002b3ab  jnz     short loc_18002B3B4
0x18002b3ad  mov     eax, 80832001h
0x18002b3b2  jmp     short loc_18002B3B8
0x18002b3b4  test    eax, eax
0x18002b3b6  jns     short loc_18002B3C7
0x18002b3b8  lea     rdx, aGettokenandsig_0; "GetTokenAndSignatureByUserContextToken"
0x18002b3bf  mov     ecx, eax; this
0x18002b3c1  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b3c7  cmp     [rsp+188h+var_128], 0
0x18002b3cd  jnz     short loc_18002B3E1
0x18002b3cf  lea     rdx, aGettokenandsig; "GetTokenAndSignatureByUserContextToken "...
0x18002b3d6  mov     ecx, 8000FFFFh; this
0x18002b3db  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b3e1  lea     rdx, aAuthorization; "Authorization: "
0x18002b3e8  mov     rcx, r15
0x18002b3eb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b3f0  mov     rdx, [rsp+188h+var_128]
0x18002b3f5  mov     rcx, r15
0x18002b3f8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b3fd  lea     rdx, SubStr; "\r\n"
0x18002b404  mov     rcx, r15
0x18002b407  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b40c  mov     r9, r15
0x18002b40f  mov     r8, r13
0x18002b412  mov     rdx, [rsp+188h+ppOldObject]
0x18002b41a  mov     rcx, r12
0x18002b41d  call    ?UpdateAuthHeaderCache@UserManager@ConnectedStorage@@AEBAXAEBVSimpleHStringWrapper@2@0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::UserManager::UpdateAuthHeaderCache(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::wstring &)
0x18002b422  nop
0x18002b423  lea     rcx, [rsp+188h+var_110]
0x18002b428  jmp     loc_18002B559
0x18002b42d  call    ?IsRunningOnConsole@ConnectedStorage@@YA_NXZ; ConnectedStorage::IsRunningOnConsole(void)
0x18002b432  test    al, al
0x18002b434  jnz     short loc_18002B473
0x18002b436  mov     r9, r13
0x18002b439  mov     r8, rdi
0x18002b43c  lea     rdx, [rsp+188h+lpCriticalSection]
0x18002b444  mov     rcx, r12
0x18002b447  call    ?GetAuthHeaderForCachedUser@UserManager@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVSimpleHStringWrapper@2@0@Z; ConnectedStorage::UserManager::GetAuthHeaderForCachedUser(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x18002b44c  mov     rdx, rax
0x18002b44f  mov     rcx, r15
0x18002b452  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b457  lea     rcx, [rsp+188h+lpCriticalSection]
0x18002b45f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b464  nop
0x18002b465  jmp     short loc_18002B473
0x18002b467  jmp     short loc_18002B46B
0x18002b469  jmp     short $+2
0x18002b46b  mov     r15, [rsp+188h+var_F0]
0x18002b473  call    ?IsRunningOnConsole@ConnectedStorage@@YA_NXZ; ConnectedStorage::IsRunningOnConsole(void)
0x18002b478  test    al, al
0x18002b47a  jz      loc_18002B55F
0x18002b480  lea     rcx, [rsp+188h+ppOldObject]; ppOldObject
0x18002b488  call    ??0ScopedCallContext@ConnectedStorage@@QEAA@PEAUIUnknown@@@Z; ConnectedStorage::ScopedCallContext::ScopedCallContext(IUnknown *)
0x18002b48d  nop
0x18002b48e  mov     rdi, [rsp+188h+var_118]
0x18002b493  mov     rax, [rdi]
0x18002b496  mov     rbx, [rax+68h]
0x18002b49a  lea     rcx, [rsp+188h+var_120]
0x18002b49f  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002b4a4  lea     rcx, [rsp+188h+var_128]
0x18002b4a9  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002b4ae  xor     edx, edx; length
0x18002b4b0  mov     rcx, [rsp+188h+var_E0]
0x18002b4b8  mov     rcx, [rcx]; string
0x18002b4bb  call    cs:__imp_WindowsGetStringRawBuffer
0x18002b4c1  lea     rcx, [rsp+188h+var_120]
0x18002b4c6  mov     [rsp+188h+var_140], rcx
0x18002b4cb  lea     rcx, [rsp+188h+var_128]
0x18002b4d0  mov     [rsp+188h+var_148], rcx
0x18002b4d5  mov     [rsp+188h+var_150], 0
0x18002b4dd  mov     [rsp+188h+var_158], 0
0x18002b4e6  lea     rcx, dword_1800983B4
0x18002b4ed  mov     [rsp+188h+var_160], rcx
0x18002b4f2  mov     [rsp+188h+ppv], rax
0x18002b4f7  lea     r9, aGet; "GET"
0x18002b4fe  lea     r8, a49312658; "49312658"
0x18002b505  xor     edx, edx
0x18002b507  mov     rcx, rdi
0x18002b50a  mov     rax, rbx
0x18002b50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b512  test    eax, eax
0x18002b514  jns     short loc_18002B525
0x18002b516  lea     rdx, aGetaccesstoken; "GetAccessTokenAndPKSignature"
0x18002b51d  mov     ecx, eax; this
0x18002b51f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b525  lea     rdx, aAuthorization; "Authorization: "
0x18002b52c  mov     rcx, r15
0x18002b52f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b534  mov     rdx, [rsp+188h+var_128]
0x18002b539  mov     rcx, r15
0x18002b53c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b541  lea     rdx, SubStr; "\r\n"
0x18002b548  mov     rcx, r15
0x18002b54b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b550  nop
0x18002b551  lea     rcx, [rsp+188h+ppOldObject]; this
0x18002b559  call    ??1ScopedCallContext@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ScopedCallContext::~ScopedCallContext(void)
0x18002b55e  nop
0x18002b55f  lea     rcx, [rsp+188h+var_120]
0x18002b564  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002b569  nop
0x18002b56a  lea     rcx, [rsp+188h+var_128]
0x18002b56f  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002b574  nop
0x18002b575  lea     rcx, [rsp+188h+var_118]
0x18002b57a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b57f  mov     rax, r15
0x18002b582  mov     rcx, [rsp+188h+var_48]
0x18002b58a  xor     rcx, rsp; StackCookie
0x18002b58d  call    __security_check_cookie
0x18002b592  add     rsp, 158h
0x18002b599  pop     r15
0x18002b59b  pop     r13
0x18002b59d  pop     r12
0x18002b59f  pop     rdi
0x18002b5a0  pop     rsi
0x18002b5a1  pop     rbx
0x18002b5a2  retn
```
