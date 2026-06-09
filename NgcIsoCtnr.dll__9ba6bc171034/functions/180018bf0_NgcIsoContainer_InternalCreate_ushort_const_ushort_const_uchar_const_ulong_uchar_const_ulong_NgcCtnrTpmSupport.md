# NgcIsoContainer::InternalCreate(ushort const *,ushort const *,uchar const *,ulong,uchar const *,ulong,NgcCtnrTpmSupport,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180018bf0`
- end: `0x18001911a`
- name: `?InternalCreate@NgcIsoContainer@@AEAAJPEBG0PEBEK1KW4NgcCtnrTpmSupport@@PEA_K3@Z`
- size: `1322`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, unsigned int, char, struct _GUID *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `37`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007670`
- `0x18000a148`
- `0x18000a168`
- `0x18000d60c`
- `0x18000d62c`
- `0x180011c1c`
- `0x180013088`
- `0x1800163e8`
- `0x180016cf4`
- `0x180017cc4`
- `0x180017cf0`
- `0x180017e2c`
- `0x1800180c0`
- `0x180018220`
- `0x1800183c4`
- `0x180018bf0`
- `0x180019330`
- `0x18001969c`
- `0x18001a444`
- `0x18001a774`
- `0x18001cb98`
- `0x18001cbe8`
- `0x18001cf64`
- `0x18001d158`
- `0x18001d1ac`
- `0x18001d1d8`
- `0x18002ff54`
- `0x1800348cc`
- `0x18003c314`
- `0x18003ed9c`
- `0x1800649d4`
- `0x180066848`
- `0x180066ae0`
- `0x180067358`
- `0x1800694fc`
- `0x180072178`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018f40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018f40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018c85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018c85`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180018d27`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180018d27`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180018df7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180018df7`

## string_xrefs

- `0x180018cbc`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_containeroperations.cpp`
- `0x180018d3d`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_containeroperations.cpp`
- `0x180018dca`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_containeroperations.cpp`
- `0x180018e08`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_containeroperations.cpp`
- `0x180018e49`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_containeroperations.cpp`
- `0x180018c50`: `NgcIsoContainerCreate`

## pseudocode

```c
__int64 __fastcall NgcIsoContainer::InternalCreate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        char a8,
        struct _GUID *a9,
        unsigned __int64 *a10)
{
  unsigned int v13; // r10d
  unsigned int LastError; // ebx
  HRESULT Guid; // eax
  bool v16; // zf
  __int64 v17; // rax
  int ContainerRootPath; // eax
  __int64 v19; // rdx
  const WCHAR *v20; // rax
  const char *v21; // r9
  FileSystem *v22; // rax
  const unsigned __int16 *v23; // rdx
  const struct _GUID *v24; // rdx
  int v25; // eax
  bool *v26; // rdx
  int IsPostLogonCachingDisabled; // eax
  const struct _GUID *v28; // rdx
  bool v29; // r8
  int v30; // eax
  __int64 NewProtector; // rax
  int v32; // eax
  NgcIsoContainer *v33; // rcx
  int v34; // eax
  unsigned __int64 *v35; // r9
  int ContainerTrustLevel; // eax
  enum TrustLevel *v37; // r8
  __int64 v38; // rdx
  struct Properties::ContainerProtectedProperties *v39; // r8
  FileSystem *v40; // rax
  const struct Properties::Container *v41; // r8
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  struct _GUID *v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  wil::details::in1diag3 *v47; // [rsp+50h] [rbp-B0h] BYREF
  const char *v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  __int16 v50; // [rsp+68h] [rbp-98h]
  __int64 v51; // [rsp+70h] [rbp-90h]
  unsigned __int64 *v52; // [rsp+78h] [rbp-88h]
  struct _GUID *v53; // [rsp+80h] [rbp-80h]
  __int64 v54; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v55; // [rsp+90h] [rbp-70h] BYREF
  __int64 v56; // [rsp+98h] [rbp-68h]
  char *v57; // [rsp+A0h] [rbp-60h]
  _BYTE v58[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v59[64]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v60[80]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v61[224]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v62[42]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  v51 = a4;
  v53 = a9;
  v52 = a10;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v62);
  v62[0] = &LogProvider::NgcIsoContainerCreate::`vftable';
  LogProvider::NgcIsoContainerCreate::StartActivity((LogProvider::NgcIsoContainerCreate *)v62);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
  v54 = a1 + 16;
  wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v61);
  v55 = v61;
  v56 = a1;
  v57 = &a8;
  v47 = retaddr;
  v48 = "onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp";
  v49 = 0;
  v50 = 61;
  wil::scope_exit_log__lambda_cd18ebc782f96f5b3bbd1fd2458377d4___(v60, &v47, &v55);
  if ( *(_DWORD *)(a1 + 24) )
  {
    LastError = -2147019873;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x5F, v13, (const char *)0x8007139FLL, v43);
    goto LABEL_43;
  }
  v55 = (_BYTE *)a1;
  LOBYTE(v56) = 1;
  Guid = CoCreateGuid((GUID *)(a1 + 136));
  LastError = Guid;
  if ( Guid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
      (const char *)(unsigned int)Guid,
      v43);
    v16 = *(_DWORD *)(a1 + 24) == 0;
    goto LABEL_5;
  }
  if ( a2 )
    std::wstring::assign(a1 + 152, a2);
  v17 = std::vector<unsigned char>::vector<unsigned char>(&v47, a6, a6 + a7);
  std::vector<unsigned char>::operator=(a1 + 184, v17);
  std::vector<unsigned char>::_Tidy(&v47);
  *(_DWORD *)(a1 + 64) = 2;
  ContainerRootPath = NgcIsoContainer::InternalGetContainerRootPath(a3, (NgcUtils *)(a1 + 136), a1 + 32);
  LastError = ContainerRootPath;
  if ( ContainerRootPath < 0 )
  {
    v19 = 118;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
      (const char *)(unsigned int)ContainerRootPath,
      v43);
