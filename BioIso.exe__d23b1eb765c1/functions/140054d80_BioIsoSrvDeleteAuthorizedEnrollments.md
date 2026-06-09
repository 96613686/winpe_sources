# BioIsoSrvDeleteAuthorizedEnrollments

- ea: `0x140054d80`
- end: `0x140054f48`
- name: `BioIsoSrvDeleteAuthorizedEnrollments`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a420`
- `0x14000bd48`
- `0x140012974`
- `0x14001bd40`
- `0x140040d2c`
- `0x140041cc8`
- `0x140043860`
- `0x140054d80`
- `0x140060a2c`
- `0x140060ab8`
- `0x140062a80`

## string_xrefs

- `0x140054ddf`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140054e6d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140054eb7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140054f02`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140054da2`: `DeleteAuthorizedEnrollments`
- `0x140054e3e`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BioIsoSrvDeleteAuthorizedEnrollments(__int64 a1)
{
  __int64 result; // rax
  Enrollments **v3; // rdi
  __int64 v4; // r8
  int v5; // eax
  int v6; // ebx
  const char *v7; // r9
  Enrollments **v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-178h] BYREF
  _QWORD v12[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v12,
    (__int64)"DeleteAuthorizedEnrollments");
  v12[0] = &BioIsoProvider::DeleteAuthorizedEnrollments::`vftable';
  BioIsoProvider::DeleteAuthorizedEnrollments::StartActivity((BioIsoProvider::DeleteAuthorizedEnrollments *)v12);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB26,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      (int)v11);
    BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments((BioIsoProvider::DeleteAuthorizedEnrollments *)v12);
    return 2147942487LL;
  }
  try
  {
    if ( *(_DWORD *)a1 == 4 )
    {
      v3 = (Enrollments **)SecureEnrollmentDatabase::Instance();
      Enrollments::lock_exclusive(*v3);
      v5 = Enrollments::DeleteEnrollment(*v3, (const unsigned __int8 *)(a1 + 4), v4);
      v6 = v5;
      if ( v5 >= 0 )
        v6 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
          (const char *)(unsigned int)v5,
          (int)v11);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v11);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB2C,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)v6,
          (int)v11);
        BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments((BioIsoProvider::DeleteAuthorizedEnrollments *)v12);
        return (unsigned int)v6;
      }
LABEL_12:
      wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12, 0);
      BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments((BioIsoProvider::DeleteAuthorizedEnrollments *)v12);
      return 0;
    }
    if ( *(_DWORD *)a1 == 3 )
    {
      v8 = (Enrollments **)SecureEnrollmentDatabase::Instance();
      v9 = SecureEnrollmentDatabase::DeleteEnrollment(v8, (void *const)(a1 + 8));
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB31,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)v9,
          (int)v11);
        BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments((BioIsoProvider::DeleteAuthorizedEnrollments *)v12);
        return v10;
      }
      goto LABEL_12;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB35,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      (int)v11);
    BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments((BioIsoProvider::DeleteAuthorizedEnrollments *)v12);
    result = 2147942487LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB3B,
                           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x140054d80  mov     [rsp+arg_8], rbx
