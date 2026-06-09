# UserAccountStore::DeleteUserAccount(IUserAccount *,bool *)

- ea: `0x180015ee0`
- end: `0x1800162fd`
- name: `?DeleteUserAccount@UserAccountStore@@UEAAJPEAUIUserAccount@@PEA_N@Z`
- size: `1053`
- prototype: `__int64 __fastcall(UserAccountStore *__hidden this, struct IUserAccount *, bool *)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000cca0`
- `0x18000ccd4`
- `0x18000cd50`
- `0x180012294`
- `0x18001415c`
- `0x1800150e8`
- `0x180015490`
- `0x1800154cc`
- `0x180015524`
- `0x1800155b4`
- `0x18001560c`
- `0x180015ee0`
- `0x180016460`
- `0x1800170ec`
- `0x180018190`
- `0x180018348`
- `0x1800184ac`
- `0x180018564`
- `0x18001873c`
- `0x180019500`
- `0x180019b18`
- `0x180023228`
- `0x180023584`
- `0x180026010`

## string_xrefs

- `0x180015f0a`: `DeleteUserAccount`
- `0x180016088`: `PolicyDrivenUserDelete`
- `0x1800161f4`: `PolicyDrivenAccountDelete`
- `0x180015f62`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180015fae`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180015ff6`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x18001603a`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180016077`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180016109`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180016175`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x18001624f`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserAccountStore::DeleteUserAccount(UserAccountStore *this, struct IUserAccount *a2, bool *a3)
{
  int v6; // eax
  __int64 (__fastcall *v7)(struct IUserAccount *, unsigned __int16 **); // rbx
  int v8; // eax
  char v9; // bl
  const char *v10; // r9
  char v11; // bl
  const char *v12; // r9
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // edi
  __int64 (__fastcall *v17)(struct IUserAccount *, __int64 *); // rbx
  int v18; // eax
  unsigned int UserIdFromSid; // ebx
  int v20; // eax
  unsigned int v22; // [rsp+20h] [rbp-468h] BYREF
  unsigned __int16 *v23; // [rsp+28h] [rbp-460h] BYREF
  __int64 v24; // [rsp+30h] [rbp-458h] BYREF
  _BYTE v25[40]; // [rsp+38h] [rbp-450h] BYREF
  _QWORD v26[42]; // [rsp+60h] [rbp-428h] BYREF
  _QWORD v27[42]; // [rsp+1B0h] [rbp-2D8h] BYREF
  _QWORD v28[42]; // [rsp+300h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v28,
    "DeleteUserAccount");
  v28[0] = &AccountsTelemetry::DeleteUserAccount::`vftable';
  AccountsTelemetry::DeleteUserAccount::StartActivity((AccountsTelemetry::DeleteUserAccount *)v28);
  *a3 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IUserAccount *, __int64))(*(_QWORD *)a2 + 88LL))(a2, 1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      (const char *)(unsigned int)v6,
      v22);
  v23 = 0;
  v7 = *(__int64 (__fastcall **)(struct IUserAccount *, unsigned __int16 **))(*(_QWORD *)a2 + 24LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v23,
    0);
  v8 = v7(a2, &v23);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      (const char *)(unsigned int)v8,
      v22);
  std::wstring::wstring(v25, v23);
  v9 = IsWCOSUserModelSpecialAccount(7, v25);
  std::wstring::_Tidy_deallocate(v25);
  if ( v9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x80,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      v10);
  std::wstring::wstring(v25, v23);
  v11 = IsCandidateUserSpecialAccount(v25);
  std::wstring::_Tidy_deallocate(v25);
  if ( v11 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x83,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      v12);
  v22 = 0;
  v13 = (*(__int64 (__fastcall **)(struct IUserAccount *, unsigned int *))(*(_QWORD *)a2 + 40LL))(a2, &v22);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      (const char *)(unsigned int)v13,
      v22);
  wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v26,
    "PolicyDrivenUserDelete");
  v26[0] = &AccountManagerUserModelTelemetry::PolicyDrivenUserDelete::`vftable';
  AccountManagerUserModelTelemetry::PolicyDrivenUserDelete::StartActivity(
    (AccountManagerUserModelTelemetry::PolicyDrivenUserDelete *)v26,
    v22);
  v14 = DoDeleteProfile((const struct _GUID *)(v26[34] + 8LL), v23);
  if ( v14 == -2147024751 || v14 == -2147024864 || v14 == -2147024846 || v14 == -2147023174 || v14 == -2147023179 )
  {
    v16 = UserAccountStore::VerifyAccountState(v15, v23);
    if ( v16 == 1 )
      goto LABEL_33;
  }
  else if ( v14 == -2147024894 )
  {
    v16 = 2;
  }
  else
  {
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
        (const char *)(unsigned int)v14,
        v22);
    v16 = 0;
  }
  if ( v22 == 1 )
  {
    v24 = 0;
    v17 = *(__int64 (__fastcall **)(struct IUserAccount *, __int64 *))(*(_QWORD *)a2 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v24,
      0);
    v18 = v17(a2, &v24);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
        (const char *)(unsigned int)v18,
        v22);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 11) + 48LL))(*((_QWORD *)this + 11), v24);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
  }
  else if ( v22 == 2 )
  {
    wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(&v24);
    std::wstring::wstring(v25, v23);
    UserIdFromSid = GetUserIdFromSid(v24, v25);
    std::wstring::_Tidy_deallocate(v25);
    if ( UserIdFromSid )
    {
      wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        v27,
        "PolicyDrivenAccountDelete");
      v27[0] = &AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::`vftable';
      AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::StartActivity(
        (AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete *)v27,
        UserIdFromSid);
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, UserIdFromSid);
      if ( v20 != -2147024846 && v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v20,
          v22);
      wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v27);
      AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::~PolicyDrivenAccountDelete((AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete *)v27);
    }
    wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(&v24);
  }
