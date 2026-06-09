# BioIsoSrvEngineCreateEnrollment

- ea: `0x14001b160`
- end: `0x14001b335`
- name: `BioIsoSrvEngineCreateEnrollment`
- size: `469`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x14001b160`
- `0x14001b33c`
- `0x14001bd40`
- `0x140043e48`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x14001b1bb`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001b1fa`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001b243`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001b2e7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001b17e`: `EngineCreateEnrollment`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineCreateEnrollment(int *a1)
{
  int BiometricUnit; // eax
  int v4; // ebx
  __int64 v5; // rax
  __int64 (*v6)(void); // rax
  int v7; // [rsp+20h] [rbp-188h]
  std::_Ref_count_base *v8[2]; // [rsp+28h] [rbp-180h] BYREF
  _QWORD v9[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v9,
    (__int64)"EngineCreateEnrollment");
  v9[0] = &BioIsoProvider::EngineCreateEnrollment::`vftable';
  BioIsoProvider::EngineCreateEnrollment::StartActivity((BioIsoProvider::EngineCreateEnrollment *)v9);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36D,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v7);
    BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment((BioIsoProvider::EngineCreateEnrollment *)v9);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v7);
    BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment((BioIsoProvider::EngineCreateEnrollment *)v9);
    return 2147942487LL;
  }
  *(_OWORD *)v8 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v8);
  v4 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x373,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v7);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
LABEL_20:
    BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment((BioIsoProvider::EngineCreateEnrollment *)v9);
    return (unsigned int)v4;
  }
  if ( *((_QWORD *)v8[0] + 3) == -32 || (v5 = *(_QWORD *)(*((_QWORD *)v8[0] + 3) + 64LL)) == 0 )
  {
    v4 = -2147467261;
    goto LABEL_18;
  }
  v6 = *(__int64 (**)(void))(v5 + 128);
  if ( !v6 )
  {
    v4 = -2147467263;
    goto LABEL_18;
  }
  v4 = v6();
  if ( v4 < 0 )
  {
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x376,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v4,
      v7);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
    goto LABEL_20;
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v9, 0);
  if ( v8[1] )
    std::_Ref_count_base::_Decref(v8[1]);
  BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment((BioIsoProvider::EngineCreateEnrollment *)v9);
  return 0;
}

