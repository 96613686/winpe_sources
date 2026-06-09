# BioIsoSrvAuthenticateEnrollmentIdentity

- ea: `0x140009cb0`
- end: `0x14000a00c`
- name: `BioIsoSrvAuthenticateEnrollmentIdentity`
- size: `860`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x140009cb0`
- `0x14000a014`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x14001bd40`
- `0x140040d2c`
- `0x140043098`
- `0x140059830`
- `0x14005d350`
- `0x14006253c`

## string_xrefs

- `0x140009d23`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140009d65`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140009db1`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140009dff`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140009e9b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140009f7e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvAuthenticateEnrollmentIdentity(
        int *a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        __int64 a4)
{
  int BiometricUnit; // eax
  unsigned int v10; // ebx
  std::_Ref_count_base *v11; // r14
  int v12; // eax
  SecureEnrollmentDatabase *v13; // rax
  int v14; // eax
  int v15; // [rsp+20h] [rbp-248h]
  int v16; // [rsp+20h] [rbp-248h]
  std::_Ref_count_base *v17[2]; // [rsp+78h] [rbp-1F0h] BYREF
  _OWORD v18[3]; // [rsp+90h] [rbp-1D8h] BYREF
  _OWORD v19[2]; // [rsp+C0h] [rbp-1A8h]
  _QWORD v20[42]; // [rsp+E0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v20,
    (__int64)"AuthenticateEnrollmentIdentity");
  v20[0] = &BioIsoProvider::AuthenticateEnrollmentIdentity::`vftable';
  BioIsoProvider::AuthenticateEnrollmentIdentity::StartActivity((BioIsoProvider::AuthenticateEnrollmentIdentity *)v20);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC9,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v15);
    BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity((BioIsoProvider::AuthenticateEnrollmentIdentity *)v20);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBCA,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v15);
    BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity((BioIsoProvider::AuthenticateEnrollmentIdentity *)v20);
    return 2147942487LL;
  }
  *(_OWORD *)v17 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v17);
  v10 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBCE,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v15);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
LABEL_20:
    BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity((BioIsoProvider::AuthenticateEnrollmentIdentity *)v20);
    return v10;
  }
  if ( *(_DWORD *)a4 == 3 )
  {
    v18[0] = *(_OWORD *)a4;
    v18[1] = *(_OWORD *)(a4 + 16);
    v18[2] = *(_OWORD *)(a4 + 32);
    v19[0] = *(_OWORD *)(a4 + 48);
    *(_OWORD *)((char *)v19 + 12) = *(_OWORD *)(a4 + 60);
    v11 = v17[0];
    v12 = SecureConnection::AuthenticateEnrollmentIdentity(
            (std::_Ref_count_base *)((char *)v17[0] + 96),
            a2,
            a3,
            (struct _WINBIO_IDENTITY *)a4);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBDE,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)v12,
        v15);
      if ( v17[1] )
        std::_Ref_count_base::_Decref(v17[1]);
      goto LABEL_20;
    }
    v13 = SecureEnrollmentDatabase::Instance();
    v14 = SecureEnrollmentDatabase::StageEnrollment(
            v13,
            (const unsigned __int8 *)(a4 + 4),
            0x20u,
            (char *)v18 + 8,
            *((const unsigned __int8 **)v11 + 37),
            *((_QWORD *)v11 + 38) - *((_QWORD *)v11 + 37),
            (const unsigned __int8 *)v11 + 368,
            0x41u,
            (const unsigned __int8 *)v11 + 433,
            0x20u,
            *((const unsigned __int8 **)v11 + 40),
            *((_QWORD *)v11 + 41) - *((_QWORD *)v11 + 40),
            *((const unsigned __int8 **)v11 + 43),
            *((_QWORD *)v11 + 44) - *((_QWORD *)v11 + 43));
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBEE,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)v14,
        v16);
      if ( v17[1] )
        std::_Ref_count_base::_Decref(v17[1]);
      goto LABEL_20;
    }
    wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20, 0);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
    BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity((BioIsoProvider::AuthenticateEnrollmentIdentity *)v20);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v15);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
    BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity((BioIsoProvider::AuthenticateEnrollmentIdentity *)v20);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140009cb0  push    rbx