LABEL_12:
    v16 = *(_DWORD *)(a1 + 24) == 0;
LABEL_5:
    if ( v16 )
      *(_DWORD *)(a1 + 24) = 3;
    goto LABEL_43;
  }
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
  if ( !CreateDirectoryW(v20, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7A,
                  (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
                  v21);
    goto LABEL_12;
  }
  v22 = (FileSystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
  ContainerRootPath = FileSystem::ProvisionFileSystem(v22, v23);
  LastError = ContainerRootPath;
  if ( ContainerRootPath < 0 )
  {
    v19 = 125;
    goto LABEL_11;
  }
  v46 = a1;
  v47 = retaddr;
  v48 = "onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp";
  v49 = 0;
  v50 = 127;
  wil::scope_exit_log__lambda_f8442aba328f370f81f9b2a3410e1eb6___(v58, &v47, &v46);
  v25 = NgcIsoTrustlet::AddNewContainer((NgcIsoTrustlet *)(a1 + 136), v24);
  LastError = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
      (const char *)(unsigned int)v25,
      v43);
LABEL_19:
    wil::details::lambda_call_log__lambda_92cd1b3e0dced8ff40b6d4a6b7cacecb___::reset(v58);
    goto LABEL_12;
  }
  LOBYTE(v45) = 0;
  IsPostLogonCachingDisabled = NgcUtils::IsPostLogonCachingDisabled((NgcUtils *)&v45, v26);
  if ( IsPostLogonCachingDisabled < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
      (const char *)(unsigned int)IsPostLogonCachingDisabled,
      v43);
  LOBYTE(v28) = (_BYTE)v45;
  v30 = NgcIsoTrustlet::SetContainerPostLogonCachingPolicy((NgcIsoTrustlet *)(a1 + 136), v28, v29);
  if ( v30 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
      (const char *)(unsigned int)v30,
      v43);
  v46 = a1;
  v47 = retaddr;
  v48 = "onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp";
  v49 = 0;
  v50 = 142;
  wil::scope_exit_log__lambda_f8442aba328f370f81f9b2a3410e1eb6___(v59, &v47, &v46);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 472));
  v46 = a1 + 472;
  NewProtector = NgcIsoContainer::MakeNewProtector(a1, 1);
  v44 = a5;
  v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)NewProtector + 8LL))(
          NewProtector,
          0,
          0,
          v51);
  LastError = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
      (const char *)(unsigned int)v32,
      a5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v46);
