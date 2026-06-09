# SRAddPackageDependency

- ea: `0x180010b00`
- end: `0x180010e3b`
- name: `SRAddPackageDependency`
- size: `827`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800075e4`
- `0x180009530`
- `0x18000eb98`
- `0x1800100b8`
- `0x1800100fc`
- `0x1800105ac`
- `0x180010854`
- `0x180010878`
- `0x1800108b4`
- `0x1800109d0`
- `0x180010ad4`
- `0x180010b00`
- `0x180011ca0`
- `0x180025f74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010b9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010c62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010b9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010c62`
- `ext-ms-onecore-appmodel-deployment-internal-l1-1-0!MsixEnsurePackageIsRegistered` at `0x180010c39`
- `ext-ms-onecore-appmodel-deployment-internal-l1-1-0!MsixEnsurePackageIsRegistered` at `0x180010d2e`
- `ext-ms-onecore-appmodel-deployment-internal-l1-1-0!MsixEnsurePackageIsRegistered` at `0x180010c39`
- `ext-ms-onecore-appmodel-deployment-internal-l1-1-0!MsixEnsurePackageIsRegistered` at `0x180010d2e`
- `ext-ms-onecore-appmodel-deployment-internal-l1-1-1!MsixIsPackageRegistrationPending` at `0x180010cdf`
- `ext-ms-onecore-appmodel-deployment-internal-l1-1-1!MsixIsPackageRegistrationPending` at `0x180010cdf`

## pseudocode

```c
__int64 __fastcall SRAddPackageDependency(char *a1, int a2, _QWORD *a3, const unsigned __int16 *a4)
{
  int v8; // eax
  unsigned int v9; // edi
  unsigned int v11; // edi
  unsigned __int16 **v12; // r8
  int IsRegistered; // eax
  __int64 v14; // rdx
  unsigned int v15; // edi
  __int64 v16; // rdx
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-50h]
  unsigned int v19; // [rsp+20h] [rbp-50h]
  int v20; // [rsp+40h] [rbp-30h] BYREF
  wil *v21; // [rsp+48h] [rbp-28h] BYREF
  RTL_SRWLOCK *v22; // [rsp+50h] [rbp-20h] BYREF
  wil **v23; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v24[2]; // [rsp+60h] [rbp-10h] BYREF
  char v25; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v27; // [rsp+B0h] [rbp+40h] BYREF
  int v28; // [rsp+B8h] [rbp+48h] BYREF

  *a3 = 0;
  *(_QWORD *)a4 = 0;
  v8 = StateRepository::RPC::Client::PrepareBindingHandle();
  v9 = v8;
  if ( v8 >= 0 )
  {
    v21 = 0;
    while ( 1 )
    {
      while ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_DontAddToDependencyGraphUntilPendingRegistrationsAreComplete>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DontAddToDependencyGraphUntilPendingRegistrationsAreComplete>::GetImpl'::`2'::impl) )
      {
        wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(&v21);
        v28 = 0;
        AcquireSRWLockExclusive(&StateRepository::RPC::Client::s_bindingLock);
        v22 = &StateRepository::RPC::Client::s_bindingLock;
        v23 = &v21;
        *(_QWORD *)v24 = 0;
        v25 = 1;
        v11 = rpcclient_PackageDependency_Add((_DWORD)a1, a2, 9, (_DWORD)a3, (__int64)v24, (__int64)&v28);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>((__int64)&v23);
        if ( v11 )
        {
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0xB4,
                 (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_rpc.cpp",
                 (const char *)v11,
                 v19);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
          goto LABEL_27;
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
        if ( (v28 & 1) == 0 )
          goto LABEL_21;
        wil::details::in1diag3::Log_Win32Msg(
          retaddr,
          (void *)0xBB,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_rpc.cpp",
          (const char *)0x3D0F,
          (unsigned int)"AddPackageDependency: PackageDependencyId:%ls PackageFullName:%ls",
          a1);
        IsRegistered = MsixEnsurePackageIsRegistered(v21);
        v9 = IsRegistered;
        if ( IsRegistered < 0 )
        {
          v14 = 188;
          goto LABEL_26;
        }
      }
      wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(&v21);
      v27 = 0;
      AcquireSRWLockExclusive(&StateRepository::RPC::Client::s_bindingLock);
      v22 = &StateRepository::RPC::Client::s_bindingLock;
      v23 = &v21;
      *(_QWORD *)v24 = 0;
      v25 = 1;
      v15 = rpcclient_PackageDependency_Add((_DWORD)a1, a2, 9, (_DWORD)a3, (__int64)v24, (__int64)&v27);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>((__int64)&v23);
      if ( v15 )
        break;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
      if ( (v27 & 1) == 0 )
      {
        if ( (v27 & 2) == 0 )
          goto LABEL_21;
        v20 = 0;
        IsRegistered = MsixIsPackageRegistrationPending(0, v21, &v20);
        v9 = IsRegistered;
        if ( IsRegistered < 0 )
        {
          v14 = 215;
          goto LABEL_26;
        }
        if ( !v20 )
        {
LABEL_21:
          IsRegistered = wil::make_nullable_process_heap_string_nothrow(v21, a4, v12);
          v9 = IsRegistered;
          if ( IsRegistered >= 0 )
          {
            wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(&v21);
            return 0;
          }
          v14 = 251;
LABEL_26:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_rpc.cpp",
            (const char *)(unsigned int)IsRegistered,
            v19);
LABEL_27:
          wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(&v21);
          return v9;
        }
      }
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_rpc.cpp",
        (const char *)0x3D0F,
        (unsigned int)"AddPackageDependency: PackageDependencyId:%ls PackageFullName:%ls",
        a1,
        v21);
      IsRegistered = MsixEnsurePackageIsRegistered(v21);
      v9 = IsRegistered;
      if ( IsRegistered < 0 )
      {
        v14 = 224;
        goto LABEL_26;
      }
      LOBYTE(v16) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_DynamicDependencies_OnDemandRegistration>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_StateRepository_DynamicDependencies_OnDemandRegistration>::GetImpl'::`2'::impl,
        v16);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeededPublicApi>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeededPublicApi>::GetImpl'::`2'::impl) )
      {
        IsRegistered = SRRemovePackageDependency(*a3);
        v9 = IsRegistered;
        if ( IsRegistered < 0 )
        {
          v14 = 239;
          goto LABEL_26;
        }
        *a3 = 0;
      }
    }
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xCE,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_rpc.cpp",
            (const char *)v15,
            v19);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
    wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(&v21);
    return v17;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_rpc.cpp",
      (const char *)(unsigned int)v8,
      v18);
    return v9;
  }
}

