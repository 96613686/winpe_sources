# BioIsoSrvAuthenticateIdentification

- ea: `0x140008c60`
- end: `0x140008ff4`
- name: `BioIsoSrvAuthenticateIdentification`
- size: `916`
- prototype: `__int64 __fastcall(unsigned int *, _QWORD *, const unsigned __int8 *, unsigned int, struct _WINBIO_IDENTITY *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x140007ed4`
- `0x140008c60`
- `0x140008ffc`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x14000ae0c`
- `0x14000d5d0`
- `0x140012974`
- `0x14001bd40`
- `0x14001cb78`
- `0x14001cb90`
- `0x140040954`
- `0x140041968`
- `0x140043140`
- `0x1400597d4`
- `0x140059830`
- `0x14005d450`

## string_xrefs

- `0x140008ce5`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008d27`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008d73`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008de1`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008e57`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008ede`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvAuthenticateIdentification(
        unsigned int *a1,
        _QWORD *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct _WINBIO_IDENTITY *a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  int BiometricUnit; // eax
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // ebx
  void *v18; // rcx
  int v19; // [rsp+20h] [rbp-228h]
  int v20; // [rsp+20h] [rbp-228h]
  void *v21; // [rsp+30h] [rbp-218h] BYREF
  std::_Ref_count_base *v22[2]; // [rsp+38h] [rbp-210h] BYREF
  void *Src; // [rsp+48h] [rbp-200h] BYREF
  __int64 v24; // [rsp+50h] [rbp-1F8h]
  _OWORD v25[3]; // [rsp+60h] [rbp-1E8h] BYREF
  _OWORD v26[2]; // [rsp+90h] [rbp-1B8h]
  _QWORD v27[42]; // [rsp+B0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v27,
    "AuthenticateIdentification");
  v27[0] = &BioIsoProvider::AuthenticateIdentification::`vftable';
  BioIsoProvider::AuthenticateIdentification::StartActivity((BioIsoProvider::AuthenticateIdentification *)v27);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC15,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v19);
    BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification((BioIsoProvider::AuthenticateIdentification *)v27);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC16,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v19);
    BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification((BioIsoProvider::AuthenticateIdentification *)v27);
    return 2147942487LL;
  }
  *(_OWORD *)v22 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, v22);
  v13 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v19);
    if ( v22[1] )
      std::_Ref_count_base::_Decref(v22[1]);
LABEL_8:
    BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification((BioIsoProvider::AuthenticateIdentification *)v27);
    return v13;
  }
  v14 = SecureConnection::AuthenticateIdentification((std::_Ref_count_base *)((char *)v22[0] + 96), a5, a3, a4, a6, a7);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC21,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v14,
      v20);
    if ( v22[1] )
      std::_Ref_count_base::_Decref(v22[1]);
    goto LABEL_8;
  }
  std::make_unique<KeyReleaseAuthzContext,,0>(&v21);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Src);
  v15 = KeyReleaseAuthzContext::Add(v21, &a5->Value, 32, &Src);
  v16 = v15;
  if ( v15 >= 0 )
  {
    memset_0(v25, 0, 0x4Cu);
    LODWORD(v25[0]) = 3;
    v17 = v24 - (_DWORD)Src;
    if ( (unsigned __int64)(v24 - (_QWORD)Src) <= 0x44 )
    {
      memcpy_0((char *)v25 + 8, Src, v24 - (_QWORD)Src);
      DWORD1(v25[0]) = v17;
      *(_OWORD *)&a5->Type = v25[0];
      *(_OWORD *)&a5->Value.AccountSid.Data[8] = v25[1];
      *(_OWORD *)&a5->Value.AccountSid.Data[24] = v25[2];
      *(_OWORD *)&a5->Value.AccountSid.Data[40] = v26[0];
      *(_OWORD *)&a5->Value.AccountSid.Data[52] = *(_OWORD *)((char *)v26 + 12);
      v18 = v21;
      v21 = 0;
      *a2 = v18;
      HardwareManager::AddHandle(v18);
      wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v27, 0);
      std::vector<unsigned char>::_Tidy(&Src);
      std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(&v21);
      if ( v22[1] )
        std::_Ref_count_base::_Decref(v22[1]);
      BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification((BioIsoProvider::AuthenticateIdentification *)v27);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2F,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x8000FFFFLL,
        v20);
      std::vector<unsigned char>::_Tidy(&Src);
      std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(&v21);
      if ( v22[1] )
        std::_Ref_count_base::_Decref(v22[1]);
      BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification((BioIsoProvider::AuthenticateIdentification *)v27);
      return 2147549183LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC29,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v15,
      v20);
    std::vector<unsigned char>::_Tidy(&Src);
    std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(&v21);
    if ( v22[1] )
      std::_Ref_count_base::_Decref(v22[1]);
    BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification((BioIsoProvider::AuthenticateIdentification *)v27);
    return v16;
  }
}

```