LABEL_26:
    wil::details::lambda_call_log__lambda_f8442aba328f370f81f9b2a3410e1eb6___::reset(v59);
    goto LABEL_19;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v46);
  v34 = NgcIsoContainer::InternalDeleteLockoutAuth(v33);
  if ( v34 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
      (const char *)(unsigned int)v34,
      a5);
  ContainerTrustLevel = NgcIsoTrustlet::FinalizeContainer((NgcIsoTrustlet *)(a1 + 136), v53, v52, v35);
  LastError = ContainerTrustLevel;
  if ( ContainerTrustLevel < 0 )
  {
    v38 = 164;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_containeroperations.cpp",
      (const char *)(unsigned int)ContainerTrustLevel,
      v44);
    goto LABEL_26;
  }
  ContainerTrustLevel = NgcIsoTrustlet::GetContainerTrustLevel(
                          (NgcIsoTrustlet *)(a1 + 136),
                          (const struct _GUID *)(a1 + 212),
                          v37);
  LastError = ContainerTrustLevel;
  if ( ContainerTrustLevel < 0 )
  {
    v38 = 168;
    goto LABEL_31;
  }
  ContainerTrustLevel = NgcIsoTrustlet::ExportContainerProtectedProperties(
                          (NgcIsoTrustlet *)(a1 + 136),
                          (const struct _GUID *)(a1 + 240),
                          v39);
  LastError = ContainerTrustLevel;
  if ( ContainerTrustLevel < 0 )
  {
    v38 = 172;
    goto LABEL_31;
  }
  NgcIsoContainer::InternalSetSrkModulusHash((NgcIsoContainer *)a1);
  v40 = (FileSystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
  ContainerTrustLevel = FileSystem::WriteContainerProperties(v40, (const unsigned __int16 *)(a1 + 64), v41);
  LastError = ContainerTrustLevel;
  if ( ContainerTrustLevel < 0 )
  {
    v38 = 181;
    goto LABEL_31;
  }
  ContainerTrustLevel = NgcIsoContainer::WriteProtectorProperties((NgcIsoContainer *)a1);
  LastError = ContainerTrustLevel;
  if ( ContainerTrustLevel < 0 )
  {
    v38 = 183;
    goto LABEL_31;
  }
  if ( !*(_DWORD *)(a1 + 24) )
    *(_DWORD *)(a1 + 24) = 2;
  v58[48] = 0;
  v59[48] = 0;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v62);
  wil::details::lambda_call_log__lambda_f8442aba328f370f81f9b2a3410e1eb6___::reset(v59);
  wil::details::lambda_call_log__lambda_92cd1b3e0dced8ff40b6d4a6b7cacecb___::reset(v58);
  LastError = 0;
LABEL_43:
  wil::details::lambda_call_log__lambda_cd18ebc782f96f5b3bbd1fd2458377d4___::reset(v60);
  wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v61);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v54);
  LogProvider::NgcIsoContainerCreate::~NgcIsoContainerCreate((LogProvider::NgcIsoContainerCreate *)v62);
  return LastError;
}

