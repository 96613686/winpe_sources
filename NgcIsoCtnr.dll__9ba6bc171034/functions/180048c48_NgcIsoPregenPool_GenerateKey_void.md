# NgcIsoPregenPool::GenerateKey(void)

- ea: `0x180048c48`
- end: `0x18004902f`
- name: `?GenerateKey@NgcIsoPregenPool@@AEAAXXZ`
- size: `999`
- prototype: `void __fastcall(NgcIsoPregenPool *__hidden this)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048b34`

## callees

- `0x180007670`
- `0x1800084c8`
- `0x18000a168`
- `0x18000d62c`
- `0x18000fa2c`
- `0x180011174`
- `0x180011c1c`
- `0x180011c9c`
- `0x180013088`
- `0x1800163e8`
- `0x180017d70`
- `0x180018818`
- `0x18002bccc`
- `0x180034858`
- `0x180047c70`
- `0x180047c94`
- `0x180048170`
- `0x180048330`
- `0x180048c48`
- `0x18004a320`
- `0x18004cb04`
- `0x18004cda8`
- `0x18004d01c`
- `0x18004d1cc`
- `0x18005bf38`
- `0x180068adc`
- `0x18006f1ec`
- `0x180070ef0`
- `0x1800762ac`
- `0x180076364`
- `0x180076894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048cad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048cad`
- `bcrypt!BCryptGenRandom` at `0x180048d74`
- `bcrypt!BCryptGenRandom` at `0x180048d74`

## string_xrefs

