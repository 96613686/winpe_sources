# BioIsoSrvStorageOpenDatabase

- ea: `0x140057340`
- end: `0x1400575ca`
- name: `BioIsoSrvStorageOpenDatabase`
- size: `650`
- prototype: `__int64 __fastcall(void *, PWINBIO_UUID DatabaseId, LPCWSTR FilePath, LPCWSTR ConnectString)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140017780`
- `0x14001bd40`
- `0x1400412e4`
- `0x1400416dc`
- `0x1400419a4`
- `0x140041cf4`
- `0x140042eb0`
- `0x1400450a8`
- `0x140057340`
- `0x1400575d0`
- `0x140059830`

## string_xrefs

- `0x1400573a8`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400573e7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14005743d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400574bb`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14005754f`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14005736b`: `OpenDatabase`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvStorageOpenDatabase(
        int *a1,
        PWINBIO_UUID DatabaseId,
        LPCWSTR FilePath,
        LPCWSTR ConnectString)
{
  int BiometricUnit; // eax
  unsigned int v10; // ebx
  char v11; // al
  const WCHAR *v12; // r8
  const WCHAR *v13; // r9
  __int64 v14; // rcx
  HRESULT v15; // eax
  HRESULT v16; // eax
  std::_Ref_count_base *v17[2]; // [rsp+20h] [rbp-1A8h] BYREF
  _QWORD v18[42]; // [rsp+40h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "OpenDatabase");
  v18[0] = &BioIsoProvider::OpenDatabase::`vftable';
  BioIsoProvider::OpenDatabase::StartActivity((BioIsoProvider::OpenDatabase *)v18);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      (int)v17[0]);
    BioIsoProvider::OpenDatabase::~OpenDatabase((BioIsoProvider::OpenDatabase *)v18);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      (int)v17[0]);
    BioIsoProvider::OpenDatabase::~OpenDatabase((BioIsoProvider::OpenDatabase *)v18);
    return 2147942487LL;
  }
  BioIsoProvider::OpenDatabase::UnitId<unsigned long &>((__int64)v18, a1);
  *(_OWORD *)v17 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v17);
  v10 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x692,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      (int)v17[0]);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
LABEL_30:
    BioIsoProvider::OpenDatabase::~OpenDatabase((BioIsoProvider::OpenDatabase *)v18);
    return v10;
  }
  v11 = VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>>();
  v12 = (const WCHAR *)&dword_14008BB54;
  v13 = (const WCHAR *)&dword_14008BB54;
  v14 = *((_QWORD *)v17[0] + 3);
  if ( v11 )
  {
    if ( ConnectString )
      v13 = ConnectString;
    if ( FilePath )
      v12 = FilePath;
    v15 = WbioStorageOpenDatabase((PWINBIO_PIPELINE)(v14 + 32), DatabaseId, v12, v13);
    v10 = v15;
    if ( v15 >= 0 )
    {
      if ( v15 == 589827 )
        BioIsoProvider::ShouldReencrypt();
      wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18);
      if ( v17[1] )
        std::_Ref_count_base::_Decref(v17[1]);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69B,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)v15,
        (int)v17[0]);
      if ( v17[1] )
        std::_Ref_count_base::_Decref(v17[1]);
    }
    goto LABEL_30;
  }
  if ( ConnectString )
    v13 = ConnectString;
  if ( FilePath )
    v12 = FilePath;
  v16 = WbioStorageOpenDatabase((PWINBIO_PIPELINE)(v14 + 32), DatabaseId, v12, v13);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AC,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v16,
      (int)v17[0]);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
    goto LABEL_30;
  }
  wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18);
  if ( v17[1] )
    std::_Ref_count_base::_Decref(v17[1]);
  BioIsoProvider::OpenDatabase::~OpenDatabase((BioIsoProvider::OpenDatabase *)v18);
  return 0;
}

