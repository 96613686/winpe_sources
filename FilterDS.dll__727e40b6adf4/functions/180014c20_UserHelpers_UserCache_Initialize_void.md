# UserHelpers::UserCache::Initialize(void)

- ea: `0x180014c20`
- end: `0x180014fe5`
- name: `?Initialize@UserCache@UserHelpers@@QEAAXXZ`
- size: `965`
- prototype: `void __fastcall(UserHelpers::UserCache *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001442c`
- `0x180015de4`

## callees

- `0x18000868c`
- `0x180008c30`
- `0x18000cd18`
- `0x18000d760`
- `0x180011824`
- `0x1800118d8`
- `0x180012284`
- `0x1800123b0`
- `0x180012eac`
- `0x1800136c0`
- `0x180014c20`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014c50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014c50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014c84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014c84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f5a`

## string_xrefs

- `0x180014f7f`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`
- `0x180014f94`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`
- `0x180014fa9`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`
- `0x180014fbe`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`
- `0x180014fd3`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`

## pseudocode

```c
void __fastcall UserHelpers::UserCache::Initialize(UserHelpers::UserCache *this)
{
  RTL_SRWLOCK *v2; // rdi
  __int64 *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, UserHelpers::UserCache *); // r14
  RTL_SRWLOCK v8; // rcx
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  UserHelpers *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  __int128 *v17; // rax
  __int64 *v18; // rax
  __int64 *v19; // rax
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 *v23; // rcx
  int v24; // [rsp+20h] [rbp-A9h]
  int v25; // [rsp+20h] [rbp-A9h]
  int v26; // [rsp+30h] [rbp-99h] BYREF
  __int64 (__fastcall *v27)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *); // [rsp+38h] [rbp-91h] BYREF
  UserHelpers *v28; // [rsp+40h] [rbp-89h] BYREF
  __int64 *v29; // [rsp+48h] [rbp-81h] BYREF
  __int64 v30; // [rsp+50h] [rbp-79h] BYREF
  int v31[2]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v32; // [rsp+60h] [rbp-69h] BYREF
  __int64 (__fastcall *v33)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *); // [rsp+68h] [rbp-61h] BYREF
  __int64 v34; // [rsp+70h] [rbp-59h] BYREF
  __int64 v35; // [rsp+78h] [rbp-51h]
  RTL_SRWLOCK *v36; // [rsp+88h] [rbp-41h]
  __int128 v37[5]; // [rsp+90h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v2 = (RTL_SRWLOCK *)((char *)this + 24);
  AcquireSRWLockShared((PSRWLOCK)this + 3);
  if ( *((_BYTE *)this + 16) )
  {
    if ( v2 )
      ReleaseSRWLockShared(v2);
  }
  else
  {
    if ( v2 )
      ReleaseSRWLockShared(v2);
    AcquireSRWLockExclusive(v2);
    v36 = v2;
    if ( !*((_BYTE *)this + 16) )
    {
      v3 = wil::GetActivationFactory<Windows::System::IUserStatics>(&v27);
      v4 = *v3;
      *v3 = 0;
      v5 = *((_QWORD *)this + 1);
      *((_QWORD *)this + 1) = v4;
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      if ( v27 )
        (*(void (__fastcall **)(__int64 (__fastcall *)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *)))(*(_QWORD *)v27 + 16LL))(v27);
      v6 = *((_QWORD *)this + 1);
      v7 = *(__int64 (__fastcall **)(__int64, UserHelpers::UserCache *))(*(_QWORD *)v6 + 48LL);
      v8.Ptr = *(PVOID *)this;
      *(_QWORD *)this = 0;
      if ( v8.Ptr )
        (*(void (__fastcall **)(RTL_SRWLOCK))(*(_QWORD *)v8.Ptr + 16LL))(v8);
      v9 = v7(v6, this);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x6F,
          (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
          (const char *)(unsigned int)v9,
          v24);
      v30 = 0;
      v10 = (__int64 *)*((_QWORD *)this + 1);
      v11 = *v10;
      v30 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 56))(v10, &v30);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x74,
          (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
          (const char *)(unsigned int)v12,
          v24);
      wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(
        &v29,
        v30);
      v26 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v29 + 56))(v29, &v26);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x79,
          (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
          (const char *)(unsigned int)v13,
          v24);
      v14 = 0;
      v28 = 0;
      if ( v26 == 1 )
      {
        v15 = *v29;
        v28 = 0;
        v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, UserHelpers **))(v15 + 48))(v29, 0, &v28);
        if ( v16 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x7E,
            (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
            (const char *)(unsigned int)v16,
            v24);
        v14 = v28;
      }
      v17 = UserHelpers::UserCache::CacheForUser(v37, v14);
      UserHelpers::UserCache::CachedData::operator=((char *)this + 32, (char *)v17);
      UserHelpers::UserCache::CachedData::~CachedData((UserHelpers::UserCache::CachedData *)v37);
      v27 = UserHelpers::UserCache::OnUserAdded;
      v33 = (__int64 (__fastcall *)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *))this;
      ___MakeAgileCallback_U__ITypedEventHandler_PEAVUserWatcher_System_Windows__PEAVUserChangedEventArgs_23__Foundation_Windows__PEAVUserCache_UserHelpers__P845_EAAJPEAUIUserWatcher_System_3_PEAUIUserChangedEventArgs_73___E_wil__YA_AV__ComPtr_U__ITypedEventHandler_PEAVUserWatcher_System_Windows__PEAVUserChangedEventArgs_23__Foundation_Windows___WRL_Microsoft____QEAPEAVUserCache_UserHelpers____QEAP845_EAAJPEAUIUserWatcher_System_Windows__PEAUIUserChangedEventArgs_78___E_Z(
        &v32,
        (__int64 *)&v33,
        (__int64 *)&v27);
      v18 = wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(
              &v34,
              *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this,
              (__int64 (__fastcall *)(_QWORD, __int64, _QWORD *)) Windows::System::IUserWatcher::`vcall'{72,{flat}},
              (__int64) Windows::System::IUserWatcher::`vcall'{80,{flat}},
              v32);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::operator=((__int64 *)this + 13, v18);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset(&v34);
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v33 = UserHelpers::UserCache::OnUserRemoved;
      v27 = (__int64 (__fastcall *)(UserHelpers::UserCache *__hidden, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *))this;
      ___MakeAgileCallback_U__ITypedEventHandler_PEAVUserWatcher_System_Windows__PEAVUserChangedEventArgs_23__Foundation_Windows__PEAVUserCache_UserHelpers__P845_EAAJPEAUIUserWatcher_System_3_PEAUIUserChangedEventArgs_73___E_wil__YA_AV__ComPtr_U__ITypedEventHandler_PEAVUserWatcher_System_Windows__PEAVUserChangedEventArgs_23__Foundation_Windows___WRL_Microsoft____QEAPEAVUserCache_UserHelpers____QEAP845_EAAJPEAUIUserWatcher_System_Windows__PEAUIUserChangedEventArgs_78___E_Z(
        v31,
        (__int64 *)&v27,
        (__int64 *)&v33);
      v19 = wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(
              &v34,
              *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this,
              (__int64 (__fastcall *)(_QWORD, __int64, _QWORD *)) Windows::System::IUserWatcher::`vcall'{88,{flat}},
              (__int64) Windows::System::IUserWatcher::`vcall'{96,{flat}},
              *(__int64 *)v31);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::operator=((__int64 *)this + 16, v19);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset(&v34);
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v20 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x89,
          (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
          (const char *)(unsigned int)v20,
          v25);
      *((_BYTE *)this + 16) = 1;
      v21 = *(_QWORD *)v31;
      if ( *(_QWORD *)v31 )
      {
        *(_QWORD *)v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      if ( v28 )
        (*(void (__fastcall **)(UserHelpers *))(*(_QWORD *)v28 + 16LL))(v28);
      v23 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
      }
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x180014c20  push    rbp
0x180014c22  push    rbx
0x180014c23  push    rsi
0x180014c24  push    rdi
0x180014c25  push    r14
0x180014c27  push    r15
0x180014c29  lea     rbp, [rsp-2Fh]
0x180014c2e  sub     rsp, 0F8h
0x180014c35  mov     rax, cs:__security_cookie
0x180014c3c  xor     rax, rsp
0x180014c3f  mov     [rbp+57h+var_40], rax
0x180014c43  mov     rbx, rcx
0x180014c46  xor     r15d, r15d
0x180014c49  lea     rdi, [rcx+18h]
0x180014c4d  mov     rcx, rdi; SRWLock
0x180014c50  call    cs:__imp_AcquireSRWLockShared
0x180014c56  cmp     [rbx+10h], r15b
0x180014c5a  jz      short loc_180014C73
0x180014c5c  test    rdi, rdi
0x180014c5f  jz      loc_180014F60
0x180014c65  mov     rcx, rdi; SRWLock
0x180014c68  call    cs:__imp_ReleaseSRWLockShared
0x180014c6e  jmp     loc_180014F60
0x180014c73  test    rdi, rdi
0x180014c76  jz      short loc_180014C81
0x180014c78  mov     rcx, rdi; SRWLock
0x180014c7b  call    cs:__imp_ReleaseSRWLockShared
0x180014c81  mov     rcx, rdi; SRWLock
0x180014c84  call    cs:__imp_AcquireSRWLockExclusive
0x180014c8a  mov     [rbp+57h+var_98], rdi
0x180014c8e  cmp     [rbx+10h], r15b
0x180014c92  jnz     loc_180014F52
0x180014c98  lea     rcx, [rsp+120h+var_E8]
0x180014c9d  call    ??$GetActivationFactory@UIUserStatics@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserStatics@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::IUserStatics>(ushort const *)
0x180014ca2  mov     rdx, [rax]
0x180014ca5  mov     [rax], r15
0x180014ca8  mov     rcx, [rbx+8]
0x180014cac  mov     [rbx+8], rdx
0x180014cb0  test    rcx, rcx
0x180014cb3  jz      short loc_180014CC2
0x180014cb5  mov     rax, [rcx]
0x180014cb8  mov     rax, [rax+10h]
0x180014cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cc1  nop
0x180014cc2  mov     rcx, [rsp+120h+var_E8]
0x180014cc7  test    rcx, rcx
0x180014cca  jz      short loc_180014CD9
0x180014ccc  mov     rax, [rcx]
0x180014ccf  mov     rax, [rax+10h]
0x180014cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cd8  nop
0x180014cd9  mov     rsi, [rbx+8]
0x180014cdd  mov     rax, [rsi]
0x180014ce0  mov     r14, [rax+30h]
0x180014ce4  mov     rcx, [rbx]
0x180014ce7  mov     [rbx], r15
0x180014cea  test    rcx, rcx
0x180014ced  jz      short loc_180014CFC
0x180014cef  mov     rdx, [rcx]
0x180014cf2  mov     rax, [rdx+10h]
0x180014cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cfb  nop
0x180014cfc  mov     rdx, rbx
0x180014cff  mov     rcx, rsi
0x180014d02  mov     rax, r14
0x180014d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d0a  mov     rcx, [rbp+5Fh]; this
0x180014d0e  test    eax, eax
0x180014d10  js      loc_180014F91
0x180014d16  mov     [rbp+57h+var_D0], r15
0x180014d1a  mov     rcx, [rbx+8]
0x180014d1e  mov     rax, [rcx]
0x180014d21  mov     [rbp+57h+var_D0], r15
0x180014d25  lea     rdx, [rbp+57h+var_D0]
0x180014d29  mov     rax, [rax+38h]
0x180014d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d32  mov     rcx, [rbp+5Fh]; this
0x180014d36  test    eax, eax
0x180014d38  js      loc_180014FA6
0x180014d3e  mov     rdx, [rbp+57h+var_D0]
0x180014d42  lea     rcx, [rsp+120h+var_D8]
0x180014d47  call    ??$wait_for_completion@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@V?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS)
0x180014d4c  nop
0x180014d4d  mov     [rsp+120h+var_F0], r15d
0x180014d52  mov     rcx, [rsp+120h+var_D8]
0x180014d57  mov     rax, [rcx]
0x180014d5a  lea     rdx, [rsp+120h+var_F0]
0x180014d5f  mov     rax, [rax+38h]
0x180014d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d68  mov     rcx, [rbp+5Fh]; this
0x180014d6c  test    eax, eax
0x180014d6e  js      loc_180014FBB
0x180014d74  mov     rdx, r15
0x180014d77  mov     [rsp+120h+var_E0], rdx
0x180014d7c  cmp     [rsp+120h+var_F0], 1
0x180014d81  jnz     short loc_180014DB1
0x180014d83  mov     rcx, [rsp+120h+var_D8]
0x180014d88  mov     rax, [rcx]
0x180014d8b  mov     [rsp+120h+var_E0], r15
0x180014d90  lea     r8, [rsp+120h+var_E0]
0x180014d95  xor     edx, edx
0x180014d97  mov     rax, [rax+30h]
0x180014d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014da0  mov     rcx, [rbp+5Fh]; this
0x180014da4  test    eax, eax
0x180014da6  js      loc_180014FD0
0x180014dac  mov     rdx, [rsp+120h+var_E0]
0x180014db1  lea     rcx, [rbp+57h+var_90]
0x180014db5  call    ?CacheForUser@UserCache@UserHelpers@@CA?AUCachedData@12@PEAUIUser@System@Windows@@@Z; UserHelpers::UserCache::CacheForUser(Windows::System::IUser *)
0x180014dba  lea     rcx, [rbx+20h]
0x180014dbe  mov     rdx, rax
0x180014dc1  call    ??4CachedData@UserCache@UserHelpers@@QEAAAEAU012@$$QEAU012@@Z; UserHelpers::UserCache::CachedData::operator=(UserHelpers::UserCache::CachedData &&)
0x180014dc6  lea     rcx, [rbp+57h+var_90]; this
0x180014dca  call    ??1CachedData@UserCache@UserHelpers@@QEAA@XZ; UserHelpers::UserCache::CachedData::~CachedData(void)
0x180014dcf  lea     rax, ?OnUserAdded@UserCache@UserHelpers@@AEAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@45@@Z; UserHelpers::UserCache::OnUserAdded(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)
0x180014dd6  mov     [rsp+120h+var_E8], rax
0x180014ddb  mov     [rbp+57h+var_B8], rbx
0x180014ddf  lea     r8, [rsp+120h+var_E8]
0x180014de4  lea     rdx, [rbp+57h+var_B8]
0x180014de8  lea     rcx, [rbp+57h+var_C0]
0x180014dec  call    ??$MakeAgileCallback@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@PEAVUserCache@UserHelpers@@P845@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@73@@_E@wil@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@@WRL@Microsoft@@$$QEAPEAVUserCache@UserHelpers@@$$QEAP845@EAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@78@@_E@Z
0x180014df1  nop
0x180014df2  mov     rax, [rbp+57h+var_C0]
0x180014df6  mov     qword ptr [rsp+120h+var_100], rax
0x180014dfb  lea     r9, ??_9IUserWatcher@System@Windows@@$BFA@AA; [thunk]: Windows::System::IUserWatcher::`vcall'{80,{flat}}
0x180014e02  lea     r8, ??_9IUserWatcher@System@Windows@@$BEI@AA; [thunk]: Windows::System::IUserWatcher::`vcall'{72,{flat}}
0x180014e09  mov     rdx, [rbx]
0x180014e0c  lea     rcx, [rbp+57h+var_B0]
0x180014e10  call    ??$make_unique_winrt_event_token@Uerr_exception_policy@wil@@UIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@ZPEAU675@@details@wil@@YA?AV?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@1@PEAUIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@Z1@Z; wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(Windows::System::IUserWatcher *,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *)
0x180014e15  lea     rcx, [rbx+68h]
0x180014e19  mov     rdx, rax
0x180014e1c  call    ??4?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::operator=(wil::unique_winrt_event_token<Windows::System::IUserWatcher> &&)
0x180014e21  lea     rcx, [rbp+57h+var_B0]
0x180014e25  call    ?reset@?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAXXZ; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset(void)
0x180014e2a  nop
0x180014e2b  mov     rcx, [rbp+57h+var_A8]
0x180014e2f  test    rcx, rcx
0x180014e32  jz      short loc_180014E41
0x180014e34  mov     rax, [rcx]
0x180014e37  mov     rax, [rax+10h]
0x180014e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e40  nop
0x180014e41  lea     rax, ?OnUserRemoved@UserCache@UserHelpers@@AEAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@45@@Z; UserHelpers::UserCache::OnUserRemoved(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)
0x180014e48  mov     [rbp+57h+var_B8], rax
0x180014e4c  mov     [rsp+120h+var_E8], rbx
0x180014e51  lea     r8, [rbp+57h+var_B8]
0x180014e55  lea     rdx, [rsp+120h+var_E8]
0x180014e5a  lea     rcx, [rbp+57h+var_C8]
0x180014e5e  call    ??$MakeAgileCallback@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@PEAVUserCache@UserHelpers@@P845@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@73@@_E@wil@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@@WRL@Microsoft@@$$QEAPEAVUserCache@UserHelpers@@$$QEAP845@EAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@78@@_E@Z
0x180014e63  nop
0x180014e64  mov     rax, qword ptr [rbp+57h+var_C8]
0x180014e68  mov     qword ptr [rsp+120h+var_100], rax; int
0x180014e6d  lea     r9, ??_9IUserWatcher@System@Windows@@$BGA@AA; [thunk]: Windows::System::IUserWatcher::`vcall'{96,{flat}}
0x180014e74  lea     r8, ??_9IUserWatcher@System@Windows@@$BFI@AA; [thunk]: Windows::System::IUserWatcher::`vcall'{88,{flat}}
0x180014e7b  mov     rdx, [rbx]
0x180014e7e  lea     rcx, [rbp+57h+var_B0]
0x180014e82  call    ??$make_unique_winrt_event_token@Uerr_exception_policy@wil@@UIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@ZPEAU675@@details@wil@@YA?AV?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@1@PEAUIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@Z1@Z; wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(Windows::System::IUserWatcher *,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *)
0x180014e87  lea     rcx, [rbx+80h]
0x180014e8e  mov     rdx, rax
0x180014e91  call    ??4?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::operator=(wil::unique_winrt_event_token<Windows::System::IUserWatcher> &&)
0x180014e96  lea     rcx, [rbp+57h+var_B0]
0x180014e9a  call    ?reset@?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAXXZ; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset(void)
0x180014e9f  nop
0x180014ea0  mov     rcx, [rbp+57h+var_A8]
0x180014ea4  test    rcx, rcx
0x180014ea7  jz      short loc_180014EB6
0x180014ea9  mov     rax, [rcx]
0x180014eac  mov     rax, [rax+10h]
0x180014eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb5  nop
0x180014eb6  mov     rcx, [rbx]
0x180014eb9  mov     rax, [rcx]
0x180014ebc  mov     rax, [rax+38h]
0x180014ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ec5  mov     rcx, [rbp+5Fh]; this
0x180014ec9  test    eax, eax
0x180014ecb  js      loc_180014F7C
0x180014ed1  mov     byte ptr [rbx+10h], 1
0x180014ed5  mov     rcx, qword ptr [rbp+57h+var_C8]
0x180014ed9  test    rcx, rcx
0x180014edc  jz      short loc_180014EEF
0x180014ede  mov     qword ptr [rbp+57h+var_C8], r15
0x180014ee2  mov     rax, [rcx]
0x180014ee5  mov     rax, [rax+10h]
0x180014ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eee  nop
0x180014eef  mov     rcx, [rbp+57h+var_C0]
0x180014ef3  test    rcx, rcx
0x180014ef6  jz      short loc_180014F09
0x180014ef8  mov     [rbp+57h+var_C0], r15
0x180014efc  mov     rax, [rcx]
0x180014eff  mov     rax, [rax+10h]
0x180014f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f08  nop
0x180014f09  mov     rcx, [rsp+120h+var_E0]
0x180014f0e  test    rcx, rcx
0x180014f11  jz      short loc_180014F20
0x180014f13  mov     rax, [rcx]
0x180014f16  mov     rax, [rax+10h]
0x180014f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f1f  nop
0x180014f20  mov     rcx, [rsp+120h+var_D8]
0x180014f25  test    rcx, rcx
0x180014f28  jz      short loc_180014F3C
0x180014f2a  mov     [rsp+120h+var_D8], r15
0x180014f2f  mov     rax, [rcx]
0x180014f32  mov     rax, [rax+10h]
0x180014f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f3b  nop
0x180014f3c  mov     rcx, [rbp+57h+var_D0]
0x180014f40  test    rcx, rcx
0x180014f43  jz      short loc_180014F52
0x180014f45  mov     rax, [rcx]
0x180014f48  mov     rax, [rax+10h]
0x180014f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f51  nop
0x180014f52  test    rdi, rdi
0x180014f55  jz      short loc_180014F60
0x180014f57  mov     rcx, rdi; SRWLock
0x180014f5a  call    cs:__imp_ReleaseSRWLockExclusive
0x180014f60  mov     rcx, [rbp+57h+var_40]
0x180014f64  xor     rcx, rsp; StackCookie
0x180014f67  call    __security_check_cookie
0x180014f6c  add     rsp, 0F8h
0x180014f73  pop     r15
0x180014f75  pop     r14
0x180014f77  pop     rdi
0x180014f78  pop     rsi
0x180014f79  pop     rbx
0x180014f7a  pop     rbp
0x180014f7b  retn
0x180014f7c  mov     r9d, eax; char *
0x180014f7f  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014f86  mov     edx, 89h; void *
0x180014f8b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014f91  mov     r9d, eax; char *
0x180014f94  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014f9b  mov     edx, 6Fh ; 'o'; void *
0x180014fa0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014fa6  mov     r9d, eax; char *
0x180014fa9  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014fb0  mov     edx, 74h ; 't'; void *
0x180014fb5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014fbb  mov     r9d, eax; char *
0x180014fbe  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014fc5  mov     edx, 79h ; 'y'; void *
0x180014fca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014fd0  mov     r9d, eax; char *
0x180014fd3  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014fda  mov     edx, 7Eh ; '~'; void *
0x180014fdf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
