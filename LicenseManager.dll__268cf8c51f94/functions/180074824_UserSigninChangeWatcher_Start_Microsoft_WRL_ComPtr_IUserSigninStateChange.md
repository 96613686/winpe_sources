# UserSigninChangeWatcher::_Start(Microsoft::WRL::ComPtr<IUserSigninStateChange> &)

- ea: `0x180074824`
- end: `0x180074ad8`
- name: `?_Start@UserSigninChangeWatcher@@AEAAXAEAV?$ComPtr@UIUserSigninStateChange@@@WRL@Microsoft@@@Z`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180090860`

## callees

- `0x180004738`
- `0x180013b50`
- `0x18003c27c`
- `0x1800593bc`
- `0x1800646a0`
- `0x180074824`
- `0x180074ae0`
- `0x180074b30`
- `0x180074cc0`
- `0x18007633c`
- `0x18008a17c`
- `0x18008d630`
- `0x18008d6d0`
- `0x180090698`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007484a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007484a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074ab9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074ab9`

## string_xrefs

- `0x18007488b`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800748b6`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180074957`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180074982`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180074a2f`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180074a5a`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180074a9f`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180074969`: `UserSigninChangeWatcher added SignInComplete callback`
- `0x180074a41`: `UserSigninChangeWatcher added SignOutComplete callback`
- `0x18007489d`: `UserSigninChangeWatcher created SignInStateManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall UserSigninChangeWatcher::_Start(UserSigninChangeWatcher *this, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  _QWORD *v5; // r15
  int v6; // eax
  __int64 v7; // rbx
  void *v8; // rax
  int v9; // eax
  __int64 v10; // rbx
  void *v11; // rax
  int v12; // eax
  int v13; // eax
  int Format; // [rsp+20h] [rbp-30h]
  UserSigninChangeWatcher *v15; // [rsp+30h] [rbp-20h] BYREF
  int (*v16)(UserSigninChangeWatcher *__hidden, struct IInspectable *, struct Windows::System::Internal::ISignInCompleteEventArgs *); // [rsp+38h] [rbp-18h]
  int v17; // [rsp+40h] [rbp-10h]
  int v18; // [rsp+44h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v20; // [rsp+80h] [rbp+30h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+90h] [rbp+40h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v21 = v4;
  Microsoft::WRL::ComPtr<IAgileReference>::operator=((char *)this + 64, a2);
  v5 = (_QWORD *)((char *)this + 40);
  if ( !*((_QWORD *)this + 5) )
  {
    GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(&v20);
    v6 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(
           &v20,
           (char *)this + 40);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v6,
        Format);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x36Bu,
      "UserSigninChangeWatcher::_Start",
      (wchar_t *)L"UserSigninChangeWatcher created SignInStateManager");
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  }
  if ( !*((_QWORD *)this + 6) )
  {
    v15 = this;
    v16 = UserSigninChangeWatcher::OnSignInComplete;
    v17 = 0;
    v18 = (unsigned __int64)UserSigninChangeWatcher::OnSignInComplete >> 32;
    v7 = 0;
    v8 = operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
    v20 = (__int64)v8;
    if ( v8 )
    {
      v7 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::Internal::SignInCompleteEventArgs *,Windows::System::Internal::ISignInCompleteEventArgs *>>::*)(IInspectable *,Windows::System::Internal::ISignInCompleteEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::SignInCompleteEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_63de52e4a46d61ae8545feddf1b6ca4c_,-1,IInspectable *,Windows::System::Internal::ISignInCompleteEventArgs *>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::SignInCompleteEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_63de52e4a46d61ae8545feddf1b6ca4c_,-1,IInspectable *,Windows::System::Internal::ISignInCompleteEventArgs *>(
             v8,
             &v15);
      v20 = 0;
    }
    Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(&v20);
    v20 = v7;
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v5 + 96LL))(*v5, v7, (char *)this + 48);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x374,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v9,
        Format);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x375u,
      "UserSigninChangeWatcher::_Start",
      (wchar_t *)L"UserSigninChangeWatcher added SignInComplete callback");
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( !*((_QWORD *)this + 7) )
  {
    v15 = this;
    v16 = UserSigninChangeWatcher::OnSignOutComplete;
    v17 = 0;
    v18 = (unsigned __int64)UserSigninChangeWatcher::OnSignOutComplete >> 32;
    v10 = 0;
    v11 = operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
    v20 = (__int64)v11;
    if ( v11 )
    {
      v10 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::Internal::SignOutCompleteEventArgs *,Windows::System::Internal::ISignOutCompleteEventArgs *>>::*)(IInspectable *,Windows::System::Internal::ISignOutCompleteEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_733bb122d74641e2f991ba3a225915b7_,-1,IInspectable *,Windows::System::Internal::ISignOutCompleteEventArgs *>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_733bb122d74641e2f991ba3a225915b7_,-1,IInspectable *,Windows::System::Internal::ISignOutCompleteEventArgs *>(
              v11,
              &v15);
      v20 = 0;
    }
    Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(&v20);
    v20 = v10;
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v5 + 112LL))(*v5, v10, (char *)this + 56);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v12,
        Format);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x37Eu,
      "UserSigninChangeWatcher::_Start",
      (wchar_t *)L"UserSigninChangeWatcher added SignOutComplete callback");
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  UserSigninChangeWatcher::ReloadAllUsersState(this, a2);
  v13 = UserSigninChangeWatcher::SetupUserWatcher(this);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x386,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v13,
      Format);
  if ( v4 )
    LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180074824  mov     [rsp-28h+arg_8], rbx