```

## disassembly

```asm
0x140057340  push    rbx
0x140057342  push    rsi
0x140057343  push    rdi
0x140057344  push    r14
0x140057346  sub     rsp, 1A8h
0x14005734d  mov     rax, cs:__security_cookie
0x140057354  xor     rax, rsp
0x140057357  mov     [rsp+1C8h+var_38], rax
0x14005735f  mov     rdi, r9
0x140057362  mov     rsi, r8
0x140057365  mov     r14, rdx
0x140057368  mov     rbx, rcx
0x14005736b  lea     rdx, aOpendatabase; "OpenDatabase"
0x140057372  lea     rcx, [rsp+1C8h+var_188]
0x140057377  call    ??0?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14005737c  lea     rax, ??_7OpenDatabase@BioIsoProvider@@6B@; const BioIsoProvider::OpenDatabase::`vftable'
0x140057383  mov     [rsp+1C8h+var_188], rax
0x140057388  lea     rcx, [rsp+1C8h+var_188]; this
0x14005738d  call    ?StartActivity@OpenDatabase@BioIsoProvider@@QEAAXXZ; BioIsoProvider::OpenDatabase::StartActivity(void)
0x140057392  nop
0x140057393  test    rbx, rbx
0x140057396  jnz     short loc_1400573CB
0x140057398  mov     rcx, [rsp+1C8h]; this
0x1400573a0  mov     ebx, 80004003h
0x1400573a5  mov     r9d, ebx; char *
0x1400573a8  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400573af  mov     edx, 68Bh; void *
0x1400573b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400573b9  nop
0x1400573ba  lea     rcx, [rsp+1C8h+var_188]; this
0x1400573bf  call    ??1OpenDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenDatabase::~OpenDatabase(void)
0x1400573c4  mov     eax, ebx
0x1400573c6  jmp     loc_1400575AC
0x1400573cb  mov     rcx, rbx; void *
0x1400573ce  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400573d3  test    al, al
0x1400573d5  jnz     short loc_14005740A
0x1400573d7  mov     rcx, [rsp+1C8h]; this
0x1400573df  mov     ebx, 80070057h
0x1400573e4  mov     r9d, ebx; char *
0x1400573e7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400573ee  mov     edx, 68Ch; void *
0x1400573f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400573f8  nop
0x1400573f9  lea     rcx, [rsp+1C8h+var_188]; this
0x1400573fe  call    ??1OpenDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenDatabase::~OpenDatabase(void)
0x140057403  mov     eax, ebx
0x140057405  jmp     loc_1400575AC
0x14005740a  mov     rdx, rbx
0x14005740d  lea     rcx, [rsp+1C8h+var_188]
0x140057412  call    ??$UnitId@AEAK@OpenDatabase@BioIsoProvider@@QEAAXAEAK@Z; BioIsoProvider::OpenDatabase::UnitId<ulong &>(ulong &)
0x140057417  xorps   xmm0, xmm0
0x14005741a  movdqu  xmmword ptr [rsp+1C8h+var_1A8], xmm0; int
0x140057420  lea     rdx, [rsp+1C8h+var_1A8]
0x140057425  mov     ecx, [rbx]
0x140057427  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14005742c  mov     ebx, eax
0x14005742e  test    eax, eax
0x140057430  jns     short loc_140057470
0x140057432  mov     rcx, [rsp+1C8h]; this
0x14005743a  mov     r9d, eax; char *
0x14005743d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140057444  mov     edx, 692h; void *
0x140057449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005744e  nop
0x14005744f  mov     rcx, [rsp+1C8h+var_1A8+8]; this
0x140057454  test    rcx, rcx
0x140057457  jz      short loc_14005745F
0x140057459  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14005745e  nop
0x14005745f  lea     rcx, [rsp+1C8h+var_188]; this
0x140057464  call    ??1OpenDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenDatabase::~OpenDatabase(void)
0x140057469  mov     eax, ebx
0x14005746b  jmp     loc_1400575AC
0x140057470  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>>(void)
0x140057475  lea     r8, dword_14008BB54
0x14005747c  mov     rdx, r14; DatabaseId
0x14005747f  mov     r9, r8
0x140057482  test    al, al
0x140057484  mov     rax, [rsp+1C8h+var_1A8]
0x140057489  mov     rcx, [rax+18h]
0x14005748d  jz      loc_140057527
0x140057493  test    rdi, rdi
0x140057496  cmovnz  r9, rdi; ConnectString
0x14005749a  test    rsi, rsi
0x14005749d  cmovnz  r8, rsi; FilePath
0x1400574a1  add     rcx, 20h ; ' '; Pipeline
0x1400574a5  call    WbioStorageOpenDatabase
0x1400574aa  mov     ebx, eax
0x1400574ac  test    eax, eax
0x1400574ae  jns     short loc_1400574EE
0x1400574b0  mov     rcx, [rsp+1C8h]; this
0x1400574b8  mov     r9d, eax; char *
0x1400574bb  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400574c2  mov     edx, 69Bh; void *
0x1400574c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400574cc  nop
0x1400574cd  mov     rcx, [rsp+1C8h+var_1A8+8]; this
0x1400574d2  test    rcx, rcx
0x1400574d5  jz      short loc_1400574DD
0x1400574d7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400574dc  nop
0x1400574dd  lea     rcx, [rsp+1C8h+var_188]; this
0x1400574e2  call    ??1OpenDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenDatabase::~OpenDatabase(void)
0x1400574e7  mov     eax, ebx
0x1400574e9  jmp     loc_1400575AC
0x1400574ee  cmp     ebx, 90003h
0x1400574f4  jnz     short loc_1400574FB
0x1400574f6  call    ?ShouldReencrypt@BioIsoProvider@@SAXXZ; BioIsoProvider::ShouldReencrypt(void)
0x1400574fb  lea     rcx, [rsp+1C8h+var_188]
0x140057500  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140057505  nop
0x140057506  mov     rcx, [rsp+1C8h+var_1A8+8]; this
0x14005750b  test    rcx, rcx
0x14005750e  jz      short loc_140057516
0x140057510  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140057515  nop
0x140057516  lea     rcx, [rsp+1C8h+var_188]; this
0x14005751b  call    ??1OpenDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenDatabase::~OpenDatabase(void)
0x140057520  mov     eax, ebx
0x140057522  jmp     loc_1400575AC
0x140057527  test    rdi, rdi
0x14005752a  cmovnz  r9, rdi; ConnectString
0x14005752e  test    rsi, rsi
0x140057531  cmovnz  r8, rsi; FilePath
0x140057535  add     rcx, 20h ; ' '; Pipeline
0x140057539  call    WbioStorageOpenDatabase
0x14005753e  mov     ebx, eax
0x140057540  test    eax, eax
0x140057542  jns     short loc_14005757F
0x140057544  mov     rcx, [rsp+1C8h]; this
0x14005754c  mov     r9d, eax; char *
0x14005754f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140057556  mov     edx, 6ACh; void *
0x14005755b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057560  nop
0x140057561  mov     rcx, [rsp+1C8h+var_1A8+8]; this
0x140057566  test    rcx, rcx
0x140057569  jz      short loc_140057571
0x14005756b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140057570  nop
0x140057571  lea     rcx, [rsp+1C8h+var_188]; this
0x140057576  call    ??1OpenDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenDatabase::~OpenDatabase(void)
0x14005757b  mov     eax, ebx
0x14005757d  jmp     short loc_1400575AC
0x14005757f  lea     rcx, [rsp+1C8h+var_188]
0x140057584  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140057589  nop
0x14005758a  mov     rcx, [rsp+1C8h+var_1A8+8]; this
0x14005758f  test    rcx, rcx
0x140057592  jz      short loc_14005759A
0x140057594  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140057599  nop
0x14005759a  lea     rcx, [rsp+1C8h+var_188]; this
0x14005759f  call    ??1OpenDatabase@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenDatabase::~OpenDatabase(void)
0x1400575a4  xor     eax, eax
0x1400575a6  jmp     short loc_1400575AC
0x1400575a8  mov     eax, [rsp+1C8h+var_198]
0x1400575ac  mov     rcx, [rsp+1C8h+var_38]
0x1400575b4  xor     rcx, rsp; StackCookie
0x1400575b7  call    __security_check_cookie
0x1400575bc  add     rsp, 1A8h
0x1400575c3  pop     r14
0x1400575c5  pop     rdi
0x1400575c6  pop     rsi
0x1400575c7  pop     rbx
0x1400575c8  retn
```
