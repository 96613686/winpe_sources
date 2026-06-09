# BioIsoSrvEngineCommitEnrollment

- ea: `0x1400098b0`
- end: `0x140009c7a`
- name: `BioIsoSrvEngineCommitEnrollment`
- size: `970`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x1400098b0`
- `0x140009c80`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x14000ae0c`
- `0x14000d5d0`
- `0x140012974`
- `0x14001bd40`
- `0x140040d2c`
- `0x140043cf8`
- `0x140059830`
- `0x140061b30`
- `0x14006253c`
- `0x140085010`

## string_xrefs

- `0x140009923`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000995e`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400099a0`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400099ec`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140009ab1`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140009b87`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140009c20`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400098dd`: `EngineCommitEnrollment`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineCommitEnrollment(int *a1, _DWORD *a2, char a3, __int64 a4, int a5)
{
  int BiometricUnit; // eax
  __int64 v11; // r8
  int v12; // ebx
  std::_Ref_count_base *v13; // rsi
  __int64 v14; // rax
  __int64 (__fastcall *v15)(__int64, _DWORD *, __int64, __int64); // rax
  int EnrollmentId; // eax
  SecureEnrollmentDatabase *v17; // rax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-208h]
  int v20; // [rsp+20h] [rbp-208h]
  std::_Ref_count_base *v21[2]; // [rsp+78h] [rbp-1B0h] BYREF
  unsigned __int8 *v22[3]; // [rsp+88h] [rbp-1A0h] BYREF
  _QWORD v23[42]; // [rsp+A0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v23,
    (__int64)"EngineCommitEnrollment");
  v23[0] = &BioIsoProvider::EngineCommitEnrollment::`vftable';
  BioIsoProvider::EngineCommitEnrollment::StartActivity((BioIsoProvider::EngineCommitEnrollment *)v23);
  if ( *a2 != 3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F1,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v19);
    BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment((BioIsoProvider::EngineCommitEnrollment *)v23);
    return 2147942487LL;
  }
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F5,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v19);
    BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment((BioIsoProvider::EngineCommitEnrollment *)v23);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v19);
    BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment((BioIsoProvider::EngineCommitEnrollment *)v23);
    return 2147942487LL;
  }
  *(_OWORD *)v21 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v21);
  v12 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v19);
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
LABEL_30:
    BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment((BioIsoProvider::EngineCommitEnrollment *)v23);
    return (unsigned int)v12;
  }
  v13 = v21[0];
  if ( *((_QWORD *)v21[0] + 3) == -32 || (v14 = *(_QWORD *)(*((_QWORD *)v21[0] + 3) + 64LL)) == 0 )
  {
    v12 = -2147467261;
    goto LABEL_28;
  }
  v15 = *(__int64 (__fastcall **)(__int64, _DWORD *, __int64, __int64))(v14 + 168);
  if ( !v15 )
  {
    v12 = -2147467263;
    goto LABEL_28;
  }
  v19 = a5;
  LOBYTE(v11) = a3;
  v12 = v15(*((_QWORD *)v21[0] + 3) + 32LL, a2, v11, a4);
  if ( v12 < 0 )
  {
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v12,
      v19);
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
    goto LABEL_30;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v22);
  EnrollmentId = GenerateEnrollmentId(*((_DWORD *)v13 + 5), (__int64)a2, (__int64)v22);
  v12 = EnrollmentId;
  if ( EnrollmentId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x405,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)EnrollmentId,
      a5);
    std::vector<unsigned char>::_Tidy((__int64)v22);
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
    goto LABEL_30;
  }
  v17 = SecureEnrollmentDatabase::Instance();
  v18 = SecureEnrollmentDatabase::StageEnrollment(v17, v22[0], v22[1] - v22[0], a2 + 2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
  v12 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v18,
      v20);
    std::vector<unsigned char>::_Tidy((__int64)v22);
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
    goto LABEL_30;
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v23, 0);
  std::vector<unsigned char>::_Tidy((__int64)v22);
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
  BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment((BioIsoProvider::EngineCommitEnrollment *)v23);
  return 0;
}

