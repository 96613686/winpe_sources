# BioIsoSrvStorageCacheExportBegin

- ea: `0x140018120`
- end: `0x140018365`
- name: `BioIsoSrvStorageCacheExportBegin`
- size: `581`
- prototype: `__int64 __fastcall(void *, unsigned int *, unsigned int *)`
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
- `0x140018120`
- `0x14001836c`
- `0x14001bd40`
- `0x140045fe0`
- `0x140058328`
- `0x140059830`

## string_xrefs

- `0x140018183`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400181c2`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001820b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140018267`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400182cc`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140018146`: `StorageCacheExportBegin`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageCacheExportBegin(int *a1, unsigned int *a2, unsigned int *a3)
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
    (__int64)"StorageCacheExportBegin");
  v14[0] = &BioIsoProvider::StorageCacheExportBegin::`vftable';
  BioIsoProvider::StorageCacheExportBegin::StartActivity((BioIsoProvider::StorageCacheExportBegin *)v14);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x801,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v10);
    BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin((BioIsoProvider::StorageCacheExportBegin *)v14);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x802,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin((BioIsoProvider::StorageCacheExportBegin *)v14);
    return 2147942487LL;
  }
  *(_OWORD *)v11 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v11);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x807,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
LABEL_8:
    BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin((BioIsoProvider::StorageCacheExportBegin *)v14);
    return v8;
  }
  BiometricUnit::PipelineObject(v11[0], &v12);
  if ( v12 )
  {
    v9 = CacheBuffer::ExportBegin((CacheBuffer *)(v12 + 1296), a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80F,
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
    BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin((BioIsoProvider::StorageCacheExportBegin *)v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin((BioIsoProvider::StorageCacheExportBegin *)v14);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140018120  push    rbx
0x140018122  push    rsi
0x140018123  push    rdi
0x140018124  sub     rsp, 1B0h
0x14001812b  mov     rax, cs:__security_cookie
0x140018132  xor     rax, rsp
0x140018135  mov     [rsp+1C8h+var_28], rax
0x14001813d  mov     rsi, r8
0x140018140  mov     rdi, rdx
0x140018143  mov     rbx, rcx
0x140018146  lea     rdx, aStoragecacheex; "StorageCacheExportBegin"
0x14001814d  lea     rcx, [rsp+1C8h+var_178]
0x140018152  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140018157  lea     rax, ??_7StorageCacheExportBegin@BioIsoProvider@@6B@; const BioIsoProvider::StorageCacheExportBegin::`vftable'
0x14001815e  mov     [rsp+1C8h+var_178], rax
0x140018163  lea     rcx, [rsp+1C8h+var_178]; this
0x140018168  call    ?StartActivity@StorageCacheExportBegin@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageCacheExportBegin::StartActivity(void)
0x14001816d  nop
0x14001816e  test    rbx, rbx
0x140018171  jnz     short loc_1400181A6
0x140018173  mov     rcx, [rsp+1C8h]; this
0x14001817b  mov     ebx, 80004003h
0x140018180  mov     r9d, ebx; char *
0x140018183  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001818a  mov     edx, 801h; void *
0x14001818f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018194  nop
0x140018195  lea     rcx, [rsp+1C8h+var_178]; this
0x14001819a  call    ??1StorageCacheExportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin(void)
0x14001819f  mov     eax, ebx
0x1400181a1  jmp     loc_140018349
0x1400181a6  mov     rcx, rbx; void *
0x1400181a9  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400181ae  test    al, al
0x1400181b0  jnz     short loc_1400181E5
0x1400181b2  mov     rcx, [rsp+1C8h]; this
0x1400181ba  mov     ebx, 80070057h
0x1400181bf  mov     r9d, ebx; char *
0x1400181c2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400181c9  mov     edx, 802h; void *
0x1400181ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400181d3  nop
0x1400181d4  lea     rcx, [rsp+1C8h+var_178]; this
0x1400181d9  call    ??1StorageCacheExportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin(void)
0x1400181de  mov     eax, ebx
0x1400181e0  jmp     loc_140018349
0x1400181e5  xorps   xmm0, xmm0
0x1400181e8  movdqu  xmmword ptr [rsp+1C8h+var_1A0], xmm0
0x1400181ee  lea     rdx, [rsp+1C8h+var_1A0]
0x1400181f3  mov     ecx, [rbx]
0x1400181f5  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x1400181fa  mov     ebx, eax
0x1400181fc  test    eax, eax
0x1400181fe  jns     short loc_14001823E
0x140018200  mov     rcx, [rsp+1C8h]; this
0x140018208  mov     r9d, eax; char *
0x14001820b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140018212  mov     edx, 807h; void *
0x140018217  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001821c  nop
0x14001821d  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x140018222  test    rcx, rcx
0x140018225  jz      short loc_14001822D
0x140018227  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001822c  nop
0x14001822d  lea     rcx, [rsp+1C8h+var_178]; this
0x140018232  call    ??1StorageCacheExportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin(void)
0x140018237  mov     eax, ebx
0x140018239  jmp     loc_140018349
0x14001823e  lea     rdx, [rsp+1C8h+var_190]
0x140018243  mov     rcx, [rsp+1C8h+var_1A0]
0x140018248  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x14001824d  mov     rcx, [rsp+1C8h+var_190]
0x140018252  test    rcx, rcx
0x140018255  jnz     short loc_1400182A9
0x140018257  mov     rcx, [rsp+1C8h]; this
0x14001825f  mov     ebx, 80070057h
0x140018264  mov     r9d, ebx; char *
0x140018267  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001826e  mov     edx, 80Ch; void *
0x140018273  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018278  mov     rcx, [rsp+1C8h+var_188]; this
0x14001827d  test    rcx, rcx
0x140018280  jz      short loc_140018288
0x140018282  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018287  nop
0x140018288  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14001828d  test    rcx, rcx
0x140018290  jz      short loc_140018298
0x140018292  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018297  nop
0x140018298  lea     rcx, [rsp+1C8h+var_178]; this
0x14001829d  call    ??1StorageCacheExportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin(void)
0x1400182a2  mov     eax, ebx
0x1400182a4  jmp     loc_140018349
0x1400182a9  add     rcx, 510h; this
0x1400182b0  mov     r8, rsi; unsigned int *
0x1400182b3  mov     rdx, rdi; unsigned int *
0x1400182b6  call    ?ExportBegin@CacheBuffer@@QEAAJPEAK0@Z; CacheBuffer::ExportBegin(ulong *,ulong *)
0x1400182bb  mov     ebx, eax
0x1400182bd  test    eax, eax
0x1400182bf  jns     short loc_14001830B
0x1400182c1  mov     rcx, [rsp+1C8h]; this
0x1400182c9  mov     r9d, eax; char *
0x1400182cc  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400182d3  mov     edx, 80Fh; void *
0x1400182d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400182dd  mov     rcx, [rsp+1C8h+var_188]; this
0x1400182e2  test    rcx, rcx
0x1400182e5  jz      short loc_1400182ED
0x1400182e7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400182ec  nop
0x1400182ed  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x1400182f2  test    rcx, rcx
0x1400182f5  jz      short loc_1400182FD
0x1400182f7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400182fc  nop
0x1400182fd  lea     rcx, [rsp+1C8h+var_178]; this
0x140018302  call    ??1StorageCacheExportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin(void)
0x140018307  mov     eax, ebx
0x140018309  jmp     short loc_140018349
0x14001830b  xor     edx, edx
0x14001830d  lea     rcx, [rsp+1C8h+var_178]
0x140018312  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140018317  mov     rcx, [rsp+1C8h+var_188]; this
0x14001831c  test    rcx, rcx
0x14001831f  jz      short loc_140018327
0x140018321  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018326  nop
0x140018327  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14001832c  test    rcx, rcx
0x14001832f  jz      short loc_140018337
0x140018331  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140018336  nop
0x140018337  lea     rcx, [rsp+1C8h+var_178]; this
0x14001833c  call    ??1StorageCacheExportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportBegin::~StorageCacheExportBegin(void)
0x140018341  xor     eax, eax
0x140018343  jmp     short loc_140018349
0x140018345  mov     eax, [rsp+1C8h+var_1A8]
0x140018349  mov     rcx, [rsp+1C8h+var_28]
0x140018351  xor     rcx, rsp; StackCookie
0x140018354  call    __security_check_cookie
0x140018359  add     rsp, 1B0h
0x140018360  pop     rdi
0x140018361  pop     rsi
0x140018362  pop     rbx
0x140018363  retn
```
