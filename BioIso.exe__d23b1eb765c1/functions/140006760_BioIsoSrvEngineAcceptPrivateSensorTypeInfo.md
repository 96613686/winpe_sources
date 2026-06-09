# BioIsoSrvEngineAcceptPrivateSensorTypeInfo

- ea: `0x140006760`
- end: `0x140006986`
- name: `BioIsoSrvEngineAcceptPrivateSensorTypeInfo`
- size: `550`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006760`
- `0x14000698c`
- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x14001bd40`
- `0x140043908`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x1400067c3`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140006802`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000685c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140006906`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140006946`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineAcceptPrivateSensorTypeInfo(int *a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rsi
  int BiometricUnit; // eax
  int v8; // ebx
  __int64 v9; // rax
  __int64 (__fastcall *v10)(__int64, __int64, __int64); // rax
  int v11; // [rsp+20h] [rbp-198h]
  std::_Ref_count_base *v12[2]; // [rsp+28h] [rbp-190h] BYREF
  _QWORD v13[42]; // [rsp+40h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v3 = a3;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v13,
    (__int64)"EngineAcceptPrivateSensorTypeInfo");
  v13[0] = &BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::`vftable';
  BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::StartActivity((BioIsoProvider::EngineAcceptPrivateSensorTypeInfo *)v13);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F4,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v11);
    BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo((BioIsoProvider::EngineAcceptPrivateSensorTypeInfo *)v13);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F5,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v11);
    BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo((BioIsoProvider::EngineAcceptPrivateSensorTypeInfo *)v13);
    return 2147942487LL;
  }
  if ( !a2 || !(_DWORD)v3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5FB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v11);
    BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo((BioIsoProvider::EngineAcceptPrivateSensorTypeInfo *)v13);
    return 2147942487LL;
  }
  *(_OWORD *)v12 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v12);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5FF,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v11);
    if ( v12[1] )
      std::_Ref_count_base::_Decref(v12[1]);
LABEL_10:
    BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo((BioIsoProvider::EngineAcceptPrivateSensorTypeInfo *)v13);
    return (unsigned int)v8;
  }
  if ( *((_QWORD *)v12[0] + 3) == -32 || (v9 = *(_QWORD *)(*((_QWORD *)v12[0] + 3) + 64LL)) == 0 )
  {
    v8 = -2147467261;
    goto LABEL_20;
  }
  v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(v9 + 336);
  if ( !v10 )
  {
    v8 = -2147467263;
    goto LABEL_20;
  }
  v8 = v10(*((_QWORD *)v12[0] + 3) + 32LL, a2, v3);
  if ( v8 < 0 )
  {
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x605,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v8,
      v11);
    if ( v12[1] )
      std::_Ref_count_base::_Decref(v12[1]);
    goto LABEL_10;
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v13, 0);
  if ( v12[1] )
    std::_Ref_count_base::_Decref(v12[1]);
  BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo((BioIsoProvider::EngineAcceptPrivateSensorTypeInfo *)v13);
  return 0;
}

```

## disassembly