```

## disassembly

```asm
0x14001b160  push    rbx
0x14001b162  sub     rsp, 1A0h
0x14001b169  mov     rax, cs:__security_cookie
0x14001b170  xor     rax, rsp
0x14001b173  mov     [rsp+1A8h+var_18], rax
0x14001b17b  mov     rbx, rcx
0x14001b17e  lea     rdx, aEnginecreateen; "EngineCreateEnrollment"
0x14001b185  lea     rcx, [rsp+1A8h+var_168]
0x14001b18a  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001b18f  lea     rax, ??_7EngineCreateEnrollment@BioIsoProvider@@6B@; const BioIsoProvider::EngineCreateEnrollment::`vftable'
0x14001b196  mov     [rsp+1A8h+var_168], rax
0x14001b19b  lea     rcx, [rsp+1A8h+var_168]; this
0x14001b1a0  call    ?StartActivity@EngineCreateEnrollment@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineCreateEnrollment::StartActivity(void)
0x14001b1a5  nop
0x14001b1a6  test    rbx, rbx
0x14001b1a9  jnz     short loc_14001B1DE
0x14001b1ab  mov     rcx, [rsp+1A8h]; this
0x14001b1b3  mov     ebx, 80004003h
0x14001b1b8  mov     r9d, ebx; char *
0x14001b1bb  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001b1c2  mov     edx, 36Dh; void *
0x14001b1c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b1cc  nop
0x14001b1cd  lea     rcx, [rsp+1A8h+var_168]; this
0x14001b1d2  call    ??1EngineCreateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment(void)
0x14001b1d7  mov     eax, ebx
0x14001b1d9  jmp     loc_14001B31B
0x14001b1de  mov     rcx, rbx; void *
0x14001b1e1  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14001b1e6  test    al, al
0x14001b1e8  jnz     short loc_14001B21D
0x14001b1ea  mov     rcx, [rsp+1A8h]; this
0x14001b1f2  mov     ebx, 80070057h
0x14001b1f7  mov     r9d, ebx; char *
0x14001b1fa  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001b201  mov     edx, 36Eh; void *
0x14001b206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b20b  nop
0x14001b20c  lea     rcx, [rsp+1A8h+var_168]; this
0x14001b211  call    ??1EngineCreateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment(void)
0x14001b216  mov     eax, ebx
0x14001b218  jmp     loc_14001B31B
0x14001b21d  xorps   xmm0, xmm0
0x14001b220  movdqu  xmmword ptr [rsp+1A8h+var_180], xmm0
0x14001b226  lea     rdx, [rsp+1A8h+var_180]
0x14001b22b  mov     ecx, [rbx]
0x14001b22d  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14001b232  mov     ebx, eax
0x14001b234  test    eax, eax
0x14001b236  jns     short loc_14001B276
0x14001b238  mov     rcx, [rsp+1A8h]; this
0x14001b240  mov     r9d, eax; char *
0x14001b243  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001b24a  mov     edx, 373h; void *
0x14001b24f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b254  nop
0x14001b255  mov     rcx, [rsp+1A8h+var_180+8]; this
0x14001b25a  test    rcx, rcx
0x14001b25d  jz      short loc_14001B265
0x14001b25f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001b264  nop
0x14001b265  lea     rcx, [rsp+1A8h+var_168]; this
0x14001b26a  call    ??1EngineCreateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment(void)
0x14001b26f  mov     eax, ebx
0x14001b271  jmp     loc_14001B31B
0x14001b276  mov     rax, [rsp+1A8h+var_180]
0x14001b27b  mov     rcx, [rax+18h]
0x14001b27f  add     rcx, 20h ; ' '
0x14001b283  jz      short loc_14001B2D7
0x14001b285  mov     rax, [rcx+20h]
0x14001b289  test    rax, rax
0x14001b28c  jz      short loc_14001B2D7
0x14001b28e  mov     rax, [rax+80h]
0x14001b295  test    rax, rax
0x14001b298  jnz     short loc_14001B2A1
0x14001b29a  mov     ebx, 80004001h
0x14001b29f  jmp     short loc_14001B2DC
0x14001b2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b2a6  mov     ebx, eax
0x14001b2a8  test    eax, eax
0x14001b2aa  js      short loc_14001B2DC
0x14001b2ac  xor     edx, edx
0x14001b2ae  lea     rcx, [rsp+1A8h+var_168]
0x14001b2b3  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001b2b8  nop
0x14001b2b9  mov     rcx, [rsp+1A8h+var_180+8]; this
0x14001b2be  test    rcx, rcx
0x14001b2c1  jz      short loc_14001B2C9
0x14001b2c3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001b2c8  nop
0x14001b2c9  lea     rcx, [rsp+1A8h+var_168]; this
0x14001b2ce  call    ??1EngineCreateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment(void)
0x14001b2d3  xor     eax, eax
0x14001b2d5  jmp     short loc_14001B31B
0x14001b2d7  mov     ebx, 80004003h
0x14001b2dc  mov     rcx, [rsp+1A8h]; this
0x14001b2e4  mov     r9d, ebx; char *
0x14001b2e7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001b2ee  mov     edx, 376h; void *
0x14001b2f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b2f8  nop
0x14001b2f9  mov     rcx, [rsp+1A8h+var_180+8]; this
0x14001b2fe  test    rcx, rcx
0x14001b301  jz      short loc_14001B309
0x14001b303  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001b308  nop
0x14001b309  lea     rcx, [rsp+1A8h+var_168]; this
0x14001b30e  call    ??1EngineCreateEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCreateEnrollment::~EngineCreateEnrollment(void)
0x14001b313  mov     eax, ebx
0x14001b315  jmp     short loc_14001B31B
0x14001b317  mov     eax, [rsp+1A8h+var_188]
0x14001b31b  mov     rcx, [rsp+1A8h+var_18]
0x14001b323  xor     rcx, rsp; StackCookie
0x14001b326  call    __security_check_cookie
0x14001b32b  add     rsp, 1A0h
0x14001b332  pop     rbx
0x14001b333  retn
```
