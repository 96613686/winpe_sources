# BioIsoSrvStorageCacheImportNext

- ea: `0x1400161a0`
- end: `0x1400163e9`
- name: `BioIsoSrvStorageCacheImportNext`
- size: `585`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int8 *, unsigned int)`
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
- `0x1400161a0`
- `0x1400163f0`
- `0x14001bd40`
- `0x140046328`
- `0x140058440`
- `0x140059830`

## string_xrefs

- `0x140016203`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016242`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001628b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400162e8`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001634e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400161c6`: `StorageCacheImportNext`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageCacheImportNext(unsigned int *a1, unsigned __int8 *a2, unsigned int a3)
{
  int BiometricUnit; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // [rsp+20h] [rbp-1A8h]
  std::_Ref_count_base *v11[2]; // [rsp+28h] [rbp-1A0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-190h] BYREF
  std::_Ref_count_base *v13; // [rsp+40h] [rbp-188h]
  _QWORD v14[42]; // [rsp+50h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v14,
    "StorageCacheImportNext");
  v14[0] = &BioIsoProvider::StorageCacheImportNext::`vftable';
  BioIsoProvider::StorageCacheImportNext::StartActivity((BioIsoProvider::StorageCacheImportNext *)v14);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C5,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v10);
    BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext((BioIsoProvider::StorageCacheImportNext *)v14);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext((BioIsoProvider::StorageCacheImportNext *)v14);
    return 2147942487LL;
  }
  *(_OWORD *)v11 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, v11);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
LABEL_8:
    BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext((BioIsoProvider::StorageCacheImportNext *)v14);
    return v8;
  }
  BiometricUnit::PipelineObject(v11[0], &v12);
  if ( v12 )
  {
    v9 = CacheBuffer::ImportNext((CacheBuffer *)(v12 + 1296), a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D3,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)v9,
        v10);
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
      if ( v11[1] )
        std::_Ref_count_base::_Decref(v11[1]);
      goto LABEL_8;
    }
    wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v14, 0);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext((BioIsoProvider::StorageCacheImportNext *)v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D0,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext((BioIsoProvider::StorageCacheImportNext *)v14);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1400161a0  push    rbx
0x1400161a2  push    rsi
0x1400161a3  push    rdi
0x1400161a4  sub     rsp, 1B0h
0x1400161ab  mov     rax, cs:__security_cookie
0x1400161b2  xor     rax, rsp
0x1400161b5  mov     [rsp+1C8h+var_28], rax
0x1400161bd  mov     esi, r8d
0x1400161c0  mov     rdi, rdx
0x1400161c3  mov     rbx, rcx
0x1400161c6  lea     rdx, aStoragecacheim_0; "StorageCacheImportNext"
0x1400161cd  lea     rcx, [rsp+1C8h+var_178]
0x1400161d2  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400161d7  lea     rax, ??_7StorageCacheImportNext@BioIsoProvider@@6B@; const BioIsoProvider::StorageCacheImportNext::`vftable'
0x1400161de  mov     [rsp+1C8h+var_178], rax
0x1400161e3  lea     rcx, [rsp+1C8h+var_178]; this
0x1400161e8  call    ?StartActivity@StorageCacheImportNext@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageCacheImportNext::StartActivity(void)
0x1400161ed  nop
0x1400161ee  test    rbx, rbx
0x1400161f1  jnz     short loc_140016226
0x1400161f3  mov     rcx, [rsp+1C8h]; this
0x1400161fb  mov     ebx, 80004003h
0x140016200  mov     r9d, ebx; char *
0x140016203  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001620a  mov     edx, 7C5h; void *
0x14001620f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016214  nop
0x140016215  lea     rcx, [rsp+1C8h+var_178]; this
0x14001621a  call    ??1StorageCacheImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext(void)
0x14001621f  mov     eax, ebx
0x140016221  jmp     loc_1400163CD
0x140016226  mov     rcx, rbx; void *
0x140016229  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14001622e  test    al, al
0x140016230  jnz     short loc_140016265
0x140016232  mov     rcx, [rsp+1C8h]; this
0x14001623a  mov     ebx, 80070057h
0x14001623f  mov     r9d, ebx; char *
0x140016242  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016249  mov     edx, 7C6h; void *
0x14001624e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016253  nop
0x140016254  lea     rcx, [rsp+1C8h+var_178]; this
0x140016259  call    ??1StorageCacheImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext(void)
0x14001625e  mov     eax, ebx
0x140016260  jmp     loc_1400163CD
0x140016265  xorps   xmm0, xmm0
0x140016268  movdqu  xmmword ptr [rsp+1C8h+var_1A0], xmm0
0x14001626e  lea     rdx, [rsp+1C8h+var_1A0]
0x140016273  mov     ecx, [rbx]
0x140016275  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14001627a  mov     ebx, eax
0x14001627c  test    eax, eax
0x14001627e  jns     short loc_1400162BE
0x140016280  mov     rcx, [rsp+1C8h]; this
0x140016288  mov     r9d, eax; char *
0x14001628b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016292  mov     edx, 7CBh; void *
0x140016297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001629c  nop
0x14001629d  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x1400162a2  test    rcx, rcx
0x1400162a5  jz      short loc_1400162AD
0x1400162a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400162ac  nop
0x1400162ad  lea     rcx, [rsp+1C8h+var_178]; this
0x1400162b2  call    ??1StorageCacheImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext(void)
0x1400162b7  mov     eax, ebx
0x1400162b9  jmp     loc_1400163CD
0x1400162be  lea     rdx, [rsp+1C8h+var_190]
0x1400162c3  mov     rcx, [rsp+1C8h+var_1A0]
0x1400162c8  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x1400162cd  nop
0x1400162ce  mov     rcx, [rsp+1C8h+var_190]
0x1400162d3  test    rcx, rcx
0x1400162d6  jnz     short loc_14001632B
0x1400162d8  mov     rcx, [rsp+1C8h]; this
0x1400162e0  mov     ebx, 80070057h
0x1400162e5  mov     r9d, ebx; char *
0x1400162e8  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400162ef  mov     edx, 7D0h; void *
0x1400162f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400162f9  nop
0x1400162fa  mov     rcx, [rsp+1C8h+var_188]; this
0x1400162ff  test    rcx, rcx
0x140016302  jz      short loc_14001630A
0x140016304  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016309  nop
0x14001630a  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14001630f  test    rcx, rcx
0x140016312  jz      short loc_14001631A
0x140016314  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016319  nop
0x14001631a  lea     rcx, [rsp+1C8h+var_178]; this
0x14001631f  call    ??1StorageCacheImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext(void)
0x140016324  mov     eax, ebx
0x140016326  jmp     loc_1400163CD
0x14001632b  add     rcx, 510h; this
0x140016332  mov     r8d, esi; unsigned int
0x140016335  mov     rdx, rdi; unsigned __int8 *
0x140016338  call    ?ImportNext@CacheBuffer@@QEAAJPEAEK@Z; CacheBuffer::ImportNext(uchar *,ulong)
0x14001633d  mov     ebx, eax
0x14001633f  test    eax, eax
0x140016341  jns     short loc_14001638E
0x140016343  mov     rcx, [rsp+1C8h]; this
0x14001634b  mov     r9d, eax; char *
0x14001634e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016355  mov     edx, 7D3h; void *
0x14001635a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001635f  nop
0x140016360  mov     rcx, [rsp+1C8h+var_188]; this
0x140016365  test    rcx, rcx
0x140016368  jz      short loc_140016370
0x14001636a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001636f  nop
0x140016370  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x140016375  test    rcx, rcx
0x140016378  jz      short loc_140016380
0x14001637a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001637f  nop
0x140016380  lea     rcx, [rsp+1C8h+var_178]; this
0x140016385  call    ??1StorageCacheImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext(void)
0x14001638a  mov     eax, ebx
0x14001638c  jmp     short loc_1400163CD
0x14001638e  xor     edx, edx
0x140016390  lea     rcx, [rsp+1C8h+var_178]
0x140016395  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001639a  nop
0x14001639b  mov     rcx, [rsp+1C8h+var_188]; this
0x1400163a0  test    rcx, rcx
0x1400163a3  jz      short loc_1400163AB
0x1400163a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400163aa  nop
0x1400163ab  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x1400163b0  test    rcx, rcx
0x1400163b3  jz      short loc_1400163BB
0x1400163b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400163ba  nop
0x1400163bb  lea     rcx, [rsp+1C8h+var_178]; this
0x1400163c0  call    ??1StorageCacheImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportNext::~StorageCacheImportNext(void)
0x1400163c5  xor     eax, eax
0x1400163c7  jmp     short loc_1400163CD
0x1400163c9  mov     eax, [rsp+1C8h+var_1A8]
0x1400163cd  mov     rcx, [rsp+1C8h+var_28]
0x1400163d5  xor     rcx, rsp; StackCookie
0x1400163d8  call    __security_check_cookie
0x1400163dd  add     rsp, 1B0h
0x1400163e4  pop     rdi
0x1400163e5  pop     rsi
0x1400163e6  pop     rbx
0x1400163e7  retn
```
