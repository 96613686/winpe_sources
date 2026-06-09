# BioIsoSrvStorageCacheImportEnd

- ea: `0x140016ef0`
- end: `0x140017125`
- name: `BioIsoSrvStorageCacheImportEnd`
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
- `0x140016ef0`
- `0x14001712c`
- `0x14001bd40`
- `0x140046280`
- `0x14005841c`
- `0x140059830`

## string_xrefs

- `0x140016f4b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016f8a`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016fd3`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001702f`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001708e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016f0e`: `StorageCacheImportEnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageCacheImportEnd(int *a1)
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
    (__int64)"StorageCacheImportEnd");
  v10[0] = &BioIsoProvider::StorageCacheImportEnd::`vftable';
  BioIsoProvider::StorageCacheImportEnd::StartActivity((BioIsoProvider::StorageCacheImportEnd *)v10);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v6);
    BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd((BioIsoProvider::StorageCacheImportEnd *)v10);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E3,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v6);
    BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd((BioIsoProvider::StorageCacheImportEnd *)v10);
    return 2147942487LL;
  }
  *(_OWORD *)v7 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v7);
  v4 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E8,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v6);
    if ( v7[1] )
      std::_Ref_count_base::_Decref(v7[1]);
LABEL_8:
    BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd((BioIsoProvider::StorageCacheImportEnd *)v10);
    return v4;
  }
  BiometricUnit::PipelineObject(v7[0], &v8);
  if ( v8 )
  {
    v5 = CacheBuffer::ImportEnd((CacheBuffer *)(v8 + 1296));
    v4 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F0,
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
    BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd((BioIsoProvider::StorageCacheImportEnd *)v10);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7ED,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v6);
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    if ( v7[1] )
      std::_Ref_count_base::_Decref(v7[1]);
    BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd((BioIsoProvider::StorageCacheImportEnd *)v10);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140016ef0  push    rbx
0x140016ef2  sub     rsp, 1B0h
0x140016ef9  mov     rax, cs:__security_cookie
0x140016f00  xor     rax, rsp
0x140016f03  mov     [rsp+1B8h+var_18], rax
0x140016f0b  mov     rbx, rcx
0x140016f0e  lea     rdx, aStoragecacheim_1; "StorageCacheImportEnd"
0x140016f15  lea     rcx, [rsp+1B8h+var_168]
0x140016f1a  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140016f1f  lea     rax, ??_7StorageCacheImportEnd@BioIsoProvider@@6B@; const BioIsoProvider::StorageCacheImportEnd::`vftable'
0x140016f26  mov     [rsp+1B8h+var_168], rax
0x140016f2b  lea     rcx, [rsp+1B8h+var_168]; this
0x140016f30  call    ?StartActivity@StorageCacheImportEnd@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageCacheImportEnd::StartActivity(void)
0x140016f35  nop
0x140016f36  test    rbx, rbx
0x140016f39  jnz     short loc_140016F6E
0x140016f3b  mov     rcx, [rsp+1B8h]; this
0x140016f43  mov     ebx, 80004003h
0x140016f48  mov     r9d, ebx; char *
0x140016f4b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016f52  mov     edx, 7E2h; void *
0x140016f57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016f5c  nop
0x140016f5d  lea     rcx, [rsp+1B8h+var_168]; this
0x140016f62  call    ??1StorageCacheImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd(void)
0x140016f67  mov     eax, ebx
0x140016f69  jmp     loc_14001710B
0x140016f6e  mov     rcx, rbx; void *
0x140016f71  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140016f76  test    al, al
0x140016f78  jnz     short loc_140016FAD
0x140016f7a  mov     rcx, [rsp+1B8h]; this
0x140016f82  mov     ebx, 80070057h
0x140016f87  mov     r9d, ebx; char *
0x140016f8a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016f91  mov     edx, 7E3h; void *
0x140016f96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016f9b  nop
0x140016f9c  lea     rcx, [rsp+1B8h+var_168]; this
0x140016fa1  call    ??1StorageCacheImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd(void)
0x140016fa6  mov     eax, ebx
0x140016fa8  jmp     loc_14001710B
0x140016fad  xorps   xmm0, xmm0
0x140016fb0  movdqu  xmmword ptr [rsp+1B8h+var_190], xmm0
0x140016fb6  lea     rdx, [rsp+1B8h+var_190]
0x140016fbb  mov     ecx, [rbx]
0x140016fbd  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140016fc2  mov     ebx, eax
0x140016fc4  test    eax, eax
0x140016fc6  jns     short loc_140017006
0x140016fc8  mov     rcx, [rsp+1B8h]; this
0x140016fd0  mov     r9d, eax; char *
0x140016fd3  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016fda  mov     edx, 7E8h; void *
0x140016fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016fe4  nop
0x140016fe5  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140016fea  test    rcx, rcx
0x140016fed  jz      short loc_140016FF5
0x140016fef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016ff4  nop
0x140016ff5  lea     rcx, [rsp+1B8h+var_168]; this
0x140016ffa  call    ??1StorageCacheImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd(void)
0x140016fff  mov     eax, ebx
0x140017001  jmp     loc_14001710B
0x140017006  lea     rdx, [rsp+1B8h+var_180]
0x14001700b  mov     rcx, [rsp+1B8h+var_190]
0x140017010  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x140017015  mov     rcx, [rsp+1B8h+var_180]
0x14001701a  test    rcx, rcx
0x14001701d  jnz     short loc_140017071
0x14001701f  mov     rcx, [rsp+1B8h]; this
0x140017027  mov     ebx, 80070057h
0x14001702c  mov     r9d, ebx; char *
0x14001702f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140017036  mov     edx, 7EDh; void *
0x14001703b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017040  mov     rcx, [rsp+1B8h+var_178]; this
0x140017045  test    rcx, rcx
0x140017048  jz      short loc_140017050
0x14001704a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001704f  nop
0x140017050  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140017055  test    rcx, rcx
0x140017058  jz      short loc_140017060
0x14001705a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001705f  nop
0x140017060  lea     rcx, [rsp+1B8h+var_168]; this
0x140017065  call    ??1StorageCacheImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd(void)
0x14001706a  mov     eax, ebx
0x14001706c  jmp     loc_14001710B
0x140017071  add     rcx, 510h; this
0x140017078  call    ?ImportEnd@CacheBuffer@@QEAAJXZ; CacheBuffer::ImportEnd(void)
0x14001707d  mov     ebx, eax
0x14001707f  test    eax, eax
0x140017081  jns     short loc_1400170CD
0x140017083  mov     rcx, [rsp+1B8h]; this
0x14001708b  mov     r9d, eax; char *
0x14001708e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140017095  mov     edx, 7F0h; void *
0x14001709a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001709f  mov     rcx, [rsp+1B8h+var_178]; this
0x1400170a4  test    rcx, rcx
0x1400170a7  jz      short loc_1400170AF
0x1400170a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400170ae  nop
0x1400170af  mov     rcx, [rsp+1B8h+var_190+8]; this
0x1400170b4  test    rcx, rcx
0x1400170b7  jz      short loc_1400170BF
0x1400170b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400170be  nop
0x1400170bf  lea     rcx, [rsp+1B8h+var_168]; this
0x1400170c4  call    ??1StorageCacheImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd(void)
0x1400170c9  mov     eax, ebx
0x1400170cb  jmp     short loc_14001710B
0x1400170cd  xor     edx, edx
0x1400170cf  lea     rcx, [rsp+1B8h+var_168]
0x1400170d4  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400170d9  mov     rcx, [rsp+1B8h+var_178]; this
0x1400170de  test    rcx, rcx
0x1400170e1  jz      short loc_1400170E9
0x1400170e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400170e8  nop
0x1400170e9  mov     rcx, [rsp+1B8h+var_190+8]; this
0x1400170ee  test    rcx, rcx
0x1400170f1  jz      short loc_1400170F9
0x1400170f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400170f8  nop
0x1400170f9  lea     rcx, [rsp+1B8h+var_168]; this
0x1400170fe  call    ??1StorageCacheImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportEnd::~StorageCacheImportEnd(void)
0x140017103  xor     eax, eax
0x140017105  jmp     short loc_14001710B
0x140017107  mov     eax, [rsp+1B8h+var_198]
0x14001710b  mov     rcx, [rsp+1B8h+var_18]
0x140017113  xor     rcx, rsp; StackCookie
0x140017116  call    __security_check_cookie
0x14001711b  add     rsp, 1B0h
0x140017122  pop     rbx
0x140017123  retn
```
