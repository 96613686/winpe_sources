# BioIsoSrvEngineSampleImportNext

- ea: `0x1400089e0`
- end: `0x140008c29`
- name: `BioIsoSrvEngineSampleImportNext`
- size: `585`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x1400089e0`
- `0x140008c30`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140013078`
- `0x14001bd40`
- `0x140044b68`
- `0x140058440`
- `0x140059830`

## string_xrefs

- `0x140008a43`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008a82`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008acb`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008b28`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008b8e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineSampleImportNext(int *a1, unsigned __int8 *a2, unsigned int a3)
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
    (__int64)"EngineSampleImportNext");
  v14[0] = &BioIsoProvider::EngineSampleImportNext::`vftable';
  BioIsoProvider::EngineSampleImportNext::StartActivity((BioIsoProvider::EngineSampleImportNext *)v14);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v10);
    BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext((BioIsoProvider::EngineSampleImportNext *)v14);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x310,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext((BioIsoProvider::EngineSampleImportNext *)v14);
    return 2147942487LL;
  }
  *(_OWORD *)v11 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v11);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x315,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
LABEL_8:
    BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext((BioIsoProvider::EngineSampleImportNext *)v14);
    return v8;
  }
  BiometricUnit::PipelineObject(v11[0], &v12);
  if ( v12 )
  {
    v9 = CacheBuffer::ImportNext((CacheBuffer *)(v12 + 1240), a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31D,
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
    BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext((BioIsoProvider::EngineSampleImportNext *)v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext((BioIsoProvider::EngineSampleImportNext *)v14);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1400089e0  push    rbx
0x1400089e2  push    rsi
0x1400089e3  push    rdi
0x1400089e4  sub     rsp, 1B0h
0x1400089eb  mov     rax, cs:__security_cookie
0x1400089f2  xor     rax, rsp
0x1400089f5  mov     [rsp+1C8h+var_28], rax
0x1400089fd  mov     esi, r8d
0x140008a00  mov     rdi, rdx
0x140008a03  mov     rbx, rcx
0x140008a06  lea     rdx, aEnginesampleim_0; "EngineSampleImportNext"
0x140008a0d  lea     rcx, [rsp+1C8h+var_178]
0x140008a12  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140008a17  lea     rax, ??_7EngineSampleImportNext@BioIsoProvider@@6B@; const BioIsoProvider::EngineSampleImportNext::`vftable'
0x140008a1e  mov     [rsp+1C8h+var_178], rax
0x140008a23  lea     rcx, [rsp+1C8h+var_178]; this
0x140008a28  call    ?StartActivity@EngineSampleImportNext@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineSampleImportNext::StartActivity(void)
0x140008a2d  nop
0x140008a2e  test    rbx, rbx
0x140008a31  jnz     short loc_140008A66
0x140008a33  mov     rcx, [rsp+1C8h]; this
0x140008a3b  mov     ebx, 80004003h
0x140008a40  mov     r9d, ebx; char *
0x140008a43  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008a4a  mov     edx, 30Fh; void *
0x140008a4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008a54  nop
0x140008a55  lea     rcx, [rsp+1C8h+var_178]; this
0x140008a5a  call    ??1EngineSampleImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext(void)
0x140008a5f  mov     eax, ebx
0x140008a61  jmp     loc_140008C0D
0x140008a66  mov     rcx, rbx; void *
0x140008a69  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140008a6e  test    al, al
0x140008a70  jnz     short loc_140008AA5
0x140008a72  mov     rcx, [rsp+1C8h]; this
0x140008a7a  mov     ebx, 80070057h
0x140008a7f  mov     r9d, ebx; char *
0x140008a82  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008a89  mov     edx, 310h; void *
0x140008a8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008a93  nop
0x140008a94  lea     rcx, [rsp+1C8h+var_178]; this
0x140008a99  call    ??1EngineSampleImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext(void)
0x140008a9e  mov     eax, ebx
0x140008aa0  jmp     loc_140008C0D
0x140008aa5  xorps   xmm0, xmm0
0x140008aa8  movdqu  xmmword ptr [rsp+1C8h+var_1A0], xmm0
0x140008aae  lea     rdx, [rsp+1C8h+var_1A0]
0x140008ab3  mov     ecx, [rbx]
0x140008ab5  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140008aba  mov     ebx, eax
0x140008abc  test    eax, eax
0x140008abe  jns     short loc_140008AFE
0x140008ac0  mov     rcx, [rsp+1C8h]; this
0x140008ac8  mov     r9d, eax; char *
0x140008acb  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008ad2  mov     edx, 315h; void *
0x140008ad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008adc  nop
0x140008add  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x140008ae2  test    rcx, rcx
0x140008ae5  jz      short loc_140008AED
0x140008ae7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008aec  nop
0x140008aed  lea     rcx, [rsp+1C8h+var_178]; this
0x140008af2  call    ??1EngineSampleImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext(void)
0x140008af7  mov     eax, ebx
0x140008af9  jmp     loc_140008C0D
0x140008afe  lea     rdx, [rsp+1C8h+var_190]
0x140008b03  mov     rcx, [rsp+1C8h+var_1A0]
0x140008b08  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x140008b0d  nop
0x140008b0e  mov     rcx, [rsp+1C8h+var_190]
0x140008b13  test    rcx, rcx
0x140008b16  jnz     short loc_140008B6B
0x140008b18  mov     rcx, [rsp+1C8h]; this
0x140008b20  mov     ebx, 80070057h
0x140008b25  mov     r9d, ebx; char *
0x140008b28  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008b2f  mov     edx, 31Ah; void *
0x140008b34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b39  nop
0x140008b3a  mov     rcx, [rsp+1C8h+var_188]; this
0x140008b3f  test    rcx, rcx
0x140008b42  jz      short loc_140008B4A
0x140008b44  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008b49  nop
0x140008b4a  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x140008b4f  test    rcx, rcx
0x140008b52  jz      short loc_140008B5A
0x140008b54  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008b59  nop
0x140008b5a  lea     rcx, [rsp+1C8h+var_178]; this
0x140008b5f  call    ??1EngineSampleImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext(void)
0x140008b64  mov     eax, ebx
0x140008b66  jmp     loc_140008C0D
0x140008b6b  add     rcx, 4D8h; this
0x140008b72  mov     r8d, esi; unsigned int
0x140008b75  mov     rdx, rdi; unsigned __int8 *
0x140008b78  call    ?ImportNext@CacheBuffer@@QEAAJPEAEK@Z; CacheBuffer::ImportNext(uchar *,ulong)
0x140008b7d  mov     ebx, eax
0x140008b7f  test    eax, eax
0x140008b81  jns     short loc_140008BCE
0x140008b83  mov     rcx, [rsp+1C8h]; this
0x140008b8b  mov     r9d, eax; char *
0x140008b8e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008b95  mov     edx, 31Dh; void *
0x140008b9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b9f  nop
0x140008ba0  mov     rcx, [rsp+1C8h+var_188]; this
0x140008ba5  test    rcx, rcx
0x140008ba8  jz      short loc_140008BB0
0x140008baa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008baf  nop
0x140008bb0  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x140008bb5  test    rcx, rcx
0x140008bb8  jz      short loc_140008BC0
0x140008bba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008bbf  nop
0x140008bc0  lea     rcx, [rsp+1C8h+var_178]; this
0x140008bc5  call    ??1EngineSampleImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext(void)
0x140008bca  mov     eax, ebx
0x140008bcc  jmp     short loc_140008C0D
0x140008bce  xor     edx, edx
0x140008bd0  lea     rcx, [rsp+1C8h+var_178]
0x140008bd5  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140008bda  nop
0x140008bdb  mov     rcx, [rsp+1C8h+var_188]; this
0x140008be0  test    rcx, rcx
0x140008be3  jz      short loc_140008BEB
0x140008be5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008bea  nop
0x140008beb  mov     rcx, [rsp+1C8h+var_1A0+8]; this
0x140008bf0  test    rcx, rcx
0x140008bf3  jz      short loc_140008BFB
0x140008bf5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008bfa  nop
0x140008bfb  lea     rcx, [rsp+1C8h+var_178]; this
0x140008c00  call    ??1EngineSampleImportNext@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSampleImportNext::~EngineSampleImportNext(void)
0x140008c05  xor     eax, eax
0x140008c07  jmp     short loc_140008C0D
0x140008c09  mov     eax, [rsp+1C8h+var_1A8]
0x140008c0d  mov     rcx, [rsp+1C8h+var_28]
0x140008c15  xor     rcx, rsp; StackCookie
0x140008c18  call    __security_check_cookie
0x140008c1d  add     rsp, 1B0h
0x140008c24  pop     rdi
0x140008c25  pop     rsi
0x140008c26  pop     rbx
0x140008c27  retn
```
