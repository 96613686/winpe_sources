# BioIsoSrvQueryAuthorizedEnrollments

- ea: `0x140056780`
- end: `0x140056dd7`
- name: `BioIsoSrvQueryAuthorizedEnrollments`
- size: `1623`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a420`
- `0x14000ae0c`
- `0x14000d030`
- `0x14000d5d0`
- `0x14000e680`
- `0x140012974`
- `0x140015cb0`
- `0x14001bd40`
- `0x14001cb90`
- `0x140040d2c`
- `0x140041da4`
- `0x140045608`
- `0x140054180`
- `0x140056780`
- `0x14005cf30`
- `0x1400619d8`
- `0x140061a60`
- `0x140061da4`
- `0x140062ab4`

## string_xrefs

- `0x1400567f5`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140056830`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14005686b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140056908`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400569d5`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140056ab1`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140056b7e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140056c3f`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140056cd7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140056d87`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400568d9`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`
- `0x140056a82`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall BioIsoSrvQueryAuthorizedEnrollments(_DWORD *a1, _QWORD *a2, _DWORD *a3)
{
  Enrollments **v7; // rbx
  int AllSecureIds; // eax
  int v9; // ebx
  const void *const *v10; // r12
  size_t v11; // rdi
  char *v12; // rbx
  __int64 i; // rdi
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  Enrollments **v16; // rdi
  int v17; // eax
  int v18; // ebx
  const void *const *v19; // r12
  size_t v20; // rdi
  __int64 j; // rdi
  __int64 v22; // rcx
  Enrollments **v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  _DWORD *v26; // rbx
  int v27; // r15d
  int v28; // edi
  int v29[12]; // [rsp+20h] [rbp-1F8h]
  void *v30; // [rsp+50h] [rbp-1C8h] BYREF
  void *Source; // [rsp+58h] [rbp-1C0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-1B8h]
  _QWORD v33[4]; // [rsp+70h] [rbp-1A8h] BYREF
  _QWORD v34[42]; // [rsp+90h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v34,
    (__int64)"QueryAuthorizedEnrollments");
  v34[0] = &BioIsoProvider::QueryAuthorizedEnrollments::`vftable';
  BioIsoProvider::QueryAuthorizedEnrollments::StartActivity((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v29[0]);
    BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC3,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v29[0]);
    BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC4,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v29[0]);
    BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
    return 2147500035LL;
  }
  switch ( *a1 )
  {
    case 1:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Source);
      v7 = (Enrollments **)SecureEnrollmentDatabase::Instance();
      Enrollments::lock_shared(*v7);
      AllSecureIds = Enrollments::GetAllSecureIds((__int64)*v7, (__int64)&Source);
      v9 = AllSecureIds;
      if ( AllSecureIds >= 0 )
        v9 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x171,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
          (const char *)(unsigned int)AllSecureIds,
          v29[0]);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v30);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xACA,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)v9,
          v29[0]);
        std::vector<std::vector<unsigned char>>::_Tidy(&Source);
        BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
        return (unsigned int)v9;
      }
      v10 = (const void *const *)Source;
      v11 = 0xAAAAAAAAAAAAAAC4uLL * ((v32 - (__int64)Source) >> 3);
      v12 = (char *)MIDL_user_allocate(v11);
      v30 = v12;
      memset_0(v12, 0, v11);
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v14 = 0xAAAAAAAAAAAAAAABuLL * ((v32 - (__int64)v10) >> 3);
        if ( (unsigned int)i >= (unsigned int)v14 )
          break;
        v15 = 76LL * (unsigned int)i;
        *(_DWORD *)&v12[v15] = 4;
        if ( memcpy_s(&v12[v15 + 4], 0x20u, v10[3 * i], (char *)v10[3 * i + 1] - (char *)v10[3 * i]) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAD9,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
            (const char *)0x80004005LL,
            v29[0]);
          std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v30);
          std::vector<std::vector<unsigned char>>::_Tidy(&Source);
          BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
          return 2147500037LL;
        }
      }
