# WinStoreAuth::AuthenticationInternal::CaptureStorePrimaryAccountTicket(HWND__ *,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *,WinStoreAuth::AccountProviderType &,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)

- ea: `0x1801e2bf0`
- end: `0x1801e3062`
- name: `?CaptureStorePrimaryAccountTicket@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUHSTRING__@@4AEAW4AccountProviderType@2@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@8@@Z`
- size: `1138`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801e8768`

## callees

- `0x1800101f4`
- `0x180010b74`
- `0x180012b48`
- `0x18007306c`
- `0x1801e2bf0`
- `0x1801e3680`
- `0x1801e3910`
- `0x1801e5270`
- `0x1801ec208`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2eb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2ec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2f5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2f74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2ff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2eb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2ec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2f5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2f74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2e33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2e33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e3016`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CaptureStorePrimaryAccountTicket(
        __int64 a1,
        __int64 a2,
        struct Windows::Security::Credentials::IWebAccount **a3,
        WinStoreAuth::AuthenticationInternal *a4,
        _QWORD *a5,
        _QWORD *a6,
        _DWORD *a7,
        __int64 a8)
{
  _QWORD *v9; // r12
  _QWORD *v10; // r13
  __int64 v11; // r15
  int CachedStorePrimaryAccount; // eax
  unsigned int v13; // ebx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64 *); // rdi
  int v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **v19; // rdx
  int TokenBroker; // eax
  void *v21; // rcx
  int v22; // esi
  unsigned int v23; // r10d
  int v24; // r8d
  int v25; // r9d
  int Tickets; // eax
  unsigned int v27; // r14d
  HSTRING *v28; // rbx
  unsigned __int64 v29; // r15
  unsigned __int64 k; // rsi
  _QWORD *v31; // rbx
  _QWORD *v32; // rcx
  HSTRING *v33; // rbx
  unsigned __int64 v34; // r14
  unsigned __int64 j; // rsi
  _QWORD *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  HSTRING *v39; // rbx
  unsigned __int64 v40; // r14
  unsigned __int64 v41; // rsi
  _QWORD *v42; // rbx
  HSTRING *v43; // rbx
  unsigned __int64 v44; // r15
  unsigned __int64 i; // r14
  _QWORD *v46; // rbx
  int v48; // [rsp+20h] [rbp-58h]
  int v49; // [rsp+20h] [rbp-58h]
  int v50; // [rsp+20h] [rbp-58h]
  unsigned __int64 v51; // [rsp+50h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v53[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  __int64 v55; // [rsp+C0h] [rbp+48h] BYREF

  v55 = a1;
  v9 = a5;
  *a5 = 0;
  v10 = a6;
  *a6 = 0;
  *a7 = 0;
  v11 = a8;
  *(_QWORD *)a8 = 0;
  a8 = 0;
  CachedStorePrimaryAccount = WinStoreAuth::AuthenticationInternal::FindCachedStorePrimaryAccount(
                                a4,
                                (struct Windows::System::IUser *)&a8,
                                a3);
  v13 = CachedStorePrimaryAccount;
  if ( CachedStorePrimaryAccount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)CachedStorePrimaryAccount,
      v48);
    goto LABEL_37;
  }
  v55 = 0;
  v14 = a8;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a8 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
  v16 = v15(v14, &v55);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v16,
      v48);
LABEL_5:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
    v13 = v17;
    goto LABEL_37;
  }
  a5 = 0;
  v18 = WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(&v55, 0, 0, (__int64)a4, &a5);
  v17 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9EA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v18,
      v49);
LABEL_8:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a5);
    goto LABEL_5;
  }
  a6 = 0;
  TokenBroker = WinStoreAuth::AuthenticationInternal::CreateTokenBroker(
                  (WinStoreAuth::AuthenticationInternal *)&a6,
                  v19);
  v17 = TokenBroker;
  if ( TokenBroker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9ED,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)TokenBroker,
      v49);
