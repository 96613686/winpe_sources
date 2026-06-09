# BioIsoSrvStorageCacheExportEnd

- ea: `0x140016c80`
- end: `0x140016eb5`
- name: `BioIsoSrvStorageCacheExportEnd`
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
- `0x140016c80`
- `0x140016ebc`
- `0x14001bd40`
- `0x140046088`
- `0x140058364`
- `0x140059830`

## string_xrefs

- `0x140016cdb`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016d1a`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016d63`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016dbf`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016e1e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140016c9e`: `StorageCacheExportEnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageCacheExportEnd(int *a1)
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
    (__int64)"StorageCacheExportEnd");
  v10[0] = &BioIsoProvider::StorageCacheExportEnd::`vftable';
  BioIsoProvider::StorageCacheExportEnd::StartActivity((BioIsoProvider::StorageCacheExportEnd *)v10);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v6);
    BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd((BioIsoProvider::StorageCacheExportEnd *)v10);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v6);
    BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd((BioIsoProvider::StorageCacheExportEnd *)v10);
    return 2147942487LL;
  }
  *(_OWORD *)v7 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v7);
  v4 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x844,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v6);
    if ( v7[1] )
      std::_Ref_count_base::_Decref(v7[1]);
LABEL_8:
    BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd((BioIsoProvider::StorageCacheExportEnd *)v10);
    return v4;
  }
  BiometricUnit::PipelineObject(v7[0], &v8);
  if ( v8 )
  {
    v5 = CacheBuffer::ExportEnd((CacheBuffer *)(v8 + 1296));
    v4 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84C,
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
    BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd((BioIsoProvider::StorageCacheExportEnd *)v10);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x849,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v6);
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    if ( v7[1] )
      std::_Ref_count_base::_Decref(v7[1]);
    BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd((BioIsoProvider::StorageCacheExportEnd *)v10);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140016c80  push    rbx