LABEL_29:
      v30 = 0;
      *a2 = v12;
      *a3 = v14;
      std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v30);
      std::vector<std::vector<unsigned char>>::_Tidy(&Source);
LABEL_36:
      wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v34, 0);
      BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
      return 0;
    case 3:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Source);
      v16 = (Enrollments **)SecureEnrollmentDatabase::Instance();
      Enrollments::lock_shared(*v16);
      v17 = Enrollments::FindBySid((__int64)*v16, a1 + 2, (__int64)&Source);
      v18 = v17;
      if ( v17 >= 0 )
        v18 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x166,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
          (const char *)(unsigned int)v17,
          v29[0]);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v30);
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAE4,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)v18,
          v29[0]);
        std::vector<std::vector<unsigned char>>::_Tidy(&Source);
        BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
        return (unsigned int)v18;
      }
      v19 = (const void *const *)Source;
      v20 = 0xAAAAAAAAAAAAAAC4uLL * ((v32 - (__int64)Source) >> 3);
      v12 = (char *)MIDL_user_allocate(v20);
      v30 = v12;
      memset_0(v12, 0, v20);
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        v14 = 0xAAAAAAAAAAAAAAABuLL * ((v32 - (__int64)v19) >> 3);
        if ( (unsigned int)j >= (unsigned int)v14 )
          break;
        v22 = 76LL * (unsigned int)j;
        *(_DWORD *)&v12[v22] = 4;
        if ( memcpy_s(&v12[v22 + 4], 0x20u, v19[3 * j], (char *)v19[3 * j + 1] - (char *)v19[3 * j]) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAF3,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
            (const char *)0x80004005LL,
            v29[0]);
          std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v30);
          std::vector<std::vector<unsigned char>>::_Tidy(&Source);
          BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
          return 2147500037LL;
        }
      }
      goto LABEL_29;
    case 4:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Source);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v33);
      v23 = (Enrollments **)SecureEnrollmentDatabase::Instance();
      v24 = SecureEnrollmentDatabase::Find(v23, a1 + 1, 0x20u, (__int64)&Source, (__int64)v33);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB06,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)v24,
          v29[0]);
        std::vector<unsigned char>::_Tidy((__int64)v33);
        std::vector<unsigned char>::_Tidy((__int64)&Source);
        BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
        return v25;
      }
      v26 = MIDL_user_allocate(0x4Cu);
      v30 = v26;
      memset_0(v26, 0, 0x4Cu);
      *v26 = 3;
      v27 = (int)Source;
      v28 = v32;
      if ( memcpy_s(v26 + 2, 0x44u, Source, v32 - (_QWORD)Source) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB11,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)0x80004005LL,
          v29[0]);
        std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v30);
        std::vector<unsigned char>::_Tidy((__int64)v33);
        std::vector<unsigned char>::_Tidy((__int64)&Source);
        BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
        return 2147500037LL;
      }
      v26[1] = v28 - v27;
      v30 = 0;
      *a2 = v26;
      *a3 = 1;
      std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v30);
      std::vector<unsigned char>::_Tidy((__int64)v33);
      std::vector<unsigned char>::_Tidy((__int64)&Source);
      goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB19,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
    (const char *)0x80070057LL,
    v29[0]);
  BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments((BioIsoProvider::QueryAuthorizedEnrollments *)v34);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140056780  mov     [rsp+arg_18], rbx
