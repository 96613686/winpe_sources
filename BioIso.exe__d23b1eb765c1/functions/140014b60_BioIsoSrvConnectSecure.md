# BioIsoSrvConnectSecure

- ea: `0x140014b60`
- end: `0x140014d9b`
- name: `BioIsoSrvConnectSecure`
- size: `571`
- prototype: `__int64 __fastcall(unsigned int *, const struct _WINBIO_SECURE_CONNECTION_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140014b60`
- `0x140014da4`
- `0x14001bd40`
- `0x1400436a0`
- `0x140059830`
- `0x14005d534`

## string_xrefs

- `0x140014bca`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014c01`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014c39`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014c78`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014cc1`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014d16`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvConnectSecure(
        unsigned int *a1,
        const struct _WINBIO_SECURE_CONNECTION_DATA *a2,
        unsigned int a3)
{
  int BiometricUnit; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // [rsp+20h] [rbp-188h]
  std::_Ref_count_base *v11[2]; // [rsp+28h] [rbp-180h] BYREF
  _QWORD v12[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "ConnectSecure");
  v12[0] = &BioIsoProvider::ConnectSecure::`vftable';
  BioIsoProvider::ConnectSecure::StartActivity((BioIsoProvider::ConnectSecure *)v12);
  if ( a3 < 0x14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB0,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::ConnectSecure::~ConnectSecure((BioIsoProvider::ConnectSecure *)v12);
    return 2147942487LL;
  }
  if ( a3 < *(_DWORD *)a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB1,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::ConnectSecure::~ConnectSecure((BioIsoProvider::ConnectSecure *)v12);
    return 2147942487LL;
  }
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB3,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v10);
    BioIsoProvider::ConnectSecure::~ConnectSecure((BioIsoProvider::ConnectSecure *)v12);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB4,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v10);
    BioIsoProvider::ConnectSecure::~ConnectSecure((BioIsoProvider::ConnectSecure *)v12);
    return 2147942487LL;
  }
  *(_OWORD *)v11 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, v11);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB8,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
LABEL_12:
    BioIsoProvider::ConnectSecure::~ConnectSecure((BioIsoProvider::ConnectSecure *)v12);
    return v8;
  }
  v9 = SecureConnection::Connect((std::_Ref_count_base *)((char *)v11[0] + 96), a2);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBBA,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v9,
      v10);
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
    goto LABEL_12;
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12, 0);
  if ( v11[1] )
    std::_Ref_count_base::_Decref(v11[1]);
  BioIsoProvider::ConnectSecure::~ConnectSecure((BioIsoProvider::ConnectSecure *)v12);
  return 0;
}