```

## disassembly

```asm
0x1400098b0  push    rbx
0x1400098b2  push    rsi
0x1400098b3  push    rdi
0x1400098b4  push    r14
0x1400098b6  push    r15
0x1400098b8  sub     rsp, 200h
0x1400098bf  mov     rax, cs:__security_cookie
0x1400098c6  xor     rax, rsp
0x1400098c9  mov     [rsp+228h+var_38], rax
0x1400098d1  mov     r15, r9
0x1400098d4  mov     r14b, r8b
0x1400098d7  mov     rdi, rdx
0x1400098da  mov     rbx, rcx
0x1400098dd  lea     rdx, aEnginecommiten; "EngineCommitEnrollment"
0x1400098e4  lea     rcx, [rsp+228h+var_188]
0x1400098ec  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400098f1  lea     rax, ??_7EngineCommitEnrollment@BioIsoProvider@@6B@; const BioIsoProvider::EngineCommitEnrollment::`vftable'
0x1400098f8  mov     [rsp+228h+var_188], rax
0x140009900  lea     rcx, [rsp+228h+var_188]; this
0x140009908  call    ?StartActivity@EngineCommitEnrollment@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineCommitEnrollment::StartActivity(void)
0x14000990d  nop
0x14000990e  cmp     dword ptr [rdi], 3
0x140009911  jz      short loc_140009949
0x140009913  mov     rcx, [rsp+228h]; this
0x14000991b  mov     ebx, 80070057h
0x140009920  mov     r9d, ebx; char *
0x140009923  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000992a  mov     edx, 3F1h; void *
0x14000992f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009934  nop
0x140009935  lea     rcx, [rsp+228h+var_188]; this
0x14000993d  call    ??1EngineCommitEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment(void)
0x140009942  mov     eax, ebx
0x140009944  jmp     loc_140009C5A
0x140009949  test    rbx, rbx
0x14000994c  jnz     short loc_140009984
0x14000994e  mov     rcx, [rsp+228h]; this
0x140009956  mov     ebx, 80004003h
0x14000995b  mov     r9d, ebx; char *
0x14000995e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009965  mov     edx, 3F5h; void *
0x14000996a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000996f  nop
0x140009970  lea     rcx, [rsp+228h+var_188]; this
0x140009978  call    ??1EngineCommitEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment(void)
0x14000997d  mov     eax, ebx
0x14000997f  jmp     loc_140009C5A
0x140009984  mov     rcx, rbx; void *
0x140009987  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14000998c  test    al, al
0x14000998e  jnz     short loc_1400099C6
0x140009990  mov     rcx, [rsp+228h]; this
0x140009998  mov     ebx, 80070057h
0x14000999d  mov     r9d, ebx; char *
0x1400099a0  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400099a7  mov     edx, 3F6h; void *
0x1400099ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400099b1  nop
0x1400099b2  lea     rcx, [rsp+228h+var_188]; this
0x1400099ba  call    ??1EngineCommitEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment(void)
0x1400099bf  mov     eax, ebx
0x1400099c1  jmp     loc_140009C5A
0x1400099c6  xorps   xmm0, xmm0
0x1400099c9  movdqu  xmmword ptr [rsp+228h+var_1B0], xmm0
0x1400099cf  lea     rdx, [rsp+228h+var_1B0]
0x1400099d4  mov     ecx, [rbx]
0x1400099d6  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x1400099db  mov     ebx, eax
0x1400099dd  test    eax, eax
0x1400099df  jns     short loc_140009A25
0x1400099e1  mov     rcx, [rsp+228h]; this
0x1400099e9  mov     r9d, eax; char *
0x1400099ec  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400099f3  mov     edx, 3FBh; void *
0x1400099f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400099fd  nop
0x1400099fe  mov     rcx, [rsp+228h+var_1B0+8]; this
0x140009a06  test    rcx, rcx
0x140009a09  jz      short loc_140009A11
0x140009a0b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009a10  nop
0x140009a11  lea     rcx, [rsp+228h+var_188]; this
0x140009a19  call    ??1EngineCommitEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment(void)
0x140009a1e  mov     eax, ebx
0x140009a20  jmp     loc_140009C5A
0x140009a25  mov     rsi, [rsp+228h+var_1B0]
0x140009a2a  mov     rcx, [rsi+18h]
0x140009a2e  add     rcx, 20h ; ' '
0x140009a32  jz      loc_140009C10
0x140009a38  mov     rax, [rcx+20h]
0x140009a3c  test    rax, rax
0x140009a3f  jz      loc_140009C10
0x140009a45  mov     rax, [rax+0A8h]
0x140009a4c  test    rax, rax
0x140009a4f  jnz     short loc_140009A5B
0x140009a51  mov     ebx, 80004001h
0x140009a56  jmp     loc_140009C15
0x140009a5b  mov     edx, [rsp+228h+arg_20]
0x140009a62  mov     [rsp+228h+var_208], rdx; int
0x140009a67  mov     r9, r15
0x140009a6a  mov     r8b, r14b
0x140009a6d  mov     rdx, rdi
0x140009a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a75  mov     ebx, eax
0x140009a77  test    eax, eax
0x140009a79  js      loc_140009C15
0x140009a7f  lea     rcx, [rsp+228h+var_1A0]
0x140009a87  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140009a8c  nop
0x140009a8d  lea     r8, [rsp+228h+var_1A0]
0x140009a95  mov     rdx, rdi
0x140009a98  mov     ecx, [rsi+14h]
0x140009a9b  call    ?GenerateEnrollmentId@@YAJIPEBU_WINBIO_IDENTITY@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; GenerateEnrollmentId(uint,_WINBIO_IDENTITY const *,std::vector<uchar> *)
0x140009aa0  mov     ebx, eax
0x140009aa2  test    eax, eax
0x140009aa4  jns     short loc_140009AF8
0x140009aa6  mov     rcx, [rsp+228h]; this
0x140009aae  mov     r9d, eax; char *
0x140009ab1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009ab8  mov     edx, 405h; void *
0x140009abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009ac2  nop
0x140009ac3  lea     rcx, [rsp+228h+var_1A0]
0x140009acb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140009ad0  nop
0x140009ad1  mov     rcx, [rsp+228h+var_1B0+8]; this
0x140009ad9  test    rcx, rcx
0x140009adc  jz      short loc_140009AE4
0x140009ade  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009ae3  nop
0x140009ae4  lea     rcx, [rsp+228h+var_188]; this
0x140009aec  call    ??1EngineCommitEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment(void)
0x140009af1  mov     eax, ebx
0x140009af3  jmp     loc_140009C5A
0x140009af8  call    ?Instance@SecureEnrollmentDatabase@@SAAEAV1@XZ; SecureEnrollmentDatabase::Instance(void)
0x140009afd  lea     r9, [rdi+8]; void *
0x140009b01  mov     r8, [rsp+228h+var_198]
0x140009b09  mov     rdx, [rsp+228h+var_1A0]; unsigned __int8 *
0x140009b11  sub     r8, rdx; unsigned __int64
0x140009b14  mov     [rsp+228h+var_1C0], 0; unsigned __int64
0x140009b1d  mov     [rsp+228h+var_1C8], 0; unsigned __int8 *
0x140009b26  mov     [rsp+228h+var_1D0], 0; unsigned __int64
0x140009b2f  mov     [rsp+228h+var_1D8], 0; unsigned __int8 *
0x140009b38  mov     [rsp+228h+var_1E0], 0; unsigned __int64
0x140009b41  mov     [rsp+228h+var_1E8], 0; unsigned __int8 *
0x140009b4a  mov     [rsp+228h+var_1F0], 0; unsigned __int64
0x140009b53  mov     [rsp+228h+var_1F8], 0; unsigned __int8 *
0x140009b5c  mov     [rsp+228h+var_200], 0; unsigned __int64
0x140009b65  mov     [rsp+228h+var_208], 0; int
0x140009b6e  mov     rcx, rax; this
0x140009b71  call    ?StageEnrollment@SecureEnrollmentDatabase@@QEAAJPEBE_KQEAX0101010101@Z; SecureEnrollmentDatabase::StageEnrollment(uchar const *,unsigned __int64,void * const,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64)
0x140009b76  mov     ebx, eax
0x140009b78  test    eax, eax
0x140009b7a  jns     short loc_140009BCE
0x140009b7c  mov     rcx, [rsp+228h]; this
0x140009b84  mov     r9d, eax; char *
0x140009b87  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009b8e  mov     edx, 40Eh; void *
0x140009b93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009b98  nop
0x140009b99  lea     rcx, [rsp+228h+var_1A0]
0x140009ba1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140009ba6  nop
0x140009ba7  mov     rcx, [rsp+228h+var_1B0+8]; this
0x140009baf  test    rcx, rcx
0x140009bb2  jz      short loc_140009BBA
0x140009bb4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009bb9  nop
0x140009bba  lea     rcx, [rsp+228h+var_188]; this
0x140009bc2  call    ??1EngineCommitEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment(void)
0x140009bc7  mov     eax, ebx
0x140009bc9  jmp     loc_140009C5A
0x140009bce  xor     edx, edx
0x140009bd0  lea     rcx, [rsp+228h+var_188]
0x140009bd8  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140009bdd  nop
0x140009bde  lea     rcx, [rsp+228h+var_1A0]
0x140009be6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140009beb  nop
0x140009bec  mov     rcx, [rsp+228h+var_1B0+8]; this
0x140009bf4  test    rcx, rcx
0x140009bf7  jz      short loc_140009BFF
0x140009bf9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009bfe  nop
0x140009bff  lea     rcx, [rsp+228h+var_188]; this
0x140009c07  call    ??1EngineCommitEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment(void)
0x140009c0c  xor     eax, eax
0x140009c0e  jmp     short loc_140009C5A
0x140009c10  mov     ebx, 80004003h
0x140009c15  mov     rcx, [rsp+228h]; this
0x140009c1d  mov     r9d, ebx; char *
0x140009c20  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009c27  mov     edx, 3FEh; void *
0x140009c2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009c31  nop
0x140009c32  mov     rcx, [rsp+228h+var_1B0+8]; this
0x140009c3a  test    rcx, rcx
0x140009c3d  jz      short loc_140009C45
0x140009c3f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009c44  nop
0x140009c45  lea     rcx, [rsp+228h+var_188]; this
0x140009c4d  call    ??1EngineCommitEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineCommitEnrollment::~EngineCommitEnrollment(void)
0x140009c52  mov     eax, ebx
0x140009c54  jmp     short loc_140009C5A
0x140009c56  mov     eax, [rsp+228h+var_1B8]
0x140009c5a  mov     rcx, [rsp+228h+var_38]
0x140009c62  xor     rcx, rsp; StackCookie
0x140009c65  call    __security_check_cookie
0x140009c6a  add     rsp, 200h
0x140009c71  pop     r15
0x140009c73  pop     r14
0x140009c75  pop     rdi
0x140009c76  pop     rsi
0x140009c77  pop     rbx
0x140009c78  retn
```
