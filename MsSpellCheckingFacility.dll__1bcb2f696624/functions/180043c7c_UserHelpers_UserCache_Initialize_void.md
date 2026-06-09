# UserHelpers::UserCache::Initialize(void)

- ea: `0x180043c7c`
- end: `0x180043fc1`
- name: `?Initialize@UserCache@UserHelpers@@QEAAXXZ`
- size: `837`
- prototype: `void __fastcall(UserHelpers::UserCache *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800994e0`

## callees

- `0x180040cc4`
- `0x180042ae0`
- `0x180043568`
- `0x180043c7c`
- `0x180043fc8`
- `0x180044074`
- `0x18004413c`
- `0x1800441c4`
- `0x180044250`
- `0x1800442e4`
- `0x180044cf4`
- `0x1800455f4`
- `0x180054d28`
- `0x180061320`
- `0x180070530`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180043cb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180043cb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043cd7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043cd7`

## string_xrefs

- `0x180043d59`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`
- `0x180043d92`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`
- `0x180043dd5`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`
- `0x180043e19`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`
- `0x180043f1c`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall UserHelpers::UserCache::Initialize(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rdi
  void **v3; // rax
  void *v4; // rdx
  PVOID Ptr; // rcx
  PVOID v6; // rdi
  __int64 (__fastcall *v7)(PVOID, RTL_SRWLOCK *); // rsi
  RTL_SRWLOCK v8; // rcx
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 *v22; // rcx
  int v23; // [rsp+20h] [rbp-89h]
  int v24; // [rsp+20h] [rbp-89h]
  int v25; // [rsp+30h] [rbp-79h] BYREF
  RTL_SRWLOCK *v26; // [rsp+38h] [rbp-71h] BYREF
  __int64 (__fastcall *v27)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *); // [rsp+40h] [rbp-69h] BYREF
  __int64 v28; // [rsp+48h] [rbp-61h] BYREF
  __int64 *v29; // [rsp+50h] [rbp-59h] BYREF
  __int64 v30; // [rsp+58h] [rbp-51h] BYREF
  int v31[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 (__fastcall *v32)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *); // [rsp+68h] [rbp-41h] BYREF
  RTL_SRWLOCK *v33; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v34[3]; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v35[80]; // [rsp+90h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v2 = this + 3;
  AcquireSRWLockShared(this + 3);
  v26 = v2;
  if ( LOBYTE(this[2].Ptr) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
    AcquireSRWLockExclusive(v2);
    v33 = v2;
    if ( !LOBYTE(this[2].Ptr) )
    {
      v3 = (void **)wil::GetActivationFactory<Windows::System::IUserStatics>(&v27);
      v4 = *v3;
      *v3 = 0;
      Ptr = this[1].Ptr;
      this[1].Ptr = v4;
      if ( Ptr )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
      v6 = this[1].Ptr;
      v7 = *(__int64 (__fastcall **)(PVOID, RTL_SRWLOCK *))(*(_QWORD *)v6 + 48LL);
      v8.Ptr = this->Ptr;
      this->Ptr = 0;
      if ( v8.Ptr )
        (*(void (__fastcall **)(RTL_SRWLOCK))(*(_QWORD *)v8.Ptr + 16LL))(v8);
      v9 = v7(v6, this);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
          (const char *)(unsigned int)v9,
          v23);
      v30 = 0;
      v10 = (__int64 *)this[1].Ptr;
      v11 = *v10;
      v30 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 56))(v10, &v30);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
          (const char *)(unsigned int)v12,
          v23);
      wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(
        &v29,
        v30);
      v25 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v29 + 56))(v29, &v25);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
          (const char *)(unsigned int)v13,
          v23);
      v28 = 0;
      if ( v25 == 1 )
      {
        v14 = *v29;
        v28 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v14 + 48))(v29, 0, &v28);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7E,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
            (const char *)(unsigned int)v15,
            v23);
      }
      v16 = UserHelpers::UserCache::CacheForUser(v35);
      UserHelpers::UserCache::CachedData::operator=(&this[4], v16);
      UserHelpers::UserCache::CachedData::~CachedData((UserHelpers::UserCache::CachedData *)v35);
      v27 = UserHelpers::UserCache::OnUserAdded;
      v32 = (__int64 (__fastcall *)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *))this;
      ___MakeAgileCallback_U__ITypedEventHandler_PEAVUserWatcher_System_Windows__PEAVUserChangedEventArgs_23__Foundation_Windows__PEAVUserCache_UserHelpers__P845_EAAJPEAUIUserWatcher_System_3_PEAUIUserChangedEventArgs_73___E_wil__YA_AV__ComPtr_U__ITypedEventHandler_PEAVUserWatcher_System_Windows__PEAVUserChangedEventArgs_23__Foundation_Windows___WRL_Microsoft____QEAPEAVUserCache_UserHelpers____QEAP845_EAAJPEAUIUserWatcher_System_Windows__PEAUIUserChangedEventArgs_78___E_Z(
        &v26,
        &v32,
        &v27);
      v17 = wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(
              v34,
              this->Ptr,
              (__int64 (__fastcall *)(_QWORD, __int64, __int64 *)) Windows::System::IUserWatcher::`vcall'{72,{flat}},
              (__int64) Windows::System::IUserWatcher::`vcall'{80,{flat}},
              (__int64)v26);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::operator=(&this[13], v17);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::~unique_winrt_event_token<Windows::System::IUserWatcher>(v34);
      v32 = UserHelpers::UserCache::OnUserRemoved;
      v27 = (__int64 (__fastcall *)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *))this;
      ___MakeAgileCallback_U__ITypedEventHandler_PEAVUserWatcher_System_Windows__PEAVUserChangedEventArgs_23__Foundation_Windows__PEAVUserCache_UserHelpers__P845_EAAJPEAUIUserWatcher_System_3_PEAUIUserChangedEventArgs_73___E_wil__YA_AV__ComPtr_U__ITypedEventHandler_PEAVUserWatcher_System_Windows__PEAVUserChangedEventArgs_23__Foundation_Windows___WRL_Microsoft____QEAPEAVUserCache_UserHelpers____QEAP845_EAAJPEAUIUserWatcher_System_Windows__PEAUIUserChangedEventArgs_78___E_Z(
        v31,
        &v27,
        &v32);
      v18 = wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(
              v34,
              this->Ptr,
              (__int64 (__fastcall *)(_QWORD, __int64, __int64 *)) Windows::System::IUserWatcher::`vcall'{88,{flat}},
              (__int64) Windows::System::IUserWatcher::`vcall'{96,{flat}},
              *(__int64 *)v31);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::operator=(&this[16], v18);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::~unique_winrt_event_token<Windows::System::IUserWatcher>(v34);
      v19 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)this->Ptr + 56LL))(this->Ptr);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x89,
          (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
          (const char *)(unsigned int)v19,
          v24);
      LOBYTE(this[2].Ptr) = 1;
      v20 = *(_QWORD *)v31;
      if ( *(_QWORD *)v31 )
      {
        *(_QWORD *)v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v21 = (__int64)v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
      v22 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v33);
  }
}

```

