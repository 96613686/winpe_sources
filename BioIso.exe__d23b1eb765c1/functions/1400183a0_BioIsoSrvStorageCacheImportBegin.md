# BioIsoSrvStorageCacheImportBegin

- ea: `0x1400183a0`
- end: `0x1400185e7`
- name: `BioIsoSrvStorageCacheImportBegin`
- size: `583`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int *)`
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
- `0x1400183a0`
- `0x1400185f0`
- `0x14001bd40`
- `0x1400461d8`
- `0x140058380`
- `0x140059830`

## string_xrefs

- `0x140018402`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140018441`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001848a`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400184e7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001854c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400183c5`: `StorageCacheImportBegin`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageCacheImportBegin(int *a1, unsigned int a2, unsigned int *a3)
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
    (__int64)v14,
    (__int64)"StorageCacheImportBegin");
  v14[0] = &BioIsoProvider::StorageCacheImportBegin::`vftable';
  BioIsoProvider::StorageCacheImportBegin::StartActivity((BioIsoProvider::StorageCacheImportBegin *)v14);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v10);
    BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin((BioIsoProvider::StorageCacheImportBegin *)v14);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin((BioIsoProvider::StorageCacheImportBegin *)v14);
    return 2147942487LL;
  }
  *(_OWORD *)v11 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v11);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7AC,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
LABEL_8:
    BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin((BioIsoProvider::StorageCacheImportBegin *)v14);
    return v8;
  }
  BiometricUnit::PipelineObject(v11[0], &v12);
  if ( v12 )
  {
    v9 = CacheBuffer::ImportBegin((CacheBuffer *)(v12 + 1296), a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B4,
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
    BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin((BioIsoProvider::StorageCacheImportBegin *)v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B1,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin((BioIsoProvider::StorageCacheImportBegin *)v14);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1400183a0  push    rbx
0x1400183a2  push    rsi
0x1400183a3  push    rdi
0x1400183a4  sub     rsp, 1B0h
0x1400183ab  mov     rax, cs:__security_cookie
0x1400183b2  xor     rax, rsp
0x1400183b5  mov     [rsp+1C8h+var_28], rax
0x1400183bd  mov     rsi, r8
0x1400183c0  mov     edi, edx
0x1400183c2  mov     rbx, rcx
0x1400183c5  lea     rdx, aStoragecacheim; "StorageCacheImportBegin"
0x1400183cc  lea     rcx, [rsp+1C8h+var_178]
0x1400183d1  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400183d6  lea     rax, ??_7StorageCacheImportBegin@BioIsoProvider@@6B@; const BioIsoProvider::StorageCacheImportBegin::`vftable'
0x1400183dd  mov     [rsp+1C8h+var_178], rax
0x1400183e2  lea     rcx, [rsp+1C8h+var_178]; this
0x1400183e7  call    ?StartActivity@StorageCacheImportBegin@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageCacheImportBegin::StartActivity(void)
0x1400183ec  nop
0x1400183ed  test    rbx, rbx
0x1400183f0  jnz     short loc_140018425
0x1400183f2  mov     rcx, [rsp+1C8h]; this
0x1400183fa  mov     ebx, 80004003h
0x1400183ff  mov     r9d, ebx; char *
0x140018402  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018409  mov     edx, 7A6h; void *
0x14001840e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018413  nop
0x140018414  lea     rcx, [rsp+1C8h+var_178]; this
0x140018419  call    ??1StorageCacheImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin(void)
0x14001841e  mov     eax, ebx
0x140018420  jmp     loc_1400185CB
0x140018425  mov     rcx, rbx; void *
0x140018428  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14001842d  test    al, al
0x14001842f  jnz     short loc_140018464
0x140018431  mov     rcx, [rsp+1C8h]; this
0x140018439  mov     ebx, 80070057h
0x14001843e  mov     r9d, ebx; char *
0x140018441  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018448  mov     edx, 7A7h; void *
0x14001844d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018452  nop
0x140018453  lea     rcx, [rsp+1C8h+var_178]; this
0x140018458  call    ??1StorageCacheImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin(void)
0x14001845d  mov     eax, ebx
0x14001845f  jmp     loc_1400185CB
0x140018464  xorps   xmm0, xmm0
0x140018467  movdqu  xmmword ptr [rsp+1C8h+var_1A0], xmm0
0x14001846d  lea     rdx, [rsp+1C8h+var_1A0]
0x140018472  mov     ecx, [rbx]
0x140018474  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140018479  mov     ebx, eax
0x14001847b  test    eax, eax
0x14001847d  jns     short loc_1400184BD
0x14001847f  mov     rcx, [rsp+1C8h]; this
0x140018487  mov     r9d, eax; char *
0x14001848a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018491  mov     edx, 7ACh; void *
0x140018496  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001849b  nop
0x14001849c  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x1400184a1  test    rcx, rcx
0x1400184a4  jz      short loc_1400184AC
0x1400184a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400184ab  nop
0x1400184ac  lea     rcx, [rsp+1C8h+var_178]; this
0x1400184b1  call    ??1StorageCacheImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin(void)
0x1400184b6  mov     eax, ebx
0x1400184b8  jmp     loc_1400185CB
0x1400184bd  lea     rdx, [rsp+1C8h+var_190]
0x1400184c2  mov     rcx, [rsp+1C8h+var_1A0]
0x1400184c7  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x1400184cc  nop
0x1400184cd  mov     rcx, [rsp+1C8h+var_190]
0x1400184d2  test    rcx, rcx
0x1400184d5  jnz     short loc_14001852A
0x1400184d7  mov     rcx, [rsp+1C8h]; this
0x1400184df  mov     ebx, 80070057h
0x1400184e4  mov     r9d, ebx; char *
0x1400184e7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400184ee  mov     edx, 7B1h; void *
0x1400184f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400184f8  nop
0x1400184f9  mov     rcx, [rsp+1C8h+var_188]; this
0x1400184fe  test    rcx, rcx
0x140018501  jz      short loc_140018509
0x140018503  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018508  nop
0x140018509  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14001850e  test    rcx, rcx
0x140018511  jz      short loc_140018519
0x140018513  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018518  nop
0x140018519  lea     rcx, [rsp+1C8h+var_178]; this
0x14001851e  call    ??1StorageCacheImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin(void)
0x140018523  mov     eax, ebx
0x140018525  jmp     loc_1400185CB
0x14001852a  add     rcx, 510h; this
0x140018531  mov     r8, rsi; unsigned int *
0x140018534  mov     edx, edi; unsigned int
0x140018536  call    ?ImportBegin@CacheBuffer@@QEAAJKPEAK@Z; CacheBuffer::ImportBegin(ulong,ulong *)
0x14001853b  mov     ebx, eax
0x14001853d  test    eax, eax
0x14001853f  jns     short loc_14001858C
0x140018541  mov     rcx, [rsp+1C8h]; this
0x140018549  mov     r9d, eax; char *
0x14001854c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018553  mov     edx, 7B4h; void *
0x140018558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001855d  nop
0x14001855e  mov     rcx, [rsp+1C8h+var_188]; this
0x140018563  test    rcx, rcx
0x140018566  jz      short loc_14001856E
0x140018568  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001856d  nop
0x14001856e  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x140018573  test    rcx, rcx
0x140018576  jz      short loc_14001857E
0x140018578  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001857d  nop
0x14001857e  lea     rcx, [rsp+1C8h+var_178]; this
0x140018583  call    ??1StorageCacheImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin(void)
0x140018588  mov     eax, ebx
0x14001858a  jmp     short loc_1400185CB
0x14001858c  xor     edx, edx
0x14001858e  lea     rcx, [rsp+1C8h+var_178]
0x140018593  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140018598  nop
0x140018599  mov     rcx, [rsp+1C8h+var_188]; this
0x14001859e  test    rcx, rcx
0x1400185a1  jz      short loc_1400185A9
0x1400185a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400185a8  nop
0x1400185a9  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x1400185ae  test    rcx, rcx
0x1400185b1  jz      short loc_1400185B9
0x1400185b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400185b8  nop
0x1400185b9  lea     rcx, [rsp+1C8h+var_178]; this
0x1400185be  call    ??1StorageCacheImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheImportBegin::~StorageCacheImportBegin(void)
0x1400185c3  xor     eax, eax
0x1400185c5  jmp     short loc_1400185CB
0x1400185c7  mov     eax, [rsp+1C8h+var_1A8]
0x1400185cb  mov     rcx, [rsp+1C8h+var_28]
0x1400185d3  xor     rcx, rsp; StackCookie
0x1400185d6  call    __security_check_cookie
0x1400185db  add     rsp, 1B0h
0x1400185e2  pop     rdi
0x1400185e3  pop     rsi
0x1400185e4  pop     rbx
0x1400185e5  retn
```