0x180074829  mov     [rsp-28h+arg_18], rsi
0x18007482e  push    rbp
0x18007482f  push    rdi
0x180074830  push    r12
0x180074832  push    r14
0x180074834  push    r15
0x180074836  mov     rbp, rsp
0x180074839  sub     rsp, 50h
0x18007483d  mov     r12, rdx
0x180074840  mov     rdi, rcx
0x180074843  lea     rsi, [rcx+58h]
0x180074847  mov     rcx, rsi; lpCriticalSection
0x18007484a  call    cs:__imp_EnterCriticalSection
0x180074850  mov     [rbp+arg_10], rsi
0x180074854  lea     rcx, [rdi+40h]
0x180074858  mov     rdx, r12
0x18007485b  call    ??4?$ComPtr@UIAgileReference@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IAgileReference>::operator=(Microsoft::WRL::ComPtr<IAgileReference> const &)
0x180074860  lea     r15, [rdi+28h]
0x180074864  cmp     qword ptr [r15], 0
0x180074868  jnz     short loc_1800748D1
0x18007486a  lea     rcx, [rbp+arg_0]
0x18007486e  call    ??$GetActivationFactory@UIUserManagerStatics@Internal@System@Windows@@@@YA?AV?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@PEBG@Z; GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(ushort const *)
0x180074873  nop
0x180074874  mov     rdx, r15
0x180074877  lea     rcx, [rbp+arg_0]
0x18007487b  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x180074880  mov     rcx, [rbp+28h]; this
0x180074884  test    eax, eax
0x180074886  jns     short loc_18007489D
0x180074888  mov     r9d, eax; char *
0x18007488b  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180074892  mov     edx, 36Ah; void *
0x180074897  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007489d  lea     rax, aUsersigninchan_6; "UserSigninChangeWatcher created SignInS"...
0x1800748a4  mov     qword ptr [rsp+50h+Format], rax; int
0x1800748a9  lea     r9, aUsersigninchan_2; "UserSigninChangeWatcher::_Start"
0x1800748b0  mov     r8d, 36Bh; unsigned int
0x1800748b6  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800748bd  mov     ecx, 3; unsigned int
0x1800748c2  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800748c7  nop
0x1800748c8  lea     rcx, [rbp+arg_0]
0x1800748cc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800748d1  cmp     qword ptr [rdi+30h], 0
0x1800748d6  jnz     loc_1800749A9
0x1800748dc  mov     [rbp+var_20], rdi
0x1800748e0  lea     rax, ?OnSignInComplete@UserSigninChangeWatcher@@QEAAJPEAUIInspectable@@PEAUISignInCompleteEventArgs@Internal@System@Windows@@@Z; UserSigninChangeWatcher::OnSignInComplete(IInspectable *,Windows::System::Internal::ISignInCompleteEventArgs *)
0x1800748e7  mov     [rbp+var_18], rax
0x1800748eb  mov     [rbp+var_10], 0
0x1800748f2  mov     eax, dword ptr [rbp+var_18+4]
0x1800748f5  mov     [rbp+var_C], eax
0x1800748f8  xor     ebx, ebx
0x1800748fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180074901  lea     ecx, [rbx+58h]; unsigned __int64
0x180074904  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180074909  mov     [rbp+arg_0], rax
0x18007490d  test    rax, rax
0x180074910  jz      short loc_180074929
0x180074912  lea     rdx, [rbp+var_20]
0x180074916  mov     rcx, rax
0x180074919  call    ??0?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IEventHandler@PEAVSignInCompleteEventArgs@Internal@System@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_63de52e4a46d61ae8545feddf1b6ca4c_@@$0?0PEAUIInspectable@@PEAUISignInCompleteEventArgs@Internal@System@Windows@@@?$DelegateArgTraits@P8?$IEventHandler_impl@U?$AggregateType@PEAVSignInCompleteEventArgs@Internal@System@Windows@@PEAUISignInCompleteEventArgs@234@@Internal@Foundation@Windows@@@Foundation@Windows@@EAAJPEAUIInspectable@@PEAUISignInCompleteEventArgs@Internal@System@3@@Z@Details@WRL@Microsoft@@QEAA@$$QEAV_lambda_63de52e4a46d61ae8545feddf1b6ca4c_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::Internal::SignInCompleteEventArgs *,Windows::System::Internal::ISignInCompleteEventArgs *>>::*)(IInspectable *,Windows::System::Internal::ISignInCompleteEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::SignInCompleteEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_63de52e4a46d61ae8545feddf1b6ca4c_,-1,IInspectable *,Windows::System::Internal::ISignInCompleteEventArgs *>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::SignInCompleteEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_63de52e4a46d61ae8545feddf1b6ca4c_,-1,IInspectable *,Windows::System::Internal::ISignInCompleteEventArgs *>(_lambda_63de52e4a46d61ae8545feddf1b6ca4c_ &&)
0x18007491e  mov     rbx, rax
0x180074921  mov     [rbp+arg_0], 0
0x180074929  lea     rcx, [rbp+arg_0]
0x18007492d  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x180074932  mov     [rbp+arg_0], rbx
0x180074936  mov     rcx, [r15]
0x180074939  mov     rax, [rcx]
0x18007493c  lea     r8, [rdi+30h]
0x180074940  mov     rdx, rbx
0x180074943  mov     rax, [rax+60h]
0x180074947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007494c  mov     rcx, [rbp+28h]; this
0x180074950  test    eax, eax
0x180074952  jns     short loc_180074969
0x180074954  mov     r9d, eax; char *
0x180074957  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18007495e  mov     edx, 374h; void *
0x180074963  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074969  lea     rax, aUsersigninchan_4; "UserSigninChangeWatcher added SignInCom"...
0x180074970  mov     qword ptr [rsp+50h+Format], rax; int
0x180074975  lea     r9, aUsersigninchan_2; "UserSigninChangeWatcher::_Start"
0x18007497c  mov     r8d, 375h; unsigned int
0x180074982  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180074989  mov     ecx, 3; unsigned int
0x18007498e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180074993  nop
0x180074994  test    rbx, rbx
0x180074997  jz      short loc_1800749A9
0x180074999  mov     rax, [rbx]
0x18007499c  mov     rcx, rbx
0x18007499f  mov     rax, [rax+10h]
0x1800749a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749a8  nop
0x1800749a9  cmp     qword ptr [rdi+38h], 0
0x1800749ae  jnz     loc_180074A81
0x1800749b4  mov     [rbp+var_20], rdi
0x1800749b8  lea     rax, ?OnSignOutComplete@UserSigninChangeWatcher@@QEAAJPEAUIInspectable@@PEAUISignOutCompleteEventArgs@Internal@System@Windows@@@Z; UserSigninChangeWatcher::OnSignOutComplete(IInspectable *,Windows::System::Internal::ISignOutCompleteEventArgs *)
0x1800749bf  mov     [rbp+var_18], rax
0x1800749c3  mov     [rbp+var_10], 0
0x1800749ca  mov     eax, dword ptr [rbp+var_18+4]
0x1800749cd  mov     [rbp+var_C], eax
0x1800749d0  xor     ebx, ebx
0x1800749d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800749d9  lea     ecx, [rbx+58h]; unsigned __int64
0x1800749dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800749e1  mov     [rbp+arg_0], rax
0x1800749e5  test    rax, rax
0x1800749e8  jz      short loc_180074A01
0x1800749ea  lea     rdx, [rbp+var_20]
0x1800749ee  mov     rcx, rax
0x1800749f1  call    ??0?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IEventHandler@PEAVSignOutCompleteEventArgs@Internal@System@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_733bb122d74641e2f991ba3a225915b7_@@$0?0PEAUIInspectable@@PEAUISignOutCompleteEventArgs@Internal@System@Windows@@@?$DelegateArgTraits@P8?$IEventHandler_impl@U?$AggregateType@PEAVSignOutCompleteEventArgs@Internal@System@Windows@@PEAUISignOutCompleteEventArgs@234@@Internal@Foundation@Windows@@@Foundation@Windows@@EAAJPEAUIInspectable@@PEAUISignOutCompleteEventArgs@Internal@System@3@@Z@Details@WRL@Microsoft@@QEAA@$$QEAV_lambda_733bb122d74641e2f991ba3a225915b7_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::Internal::SignOutCompleteEventArgs *,Windows::System::Internal::ISignOutCompleteEventArgs *>>::*)(IInspectable *,Windows::System::Internal::ISignOutCompleteEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_733bb122d74641e2f991ba3a225915b7_,-1,IInspectable *,Windows::System::Internal::ISignOutCompleteEventArgs *>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_733bb122d74641e2f991ba3a225915b7_,-1,IInspectable *,Windows::System::Internal::ISignOutCompleteEventArgs *>(_lambda_733bb122d74641e2f991ba3a225915b7_ &&)
0x1800749f6  mov     rbx, rax
0x1800749f9  mov     [rbp+arg_0], 0
0x180074a01  lea     rcx, [rbp+arg_0]
0x180074a05  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x180074a0a  mov     [rbp+arg_0], rbx
0x180074a0e  mov     rcx, [r15]
0x180074a11  mov     rax, [rcx]
0x180074a14  lea     r8, [rdi+38h]
0x180074a18  mov     rdx, rbx
0x180074a1b  mov     rax, [rax+70h]
0x180074a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074a24  mov     rcx, [rbp+28h]; this
0x180074a28  test    eax, eax
0x180074a2a  jns     short loc_180074A41
0x180074a2c  mov     r9d, eax; char *
0x180074a2f  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180074a36  mov     edx, 37Dh; void *
0x180074a3b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074a41  lea     rax, aUsersigninchan_5; "UserSigninChangeWatcher added SignOutCo"...
0x180074a48  mov     qword ptr [rsp+50h+Format], rax; int
0x180074a4d  lea     r9, aUsersigninchan_2; "UserSigninChangeWatcher::_Start"
0x180074a54  mov     r8d, 37Eh; unsigned int
0x180074a5a  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180074a61  mov     ecx, 3; unsigned int
0x180074a66  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180074a6b  nop
0x180074a6c  test    rbx, rbx
0x180074a6f  jz      short loc_180074A81
0x180074a71  mov     rax, [rbx]
0x180074a74  mov     rcx, rbx
0x180074a77  mov     rax, [rax+10h]
0x180074a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074a80  nop
0x180074a81  mov     rdx, r12
0x180074a84  mov     rcx, rdi
0x180074a87  call    ?ReloadAllUsersState@UserSigninChangeWatcher@@AEAAXAEAV?$ComPtr@UIUserSigninStateChange@@@WRL@Microsoft@@@Z; UserSigninChangeWatcher::ReloadAllUsersState(Microsoft::WRL::ComPtr<IUserSigninStateChange> &)
0x180074a8c  mov     rcx, rdi; this
0x180074a8f  call    ?SetupUserWatcher@UserSigninChangeWatcher@@AEAAJXZ; UserSigninChangeWatcher::SetupUserWatcher(void)
0x180074a94  mov     rcx, [rbp+28h]; this
0x180074a98  test    eax, eax
0x180074a9a  jns     short loc_180074AB1
0x180074a9c  mov     r9d, eax; char *
0x180074a9f  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180074aa6  mov     edx, 386h; void *
0x180074aab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180074ab0  nop
0x180074ab1  test    rsi, rsi
0x180074ab4  jz      short loc_180074ABF
0x180074ab6  mov     rcx, rsi; lpCriticalSection
0x180074ab9  call    cs:__imp_LeaveCriticalSection
0x180074abf  lea     r11, [rsp+50h+var_s0]
0x180074ac4  mov     rbx, [r11+38h]
0x180074ac8  mov     rsi, [r11+48h]
0x180074acc  mov     rsp, r11
0x180074acf  pop     r15
0x180074ad1  pop     r14
0x180074ad3  pop     r12
0x180074ad5  pop     rdi
0x180074ad6  pop     rbp
0x180074ad7  retn
```