0x140009cb2  push    rsi
0x140009cb3  push    rdi
0x140009cb4  push    r14
0x140009cb6  push    r15
0x140009cb8  sub     rsp, 240h
0x140009cbf  mov     rax, cs:__security_cookie
0x140009cc6  xor     rax, rsp
0x140009cc9  mov     [rsp+268h+var_38], rax
0x140009cd1  mov     rsi, r9
0x140009cd4  mov     r15d, r8d
0x140009cd7  mov     rdi, rdx
0x140009cda  mov     rbx, rcx
0x140009cdd  lea     rdx, aAuthenticateen; "AuthenticateEnrollmentIdentity"
0x140009ce4  lea     rcx, [rsp+268h+var_188]
0x140009cec  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140009cf1  lea     rax, ??_7AuthenticateEnrollmentIdentity@BioIsoProvider@@6B@; const BioIsoProvider::AuthenticateEnrollmentIdentity::`vftable'
0x140009cf8  mov     [rsp+268h+var_188], rax
0x140009d00  lea     rcx, [rsp+268h+var_188]; this
0x140009d08  call    ?StartActivity@AuthenticateEnrollmentIdentity@BioIsoProvider@@QEAAXXZ; BioIsoProvider::AuthenticateEnrollmentIdentity::StartActivity(void)
0x140009d0d  nop
0x140009d0e  test    rbx, rbx
0x140009d11  jnz     short loc_140009D49
0x140009d13  mov     rcx, [rsp+268h]; this
0x140009d1b  mov     ebx, 80004003h
0x140009d20  mov     r9d, ebx; char *
0x140009d23  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009d2a  mov     edx, 0BC9h; void *
0x140009d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009d34  nop
0x140009d35  lea     rcx, [rsp+268h+var_188]; this
0x140009d3d  call    ??1AuthenticateEnrollmentIdentity@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity(void)
0x140009d42  mov     eax, ebx
0x140009d44  jmp     loc_140009FEC
0x140009d49  mov     rcx, rbx; void *
0x140009d4c  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140009d51  test    al, al
0x140009d53  jnz     short loc_140009D8B
0x140009d55  mov     rcx, [rsp+268h]; this
0x140009d5d  mov     ebx, 80070057h
0x140009d62  mov     r9d, ebx; char *
0x140009d65  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009d6c  mov     edx, 0BCAh; void *
0x140009d71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009d76  nop
0x140009d77  lea     rcx, [rsp+268h+var_188]; this
0x140009d7f  call    ??1AuthenticateEnrollmentIdentity@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity(void)
0x140009d84  mov     eax, ebx
0x140009d86  jmp     loc_140009FEC
0x140009d8b  xorps   xmm0, xmm0
0x140009d8e  movdqu  xmmword ptr [rsp+268h+var_1F0], xmm0
0x140009d94  lea     rdx, [rsp+268h+var_1F0]
0x140009d99  mov     ecx, [rbx]
0x140009d9b  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140009da0  mov     ebx, eax
0x140009da2  test    eax, eax
0x140009da4  jns     short loc_140009DEA
0x140009da6  mov     rcx, [rsp+268h]; this
0x140009dae  mov     r9d, eax; char *
0x140009db1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009db8  mov     edx, 0BCEh; void *
0x140009dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009dc2  nop
0x140009dc3  mov     rcx, [rsp+268h+var_1F0+8]; this
0x140009dcb  test    rcx, rcx
0x140009dce  jz      short loc_140009DD6
0x140009dd0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009dd5  nop
0x140009dd6  lea     rcx, [rsp+268h+var_188]; this
0x140009dde  call    ??1AuthenticateEnrollmentIdentity@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity(void)
0x140009de3  mov     eax, ebx
0x140009de5  jmp     loc_140009FEC
0x140009dea  cmp     dword ptr [rsi], 3
0x140009ded  jz      short loc_140009E38
0x140009def  mov     rcx, [rsp+268h]; this
0x140009df7  mov     ebx, 80070057h
0x140009dfc  mov     r9d, ebx; char *
0x140009dff  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009e06  mov     edx, 0BD7h; void *
0x140009e0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009e10  nop
0x140009e11  mov     rcx, [rsp+268h+var_1F0+8]; this
0x140009e19  test    rcx, rcx
0x140009e1c  jz      short loc_140009E24
0x140009e1e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009e23  nop
0x140009e24  lea     rcx, [rsp+268h+var_188]; this
0x140009e2c  call    ??1AuthenticateEnrollmentIdentity@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity(void)
0x140009e31  mov     eax, ebx
0x140009e33  jmp     loc_140009FEC
0x140009e38  movups  xmm0, xmmword ptr [rsi]
0x140009e3b  movaps  [rsp+268h+var_1D8], xmm0
0x140009e43  movups  xmm1, xmmword ptr [rsi+10h]
0x140009e47  movaps  [rsp+268h+var_1C8], xmm1
0x140009e4f  movups  xmm0, xmmword ptr [rsi+20h]
0x140009e53  movaps  [rsp+268h+var_1B8], xmm0
0x140009e5b  movups  xmm1, xmmword ptr [rsi+30h]
0x140009e5f  movaps  xmmword ptr [rsp+268h+var_1A8], xmm1
0x140009e67  movups  xmm0, xmmword ptr [rsi+3Ch]
0x140009e6b  movups  xmmword ptr [rsp+268h+var_1A8+0Ch], xmm0
0x140009e73  mov     r14, [rsp+268h+var_1F0]
0x140009e78  mov     r9, rsi; struct _WINBIO_IDENTITY *
0x140009e7b  mov     r8d, r15d; unsigned int
0x140009e7e  mov     rdx, rdi; unsigned __int8 *
0x140009e81  lea     rcx, [r14+60h]; this
0x140009e85  call    ?AuthenticateEnrollmentIdentity@SecureConnection@@QEAAJPEBEKPEAU_WINBIO_IDENTITY@@@Z; SecureConnection::AuthenticateEnrollmentIdentity(uchar const *,ulong,_WINBIO_IDENTITY *)
0x140009e8a  mov     ebx, eax
0x140009e8c  test    eax, eax
0x140009e8e  jns     short loc_140009ED4
0x140009e90  mov     rcx, [rsp+268h]; this
0x140009e98  mov     r9d, eax; char *
0x140009e9b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009ea2  mov     edx, 0BDEh; void *
0x140009ea7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009eac  nop
0x140009ead  mov     rcx, [rsp+268h+var_1F0+8]; this
0x140009eb5  test    rcx, rcx
0x140009eb8  jz      short loc_140009EC0
0x140009eba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009ebf  nop
0x140009ec0  lea     rcx, [rsp+268h+var_188]; this
0x140009ec8  call    ??1AuthenticateEnrollmentIdentity@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity(void)
0x140009ecd  mov     eax, ebx
0x140009ecf  jmp     loc_140009FEC
0x140009ed4  call    ?Instance@SecureEnrollmentDatabase@@SAAEAV1@XZ; SecureEnrollmentDatabase::Instance(void)
0x140009ed9  mov     r15, rax
0x140009edc  mov     r11, [r14+158h]
0x140009ee3  mov     rbx, [r14+140h]
0x140009eea  mov     rdi, [r14+128h]
0x140009ef1  mov     rcx, [r14+160h]
0x140009ef8  sub     rcx, r11
0x140009efb  mov     r8, [r14+148h]
0x140009f02  sub     r8, rbx
0x140009f05  lea     r9, [r14+1B1h]
0x140009f0c  lea     r10, [r14+170h]
0x140009f13  mov     rax, [r14+130h]
0x140009f1a  sub     rax, rdi
0x140009f1d  lea     rdx, [rsi+4]; unsigned __int8 *
0x140009f21  mov     [rsp+268h+var_200], rcx; unsigned __int64
0x140009f26  mov     [rsp+268h+var_208], r11; unsigned __int8 *
0x140009f2b  mov     [rsp+268h+var_210], r8; unsigned __int64
0x140009f30  mov     [rsp+268h+var_218], rbx; unsigned __int8 *
0x140009f35  mov     r8d, 20h ; ' '; unsigned __int64
0x140009f3b  mov     [rsp+268h+var_220], r8; unsigned __int64
0x140009f40  mov     [rsp+268h+var_228], r9; unsigned __int8 *
0x140009f45  mov     [rsp+268h+var_230], 41h ; 'A'; unsigned __int64
0x140009f4e  mov     [rsp+268h+var_238], r10; unsigned __int8 *
0x140009f53  mov     [rsp+268h+var_240], rax; unsigned __int64
0x140009f58  mov     [rsp+268h+var_248], rdi; int
0x140009f5d  lea     r9, [rsp+268h+var_1D8+8]; void *
0x140009f65  mov     rcx, r15; this
0x140009f68  call    ?StageEnrollment@SecureEnrollmentDatabase@@QEAAJPEBE_KQEAX0101010101@Z; SecureEnrollmentDatabase::StageEnrollment(uchar const *,unsigned __int64,void * const,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64)
0x140009f6d  mov     ebx, eax
0x140009f6f  test    eax, eax
0x140009f71  jns     short loc_140009FB4
0x140009f73  mov     rcx, [rsp+268h]; this
0x140009f7b  mov     r9d, eax; char *
0x140009f7e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009f85  mov     edx, 0BEEh; void *
0x140009f8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009f8f  nop
0x140009f90  mov     rcx, [rsp+268h+var_1F0+8]; this
0x140009f98  test    rcx, rcx
0x140009f9b  jz      short loc_140009FA3
0x140009f9d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009fa2  nop
0x140009fa3  lea     rcx, [rsp+268h+var_188]; this
0x140009fab  call    ??1AuthenticateEnrollmentIdentity@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity(void)
0x140009fb0  mov     eax, ebx
0x140009fb2  jmp     short loc_140009FEC
0x140009fb4  xor     edx, edx
0x140009fb6  lea     rcx, [rsp+268h+var_188]
0x140009fbe  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140009fc3  nop
0x140009fc4  mov     rcx, [rsp+268h+var_1F0+8]; this
0x140009fcc  test    rcx, rcx
0x140009fcf  jz      short loc_140009FD7
0x140009fd1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009fd6  nop
0x140009fd7  lea     rcx, [rsp+268h+var_188]; this
0x140009fdf  call    ??1AuthenticateEnrollmentIdentity@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthenticateEnrollmentIdentity::~AuthenticateEnrollmentIdentity(void)
0x140009fe4  xor     eax, eax
0x140009fe6  jmp     short loc_140009FEC
0x140009fe8  mov     eax, [rsp+268h+var_1F8]
0x140009fec  mov     rcx, [rsp+268h+var_38]
0x140009ff4  xor     rcx, rsp; StackCookie
0x140009ff7  call    __security_check_cookie
0x140009ffc  add     rsp, 240h
0x14000a003  pop     r15
0x14000a005  pop     r14
0x14000a007  pop     rdi
0x14000a008  pop     rsi
0x14000a009  pop     rbx
0x14000a00a  retn
```