## disassembly

```asm
0x140008c60  push    rbx
0x140008c62  push    rsi
0x140008c63  push    rdi
0x140008c64  push    r12
0x140008c66  push    r14
0x140008c68  push    r15
0x140008c6a  sub     rsp, 218h
0x140008c71  mov     rax, cs:__security_cookie
0x140008c78  xor     rax, rsp
0x140008c7b  mov     [rsp+248h+var_48], rax
0x140008c83  mov     r14d, r9d
0x140008c86  mov     rsi, r8
0x140008c89  mov     r12, rdx
0x140008c8c  mov     rbx, rcx
0x140008c8f  mov     rdi, [rsp+248h+arg_20]
0x140008c97  mov     r15, [rsp+248h+arg_28]
0x140008c9f  lea     rdx, aAuthenticateid; "AuthenticateIdentification"
0x140008ca6  lea     rcx, [rsp+248h+var_198]
0x140008cae  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140008cb3  lea     rax, ??_7AuthenticateIdentification@BioIsoProvider@@6B@; const BioIsoProvider::AuthenticateIdentification::`vftable'
0x140008cba  mov     [rsp+248h+var_198], rax
0x140008cc2  lea     rcx, [rsp+248h+var_198]; this
0x140008cca  call    ?StartActivity@AuthenticateIdentification@BioIsoProvider@@QEAAXXZ; BioIsoProvider::AuthenticateIdentification::StartActivity(void)
0x140008ccf  nop
0x140008cd0  test    rbx, rbx
0x140008cd3  jnz     short loc_140008D0B
0x140008cd5  mov     rcx, [rsp+248h]; this
0x140008cdd  mov     ebx, 80004003h
0x140008ce2  mov     r9d, ebx; char *
0x140008ce5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008cec  mov     edx, 0C15h; void *
0x140008cf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008cf6  nop
0x140008cf7  lea     rcx, [rsp+248h+var_198]; this
0x140008cff  call    ??1AuthenticateIdentification@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification(void)
0x140008d04  mov     eax, ebx
0x140008d06  jmp     loc_140008FD2
0x140008d0b  mov     rcx, rbx; void *
0x140008d0e  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140008d13  test    al, al
0x140008d15  jnz     short loc_140008D4D
0x140008d17  mov     rcx, [rsp+248h]; this
0x140008d1f  mov     ebx, 80070057h
0x140008d24  mov     r9d, ebx; char *
0x140008d27  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008d2e  mov     edx, 0C16h; void *
0x140008d33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008d38  nop
0x140008d39  lea     rcx, [rsp+248h+var_198]; this
0x140008d41  call    ??1AuthenticateIdentification@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification(void)
0x140008d46  mov     eax, ebx
0x140008d48  jmp     loc_140008FD2
0x140008d4d  xorps   xmm0, xmm0
0x140008d50  movdqu  xmmword ptr [rsp+248h+var_210], xmm0
0x140008d56  lea     rdx, [rsp+248h+var_210]
0x140008d5b  mov     ecx, [rbx]
0x140008d5d  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140008d62  mov     ebx, eax
0x140008d64  test    eax, eax
0x140008d66  jns     short loc_140008DA9
0x140008d68  mov     rcx, [rsp+248h]; this
0x140008d70  mov     r9d, eax; char *
0x140008d73  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008d7a  mov     edx, 0C1Ah; void *
0x140008d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008d84  nop
0x140008d85  mov     rcx, [rsp+248h+var_210+8]; this
0x140008d8a  test    rcx, rcx
0x140008d8d  jz      short loc_140008D95
0x140008d8f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008d94  nop
0x140008d95  lea     rcx, [rsp+248h+var_198]; this
0x140008d9d  call    ??1AuthenticateIdentification@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification(void)
0x140008da2  mov     eax, ebx
0x140008da4  jmp     loc_140008FD2
0x140008da9  mov     rcx, [rsp+248h+var_210]
0x140008dae  add     rcx, 60h ; '`'; this
0x140008db2  mov     eax, [rsp+248h+arg_30]
0x140008db9  mov     [rsp+248h+var_220], eax; unsigned int
0x140008dbd  mov     [rsp+248h+var_228], r15; int
0x140008dc2  mov     r9d, r14d; unsigned int
0x140008dc5  mov     r8, rsi; unsigned __int8 *
0x140008dc8  mov     rdx, rdi; struct _WINBIO_IDENTITY *
0x140008dcb  call    ?AuthenticateIdentification@SecureConnection@@QEAAJPEAU_WINBIO_IDENTITY@@PEBEK1K@Z; SecureConnection::AuthenticateIdentification(_WINBIO_IDENTITY *,uchar const *,ulong,uchar const *,ulong)
0x140008dd0  mov     ebx, eax
0x140008dd2  test    eax, eax
0x140008dd4  jns     short loc_140008E17
0x140008dd6  mov     rcx, [rsp+248h]; this
0x140008dde  mov     r9d, eax; char *
0x140008de1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008de8  mov     edx, 0C21h; void *
0x140008ded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008df2  nop
0x140008df3  mov     rcx, [rsp+248h+var_210+8]; this
0x140008df8  test    rcx, rcx
0x140008dfb  jz      short loc_140008E03
0x140008dfd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008e02  nop
0x140008e03  lea     rcx, [rsp+248h+var_198]; this
0x140008e0b  call    ??1AuthenticateIdentification@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification(void)
0x140008e10  mov     eax, ebx
0x140008e12  jmp     loc_140008FD2
0x140008e17  lea     rcx, [rsp+248h+var_218]
0x140008e1c  call    ??$make_unique@VKeyReleaseAuthzContext@@$$V$0A@@std@@YA?AV?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@0@XZ; std::make_unique<KeyReleaseAuthzContext,,0>(void)
0x140008e21  nop
0x140008e22  lea     rcx, [rsp+248h+Src]
0x140008e27  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140008e2c  nop
0x140008e2d  lea     rdx, [rdi+4]
0x140008e31  lea     r9, [rsp+248h+Src]
0x140008e36  mov     r8d, 20h ; ' '
0x140008e3c  mov     rcx, [rsp+248h+var_218]
0x140008e41  call    ?Add@KeyReleaseAuthzContext@@QEAAJPEBE_KPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; KeyReleaseAuthzContext::Add(uchar const *,unsigned __int64,std::vector<uchar> *)
0x140008e46  mov     ebx, eax
0x140008e48  test    eax, eax
0x140008e4a  jns     short loc_140008EA3
0x140008e4c  mov     rcx, [rsp+248h]; this
0x140008e54  mov     r9d, eax; char *
0x140008e57  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008e5e  mov     edx, 0C29h; void *
0x140008e63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008e68  nop
0x140008e69  lea     rcx, [rsp+248h+Src]
0x140008e6e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140008e73  nop
0x140008e74  lea     rcx, [rsp+248h+var_218]
0x140008e79  call    ??1?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(void)
0x140008e7e  nop
0x140008e7f  mov     rcx, [rsp+248h+var_210+8]; this
0x140008e84  test    rcx, rcx
0x140008e87  jz      short loc_140008E8F
0x140008e89  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008e8e  nop
0x140008e8f  lea     rcx, [rsp+248h+var_198]; this
0x140008e97  call    ??1AuthenticateIdentification@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification(void)
0x140008e9c  mov     eax, ebx
0x140008e9e  jmp     loc_140008FD2
0x140008ea3  xor     edx, edx; Val
0x140008ea5  lea     r8d, [rdx+4Ch]; Size
0x140008ea9  lea     rcx, [rsp+248h+var_1E8]; void *
0x140008eae  call    memset_0
0x140008eb3  mov     dword ptr [rsp+248h+var_1E8], 3
0x140008ebb  mov     rdx, [rsp+248h+Src]; Src
0x140008ec0  mov     rbx, [rsp+248h+var_1F8]
0x140008ec5  sub     rbx, rdx
0x140008ec8  cmp     rbx, 44h ; 'D'
0x140008ecc  jbe     short loc_140008F2A
0x140008ece  mov     rcx, [rsp+248h]; this
0x140008ed6  mov     ebx, 8000FFFFh
0x140008edb  mov     r9d, ebx; char *
0x140008ede  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008ee5  mov     edx, 0C2Fh; void *
0x140008eea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008eef  nop
0x140008ef0  lea     rcx, [rsp+248h+Src]
0x140008ef5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140008efa  nop
0x140008efb  lea     rcx, [rsp+248h+var_218]
0x140008f00  call    ??1?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(void)
0x140008f05  nop
0x140008f06  mov     rcx, [rsp+248h+var_210+8]; this
0x140008f0b  test    rcx, rcx
0x140008f0e  jz      short loc_140008F16
0x140008f10  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008f15  nop
0x140008f16  lea     rcx, [rsp+248h+var_198]; this
0x140008f1e  call    ??1AuthenticateIdentification@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification(void)
0x140008f23  mov     eax, ebx
0x140008f25  jmp     loc_140008FD2
0x140008f2a  mov     r8, rbx; Size
0x140008f2d  lea     rcx, [rsp+248h+var_1E8+8]; void *
0x140008f32  call    memcpy_0
0x140008f37  mov     dword ptr [rsp+248h+var_1E8+4], ebx
0x140008f3b  movaps  xmm0, [rsp+248h+var_1E8]
0x140008f40  movups  xmmword ptr [rdi], xmm0
0x140008f43  movaps  xmm1, [rsp+248h+var_1D8]
0x140008f48  movups  xmmword ptr [rdi+10h], xmm1
0x140008f4c  movaps  xmm0, [rsp+248h+var_1C8]
0x140008f54  movups  xmmword ptr [rdi+20h], xmm0
0x140008f58  movaps  xmm1, xmmword ptr [rsp+248h+var_1B8]
0x140008f60  movups  xmmword ptr [rdi+30h], xmm1
0x140008f64  movups  xmm0, xmmword ptr [rsp+248h+var_1B8+0Ch]
0x140008f6c  movups  xmmword ptr [rdi+3Ch], xmm0
0x140008f70  mov     rcx, [rsp+248h+var_218]; void *
0x140008f75  mov     [rsp+248h+var_218], 0
0x140008f7e  mov     [r12], rcx
0x140008f82  call    ?AddHandle@HardwareManager@@SAXQEAX@Z; HardwareManager::AddHandle(void * const)
0x140008f87  xor     edx, edx
0x140008f89  lea     rcx, [rsp+248h+var_198]
0x140008f91  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140008f96  nop
0x140008f97  lea     rcx, [rsp+248h+Src]
0x140008f9c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140008fa1  nop
0x140008fa2  lea     rcx, [rsp+248h+var_218]
0x140008fa7  call    ??1?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(void)
0x140008fac  nop
0x140008fad  mov     rcx, [rsp+248h+var_210+8]; this
0x140008fb2  test    rcx, rcx
0x140008fb5  jz      short loc_140008FBD
0x140008fb7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008fbc  nop
0x140008fbd  lea     rcx, [rsp+248h+var_198]; this
0x140008fc5  call    ??1AuthenticateIdentification@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateIdentification::~AuthenticateIdentification(void)
0x140008fca  xor     eax, eax
0x140008fcc  jmp     short loc_140008FD2
0x140008fce  mov     eax, dword ptr [rsp+248h+var_218]
0x140008fd2  mov     rcx, [rsp+248h+var_48]
0x140008fda  xor     rcx, rsp; StackCookie
0x140008fdd  call    __security_check_cookie
0x140008fe2  add     rsp, 218h
0x140008fe9  pop     r15
0x140008feb  pop     r14
0x140008fed  pop     r12
0x140008fef  pop     rdi
0x140008ff0  pop     rsi
0x140008ff1  pop     rbx
0x140008ff2  retn
```
