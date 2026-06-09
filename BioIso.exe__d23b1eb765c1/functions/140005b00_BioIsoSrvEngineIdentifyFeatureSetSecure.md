# BioIsoSrvEngineIdentifyFeatureSetSecure

- ea: `0x140005b00`
- end: `0x140005e67`
- name: `BioIsoSrvEngineIdentifyFeatureSetSecure`
- size: `871`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005b00`
- `0x140005e70`
- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x14001bd40`
- `0x140044238`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x140005bb3`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140005bf5`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140005c8c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140005d9c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140005ddf`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140005e12`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineIdentifyFeatureSetSecure(
        int *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _DWORD *a10)
{
  int BiometricUnit; // eax
  int v16; // ebx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64, __int64, __int64, __int64 *); // rax
  __int64 *v19; // [rsp+20h] [rbp-1F8h]
  std::_Ref_count_base *v20[2]; // [rsp+58h] [rbp-1C0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-1B0h]
  __int64 v22; // [rsp+70h] [rbp-1A8h]
  __int64 v23; // [rsp+78h] [rbp-1A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-198h] BYREF
  __int64 v25; // [rsp+88h] [rbp-190h]
  _QWORD v26[42]; // [rsp+90h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v25 = a7;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v26,
    (__int64)"EngineIdentifyFeatureSetSecure");
  v26[0] = &BioIsoProvider::EngineIdentifyFeatureSetSecure::`vftable';
  BioIsoProvider::EngineIdentifyFeatureSetSecure::StartActivity((BioIsoProvider::EngineIdentifyFeatureSetSecure *)v26);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      (int)v19);
    BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure((BioIsoProvider::EngineIdentifyFeatureSetSecure *)v26);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BC,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      (int)v19);
    BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure((BioIsoProvider::EngineIdentifyFeatureSetSecure *)v26);
    return 2147942487LL;
  }
  if ( !a9 || !a10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      (int)v19);
    BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure((BioIsoProvider::EngineIdentifyFeatureSetSecure *)v26);
    return 2147500035LL;
  }
  *a9 = 0;
  *a10 = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      (int)v19);
    BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure((BioIsoProvider::EngineIdentifyFeatureSetSecure *)v26);
    return 2147942487LL;
  }
  *(_OWORD *)v20 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v20);
  v16 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CF,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      (int)v19);
    if ( v20[1] )
      std::_Ref_count_base::_Decref(v20[1]);
LABEL_14:
    BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure((BioIsoProvider::EngineIdentifyFeatureSetSecure *)v26);
    return (unsigned int)v16;
  }
  v24 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  if ( *((_QWORD *)v20[0] + 3) == -32 || (v17 = *(_QWORD *)(*((_QWORD *)v20[0] + 3) + 64LL)) == 0 )
  {
    v16 = -2147467261;
    goto LABEL_24;
  }
  v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(v17 + 120);
  if ( !v18 )
  {
    v16 = -2147467263;
    goto LABEL_24;
  }
  v19 = &v23;
  v16 = v18(*((_QWORD *)v20[0] + 3) + 32LL, a6, v25, &v24);
  if ( v16 < 0 )
  {
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E0,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v16,
      (int)v19);
    if ( v20[1] )
      std::_Ref_count_base::_Decref(v20[1]);
    goto LABEL_14;
  }
  *a9 = 0;
  *a10 = 0;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v26, 0);
  if ( v20[1] )
    std::_Ref_count_base::_Decref(v20[1]);
  BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure((BioIsoProvider::EngineIdentifyFeatureSetSecure *)v26);
  return 0;
}

```

## disassembly

