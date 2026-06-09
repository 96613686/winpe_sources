# BioIsoSrvEngineUpdateEnrollment

- ea: `0x140015200`
- end: `0x1400153e7`
- name: `BioIsoSrvEngineUpdateEnrollment`
- size: `487`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140015200`
- `0x1400153f0`
- `0x14001bd40`
- `0x140044eb0`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x140015262`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400152a1`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400152ea`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140015391`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140015225`: `EngineUpdateEnrollment`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineUpdateEnrollment(int *a1, __int64 a2)
{
  int BiometricUnit; // eax
  int v6; // ebx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(__int64, __int64); // rax
  int v9; // [rsp+20h] [rbp-188h]
  std::_Ref_count_base *v10[2]; // [rsp+28h] [rbp-180h] BYREF
  _QWORD v11[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v11,
    (__int64)"EngineUpdateEnrollment");
  v11[0] = &BioIsoProvider::EngineUpdateEnrollment::`vftable';
  BioIsoProvider::EngineUpdateEnrollment::StartActivity((BioIsoProvider::EngineUpdateEnrollment *)v11);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x386,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v9);
    BioIsoProvider::EngineUpdateEnrollment::~EngineUpdateEnrollment((BioIsoProvider::EngineUpdateEnrollment *)v11);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x387,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v9);
    BioIsoProvider::EngineUpdateEnrollment::~EngineUpdateEnrollment((BioIsoProvider::EngineUpdateEnrollment *)v11);
    return 2147942487LL;
  }
  *(_OWORD *)v10 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v10);
  v6 = BiometricUnit;
  if ( BiometricUnit >= 0 )
  {
    if ( *((_QWORD *)v10[0] + 3) == -32 || (v7 = *(_QWORD *)(*((_QWORD *)v10[0] + 3) + 64LL)) == 0 )
    {
      v6 = -2147467261;
    }
    else
    {
      v8 = *(__int64 (__fastcall **)(__int64, __int64))(v7 + 136);
      if ( v8 )
      {
        v6 = v8(*((_QWORD *)v10[0] + 3) + 32LL, a2);
        if ( v6 >= 0 )
        {
          wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, 0);
          if ( v10[1] )
            std::_Ref_count_base::_Decref(v10[1]);
          goto LABEL_20;
        }
      }
      else
      {
        v6 = -2147467263;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v6,
      v9);
    if ( v10[1] )
      std::_Ref_count_base::_Decref(v10[1]);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v9);
    if ( v10[1] )
      std::_Ref_count_base::_Decref(v10[1]);
  }
LABEL_20:
  BioIsoProvider::EngineUpdateEnrollment::~EngineUpdateEnrollment((BioIsoProvider::EngineUpdateEnrollment *)v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140015200  mov     [rsp+arg_10], rbx
0x140015205  push    rdi
0x140015206  sub     rsp, 1A0h
0x14001520d  mov     rax, cs:__security_cookie
0x140015214  xor     rax, rsp
0x140015217  mov     [rsp+1A8h+var_18], rax
0x14001521f  mov     rdi, rdx
0x140015222  mov     rbx, rcx
0x140015225  lea     rdx, aEngineupdateen; "EngineUpdateEnrollment"
0x14001522c  lea     rcx, [rsp+1A8h+var_168]
0x140015231  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140015236  lea     rax, ??_7EngineUpdateEnrollment@BioIsoProvider@@6B@; const BioIsoProvider::EngineUpdateEnrollment::`vftable'
0x14001523d  mov     [rsp+1A8h+var_168], rax
0x140015242  lea     rcx, [rsp+1A8h+var_168]; this
0x140015247  call    ?StartActivity@EngineUpdateEnrollment@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineUpdateEnrollment::StartActivity(void)
0x14001524c  nop
0x14001524d  test    rbx, rbx
0x140015250  jnz     short loc_140015285
0x140015252  mov     rcx, [rsp+1A8h]; this
0x14001525a  mov     ebx, 80004003h
0x14001525f  mov     r9d, ebx; char *
0x140015262  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140015269  mov     edx, 386h; void *
0x14001526e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015273  nop
0x140015274  lea     rcx, [rsp+1A8h+var_168]; this
0x140015279  call    ??1EngineUpdateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineUpdateEnrollment::~EngineUpdateEnrollment(void)
0x14001527e  mov     eax, ebx
0x140015280  jmp     loc_1400153C5
0x140015285  mov     rcx, rbx; void *
0x140015288  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14001528d  test    al, al
0x14001528f  jnz     short loc_1400152C4
0x140015291  mov     rcx, [rsp+1A8h]; this
0x140015299  mov     ebx, 80070057h
0x14001529e  mov     r9d, ebx; char *
0x1400152a1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400152a8  mov     edx, 387h; void *
0x1400152ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400152b2  nop
0x1400152b3  lea     rcx, [rsp+1A8h+var_168]; this
0x1400152b8  call    ??1EngineUpdateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineUpdateEnrollment::~EngineUpdateEnrollment(void)
0x1400152bd  mov     eax, ebx
0x1400152bf  jmp     loc_1400153C5
0x1400152c4  xorps   xmm0, xmm0
0x1400152c7  movdqu  xmmword ptr [rsp+1A8h+var_180], xmm0
0x1400152cd  lea     rdx, [rsp+1A8h+var_180]
0x1400152d2  mov     ecx, [rbx]
0x1400152d4  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x1400152d9  mov     ebx, eax
0x1400152db  test    eax, eax
0x1400152dd  jns     short loc_14001531D
0x1400152df  mov     rcx, [rsp+1A8h]; this
0x1400152e7  mov     r9d, eax; char *
0x1400152ea  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400152f1  mov     edx, 38Ch; void *
0x1400152f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400152fb  nop
0x1400152fc  mov     rcx, [rsp+1A8h+var_180+8]; this
0x140015301  test    rcx, rcx
0x140015304  jz      short loc_14001530C
0x140015306  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001530b  nop
0x14001530c  lea     rcx, [rsp+1A8h+var_168]; this
0x140015311  call    ??1EngineUpdateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineUpdateEnrollment::~EngineUpdateEnrollment(void)
0x140015316  mov     eax, ebx
0x140015318  jmp     loc_1400153C5
0x14001531d  mov     rax, [rsp+1A8h+var_180]
0x140015322  mov     rcx, [rax+18h]
0x140015326  add     rcx, 20h ; ' '
0x14001532a  jz      short loc_140015381
0x14001532c  mov     rax, [rcx+20h]
0x140015330  test    rax, rax
0x140015333  jz      short loc_140015381
0x140015335  mov     rax, [rax+88h]
0x14001533c  test    rax, rax
0x14001533f  jnz     short loc_140015348
0x140015341  mov     ebx, 80004001h
0x140015346  jmp     short loc_140015386
0x140015348  mov     rdx, rdi
0x14001534b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015350  mov     ebx, eax
0x140015352  test    eax, eax
0x140015354  js      short loc_140015386
0x140015356  xor     edx, edx
0x140015358  lea     rcx, [rsp+1A8h+var_168]
0x14001535d  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140015362  nop
0x140015363  mov     rcx, [rsp+1A8h+var_180+8]; this
0x140015368  test    rcx, rcx
0x14001536b  jz      short loc_140015373
0x14001536d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140015372  nop
0x140015373  lea     rcx, [rsp+1A8h+var_168]; this
0x140015378  call    ??1EngineUpdateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineUpdateEnrollment::~EngineUpdateEnrollment(void)
0x14001537d  mov     eax, ebx
0x14001537f  jmp     short loc_1400153C5
0x140015381  mov     ebx, 80004003h
0x140015386  mov     rcx, [rsp+1A8h]; this
0x14001538e  mov     r9d, ebx; char *
0x140015391  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140015398  mov     edx, 38Fh; void *
0x14001539d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400153a2  nop
0x1400153a3  mov     rcx, [rsp+1A8h+var_180+8]; this
0x1400153a8  test    rcx, rcx
0x1400153ab  jz      short loc_1400153B3
0x1400153ad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400153b2  nop
0x1400153b3  lea     rcx, [rsp+1A8h+var_168]; this
0x1400153b8  call    ??1EngineUpdateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineUpdateEnrollment::~EngineUpdateEnrollment(void)
0x1400153bd  mov     eax, ebx
0x1400153bf  jmp     short loc_1400153C5
0x1400153c1  mov     eax, [rsp+1A8h+var_188]
0x1400153c5  mov     rcx, [rsp+1A8h+var_18]
0x1400153cd  xor     rcx, rsp; StackCookie
0x1400153d0  call    __security_check_cookie
0x1400153d5  mov     rbx, [rsp+1A8h+arg_10]
0x1400153dd  add     rsp, 1A0h
0x1400153e4  pop     rdi
0x1400153e5  retn
```
