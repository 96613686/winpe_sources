# BioIsoSrvStorageDeleteRecord

- ea: `0x140014940`
- end: `0x140014b22`
- name: `BioIsoSrvStorageDeleteRecord`
- size: `482`
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
- `0x140014940`
- `0x140014b28`
- `0x14001bd40`
- `0x140046520`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x1400149a3`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400149e2`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014a2b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014ad2`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014966`: `StorageDeleteRecord`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageDeleteRecord(int *a1, __int64 a2, char a3)
{
  int BiometricUnit; // eax
  __int64 v8; // r8
  int v9; // ebx
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64, __int64, __int64); // rax
  int v12; // [rsp+20h] [rbp-198h]
  std::_Ref_count_base *v13[2]; // [rsp+28h] [rbp-190h] BYREF
  _QWORD v14[42]; // [rsp+40h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v14,
    (__int64)"StorageDeleteRecord");
  v14[0] = &BioIsoProvider::StorageDeleteRecord::`vftable';
  BioIsoProvider::StorageDeleteRecord::StartActivity((BioIsoProvider::StorageDeleteRecord *)v14);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v12);
    BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord((BioIsoProvider::StorageDeleteRecord *)v14);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D8,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v12);
    BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord((BioIsoProvider::StorageDeleteRecord *)v14);
    return 2147942487LL;
  }
  *(_OWORD *)v13 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v13);
  v9 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DD,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v12);
    if ( v13[1] )
      std::_Ref_count_base::_Decref(v13[1]);
LABEL_20:
    BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord((BioIsoProvider::StorageDeleteRecord *)v14);
    return (unsigned int)v9;
  }
  if ( *((_QWORD *)v13[0] + 3) == -32 || (v10 = *(_QWORD *)(*((_QWORD *)v13[0] + 3) + 72LL)) == 0 )
  {
    v9 = -2147467261;
    goto LABEL_18;
  }
  v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(v10 + 112);
  if ( !v11 )
  {
    v9 = -2147467263;
    goto LABEL_18;
  }
  LOBYTE(v8) = a3;
  v9 = v11(*((_QWORD *)v13[0] + 3) + 32LL, a2, v8);
  if ( v9 < 0 )
  {
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E0,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v9,
      v12);
    if ( v13[1] )
      std::_Ref_count_base::_Decref(v13[1]);
    goto LABEL_20;
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v14, 0);
  if ( v13[1] )
    std::_Ref_count_base::_Decref(v13[1]);
  BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord((BioIsoProvider::StorageDeleteRecord *)v14);
  return 0;
}

```

## disassembly