```asm
0x140005b00  mov     [rsp+arg_8], rbx
0x140005b05  mov     [rsp+arg_10], rsi
0x140005b0a  push    rdi
0x140005b0b  push    r12
0x140005b0d  push    r13
0x140005b0f  push    r14
0x140005b11  push    r15
0x140005b13  sub     rsp, 1F0h
0x140005b1a  mov     rax, cs:__security_cookie
0x140005b21  xor     rax, rsp
0x140005b24  mov     [rsp+218h+var_38], rax
0x140005b2c  mov     r12, r9
0x140005b2f  mov     r15d, r8d
0x140005b32  mov     r14, rdx
0x140005b35  mov     rbx, rcx
0x140005b38  mov     r13, [rsp+218h+arg_28]
0x140005b40  mov     rax, [rsp+218h+arg_30]
0x140005b48  mov     [rsp+218h+var_190], rax
0x140005b50  mov     rax, [rsp+218h+arg_38]
0x140005b58  mov     [rsp+218h+var_1C8], rax
0x140005b5d  mov     rdi, [rsp+218h+arg_40]
0x140005b65  mov     rsi, [rsp+218h+arg_48]
0x140005b6d  lea     rdx, aEngineidentify; "EngineIdentifyFeatureSetSecure"
0x140005b74  lea     rcx, [rsp+218h+var_188]
0x140005b7c  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140005b81  lea     rax, ??_7EngineIdentifyFeatureSetSecure@BioIsoProvider@@6B@; const BioIsoProvider::EngineIdentifyFeatureSetSecure::`vftable'
0x140005b88  mov     [rsp+218h+var_188], rax
0x140005b90  lea     rcx, [rsp+218h+var_188]; this
0x140005b98  call    ?StartActivity@EngineIdentifyFeatureSetSecure@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineIdentifyFeatureSetSecure::StartActivity(void)
0x140005b9d  nop
0x140005b9e  test    rbx, rbx
0x140005ba1  jnz     short loc_140005BD9
0x140005ba3  mov     rcx, [rsp+218h]; this
0x140005bab  mov     ebx, 80004003h
0x140005bb0  mov     r9d, ebx; char *
0x140005bb3  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140005bba  mov     edx, 5BBh; void *
0x140005bbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005bc4  nop
0x140005bc5  lea     rcx, [rsp+218h+var_188]; this
0x140005bcd  call    ??1EngineIdentifyFeatureSetSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure(void)
0x140005bd2  mov     eax, ebx
0x140005bd4  jmp     loc_140005E39
0x140005bd9  mov     rcx, rbx; void *
0x140005bdc  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140005be1  test    al, al
0x140005be3  jnz     short loc_140005C1B
0x140005be5  mov     rcx, [rsp+218h]; this
0x140005bed  mov     ebx, 80070057h
0x140005bf2  mov     r9d, ebx; char *
0x140005bf5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140005bfc  mov     edx, 5BCh; void *
0x140005c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005c06  nop
0x140005c07  lea     rcx, [rsp+218h+var_188]; this
0x140005c0f  call    ??1EngineIdentifyFeatureSetSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure(void)
0x140005c14  mov     eax, ebx
0x140005c16  jmp     loc_140005E39
0x140005c1b  test    rdi, rdi
0x140005c1e  jz      loc_140005E02
0x140005c24  test    rsi, rsi
0x140005c27  jz      loc_140005E02
0x140005c2d  mov     qword ptr [rdi], 0
0x140005c34  mov     dword ptr [rsi], 0
0x140005c3a  test    r14, r14
0x140005c3d  jz      loc_140005DCF
0x140005c43  xor     r14d, r14d
0x140005c46  test    r15d, r15d
0x140005c49  jz      loc_140005DCF
0x140005c4f  test    r12, r12
0x140005c52  jz      loc_140005DCF
0x140005c58  cmp     [rsp+218h+arg_20], r14d
0x140005c60  jz      loc_140005DCF
0x140005c66  xorps   xmm0, xmm0
0x140005c69  movdqu  xmmword ptr [rsp+218h+var_1C0], xmm0
0x140005c6f  lea     rdx, [rsp+218h+var_1C0]
0x140005c74  mov     ecx, [rbx]
0x140005c76  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140005c7b  mov     ebx, eax
0x140005c7d  test    eax, eax
0x140005c7f  jns     short loc_140005CC2
0x140005c81  mov     rcx, [rsp+218h]; this
0x140005c89  mov     r9d, eax; char *
0x140005c8c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140005c93  mov     edx, 5CFh; void *
0x140005c98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005c9d  nop
0x140005c9e  mov     rcx, [rsp+218h+var_1C0+8]; this
0x140005ca3  test    rcx, rcx
0x140005ca6  jz      short loc_140005CAE
0x140005ca8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140005cad  nop
0x140005cae  lea     rcx, [rsp+218h+var_188]; this
0x140005cb6  call    ??1EngineIdentifyFeatureSetSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure(void)
0x140005cbb  mov     eax, ebx
0x140005cbd  jmp     loc_140005E39
0x140005cc2  mov     [rsp+218h+var_198], r14
0x140005cca  mov     [rsp+218h+var_1A0], r14
0x140005ccf  mov     [rsp+218h+var_1A8], r14
0x140005cd4  mov     [rsp+218h+var_1B0], r14
0x140005cd9  mov     rax, [rsp+218h+var_1C0]
0x140005cde  mov     rcx, [rax+18h]
0x140005ce2  add     rcx, 20h ; ' '
0x140005ce6  jz      loc_140005D8C
0x140005cec  mov     rax, [rcx+20h]
0x140005cf0  test    rax, rax
0x140005cf3  jz      loc_140005D8C
0x140005cf9  mov     rax, [rax+78h]
0x140005cfd  test    rax, rax
0x140005d00  jnz     short loc_140005D0C
0x140005d02  mov     ebx, 80004001h
0x140005d07  jmp     loc_140005D91
0x140005d0c  mov     rdx, [rsp+218h+var_1C8]
0x140005d11  mov     [rsp+218h+var_1E0], rdx
0x140005d16  lea     rdx, [rsp+218h+var_1B0]
0x140005d1b  mov     [rsp+218h+var_1E8], rdx
0x140005d20  lea     rdx, [rsp+218h+var_1A8]
0x140005d25  mov     [rsp+218h+var_1F0], rdx
0x140005d2a  lea     rdx, [rsp+218h+var_1A0]
0x140005d2f  mov     [rsp+218h+var_1F8], rdx
0x140005d34  lea     r9, [rsp+218h+var_198]
0x140005d3c  mov     r8, [rsp+218h+var_190]
0x140005d44  mov     rdx, r13
0x140005d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d4c  mov     ebx, eax
0x140005d4e  test    eax, eax
0x140005d50  js      short loc_140005D91
0x140005d52  mov     [rdi], r14
0x140005d55  mov     [rsi], r14d
0x140005d58  xor     edx, edx
0x140005d5a  lea     rcx, [rsp+218h+var_188]
0x140005d62  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140005d67  nop
0x140005d68  mov     rcx, [rsp+218h+var_1C0+8]; this
0x140005d6d  test    rcx, rcx
0x140005d70  jz      short loc_140005D78
0x140005d72  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140005d77  nop
0x140005d78  lea     rcx, [rsp+218h+var_188]; this
0x140005d80  call    ??1EngineIdentifyFeatureSetSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure(void)
0x140005d85  xor     eax, eax
0x140005d87  jmp     loc_140005E39
0x140005d8c  mov     ebx, 80004003h
0x140005d91  mov     rcx, [rsp+218h]; this
0x140005d99  mov     r9d, ebx; char *
0x140005d9c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140005da3  mov     edx, 5E0h; void *
0x140005da8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005dad  nop
0x140005dae  mov     rcx, [rsp+218h+var_1C0+8]; this
0x140005db3  test    rcx, rcx
0x140005db6  jz      short loc_140005DBE
0x140005db8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140005dbd  nop
0x140005dbe  lea     rcx, [rsp+218h+var_188]; this
0x140005dc6  call    ??1EngineIdentifyFeatureSetSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure(void)
0x140005dcb  mov     eax, ebx
0x140005dcd  jmp     short loc_140005E39
0x140005dcf  mov     rcx, [rsp+218h]; this
0x140005dd7  mov     ebx, 80070057h
0x140005ddc  mov     r9d, ebx; char *
0x140005ddf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140005de6  mov     edx, 5CBh; void *
0x140005deb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005df0  nop
0x140005df1  lea     rcx, [rsp+218h+var_188]; this
0x140005df9  call    ??1EngineIdentifyFeatureSetSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure(void)
0x140005dfe  mov     eax, ebx
0x140005e00  jmp     short loc_140005E39
0x140005e02  mov     rcx, [rsp+218h]; this
0x140005e0a  mov     ebx, 80004003h
0x140005e0f  mov     r9d, ebx; char *
0x140005e12  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140005e19  mov     edx, 5C2h; void *
0x140005e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005e23  nop
0x140005e24  lea     rcx, [rsp+218h+var_188]; this
0x140005e2c  call    ??1EngineIdentifyFeatureSetSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineIdentifyFeatureSetSecure::~EngineIdentifyFeatureSetSecure(void)
0x140005e31  mov     eax, ebx
0x140005e33  jmp     short loc_140005E39
0x140005e35  mov     eax, dword ptr [rsp+218h+var_1C8]
0x140005e39  mov     rcx, [rsp+218h+var_38]
0x140005e41  xor     rcx, rsp; StackCookie
0x140005e44  call    __security_check_cookie
0x140005e49  lea     r11, [rsp+218h+var_28]
0x140005e51  mov     rbx, [r11+38h]
0x140005e55  mov     rsi, [r11+40h]
0x140005e59  mov     rsp, r11
0x140005e5c  pop     r15
0x140005e5e  pop     r14
0x140005e60  pop     r13
0x140005e62  pop     r12
0x140005e64  pop     rdi
0x140005e65  retn
```
