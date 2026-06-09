# BioIsoSrvStorageCacheClear

- ea: `0x140007030`
- end: `0x14000724b`
- name: `BioIsoSrvStorageCacheClear`
- size: `539`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007030`
- `0x140007254`
- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140013078`
- `0x14001bd40`
- `0x140045f38`
- `0x140059830`

## string_xrefs

- `0x14000708b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400070ca`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140007113`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000716f`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000704e`: `StorageCacheClear`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageCacheClear(int *a1)
{
  int BiometricUnit; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // [rsp+20h] [rbp-198h]
  std::_Ref_count_base *v8[2]; // [rsp+28h] [rbp-190h] BYREF
  __int64 v9; // [rsp+38h] [rbp-180h] BYREF
  std::_Ref_count_base *v10; // [rsp+40h] [rbp-178h]
  _QWORD v11[42]; // [rsp+50h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v11,
    (__int64)"StorageCacheClear");
  v11[0] = &BioIsoProvider::StorageCacheClear::`vftable';
  BioIsoProvider::StorageCacheClear::StartActivity((BioIsoProvider::StorageCacheClear *)v11);
  if ( a1 )
  {
    if ( HardwareManager::ContainsHandle((unsigned __int64)a1) )
    {
      *(_OWORD *)v8 = 0;
      BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v8);
      v4 = BiometricUnit;
      if ( BiometricUnit >= 0 )
      {
        BiometricUnit::PipelineObject(v8[0], &v9);
        v5 = v9;
        if ( v9 )
        {
          v6 = *(_QWORD *)(v9 + 1296);
          if ( v6 != *(_QWORD *)(v9 + 1304) )
            *(_QWORD *)(v9 + 1304) = v6;
          *(_DWORD *)(v5 + 1320) = 0;
          *(_QWORD *)(v5 + 1328) = 0;
          *(_QWORD *)(v5 + 1336) = 0;
          *(_QWORD *)(v5 + 1344) = 0;
          wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, 0);
          if ( v10 )
            std::_Ref_count_base::_Decref(v10);
          if ( v8[1] )
            std::_Ref_count_base::_Decref(v8[1]);
          BioIsoProvider::StorageCacheClear::~StorageCacheClear((BioIsoProvider::StorageCacheClear *)v11);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x793,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
            (const char *)0x80070057LL,
            v7);
          if ( v10 )
            std::_Ref_count_base::_Decref(v10);
          if ( v8[1] )
            std::_Ref_count_base::_Decref(v8[1]);
          BioIsoProvider::StorageCacheClear::~StorageCacheClear((BioIsoProvider::StorageCacheClear *)v11);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x78E,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)BiometricUnit,
          v7);
        if ( v8[1] )
          std::_Ref_count_base::_Decref(v8[1]);
        BioIsoProvider::StorageCacheClear::~StorageCacheClear((BioIsoProvider::StorageCacheClear *)v11);
        return v4;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x789,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x80070057LL,
        v7);
      BioIsoProvider::StorageCacheClear::~StorageCacheClear((BioIsoProvider::StorageCacheClear *)v11);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v7);
    BioIsoProvider::StorageCacheClear::~StorageCacheClear((BioIsoProvider::StorageCacheClear *)v11);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140007030  push    rbx