- `0x180048d44`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180048d89`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180048dd1`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180048e27`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180048e63`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180048ec3`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180048f6c`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180048f2c`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`
- `0x180048f48`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\ngcisotrustlet.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall NgcIsoPregenPool::GenerateKey(RTL_SRWLOCK *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // r8
  struct VsmUtils::Vtl0Tpm *v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  NTSTATUS v8; // eax
  unsigned __int16 *v9; // r8
  unsigned int v10; // r9d
  int StringFromGuid; // eax
  RTL_SRWLOCK *v12; // rbx
  NCRYPT_PROV_HANDLE *v13; // rax
  int v14; // eax
  int Vtl1ProtectedKey; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // ebx
  const char *v20; // r9
  __int64 v21; // rax
  unsigned int v22; // [rsp+20h] [rbp-2C8h]
  unsigned int v23; // [rsp+20h] [rbp-2C8h]
  int v24; // [rsp+20h] [rbp-2C8h]
  int v25; // [rsp+20h] [rbp-2C8h]
  unsigned int v26; // [rsp+28h] [rbp-2C0h]
  NCRYPT_KEY_HANDLE hKey; // [rsp+40h] [rbp-2A8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-2A0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-298h] BYREF
  _QWORD v30[2]; // [rsp+58h] [rbp-290h] BYREF
  char v31; // [rsp+68h] [rbp-280h]
  unsigned int v32[2]; // [rsp+70h] [rbp-278h] BYREF
  int v33; // [rsp+78h] [rbp-270h]
  BYTE *v34; // [rsp+88h] [rbp-260h] BYREF
  _BYTE v35[24]; // [rsp+90h] [rbp-258h] BYREF
  _BYTE v36[32]; // [rsp+A8h] [rbp-240h] BYREF
  __int64 v37; // [rsp+C8h] [rbp-220h]
  UCHAR pbBuffer[16]; // [rsp+D0h] [rbp-218h] BYREF
  BYTE pbOutput[40]; // [rsp+E0h] [rbp-208h] BYREF
  __int64 v40; // [rsp+108h] [rbp-1E0h]
  int v41; // [rsp+110h] [rbp-1D8h]
  __int64 v42; // [rsp+118h] [rbp-1D0h]
  __int64 v43; // [rsp+120h] [rbp-1C8h]
  char v44; // [rsp+128h] [rbp-1C0h]
  _QWORD v45[42]; // [rsp+130h] [rbp-1B8h] BYREF
  struct _GUID v46; // [rsp+280h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  std::promise<NgcIsoPregenPool::PregenKey>::promise<NgcIsoPregenPool::PregenKey>(v30);
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v45);
  v45[0] = &LogProvider::NgcIsoPregenPoolGenerateKey::`vftable';
  LogProvider::NgcIsoPregenPoolGenerateKey::StartActivity((LogProvider::NgcIsoPregenPoolGenerateKey *)v45);
  AcquireSRWLockExclusive(this + 9);
  hKey = (NCRYPT_KEY_HANDLE)&this[9];
  v2 = std::queue<std::promise<NgcIsoPregenPool::PregenKey>>::front(&this[10]);
  v3 = std::promise<NgcIsoPregenPool::PregenKey>::promise<NgcIsoPregenPool::PregenKey>(v32, v2);
  v4 = *(_QWORD *)v3;
  *(_QWORD *)v3 = v30[0];
  v30[0] = v4;
  LOBYTE(v4) = *(_BYTE *)(v3 + 16);
  *(_BYTE *)(v3 + 16) = v31;
  v31 = v4;
  std::promise<NgcIsoPregenPool::PregenKey>::~promise<NgcIsoPregenPool::PregenKey>(v32);
  std::deque<std::promise<NgcIsoPregenPool::PregenKey>>::pop_front(&this[10]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&hKey);
  v28 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v32);
  try
  {
    v5 = VsmUtils::Vtl0Tpm::Instance();
    v7 = NgcIsoTrustlet::PregenTpmKey(v6, *((_QWORD *)v5 + 1), &v28, v32);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
        (const char *)(unsigned int)v7,
        v22);
    *(_OWORD *)pbBuffer = 0;
    v8 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
        (const char *)(unsigned int)v8,
        v22);
    memset_0(&v46, 0, 0x4Eu);
    StringFromGuid = NgcUtils::GetStringFromGuid((NgcUtils *)pbBuffer, &v46, v9, v10);
    if ( StringFromGuid < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
        (const char *)(unsigned int)StringFromGuid,
        v22);
    hKey = 0;
    v12 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
    v13 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
    v14 = NgcCtnrCommon::KeyHandleCache::CreateKey(v12, *v13, L"RSA", (LPCWSTR)&v46, v22, v26, &hKey);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
        (const char *)(unsigned int)v14,
        v23);
    Vtl1ProtectedKey = VsmUtils::CreateVtl1ProtectedKey(hKey, 3u, v32[0], (unsigned __int8 *)(v33 - v32[0]), v23);
    if ( Vtl1ProtectedKey < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
        (const char *)(unsigned int)Vtl1ProtectedKey,
        v24);
    *(_DWORD *)pbOutput = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v16 = VsmUtils::Vtl0KeyBlob::Load(pbOutput, hKey);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
        (const char *)(unsigned int)v16,
        v24);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v35);
    v34 = pbOutput;
    LODWORD(hKey) = 80;
    v29 = v28;
    v18 = RpcCallWithBind<long (&)(void *,void *,unsigned long,unsigned char const *),void * &,unsigned long &,unsigned char const * &>(
            v17,
            &v29,
            &hKey,
            &v34);
    v19 = v18;
    if ( v18 >= 0 )
    {
      v19 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16C,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
        (const char *)(unsigned int)v18,
        v24);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6BC,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\ngcisotrustlet.cpp",
        (const char *)(unsigned int)v19,
        v25);
    }
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
        (const char *)(unsigned int)v19,
        v24);
    std::wstring::wstring(v36, &v46);
    v37 = v28;
    std::promise<NgcIsoPregenPool::PregenKey>::set_value(v30, v36);
    std::wstring::_Tidy_deallocate(v36);
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v45);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v35);
    VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
    std::vector<unsigned char>::_Tidy(v32);
    LogProvider::NgcIsoPregenPoolGenerateKey::~NgcIsoPregenPoolGenerateKey((LogProvider::NgcIsoPregenPoolGenerateKey *)v45);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
      v20);
    v21 = std::current_exception(pbBuffer);
    std::promise<NgcIsoPregenPool::PregenKey>::set_exception(v30, v21);
  }
  std::promise<NgcIsoPregenPool::PregenKey>::~promise<NgcIsoPregenPool::PregenKey>(v30);
}

```

## disassembly