LABEL_33:
  wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v26);
  AccountsTelemetry::DeleteUserAccount::Stop(v28, v23, v22, v16);
  *a3 = v16 == 0;
  AccountManagerUserModelTelemetry::PolicyDrivenUserDelete::~PolicyDrivenUserDelete((AccountManagerUserModelTelemetry::PolicyDrivenUserDelete *)v26);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
  AccountsTelemetry::DeleteUserAccount::~DeleteUserAccount((AccountsTelemetry::DeleteUserAccount *)v28);
  return 0;
}

```

## disassembly

```asm
0x180015ee0  push    rbx
0x180015ee2  push    rsi
0x180015ee3  push    rdi
0x180015ee4  push    r14
0x180015ee6  push    r15
0x180015ee8  sub     rsp, 460h
0x180015eef  mov     rax, cs:__security_cookie
0x180015ef6  xor     rax, rsp
0x180015ef9  mov     [rsp+488h+var_38], rax
0x180015f01  mov     r15, r8
0x180015f04  mov     rsi, rdx
0x180015f07  mov     r14, rcx
0x180015f0a  lea     rdx, aDeleteuseracco; "DeleteUserAccount"
0x180015f11  lea     rcx, [rsp+488h+var_188]
0x180015f19  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015f1e  lea     rax, ??_7DeleteUserAccount@AccountsTelemetry@@6B@; const AccountsTelemetry::DeleteUserAccount::`vftable'
0x180015f25  mov     [rsp+488h+var_188], rax
0x180015f2d  lea     rcx, [rsp+488h+var_188]; this
0x180015f35  call    ?StartActivity@DeleteUserAccount@AccountsTelemetry@@QEAAXXZ; AccountsTelemetry::DeleteUserAccount::StartActivity(void)
0x180015f3a  nop
0x180015f3b  mov     byte ptr [r15], 0
0x180015f3f  mov     rax, [rsi]
0x180015f42  mov     edx, 1
0x180015f47  mov     rcx, rsi
0x180015f4a  mov     rax, [rax+58h]
0x180015f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f53  mov     rcx, [rsp+488h]; this
0x180015f5b  test    eax, eax
0x180015f5d  jns     short loc_180015F73
0x180015f5f  mov     r9d, eax; char *
0x180015f62  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015f69  mov     edx, 77h ; 'w'; void *
0x180015f6e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015f73  mov     [rsp+488h+var_460], 0
0x180015f7c  mov     rax, [rsi]
0x180015f7f  mov     rbx, [rax+18h]
0x180015f83  xor     edx, edx
0x180015f85  lea     rcx, [rsp+488h+var_460]
0x180015f8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015f8f  lea     rdx, [rsp+488h+var_460]
0x180015f94  mov     rcx, rsi
0x180015f97  mov     rax, rbx
0x180015f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f9f  mov     rcx, [rsp+488h]; this
0x180015fa7  test    eax, eax
0x180015fa9  jns     short loc_180015FBF
0x180015fab  mov     r9d, eax; char *
0x180015fae  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015fb5  mov     edx, 7Ah ; 'z'; void *
0x180015fba  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015fbf  mov     rdx, [rsp+488h+var_460]
0x180015fc4  lea     rcx, [rsp+488h+var_450]
0x180015fc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015fce  nop
0x180015fcf  lea     rdx, [rsp+488h+var_450]
0x180015fd4  mov     ecx, 7
0x180015fd9  call    ?IsWCOSUserModelSpecialAccount@@YA_NW4SpecialAccountTypes@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsWCOSUserModelSpecialAccount(SpecialAccountTypes,std::wstring const &)
0x180015fde  mov     bl, al
0x180015fe0  lea     rcx, [rsp+488h+var_450]
0x180015fe5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015fea  mov     rcx, [rsp+488h]; this
0x180015ff2  test    bl, bl
0x180015ff4  jz      short loc_180016008
0x180015ff6  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015ffd  mov     edx, 80h; void *
0x180016002  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016008  mov     rdx, [rsp+488h+var_460]
0x18001600d  lea     rcx, [rsp+488h+var_450]
0x180016012  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016017  nop
0x180016018  lea     rcx, [rsp+488h+var_450]
0x18001601d  call    ?IsCandidateUserSpecialAccount@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsCandidateUserSpecialAccount(std::wstring const &)
0x180016022  mov     bl, al
0x180016024  lea     rcx, [rsp+488h+var_450]
0x180016029  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001602e  mov     rcx, [rsp+488h]; this
0x180016036  test    bl, bl
0x180016038  jz      short loc_18001604C
0x18001603a  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016041  mov     edx, 83h; void *
0x180016046  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001604c  mov     [rsp+488h+var_468], 0; int
0x180016054  mov     rax, [rsi]
0x180016057  lea     rdx, [rsp+488h+var_468]
0x18001605c  mov     rcx, rsi
0x18001605f  mov     rax, [rax+28h]
0x180016063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016068  mov     rcx, [rsp+488h]; this
0x180016070  test    eax, eax
0x180016072  jns     short loc_180016088
0x180016074  mov     r9d, eax; char *
0x180016077  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001607e  mov     edx, 86h; void *
0x180016083  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016088  lea     rdx, aPolicydrivenus; "PolicyDrivenUserDelete"
0x18001608f  lea     rcx, [rsp+488h+var_428]
0x180016094  call    ??0?$ActivityBase@VAccountManagerUserModelTelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016099  lea     rax, ??_7PolicyDrivenUserDelete@AccountManagerUserModelTelemetry@@6B@; const AccountManagerUserModelTelemetry::PolicyDrivenUserDelete::`vftable'
0x1800160a0  mov     [rsp+488h+var_428], rax
0x1800160a5  mov     edx, [rsp+488h+var_468]; unsigned int
0x1800160a9  lea     rcx, [rsp+488h+var_428]; this
0x1800160ae  call    ?StartActivity@PolicyDrivenUserDelete@AccountManagerUserModelTelemetry@@QEAAXI@Z; AccountManagerUserModelTelemetry::PolicyDrivenUserDelete::StartActivity(uint)
0x1800160b3  mov     rcx, [rsp+488h+var_318]
0x1800160bb  add     rcx, 8; struct _GUID *
0x1800160bf  mov     rdx, [rsp+488h+var_460]; unsigned __int16 *
0x1800160c4  call    ?DoDeleteProfile@@YAJAEBU_GUID@@PEBG@Z; DoDeleteProfile(_GUID const &,ushort const *)
0x1800160c9  cmp     eax, 80070091h
0x1800160ce  jz      short loc_18001611E
0x1800160d0  cmp     eax, 80070020h
0x1800160d5  jz      short loc_18001611E
0x1800160d7  cmp     eax, 80070032h
0x1800160dc  jz      short loc_18001611E
0x1800160de  cmp     eax, 800706BAh
0x1800160e3  jz      short loc_18001611E
0x1800160e5  cmp     eax, 800706B5h
0x1800160ea  jz      short loc_18001611E
0x1800160ec  cmp     eax, 80070002h
0x1800160f1  jnz     short loc_1800160FA
0x1800160f3  mov     edi, 2
0x1800160f8  jmp     short loc_180016133
0x1800160fa  mov     rcx, [rsp+488h]; this
0x180016102  test    eax, eax
0x180016104  jns     short loc_18001611A
0x180016106  mov     r9d, eax; char *
0x180016109  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016110  mov     edx, 0A5h; void *
0x180016115  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001611a  xor     edi, edi
0x18001611c  jmp     short loc_180016133
0x18001611e  mov     rdx, [rsp+488h+var_460]
0x180016123  call    ?VerifyAccountState@UserAccountStore@@AEAA?AW4AccountDeleteState@@PEBG@Z; UserAccountStore::VerifyAccountState(ushort const *)
0x180016128  mov     edi, eax
0x18001612a  cmp     eax, 1
0x18001612d  jz      loc_180016286
0x180016133  cmp     [rsp+488h+var_468], 1
0x180016138  jnz     short loc_1800161AB
0x18001613a  mov     [rsp+488h+var_458], 0
0x180016143  mov     rax, [rsi]
0x180016146  mov     rbx, [rax+20h]
0x18001614a  xor     edx, edx
0x18001614c  lea     rcx, [rsp+488h+var_458]
0x180016151  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180016156  lea     rdx, [rsp+488h+var_458]
0x18001615b  mov     rcx, rsi
0x18001615e  mov     rax, rbx
0x180016161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016166  mov     rcx, [rsp+488h]; this
0x18001616e  test    eax, eax
0x180016170  jns     short loc_180016186
0x180016172  mov     r9d, eax; char *
0x180016175  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001617c  mov     edx, 0AFh; void *
0x180016181  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016186  mov     rcx, [r14+58h]
0x18001618a  mov     rax, [rcx]
0x18001618d  mov     rdx, [rsp+488h+var_458]
0x180016192  mov     rax, [rax+30h]
0x180016196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001619b  nop
0x18001619c  lea     rcx, [rsp+488h+var_458]
0x1800161a1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800161a6  jmp     loc_180016286
0x1800161ab  cmp     [rsp+488h+var_468], 2
0x1800161b0  jnz     loc_180016286
0x1800161b6  lea     rcx, [rsp+488h+var_458]
0x1800161bb  call    ??$GetActivationFactory@UIUserManagerStatics@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserManagerStatics@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(ushort const *)
0x1800161c0  nop
0x1800161c1  mov     rdx, [rsp+488h+var_460]
0x1800161c6  lea     rcx, [rsp+488h+var_450]
0x1800161cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800161d0  nop
0x1800161d1  lea     rdx, [rsp+488h+var_450]
0x1800161d6  mov     rcx, [rsp+488h+var_458]
0x1800161db  call    ?GetUserIdFromSid@@YAIPEAUIUserManagerStatics@Internal@System@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetUserIdFromSid(Windows::System::Internal::IUserManagerStatics *,std::wstring const &)
0x1800161e0  mov     ebx, eax
0x1800161e2  lea     rcx, [rsp+488h+var_450]
0x1800161e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800161ec  test    ebx, ebx
0x1800161ee  jz      loc_18001627C
0x1800161f4  lea     rdx, aPolicydrivenac; "PolicyDrivenAccountDelete"
0x1800161fb  lea     rcx, [rsp+488h+var_2D8]
0x180016203  call    ??0?$ActivityBase@VAccountManagerUserModelTelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016208  lea     rax, ??_7PolicyDrivenAccountDelete@AccountManagerUserModelTelemetry@@6B@; const AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::`vftable'
0x18001620f  mov     [rsp+488h+var_2D8], rax
0x180016217  mov     edx, ebx; unsigned int
0x180016219  lea     rcx, [rsp+488h+var_2D8]; this
0x180016221  call    ?StartActivity@PolicyDrivenAccountDelete@AccountManagerUserModelTelemetry@@QEAAXI@Z; AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::StartActivity(uint)
0x180016226  mov     rcx, [rsp+488h+var_458]
0x18001622b  mov     rax, [rcx]
0x18001622e  mov     edx, ebx
0x180016230  mov     rax, [rax+48h]
0x180016234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016239  cmp     eax, 80070032h
0x18001623e  jz      short loc_180016260
0x180016240  mov     rcx, [rsp+488h]; this
0x180016248  test    eax, eax
0x18001624a  jns     short loc_180016260
0x18001624c  mov     r9d, eax; char *
0x18001624f  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016256  mov     edx, 0C2h; void *
0x18001625b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016260  lea     rcx, [rsp+488h+var_2D8]
0x180016268  call    ?Stop@?$ActivityBase@VAccountManagerUserModelTelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001626d  nop
0x18001626e  lea     rcx, [rsp+488h+var_2D8]; this
0x180016276  call    ??1PolicyDrivenAccountDelete@AccountManagerUserModelTelemetry@@QEAA@XZ; AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::~PolicyDrivenAccountDelete(void)
0x18001627b  nop
0x18001627c  lea     rcx, [rsp+488h+var_458]
0x180016281  call    ??1?$com_ptr_t@UIUserProfile2@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(void)
0x180016286  lea     rcx, [rsp+488h+var_428]
0x18001628b  call    ?Stop@?$ActivityBase@VAccountManagerUserModelTelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180016290  mov     r9d, edi
0x180016293  mov     r8d, [rsp+488h+var_468]
0x180016298  mov     rdx, [rsp+488h+var_460]
0x18001629d  lea     rcx, [rsp+488h+var_188]
0x1800162a5  call    ?Stop@DeleteUserAccount@AccountsTelemetry@@QEAAXPEBGW4AccountType@@W4AccountDeleteState@@@Z; AccountsTelemetry::DeleteUserAccount::Stop(ushort const *,AccountType,AccountDeleteState)
0x1800162aa  test    edi, edi
0x1800162ac  setz    al
0x1800162af  mov     [r15], al
0x1800162b2  lea     rcx, [rsp+488h+var_428]; this
0x1800162b7  call    ??1PolicyDrivenUserDelete@AccountManagerUserModelTelemetry@@QEAA@XZ; AccountManagerUserModelTelemetry::PolicyDrivenUserDelete::~PolicyDrivenUserDelete(void)
0x1800162bc  nop
0x1800162bd  lea     rcx, [rsp+488h+var_460]
0x1800162c2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800162c7  nop
0x1800162c8  lea     rcx, [rsp+488h+var_188]; this
0x1800162d0  call    ??1DeleteUserAccount@AccountsTelemetry@@QEAA@XZ; AccountsTelemetry::DeleteUserAccount::~DeleteUserAccount(void)
0x1800162d5  xor     eax, eax
0x1800162d7  jmp     short loc_1800162DD
0x1800162d9  mov     eax, [rsp+488h+var_468]
0x1800162dd  mov     rcx, [rsp+488h+var_38]
0x1800162e5  xor     rcx, rsp; StackCookie
0x1800162e8  call    __security_check_cookie
0x1800162ed  add     rsp, 460h
0x1800162f4  pop     r15
0x1800162f6  pop     r14
0x1800162f8  pop     rdi
0x1800162f9  pop     rsi
0x1800162fa  pop     rbx
0x1800162fb  retn
```
