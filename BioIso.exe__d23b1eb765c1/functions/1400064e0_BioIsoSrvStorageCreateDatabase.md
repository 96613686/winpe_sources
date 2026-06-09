# BioIsoSrvStorageCreateDatabase

- ea: `0x1400064e0`
- end: `0x140006720`
- name: `BioIsoSrvStorageCreateDatabase`
- size: `576`
- prototype: `__int64 __fastcall(unsigned int *, __int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400064e0`
- `0x140006728`
- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x14001bd40`
- `0x1400463d0`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x14000655c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000659b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400065e4`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400066ca`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000651f`: `StorageCreateDatabase`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageCreateDatabase(
        unsigned int *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  int BiometricUnit; // eax
  int v11; // ebx
  int *v12; // rdx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, __int64); // rax
  int v15; // [rsp+20h] [rbp-1E8h]
  std::_Ref_count_base *v16[2]; // [rsp+58h] [rbp-1B0h] BYREF
  _QWORD v17[42]; // [rsp+70h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "StorageCreateDatabase");
  v17[0] = &BioIsoProvider::StorageCreateDatabase::`vftable';
  BioIsoProvider::StorageCreateDatabase::StartActivity((BioIsoProvider::StorageCreateDatabase *)v17);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x668,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v15);
    BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase((BioIsoProvider::StorageCreateDatabase *)v17);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x669,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v15);
    BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase((BioIsoProvider::StorageCreateDatabase *)v17);
    return 2147942487LL;
  }
  *(_OWORD *)v16 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, v16);
  v11 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v15);
    if ( v16[1] )
      std::_Ref_count_base::_Decref(v16[1]);
LABEL_22:
    BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase((BioIsoProvider::StorageCreateDatabase *)v17);
    return (unsigned int)v11;
  }
  v12 = &dword_14008BB54;
  if ( a5 )
    LODWORD(v12) = a5;
  if ( *((_QWORD *)v16[0] + 3) == -32 || (v13 = *(_QWORD *)(*((_QWORD *)v16[0] + 3) + 72LL)) == 0 )
  {
    v11 = -2147467261;
    goto LABEL_20;
  }
  v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(v13 + 56);
  if ( !v14 )
  {
    v11 = -2147467263;
    goto LABEL_20;
  }
  v15 = (int)v12;
  v11 = v14(*((_QWORD *)v16[0] + 3) + 32LL, a2, a3, a4);
  if ( v11 < 0 )
  {
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x679,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v11,
      v15);
    if ( v16[1] )
      std::_Ref_count_base::_Decref(v16[1]);
    goto LABEL_22;
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17, 0);
  if ( v16[1] )
    std::_Ref_count_base::_Decref(v16[1]);
  BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase((BioIsoProvider::StorageCreateDatabase *)v17);
  return 0;
}

```

## disassembly

```asm
0x1400064e0  push    rbx
0x1400064e2  push    rsi
0x1400064e3  push    rdi
0x1400064e4  push    r12
0x1400064e6  push    r14
0x1400064e8  push    r15
0x1400064ea  sub     rsp, 1D8h
0x1400064f1  mov     rax, cs:__security_cookie
0x1400064f8  xor     rax, rsp
0x1400064fb  mov     [rsp+208h+var_48], rax
0x140006503  mov     r12, r9
0x140006506  mov     r15d, r8d
0x140006509  mov     r14, rdx
0x14000650c  mov     rbx, rcx
0x14000650f  mov     rdi, [rsp+208h+arg_20]
0x140006517  mov     rsi, [rsp+208h+arg_28]
0x14000651f  lea     rdx, aStoragecreated; "StorageCreateDatabase"
0x140006526  lea     rcx, [rsp+208h+var_198]
0x14000652b  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140006530  lea     rax, ??_7StorageCreateDatabase@BioIsoProvider@@6B@; const BioIsoProvider::StorageCreateDatabase::`vftable'
0x140006537  mov     [rsp+208h+var_198], rax
0x14000653c  lea     rcx, [rsp+208h+var_198]; this
0x140006541  call    ?StartActivity@StorageCreateDatabase@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageCreateDatabase::StartActivity(void)
0x140006546  nop
0x140006547  test    rbx, rbx
0x14000654a  jnz     short loc_14000657F
0x14000654c  mov     rcx, [rsp+208h]; this
0x140006554  mov     ebx, 80004003h
0x140006559  mov     r9d, ebx; char *
0x14000655c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140006563  mov     edx, 668h; void *
0x140006568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000656d  nop
0x14000656e  lea     rcx, [rsp+208h+var_198]; this
0x140006573  call    ??1StorageCreateDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase(void)
0x140006578  mov     eax, ebx
0x14000657a  jmp     loc_1400066FE
0x14000657f  mov     rcx, rbx; void *
0x140006582  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140006587  test    al, al
0x140006589  jnz     short loc_1400065BE
0x14000658b  mov     rcx, [rsp+208h]; this
0x140006593  mov     ebx, 80070057h
0x140006598  mov     r9d, ebx; char *
0x14000659b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400065a2  mov     edx, 669h; void *
0x1400065a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400065ac  nop
0x1400065ad  lea     rcx, [rsp+208h+var_198]; this
0x1400065b2  call    ??1StorageCreateDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase(void)
0x1400065b7  mov     eax, ebx
0x1400065b9  jmp     loc_1400066FE
0x1400065be  xorps   xmm0, xmm0
0x1400065c1  movdqu  xmmword ptr [rsp+208h+var_1B0], xmm0
0x1400065c7  lea     rdx, [rsp+208h+var_1B0]
0x1400065cc  mov     ecx, [rbx]
0x1400065ce  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x1400065d3  mov     ebx, eax
0x1400065d5  test    eax, eax
0x1400065d7  jns     short loc_140006617
0x1400065d9  mov     rcx, [rsp+208h]; this
0x1400065e1  mov     r9d, eax; char *
0x1400065e4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400065eb  mov     edx, 66Eh; void *
0x1400065f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400065f5  nop
0x1400065f6  mov     rcx, [rsp+208h+var_1B0+8]; this
0x1400065fb  test    rcx, rcx
0x1400065fe  jz      short loc_140006606
0x140006600  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140006605  nop
0x140006606  lea     rcx, [rsp+208h+var_198]; this
0x14000660b  call    ??1StorageCreateDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase(void)
0x140006610  mov     eax, ebx
0x140006612  jmp     loc_1400066FE
0x140006617  lea     rdx, dword_14008BB54
0x14000661e  mov     r8, rdx
0x140006621  test    rsi, rsi
0x140006624  cmovnz  r8, rsi
0x140006628  test    rdi, rdi
0x14000662b  cmovnz  rdx, rdi
0x14000662f  mov     rax, [rsp+208h+var_1B0]
0x140006634  mov     rcx, [rax+18h]
0x140006638  add     rcx, 20h ; ' '
0x14000663c  jz      short loc_1400066BA
0x14000663e  mov     rax, [rcx+28h]
0x140006642  test    rax, rax
0x140006645  jz      short loc_1400066BA
0x140006647  mov     rax, [rax+38h]
0x14000664b  test    rax, rax
0x14000664e  jnz     short loc_140006657
0x140006650  mov     ebx, 80004001h
0x140006655  jmp     short loc_1400066BF
0x140006657  mov     r10d, [rsp+208h+arg_38]
0x14000665f  mov     r11d, [rsp+208h+arg_30]
0x140006667  mov     [rsp+208h+var_1D0], r10
0x14000666c  mov     [rsp+208h+var_1D8], r11
0x140006671  mov     [rsp+208h+var_1E0], r8
0x140006676  mov     [rsp+208h+var_1E8], rdx
0x14000667b  mov     r9, r12
0x14000667e  mov     r8d, r15d
0x140006681  mov     rdx, r14
0x140006684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006689  mov     ebx, eax
0x14000668b  test    eax, eax
0x14000668d  js      short loc_1400066BF
0x14000668f  xor     edx, edx
0x140006691  lea     rcx, [rsp+208h+var_198]
0x140006696  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000669b  nop
0x14000669c  mov     rcx, [rsp+208h+var_1B0+8]; this
0x1400066a1  test    rcx, rcx
0x1400066a4  jz      short loc_1400066AC
0x1400066a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400066ab  nop
0x1400066ac  lea     rcx, [rsp+208h+var_198]; this
0x1400066b1  call    ??1StorageCreateDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase(void)
0x1400066b6  xor     eax, eax
0x1400066b8  jmp     short loc_1400066FE
0x1400066ba  mov     ebx, 80004003h
0x1400066bf  mov     rcx, [rsp+208h]; this
0x1400066c7  mov     r9d, ebx; char *
0x1400066ca  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400066d1  mov     edx, 679h; void *
0x1400066d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400066db  nop
0x1400066dc  mov     rcx, [rsp+208h+var_1B0+8]; this
0x1400066e1  test    rcx, rcx
0x1400066e4  jz      short loc_1400066EC
0x1400066e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400066eb  nop
0x1400066ec  lea     rcx, [rsp+208h+var_198]; this
0x1400066f1  call    ??1StorageCreateDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageCreateDatabase::~StorageCreateDatabase(void)
0x1400066f6  mov     eax, ebx
0x1400066f8  jmp     short loc_1400066FE
0x1400066fa  mov     eax, [rsp+208h+var_1B8]
0x1400066fe  mov     rcx, [rsp+208h+var_48]
0x140006706  xor     rcx, rsp; StackCookie
0x140006709  call    __security_check_cookie
0x14000670e  add     rsp, 1D8h
0x140006715  pop     r15
0x140006717  pop     r14
0x140006719  pop     r12
0x14000671b  pop     rdi
0x14000671c  pop     rsi
0x14000671d  pop     rbx
0x14000671e  retn
```