```asm
0x180048c48  mov     [rsp+arg_8], rbx
0x180048c4d  push    rdi
0x180048c4e  sub     rsp, 2E0h
0x180048c55  mov     rax, cs:__security_cookie
0x180048c5c  xor     rax, rsp
0x180048c5f  mov     [rsp+2E8h+var_18], rax
0x180048c67  mov     rdi, rcx
0x180048c6a  lea     rcx, [rsp+2E8h+var_290]
0x180048c6f  call    ??0?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAA@XZ; std::promise<NgcIsoPregenPool::PregenKey>::promise<NgcIsoPregenPool::PregenKey>(void)
0x180048c74  nop
0x180048c75  lea     rdx, aNgcisopregenpo_4; "NgcIsoPregenPoolGenerateKey"
0x180048c7c  lea     rcx, [rsp+2E8h+var_1B8]; struct wil::details::IFailureCallback *
0x180048c84  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180048c89  lea     rax, ??_7NgcIsoPregenPoolGenerateKey@LogProvider@@6B@; const LogProvider::NgcIsoPregenPoolGenerateKey::`vftable'
0x180048c90  mov     [rsp+2E8h+var_1B8], rax
0x180048c98  lea     rcx, [rsp+2E8h+var_1B8]; this
0x180048ca0  call    ?StartActivity@NgcIsoPregenPoolGenerateKey@LogProvider@@QEAAXXZ; LogProvider::NgcIsoPregenPoolGenerateKey::StartActivity(void)
0x180048ca5  nop
0x180048ca6  lea     rbx, [rdi+48h]
0x180048caa  mov     rcx, rbx; SRWLock
0x180048cad  call    cs:__imp_AcquireSRWLockExclusive
0x180048cb3  mov     [rsp+2E8h+hKey], rbx
0x180048cb8  lea     rcx, [rdi+50h]
0x180048cbc  call    ?front@?$queue@V?$promise@UPregenKey@NgcIsoPregenPool@@@std@@V?$deque@V?$promise@UPregenKey@NgcIsoPregenPool@@@std@@V?$allocator@V?$promise@UPregenKey@NgcIsoPregenPool@@@std@@@2@@2@@std@@QEAAAEAV?$promise@UPregenKey@NgcIsoPregenPool@@@2@XZ; std::queue<std::promise<NgcIsoPregenPool::PregenKey>>::front(void)
0x180048cc1  mov     rdx, rax
0x180048cc4  lea     rcx, [rsp+2E8h+var_278]
0x180048cc9  call    ??0?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAA@$$QEAV01@@Z; std::promise<NgcIsoPregenPool::PregenKey>::promise<NgcIsoPregenPool::PregenKey>(std::promise<NgcIsoPregenPool::PregenKey> &&)
0x180048cce  mov     r8, [rax]
0x180048cd1  mov     rdx, [rsp+2E8h+var_290]
0x180048cd6  mov     [rax], rdx
0x180048cd9  mov     [rsp+2E8h+var_290], r8
0x180048cde  mov     r8b, [rax+10h]
0x180048ce2  mov     dl, [rsp+2E8h+var_280]
0x180048ce6  mov     [rax+10h], dl
0x180048ce9  mov     [rsp+2E8h+var_280], r8b
0x180048cee  lea     rcx, [rsp+2E8h+var_278]
0x180048cf3  call    ??1?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAA@XZ; std::promise<NgcIsoPregenPool::PregenKey>::~promise<NgcIsoPregenPool::PregenKey>(void)
0x180048cf8  lea     rcx, [rdi+50h]
0x180048cfc  call    ?pop_front@?$deque@V?$promise@UPregenKey@NgcIsoPregenPool@@@std@@V?$allocator@V?$promise@UPregenKey@NgcIsoPregenPool@@@std@@@2@@std@@QEAAXXZ; std::deque<std::promise<NgcIsoPregenPool::PregenKey>>::pop_front(void)
0x180048d01  lea     rcx, [rsp+2E8h+hKey]
0x180048d06  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180048d0b  xor     edi, edi
0x180048d0d  mov     [rsp+2E8h+var_2A0], rdi
0x180048d12  lea     rcx, [rsp+2E8h+var_278]
0x180048d17  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180048d1c  nop
0x180048d1d  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x180048d22  lea     r9, [rsp+2E8h+var_278]
0x180048d27  lea     r8, [rsp+2E8h+var_2A0]
0x180048d2c  mov     rdx, [rax+8]
0x180048d30  call    ?PregenTpmKey@NgcIsoTrustlet@@YAJW4Algorithm@@_KPEAPEAXPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcIsoTrustlet::PregenTpmKey(Algorithm,unsigned __int64,void * *,std::vector<uchar> *)
0x180048d35  mov     rcx, [rsp+2E8h]; this
0x180048d3d  test    eax, eax
0x180048d3f  jns     short loc_180048D55
0x180048d41  mov     r9d, eax; char *
0x180048d44  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048d4b  mov     edx, 129h; void *
0x180048d50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048d55  xorps   xmm0, xmm0
0x180048d58  movups  xmmword ptr [rsp+2E8h+pbBuffer], xmm0
0x180048d60  mov     r9d, 2; dwFlags
0x180048d66  lea     r8d, [r9+0Eh]; cbBuffer
0x180048d6a  lea     rdx, [rsp+2E8h+pbBuffer]; pbBuffer
0x180048d72  xor     ecx, ecx; hAlgorithm
0x180048d74  call    cs:__imp_BCryptGenRandom
0x180048d7a  mov     rcx, [rsp+2E8h]; this
0x180048d82  test    eax, eax
0x180048d84  jns     short loc_180048D9A
0x180048d86  mov     r9d, eax; char *
0x180048d89  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048d90  mov     edx, 130h; void *
0x180048d95  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180048d9a  xor     edx, edx; Val
0x180048d9c  lea     r8d, [rdx+4Eh]; Size
0x180048da0  lea     rcx, [rsp+2E8h+var_68]; void *
0x180048da8  call    memset_0
0x180048dad  lea     rdx, [rsp+2E8h+var_68]; struct _GUID *
0x180048db5  lea     rcx, [rsp+2E8h+pbBuffer]; this
0x180048dbd  call    ?GetStringFromGuid@NgcUtils@@YAJAEBU_GUID@@PEAGK@Z; NgcUtils::GetStringFromGuid(_GUID const &,ushort *,ulong)
0x180048dc2  mov     rcx, [rsp+2E8h]; this
0x180048dca  test    eax, eax
0x180048dcc  jns     short loc_180048DE2
0x180048dce  mov     r9d, eax; char *
0x180048dd1  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048dd8  mov     edx, 136h; void *
0x180048ddd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048de2  mov     [rsp+2E8h+hKey], rdi
0x180048de7  call    ?Instance@KeyHandleCache@NgcCtnrCommon@@SAAEAV12@XZ; NgcCtnrCommon::KeyHandleCache::Instance(void)
0x180048dec  mov     rbx, rax
0x180048def  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x180048df4  lea     rcx, [rsp+2E8h+hKey]
0x180048df9  mov     [rsp+2E8h+var_2B8], rcx; unsigned __int64 *
0x180048dfe  lea     r9, [rsp+2E8h+var_68]; pszKeyName
0x180048e06  lea     r8, aRsa; "RSA"
0x180048e0d  mov     rdx, [rax]; hProvider
0x180048e10  mov     rcx, rbx; SRWLock
0x180048e13  call    ?CreateKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBG1KKPEA_K@Z; NgcCtnrCommon::KeyHandleCache::CreateKey(unsigned __int64,ushort const *,ushort const *,ulong,ulong,unsigned __int64 *)
0x180048e18  mov     rcx, [rsp+2E8h]; this
0x180048e20  test    eax, eax
0x180048e22  jns     short loc_180048E38
0x180048e24  mov     r9d, eax; char *
0x180048e27  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048e2e  mov     edx, 13Fh; void *
0x180048e33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048e38  mov     r9d, [rsp+2E8h+var_270]
0x180048e3d  mov     r8, qword ptr [rsp+2E8h+var_278]; unsigned int
0x180048e42  sub     r9d, r8d; unsigned __int8 *
0x180048e45  mov     edx, 3; unsigned __int64
0x180048e4a  mov     rcx, [rsp+2E8h+hKey]; hKey
0x180048e4f  call    ?CreateVtl1ProtectedKey@VsmUtils@@YAJ_KKPEAEK@Z; VsmUtils::CreateVtl1ProtectedKey(unsigned __int64,ulong,uchar *,ulong)
0x180048e54  mov     rcx, [rsp+2E8h]; this
0x180048e5c  test    eax, eax
0x180048e5e  jns     short loc_180048E74
0x180048e60  mov     r9d, eax; char *
0x180048e63  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048e6a  mov     edx, 145h; void *
0x180048e6f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048e74  mov     dword ptr [rsp+2E8h+pbOutput], edi
0x180048e7b  mov     [rsp+2E8h+var_1E0], rdi
0x180048e83  mov     [rsp+2E8h+var_1D8], edi
0x180048e8a  mov     [rsp+2E8h+var_1D0], rdi
0x180048e92  mov     [rsp+2E8h+var_1C8], rdi
0x180048e9a  mov     [rsp+2E8h+var_1C0], dil
0x180048ea2  mov     rdx, [rsp+2E8h+hKey]; hObject
0x180048ea7  lea     rcx, [rsp+2E8h+pbOutput]; pbOutput
0x180048eaf  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x180048eb4  mov     rcx, [rsp+2E8h]; this
0x180048ebc  test    eax, eax
0x180048ebe  jns     short loc_180048ED4
0x180048ec0  mov     r9d, eax; char *
0x180048ec3  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048eca  mov     edx, 148h; void *
0x180048ecf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048ed4  lea     rcx, [rsp+2E8h+var_258]
0x180048edc  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180048ee1  nop
0x180048ee2  lea     rax, [rsp+2E8h+pbOutput]
0x180048eea  mov     [rsp+2E8h+var_260], rax
0x180048ef2  mov     dword ptr [rsp+2E8h+hKey], 50h ; 'P'
0x180048efa  mov     rax, [rsp+2E8h+var_2A0]
0x180048eff  mov     [rsp+2E8h+var_298], rax
0x180048f04  lea     r9, [rsp+2E8h+var_260]
0x180048f0c  lea     r8, [rsp+2E8h+hKey]
0x180048f11  lea     rdx, [rsp+2E8h+var_298]
0x180048f16  call    ??$RpcCallWithBind@A6AJPEAX0KPEBE@ZAEAPEAXAEAKAEAPEBE@@YAJA6AJPEAX0KPEBE@ZAEAPEAXAEAKAEAPEBE@Z; RpcCallWithBind<long (&)(void *,void *,ulong,uchar const *),void * &,ulong &,uchar const * &>(long (&)(void *,void *,ulong,uchar const *),void * &,ulong &,uchar const * &)
0x180048f1b  mov     ebx, eax
0x180048f1d  test    eax, eax
0x180048f1f  jns     short loc_180048F5B
0x180048f21  mov     rcx, [rsp+2E8h]; this
0x180048f29  mov     r9d, eax; char *
0x180048f2c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048f33  mov     edx, 16Ch; void *
0x180048f38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f3d  mov     rcx, [rsp+2E8h]; this
0x180048f45  mov     r9d, ebx; char *
0x180048f48  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048f4f  mov     edx, 6BCh; void *
0x180048f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f59  jmp     short loc_180048F5D
0x180048f5b  mov     ebx, edi
0x180048f5d  mov     rcx, [rsp+2E8h]; this
0x180048f65  test    ebx, ebx
0x180048f67  jns     short loc_180048F7D
0x180048f69  mov     r9d, ebx; char *
0x180048f6c  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180048f73  mov     edx, 14Eh; void *
0x180048f78  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048f7d  lea     rdx, [rsp+2E8h+var_68]
0x180048f85  lea     rcx, [rsp+2E8h+var_240]
0x180048f8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180048f92  mov     rax, [rsp+2E8h+var_2A0]
0x180048f97  mov     [rsp+2E8h+var_220], rax
0x180048f9f  lea     rdx, [rsp+2E8h+var_240]
0x180048fa7  lea     rcx, [rsp+2E8h+var_290]
0x180048fac  call    ?set_value@?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAAX$$QEAUPregenKey@NgcIsoPregenPool@@@Z; std::promise<NgcIsoPregenPool::PregenKey>::set_value(NgcIsoPregenPool::PregenKey &&)
0x180048fb1  nop
0x180048fb2  lea     rcx, [rsp+2E8h+var_240]
0x180048fba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048fbf  lea     rcx, [rsp+2E8h+var_1B8]
0x180048fc7  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180048fcc  nop
0x180048fcd  lea     rcx, [rsp+2E8h+var_258]
0x180048fd5  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180048fda  nop
0x180048fdb  lea     rcx, [rsp+2E8h+pbOutput]; this
0x180048fe3  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x180048fe8  nop
0x180048fe9  lea     rcx, [rsp+2E8h+var_278]
0x180048fee  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180048ff3  nop
0x180048ff4  lea     rcx, [rsp+2E8h+var_1B8]; this
0x180048ffc  call    ??1NgcIsoPregenPoolGenerateKey@LogProvider@@QEAA@XZ; LogProvider::NgcIsoPregenPoolGenerateKey::~NgcIsoPregenPoolGenerateKey(void)
0x180049001  nop
0x180049002  jmp     short $+2
0x180049004  lea     rcx, [rsp+2E8h+var_290]
0x180049009  call    ??1?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAA@XZ; std::promise<NgcIsoPregenPool::PregenKey>::~promise<NgcIsoPregenPool::PregenKey>(void)
0x18004900e  mov     rcx, [rsp+2E8h+var_18]
0x180049016  xor     rcx, rsp; StackCookie
0x180049019  call    __security_check_cookie
0x18004901e  mov     rbx, [rsp+2E8h+arg_8]
0x180049026  add     rsp, 2E0h
0x18004902d  pop     rdi
0x18004902e  retn
```
