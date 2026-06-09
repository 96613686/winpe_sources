# BioIsoSrvEngineSampleImportBegin

- ea: `0x14000bd70`
- end: `0x14000bfb7`
- name: `BioIsoSrvEngineSampleImportBegin`
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
- `0x14000bd70`
- `0x14000bfc0`
- `0x140012974`
- `0x140013078`
- `0x14001bd40`
- `0x140044a18`
- `0x140058380`
- `0x140059830`

## string_xrefs

- `0x14000bdd2`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000be11`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000be5a`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000beb7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000bf1c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineSampleImportBegin(int *a1, unsigned int a2, unsigned int *a3)
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
    (__int64)"EngineSampleImportBegin");
  v14[0] = &BioIsoProvider::EngineSampleImportBegin::`vftable';
  BioIsoProvider::EngineSampleImportBegin::StartActivity((BioIsoProvider::EngineSampleImportBegin *)v14);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v10);
    BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin((BioIsoProvider::EngineSampleImportBegin *)v14);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F1,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin((BioIsoProvider::EngineSampleImportBegin *)v14);
    return 2147942487LL;
  }
  *(_OWORD *)v11 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v11);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
LABEL_8:
    BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin((BioIsoProvider::EngineSampleImportBegin *)v14);
    return v8;
  }
  BiometricUnit::PipelineObject(v11[0], &v12);
  if ( v12 )
  {
    v9 = CacheBuffer::ImportBegin((CacheBuffer *)(v12 + 1240), a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FE,
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
    BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin((BioIsoProvider::EngineSampleImportBegin *)v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin((BioIsoProvider::EngineSampleImportBegin *)v14);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14000bd70  push    rbx
0x14000bd72  push    rsi
0x14000bd73  push    rdi
0x14000bd74  sub     rsp, 1B0h
0x14000bd7b  mov     rax, cs:__security_cookie
0x14000bd82  xor     rax, rsp
0x14000bd85  mov     [rsp+1C8h+var_28], rax
0x14000bd8d  mov     rsi, r8
0x14000bd90  mov     edi, edx
0x14000bd92  mov     rbx, rcx
0x14000bd95  lea     rdx, aEnginesampleim_1; "EngineSampleImportBegin"
0x14000bd9c  lea     rcx, [rsp+1C8h+var_178]
0x14000bda1  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000bda6  lea     rax, ??_7EngineSampleImportBegin@BioIsoProvider@@6B@; const BioIsoProvider::EngineSampleImportBegin::`vftable'
0x14000bdad  mov     [rsp+1C8h+var_178], rax
0x14000bdb2  lea     rcx, [rsp+1C8h+var_178]; this
0x14000bdb7  call    ?StartActivity@EngineSampleImportBegin@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineSampleImportBegin::StartActivity(void)
0x14000bdbc  nop
0x14000bdbd  test    rbx, rbx
0x14000bdc0  jnz     short loc_14000BDF5
0x14000bdc2  mov     rcx, [rsp+1C8h]; this
0x14000bdca  mov     ebx, 80004003h
0x14000bdcf  mov     r9d, ebx; char *
0x14000bdd2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000bdd9  mov     edx, 2F0h; void *
0x14000bdde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bde3  nop
0x14000bde4  lea     rcx, [rsp+1C8h+var_178]; this
0x14000bde9  call    ??1EngineSampleImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin(void)
0x14000bdee  mov     eax, ebx
0x14000bdf0  jmp     loc_14000BF9B
0x14000bdf5  mov     rcx, rbx; void *
0x14000bdf8  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14000bdfd  test    al, al
0x14000bdff  jnz     short loc_14000BE34
0x14000be01  mov     rcx, [rsp+1C8h]; this
0x14000be09  mov     ebx, 80070057h
0x14000be0e  mov     r9d, ebx; char *
0x14000be11  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000be18  mov     edx, 2F1h; void *
0x14000be1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000be22  nop
0x14000be23  lea     rcx, [rsp+1C8h+var_178]; this
0x14000be28  call    ??1EngineSampleImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin(void)
0x14000be2d  mov     eax, ebx
0x14000be2f  jmp     loc_14000BF9B
0x14000be34  xorps   xmm0, xmm0
0x14000be37  movdqu  xmmword ptr [rsp+1C8h+var_1A0], xmm0
0x14000be3d  lea     rdx, [rsp+1C8h+var_1A0]
0x14000be42  mov     ecx, [rbx]
0x14000be44  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14000be49  mov     ebx, eax
0x14000be4b  test    eax, eax
0x14000be4d  jns     short loc_14000BE8D
0x14000be4f  mov     rcx, [rsp+1C8h]; this
0x14000be57  mov     r9d, eax; char *
0x14000be5a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000be61  mov     edx, 2F6h; void *
0x14000be66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000be6b  nop
0x14000be6c  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000be71  test    rcx, rcx
0x14000be74  jz      short loc_14000BE7C
0x14000be76  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000be7b  nop
0x14000be7c  lea     rcx, [rsp+1C8h+var_178]; this
0x14000be81  call    ??1EngineSampleImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin(void)
0x14000be86  mov     eax, ebx
0x14000be88  jmp     loc_14000BF9B
0x14000be8d  lea     rdx, [rsp+1C8h+var_190]
0x14000be92  mov     rcx, [rsp+1C8h+var_1A0]
0x14000be97  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x14000be9c  nop
0x14000be9d  mov     rcx, [rsp+1C8h+var_190]
0x14000bea2  test    rcx, rcx
0x14000bea5  jnz     short loc_14000BEFA
0x14000bea7  mov     rcx, [rsp+1C8h]; this
0x14000beaf  mov     ebx, 80070057h
0x14000beb4  mov     r9d, ebx; char *
0x14000beb7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000bebe  mov     edx, 2FBh; void *
0x14000bec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bec8  nop
0x14000bec9  mov     rcx, [rsp+1C8h+var_188]; this
0x14000bece  test    rcx, rcx
0x14000bed1  jz      short loc_14000BED9
0x14000bed3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000bed8  nop
0x14000bed9  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000bede  test    rcx, rcx
0x14000bee1  jz      short loc_14000BEE9
0x14000bee3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000bee8  nop
0x14000bee9  lea     rcx, [rsp+1C8h+var_178]; this
0x14000beee  call    ??1EngineSampleImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin(void)
0x14000bef3  mov     eax, ebx
0x14000bef5  jmp     loc_14000BF9B
0x14000befa  add     rcx, 4D8h; this
0x14000bf01  mov     r8, rsi; unsigned int *
0x14000bf04  mov     edx, edi; unsigned int
0x14000bf06  call    ?ImportBegin@CacheBuffer@@QEAAJKPEAK@Z; CacheBuffer::ImportBegin(ulong,ulong *)
0x14000bf0b  mov     ebx, eax
0x14000bf0d  test    eax, eax
0x14000bf0f  jns     short loc_14000BF5C
0x14000bf11  mov     rcx, [rsp+1C8h]; this
0x14000bf19  mov     r9d, eax; char *
0x14000bf1c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000bf23  mov     edx, 2FEh; void *
0x14000bf28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bf2d  nop
0x14000bf2e  mov     rcx, [rsp+1C8h+var_188]; this
0x14000bf33  test    rcx, rcx
0x14000bf36  jz      short loc_14000BF3E
0x14000bf38  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000bf3d  nop
0x14000bf3e  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000bf43  test    rcx, rcx
0x14000bf46  jz      short loc_14000BF4E
0x14000bf48  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000bf4d  nop
0x14000bf4e  lea     rcx, [rsp+1C8h+var_178]; this
0x14000bf53  call    ??1EngineSampleImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin(void)
0x14000bf58  mov     eax, ebx
0x14000bf5a  jmp     short loc_14000BF9B
0x14000bf5c  xor     edx, edx
0x14000bf5e  lea     rcx, [rsp+1C8h+var_178]
0x14000bf63  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000bf68  nop
0x14000bf69  mov     rcx, [rsp+1C8h+var_188]; this
0x14000bf6e  test    rcx, rcx
0x14000bf71  jz      short loc_14000BF79
0x14000bf73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000bf78  nop
0x14000bf79  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x14000bf7e  test    rcx, rcx
0x14000bf81  jz      short loc_14000BF89
0x14000bf83  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000bf88  nop
0x14000bf89  lea     rcx, [rsp+1C8h+var_178]; this
0x14000bf8e  call    ??1EngineSampleImportBegin@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportBegin::~EngineSampleImportBegin(void)
0x14000bf93  xor     eax, eax
0x14000bf95  jmp     short loc_14000BF9B
0x14000bf97  mov     eax, [rsp+1C8h+var_1A8]
0x14000bf9b  mov     rcx, [rsp+1C8h+var_28]
0x14000bfa3  xor     rcx, rsp; StackCookie
0x14000bfa6  call    __security_check_cookie
0x14000bfab  add     rsp, 1B0h
0x14000bfb2  pop     rdi
0x14000bfb3  pop     rsi
0x14000bfb4  pop     rbx
0x14000bfb5  retn
```
