# BioIsoSrvSensorAsyncRawBufferImportNext

- ea: `0x14000b070`
- end: `0x14000b29c`
- name: `BioIsoSrvSensorAsyncRawBufferImportNext`
- size: `556`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x14000b070`
- `0x14000b984`
- `0x14000dd30`
- `0x140013078`
- `0x14001bd40`
- `0x140058440`
- `0x140059830`

## string_xrefs

- `0x14000b0b6`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000b0f5`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000b13e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000b19b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000b201`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall BioIsoSrvSensorAsyncRawBufferImportNext(int *a1, unsigned __int8 *a2, unsigned int a3)
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

  BioIsoProvider::AsyncRawBufferImportNext::Start<>((BioIsoProvider::AsyncRawBufferImportNext *)v14);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v10);
    BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext((BioIsoProvider::AsyncRawBufferImportNext *)v14);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext((BioIsoProvider::AsyncRawBufferImportNext *)v14);
    return 2147942487LL;
  }
  *(_OWORD *)v11 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v11);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
LABEL_8:
    BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext((BioIsoProvider::AsyncRawBufferImportNext *)v14);
    return v8;
  }
  BiometricUnit::PipelineObject(v11[0], &v12);
  if ( v12 )
  {
    v9 = CacheBuffer::ImportNext((CacheBuffer *)(v12 + 1128), a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x143,
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
    BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext((BioIsoProvider::AsyncRawBufferImportNext *)v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext((BioIsoProvider::AsyncRawBufferImportNext *)v14);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14000b070  push    rbx
0x14000b072  push    rsi
0x14000b073  push    rdi
0x14000b074  sub     rsp, 1B0h
0x14000b07b  mov     rax, cs:__security_cookie
0x14000b082  xor     rax, rsp
0x14000b085  mov     [rsp+1C8h+var_28], rax
0x14000b08d  mov     esi, r8d
0x14000b090  mov     rdi, rdx
0x14000b093  mov     rbx, rcx
0x14000b096  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b09b  call    ??$Start@$$V@AsyncRawBufferImportNext@BioIsoProvider@@SA?AV01@XZ; BioIsoProvider::AsyncRawBufferImportNext::Start<>(void)
0x14000b0a0  nop
0x14000b0a1  test    rbx, rbx
0x14000b0a4  jnz     short loc_14000B0D9
0x14000b0a6  mov     rcx, [rsp+1C8h]; this
0x14000b0ae  mov     ebx, 80004003h
0x14000b0b3  mov     r9d, ebx; char *
0x14000b0b6  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b0bd  mov     edx, 135h; void *
0x14000b0c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b0c7  nop
0x14000b0c8  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b0cd  call    ??1AsyncRawBufferImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext(void)
0x14000b0d2  mov     eax, ebx
0x14000b0d4  jmp     loc_14000B280
0x14000b0d9  mov     rcx, rbx; void *
0x14000b0dc  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14000b0e1  test    al, al
0x14000b0e3  jnz     short loc_14000B118
0x14000b0e5  mov     rcx, [rsp+1C8h]; this
0x14000b0ed  mov     ebx, 80070057h
0x14000b0f2  mov     r9d, ebx; char *
0x14000b0f5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b0fc  mov     edx, 136h; void *
0x14000b101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b106  nop
0x14000b107  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b10c  call    ??1AsyncRawBufferImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext(void)
0x14000b111  mov     eax, ebx
0x14000b113  jmp     loc_14000B280
0x14000b118  xorps   xmm0, xmm0
0x14000b11b  movdqu  xmmword ptr [rsp+1C8h+var_1A0], xmm0
0x14000b121  lea     rdx, [rsp+1C8h+var_1A0]
0x14000b126  mov     ecx, [rbx]
0x14000b128  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14000b12d  mov     ebx, eax
0x14000b12f  test    eax, eax
0x14000b131  jns     short loc_14000B171
0x14000b133  mov     rcx, [rsp+1C8h]; this
0x14000b13b  mov     r9d, eax; char *
0x14000b13e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b145  mov     edx, 13Bh; void *
0x14000b14a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b14f  nop
0x14000b150  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000b155  test    rcx, rcx
0x14000b158  jz      short loc_14000B160
0x14000b15a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b15f  nop
0x14000b160  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b165  call    ??1AsyncRawBufferImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext(void)
0x14000b16a  mov     eax, ebx
0x14000b16c  jmp     loc_14000B280
0x14000b171  lea     rdx, [rsp+1C8h+var_190]
0x14000b176  mov     rcx, [rsp+1C8h+var_1A0]
0x14000b17b  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x14000b180  nop
0x14000b181  mov     rcx, [rsp+1C8h+var_190]
0x14000b186  test    rcx, rcx
0x14000b189  jnz     short loc_14000B1DE
0x14000b18b  mov     rcx, [rsp+1C8h]; this
0x14000b193  mov     ebx, 80070057h
0x14000b198  mov     r9d, ebx; char *
0x14000b19b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b1a2  mov     edx, 140h; void *
0x14000b1a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b1ac  nop
0x14000b1ad  mov     rcx, [rsp+1C8h+var_188]; this
0x14000b1b2  test    rcx, rcx
0x14000b1b5  jz      short loc_14000B1BD
0x14000b1b7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b1bc  nop
0x14000b1bd  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000b1c2  test    rcx, rcx
0x14000b1c5  jz      short loc_14000B1CD
0x14000b1c7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b1cc  nop
0x14000b1cd  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b1d2  call    ??1AsyncRawBufferImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext(void)
0x14000b1d7  mov     eax, ebx
0x14000b1d9  jmp     loc_14000B280
0x14000b1de  add     rcx, 468h; this
0x14000b1e5  mov     r8d, esi; unsigned int
0x14000b1e8  mov     rdx, rdi; unsigned __int8 *
0x14000b1eb  call    ?ImportNext@CacheBuffer@@QEAAJPEAEK@Z; CacheBuffer::ImportNext(uchar *,ulong)
0x14000b1f0  mov     ebx, eax
0x14000b1f2  test    eax, eax
0x14000b1f4  jns     short loc_14000B241
0x14000b1f6  mov     rcx, [rsp+1C8h]; this
0x14000b1fe  mov     r9d, eax; char *
0x14000b201  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b208  mov     edx, 143h; void *
0x14000b20d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b212  nop
0x14000b213  mov     rcx, [rsp+1C8h+var_188]; this
0x14000b218  test    rcx, rcx
0x14000b21b  jz      short loc_14000B223
0x14000b21d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b222  nop
0x14000b223  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000b228  test    rcx, rcx
0x14000b22b  jz      short loc_14000B233
0x14000b22d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b232  nop
0x14000b233  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b238  call    ??1AsyncRawBufferImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext(void)
0x14000b23d  mov     eax, ebx
0x14000b23f  jmp     short loc_14000B280
0x14000b241  xor     edx, edx
0x14000b243  lea     rcx, [rsp+1C8h+var_178]
0x14000b248  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000b24d  nop
0x14000b24e  mov     rcx, [rsp+1C8h+var_188]; this
0x14000b253  test    rcx, rcx
0x14000b256  jz      short loc_14000B25E
0x14000b258  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b25d  nop
0x14000b25e  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000b263  test    rcx, rcx
0x14000b266  jz      short loc_14000B26E
0x14000b268  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b26d  nop
0x14000b26e  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b273  call    ??1AsyncRawBufferImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportNext::~AsyncRawBufferImportNext(void)
0x14000b278  xor     eax, eax
0x14000b27a  jmp     short loc_14000B280
0x14000b27c  mov     eax, [rsp+1C8h+var_1A8]
0x14000b280  mov     rcx, [rsp+1C8h+var_28]
0x14000b288  xor     rcx, rsp; StackCookie
0x14000b28b  call    __security_check_cookie
0x14000b290  add     rsp, 1B0h
0x14000b297  pop     rdi
0x14000b298  pop     rsi
0x14000b299  pop     rbx
0x14000b29a  retn
```