0x140054d85  push    rdi
0x140054d86  sub     rsp, 190h
0x140054d8d  mov     rax, cs:__security_cookie
0x140054d94  xor     rax, rsp
0x140054d97  mov     [rsp+198h+var_18], rax
0x140054d9f  mov     rbx, rcx
0x140054da2  lea     rdx, aDeleteauthoriz; "DeleteAuthorizedEnrollments"
0x140054da9  lea     rcx, [rsp+198h+var_168]
0x140054dae  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140054db3  lea     rax, ??_7DeleteAuthorizedEnrollments@BioIsoProvider@@6B@; const BioIsoProvider::DeleteAuthorizedEnrollments::`vftable'
0x140054dba  mov     [rsp+198h+var_168], rax
0x140054dbf  lea     rcx, [rsp+198h+var_168]; this
0x140054dc4  call    ?StartActivity@DeleteAuthorizedEnrollments@BioIsoProvider@@QEAAXXZ; BioIsoProvider::DeleteAuthorizedEnrollments::StartActivity(void)
0x140054dc9  nop
0x140054dca  test    rbx, rbx
0x140054dcd  jnz     short loc_140054E02
0x140054dcf  mov     rcx, [rsp+198h]; this
0x140054dd7  mov     ebx, 80070057h
0x140054ddc  mov     r9d, ebx; char *
0x140054ddf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054de6  mov     edx, 0B26h; void *
0x140054deb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054df0  nop
0x140054df1  lea     rcx, [rsp+198h+var_168]; this
0x140054df6  call    ??1DeleteAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments(void)
0x140054dfb  mov     eax, ebx
0x140054dfd  jmp     loc_140054F26
0x140054e02  cmp     dword ptr [rbx], 4
0x140054e05  jnz     loc_140054E90
0x140054e0b  call    ?Instance@SecureEnrollmentDatabase@@SAAEAV1@XZ; SecureEnrollmentDatabase::Instance(void)
0x140054e10  mov     rdi, rax
0x140054e13  lea     rdx, [rsp+198h+var_178]
0x140054e18  mov     rcx, [rax]; this
0x140054e1b  call    ?lock_exclusive@Enrollments@@QEBA@XZ; Enrollments::lock_exclusive(void)
0x140054e20  nop
0x140054e21  lea     rdx, [rbx+4]; unsigned __int8 *
0x140054e25  mov     rcx, [rdi]; this
0x140054e28  call    ?DeleteEnrollment@Enrollments@@QEAAJPEBE_K@Z; Enrollments::DeleteEnrollment(uchar const *,unsigned __int64)
0x140054e2d  mov     ebx, eax
0x140054e2f  test    eax, eax
0x140054e31  jns     short loc_140054E52
0x140054e33  mov     rcx, [rsp+198h]; this
0x140054e3b  mov     r9d, eax; char *
0x140054e3e  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140054e45  mov     edx, 12Fh; void *
0x140054e4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054e4f  nop
0x140054e50  jmp     short loc_140054E54
0x140054e52  xor     ebx, ebx
0x140054e54  lea     rcx, [rsp+198h+var_178]
0x140054e59  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140054e5e  test    ebx, ebx
0x140054e60  jns     short loc_140054ED7
0x140054e62  mov     rcx, [rsp+198h]; this
0x140054e6a  mov     r9d, ebx; char *
0x140054e6d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054e74  mov     edx, 0B2Ch; void *
0x140054e79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054e7e  nop
0x140054e7f  lea     rcx, [rsp+198h+var_168]; this
0x140054e84  call    ??1DeleteAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments(void)
0x140054e89  mov     eax, ebx
0x140054e8b  jmp     loc_140054F26
0x140054e90  cmp     dword ptr [rbx], 3
0x140054e93  jnz     short loc_140054EF2
0x140054e95  call    ?Instance@SecureEnrollmentDatabase@@SAAEAV1@XZ; SecureEnrollmentDatabase::Instance(void)
0x140054e9a  lea     rdx, [rbx+8]; void *
0x140054e9e  mov     rcx, rax; this
0x140054ea1  call    ?DeleteEnrollment@SecureEnrollmentDatabase@@QEAAJQEAX@Z; SecureEnrollmentDatabase::DeleteEnrollment(void * const)
0x140054ea6  mov     ebx, eax
0x140054ea8  test    eax, eax
0x140054eaa  jns     short loc_140054ED7
0x140054eac  mov     rcx, [rsp+198h]; this
0x140054eb4  mov     r9d, eax; char *
0x140054eb7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054ebe  mov     edx, 0B31h; void *
0x140054ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054ec8  nop
0x140054ec9  lea     rcx, [rsp+198h+var_168]; this
0x140054ece  call    ??1DeleteAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments(void)
0x140054ed3  mov     eax, ebx
0x140054ed5  jmp     short loc_140054F26
0x140054ed7  xor     edx, edx
0x140054ed9  lea     rcx, [rsp+198h+var_168]
0x140054ede  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140054ee3  nop
0x140054ee4  lea     rcx, [rsp+198h+var_168]; this
0x140054ee9  call    ??1DeleteAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments(void)
0x140054eee  xor     eax, eax
0x140054ef0  jmp     short loc_140054F26
0x140054ef2  mov     rcx, [rsp+198h]; this
0x140054efa  mov     ebx, 80070057h
0x140054eff  mov     r9d, ebx; char *
0x140054f02  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054f09  mov     edx, 0B35h; void *
0x140054f0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054f13  nop
0x140054f14  lea     rcx, [rsp+198h+var_168]; this
0x140054f19  call    ??1DeleteAuthorizedEnrollments@BioIsoProvider@@QEAA@XZ; BioIsoProvider::DeleteAuthorizedEnrollments::~DeleteAuthorizedEnrollments(void)
0x140054f1e  mov     eax, ebx
0x140054f20  jmp     short loc_140054F26
0x140054f22  mov     eax, dword ptr [rsp+198h+var_178]
0x140054f26  mov     rcx, [rsp+198h+var_18]
0x140054f2e  xor     rcx, rsp; StackCookie
0x140054f31  call    __security_check_cookie
0x140054f36  mov     rbx, [rsp+198h+arg_8]
0x140054f3e  add     rsp, 190h
0x140054f45  pop     rdi
0x140054f46  retn
```
