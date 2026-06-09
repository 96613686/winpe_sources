# BioIsoSrvStorageCacheExportNext

- ea: `0x140015f10`
- end: `0x140016163`
- name: `BioIsoSrvStorageCacheExportNext`
- size: `595`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002da0`
- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140013078`
- `0x140015f10`
- `0x14001616c`
- `0x14001bd40`
- `0x140046130`
- `0x140059830`

## string_xrefs

- `0x140015f78`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140015fb7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016000`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001605d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400160c6`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140015f3b`: `StorageCacheExportNext`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageCacheExportNext(
        unsigned int *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  int BiometricUnit; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-1B8h]
  std::_Ref_count_base *v13[2]; // [rsp+28h] [rbp-1B0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-1A0h] BYREF
  std::_Ref_count_base *v15; // [rsp+40h] [rbp-198h]
  _QWORD v16[42]; // [rsp+50h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "StorageCacheExportNext");
  v16[0] = &BioIsoProvider::StorageCacheExportNext::`vftable';
  BioIsoProvider::StorageCacheExportNext::StartActivity((BioIsoProvider::StorageCacheExportNext *)v16);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x821,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v12);
    BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext((BioIsoProvider::StorageCacheExportNext *)v16);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x822,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v12);
    BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext((BioIsoProvider::StorageCacheExportNext *)v16);
    return 2147942487LL;
  }
  *(_OWORD *)v13 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, v13);
  v10 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x827,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v12);
    if ( v13[1] )
      std::_Ref_count_base::_Decref(v13[1]);
LABEL_8:
    BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext((BioIsoProvider::StorageCacheExportNext *)v16);
    return v10;
  }
  BiometricUnit::PipelineObject(v13[0], &v14);
  if ( v14 )
  {
    v11 = CacheBuffer::ExportNext((CacheBuffer *)(v14 + 1296), a2, a3, a4);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82F,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)v11,
        v12);
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      if ( v13[1] )
        std::_Ref_count_base::_Decref(v13[1]);
      goto LABEL_8;
    }
    wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16, 0);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v13[1] )
      std::_Ref_count_base::_Decref(v13[1]);
    BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext((BioIsoProvider::StorageCacheExportNext *)v16);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v12);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v13[1] )
      std::_Ref_count_base::_Decref(v13[1]);
    BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext((BioIsoProvider::StorageCacheExportNext *)v16);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140015f10  push    rbx