0x140007032  sub     rsp, 1B0h
0x140007039  mov     rax, cs:__security_cookie
0x140007040  xor     rax, rsp
0x140007043  mov     [rsp+1B8h+var_18], rax
0x14000704b  mov     rbx, rcx
0x14000704e  lea     rdx, aStoragecachecl; "StorageCacheClear"
0x140007055  lea     rcx, [rsp+1B8h+var_168]
0x14000705a  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000705f  lea     rax, ??_7StorageCacheClear@BioIsoProvider@@6B@; const BioIsoProvider::StorageCacheClear::`vftable'
0x140007066  mov     [rsp+1B8h+var_168], rax
0x14000706b  lea     rcx, [rsp+1B8h+var_168]; this
0x140007070  call    ?StartActivity@StorageCacheClear@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageCacheClear::StartActivity(void)
0x140007075  nop
0x140007076  test    rbx, rbx
0x140007079  jnz     short loc_1400070AE
0x14000707b  mov     rcx, [rsp+1B8h]; this
0x140007083  mov     ebx, 80004003h
0x140007088  mov     r9d, ebx; char *
0x14000708b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140007092  mov     edx, 788h; void *
0x140007097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000709c  nop
0x14000709d  lea     rcx, [rsp+1B8h+var_168]; this
0x1400070a2  call    ??1StorageCacheClear@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheClear::~StorageCacheClear(void)
0x1400070a7  mov     eax, ebx
0x1400070a9  jmp     loc_140007231
0x1400070ae  mov     rcx, rbx; void *
0x1400070b1  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400070b6  test    al, al
0x1400070b8  jnz     short loc_1400070ED
0x1400070ba  mov     rcx, [rsp+1B8h]; this
0x1400070c2  mov     ebx, 80070057h
0x1400070c7  mov     r9d, ebx; char *
0x1400070ca  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400070d1  mov     edx, 789h; void *
0x1400070d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400070db  nop
0x1400070dc  lea     rcx, [rsp+1B8h+var_168]; this
0x1400070e1  call    ??1StorageCacheClear@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheClear::~StorageCacheClear(void)
0x1400070e6  mov     eax, ebx
0x1400070e8  jmp     loc_140007231
0x1400070ed  xorps   xmm0, xmm0
0x1400070f0  movdqu  xmmword ptr [rsp+1B8h+var_190], xmm0
0x1400070f6  lea     rdx, [rsp+1B8h+var_190]
0x1400070fb  mov     ecx, [rbx]
0x1400070fd  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140007102  mov     ebx, eax
0x140007104  test    eax, eax
0x140007106  jns     short loc_140007146
0x140007108  mov     rcx, [rsp+1B8h]; this
0x140007110  mov     r9d, eax; char *
0x140007113  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000711a  mov     edx, 78Eh; void *
0x14000711f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007124  nop
0x140007125  mov     rcx, [rsp+1B8h+var_190+8]; this
0x14000712a  test    rcx, rcx
0x14000712d  jz      short loc_140007135
0x14000712f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140007134  nop
0x140007135  lea     rcx, [rsp+1B8h+var_168]; this
0x14000713a  call    ??1StorageCacheClear@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheClear::~StorageCacheClear(void)
0x14000713f  mov     eax, ebx
0x140007141  jmp     loc_140007231
0x140007146  lea     rdx, [rsp+1B8h+var_180]
0x14000714b  mov     rcx, [rsp+1B8h+var_190]
0x140007150  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x140007155  mov     rcx, [rsp+1B8h+var_180]
0x14000715a  test    rcx, rcx
0x14000715d  jnz     short loc_1400071B1
0x14000715f  mov     rcx, [rsp+1B8h]; this
0x140007167  mov     ebx, 80070057h
0x14000716c  mov     r9d, ebx; char *
0x14000716f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140007176  mov     edx, 793h; void *
0x14000717b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007180  mov     rcx, [rsp+1B8h+var_178]; this
0x140007185  test    rcx, rcx
0x140007188  jz      short loc_140007190
0x14000718a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000718f  nop
0x140007190  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140007195  test    rcx, rcx
0x140007198  jz      short loc_1400071A0
0x14000719a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000719f  nop
0x1400071a0  lea     rcx, [rsp+1B8h+var_168]; this
0x1400071a5  call    ??1StorageCacheClear@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheClear::~StorageCacheClear(void)
0x1400071aa  mov     eax, ebx
0x1400071ac  jmp     loc_140007231
0x1400071b1  mov     rax, [rcx+510h]
0x1400071b8  cmp     rax, [rcx+518h]
0x1400071bf  jz      short loc_1400071C8
0x1400071c1  mov     [rcx+518h], rax
0x1400071c8  mov     dword ptr [rcx+528h], 0
0x1400071d2  mov     qword ptr [rcx+530h], 0
0x1400071dd  mov     qword ptr [rcx+538h], 0
0x1400071e8  mov     qword ptr [rcx+540h], 0
0x1400071f3  xor     edx, edx
0x1400071f5  lea     rcx, [rsp+1B8h+var_168]
0x1400071fa  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400071ff  mov     rcx, [rsp+1B8h+var_178]; this
0x140007204  test    rcx, rcx
0x140007207  jz      short loc_14000720F
0x140007209  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000720e  nop
0x14000720f  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140007214  test    rcx, rcx
0x140007217  jz      short loc_14000721F
0x140007219  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000721e  nop
0x14000721f  lea     rcx, [rsp+1B8h+var_168]; this
0x140007224  call    ??1StorageCacheClear@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCacheClear::~StorageCacheClear(void)
0x140007229  xor     eax, eax
0x14000722b  jmp     short loc_140007231
0x14000722d  mov     eax, [rsp+1B8h+var_198]
0x140007231  mov     rcx, [rsp+1B8h+var_18]
0x140007239  xor     rcx, rsp; StackCookie
0x14000723c  call    __security_check_cookie
0x140007241  add     rsp, 1B0h
0x140007248  pop     rbx
0x140007249  retn
```
