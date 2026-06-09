# KeyMachine::DoesUserHaveLinkedWebAccountHelper(IXblAuthManager *,unsigned __int64,ushort const *,ushort const *,int *)

- ea: `0x180059460`
- end: `0x18005975b`
- name: `?DoesUserHaveLinkedWebAccountHelper@KeyMachine@@KAJPEAUIXblAuthManager@@_KPEBG2PEAH@Z`
- size: `763`
- prototype: `__int64 __fastcall(struct IXblAuthManager *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180087268`

## callees

- `0x180004738`
- `0x18000b7a4`
- `0x180035afc`
- `0x18003dab0`
- `0x1800593bc`
- `0x180059460`
- `0x180075e60`
- `0x180084664`
- `0x180084a50`
- `0x180084be0`
- `0x180085084`
- `0x1800853a0`
- `0x1800b8010`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18005953a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18005953a`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x1800594a2`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x1800594a2`

## string_xrefs

- `0x18005957d`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x180059497`: `https://login.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall KeyMachine::DoesUserHaveLinkedWebAccountHelper(
        struct IXblAuthManager *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int *a5)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, _QWORD, __int64 *); // rbx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  int v23; // [rsp+20h] [rbp-61h]
  __int64 v24; // [rsp+30h] [rbp-51h] BYREF
  __int64 v25; // [rsp+38h] [rbp-49h] BYREF
  __int64 v26; // [rsp+40h] [rbp-41h] BYREF
  __int64 v27; // [rsp+48h] [rbp-39h] BYREF
  __int64 v28; // [rsp+50h] [rbp-31h] BYREF
  void **v29; // [rsp+58h] [rbp-29h] BYREF
  __int64 v30; // [rsp+60h] [rbp-21h] BYREF
  const WCHAR *v31; // [rsp+68h] [rbp-19h] BYREF
  const unsigned __int16 *v32; // [rsp+70h] [rbp-11h] BYREF
  _BYTE v33[16]; // [rsp+78h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+7h] BYREF
  __int64 v35; // [rsp+A0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v32 = a3;
  v31 = L"https://login.microsoft.com";
  if ( (unsigned int)XblaIsConsole(a1) )
    return (*(__int64 (__fastcall **)(struct IXblAuthManager *, __int64, const unsigned __int16 *, const WCHAR *, int *))(*(_QWORD *)a1 + 544LL))(
             a1,
             a2,
             a3,
             L"https://login.microsoft.com",
             a5);
  if ( !a5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x581,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)0x80004003LL,
      v23);
  *a5 = 0;
  v26 = 0;
  v25 = 0;
  v28 = 0;
  v24 = 0;
  v27 = 0;
  v29 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  v30 = 0;
  v9 = UMgrQueryUserToken(a2, &v30);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x58C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v9,
      v23);
  ImpersonateContext::ImpersonateContext((__int64)v33, (__int64)&v29);
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
          v35,
          &v26);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x58F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v10,
      v23);
  v11 = v26;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 88LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v31);
  v14 = v12(v11, *(_QWORD *)(v13 + 24), &v25);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x590,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v14,
      v23);
  v15 = v25;
  v16 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(v25);
  if ( v16 >= 0 )
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, &v28);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x591,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v16,
      v23);
  v17 = v26;
  v18 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 80LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v32);
  v20 = v18(v17, v28, *(_QWORD *)(v19 + 24), &v24);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x592,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v20,
      v23);
  v21 = v24;
  v22 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(v24);
  if ( v22 >= 0 )
    v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 64LL))(v21, &v27);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x593,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v22,
      v23);
  if ( v27 )
    *a5 = 1;
  ImpersonateContext::~ImpersonateContext((ImpersonateContext *)v33);
  v29 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v29);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
  return 0;
}

```

## disassembly