## disassembly

```asm
0x180043c7c  mov     [rsp-8+arg_8], rbx
0x180043c81  mov     [rsp-8+arg_10], rsi
0x180043c86  push    rbp
0x180043c87  push    rdi
0x180043c88  push    r14
0x180043c8a  lea     rbp, [rsp-47h]
0x180043c8f  sub     rsp, 0F0h
0x180043c96  mov     rax, cs:__security_cookie
0x180043c9d  xor     rax, rsp
0x180043ca0  mov     [rbp+57h+var_20], rax
0x180043ca4  mov     rbx, rcx
0x180043ca7  xor     r14d, r14d
0x180043caa  lea     rdi, [rcx+18h]
0x180043cae  mov     rcx, rdi; SRWLock
0x180043cb1  call    cs:__imp_AcquireSRWLockShared
0x180043cb7  mov     [rbp+57h+var_C8], rdi
0x180043cbb  lea     rcx, [rbp+57h+var_C8]
0x180043cbf  cmp     [rbx+10h], r14b
0x180043cc3  jz      short loc_180043CCF
0x180043cc5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180043cca  jmp     loc_180043F9D
0x180043ccf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180043cd4  mov     rcx, rdi; SRWLock
0x180043cd7  call    cs:__imp_AcquireSRWLockExclusive
0x180043cdd  mov     [rbp+57h+var_90], rdi
0x180043ce1  cmp     [rbx+10h], r14b
0x180043ce5  jnz     loc_180043F94
0x180043ceb  lea     rcx, [rbp+57h+var_C0]
0x180043cef  call    ??$GetActivationFactory@UIUserStatics@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserStatics@System@Windows@@Uerr_exception_policy@wil@@@0@PEB_W@Z; wil::GetActivationFactory<Windows::System::IUserStatics>(wchar_t const *)
0x180043cf4  mov     rdx, [rax]
0x180043cf7  mov     [rax], r14
0x180043cfa  mov     rcx, [rbx+8]
0x180043cfe  mov     [rbx+8], rdx
0x180043d02  test    rcx, rcx
0x180043d05  jz      short loc_180043D14
0x180043d07  mov     rax, [rcx]
0x180043d0a  mov     rax, [rax+10h]
0x180043d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d13  nop
0x180043d14  lea     rcx, [rbp+57h+var_C0]
0x180043d18  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180043d1d  mov     rdi, [rbx+8]
0x180043d21  mov     rax, [rdi]
0x180043d24  mov     rsi, [rax+30h]
0x180043d28  mov     rcx, [rbx]
0x180043d2b  mov     [rbx], r14
0x180043d2e  test    rcx, rcx
0x180043d31  jz      short loc_180043D40
0x180043d33  mov     rdx, [rcx]
0x180043d36  mov     rax, [rdx+10h]
0x180043d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d3f  nop
0x180043d40  mov     rdx, rbx
0x180043d43  mov     rcx, rdi
0x180043d46  mov     rax, rsi
0x180043d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d4e  mov     rcx, [rbp+5Fh]; this
0x180043d52  test    eax, eax
0x180043d54  jns     short loc_180043D6B
0x180043d56  mov     r9d, eax; char *
0x180043d59  lea     r8, aOnecoreInterna_9; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180043d60  mov     edx, 6Fh ; 'o'; void *
0x180043d65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043d6b  mov     [rbp+57h+var_A8], r14
0x180043d6f  mov     rcx, [rbx+8]
0x180043d73  mov     rax, [rcx]
0x180043d76  mov     [rbp+57h+var_A8], r14
0x180043d7a  lea     rdx, [rbp+57h+var_A8]
0x180043d7e  mov     rax, [rax+38h]
0x180043d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d87  mov     rcx, [rbp+5Fh]; this
0x180043d8b  test    eax, eax
0x180043d8d  jns     short loc_180043DA4
0x180043d8f  mov     r9d, eax; char *
0x180043d92  lea     r8, aOnecoreInterna_9; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180043d99  mov     edx, 74h ; 't'; void *
0x180043d9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043da4  mov     rdx, [rbp+57h+var_A8]
0x180043da8  lea     rcx, [rbp+57h+var_B0]
0x180043dac  call    ??$wait_for_completion@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@V?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS)
0x180043db1  nop
0x180043db2  mov     [rbp+57h+var_D0], r14d
0x180043db6  mov     rcx, [rbp+57h+var_B0]
0x180043dba  mov     rax, [rcx]
0x180043dbd  lea     rdx, [rbp+57h+var_D0]
0x180043dc1  mov     rax, [rax+38h]
0x180043dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043dca  mov     rcx, [rbp+5Fh]; this
0x180043dce  test    eax, eax
0x180043dd0  jns     short loc_180043DE7
0x180043dd2  mov     r9d, eax; char *
0x180043dd5  lea     r8, aOnecoreInterna_9; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180043ddc  mov     edx, 79h ; 'y'; void *
0x180043de1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043de7  mov     rdx, r14
0x180043dea  mov     [rbp+57h+var_B8], rdx
0x180043dee  cmp     [rbp+57h+var_D0], 1
0x180043df2  jnz     short loc_180043E2F
0x180043df4  mov     rcx, [rbp+57h+var_B0]
0x180043df8  mov     rax, [rcx]
0x180043dfb  mov     [rbp+57h+var_B8], r14
0x180043dff  lea     r8, [rbp+57h+var_B8]
0x180043e03  xor     edx, edx
0x180043e05  mov     rax, [rax+30h]
0x180043e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e0e  mov     rcx, [rbp+5Fh]; this
0x180043e12  test    eax, eax
0x180043e14  jns     short loc_180043E2B
0x180043e16  mov     r9d, eax; char *
0x180043e19  lea     r8, aOnecoreInterna_9; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180043e20  mov     edx, 7Eh ; '~'; void *
0x180043e25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043e2b  mov     rdx, [rbp+57h+var_B8]
0x180043e2f  lea     rcx, [rbp+57h+var_70]
0x180043e33  call    ?CacheForUser@UserCache@UserHelpers@@CA?AUCachedData@12@PEAUIUser@System@Windows@@@Z; UserHelpers::UserCache::CacheForUser(Windows::System::IUser *)
0x180043e38  lea     rcx, [rbx+20h]
0x180043e3c  mov     rdx, rax
0x180043e3f  call    ??4CachedData@UserCache@UserHelpers@@QEAAAEAU012@$$QEAU012@@Z; UserHelpers::UserCache::CachedData::operator=(UserHelpers::UserCache::CachedData &&)
0x180043e44  lea     rcx, [rbp+57h+var_70]; this
0x180043e48  call    ??1CachedData@UserCache@UserHelpers@@QEAA@XZ; UserHelpers::UserCache::CachedData::~CachedData(void)
0x180043e4d  lea     rax, ?OnUserAdded@UserCache@UserHelpers@@AEAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@45@@Z; UserHelpers::UserCache::OnUserAdded(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)
0x180043e54  mov     [rbp+57h+var_C0], rax
0x180043e58  mov     [rbp+57h+var_98], rbx
0x180043e5c  lea     r8, [rbp+57h+var_C0]
0x180043e60  lea     rdx, [rbp+57h+var_98]
0x180043e64  lea     rcx, [rbp+57h+var_C8]
0x180043e68  call    ??$MakeAgileCallback@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@PEAVUserCache@UserHelpers@@P845@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@73@@_E@wil@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@@WRL@Microsoft@@$$QEAPEAVUserCache@UserHelpers@@$$QEAP845@EAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@78@@_E@Z
0x180043e6d  nop
0x180043e6e  mov     rax, [rbp+57h+var_C8]
0x180043e72  mov     qword ptr [rsp+100h+var_E0], rax
0x180043e77  lea     r9, ??_9IUserWatcher@System@Windows@@$BFA@AA; [thunk]: Windows::System::IUserWatcher::`vcall'{80,{flat}}
0x180043e7e  lea     r8, ??_9IUserWatcher@System@Windows@@$BEI@AA; [thunk]: Windows::System::IUserWatcher::`vcall'{72,{flat}}
0x180043e85  mov     rdx, [rbx]
0x180043e88  lea     rcx, [rbp+57h+var_88]
0x180043e8c  call    ??$make_unique_winrt_event_token@Uerr_exception_policy@wil@@UIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@ZPEAU675@@details@wil@@YA?AV?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@1@PEAUIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@Z1@Z; wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(Windows::System::IUserWatcher *,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *)
0x180043e91  lea     rcx, [rbx+68h]
0x180043e95  mov     rdx, rax
0x180043e98  call    ??4?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::operator=(wil::unique_winrt_event_token<Windows::System::IUserWatcher> &&)
0x180043e9d  lea     rcx, [rbp+57h+var_88]
0x180043ea1  call    ??1?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAA@XZ; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::~unique_winrt_event_token<Windows::System::IUserWatcher>(void)
0x180043ea6  lea     rax, ?OnUserRemoved@UserCache@UserHelpers@@AEAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@45@@Z; UserHelpers::UserCache::OnUserRemoved(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)
0x180043ead  mov     [rbp+57h+var_98], rax
0x180043eb1  mov     [rbp+57h+var_C0], rbx
0x180043eb5  lea     r8, [rbp+57h+var_98]
0x180043eb9  lea     rdx, [rbp+57h+var_C0]
0x180043ebd  lea     rcx, [rbp+57h+var_A0]
0x180043ec1  call    ??$MakeAgileCallback@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@PEAVUserCache@UserHelpers@@P845@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@73@@_E@wil@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@@WRL@Microsoft@@$$QEAPEAVUserCache@UserHelpers@@$$QEAP845@EAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@78@@_E@Z
0x180043ec6  nop
0x180043ec7  mov     rax, qword ptr [rbp+57h+var_A0]
0x180043ecb  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180043ed0  lea     r9, ??_9IUserWatcher@System@Windows@@$BGA@AA; [thunk]: Windows::System::IUserWatcher::`vcall'{96,{flat}}
0x180043ed7  lea     r8, ??_9IUserWatcher@System@Windows@@$BFI@AA; [thunk]: Windows::System::IUserWatcher::`vcall'{88,{flat}}
0x180043ede  mov     rdx, [rbx]
0x180043ee1  lea     rcx, [rbp+57h+var_88]
0x180043ee5  call    ??$make_unique_winrt_event_token@Uerr_exception_policy@wil@@UIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@ZPEAU675@@details@wil@@YA?AV?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@1@PEAUIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@Z1@Z; wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(Windows::System::IUserWatcher *,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *)
0x180043eea  lea     rcx, [rbx+80h]
0x180043ef1  mov     rdx, rax
0x180043ef4  call    ??4?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::operator=(wil::unique_winrt_event_token<Windows::System::IUserWatcher> &&)
0x180043ef9  lea     rcx, [rbp+57h+var_88]
0x180043efd  call    ??1?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAA@XZ; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::~unique_winrt_event_token<Windows::System::IUserWatcher>(void)
0x180043f02  mov     rcx, [rbx]
0x180043f05  mov     rax, [rcx]
0x180043f08  mov     rax, [rax+38h]
0x180043f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f11  mov     rcx, [rbp+5Fh]; this
0x180043f15  test    eax, eax
0x180043f17  jns     short loc_180043F2E
0x180043f19  mov     r9d, eax; char *
0x180043f1c  lea     r8, aOnecoreInterna_9; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180043f23  mov     edx, 89h; void *
0x180043f28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043f2e  mov     byte ptr [rbx+10h], 1
0x180043f32  mov     rcx, qword ptr [rbp+57h+var_A0]
0x180043f36  test    rcx, rcx
0x180043f39  jz      short loc_180043F4C
0x180043f3b  mov     qword ptr [rbp+57h+var_A0], r14
0x180043f3f  mov     rax, [rcx]
0x180043f42  mov     rax, [rax+10h]
0x180043f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f4b  nop
0x180043f4c  mov     rcx, [rbp+57h+var_C8]
0x180043f50  test    rcx, rcx
0x180043f53  jz      short loc_180043F66
0x180043f55  mov     [rbp+57h+var_C8], r14
0x180043f59  mov     rax, [rcx]
0x180043f5c  mov     rax, [rax+10h]
0x180043f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f65  nop
0x180043f66  lea     rcx, [rbp+57h+var_B8]
0x180043f6a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180043f6f  nop
0x180043f70  mov     rcx, [rbp+57h+var_B0]
0x180043f74  test    rcx, rcx
0x180043f77  jz      short loc_180043F8A
0x180043f79  mov     [rbp+57h+var_B0], r14
0x180043f7d  mov     rax, [rcx]
0x180043f80  mov     rax, [rax+10h]
0x180043f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f89  nop
0x180043f8a  lea     rcx, [rbp+57h+var_A8]
0x180043f8e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180043f93  nop
0x180043f94  lea     rcx, [rbp+57h+var_90]
0x180043f98  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180043f9d  mov     rcx, [rbp+57h+var_20]
0x180043fa1  xor     rcx, rsp; StackCookie
0x180043fa4  call    __security_check_cookie
0x180043fa9  lea     r11, [rsp+100h+var_10]
0x180043fb1  mov     rbx, [r11+28h]
0x180043fb5  mov     rsi, [r11+30h]
0x180043fb9  mov     rsp, r11
0x180043fbc  pop     r14
0x180043fbe  pop     rdi
0x180043fbf  pop     rbp
0x180043fc0  retn
```
