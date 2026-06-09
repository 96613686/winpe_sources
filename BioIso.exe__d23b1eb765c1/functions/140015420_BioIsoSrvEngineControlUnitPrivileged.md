# BioIsoSrvEngineControlUnitPrivileged

- ea: `0x140015420`
- end: `0x140015665`
- name: `BioIsoSrvEngineControlUnitPrivileged`
- size: `581`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, __int64, unsigned int, __int64, int, _DWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140015420`
- `0x14001566c`
- `0x14001bd40`
- `0x140043da0`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x1400154a5`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400154e4`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001552d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001560d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140015468`: `EngineControlUnitPrivileged`

## pseudocode

```c
__int64 __fastcall BioIsoSrvEngineControlUnitPrivileged(
        unsigned int *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        _DWORD *a7)
{
  __int64 v7; // r15
  int BiometricUnit; // eax
  int v13; // ebx
  __int64 v14; // rax
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64, __int64); // rax
  int v16; // [rsp+20h] [rbp-1E8h]
  std::_Ref_count_base *v17[2]; // [rsp+58h] [rbp-1B0h] BYREF
  _QWORD v18[42]; // [rsp+70h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v7 = a4;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "EngineControlUnitPrivileged");
  v18[0] = &BioIsoProvider::EngineControlUnitPrivileged::`vftable';
  BioIsoProvider::EngineControlUnitPrivileged::StartActivity((BioIsoProvider::EngineControlUnitPrivileged *)v18);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43D,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v16);
    BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged((BioIsoProvider::EngineControlUnitPrivileged *)v18);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v16);
    BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged((BioIsoProvider::EngineControlUnitPrivileged *)v18);
    return 2147942487LL;
  }
  *(_OWORD *)v17 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, v17);
  v13 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x443,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v16);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
LABEL_20:
    BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged((BioIsoProvider::EngineControlUnitPrivileged *)v18);
    return (unsigned int)v13;
  }
  if ( *((_QWORD *)v17[0] + 3) == -32 || (v14 = *(_QWORD *)(*((_QWORD *)v17[0] + 3) + 64LL)) == 0 )
  {
    v13 = -2147467261;
    goto LABEL_18;
  }
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(v14 + 192);
  if ( !v15 )
  {
    v13 = -2147467263;
    goto LABEL_18;
  }
  v16 = a5;
  v13 = v15(*((_QWORD *)v17[0] + 3) + 32LL, a2, a3, v7);
  if ( v13 < 0 )
  {
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x452,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v13,
      v16);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
    goto LABEL_20;
  }
  *a7 = 0;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, 0);
  if ( v17[1] )
    std::_Ref_count_base::_Decref(v17[1]);
  BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged((BioIsoProvider::EngineControlUnitPrivileged *)v18);
  return 0;
}