LABEL_11:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a6);
    goto LABEL_8;
  }
  v17 = 0;
  v53[0] = 0;
  pv = 0;
  v51 = 0;
  v22 = ULongLongMult(1u, 0x18u, &v51);
  if ( v22 < 0 || (v22 = CTCoAllocPolicy::Alloc(v21, v23, v51, &pv), v22 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v22,
      v49);
    v43 = (HSTRING *)pv;
    if ( pv )
    {
      v44 = v53[0];
      for ( i = 0; i < v44; v43 = (HSTRING *)pv )
      {
        WindowsDeleteString(v43[3 * i + 1]);
        v43[3 * i + 1] = 0;
        v46 = pv;
        WindowsDeleteString(*((HSTRING *)pv + 3 * i + 2));
        v46[3 * i++ + 2] = 0;
      }
      CoTaskMemFree(v43);
      pv = 0;
    }
    v53[0] = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a6);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a5);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
    v13 = v22;
  }
  else
  {
    Tickets = WinStoreAuth::AuthenticationInternal::SendTokenRequestAndGetTickets(
                (unsigned int)&a6,
                (unsigned int)&a5,
                v24,
                v25,
                v14,
                (__int64)pv,
                1,
                (__int64)v53,
                (__int64)a4,
                v11);
    v27 = Tickets;
    if ( Tickets >= 0 )
    {
      v32 = pv;
      if ( *(_DWORD *)pv == 1 )
      {
        *a7 = 1;
        v37 = v32[1];
        v32[1] = 0;
        *v9 = v37;
        v38 = *((_QWORD *)pv + 2);
        *((_QWORD *)pv + 2) = 0;
        *v10 = v38;
        v39 = (HSTRING *)pv;
        if ( pv )
        {
          v40 = v53[0];
          v41 = 0;
          if ( v53[0] )
          {
            do
            {
              WindowsDeleteString(v39[3 * v41 + 1]);
              v39[3 * v41 + 1] = 0;
              v42 = pv;
              WindowsDeleteString(*((HSTRING *)pv + 3 * v41 + 2));
              v42[3 * v41++ + 2] = 0;
              v39 = (HSTRING *)pv;
            }
            while ( v41 < v40 );
            v17 = 0;
          }
          CoTaskMemFree(v39);
          pv = 0;
        }
        v53[0] = 0;
        goto LABEL_11;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F4,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)0x8000FFFFLL,
        v50);
      v33 = (HSTRING *)pv;
      if ( pv )
      {
        v34 = v53[0];
        for ( j = 0; j < v34; v33 = (HSTRING *)pv )
        {
          WindowsDeleteString(v33[3 * j + 1]);
          v33[3 * j + 1] = 0;
          v36 = pv;
          WindowsDeleteString(*((HSTRING *)pv + 3 * j + 2));
          v36[3 * j++ + 2] = 0;
        }
        CoTaskMemFree(v33);
        pv = 0;
      }
      v53[0] = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a6);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a5);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
      v13 = -2147418113;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)Tickets,
        v50);
      v28 = (HSTRING *)pv;
      if ( pv )
      {
        v29 = v53[0];
        for ( k = 0; k < v29; v28 = (HSTRING *)pv )
        {
          WindowsDeleteString(v28[3 * k + 1]);
          v28[3 * k + 1] = 0;
          v31 = pv;
          WindowsDeleteString(*((HSTRING *)pv + 3 * k + 2));
          v31[3 * k++ + 2] = 0;
        }
        CoTaskMemFree(v28);
        pv = 0;
      }
      v53[0] = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a6);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a5);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
      v13 = v27;
    }
  }
LABEL_37:
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a8);
  return v13;
}