0x140015f12  push    rsi
0x140015f13  push    rdi
0x140015f14  push    r14
0x140015f16  sub     rsp, 1B8h
0x140015f1d  mov     rax, cs:__security_cookie
0x140015f24  xor     rax, rsp
0x140015f27  mov     [rsp+1D8h+var_38], rax
0x140015f2f  mov     r14, r9
0x140015f32  mov     esi, r8d
0x140015f35  mov     rdi, rdx
0x140015f38  mov     rbx, rcx
0x140015f3b  lea     rdx, aStoragecacheex_0; "StorageCacheExportNext"
0x140015f42  lea     rcx, [rsp+1D8h+var_188]
0x140015f47  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140015f4c  lea     rax, ??_7StorageCacheExportNext@BioIsoProvider@@6B@; const BioIsoProvider::StorageCacheExportNext::`vftable'
0x140015f53  mov     [rsp+1D8h+var_188], rax
0x140015f58  lea     rcx, [rsp+1D8h+var_188]; this
0x140015f5d  call    ?StartActivity@StorageCacheExportNext@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageCacheExportNext::StartActivity(void)
0x140015f62  nop
0x140015f63  test    rbx, rbx
0x140015f66  jnz     short loc_140015F9B
0x140015f68  mov     rcx, [rsp+1D8h]; this
0x140015f70  mov     ebx, 80004003h
0x140015f75  mov     r9d, ebx; char *
0x140015f78  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140015f7f  mov     edx, 821h; void *
0x140015f84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015f89  nop
0x140015f8a  lea     rcx, [rsp+1D8h+var_188]; this
0x140015f8f  call    ??1StorageCacheExportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext(void)
0x140015f94  mov     eax, ebx
0x140015f96  jmp     loc_140016145
0x140015f9b  mov     rcx, rbx; void *
0x140015f9e  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140015fa3  test    al, al
0x140015fa5  jnz     short loc_140015FDA
0x140015fa7  mov     rcx, [rsp+1D8h]; this
0x140015faf  mov     ebx, 80070057h
0x140015fb4  mov     r9d, ebx; char *
0x140015fb7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140015fbe  mov     edx, 822h; void *
0x140015fc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015fc8  nop
0x140015fc9  lea     rcx, [rsp+1D8h+var_188]; this
0x140015fce  call    ??1StorageCacheExportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext(void)
0x140015fd3  mov     eax, ebx
0x140015fd5  jmp     loc_140016145
0x140015fda  xorps   xmm0, xmm0
0x140015fdd  movdqu  xmmword ptr [rsp+1D8h+var_1B0], xmm0
0x140015fe3  lea     rdx, [rsp+1D8h+var_1B0]
0x140015fe8  mov     ecx, [rbx]
0x140015fea  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140015fef  mov     ebx, eax
0x140015ff1  test    eax, eax
0x140015ff3  jns     short loc_140016033
0x140015ff5  mov     rcx, [rsp+1D8h]; this
0x140015ffd  mov     r9d, eax; char *
0x140016000  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016007  mov     edx, 827h; void *
0x14001600c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016011  nop
0x140016012  mov     rcx, [rsp+1D8h+var_1B0+8]; this
0x140016017  test    rcx, rcx
0x14001601a  jz      short loc_140016022
0x14001601c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016021  nop
0x140016022  lea     rcx, [rsp+1D8h+var_188]; this
0x140016027  call    ??1StorageCacheExportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext(void)
0x14001602c  mov     eax, ebx
0x14001602e  jmp     loc_140016145
0x140016033  lea     rdx, [rsp+1D8h+var_1A0]
0x140016038  mov     rcx, [rsp+1D8h+var_1B0]
0x14001603d  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x140016042  nop
0x140016043  mov     rcx, [rsp+1D8h+var_1A0]
0x140016048  test    rcx, rcx
0x14001604b  jnz     short loc_1400160A0
0x14001604d  mov     rcx, [rsp+1D8h]; this
0x140016055  mov     ebx, 80070057h
0x14001605a  mov     r9d, ebx; char *
0x14001605d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016064  mov     edx, 82Ch; void *
0x140016069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001606e  nop
0x14001606f  mov     rcx, [rsp+1D8h+var_198]; this
0x140016074  test    rcx, rcx
0x140016077  jz      short loc_14001607F
0x140016079  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001607e  nop
0x14001607f  mov     rcx, [rsp+1D8h+var_1B0+8]; this
0x140016084  test    rcx, rcx
0x140016087  jz      short loc_14001608F
0x140016089  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001608e  nop
0x14001608f  lea     rcx, [rsp+1D8h+var_188]; this
0x140016094  call    ??1StorageCacheExportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext(void)
0x140016099  mov     eax, ebx
0x14001609b  jmp     loc_140016145
0x1400160a0  add     rcx, 510h; this
0x1400160a7  mov     r9, r14; unsigned int *
0x1400160aa  mov     r8d, esi; unsigned int
0x1400160ad  mov     rdx, rdi; unsigned __int8 *
0x1400160b0  call    ?ExportNext@CacheBuffer@@QEAAJPEAEKPEAK@Z; CacheBuffer::ExportNext(uchar *,ulong,ulong *)
0x1400160b5  mov     ebx, eax
0x1400160b7  test    eax, eax
0x1400160b9  jns     short loc_140016106
0x1400160bb  mov     rcx, [rsp+1D8h]; this
0x1400160c3  mov     r9d, eax; char *
0x1400160c6  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400160cd  mov     edx, 82Fh; void *
0x1400160d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400160d7  nop
0x1400160d8  mov     rcx, [rsp+1D8h+var_198]; this
0x1400160dd  test    rcx, rcx
0x1400160e0  jz      short loc_1400160E8
0x1400160e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400160e7  nop
0x1400160e8  mov     rcx, [rsp+1D8h+var_1B0+8]; this
0x1400160ed  test    rcx, rcx
0x1400160f0  jz      short loc_1400160F8
0x1400160f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400160f7  nop
0x1400160f8  lea     rcx, [rsp+1D8h+var_188]; this
0x1400160fd  call    ??1StorageCacheExportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext(void)
0x140016102  mov     eax, ebx
0x140016104  jmp     short loc_140016145
0x140016106  xor     edx, edx
0x140016108  lea     rcx, [rsp+1D8h+var_188]
0x14001610d  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140016112  nop
0x140016113  mov     rcx, [rsp+1D8h+var_198]; this
0x140016118  test    rcx, rcx
0x14001611b  jz      short loc_140016123
0x14001611d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016122  nop
0x140016123  mov     rcx, [rsp+1D8h+var_1B0+8]; this
0x140016128  test    rcx, rcx
0x14001612b  jz      short loc_140016133
0x14001612d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016132  nop
0x140016133  lea     rcx, [rsp+1D8h+var_188]; this
0x140016138  call    ??1StorageCacheExportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportNext::~StorageCacheExportNext(void)
0x14001613d  xor     eax, eax
0x14001613f  jmp     short loc_140016145
0x140016141  mov     eax, [rsp+1D8h+var_1B8]
0x140016145  mov     rcx, [rsp+1D8h+var_38]
0x14001614d  xor     rcx, rsp; StackCookie
0x140016150  call    __security_check_cookie
0x140016155  add     rsp, 1B8h
0x14001615c  pop     r14
0x14001615e  pop     rdi
0x14001615f  pop     rsi
0x140016160  pop     rbx
0x140016161  retn
```