```

## disassembly

```asm
0x180018bf0  push    rbp
0x180018bf2  push    rbx
0x180018bf3  push    rsi
0x180018bf4  push    rdi
0x180018bf5  push    r12
0x180018bf7  push    r13
0x180018bf9  push    r14
0x180018bfb  push    r15
0x180018bfd  lea     rbp, [rsp-2B8h]
0x180018c05  sub     rsp, 3B8h
0x180018c0c  mov     rax, cs:__security_cookie
0x180018c13  xor     rax, rsp
0x180018c16  mov     [rbp+2F0h+var_50], rax
0x180018c1d  mov     [rsp+3F0h+var_380], r9
0x180018c22  mov     r12, r8
0x180018c25  mov     r14, rdx
0x180018c28  mov     rdi, rcx
0x180018c2b  mov     r15, [rbp+2F0h+arg_28]
0x180018c32  mov     r13d, [rbp+2F0h+arg_30]
0x180018c39  mov     rax, [rbp+2F0h+arg_40]
0x180018c40  mov     [rbp+2F0h+var_370], rax
0x180018c44  mov     rax, [rbp+2F0h+arg_48]
0x180018c4b  mov     [rsp+3F0h+var_378], rax
0x180018c50  lea     rdx, aNgcisocontaine_44; "NgcIsoContainerCreate"
0x180018c57  lea     rcx, [rbp+2F0h+var_1A0]; struct wil::details::IFailureCallback *
0x180018c5e  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180018c63  lea     rax, ??_7NgcIsoContainerCreate@LogProvider@@6B@; const LogProvider::NgcIsoContainerCreate::`vftable'
0x180018c6a  mov     [rbp+2F0h+var_1A0], rax
0x180018c71  lea     rcx, [rbp+2F0h+var_1A0]; this
0x180018c78  call    ?StartActivity@NgcIsoContainerCreate@LogProvider@@QEAAXXZ; LogProvider::NgcIsoContainerCreate::StartActivity(void)
0x180018c7d  nop
0x180018c7e  lea     rbx, [rdi+10h]
0x180018c82  mov     rcx, rbx; SRWLock
0x180018c85  call    cs:__imp_AcquireSRWLockExclusive
0x180018c8b  mov     [rbp+2F0h+var_368], rbx
0x180018c8f  lea     rcx, [rbp+2F0h+var_280]; this
0x180018c93  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x180018c98  nop
0x180018c99  lea     rax, [rbp+2F0h+var_280]
0x180018c9d  mov     [rbp+2F0h+var_360], rax
0x180018ca1  mov     [rbp+2F0h+var_358], rdi
0x180018ca5  lea     rax, [rbp+2F0h+arg_38]
0x180018cac  mov     [rbp+2F0h+var_350], rax
0x180018cb0  mov     rax, [rbp+2F8h]
0x180018cb7  mov     [rsp+3F0h+var_3A0], rax
0x180018cbc  lea     r10, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180018cc3  mov     [rsp+3F0h+var_398], r10
0x180018cc8  mov     [rsp+3F0h+var_390], 0
0x180018cd1  mov     eax, 3Dh ; '='
0x180018cd6  mov     [rsp+3F0h+var_388], ax
0x180018cdb  lea     r8, [rbp+2F0h+var_360]
0x180018cdf  lea     rdx, [rsp+3F0h+var_3A0]
0x180018ce4  lea     rcx, [rbp+2F0h+var_2D0]
0x180018ce8  call    wil__scope_exit_log__lambda_cd18ebc782f96f5b3bbd1fd2458377d4___
0x180018ced  nop
0x180018cee  cmp     dword ptr [rdi+18h], 0
0x180018cf2  jz      short loc_180018D15
0x180018cf4  mov     rcx, [rbp+2F8h]; this
0x180018cfb  mov     ebx, 8007139Fh
0x180018d00  mov     r9d, ebx; char *
0x180018d03  mov     r8, r10; unsigned int
0x180018d06  mov     edx, 5Fh ; '_'; void *
0x180018d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d10  jmp     loc_1800190CB
0x180018d15  mov     [rbp+2F0h+var_360], rdi
0x180018d19  mov     byte ptr [rbp+2F0h+var_358], 1
0x180018d1d  lea     rsi, [rdi+88h]
0x180018d24  mov     rcx, rsi; pguid
0x180018d27  call    cs:__imp_CoCreateGuid
0x180018d2d  mov     ebx, eax
0x180018d2f  test    eax, eax
0x180018d31  jns     short loc_180018D65
0x180018d33  mov     rcx, [rbp+2F8h]; this
0x180018d3a  mov     r9d, eax; char *
0x180018d3d  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180018d44  mov     edx, 66h ; 'f'; void *
0x180018d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d4e  nop
0x180018d4f  cmp     dword ptr [rdi+18h], 0
0x180018d53  jnz     loc_1800190CB
0x180018d59  mov     dword ptr [rdi+18h], 3
0x180018d60  jmp     loc_1800190CB
0x180018d65  test    r14, r14
0x180018d68  jz      short loc_180018D79
0x180018d6a  lea     rcx, [rdi+98h]
0x180018d71  mov     rdx, r14
0x180018d74  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180018d79  lea     r8, [r15+r13]
0x180018d7d  mov     rdx, r15
0x180018d80  lea     rcx, [rsp+3F0h+var_3A0]
0x180018d85  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x180018d8a  lea     rcx, [rdi+0B8h]
0x180018d91  mov     rdx, rax
0x180018d94  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180018d99  lea     rcx, [rsp+3F0h+var_3A0]
0x180018d9e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018da3  mov     dword ptr [rdi+40h], 2
0x180018daa  lea     r14, [rdi+20h]
0x180018dae  mov     r8, r14
0x180018db1  mov     rdx, rsi
0x180018db4  mov     rcx, r12
0x180018db7  call    ?InternalGetContainerRootPath@NgcIsoContainer@@CAJPEBGAEBU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcIsoContainer::InternalGetContainerRootPath(ushort const *,_GUID const &,std::wstring *)
0x180018dbc  mov     ebx, eax
0x180018dbe  xor     r12d, r12d
0x180018dc1  test    eax, eax
0x180018dc3  jns     short loc_180018DEA
0x180018dc5  lea     edx, [r12+76h]; void *
0x180018dca  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180018dd1  mov     r9d, eax; char *
0x180018dd4  mov     rcx, [rbp+2F8h]; this
0x180018ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018de0  nop
0x180018de1  cmp     [rdi+18h], r12d
0x180018de5  jmp     loc_180018D53
0x180018dea  mov     rcx, r14
0x180018ded  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018df2  mov     rcx, rax; lpPathName
0x180018df5  xor     edx, edx; lpSecurityAttributes
0x180018df7  call    cs:__imp_CreateDirectoryW
0x180018dfd  test    eax, eax
0x180018dff  jnz     short loc_180018E1B
0x180018e01  mov     rcx, [rbp+2F8h]; this
0x180018e08  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180018e0f  lea     edx, [rax+7Ah]; void *
0x180018e12  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018e17  mov     ebx, eax
0x180018e19  jmp     short loc_180018DE1
0x180018e1b  mov     rcx, r14
0x180018e1e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018e23  mov     rcx, rax; this
0x180018e26  call    ?ProvisionFileSystem@FileSystem@@YAJPEBG@Z; FileSystem::ProvisionFileSystem(ushort const *)
0x180018e2b  mov     ebx, eax
0x180018e2d  test    eax, eax
0x180018e2f  jns     short loc_180018E38
0x180018e31  mov     edx, 7Dh ; '}'
0x180018e36  jmp     short loc_180018DCA
0x180018e38  mov     [rsp+3F0h+var_3A8], rdi
0x180018e3d  mov     rax, [rbp+2F8h]
0x180018e44  mov     [rsp+3F0h+var_3A0], rax
0x180018e49  lea     r13, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180018e50  mov     [rsp+3F0h+var_398], r13
0x180018e55  mov     [rsp+3F0h+var_390], r12
0x180018e5a  mov     eax, 7Fh
0x180018e5f  mov     [rsp+3F0h+var_388], ax
0x180018e64  lea     r8, [rsp+3F0h+var_3A8]
0x180018e69  lea     rdx, [rsp+3F0h+var_3A0]
0x180018e6e  lea     rcx, [rbp+2F0h+var_348]
0x180018e72  call    wil__scope_exit_log__lambda_f8442aba328f370f81f9b2a3410e1eb6___
0x180018e77  nop
0x180018e78  mov     rcx, rsi; this
0x180018e7b  call    ?AddNewContainer@NgcIsoTrustlet@@YAJAEBU_GUID@@@Z; NgcIsoTrustlet::AddNewContainer(_GUID const &)
0x180018e80  mov     ebx, eax
0x180018e82  test    eax, eax
0x180018e84  jns     short loc_180018EAC
0x180018e86  mov     rcx, [rbp+2F8h]; this
0x180018e8d  mov     r9d, eax; char *
0x180018e90  mov     r8, r13; unsigned int
0x180018e93  mov     edx, 86h; void *
0x180018e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e9d  nop
0x180018e9e  lea     rcx, [rbp+2F0h+var_348]
0x180018ea2  call    wil__details__lambda_call_log__lambda_92cd1b3e0dced8ff40b6d4a6b7cacecb_____reset
0x180018ea7  jmp     loc_180018DE1
0x180018eac  mov     byte ptr [rsp+3F0h+var_3B0], r12b
0x180018eb1  lea     rcx, [rsp+3F0h+var_3B0]; this
0x180018eb6  call    ?IsPostLogonCachingDisabled@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsPostLogonCachingDisabled(bool *)
0x180018ebb  mov     rcx, [rbp+2F8h]; this
0x180018ec2  test    eax, eax
0x180018ec4  jns     short loc_180018ED6
0x180018ec6  mov     r9d, eax; char *
0x180018ec9  mov     r8, r13; unsigned int
0x180018ecc  mov     edx, 89h; void *
0x180018ed1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018ed6  mov     dl, byte ptr [rsp+3F0h+var_3B0]; struct _GUID *
0x180018eda  mov     rcx, rsi; this
0x180018edd  call    ?SetContainerPostLogonCachingPolicy@NgcIsoTrustlet@@YAJAEBU_GUID@@_N@Z; NgcIsoTrustlet::SetContainerPostLogonCachingPolicy(_GUID const &,bool)
0x180018ee2  mov     rcx, [rbp+2F8h]; this
0x180018ee9  test    eax, eax
0x180018eeb  jns     short loc_180018EFD
0x180018eed  mov     r9d, eax; char *
0x180018ef0  mov     r8, r13; unsigned int
0x180018ef3  mov     edx, 8Ch; void *
0x180018ef8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018efd  mov     [rsp+3F0h+var_3A8], rdi
0x180018f02  mov     rax, [rbp+2F8h]
0x180018f09  mov     [rsp+3F0h+var_3A0], rax
0x180018f0e  mov     [rsp+3F0h+var_398], r13
0x180018f13  mov     [rsp+3F0h+var_390], r12
0x180018f18  mov     eax, 8Eh
0x180018f1d  mov     [rsp+3F0h+var_388], ax
0x180018f22  lea     r8, [rsp+3F0h+var_3A8]
0x180018f27  lea     rdx, [rsp+3F0h+var_3A0]
0x180018f2c  lea     rcx, [rbp+2F0h+var_310]
0x180018f30  call    wil__scope_exit_log__lambda_f8442aba328f370f81f9b2a3410e1eb6___
0x180018f35  nop
0x180018f36  lea     rbx, [rdi+1D8h]
0x180018f3d  mov     rcx, rbx; lpCriticalSection
0x180018f40  call    cs:__imp_EnterCriticalSection
0x180018f46  mov     [rsp+3F0h+var_3A8], rbx
0x180018f4b  mov     edx, 1
0x180018f50  mov     rcx, rdi
0x180018f53  call    ?MakeNewProtector@NgcIsoContainer@@AEAAPEAVProtector@2@W4NgcCtnrProtectorId@@@Z; NgcIsoContainer::MakeNewProtector(NgcCtnrProtectorId)
0x180018f58  mov     r10, rax
0x180018f5b  mov     rcx, [rax]
0x180018f5e  mov     rax, [rcx+8]
0x180018f62  mov     [rsp+3F0h+var_3C0], r12
0x180018f67  mov     [rsp+3F0h+var_3C8], r12
0x180018f6c  mov     ecx, [rbp+2F0h+arg_20]
0x180018f72  mov     [rsp+3F0h+var_3D0], ecx; int
0x180018f76  mov     r9, [rsp+3F0h+var_380]
0x180018f7b  xor     r8d, r8d
0x180018f7e  xor     edx, edx
0x180018f80  mov     rcx, r10
0x180018f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f88  mov     ebx, eax
0x180018f8a  test    eax, eax
0x180018f8c  jns     short loc_180018FBF
0x180018f8e  mov     rcx, [rbp+2F8h]; this
0x180018f95  mov     r9d, eax; char *
0x180018f98  mov     r8, r13; unsigned int
0x180018f9b  mov     edx, 9Ch; void *
0x180018fa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018fa5  nop
0x180018fa6  lea     rcx, [rsp+3F0h+var_3A8]
0x180018fab  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180018fb0  nop
0x180018fb1  lea     rcx, [rbp+2F0h+var_310]
0x180018fb5  call    wil__details__lambda_call_log__lambda_f8442aba328f370f81f9b2a3410e1eb6_____reset
0x180018fba  jmp     loc_180018E9E
0x180018fbf  lea     rcx, [rsp+3F0h+var_3A8]
0x180018fc4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180018fc9  call    ?InternalDeleteLockoutAuth@NgcIsoContainer@@AEAAJXZ; NgcIsoContainer::InternalDeleteLockoutAuth(void)
0x180018fce  mov     rcx, [rbp+2F8h]; this
0x180018fd5  test    eax, eax
0x180018fd7  jns     short loc_180018FE9
0x180018fd9  mov     r9d, eax; char *
0x180018fdc  mov     r8, r13; unsigned int
0x180018fdf  mov     edx, 9Fh; void *
0x180018fe4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018fe9  mov     r8, [rsp+3F0h+var_378]; unsigned __int64 *
0x180018fee  mov     rdx, [rbp+2F0h+var_370]; struct _GUID *
0x180018ff2  mov     rcx, rsi; this
0x180018ff5  call    ?FinalizeContainer@NgcIsoTrustlet@@YAJAEBU_GUID@@PEA_K1@Z; NgcIsoTrustlet::FinalizeContainer(_GUID const &,unsigned __int64 *,unsigned __int64 *)
0x180018ffa  mov     ebx, eax
0x180018ffc  test    eax, eax
0x180018ffe  jns     short loc_180019019
0x180019000  mov     edx, 0A4h; void *
0x180019005  mov     rcx, [rbp+2F8h]; this
0x18001900c  mov     r9d, eax; char *
0x18001900f  mov     r8, r13; unsigned int
0x180019012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019017  jmp     short loc_180018FB1
0x180019019  lea     rdx, [rdi+0D4h]; struct _GUID *
0x180019020  mov     rcx, rsi; this
0x180019023  call    ?GetContainerTrustLevel@NgcIsoTrustlet@@YAJAEBU_GUID@@PEAW4TrustLevel@VsmUtils@@@Z; NgcIsoTrustlet::GetContainerTrustLevel(_GUID const &,VsmUtils::TrustLevel *)
0x180019028  mov     ebx, eax
0x18001902a  test    eax, eax
0x18001902c  jns     short loc_180019035
0x18001902e  mov     edx, 0A8h
0x180019033  jmp     short loc_180019005
0x180019035  lea     rdx, [rdi+0F0h]; struct _GUID *
0x18001903c  mov     rcx, rsi; this
0x18001903f  call    ?ExportContainerProtectedProperties@NgcIsoTrustlet@@YAJAEBU_GUID@@PEAUContainerProtectedProperties@Properties@@@Z; NgcIsoTrustlet::ExportContainerProtectedProperties(_GUID const &,Properties::ContainerProtectedProperties *)
0x180019044  mov     ebx, eax
0x180019046  test    eax, eax
0x180019048  jns     short loc_180019051
0x18001904a  mov     edx, 0ACh
0x18001904f  jmp     short loc_180019005
0x180019051  mov     rcx, rdi; this
0x180019054  call    ?InternalSetSrkModulusHash@NgcIsoContainer@@AEAAXXZ; NgcIsoContainer::InternalSetSrkModulusHash(void)
0x180019059  mov     rcx, r14
0x18001905c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019061  mov     rcx, rax; this
0x180019064  lea     rdx, [rdi+40h]; unsigned __int16 *
0x180019068  call    ?WriteContainerProperties@FileSystem@@YAJPEBGAEBUContainer@Properties@@@Z; FileSystem::WriteContainerProperties(ushort const *,Properties::Container const &)
0x18001906d  mov     ebx, eax
0x18001906f  test    eax, eax
0x180019071  jns     short loc_18001907A
0x180019073  mov     edx, 0B5h
0x180019078  jmp     short loc_180019005
0x18001907a  mov     rcx, rdi; this
0x18001907d  call    ?WriteProtectorProperties@NgcIsoContainer@@AEAAJXZ; NgcIsoContainer::WriteProtectorProperties(void)
0x180019082  mov     ebx, eax
0x180019084  test    eax, eax
0x180019086  jns     short loc_180019092
0x180019088  mov     edx, 0B7h
0x18001908d  jmp     loc_180019005
0x180019092  cmp     [rdi+18h], r12d
0x180019096  jnz     short loc_18001909F
0x180019098  mov     dword ptr [rdi+18h], 2
0x18001909f  mov     [rbp+2F0h+var_318], r12b
0x1800190a3  mov     [rbp+2F0h+var_2E0], r12b
0x1800190a7  lea     rcx, [rbp+2F0h+var_1A0]
0x1800190ae  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800190b3  nop
0x1800190b4  lea     rcx, [rbp+2F0h+var_310]
0x1800190b8  call    wil__details__lambda_call_log__lambda_f8442aba328f370f81f9b2a3410e1eb6_____reset
0x1800190bd  nop
0x1800190be  lea     rcx, [rbp+2F0h+var_348]
0x1800190c2  call    wil__details__lambda_call_log__lambda_92cd1b3e0dced8ff40b6d4a6b7cacecb_____reset
  ... truncated ...
```