```asm
0x140006760  push    rbx
0x140006762  push    rsi
0x140006763  push    rdi
0x140006764  sub     rsp, 1A0h
0x14000676b  mov     rax, cs:__security_cookie
0x140006772  xor     rax, rsp
0x140006775  mov     [rsp+1B8h+var_28], rax
0x14000677d  mov     esi, r8d
0x140006780  mov     rdi, rdx
0x140006783  mov     rbx, rcx
0x140006786  lea     rdx, aEngineacceptpr; "EngineAcceptPrivateSensorTypeInfo"
0x14000678d  lea     rcx, [rsp+1B8h+var_178]
0x140006792  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140006797  lea     rax, ??_7EngineAcceptPrivateSensorTypeInfo@BioIsoProvider@@6B@; const BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::`vftable'
0x14000679e  mov     [rsp+1B8h+var_178], rax
0x1400067a3  lea     rcx, [rsp+1B8h+var_178]; this
0x1400067a8  call    ?StartActivity@EngineAcceptPrivateSensorTypeInfo@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::StartActivity(void)
0x1400067ad  nop
0x1400067ae  test    rbx, rbx
0x1400067b1  jnz     short loc_1400067E6
0x1400067b3  mov     rcx, [rsp+1B8h]; this
0x1400067bb  mov     ebx, 80004003h
0x1400067c0  mov     r9d, ebx; char *
0x1400067c3  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400067ca  mov     edx, 5F4h; void *
0x1400067cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400067d4  nop
0x1400067d5  lea     rcx, [rsp+1B8h+var_178]; this
0x1400067da  call    ??1EngineAcceptPrivateSensorTypeInfo@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo(void)
0x1400067df  mov     eax, ebx
0x1400067e1  jmp     loc_14000696A
0x1400067e6  mov     rcx, rbx; void *
0x1400067e9  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400067ee  test    al, al
0x1400067f0  jnz     short loc_140006825
0x1400067f2  mov     rcx, [rsp+1B8h]; this
0x1400067fa  mov     ebx, 80070057h
0x1400067ff  mov     r9d, ebx; char *
0x140006802  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140006809  mov     edx, 5F5h; void *
0x14000680e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006813  nop
0x140006814  lea     rcx, [rsp+1B8h+var_178]; this
0x140006819  call    ??1EngineAcceptPrivateSensorTypeInfo@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo(void)
0x14000681e  mov     eax, ebx
0x140006820  jmp     loc_14000696A
0x140006825  test    rdi, rdi
0x140006828  jz      loc_140006936
0x14000682e  test    esi, esi
0x140006830  jz      loc_140006936
0x140006836  xorps   xmm0, xmm0
0x140006839  movdqu  xmmword ptr [rsp+1B8h+var_190], xmm0
0x14000683f  lea     rdx, [rsp+1B8h+var_190]
0x140006844  mov     ecx, [rbx]
0x140006846  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14000684b  mov     ebx, eax
0x14000684d  test    eax, eax
0x14000684f  jns     short loc_14000688F
0x140006851  mov     rcx, [rsp+1B8h]; this
0x140006859  mov     r9d, eax; char *
0x14000685c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140006863  mov     edx, 5FFh; void *
0x140006868  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000686d  nop
0x14000686e  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140006873  test    rcx, rcx
0x140006876  jz      short loc_14000687E
0x140006878  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000687d  nop
0x14000687e  lea     rcx, [rsp+1B8h+var_178]; this
0x140006883  call    ??1EngineAcceptPrivateSensorTypeInfo@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo(void)
0x140006888  mov     eax, ebx
0x14000688a  jmp     loc_14000696A
0x14000688f  mov     rax, [rsp+1B8h+var_190]
0x140006894  mov     rcx, [rax+18h]
0x140006898  add     rcx, 20h ; ' '
0x14000689c  jz      short loc_1400068F6
0x14000689e  mov     rax, [rcx+20h]
0x1400068a2  test    rax, rax
0x1400068a5  jz      short loc_1400068F6
0x1400068a7  mov     rax, [rax+150h]
0x1400068ae  test    rax, rax
0x1400068b1  jnz     short loc_1400068BA
0x1400068b3  mov     ebx, 80004001h
0x1400068b8  jmp     short loc_1400068FB
0x1400068ba  mov     r8, rsi
0x1400068bd  mov     rdx, rdi
0x1400068c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068c5  mov     ebx, eax
0x1400068c7  test    eax, eax
0x1400068c9  js      short loc_1400068FB
0x1400068cb  xor     edx, edx
0x1400068cd  lea     rcx, [rsp+1B8h+var_178]
0x1400068d2  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400068d7  nop
0x1400068d8  mov     rcx, [rsp+1B8h+var_190+8]; this
0x1400068dd  test    rcx, rcx
0x1400068e0  jz      short loc_1400068E8
0x1400068e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400068e7  nop
0x1400068e8  lea     rcx, [rsp+1B8h+var_178]; this
0x1400068ed  call    ??1EngineAcceptPrivateSensorTypeInfo@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo(void)
0x1400068f2  xor     eax, eax
0x1400068f4  jmp     short loc_14000696A
0x1400068f6  mov     ebx, 80004003h
0x1400068fb  mov     rcx, [rsp+1B8h]; this
0x140006903  mov     r9d, ebx; char *
0x140006906  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000690d  mov     edx, 605h; void *
0x140006912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006917  nop
0x140006918  mov     rcx, [rsp+1B8h+var_190+8]; this
0x14000691d  test    rcx, rcx
0x140006920  jz      short loc_140006928
0x140006922  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140006927  nop
0x140006928  lea     rcx, [rsp+1B8h+var_178]; this
0x14000692d  call    ??1EngineAcceptPrivateSensorTypeInfo@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo(void)
0x140006932  mov     eax, ebx
0x140006934  jmp     short loc_14000696A
0x140006936  mov     rcx, [rsp+1B8h]; this
0x14000693e  mov     ebx, 80070057h
0x140006943  mov     r9d, ebx; char *
0x140006946  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000694d  mov     edx, 5FBh; void *
0x140006952  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006957  nop
0x140006958  lea     rcx, [rsp+1B8h+var_178]; this
0x14000695d  call    ??1EngineAcceptPrivateSensorTypeInfo@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptPrivateSensorTypeInfo::~EngineAcceptPrivateSensorTypeInfo(void)
0x140006962  mov     eax, ebx
0x140006964  jmp     short loc_14000696A
0x140006966  mov     eax, [rsp+1B8h+var_198]
0x14000696a  mov     rcx, [rsp+1B8h+var_28]
0x140006972  xor     rcx, rsp; StackCookie
0x140006975  call    __security_check_cookie
0x14000697a  add     rsp, 1A0h
0x140006981  pop     rdi
0x140006982  pop     rsi
0x140006983  pop     rbx
0x140006984  retn
```
