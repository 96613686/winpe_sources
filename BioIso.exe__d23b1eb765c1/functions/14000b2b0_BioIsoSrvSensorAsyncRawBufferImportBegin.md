# BioIsoSrvSensorAsyncRawBufferImportBegin

- ea: `0x14000b2b0`
- end: `0x14000b4da`
- name: `BioIsoSrvSensorAsyncRawBufferImportBegin`
- size: `554`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x14000b2b0`
- `0x14000b678`
- `0x14000d734`
- `0x140013078`
- `0x14001bd40`
- `0x140058380`
- `0x140059830`

## string_xrefs

- `0x14000b2f5`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000b334`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000b37d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000b3da`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000b43f`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall BioIsoSrvSensorAsyncRawBufferImportBegin(int *a1, unsigned int a2, unsigned int *a3)
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

  BioIsoProvider::AsyncRawBufferImportBegin::Start<>((BioIsoProvider::AsyncRawBufferImportBegin *)v14);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v10);
    BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin((BioIsoProvider::AsyncRawBufferImportBegin *)v14);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin((BioIsoProvider::AsyncRawBufferImportBegin *)v14);
    return 2147942487LL;
  }
  *(_OWORD *)v11 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v11);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
LABEL_8:
    BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin((BioIsoProvider::AsyncRawBufferImportBegin *)v14);
    return v8;
  }
  BiometricUnit::PipelineObject(v11[0], &v12);
  if ( v12 )
  {
    v9 = CacheBuffer::ImportBegin((CacheBuffer *)(v12 + 1128), a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
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
    BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin((BioIsoProvider::AsyncRawBufferImportBegin *)v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin((BioIsoProvider::AsyncRawBufferImportBegin *)v14);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14000b2b0  push    rbx
0x14000b2b2  push    rsi
0x14000b2b3  push    rdi
0x14000b2b4  sub     rsp, 1B0h
0x14000b2bb  mov     rax, cs:__security_cookie
0x14000b2c2  xor     rax, rsp
0x14000b2c5  mov     [rsp+1C8h+var_28], rax
0x14000b2cd  mov     rsi, r8
0x14000b2d0  mov     edi, edx
0x14000b2d2  mov     rbx, rcx
0x14000b2d5  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b2da  call    ??$Start@$$V@AsyncRawBufferImportBegin@BioIsoProvider@@SA?AV01@XZ; BioIsoProvider::AsyncRawBufferImportBegin::Start<>(void)
0x14000b2df  nop
0x14000b2e0  test    rbx, rbx
0x14000b2e3  jnz     short loc_14000B318
0x14000b2e5  mov     rcx, [rsp+1C8h]; this
0x14000b2ed  mov     ebx, 80004003h
0x14000b2f2  mov     r9d, ebx; char *
0x14000b2f5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b2fc  mov     edx, 116h; void *
0x14000b301  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b306  nop
0x14000b307  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b30c  call    ??1AsyncRawBufferImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin(void)
0x14000b311  mov     eax, ebx
0x14000b313  jmp     loc_14000B4BE
0x14000b318  mov     rcx, rbx; void *
0x14000b31b  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14000b320  test    al, al
0x14000b322  jnz     short loc_14000B357
0x14000b324  mov     rcx, [rsp+1C8h]; this
0x14000b32c  mov     ebx, 80070057h
0x14000b331  mov     r9d, ebx; char *
0x14000b334  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b33b  mov     edx, 117h; void *
0x14000b340  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b345  nop
0x14000b346  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b34b  call    ??1AsyncRawBufferImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin(void)
0x14000b350  mov     eax, ebx
0x14000b352  jmp     loc_14000B4BE
0x14000b357  xorps   xmm0, xmm0
0x14000b35a  movdqu  xmmword ptr [rsp+1C8h+var_1A0], xmm0
0x14000b360  lea     rdx, [rsp+1C8h+var_1A0]
0x14000b365  mov     ecx, [rbx]
0x14000b367  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14000b36c  mov     ebx, eax
0x14000b36e  test    eax, eax
0x14000b370  jns     short loc_14000B3B0
0x14000b372  mov     rcx, [rsp+1C8h]; this
0x14000b37a  mov     r9d, eax; char *
0x14000b37d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b384  mov     edx, 11Ch; void *
0x14000b389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b38e  nop
0x14000b38f  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000b394  test    rcx, rcx
0x14000b397  jz      short loc_14000B39F
0x14000b399  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b39e  nop
0x14000b39f  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b3a4  call    ??1AsyncRawBufferImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin(void)
0x14000b3a9  mov     eax, ebx
0x14000b3ab  jmp     loc_14000B4BE
0x14000b3b0  lea     rdx, [rsp+1C8h+var_190]
0x14000b3b5  mov     rcx, [rsp+1C8h+var_1A0]
0x14000b3ba  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x14000b3bf  nop
0x14000b3c0  mov     rcx, [rsp+1C8h+var_190]
0x14000b3c5  test    rcx, rcx
0x14000b3c8  jnz     short loc_14000B41D
0x14000b3ca  mov     rcx, [rsp+1C8h]; this
0x14000b3d2  mov     ebx, 80070057h
0x14000b3d7  mov     r9d, ebx; char *
0x14000b3da  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b3e1  mov     edx, 121h; void *
0x14000b3e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b3eb  nop
0x14000b3ec  mov     rcx, [rsp+1C8h+var_188]; this
0x14000b3f1  test    rcx, rcx
0x14000b3f4  jz      short loc_14000B3FC
0x14000b3f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b3fb  nop
0x14000b3fc  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000b401  test    rcx, rcx
0x14000b404  jz      short loc_14000B40C
0x14000b406  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b40b  nop
0x14000b40c  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b411  call    ??1AsyncRawBufferImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin(void)
0x14000b416  mov     eax, ebx
0x14000b418  jmp     loc_14000B4BE
0x14000b41d  add     rcx, 468h; this
0x14000b424  mov     r8, rsi; unsigned int *
0x14000b427  mov     edx, edi; unsigned int
0x14000b429  call    ?ImportBegin@CacheBuffer@@QEAAJKPEAK@Z; CacheBuffer::ImportBegin(ulong,ulong *)
0x14000b42e  mov     ebx, eax
0x14000b430  test    eax, eax
0x14000b432  jns     short loc_14000B47F
0x14000b434  mov     rcx, [rsp+1C8h]; this
0x14000b43c  mov     r9d, eax; char *
0x14000b43f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000b446  mov     edx, 124h; void *
0x14000b44b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b450  nop
0x14000b451  mov     rcx, [rsp+1C8h+var_188]; this
0x14000b456  test    rcx, rcx
0x14000b459  jz      short loc_14000B461
0x14000b45b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b460  nop
0x14000b461  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000b466  test    rcx, rcx
0x14000b469  jz      short loc_14000B471
0x14000b46b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b470  nop
0x14000b471  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b476  call    ??1AsyncRawBufferImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin(void)
0x14000b47b  mov     eax, ebx
0x14000b47d  jmp     short loc_14000B4BE
0x14000b47f  xor     edx, edx
0x14000b481  lea     rcx, [rsp+1C8h+var_178]
0x14000b486  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000b48b  nop
0x14000b48c  mov     rcx, [rsp+1C8h+var_188]; this
0x14000b491  test    rcx, rcx
0x14000b494  jz      short loc_14000B49C
0x14000b496  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b49b  nop
0x14000b49c  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000b4a1  test    rcx, rcx
0x14000b4a4  jz      short loc_14000B4AC
0x14000b4a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000b4ab  nop
0x14000b4ac  lea     rcx, [rsp+1C8h+var_178]; this
0x14000b4b1  call    ??1AsyncRawBufferImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportBegin::~AsyncRawBufferImportBegin(void)
0x14000b4b6  xor     eax, eax
0x14000b4b8  jmp     short loc_14000B4BE
0x14000b4ba  mov     eax, [rsp+1C8h+var_1A8]
0x14000b4be  mov     rcx, [rsp+1C8h+var_28]
0x14000b4c6  xor     rcx, rsp; StackCookie
0x14000b4c9  call    __security_check_cookie
0x14000b4ce  add     rsp, 1B0h
0x14000b4d5  pop     rdi
0x14000b4d6  pop     rsi
0x14000b4d7  pop     rbx
0x14000b4d8  retn
```