0x140056785  push    rsi
0x140056786  push    rdi
0x140056787  push    r12
0x140056789  push    r14
0x14005678b  push    r15
0x14005678d  sub     rsp, 1F0h
0x140056794  mov     rax, cs:__security_cookie
0x14005679b  xor     rax, rsp
0x14005679e  mov     [rsp+218h+var_38], rax
0x1400567a6  mov     r14, r8
0x1400567a9  mov     rsi, rdx
0x1400567ac  mov     rbx, rcx
0x1400567af  lea     rdx, aQueryauthorize; "QueryAuthorizedEnrollments"
0x1400567b6  lea     rcx, [rsp+218h+var_188]
0x1400567be  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400567c3  lea     rax, ??_7QueryAuthorizedEnrollments@BioIsoProvider@@6B@; const BioIsoProvider::QueryAuthorizedEnrollments::`vftable'
0x1400567ca  mov     [rsp+218h+var_188], rax
0x1400567d2  lea     rcx, [rsp+218h+var_188]; this
0x1400567da  call    ?StartActivity@QueryAuthorizedEnrollments@BioIsoProvider@@QEAAXXZ; BioIsoProvider::QueryAuthorizedEnrollments::StartActivity(void)
0x1400567df  nop
0x1400567e0  test    rbx, rbx
0x1400567e3  jnz     short loc_14005681B
0x1400567e5  mov     rcx, [rsp+218h]; this
0x1400567ed  mov     ebx, 80070057h
0x1400567f2  mov     r9d, ebx; char *
0x1400567f5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400567fc  mov     edx, 0AC2h; void *
0x140056801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056806  nop
0x140056807  lea     rcx, [rsp+218h+var_188]; this
0x14005680f  call    ??1QueryAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments(void)
0x140056814  mov     eax, ebx
0x140056816  jmp     loc_140056DAE
0x14005681b  test    rsi, rsi
0x14005681e  jnz     short loc_140056856
0x140056820  mov     rcx, [rsp+218h]; this
0x140056828  mov     ebx, 80004003h
0x14005682d  mov     r9d, ebx; char *
0x140056830  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140056837  mov     edx, 0AC3h; void *
0x14005683c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056841  nop
0x140056842  lea     rcx, [rsp+218h+var_188]; this
0x14005684a  call    ??1QueryAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments(void)
0x14005684f  mov     eax, ebx
0x140056851  jmp     loc_140056DAE
0x140056856  test    r14, r14
0x140056859  jnz     short loc_140056891
0x14005685b  mov     rcx, [rsp+218h]; this
0x140056863  mov     ebx, 80004003h
0x140056868  mov     r9d, ebx; char *
0x14005686b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140056872  mov     edx, 0AC4h; void *
0x140056877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005687c  nop
0x14005687d  lea     rcx, [rsp+218h+var_188]; this
0x140056885  call    ??1QueryAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments(void)
0x14005688a  mov     eax, ebx
0x14005688c  jmp     loc_140056DAE
0x140056891  cmp     dword ptr [rbx], 1
0x140056894  jnz     loc_140056A36
0x14005689a  lea     rcx, [rsp+218h+Source]
0x14005689f  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1400568a4  nop
0x1400568a5  call    ?Instance@SecureEnrollmentDatabase@@SAAEAV1@XZ; SecureEnrollmentDatabase::Instance(void)
0x1400568aa  mov     rbx, rax
0x1400568ad  lea     rdx, [rsp+218h+var_1C8]
0x1400568b2  mov     rcx, [rax]; this
0x1400568b5  call    ?lock_shared@Enrollments@@QEBA@XZ; Enrollments::lock_shared(void)
0x1400568ba  nop
0x1400568bb  lea     rdx, [rsp+218h+Source]
0x1400568c0  mov     rcx, [rbx]
0x1400568c3  call    ?GetAllSecureIds@Enrollments@@QEBAJPEAV?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@Z; Enrollments::GetAllSecureIds(std::vector<std::vector<uchar>> *)
0x1400568c8  mov     ebx, eax
0x1400568ca  test    eax, eax
0x1400568cc  jns     short loc_1400568ED
0x1400568ce  mov     rcx, [rsp+218h]; this
0x1400568d6  mov     r9d, eax; char *
0x1400568d9  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x1400568e0  mov     edx, 171h; void *
0x1400568e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400568ea  nop
0x1400568eb  jmp     short loc_1400568EF
0x1400568ed  xor     ebx, ebx
0x1400568ef  lea     rcx, [rsp+218h+var_1C8]
0x1400568f4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400568f9  test    ebx, ebx
0x1400568fb  jns     short loc_140056939
0x1400568fd  mov     rcx, [rsp+218h]; this
0x140056905  mov     r9d, ebx; char *
0x140056908  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14005690f  mov     edx, 0ACAh; void *
0x140056914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056919  nop
0x14005691a  lea     rcx, [rsp+218h+Source]
0x14005691f  call    ?_Tidy@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<uchar>>::_Tidy(void)
0x140056924  nop
0x140056925  lea     rcx, [rsp+218h+var_188]; this
0x14005692d  call    ??1QueryAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments(void)
0x140056932  mov     eax, ebx
0x140056934  jmp     loc_140056DAE
0x140056939  mov     rax, [rsp+218h+var_1B8]
0x14005693e  mov     r12, [rsp+218h+Source]
0x140056943  sub     rax, r12
0x140056946  sar     rax, 3
0x14005694a  mov     r15, 0AAAAAAAAAAAAAAABh
0x140056954  imul    rax, r15
0x140056958  imul    rdi, rax, 4Ch ; 'L'
0x14005695c  mov     rcx, rdi; size
0x14005695f  call    MIDL_user_allocate
0x140056964  mov     rbx, rax
0x140056967  mov     [rsp+218h+var_1C8], rax
0x14005696c  mov     r8, rdi; Size
0x14005696f  xor     edx, edx; Val
0x140056971  mov     rcx, rax; void *
0x140056974  call    memset_0
0x140056979  xor     edi, edi
0x14005697b  mov     rax, [rsp+218h+var_1B8]
0x140056980  sub     rax, r12
0x140056983  sar     rax, 3
0x140056987  imul    rax, r15
0x14005698b  cmp     edi, eax
0x14005698d  jnb     loc_140056A17
0x140056993  mov     eax, edi
0x140056995  imul    rcx, rax, 4Ch ; 'L'
0x140056999  mov     dword ptr [rcx+rbx], 4
0x1400569a0  lea     rax, [rdi+rdi*2]
0x1400569a4  mov     r8, [r12+rax*8]; Source
0x1400569a8  mov     r9, [r12+rax*8+8]
0x1400569ad  sub     r9, r8; SourceSize
0x1400569b0  add     rcx, 4
0x1400569b4  add     rcx, rbx; Destination
0x1400569b7  mov     edx, 20h ; ' '; DestinationSize
0x1400569bc  call    memcpy_s
0x1400569c1  test    eax, eax
0x1400569c3  jz      short loc_140056A10
0x1400569c5  mov     rcx, [rsp+218h]; this
0x1400569cd  mov     ebx, 80004005h
0x1400569d2  mov     r9d, ebx; char *
0x1400569d5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400569dc  mov     edx, 0AD9h; void *
0x1400569e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400569e6  lea     rcx, [rsp+218h+var_1C8]
0x1400569eb  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x1400569f0  nop
0x1400569f1  lea     rcx, [rsp+218h+Source]
0x1400569f6  call    ?_Tidy@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<uchar>>::_Tidy(void)
0x1400569fb  nop
0x1400569fc  lea     rcx, [rsp+218h+var_188]; this
0x140056a04  call    ??1QueryAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments(void)
0x140056a09  mov     eax, ebx
0x140056a0b  jmp     loc_140056DAE
0x140056a10  inc     edi
0x140056a12  jmp     loc_14005697B
0x140056a17  mov     [rsp+218h+var_1C8], 0
0x140056a20  mov     [rsi], rbx
0x140056a23  mov     [r14], eax
0x140056a26  lea     rcx, [rsp+218h+var_1C8]
0x140056a2b  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x140056a30  nop
0x140056a31  jmp     loc_140056BDA
0x140056a36  cmp     dword ptr [rbx], 3
0x140056a39  jnz     loc_140056BE9
0x140056a3f  lea     rcx, [rsp+218h+Source]
0x140056a44  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140056a49  nop
0x140056a4a  call    ?Instance@SecureEnrollmentDatabase@@SAAEAV1@XZ; SecureEnrollmentDatabase::Instance(void)
0x140056a4f  mov     rdi, rax
0x140056a52  lea     rdx, [rsp+218h+var_1C8]
0x140056a57  mov     rcx, [rax]; this
0x140056a5a  call    ?lock_shared@Enrollments@@QEBA@XZ; Enrollments::lock_shared(void)
0x140056a5f  nop
0x140056a60  lea     rdx, [rbx+8]
0x140056a64  lea     r8, [rsp+218h+Source]
0x140056a69  mov     rcx, [rdi]
0x140056a6c  call    ?FindBySid@Enrollments@@QEBAJQEAXPEAV?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@Z; Enrollments::FindBySid(void * const,std::vector<std::vector<uchar>> *)
0x140056a71  mov     ebx, eax
0x140056a73  test    eax, eax
0x140056a75  jns     short loc_140056A96
0x140056a77  mov     rcx, [rsp+218h]; this
0x140056a7f  mov     r9d, eax; char *
0x140056a82  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140056a89  mov     edx, 166h; void *
0x140056a8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056a93  nop
0x140056a94  jmp     short loc_140056A98
0x140056a96  xor     ebx, ebx
0x140056a98  lea     rcx, [rsp+218h+var_1C8]
0x140056a9d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140056aa2  test    ebx, ebx
0x140056aa4  jns     short loc_140056AE2
0x140056aa6  mov     rcx, [rsp+218h]; this
0x140056aae  mov     r9d, ebx; char *
0x140056ab1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140056ab8  mov     edx, 0AE4h; void *
0x140056abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056ac2  nop
0x140056ac3  lea     rcx, [rsp+218h+Source]
0x140056ac8  call    ?_Tidy@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<uchar>>::_Tidy(void)
0x140056acd  nop
0x140056ace  lea     rcx, [rsp+218h+var_188]; this
0x140056ad6  call    ??1QueryAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments(void)
0x140056adb  mov     eax, ebx
0x140056add  jmp     loc_140056DAE
0x140056ae2  mov     rax, [rsp+218h+var_1B8]
0x140056ae7  mov     r12, [rsp+218h+Source]
0x140056aec  sub     rax, r12
0x140056aef  sar     rax, 3
0x140056af3  mov     r15, 0AAAAAAAAAAAAAAABh
0x140056afd  imul    rax, r15
0x140056b01  imul    rdi, rax, 4Ch ; 'L'
0x140056b05  mov     rcx, rdi; size
0x140056b08  call    MIDL_user_allocate
0x140056b0d  mov     rbx, rax
0x140056b10  mov     [rsp+218h+var_1C8], rax
0x140056b15  mov     r8, rdi; Size
0x140056b18  xor     edx, edx; Val
0x140056b1a  mov     rcx, rax; void *
0x140056b1d  call    memset_0
0x140056b22  xor     edi, edi
0x140056b24  mov     rax, [rsp+218h+var_1B8]
0x140056b29  sub     rax, r12
0x140056b2c  sar     rax, 3
0x140056b30  imul    rax, r15
0x140056b34  cmp     edi, eax
0x140056b36  jnb     loc_140056BC0
0x140056b3c  mov     eax, edi
0x140056b3e  imul    rcx, rax, 4Ch ; 'L'
0x140056b42  mov     dword ptr [rcx+rbx], 4
0x140056b49  lea     rax, [rdi+rdi*2]
0x140056b4d  mov     r8, [r12+rax*8]; Source
0x140056b51  mov     r9, [r12+rax*8+8]
0x140056b56  sub     r9, r8; SourceSize
0x140056b59  add     rcx, 4
0x140056b5d  add     rcx, rbx; Destination
0x140056b60  mov     edx, 20h ; ' '; DestinationSize
0x140056b65  call    memcpy_s
0x140056b6a  test    eax, eax
0x140056b6c  jz      short loc_140056BB9
0x140056b6e  mov     rcx, [rsp+218h]; this
0x140056b76  mov     ebx, 80004005h
0x140056b7b  mov     r9d, ebx; char *
0x140056b7e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140056b85  mov     edx, 0AF3h; void *
0x140056b8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056b8f  lea     rcx, [rsp+218h+var_1C8]
0x140056b94  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x140056b99  nop
0x140056b9a  lea     rcx, [rsp+218h+Source]
0x140056b9f  call    ?_Tidy@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<uchar>>::_Tidy(void)
0x140056ba4  nop
0x140056ba5  lea     rcx, [rsp+218h+var_188]; this
0x140056bad  call    ??1QueryAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments(void)
0x140056bb2  mov     eax, ebx
0x140056bb4  jmp     loc_140056DAE
0x140056bb9  inc     edi
0x140056bbb  jmp     loc_140056B24
0x140056bc0  mov     [rsp+218h+var_1C8], 0
0x140056bc9  mov     [rsi], rbx
0x140056bcc  mov     [r14], eax
0x140056bcf  lea     rcx, [rsp+218h+var_1C8]
0x140056bd4  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x140056bd9  nop
0x140056bda  lea     rcx, [rsp+218h+Source]
0x140056bdf  call    ?_Tidy@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<uchar>>::_Tidy(void)
0x140056be4  jmp     loc_140056D56
0x140056be9  cmp     dword ptr [rbx], 4
0x140056bec  jnz     loc_140056D77
0x140056bf2  lea     rcx, [rsp+218h+Source]
0x140056bf7  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140056bfc  nop
0x140056bfd  lea     rcx, [rsp+218h+var_1A8]
0x140056c02  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140056c07  nop
0x140056c08  call    ?Instance@SecureEnrollmentDatabase@@SAAEAV1@XZ; SecureEnrollmentDatabase::Instance(void)
0x140056c0d  lea     rdx, [rbx+4]
0x140056c11  lea     rcx, [rsp+218h+var_1A8]
0x140056c16  mov     qword ptr [rsp+218h+var_1F8], rcx; int
0x140056c1b  lea     r9, [rsp+218h+Source]
0x140056c20  mov     r8d, 20h ; ' '
0x140056c26  mov     rcx, rax
0x140056c29  call    ?Find@SecureEnrollmentDatabase@@QEBAJPEBE_KPEAV?$vector@EV?$allocator@E@std@@@std@@222222@Z; SecureEnrollmentDatabase::Find(uchar const *,unsigned __int64,std::vector<uchar> *,std::vector<uchar> *,std::vector<uchar> *,std::vector<uchar> *,std::vector<uchar> *,std::vector<uchar> *,std::vector<uchar> *)
0x140056c2e  mov     ebx, eax
0x140056c30  test    eax, eax
0x140056c32  jns     short loc_140056C7B
0x140056c34  mov     rcx, [rsp+218h]; this
0x140056c3c  mov     r9d, eax; char *
0x140056c3f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140056c46  mov     edx, 0B06h; void *
0x140056c4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056c50  nop
0x140056c51  lea     rcx, [rsp+218h+var_1A8]
0x140056c56  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140056c5b  nop
0x140056c5c  lea     rcx, [rsp+218h+Source]
0x140056c61  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140056c66  nop
0x140056c67  lea     rcx, [rsp+218h+var_188]; this
0x140056c6f  call    ??1QueryAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::QueryAuthorizedEnrollments::~QueryAuthorizedEnrollments(void)
  ... truncated ...
```