0x140016c82  sub     rsp, 1B0h
0x140016c89  mov     rax, cs:__security_cookie
0x140016c90  xor     rax, rsp
0x140016c93  mov     [rsp+1B8h+var_18], rax
0x140016c9b  mov     rbx, rcx
0x140016c9e  lea     rdx, aStoragecacheex_1; "StorageCacheExportEnd"
0x140016ca5  lea     rcx, [rsp+1B8h+var_168]
0x140016caa  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140016caf  lea     rax, ??_7StorageCacheExportEnd@BioIsoProvider@@6B@; const BioIsoProvider::StorageCacheExportEnd::`vftable'
0x140016cb6  mov     [rsp+1B8h+var_168], rax
0x140016cbb  lea     rcx, [rsp+1B8h+var_168]; this
0x140016cc0  call    ?StartActivity@StorageCacheExportEnd@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageCacheExportEnd::StartActivity(void)
0x140016cc5  nop
0x140016cc6  test    rbx, rbx
0x140016cc9  jnz     short loc_140016CFE
0x140016ccb  mov     rcx, [rsp+1B8h]; this
0x140016cd3  mov     ebx, 80004003h
0x140016cd8  mov     r9d, ebx; char *
0x140016cdb  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016ce2  mov     edx, 83Eh; void *
0x140016ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016cec  nop
0x140016ced  lea     rcx, [rsp+1B8h+var_168]; this
0x140016cf2  call    ??1StorageCacheExportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd(void)
0x140016cf7  mov     eax, ebx
0x140016cf9  jmp     loc_140016E9B
0x140016cfe  mov     rcx, rbx; void *
0x140016d01  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140016d06  test    al, al
0x140016d08  jnz     short loc_140016D3D
0x140016d0a  mov     rcx, [rsp+1B8h]; this
0x140016d12  mov     ebx, 80070057h
0x140016d17  mov     r9d, ebx; char *
0x140016d1a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016d21  mov     edx, 83Fh; void *
0x140016d26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016d2b  nop
0x140016d2c  lea     rcx, [rsp+1B8h+var_168]; this
0x140016d31  call    ??1StorageCacheExportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd(void)
0x140016d36  mov     eax, ebx
0x140016d38  jmp     loc_140016E9B
0x140016d3d  xorps   xmm0, xmm0
0x140016d40  movdqu  xmmword ptr [rsp+1B8h+var_190], xmm0
0x140016d46  lea     rdx, [rsp+1B8h+var_190]
0x140016d4b  mov     ecx, [rbx]
0x140016d4d  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140016d52  mov     ebx, eax
0x140016d54  test    eax, eax
0x140016d56  jns     short loc_140016D96
0x140016d58  mov     rcx, [rsp+1B8h]; this
0x140016d60  mov     r9d, eax; char *
0x140016d63  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016d6a  mov     edx, 844h; void *
0x140016d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016d74  nop
0x140016d75  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140016d7a  test    rcx, rcx
0x140016d7d  jz      short loc_140016D85
0x140016d7f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016d84  nop
0x140016d85  lea     rcx, [rsp+1B8h+var_168]; this
0x140016d8a  call    ??1StorageCacheExportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd(void)
0x140016d8f  mov     eax, ebx
0x140016d91  jmp     loc_140016E9B
0x140016d96  lea     rdx, [rsp+1B8h+var_180]
0x140016d9b  mov     rcx, [rsp+1B8h+var_190]
0x140016da0  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x140016da5  mov     rcx, [rsp+1B8h+var_180]
0x140016daa  test    rcx, rcx
0x140016dad  jnz     short loc_140016E01
0x140016daf  mov     rcx, [rsp+1B8h]; this
0x140016db7  mov     ebx, 80070057h
0x140016dbc  mov     r9d, ebx; char *
0x140016dbf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016dc6  mov     edx, 849h; void *
0x140016dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016dd0  mov     rcx, [rsp+1B8h+var_178]; this
0x140016dd5  test    rcx, rcx
0x140016dd8  jz      short loc_140016DE0
0x140016dda  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016ddf  nop
0x140016de0  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140016de5  test    rcx, rcx
0x140016de8  jz      short loc_140016DF0
0x140016dea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016def  nop
0x140016df0  lea     rcx, [rsp+1B8h+var_168]; this
0x140016df5  call    ??1StorageCacheExportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd(void)
0x140016dfa  mov     eax, ebx
0x140016dfc  jmp     loc_140016E9B
0x140016e01  add     rcx, 510h; this
0x140016e08  call    ?ExportEnd@CacheBuffer@@QEAAJXZ; CacheBuffer::ExportEnd(void)
0x140016e0d  mov     ebx, eax
0x140016e0f  test    eax, eax
0x140016e11  jns     short loc_140016E5D
0x140016e13  mov     rcx, [rsp+1B8h]; this
0x140016e1b  mov     r9d, eax; char *
0x140016e1e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140016e25  mov     edx, 84Ch; void *
0x140016e2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016e2f  mov     rcx, [rsp+1B8h+var_178]; this
0x140016e34  test    rcx, rcx
0x140016e37  jz      short loc_140016E3F
0x140016e39  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016e3e  nop
0x140016e3f  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140016e44  test    rcx, rcx
0x140016e47  jz      short loc_140016E4F
0x140016e49  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016e4e  nop
0x140016e4f  lea     rcx, [rsp+1B8h+var_168]; this
0x140016e54  call    ??1StorageCacheExportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd(void)
0x140016e59  mov     eax, ebx
0x140016e5b  jmp     short loc_140016E9B
0x140016e5d  xor     edx, edx
0x140016e5f  lea     rcx, [rsp+1B8h+var_168]
0x140016e64  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140016e69  mov     rcx, [rsp+1B8h+var_178]; this
0x140016e6e  test    rcx, rcx
0x140016e71  jz      short loc_140016E79
0x140016e73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016e78  nop
0x140016e79  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140016e7e  test    rcx, rcx
0x140016e81  jz      short loc_140016E89
0x140016e83  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140016e88  nop
0x140016e89  lea     rcx, [rsp+1B8h+var_168]; this
0x140016e8e  call    ??1StorageCacheExportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheExportEnd::~StorageCacheExportEnd(void)
0x140016e93  xor     eax, eax
0x140016e95  jmp     short loc_140016E9B
0x140016e97  mov     eax, [rsp+1B8h+var_198]
0x140016e9b  mov     rcx, [rsp+1B8h+var_18]
0x140016ea3  xor     rcx, rsp; StackCookie
0x140016ea6  call    __security_check_cookie
0x140016eab  add     rsp, 1B0h
0x140016eb2  pop     rbx
0x140016eb3  retn
```