```

## disassembly

```asm
0x140015420  push    rbx
0x140015422  push    rsi
0x140015423  push    rdi
0x140015424  push    r12
0x140015426  push    r13
0x140015428  push    r14
0x14001542a  push    r15
0x14001542c  sub     rsp, 1D0h
0x140015433  mov     rax, cs:__security_cookie
0x14001543a  xor     rax, rsp
0x14001543d  mov     [rsp+208h+var_48], rax
0x140015445  mov     r15d, r9d
0x140015448  mov     r14, r8
0x14001544b  mov     esi, edx
0x14001544d  mov     rbx, rcx
0x140015450  mov     r12, [rsp+208h+arg_20]
0x140015458  mov     rdi, [rsp+208h+arg_30]
0x140015460  mov     r13, [rsp+208h+arg_38]
0x140015468  lea     rdx, aEnginecontrolu; "EngineControlUnitPrivileged"
0x14001546f  lea     rcx, [rsp+208h+var_198]
0x140015474  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140015479  lea     rax, ??_7EngineControlUnitPrivileged@BioIsoProvider@@6B@; const BioIsoProvider::EngineControlUnitPrivileged::`vftable'
0x140015480  mov     [rsp+208h+var_198], rax
0x140015485  lea     rcx, [rsp+208h+var_198]; this
0x14001548a  call    ?StartActivity@EngineControlUnitPrivileged@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineControlUnitPrivileged::StartActivity(void)
0x14001548f  nop
0x140015490  test    rbx, rbx
0x140015493  jnz     short loc_1400154C8
0x140015495  mov     rcx, [rsp+208h]; this
0x14001549d  mov     ebx, 80004003h
0x1400154a2  mov     r9d, ebx; char *
0x1400154a5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400154ac  mov     edx, 43Dh; void *
0x1400154b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400154b6  nop
0x1400154b7  lea     rcx, [rsp+208h+var_198]; this
0x1400154bc  call    ??1EngineControlUnitPrivileged@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged(void)
0x1400154c1  mov     eax, ebx
0x1400154c3  jmp     loc_140015641
0x1400154c8  mov     rcx, rbx; void *
0x1400154cb  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400154d0  test    al, al
0x1400154d2  jnz     short loc_140015507
0x1400154d4  mov     rcx, [rsp+208h]; this
0x1400154dc  mov     ebx, 80070057h
0x1400154e1  mov     r9d, ebx; char *
0x1400154e4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400154eb  mov     edx, 43Eh; void *
0x1400154f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400154f5  nop
0x1400154f6  lea     rcx, [rsp+208h+var_198]; this
0x1400154fb  call    ??1EngineControlUnitPrivileged@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged(void)
0x140015500  mov     eax, ebx
0x140015502  jmp     loc_140015641
0x140015507  xorps   xmm0, xmm0
0x14001550a  movdqu  xmmword ptr [rsp+208h+var_1B0], xmm0
0x140015510  lea     rdx, [rsp+208h+var_1B0]
0x140015515  mov     ecx, [rbx]
0x140015517  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14001551c  mov     ebx, eax
0x14001551e  test    eax, eax
0x140015520  jns     short loc_140015560
0x140015522  mov     rcx, [rsp+208h]; this
0x14001552a  mov     r9d, eax; char *
0x14001552d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140015534  mov     edx, 443h; void *
0x140015539  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001553e  nop
0x14001553f  mov     rcx, [rsp+208h+var_1B0+8]; this
0x140015544  test    rcx, rcx
0x140015547  jz      short loc_14001554F
0x140015549  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001554e  nop
0x14001554f  lea     rcx, [rsp+208h+var_198]; this
0x140015554  call    ??1EngineControlUnitPrivileged@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged(void)
0x140015559  mov     eax, ebx
0x14001555b  jmp     loc_140015641
0x140015560  mov     [rsp+208h+var_1B8], 0
0x140015569  mov     rax, [rsp+208h+var_1B0]
0x14001556e  mov     rcx, [rax+18h]
0x140015572  add     rcx, 20h ; ' '
0x140015576  jz      loc_1400155FD
0x14001557c  mov     rax, [rcx+20h]
0x140015580  test    rax, rax
0x140015583  jz      short loc_1400155FD
0x140015585  mov     rax, [rax+0C0h]
0x14001558c  test    rax, rax
0x14001558f  jnz     short loc_140015598
0x140015591  mov     ebx, 80004001h
0x140015596  jmp     short loc_140015602
0x140015598  mov     r10d, [rsp+208h+arg_28]
0x1400155a0  mov     r9, r15
0x1400155a3  mov     [rsp+208h+var_1D0], r13
0x1400155a8  lea     rdx, [rsp+208h+var_1B8]
0x1400155ad  mov     [rsp+208h+var_1D8], rdx
0x1400155b2  mov     [rsp+208h+var_1E0], r10
0x1400155b7  mov     [rsp+208h+var_1E8], r12
0x1400155bc  mov     r8, r14
0x1400155bf  mov     edx, esi
0x1400155c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400155c6  mov     ebx, eax
0x1400155c8  test    eax, eax
0x1400155ca  js      short loc_140015602
0x1400155cc  mov     eax, dword ptr [rsp+208h+var_1B8]
0x1400155d0  mov     [rdi], eax
0x1400155d2  xor     edx, edx
0x1400155d4  lea     rcx, [rsp+208h+var_198]
0x1400155d9  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400155de  nop
0x1400155df  mov     rcx, [rsp+208h+var_1B0+8]; this
0x1400155e4  test    rcx, rcx
0x1400155e7  jz      short loc_1400155EF
0x1400155e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400155ee  nop
0x1400155ef  lea     rcx, [rsp+208h+var_198]; this
0x1400155f4  call    ??1EngineControlUnitPrivileged@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged(void)
0x1400155f9  xor     eax, eax
0x1400155fb  jmp     short loc_140015641
0x1400155fd  mov     ebx, 80004003h
0x140015602  mov     rcx, [rsp+208h]; this
0x14001560a  mov     r9d, ebx; char *
0x14001560d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140015614  mov     edx, 452h; void *
0x140015619  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001561e  nop
0x14001561f  mov     rcx, [rsp+208h+var_1B0+8]; this
0x140015624  test    rcx, rcx
0x140015627  jz      short loc_14001562F
0x140015629  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001562e  nop
0x14001562f  lea     rcx, [rsp+208h+var_198]; this
0x140015634  call    ??1EngineControlUnitPrivileged@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineControlUnitPrivileged::~EngineControlUnitPrivileged(void)
0x140015639  mov     eax, ebx
0x14001563b  jmp     short loc_140015641
0x14001563d  mov     eax, dword ptr [rsp+208h+var_1B8]
0x140015641  mov     rcx, [rsp+208h+var_48]
0x140015649  xor     rcx, rsp; StackCookie
0x14001564c  call    __security_check_cookie
0x140015651  add     rsp, 1D0h
0x140015658  pop     r15
0x14001565a  pop     r14
0x14001565c  pop     r13
0x14001565e  pop     r12
0x140015660  pop     rdi
0x140015661  pop     rsi
0x140015662  pop     rbx
0x140015663  retn
```