```

## disassembly

```asm
0x1801e2bf0  mov     [rsp-40h+arg_0], rcx
0x1801e2bf5  push    rbp
0x1801e2bf6  push    rbx
0x1801e2bf7  push    rsi
0x1801e2bf8  push    rdi
0x1801e2bf9  push    r12
0x1801e2bfb  push    r13
0x1801e2bfd  push    r14
0x1801e2bff  push    r15
0x1801e2c01  mov     rbp, rsp
0x1801e2c04  sub     rsp, 78h
0x1801e2c08  mov     r14, r9
0x1801e2c0b  xor     esi, esi
0x1801e2c0d  mov     r12, [rbp+arg_20]
0x1801e2c11  mov     [r12], rsi
0x1801e2c15  mov     r13, [rbp+arg_28]
0x1801e2c19  mov     [r13+0], rsi
0x1801e2c1d  mov     rax, [rbp+arg_30]
0x1801e2c21  mov     [rax], esi
0x1801e2c23  mov     r15, [rbp+arg_38]
0x1801e2c2a  mov     [r15], rsi
0x1801e2c2d  mov     [rbp+arg_38], rsi
0x1801e2c34  lea     rdx, [rbp+arg_38]; struct Windows::System::IUser *
0x1801e2c3b  mov     rcx, r9; this
0x1801e2c3e  call    ?FindCachedStorePrimaryAccount@AuthenticationInternal@WinStoreAuth@@YAJPEAUIUser@System@Windows@@PEAPEAUIWebAccount@Credentials@Security@5@@Z; WinStoreAuth::AuthenticationInternal::FindCachedStorePrimaryAccount(Windows::System::IUser *,Windows::Security::Credentials::IWebAccount * *)
0x1801e2c43  mov     ebx, eax
0x1801e2c45  test    eax, eax
0x1801e2c47  jns     short loc_1801E2C66
0x1801e2c49  mov     rcx, [rbp+40h]; this
0x1801e2c4d  mov     r9d, eax; char *
0x1801e2c50  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2c57  mov     edx, 9E4h; void *
0x1801e2c5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2c61  jmp     loc_1801E3043
0x1801e2c66  mov     [rbp+arg_0], rsi
0x1801e2c6a  mov     rbx, [rbp+arg_38]
0x1801e2c71  mov     rax, [rbx]
0x1801e2c74  mov     rdi, [rax+30h]
0x1801e2c78  lea     rcx, [rbp+arg_0]
0x1801e2c7c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2c81  lea     rdx, [rbp+arg_0]
0x1801e2c85  mov     rcx, rbx
0x1801e2c88  mov     rax, rdi
0x1801e2c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2c90  mov     edi, eax
0x1801e2c92  test    eax, eax
0x1801e2c94  jns     short loc_1801E2CBF
0x1801e2c96  mov     rcx, [rbp+40h]; this
0x1801e2c9a  mov     r9d, eax; char *
0x1801e2c9d  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2ca4  mov     edx, 9E7h; void *
0x1801e2ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2cae  nop
0x1801e2caf  lea     rcx, [rbp+arg_0]
0x1801e2cb3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2cb8  mov     ebx, edi
0x1801e2cba  jmp     loc_1801E3043
0x1801e2cbf  mov     [rbp+arg_20], rsi
0x1801e2cc3  lea     rax, [rbp+arg_20]
0x1801e2cc7  mov     qword ptr [rsp+78h+var_58], rax; int
0x1801e2ccc  mov     r9, r14
0x1801e2ccf  xor     r8d, r8d
0x1801e2cd2  xor     edx, edx
0x1801e2cd4  lea     rcx, [rbp+arg_0]
0x1801e2cd8  call    ?CreateTokenRequestHelper@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)
0x1801e2cdd  mov     edi, eax
0x1801e2cdf  test    eax, eax
0x1801e2ce1  jns     short loc_1801E2D07
0x1801e2ce3  mov     rcx, [rbp+40h]; this
0x1801e2ce7  mov     r9d, eax; char *
0x1801e2cea  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2cf1  mov     edx, 9EAh; void *
0x1801e2cf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2cfb  nop
0x1801e2cfc  lea     rcx, [rbp+arg_20]
0x1801e2d00  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2d05  jmp     short loc_1801E2CAF
0x1801e2d07  mov     [rbp+arg_28], rsi
0x1801e2d0b  lea     rcx, [rbp+arg_28]; this
0x1801e2d0f  call    ?CreateTokenBroker@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::CreateTokenBroker(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics * *)
0x1801e2d14  mov     edi, eax
0x1801e2d16  test    eax, eax
0x1801e2d18  jns     short loc_1801E2D3E
0x1801e2d1a  mov     rcx, [rbp+40h]; this
0x1801e2d1e  mov     r9d, eax; char *
0x1801e2d21  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2d28  mov     edx, 9EDh; void *
0x1801e2d2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2d32  nop
0x1801e2d33  lea     rcx, [rbp+arg_28]
0x1801e2d37  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2d3c  jmp     short loc_1801E2CFC
0x1801e2d3e  xor     edi, edi
0x1801e2d40  mov     [rbp+var_18], rdi
0x1801e2d44  mov     [rbp+pv], rdi
0x1801e2d48  mov     [rbp+var_28], rdi
0x1801e2d4c  lea     r8, [rbp+var_28]; unsigned __int64 *
0x1801e2d50  lea     edx, [rdi+18h]; unsigned __int64
0x1801e2d53  lea     r10d, [rdi+1]
0x1801e2d57  mov     ecx, r10d; unsigned __int64
0x1801e2d5a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801e2d5f  mov     esi, eax
0x1801e2d61  test    eax, eax
0x1801e2d63  js      loc_1801E2FA7
0x1801e2d69  lea     r9, [rbp+pv]; void **
0x1801e2d6d  mov     r8, [rbp+var_28]; unsigned __int64
0x1801e2d71  mov     edx, r10d; unsigned int
0x1801e2d74  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1801e2d79  mov     esi, eax
0x1801e2d7b  test    eax, eax
0x1801e2d7d  js      loc_1801E2FA7
0x1801e2d83  mov     [rsp+78h+var_30], r15
0x1801e2d88  mov     [rsp+78h+var_38], r14
0x1801e2d8d  lea     rax, [rbp+var_18]
0x1801e2d91  mov     [rsp+78h+var_40], rax
0x1801e2d96  lea     r15d, [rdi+1]
0x1801e2d9a  mov     [rsp+78h+var_48], r15
0x1801e2d9f  mov     rax, [rbp+pv]
0x1801e2da3  mov     [rsp+78h+var_50], rax
0x1801e2da8  mov     qword ptr [rsp+78h+var_58], rbx; int
0x1801e2dad  lea     rdx, [rbp+arg_20]
0x1801e2db1  lea     rcx, [rbp+arg_28]
0x1801e2db5  call    ?SendTokenRequestAndGetTickets@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@45@W4PromptType@2@PEAUHWND__@@PEAUIWebAccount@Credentials@Security@Windows@@PEAUTicketHolder@2@_KPEA_KPEAUIUser@System@Windows@@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::SendTokenRequestAndGetTickets(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> const &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> const &,WinStoreAuth::PromptType,HWND__ *,Windows::Security::Credentials::IWebAccount *,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x1801e2dba  mov     r14d, eax
0x1801e2dbd  test    eax, eax
0x1801e2dbf  jns     loc_1801E2E66
0x1801e2dc5  mov     rcx, [rbp+40h]; this
0x1801e2dc9  mov     r9d, eax; char *
0x1801e2dcc  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2dd3  mov     edx, 9F1h; void *
0x1801e2dd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2ddd  nop
0x1801e2dde  mov     rbx, [rbp+pv]
0x1801e2de2  test    rbx, rbx
0x1801e2de5  jz      short loc_1801E2E3D
0x1801e2de7  mov     r15, [rbp+var_18]
0x1801e2deb  mov     esi, edi
0x1801e2ded  test    r15, r15
0x1801e2df0  jz      short loc_1801E2E30
0x1801e2df2  lea     rdi, [rsi+rsi*2]
0x1801e2df6  mov     rcx, [rbx+rdi*8+8]; string
0x1801e2dfb  call    cs:__imp_WindowsDeleteString
0x1801e2e01  mov     qword ptr [rbx+rdi*8+8], 0
0x1801e2e0a  mov     rbx, [rbp+pv]
0x1801e2e0e  mov     rcx, [rbx+rdi*8+10h]; string
0x1801e2e13  call    cs:__imp_WindowsDeleteString
0x1801e2e19  mov     qword ptr [rbx+rdi*8+10h], 0
0x1801e2e22  inc     rsi
0x1801e2e25  mov     rbx, [rbp+pv]
0x1801e2e29  cmp     rsi, r15
0x1801e2e2c  jb      short loc_1801E2DF2
0x1801e2e2e  xor     edi, edi
0x1801e2e30  mov     rcx, rbx; pv
0x1801e2e33  call    cs:__imp_CoTaskMemFree
0x1801e2e39  mov     [rbp+pv], rdi
0x1801e2e3d  mov     [rbp+var_18], rdi
0x1801e2e41  lea     rcx, [rbp+arg_28]
0x1801e2e45  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2e4a  nop
0x1801e2e4b  lea     rcx, [rbp+arg_20]
0x1801e2e4f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2e54  nop
0x1801e2e55  lea     rcx, [rbp+arg_0]
0x1801e2e59  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2e5e  mov     ebx, r14d
0x1801e2e61  jmp     loc_1801E3043
0x1801e2e66  mov     rcx, [rbp+pv]
0x1801e2e6a  cmp     [rcx], r15d
0x1801e2e6d  jz      loc_1801E2F1B
0x1801e2e73  mov     rcx, [rbp+40h]; this
0x1801e2e77  mov     r12d, 8000FFFFh
0x1801e2e7d  mov     r9d, r12d; char *
0x1801e2e80  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2e87  mov     edx, 9F4h; void *
0x1801e2e8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2e91  nop
0x1801e2e92  mov     rbx, [rbp+pv]
0x1801e2e96  test    rbx, rbx
0x1801e2e99  jz      short loc_1801E2EF2
0x1801e2e9b  mov     r14, [rbp+var_18]
0x1801e2e9f  mov     rsi, rdi
0x1801e2ea2  test    r14, r14
0x1801e2ea5  jz      short loc_1801E2EE5
0x1801e2ea7  lea     rdi, [rsi+rsi*2]
0x1801e2eab  mov     rcx, [rbx+rdi*8+8]; string
0x1801e2eb0  call    cs:__imp_WindowsDeleteString
0x1801e2eb6  mov     qword ptr [rbx+rdi*8+8], 0
0x1801e2ebf  mov     rbx, [rbp+pv]
0x1801e2ec3  mov     rcx, [rbx+rdi*8+10h]; string
0x1801e2ec8  call    cs:__imp_WindowsDeleteString
0x1801e2ece  mov     qword ptr [rbx+rdi*8+10h], 0
0x1801e2ed7  add     rsi, r15
0x1801e2eda  mov     rbx, [rbp+pv]
0x1801e2ede  cmp     rsi, r14
0x1801e2ee1  jb      short loc_1801E2EA7
0x1801e2ee3  xor     edi, edi
0x1801e2ee5  mov     rcx, rbx; pv
0x1801e2ee8  call    cs:__imp_CoTaskMemFree
0x1801e2eee  mov     [rbp+pv], rdi
0x1801e2ef2  mov     [rbp+var_18], rdi
0x1801e2ef6  lea     rcx, [rbp+arg_28]
0x1801e2efa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2eff  nop
0x1801e2f00  lea     rcx, [rbp+arg_20]
0x1801e2f04  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2f09  nop
0x1801e2f0a  lea     rcx, [rbp+arg_0]
0x1801e2f0e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2f13  mov     ebx, r12d
0x1801e2f16  jmp     loc_1801E3043
0x1801e2f1b  mov     rax, [rbp+arg_30]
0x1801e2f1f  mov     [rax], r15d
0x1801e2f22  mov     rax, [rcx+8]
0x1801e2f26  mov     [rcx+8], rdi
0x1801e2f2a  mov     [r12], rax
0x1801e2f2e  mov     rcx, [rbp+pv]
0x1801e2f32  mov     rax, [rcx+10h]
0x1801e2f36  mov     [rcx+10h], rdi
0x1801e2f3a  mov     [r13+0], rax
0x1801e2f3e  mov     rbx, [rbp+pv]
0x1801e2f42  test    rbx, rbx
0x1801e2f45  jz      short loc_1801E2F9E
0x1801e2f47  mov     r14, [rbp+var_18]
0x1801e2f4b  mov     rsi, rdi
0x1801e2f4e  test    r14, r14
0x1801e2f51  jz      short loc_1801E2F91
0x1801e2f53  lea     rdi, [rsi+rsi*2]
0x1801e2f57  mov     rcx, [rbx+rdi*8+8]; string
0x1801e2f5c  call    cs:__imp_WindowsDeleteString
0x1801e2f62  mov     qword ptr [rbx+rdi*8+8], 0
0x1801e2f6b  mov     rbx, [rbp+pv]
0x1801e2f6f  mov     rcx, [rbx+rdi*8+10h]; string
0x1801e2f74  call    cs:__imp_WindowsDeleteString
0x1801e2f7a  mov     qword ptr [rbx+rdi*8+10h], 0
0x1801e2f83  add     rsi, r15
0x1801e2f86  mov     rbx, [rbp+pv]
0x1801e2f8a  cmp     rsi, r14
0x1801e2f8d  jb      short loc_1801E2F53
0x1801e2f8f  xor     edi, edi
0x1801e2f91  mov     rcx, rbx; pv
0x1801e2f94  call    cs:__imp_CoTaskMemFree
0x1801e2f9a  mov     [rbp+pv], rdi
0x1801e2f9e  mov     [rbp+var_18], rdi
0x1801e2fa2  jmp     loc_1801E2D33
0x1801e2fa7  mov     rcx, [rbp+40h]; this
0x1801e2fab  mov     r9d, esi; char *
0x1801e2fae  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2fb5  mov     edx, 9F0h; void *
0x1801e2fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2fbf  nop
0x1801e2fc0  mov     rbx, [rbp+pv]
0x1801e2fc4  test    rbx, rbx
0x1801e2fc7  jz      short loc_1801E3020
0x1801e2fc9  mov     r15, [rbp+var_18]
0x1801e2fcd  mov     r14, rdi
0x1801e2fd0  test    r15, r15
0x1801e2fd3  jz      short loc_1801E3013
0x1801e2fd5  lea     rdi, [r14+r14*2]
0x1801e2fd9  mov     rcx, [rbx+rdi*8+8]; string
0x1801e2fde  call    cs:__imp_WindowsDeleteString
0x1801e2fe4  mov     qword ptr [rbx+rdi*8+8], 0
0x1801e2fed  mov     rbx, [rbp+pv]
0x1801e2ff1  mov     rcx, [rbx+rdi*8+10h]; string
0x1801e2ff6  call    cs:__imp_WindowsDeleteString
0x1801e2ffc  mov     qword ptr [rbx+rdi*8+10h], 0
0x1801e3005  inc     r14
0x1801e3008  mov     rbx, [rbp+pv]
0x1801e300c  cmp     r14, r15
0x1801e300f  jb      short loc_1801E2FD5
0x1801e3011  xor     edi, edi
0x1801e3013  mov     rcx, rbx; pv
0x1801e3016  call    cs:__imp_CoTaskMemFree
0x1801e301c  mov     [rbp+pv], rdi
0x1801e3020  mov     [rbp+var_18], rdi
0x1801e3024  lea     rcx, [rbp+arg_28]
0x1801e3028  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e302d  nop
0x1801e302e  lea     rcx, [rbp+arg_20]
0x1801e3032  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e3037  nop
0x1801e3038  lea     rcx, [rbp+arg_0]
0x1801e303c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e3041  mov     ebx, esi
0x1801e3043  lea     rcx, [rbp+arg_38]
0x1801e304a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e304f  mov     eax, ebx
0x1801e3051  add     rsp, 78h
0x1801e3055  pop     r15
0x1801e3057  pop     r14
0x1801e3059  pop     r13
0x1801e305b  pop     r12
0x1801e305d  pop     rdi
0x1801e305e  pop     rsi
0x1801e305f  pop     rbx
0x1801e3060  pop     rbp
0x1801e3061  retn
```