```asm
0x140014940  push    rbx
0x140014942  push    rsi
0x140014943  push    rdi
0x140014944  sub     rsp, 1A0h
0x14001494b  mov     rax, cs:__security_cookie
0x140014952  xor     rax, rsp
0x140014955  mov     [rsp+1B8h+var_28], rax
0x14001495d  mov     sil, r8b
0x140014960  mov     rdi, rdx
0x140014963  mov     rbx, rcx
0x140014966  lea     rdx, aStoragedeleter; "StorageDeleteRecord"
0x14001496d  lea     rcx, [rsp+1B8h+var_178]
0x140014972  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140014977  lea     rax, ??_7StorageDeleteRecord@BioIsoProvider@@6B@; const BioIsoProvider::StorageDeleteRecord::`vftable'
0x14001497e  mov     [rsp+1B8h+var_178], rax
0x140014983  lea     rcx, [rsp+1B8h+var_178]; this
0x140014988  call    ?StartActivity@StorageDeleteRecord@BioIsoProvider@@QEAAXXZ; BioIsoProvider::StorageDeleteRecord::StartActivity(void)
0x14001498d  nop
0x14001498e  test    rbx, rbx
0x140014991  jnz     short loc_1400149C6
0x140014993  mov     rcx, [rsp+1B8h]; this
0x14001499b  mov     ebx, 80004003h
0x1400149a0  mov     r9d, ebx; char *
0x1400149a3  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400149aa  mov     edx, 6D7h; void *
0x1400149af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400149b4  nop
0x1400149b5  lea     rcx, [rsp+1B8h+var_178]; this
0x1400149ba  call    ??1StorageDeleteRecord@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord(void)
0x1400149bf  mov     eax, ebx
0x1400149c1  jmp     loc_140014B06
0x1400149c6  mov     rcx, rbx; void *
0x1400149c9  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400149ce  test    al, al
0x1400149d0  jnz     short loc_140014A05
0x1400149d2  mov     rcx, [rsp+1B8h]; this
0x1400149da  mov     ebx, 80070057h
0x1400149df  mov     r9d, ebx; char *
0x1400149e2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400149e9  mov     edx, 6D8h; void *
0x1400149ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400149f3  nop
0x1400149f4  lea     rcx, [rsp+1B8h+var_178]; this
0x1400149f9  call    ??1StorageDeleteRecord@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord(void)
0x1400149fe  mov     eax, ebx
0x140014a00  jmp     loc_140014B06
0x140014a05  xorps   xmm0, xmm0
0x140014a08  movdqu  xmmword ptr [rsp+1B8h+var_190], xmm0
0x140014a0e  lea     rdx, [rsp+1B8h+var_190]
0x140014a13  mov     ecx, [rbx]
0x140014a15  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140014a1a  mov     ebx, eax
0x140014a1c  test    eax, eax
0x140014a1e  jns     short loc_140014A5E
0x140014a20  mov     rcx, [rsp+1B8h]; this
0x140014a28  mov     r9d, eax; char *
0x140014a2b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140014a32  mov     edx, 6DDh; void *
0x140014a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014a3c  nop
0x140014a3d  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140014a42  test    rcx, rcx
0x140014a45  jz      short loc_140014A4D
0x140014a47  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140014a4c  nop
0x140014a4d  lea     rcx, [rsp+1B8h+var_178]; this
0x140014a52  call    ??1StorageDeleteRecord@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord(void)
0x140014a57  mov     eax, ebx
0x140014a59  jmp     loc_140014B06
0x140014a5e  mov     rax, [rsp+1B8h+var_190]
0x140014a63  mov     rcx, [rax+18h]
0x140014a67  add     rcx, 20h ; ' '
0x140014a6b  jz      short loc_140014AC2
0x140014a6d  mov     rax, [rcx+28h]
0x140014a71  test    rax, rax
0x140014a74  jz      short loc_140014AC2
0x140014a76  mov     rax, [rax+70h]
0x140014a7a  test    rax, rax
0x140014a7d  jnz     short loc_140014A86
0x140014a7f  mov     ebx, 80004001h
0x140014a84  jmp     short loc_140014AC7
0x140014a86  mov     r8b, sil
0x140014a89  mov     rdx, rdi
0x140014a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a91  mov     ebx, eax
0x140014a93  test    eax, eax
0x140014a95  js      short loc_140014AC7
0x140014a97  xor     edx, edx
0x140014a99  lea     rcx, [rsp+1B8h+var_178]
0x140014a9e  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140014aa3  nop
0x140014aa4  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140014aa9  test    rcx, rcx
0x140014aac  jz      short loc_140014AB4
0x140014aae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140014ab3  nop
0x140014ab4  lea     rcx, [rsp+1B8h+var_178]; this
0x140014ab9  call    ??1StorageDeleteRecord@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord(void)
0x140014abe  xor     eax, eax
0x140014ac0  jmp     short loc_140014B06
0x140014ac2  mov     ebx, 80004003h
0x140014ac7  mov     rcx, [rsp+1B8h]; this
0x140014acf  mov     r9d, ebx; char *
0x140014ad2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140014ad9  mov     edx, 6E0h; void *
0x140014ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014ae3  nop
0x140014ae4  mov     rcx, [rsp+1B8h+var_190+8]; this
0x140014ae9  test    rcx, rcx
0x140014aec  jz      short loc_140014AF4
0x140014aee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140014af3  nop
0x140014af4  lea     rcx, [rsp+1B8h+var_178]; this
0x140014af9  call    ??1StorageDeleteRecord@BioIsoProvider@@QEAA@XZ; BioIsoProvider::StorageDeleteRecord::~StorageDeleteRecord(void)
0x140014afe  mov     eax, ebx
0x140014b00  jmp     short loc_140014B06
0x140014b02  mov     eax, [rsp+1B8h+var_198]
0x140014b06  mov     rcx, [rsp+1B8h+var_28]
0x140014b0e  xor     rcx, rsp; StackCookie
0x140014b11  call    __security_check_cookie
0x140014b16  add     rsp, 1A0h
0x140014b1d  pop     rdi
0x140014b1e  pop     rsi
0x140014b1f  pop     rbx
0x140014b20  retn
```