```asm
0x180059460  mov     [rsp-8+arg_18], rbx
0x180059465  push    rbp
0x180059466  push    rsi
0x180059467  push    rdi
0x180059468  push    r12
0x18005946a  push    r14
0x18005946c  lea     rbp, [rsp-2Fh]
0x180059471  sub     rsp, 0B0h
0x180059478  mov     rax, cs:__security_cookie
0x18005947f  xor     rax, rsp
0x180059482  mov     [rbp+4Fh+var_28], rax
0x180059486  mov     r14, r8
0x180059489  mov     rbx, rdx
0x18005948c  mov     rdi, rcx
0x18005948f  mov     [rbp+4Fh+var_60], r8
0x180059493  mov     rsi, [rbp+4Fh+arg_20]
0x180059497  lea     r12, aHttpsLoginMicr; "https://login.microsoft.com"
0x18005949e  mov     [rbp+4Fh+var_68], r12
0x1800594a2  call    cs:__imp_XblaIsConsole
0x1800594a8  test    eax, eax
0x1800594aa  jz      short loc_1800594D1
0x1800594ac  mov     rax, [rdi]
0x1800594af  mov     qword ptr [rsp+0D0h+var_B0], rsi
0x1800594b4  mov     r9, r12
0x1800594b7  mov     r8, r14
0x1800594ba  mov     rdx, rbx
0x1800594bd  mov     rcx, rdi
0x1800594c0  mov     rax, [rax+220h]
0x1800594c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594cc  jmp     loc_180059738
0x1800594d1  test    rsi, rsi
0x1800594d4  jnz     short loc_1800594F2
0x1800594d6  mov     rcx, [rbp+57h]; this
0x1800594da  mov     r9d, 80004003h; char *
0x1800594e0  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800594e7  mov     edx, 581h; void *
0x1800594ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800594f2  mov     dword ptr [rsi], 0
0x1800594f8  mov     [rbp+4Fh+var_90], 0
0x180059500  mov     [rbp+4Fh+var_98], 0
0x180059508  mov     [rbp+4Fh+var_80], 0
0x180059510  mov     [rbp+4Fh+var_A0], 0
0x180059518  mov     [rbp+4Fh+var_88], 0
0x180059520  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180059527  mov     [rbp+4Fh+var_78], r14
0x18005952b  mov     [rbp+4Fh+var_70], 0
0x180059533  lea     rdx, [rbp+4Fh+var_70]
0x180059537  mov     rcx, rbx
0x18005953a  call    cs:__imp_UMgrQueryUserToken
0x180059540  mov     rcx, [rbp+57h]; this
0x180059544  test    eax, eax
0x180059546  jns     short loc_18005955D
0x180059548  mov     r9d, eax; char *
0x18005954b  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180059552  mov     edx, 58Ch; void *
0x180059557  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005955d  lea     rdx, [rbp+4Fh+var_78]
0x180059561  lea     rcx, [rbp+4Fh+var_58]
0x180059565  call    ??0ImpersonateContext@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; ImpersonateContext::ImpersonateContext(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x18005956a  nop
0x18005956b  mov     [rbp+4Fh+var_30], 0
0x180059573  mov     r9d, 45h ; 'E'; unsigned int
0x180059579  lea     r8d, [r9+1]; unsigned int
0x18005957d  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180059584  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x180059588  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005958d  nop
0x18005958e  lea     rdx, [rbp+4Fh+var_90]
0x180059592  mov     rcx, [rbp+4Fh+var_30]
0x180059596  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x18005959b  mov     rcx, [rbp+57h]; this
0x18005959f  test    eax, eax
0x1800595a1  jns     short loc_1800595B8
0x1800595a3  mov     r9d, eax; char *
0x1800595a6  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800595ad  mov     edx, 58Fh; void *
0x1800595b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800595b8  mov     rdi, [rbp+4Fh+var_90]
0x1800595bc  mov     rax, [rdi]
0x1800595bf  mov     rbx, [rax+58h]
0x1800595c3  lea     rcx, [rbp+4Fh+var_98]
0x1800595c7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800595cc  lea     rdx, [rbp+4Fh+var_68]
0x1800595d0  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800595d4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800595d9  nop
0x1800595da  lea     r8, [rbp+4Fh+var_98]
0x1800595de  mov     rdx, [rax+18h]
0x1800595e2  mov     rcx, rdi
0x1800595e5  mov     rax, rbx
0x1800595e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595ed  mov     rcx, [rbp+57h]; this
0x1800595f1  test    eax, eax
0x1800595f3  jns     short loc_18005960A
0x1800595f5  mov     r9d, eax; char *
0x1800595f8  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800595ff  mov     edx, 590h; void *
0x180059604  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005960a  mov     rbx, [rbp+4Fh+var_98]
0x18005960e  mov     rcx, rbx
0x180059611  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x180059616  test    eax, eax
0x180059618  js      short loc_18005962D
0x18005961a  mov     rax, [rbx]
0x18005961d  lea     rdx, [rbp+4Fh+var_80]
0x180059621  mov     rcx, rbx
0x180059624  mov     rax, [rax+40h]
0x180059628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005962d  mov     rcx, [rbp+57h]; this
0x180059631  test    eax, eax
0x180059633  jns     short loc_18005964A
0x180059635  mov     r9d, eax; char *
0x180059638  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005963f  mov     edx, 591h; void *
0x180059644  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005964a  mov     rdi, [rbp+4Fh+var_90]
0x18005964e  mov     rax, [rdi]
0x180059651  mov     rbx, [rax+50h]
0x180059655  lea     rcx, [rbp+4Fh+var_A0]
0x180059659  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005965e  lea     rdx, [rbp+4Fh+var_60]
0x180059662  lea     rcx, [rbp+4Fh+hstringHeader]
0x180059666  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005966b  nop
0x18005966c  lea     r9, [rbp+4Fh+var_A0]
0x180059670  mov     r8, [rax+18h]
0x180059674  mov     rdx, [rbp+4Fh+var_80]
0x180059678  mov     rcx, rdi
0x18005967b  mov     rax, rbx
0x18005967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059683  mov     rcx, [rbp+57h]; this
0x180059687  test    eax, eax
0x180059689  jns     short loc_1800596A0
0x18005968b  mov     r9d, eax; char *
0x18005968e  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180059695  mov     edx, 592h; void *
0x18005969a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800596a0  mov     rbx, [rbp+4Fh+var_A0]
0x1800596a4  mov     rcx, rbx
0x1800596a7  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)
0x1800596ac  test    eax, eax
0x1800596ae  js      short loc_1800596C3
0x1800596b0  mov     rax, [rbx]
0x1800596b3  lea     rdx, [rbp+4Fh+var_88]
0x1800596b7  mov     rcx, rbx
0x1800596ba  mov     rax, [rax+40h]
0x1800596be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596c3  mov     rcx, [rbp+57h]; this
0x1800596c7  test    eax, eax
0x1800596c9  jns     short loc_1800596E0
0x1800596cb  mov     r9d, eax; char *
0x1800596ce  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800596d5  mov     edx, 593h; void *
0x1800596da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800596e0  cmp     [rbp+4Fh+var_88], 0
0x1800596e5  jz      short loc_1800596ED
0x1800596e7  mov     dword ptr [rsi], 1
0x1800596ed  lea     rcx, [rbp+4Fh+var_58]; this
0x1800596f1  call    ??1ImpersonateContext@@QEAA@XZ; ImpersonateContext::~ImpersonateContext(void)
0x1800596f6  nop
0x1800596f7  mov     [rbp+4Fh+var_78], r14
0x1800596fb  lea     rcx, [rbp+4Fh+var_78]
0x1800596ff  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180059704  nop
0x180059705  lea     rcx, [rbp+4Fh+var_88]
0x180059709  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005970e  nop
0x18005970f  lea     rcx, [rbp+4Fh+var_A0]
0x180059713  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180059718  nop
0x180059719  lea     rcx, [rbp+4Fh+var_80]
0x18005971d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180059722  nop
0x180059723  lea     rcx, [rbp+4Fh+var_98]
0x180059727  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005972c  nop
0x18005972d  lea     rcx, [rbp+4Fh+var_90]
0x180059731  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180059736  xor     eax, eax
0x180059738  mov     rcx, [rbp+4Fh+var_28]
0x18005973c  xor     rcx, rsp; StackCookie
0x18005973f  call    __security_check_cookie
0x180059744  mov     rbx, [rsp+0D0h+arg_18]
0x18005974c  add     rsp, 0B0h
0x180059753  pop     r14
0x180059755  pop     r12
0x180059757  pop     rdi
0x180059758  pop     rsi
0x180059759  pop     rbp
0x18005975a  retn
```
