# BioIsoSrvEngineSampleImportEnd

- ea: `0x140018c90`
- end: `0x140018ec5`
- name: `BioIsoSrvEngineSampleImportEnd`
- size: `565`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140013078`
- `0x140018c90`
- `0x140018ecc`
- `0x14001bd40`
- `0x140044ac0`
- `0x14005841c`
- `0x140059830`

## string_xrefs

- `0x140018ceb`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140018d2a`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140018d73`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140018dcf`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140018e2e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineSampleImportEnd(int *a1)
{
  int BiometricUnit; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // [rsp+20h] [rbp-198h]
  std::_Ref_count_base *v7[2]; // [rsp+28h] [rbp-190h] BYREF
  __int64 v8; // [rsp+38h] [rbp-180h] BYREF
  std::_Ref_count_base *v9; // [rsp+40h] [rbp-178h]
  _QWORD v10[42]; // [rsp+50h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v10,
    (__int64)"EngineSampleImportEnd");
  v10[0] = &BioIsoProvider::EngineSampleImportEnd::`vftable';
  BioIsoProvider::EngineSampleImportEnd::StartActivity((BioIsoProvider::EngineSampleImportEnd *)v10);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v6);
    BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd((BioIsoProvider::EngineSampleImportEnd *)v10);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32D,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v6);
    BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd((BioIsoProvider::EngineSampleImportEnd *)v10);
    return 2147942487LL;
  }
  *(_OWORD *)v7 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v7);
  v4 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x332,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v6);
    if ( v7[1] )
      std::_Ref_count_base::_Decref(v7[1]);
LABEL_8:
    BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd((BioIsoProvider::EngineSampleImportEnd *)v10);
    return v4;
  }
  BiometricUnit::PipelineObject(v7[0], &v8);
  if ( v8 )
  {
    v5 = CacheBuffer::ImportEnd((CacheBuffer *)(v8 + 1240));
    v4 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33A,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)v5,
        v6);
      if ( v9 )
        std::_Ref_count_base::_Decref(v9);
      if ( v7[1] )
        std::_Ref_count_base::_Decref(v7[1]);
      goto LABEL_8;
    }
    wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v10, 0);
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    if ( v7[1] )
      std::_Ref_count_base::_Decref(v7[1]);
    BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd((BioIsoProvider::EngineSampleImportEnd *)v10);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x337,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v6);
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    if ( v7[1] )
      std::_Ref_count_base::_Decref(v7[1]);
    BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd((BioIsoProvider::EngineSampleImportEnd *)v10);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140018c90  push    rbx
0x140018c92  sub     rsp, 1B0h
0x140018c99  mov     rax, cs:__security_cookie
0x140018ca0  xor     rax, rsp
0x140018ca3  mov     [rsp+1B8h+var_18], rax
0x140018cab  mov     rbx, rcx
0x140018cae  lea     rdx, aEnginesampleim; "EngineSampleImportEnd"
0x140018cb5  lea     rcx, [rsp+1B8h+var_168]
0x140018cba  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140018cbf  lea     rax, ??_7EngineSampleImportEnd@BioIsoProvider@@6B@; const BioIsoProvider::EngineSampleImportEnd::`vftable'
0x140018cc6  mov     [rsp+1B8h+var_168], rax
0x140018ccb  lea     rcx, [rsp+1B8h+var_168]; this
0x140018cd0  call    ?StartActivity@EngineSampleImportEnd@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineSampleImportEnd::StartActivity(void)
0x140018cd5  nop
0x140018cd6  test    rbx, rbx
0x140018cd9  jnz     short loc_140018D0E
0x140018cdb  mov     rcx, [rsp+1B8h]; this
0x140018ce3  mov     ebx, 80004003h
0x140018ce8  mov     r9d, ebx; char *
0x140018ceb  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018cf2  mov     edx, 32Ch; void *
0x140018cf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018cfc  nop
0x140018cfd  lea     rcx, [rsp+1B8h+var_168]; this
0x140018d02  call    ??1EngineSampleImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd(void)
0x140018d07  mov     eax, ebx
0x140018d09  jmp     loc_140018EAB
0x140018d0e  mov     rcx, rbx; void *
0x140018d11  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140018d16  test    al, al
0x140018d18  jnz     short loc_140018D4D
0x140018d1a  mov     rcx, [rsp+1B8h]; this
0x140018d22  mov     ebx, 80070057h
0x140018d27  mov     r9d, ebx; char *
0x140018d2a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018d31  mov     edx, 32Dh; void *
0x140018d36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018d3b  nop
0x140018d3c  lea     rcx, [rsp+1B8h+var_168]; this
0x140018d41  call    ??1EngineSampleImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd(void)
0x140018d46  mov     eax, ebx
0x140018d48  jmp     loc_140018EAB
0x140018d4d  xorps   xmm0, xmm0
0x140018d50  movdqu  xmmword ptr [rsp+1B8h+var_190], xmm0
0x140018d56  lea     rdx, [rsp+1B8h+var_190]
0x140018d5b  mov     ecx, [rbx]
0x140018d5d  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140018d62  mov     ebx, eax
0x140018d64  test    eax, eax
0x140018d66  jns     short loc_140018DA6
0x140018d68  mov     rcx, [rsp+1B8h]; this
0x140018d70  mov     r9d, eax; char *
0x140018d73  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018d7a  mov     edx, 332h; void *
0x140018d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018d84  nop
0x140018d85  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140018d8a  test    rcx, rcx
0x140018d8d  jz      short loc_140018D95
0x140018d8f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018d94  nop
0x140018d95  lea     rcx, [rsp+1B8h+var_168]; this
0x140018d9a  call    ??1EngineSampleImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd(void)
0x140018d9f  mov     eax, ebx
0x140018da1  jmp     loc_140018EAB
0x140018da6  lea     rdx, [rsp+1B8h+var_180]
0x140018dab  mov     rcx, [rsp+1B8h+var_190]
0x140018db0  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x140018db5  mov     rcx, [rsp+1B8h+var_180]
0x140018dba  test    rcx, rcx
0x140018dbd  jnz     short loc_140018E11
0x140018dbf  mov     rcx, [rsp+1B8h]; this
0x140018dc7  mov     ebx, 80070057h
0x140018dcc  mov     r9d, ebx; char *
0x140018dcf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018dd6  mov     edx, 337h; void *
0x140018ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018de0  mov     rcx, [rsp+1B8h+var_178]; this
0x140018de5  test    rcx, rcx
0x140018de8  jz      short loc_140018DF0
0x140018dea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018def  nop
0x140018df0  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140018df5  test    rcx, rcx
0x140018df8  jz      short loc_140018E00
0x140018dfa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018dff  nop
0x140018e00  lea     rcx, [rsp+1B8h+var_168]; this
0x140018e05  call    ??1EngineSampleImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd(void)
0x140018e0a  mov     eax, ebx
0x140018e0c  jmp     loc_140018EAB
0x140018e11  add     rcx, 4D8h; this
0x140018e18  call    ?ImportEnd@CacheBuffer@@QEAAJXZ; CacheBuffer::ImportEnd(void)
0x140018e1d  mov     ebx, eax
0x140018e1f  test    eax, eax
0x140018e21  jns     short loc_140018E6D
0x140018e23  mov     rcx, [rsp+1B8h]; this
0x140018e2b  mov     r9d, eax; char *
0x140018e2e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018e35  mov     edx, 33Ah; void *
0x140018e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018e3f  mov     rcx, [rsp+1B8h+var_178]; this
0x140018e44  test    rcx, rcx
0x140018e47  jz      short loc_140018E4F
0x140018e49  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018e4e  nop
0x140018e4f  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140018e54  test    rcx, rcx
0x140018e57  jz      short loc_140018E5F
0x140018e59  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018e5e  nop
0x140018e5f  lea     rcx, [rsp+1B8h+var_168]; this
0x140018e64  call    ??1EngineSampleImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd(void)
0x140018e69  mov     eax, ebx
0x140018e6b  jmp     short loc_140018EAB
0x140018e6d  xor     edx, edx
0x140018e6f  lea     rcx, [rsp+1B8h+var_168]
0x140018e74  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140018e79  mov     rcx, [rsp+1B8h+var_178]; this
0x140018e7e  test    rcx, rcx
0x140018e81  jz      short loc_140018E89
0x140018e83  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018e88  nop
0x140018e89  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140018e8e  test    rcx, rcx
0x140018e91  jz      short loc_140018E99
0x140018e93  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018e98  nop
0x140018e99  lea     rcx, [rsp+1B8h+var_168]; this
0x140018e9e  call    ??1EngineSampleImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportEnd::~EngineSampleImportEnd(void)
0x140018ea3  xor     eax, eax
0x140018ea5  jmp     short loc_140018EAB
0x140018ea7  mov     eax, [rsp+1B8h+var_198]
0x140018eab  mov     rcx, [rsp+1B8h+var_18]
0x140018eb3  xor     rcx, rsp; StackCookie
0x140018eb6  call    __security_check_cookie
0x140018ebb  add     rsp, 1B0h
0x140018ec2  pop     rbx
0x140018ec3  retn
```