```

## disassembly

```asm
0x180010b00  mov     [rsp-28h+arg_0], rbx
0x180010b05  mov     [rsp-28h+arg_8], rsi
0x180010b0a  push    rbp
0x180010b0b  push    rdi
0x180010b0c  push    r12
0x180010b0e  push    r14
0x180010b10  push    r15
0x180010b12  mov     rbp, rsp
0x180010b15  sub     rsp, 70h
0x180010b19  mov     qword ptr [r8], 0
0x180010b20  mov     r14, r9
0x180010b23  mov     qword ptr [r9], 0
0x180010b2a  mov     rsi, r8
0x180010b2d  mov     r12d, edx
0x180010b30  mov     r15, rcx
0x180010b33  call    ?PrepareBindingHandle@Client@RPC@StateRepository@@SAJXZ; StateRepository::RPC::Client::PrepareBindingHandle(void)
0x180010b38  mov     edi, eax
0x180010b3a  test    eax, eax
0x180010b3c  jns     short loc_180010B5D
0x180010b3e  mov     rcx, [rbp+28h]; this
0x180010b42  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180010b49  mov     r9d, eax; char *
0x180010b4c  mov     edx, 0A8h; void *
0x180010b51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b56  mov     eax, edi
0x180010b58  jmp     loc_180010E22
0x180010b5d  mov     [rbp+var_28], 0
0x180010b65  lea     rbx, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180010b6c  lea     rdi, ?s_bindingLock@Client@RPC@StateRepository@@2Vsrwlock@wil@@A; wil::srwlock StateRepository::RPC::Client::s_bindingLock
0x180010b73  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DontAddToDependencyGraphUntilPendingRegistrationsAreComplete@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DontAddToDependencyGraphUntilPendingRegistrationsAreComplete@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DontAddToDependencyGraphUntilPendingRegistrationsAreComplete> `wil::Feature<__WilFeatureTraits_Feature_DontAddToDependencyGraphUntilPendingRegistrationsAreComplete>::GetImpl(void)'::`2'::impl
0x180010b7a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DontAddToDependencyGraphUntilPendingRegistrationsAreComplete@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DontAddToDependencyGraphUntilPendingRegistrationsAreComplete>::__private_IsEnabled(void)
0x180010b7f  lea     rcx, [rbp+var_28]
0x180010b83  test    al, al
0x180010b85  jz      loc_180010C53
0x180010b8b  call    ?reset@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(std::nullptr_t)
0x180010b90  mov     rcx, rdi; SRWLock
0x180010b93  mov     [rbp+arg_18], 0
0x180010b9a  call    cs:__imp_AcquireSRWLockExclusive
0x180010ba0  lea     rax, [rbp+var_28]
0x180010ba4  mov     [rbp+var_20], rdi
0x180010ba8  mov     [rbp+var_18], rax
0x180010bac  mov     r9, rsi
0x180010baf  lea     rax, [rbp+arg_18]
0x180010bb3  mov     qword ptr [rbp+var_10], 0
0x180010bbb  mov     [rsp+70h+var_48], rax
0x180010bc0  mov     r8d, 9
0x180010bc6  lea     rax, [rbp+var_10]
0x180010bca  mov     [rbp+var_8], 1
0x180010bce  mov     edx, r12d
0x180010bd1  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x180010bd6  mov     rcx, r15
0x180010bd9  call    rpcclient_PackageDependency_Add
0x180010bde  lea     rcx, [rbp+var_18]
0x180010be2  mov     edi, eax
0x180010be4  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>(void)
0x180010be9  test    edi, edi
0x180010beb  jnz     loc_180010D81
0x180010bf1  lea     rcx, [rbp+var_20]
0x180010bf5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010bfa  test    byte ptr [rbp+arg_18], 1
0x180010bfe  jz      loc_180010DA9
0x180010c04  mov     rax, [rbp+var_28]
0x180010c08  mov     r9d, 3D0Fh; char *
0x180010c0e  mov     rcx, [rbp+28h]; this
0x180010c12  mov     r8, rbx; unsigned int
0x180010c15  mov     [rsp+70h+var_40], rax
0x180010c1a  mov     edx, 0BBh; void *
0x180010c1f  lea     rax, aAddpackagedepe; "AddPackageDependency: PackageDependency"...
0x180010c26  mov     [rsp+70h+var_48], r15; char *
0x180010c2b  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x180010c30  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180010c35  mov     rcx, [rbp+var_28]
0x180010c39  call    cs:__imp_MsixEnsurePackageIsRegistered
0x180010c3f  mov     edi, eax
0x180010c41  test    eax, eax
0x180010c43  jns     loc_180010B6C
0x180010c49  mov     edx, 0BCh
0x180010c4e  jmp     loc_180010DDB
0x180010c53  call    ?reset@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(std::nullptr_t)
0x180010c58  mov     rcx, rdi; SRWLock
0x180010c5b  mov     [rbp+arg_10], 0
0x180010c62  call    cs:__imp_AcquireSRWLockExclusive
0x180010c68  lea     rax, [rbp+var_28]
0x180010c6c  mov     [rbp+var_20], rdi
0x180010c70  mov     [rbp+var_18], rax
0x180010c74  mov     r9, rsi
0x180010c77  lea     rax, [rbp+arg_10]
0x180010c7b  mov     qword ptr [rbp+var_10], 0
0x180010c83  mov     [rsp+70h+var_48], rax
0x180010c88  mov     r8d, 9
0x180010c8e  lea     rax, [rbp+var_10]
0x180010c92  mov     [rbp+var_8], 1
0x180010c96  mov     edx, r12d
0x180010c99  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x180010c9e  mov     rcx, r15
0x180010ca1  call    rpcclient_PackageDependency_Add
0x180010ca6  lea     rcx, [rbp+var_18]
0x180010caa  mov     edi, eax
0x180010cac  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>(void)
0x180010cb1  test    edi, edi
0x180010cb3  jnz     loc_180010DF8
0x180010cb9  lea     rcx, [rbp+var_20]
0x180010cbd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010cc2  test    byte ptr [rbp+arg_10], 1
0x180010cc6  jnz     short loc_180010CF9
0x180010cc8  test    byte ptr [rbp+arg_10], 2
0x180010ccc  jz      loc_180010DA9
0x180010cd2  mov     rdx, [rbp+var_28]
0x180010cd6  lea     r8, [rbp+var_30]
0x180010cda  xor     ecx, ecx
0x180010cdc  mov     [rbp+var_30], edi
0x180010cdf  call    cs:__imp_MsixIsPackageRegistrationPending
0x180010ce5  mov     edi, eax
0x180010ce7  test    eax, eax
0x180010ce9  js      loc_180010DA2
0x180010cef  cmp     [rbp+var_30], 0
0x180010cf3  jz      loc_180010DA9
0x180010cf9  mov     rax, [rbp+var_28]
0x180010cfd  mov     r9d, 3D0Fh; char *
0x180010d03  mov     rcx, [rbp+28h]; this
0x180010d07  mov     r8, rbx; unsigned int
0x180010d0a  mov     [rsp+70h+var_40], rax
0x180010d0f  mov     edx, 0DFh; void *
0x180010d14  lea     rax, aAddpackagedepe; "AddPackageDependency: PackageDependency"...
0x180010d1b  mov     [rsp+70h+var_48], r15; char *
0x180010d20  mov     qword ptr [rsp+70h+var_50], rax; int
0x180010d25  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180010d2a  mov     rcx, [rbp+var_28]
0x180010d2e  call    cs:__imp_MsixEnsurePackageIsRegistered
0x180010d34  mov     edi, eax
0x180010d36  test    eax, eax
0x180010d38  js      loc_180010DD6
0x180010d3e  mov     dl, 1
0x180010d40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StateRepository_DynamicDependencies_OnDemandRegistration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_DynamicDependencies_OnDemandRegistration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_DynamicDependencies_OnDemandRegistration> `wil::Feature<__WilFeatureTraits_Feature_StateRepository_DynamicDependencies_OnDemandRegistration>::GetImpl(void)'::`2'::impl
0x180010d47  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_DynamicDependencies_OnDemandRegistration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_DynamicDependencies_OnDemandRegistration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180010d4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeededPublicApi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeededPublicApi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeededPublicApi> `wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeededPublicApi>::GetImpl(void)'::`2'::impl
0x180010d53  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeededPublicApi@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeededPublicApi>::__private_IsEnabled(void)
0x180010d58  lea     rdi, ?s_bindingLock@Client@RPC@StateRepository@@2Vsrwlock@wil@@A; wil::srwlock StateRepository::RPC::Client::s_bindingLock
0x180010d5f  test    al, al
0x180010d61  jz      loc_180010B73
0x180010d67  mov     rcx, [rsi]
0x180010d6a  call    SRRemovePackageDependency
0x180010d6f  mov     edi, eax
0x180010d71  test    eax, eax
0x180010d73  js      short loc_180010DCF
0x180010d75  mov     qword ptr [rsi], 0
0x180010d7c  jmp     loc_180010B6C
0x180010d81  mov     rcx, [rbp+28h]; this
0x180010d85  mov     r9d, edi; char *
0x180010d88  mov     r8, rbx; unsigned int
0x180010d8b  mov     edx, 0B4h; void *
0x180010d90  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010d95  lea     rcx, [rbp+var_20]
0x180010d99  mov     edi, eax
0x180010d9b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010da0  jmp     short loc_180010DEA
0x180010da2  mov     edx, 0D7h
0x180010da7  jmp     short loc_180010DDB
0x180010da9  mov     rcx, [rbp+var_28]; this
0x180010dad  mov     rdx, r14; unsigned __int16 *
0x180010db0  call    ?make_nullable_process_heap_string_nothrow@wil@@YAJPEBGPEAPEAG@Z; wil::make_nullable_process_heap_string_nothrow(ushort const *,ushort * *)
0x180010db5  mov     edi, eax
0x180010db7  test    eax, eax
0x180010db9  jns     short loc_180010DC2
0x180010dbb  mov     edx, 0FBh
0x180010dc0  jmp     short loc_180010DDB
0x180010dc2  lea     rcx, [rbp+var_28]
0x180010dc6  call    ?reset@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(std::nullptr_t)
0x180010dcb  xor     eax, eax
0x180010dcd  jmp     short loc_180010E22
0x180010dcf  mov     edx, 0EFh
0x180010dd4  jmp     short loc_180010DDB
0x180010dd6  mov     edx, 0E0h; void *
0x180010ddb  mov     rcx, [rbp+28h]; this
0x180010ddf  mov     r9d, eax; char *
0x180010de2  mov     r8, rbx; unsigned int
0x180010de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010dea  lea     rcx, [rbp+var_28]
0x180010dee  call    ?reset@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(std::nullptr_t)
0x180010df3  jmp     loc_180010B56
0x180010df8  mov     rcx, [rbp+28h]; this
0x180010dfc  mov     r9d, edi; char *
0x180010dff  mov     r8, rbx; unsigned int
0x180010e02  mov     edx, 0CEh; void *
0x180010e07  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010e0c  lea     rcx, [rbp+var_20]
0x180010e10  mov     ebx, eax
0x180010e12  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010e17  lea     rcx, [rbp+var_28]
0x180010e1b  call    ?reset@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(std::nullptr_t)
0x180010e20  mov     eax, ebx
0x180010e22  lea     r11, [rsp+70h+var_s0]
0x180010e27  mov     rbx, [r11+30h]
0x180010e2b  mov     rsi, [r11+38h]
0x180010e2f  mov     rsp, r11
0x180010e32  pop     r15
0x180010e34  pop     r14
0x180010e36  pop     r12
0x180010e38  pop     rdi
0x180010e39  pop     rbp
0x180010e3a  retn
```