```

## disassembly

```asm
0x140014b60  mov     [rsp+arg_10], rbx
0x140014b65  mov     [rsp+arg_18], rsi
0x140014b6a  push    rdi
0x140014b6b  sub     rsp, 1A0h
0x140014b72  mov     rax, cs:__security_cookie
0x140014b79  xor     rax, rsp
0x140014b7c  mov     [rsp+1A8h+var_18], rax
0x140014b84  mov     edi, r8d
0x140014b87  mov     rsi, rdx
0x140014b8a  mov     rbx, rcx
0x140014b8d  lea     rdx, aConnectsecure; "ConnectSecure"
0x140014b94  lea     rcx, [rsp+1A8h+var_168]
0x140014b99  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140014b9e  lea     rax, ??_7ConnectSecure@BioIsoProvider@@6B@; const BioIsoProvider::ConnectSecure::`vftable'
0x140014ba5  mov     [rsp+1A8h+var_168], rax
0x140014baa  lea     rcx, [rsp+1A8h+var_168]; this
0x140014baf  call    ?StartActivity@ConnectSecure@BioIsoProvider@@QEAAXXZ; BioIsoProvider::ConnectSecure::StartActivity(void)
0x140014bb4  nop
0x140014bb5  cmp     edi, 14h
0x140014bb8  jnb     short loc_140014BED
0x140014bba  mov     rcx, [rsp+1A8h]; this
0x140014bc2  mov     ebx, 80070057h
0x140014bc7  mov     r9d, ebx; char *
0x140014bca  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140014bd1  mov     edx, 0BB0h; void *
0x140014bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014bdb  nop
0x140014bdc  lea     rcx, [rsp+1A8h+var_168]; this
0x140014be1  call    ??1ConnectSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::ConnectSecure::~ConnectSecure(void)
0x140014be6  mov     eax, ebx
0x140014be8  jmp     loc_140014D75
0x140014bed  cmp     edi, [rsi]
0x140014bef  jnb     short loc_140014C24
0x140014bf1  mov     rcx, [rsp+1A8h]; this
0x140014bf9  mov     ebx, 80070057h
0x140014bfe  mov     r9d, ebx; char *
0x140014c01  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140014c08  mov     edx, 0BB1h; void *
0x140014c0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014c12  nop
0x140014c13  lea     rcx, [rsp+1A8h+var_168]; this
0x140014c18  call    ??1ConnectSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::ConnectSecure::~ConnectSecure(void)
0x140014c1d  mov     eax, ebx
0x140014c1f  jmp     loc_140014D75
0x140014c24  test    rbx, rbx
0x140014c27  jnz     short loc_140014C5C
0x140014c29  mov     rcx, [rsp+1A8h]; this
0x140014c31  mov     ebx, 80004003h
0x140014c36  mov     r9d, ebx; char *
0x140014c39  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140014c40  mov     edx, 0BB3h; void *
0x140014c45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014c4a  nop
0x140014c4b  lea     rcx, [rsp+1A8h+var_168]; this
0x140014c50  call    ??1ConnectSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::ConnectSecure::~ConnectSecure(void)
0x140014c55  mov     eax, ebx
0x140014c57  jmp     loc_140014D75
0x140014c5c  mov     rcx, rbx; void *
0x140014c5f  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140014c64  test    al, al
0x140014c66  jnz     short loc_140014C9B
0x140014c68  mov     rcx, [rsp+1A8h]; this
0x140014c70  mov     ebx, 80070057h
0x140014c75  mov     r9d, ebx; char *
0x140014c78  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140014c7f  mov     edx, 0BB4h; void *
0x140014c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014c89  nop
0x140014c8a  lea     rcx, [rsp+1A8h+var_168]; this
0x140014c8f  call    ??1ConnectSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::ConnectSecure::~ConnectSecure(void)
0x140014c94  mov     eax, ebx
0x140014c96  jmp     loc_140014D75
0x140014c9b  xorps   xmm0, xmm0
0x140014c9e  movdqu  xmmword ptr [rsp+1A8h+var_180], xmm0
0x140014ca4  lea     rdx, [rsp+1A8h+var_180]
0x140014ca9  mov     ecx, [rbx]
0x140014cab  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140014cb0  mov     ebx, eax
0x140014cb2  test    eax, eax
0x140014cb4  jns     short loc_140014CF4
0x140014cb6  mov     rcx, [rsp+1A8h]; this
0x140014cbe  mov     r9d, eax; char *
0x140014cc1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140014cc8  mov     edx, 0BB8h; void *
0x140014ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014cd2  nop
0x140014cd3  mov     rcx, [rsp+1A8h+var_180+8]; this
0x140014cd8  test    rcx, rcx
0x140014cdb  jz      short loc_140014CE3
0x140014cdd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140014ce2  nop
0x140014ce3  lea     rcx, [rsp+1A8h+var_168]; this
0x140014ce8  call    ??1ConnectSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::ConnectSecure::~ConnectSecure(void)
0x140014ced  mov     eax, ebx
0x140014cef  jmp     loc_140014D75
0x140014cf4  mov     rcx, [rsp+1A8h+var_180]
0x140014cf9  add     rcx, 60h ; '`'; this
0x140014cfd  mov     rdx, rsi; struct _WINBIO_SECURE_CONNECTION_DATA *
0x140014d00  call    ?Connect@SecureConnection@@QEAAJPEBU_WINBIO_SECURE_CONNECTION_DATA@@@Z; SecureConnection::Connect(_WINBIO_SECURE_CONNECTION_DATA const *)
0x140014d05  mov     ebx, eax
0x140014d07  test    eax, eax
0x140014d09  jns     short loc_140014D46
0x140014d0b  mov     rcx, [rsp+1A8h]; this
0x140014d13  mov     r9d, eax; char *
0x140014d16  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140014d1d  mov     edx, 0BBAh; void *
0x140014d22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014d27  nop
0x140014d28  mov     rcx, [rsp+1A8h+var_180+8]; this
0x140014d2d  test    rcx, rcx
0x140014d30  jz      short loc_140014D38
0x140014d32  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140014d37  nop
0x140014d38  lea     rcx, [rsp+1A8h+var_168]; this
0x140014d3d  call    ??1ConnectSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::ConnectSecure::~ConnectSecure(void)
0x140014d42  mov     eax, ebx
0x140014d44  jmp     short loc_140014D75
0x140014d46  xor     edx, edx
0x140014d48  lea     rcx, [rsp+1A8h+var_168]
0x140014d4d  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140014d52  nop
0x140014d53  mov     rcx, [rsp+1A8h+var_180+8]; this
0x140014d58  test    rcx, rcx
0x140014d5b  jz      short loc_140014D63
0x140014d5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140014d62  nop
0x140014d63  lea     rcx, [rsp+1A8h+var_168]; this
0x140014d68  call    ??1ConnectSecure@BioIsoProvider@@QEAA@XZ; BioIsoProvider::ConnectSecure::~ConnectSecure(void)
0x140014d6d  xor     eax, eax
0x140014d6f  jmp     short loc_140014D75
0x140014d71  mov     eax, [rsp+1A8h+var_188]
0x140014d75  mov     rcx, [rsp+1A8h+var_18]
0x140014d7d  xor     rcx, rsp; StackCookie
0x140014d80  call    __security_check_cookie
0x140014d85  lea     r11, [rsp+1A8h+var_8]
0x140014d8d  mov     rbx, [r11+20h]
0x140014d91  mov     rsi, [r11+28h]
0x140014d95  mov     rsp, r11
0x140014d98  pop     rdi
0x140014d99  retn
```
