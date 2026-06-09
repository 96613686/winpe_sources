# AiDoesExecutableExistInPackage(ushort const *,ushort const *,bool *)

- ea: `0x1800187f0`
- end: `0x180018db5`
- name: `?AiDoesExecutableExistInPackage@@YAJPEBG0PEA_N@Z`
- size: `1477`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ed98`

## callees

- `0x1800058b0`
- `0x18000720c`
- `0x180009ba8`
- `0x180009d10`
- `0x18000b0a4`
- `0x18000b2c0`
- `0x18000d3d0`
- `0x180010084`
- `0x180011414`
- `0x1800187f0`
- `0x180018dbc`
- `0x18001d494`
- `0x18001ddf0`
- `0x180031ad8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018bc2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018bc2`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x180018999`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x180018999`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800188a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018c52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018cbe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018d30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800188a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018c52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018cbe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018d30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18001884d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18001884d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018aa5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018c2b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018c9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018d0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018d89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018aa5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018c2b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018c9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018d0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018d89`

## string_xrefs

- `0x180018866`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x180018a66`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001887e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018924`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001895a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800189e5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018a7e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018b02`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018c61`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018cd0`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall AiDoesExecutableExistInPackage(const unsigned __int16 *a1, const unsigned __int16 *a2, bool *a3)
{
  int IsTrustedAndInPackage; // ebx
  __int64 v7; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r13
  __int64 v13; // rcx
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r14
  __int64 v21; // rax
  const WCHAR *v22; // rbx
  const unsigned __int16 *v23; // r8
  int v24; // eax
  unsigned int v25; // r14d
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  const unsigned __int16 *v31; // rax
  __int64 v32; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  unsigned int *bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCased; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  __int64 v38; // [rsp+30h] [rbp-D0h] BYREF
  int v39; // [rsp+38h] [rbp-C8h]
  __int64 v40; // [rsp+40h] [rbp-C0h]
  __int64 v41[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h]
  __int64 v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h]
  __int64 v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h]
  __int128 v48; // [rsp+90h] [rbp-70h]
  int v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v52; // [rsp+C0h] [rbp-40h]
  __int64 *v53; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-30h] BYREF
  char v55; // [rsp+D8h] [rbp-28h]
  __int128 v56; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]
  __int128 v59; // [rsp+100h] [rbp+0h]
  __int128 v60; // [rsp+110h] [rbp+10h]
  int v61[4]; // [rsp+120h] [rbp+20h]
  __int128 v62; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  unsigned int v64; // [rsp+180h] [rbp+80h] BYREF
  __int64 v65; // [rsp+190h] [rbp+90h] BYREF
  LPCWCH lpString1; // [rsp+198h] [rbp+98h] BYREF

  *a3 = 0;
  if ( !a1 || !a2 )
  {
    *a3 = 1;
    return 0;
  }
  v65 = 0;
  v53 = &v65;
  v54 = 0;
  v55 = 1;
  IsTrustedAndInPackage = SRCacheManager_Open(0, &v54);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v53);
  if ( IsTrustedAndInPackage < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCase);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B92,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCasec);
LABEL_5:
    v7 = v65;
    v65 = 0;
    if ( v7 )
      SRCacheManager_Close();
    return (unsigned int)IsTrustedAndInPackage;
  }
  v42 = 0;
  *(_OWORD *)v41 = 0;
  v48 = 0;
  bIgnoreCasea = &v64;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  LOBYTE(v64) = 0;
  IsTrustedAndInPackage = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(&v65, a1, 304, v41);
  if ( IsTrustedAndInPackage < 0 )
  {
    v9 = 11165;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      (int)&v64);
LABEL_11:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
    goto LABEL_5;
  }
  if ( !(_BYTE)v64 )
  {
    v10 = 2;
    v11 = 11169;
LABEL_14:
    IsTrustedAndInPackage = wil::details::in1diag3::Return_Win32(
                              retaddr,
                              (void *)v11,
                              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                              (const char *)v10,
                              (unsigned int)&v64);
    goto LABEL_11;
  }
  v10 = 3;
  if ( HIDWORD(v44) == 3 && (v44 & 0x10) != 0 || (v44 & 0x20) != 0 )
  {
    v64 = 0;
    IsTrustedAndInPackage = VerifyFileIsTrustedAndInPackage(a2, a1, &v64);
    if ( IsTrustedAndInPackage < 0 )
    {
      v9 = 11180;
      goto LABEL_10;
    }
    *a3 = v64 != 0;
    goto LABEL_49;
  }
  v12 = v47;
  if ( !v47 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BB2,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x8007000ELL,
      (int)&v64);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
    v13 = v65;
    v65 = 0;
LABEL_59:
    if ( v13 )
      SRCacheManager_Close();
    return 2147942414LL;
  }
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v47 + 2 * v14) );
  if ( !v14 )
  {
    v11 = 11191;
    goto LABEL_14;
  }
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v15 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
          (StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *)&v38,
          (struct StateRepository::Cache::Manager_NoThrow *)&v65,
          v41[0]);
  IsTrustedAndInPackage = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v15,
      (int)&v64);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BBB,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCased);
LABEL_30:
    v17 = v38;
    v38 = 0;
    if ( v17 )
      SRCacheContext_Close();
    goto LABEL_11;
  }
  v57 = 0;
  v56 = 0;
  v59 = 0;
  v60 = 0;
  *(_OWORD *)v61 = 0;
  v62 = 0;
  v58 = 0;
  LOBYTE(v64) = 0;
  IsTrustedAndInPackage = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v38, v16, &v56, &v64);
  if ( IsTrustedAndInPackage < 0 )
  {
    v19 = 11201;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      (int)bIgnoreCasea);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v56);
    goto LABEL_30;
  }
  while ( 1 )
  {
    if ( !(_BYTE)v64 )
    {
      v31 = AipJustFileName(a2);
      AipLogDesktopAppXProcessStartFailure(8, 0, a1, v31, &String2, L"[AiDoesExecutableExistInPackage]");
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v56);
      v32 = v38;
      v38 = 0;
      if ( !v32 )
      {
LABEL_49:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
        v27 = v65;
        v65 = 0;
        if ( v27 )
          SRCacheManager_Close();
        return 0;
      }
      goto LABEL_48;
    }
    v20 = *(_QWORD *)&v61[2];
    if ( *(_QWORD *)&v61[2] )
      break;
LABEL_45:
    ++v39;
    IsTrustedAndInPackage = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v38, v18, &v56, &v64);
    if ( IsTrustedAndInPackage < 0 )
    {
      v19 = 11229;
      goto LABEL_34;
    }
  }
  v21 = -1;
  do
    ++v21;
  while ( *(_WORD *)(*(_QWORD *)&v61[2] + 2 * v21) );
  v52 = v14 + v21 + 4;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpString1,
    0,
    v52);
  v22 = lpString1;
  if ( !lpString1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BCB,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x8007000ELL,
      (int)bIgnoreCasea);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v56);
    v30 = v38;
    v38 = 0;
    if ( v30 )
      SRCacheContext_Close();
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
    v13 = v65;
    v65 = 0;
    goto LABEL_59;
  }
  v23 = L"%s\\%s";
  if ( *(_WORD *)(v12 + 2 * v14 - 2) == 92 )
    v23 = L"%s%s";
  v24 = StringCchPrintfW((unsigned __int16 *)lpString1, v52, v23, v12, v20);
  v25 = v24;
  if ( v24 >= 0 )
  {
    if ( CompareStringOrdinal(v22, -1, a2, -1, 1) != 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
      goto LABEL_45;
    }
    *a3 = 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v56);
    v26 = v38;
    v38 = 0;
    if ( !v26 )
      goto LABEL_49;
LABEL_48:
    SRCacheContext_Close();
    goto LABEL_49;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2BD3,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
    (const char *)(unsigned int)v24,
    bIgnoreCaseb);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v56);
  v28 = v38;
  v38 = 0;
  if ( v28 )
    SRCacheContext_Close();
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
  v29 = v65;
  v65 = 0;
  if ( v29 )
    SRCacheManager_Close();
  return v25;
}

```

## disassembly

```asm
0x1800187f0  mov     [rsp-8+arg_8], rbx
0x1800187f5  push    rbp
0x1800187f6  push    rsi
0x1800187f7  push    rdi
0x1800187f8  push    r12
0x1800187fa  push    r13
0x1800187fc  push    r14
0x1800187fe  push    r15
0x180018800  lea     rbp, [rsp-40h]
0x180018805  sub     rsp, 140h
0x18001880c  xor     r14d, r14d
0x18001880f  mov     rdi, r8
0x180018812  mov     [r8], r14b
0x180018815  mov     r15, rdx
0x180018818  mov     r12, rcx
0x18001881b  test    rcx, rcx
0x18001881e  jz      loc_180018D94
0x180018824  test    rdx, rdx
0x180018827  jz      loc_180018D94
0x18001882d  lea     rax, [rbp+70h+arg_10]
0x180018834  mov     [rbp+70h+arg_10], r14
0x18001883b  lea     rdx, [rbp+70h+var_A0]
0x18001883f  mov     [rbp+70h+var_A8], rax
0x180018843  xor     ecx, ecx
0x180018845  mov     [rbp+70h+var_A0], r14
0x180018849  mov     [rbp+70h+var_98], 1
0x18001884d  call    cs:__imp_SRCacheManager_Open
0x180018853  lea     rcx, [rbp+70h+var_A8]
0x180018857  mov     ebx, eax
0x180018859  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18001885e  test    ebx, ebx
0x180018860  jns     short loc_1800188B2
0x180018862  mov     rcx, [rbp+78h]; this
0x180018866  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001886d  mov     r9d, ebx; char *
0x180018870  mov     edx, 0A5h; void *
0x180018875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001887a  mov     rcx, [rbp+78h]; this
0x18001887e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018885  mov     r9d, ebx; char *
0x180018888  mov     edx, 2B92h; void *
0x18001888d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018892  mov     rcx, [rbp+70h+arg_10]
0x180018899  mov     [rbp+70h+arg_10], r14
0x1800188a0  test    rcx, rcx
0x1800188a3  jz      short loc_1800188AB
0x1800188a5  call    cs:__imp_SRCacheManager_Close
0x1800188ab  mov     eax, ebx
0x1800188ad  jmp     loc_180018D9A
0x1800188b2  xorps   xmm0, xmm0
0x1800188b5  mov     [rsp+170h+var_110], r14
0x1800188ba  lea     rax, [rbp+70h+arg_0]
0x1800188c1  movdqa  xmmword ptr [rsp+170h+var_120], xmm0
0x1800188c7  lea     r9, [rsp+170h+var_120]
0x1800188cc  movdqa  [rbp+70h+var_E0], xmm0
0x1800188d1  mov     r8d, 130h
0x1800188d7  mov     qword ptr [rsp+170h+bIgnoreCase], rax; int
0x1800188dc  mov     rdx, r12
0x1800188df  mov     [rsp+170h+var_108], r14
0x1800188e4  lea     rcx, [rbp+70h+arg_10]
0x1800188eb  mov     [rsp+170h+var_100], r14
0x1800188f0  mov     [rsp+170h+var_F8], r14
0x1800188f5  mov     [rbp+70h+var_F0], r14
0x1800188f9  mov     [rbp+70h+var_E8], r14
0x1800188fd  mov     [rbp+70h+var_D0], r14d
0x180018901  mov     [rbp+70h+var_C8], r14
0x180018905  mov     [rbp+70h+var_C0], r14
0x180018909  mov     byte ptr [rbp+70h+arg_0], r14b
0x180018910  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180018915  mov     ebx, eax
0x180018917  test    eax, eax
0x180018919  jns     short loc_180018942
0x18001891b  mov     edx, 2B9Dh; void *
0x180018920  mov     rcx, [rbp+78h]; this
0x180018924  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18001892b  mov     r9d, ebx; char *
0x18001892e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018933  lea     rcx, [rsp+170h+var_120]; this
0x180018938  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18001893d  jmp     loc_180018892
0x180018942  cmp     byte ptr [rbp+70h+arg_0], r14b
0x180018949  jnz     short loc_18001896A
0x18001894b  mov     r9d, 2; char *
0x180018951  mov     edx, 2BA1h; void *
0x180018956  mov     rcx, [rbp+78h]; this
0x18001895a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018961  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018966  mov     ebx, eax
0x180018968  jmp     short loc_180018933
0x18001896a  mov     r9d, 3
0x180018970  cmp     dword ptr [rsp+170h+var_100+4], r9d
0x180018975  jnz     short loc_18001897E
0x180018977  test    byte ptr [rsp+170h+var_100], 10h
0x18001897c  jnz     short loc_180018985
0x18001897e  test    byte ptr [rsp+170h+var_100], 20h
0x180018983  jz      short loc_1800189D8
0x180018985  lea     r8, [rbp+70h+arg_0]
0x18001898c  mov     [rbp+70h+arg_0], r14d
0x180018993  mov     rdx, r12
0x180018996  mov     rcx, r15
0x180018999  call    cs:__imp_VerifyFileIsTrustedAndInPackage
0x18001899f  mov     ebx, eax
0x1800189a1  test    eax, eax
0x1800189a3  jns     short loc_1800189AF
0x1800189a5  mov     edx, 2BACh
0x1800189aa  jmp     loc_180018920
0x1800189af  cmp     [rbp+70h+arg_0], r14d
0x1800189b6  setnz   al
0x1800189b9  mov     [rdi], al
0x1800189bb  lea     rcx, [rsp+170h+var_120]; this
0x1800189c0  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800189c5  mov     rcx, [rbp+70h+arg_10]
0x1800189cc  mov     [rbp+70h+arg_10], r14
0x1800189d3  jmp     loc_180018C49
0x1800189d8  mov     r13, [rbp+70h+var_E8]
0x1800189dc  test    r13, r13
0x1800189df  jnz     short loc_180018A19
0x1800189e1  mov     rcx, [rbp+78h]; this
0x1800189e5  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800189ec  mov     r9d, 8007000Eh; char *
0x1800189f2  mov     edx, 2BB2h; void *
0x1800189f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800189fc  lea     rcx, [rsp+170h+var_120]; this
0x180018a01  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180018a06  mov     rcx, [rbp+70h+arg_10]
0x180018a0d  mov     [rbp+70h+arg_10], r14
0x180018a14  jmp     loc_180018D2B
0x180018a19  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180018a1d  inc     rsi
0x180018a20  cmp     [r13+rsi*2+0], r14w
0x180018a26  jnz     short loc_180018A1D
0x180018a28  test    rsi, rsi
0x180018a2b  jnz     short loc_180018A37
0x180018a2d  mov     edx, 2BB7h
0x180018a32  jmp     loc_180018956
0x180018a37  mov     r8, [rsp+170h+var_120]; __int64
0x180018a3c  lea     rdx, [rbp+70h+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x180018a43  lea     rcx, [rsp+170h+var_140]; this
0x180018a48  mov     [rsp+170h+var_140], r14
0x180018a4d  mov     [rsp+170h+var_138], r14d
0x180018a52  mov     [rsp+170h+var_130], r14
0x180018a57  call    ?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)
0x180018a5c  mov     ebx, eax
0x180018a5e  test    eax, eax
0x180018a60  jns     short loc_180018AB0
0x180018a62  mov     rcx, [rbp+78h]; this
0x180018a66  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018a6d  mov     r9d, eax; char *
0x180018a70  mov     edx, 47Bh; void *
0x180018a75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a7a  mov     rcx, [rbp+78h]; this
0x180018a7e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018a85  mov     r9d, ebx; char *
0x180018a88  mov     edx, 2BBBh; void *
0x180018a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a92  mov     rcx, [rsp+170h+var_140]
0x180018a97  mov     [rsp+170h+var_140], r14
0x180018a9c  test    rcx, rcx
0x180018a9f  jz      loc_180018933
0x180018aa5  call    cs:__imp_SRCacheContext_Close
0x180018aab  jmp     loc_180018933
0x180018ab0  xorps   xmm0, xmm0
0x180018ab3  mov     [rbp+70h+var_80], r14
0x180018ab7  xorps   xmm1, xmm1
0x180018aba  movdqa  [rbp+70h+var_90], xmm0
0x180018abf  lea     r9, [rbp+70h+arg_0]
0x180018ac6  movdqa  [rbp+70h+var_70], xmm0
0x180018acb  lea     r8, [rbp+70h+var_90]
0x180018acf  movdqa  [rbp+70h+var_60], xmm1
0x180018ad4  lea     rcx, [rsp+170h+var_140]
0x180018ad9  movdqa  xmmword ptr [rbp+70h+var_50], xmm0
0x180018ade  movdqa  [rbp+70h+var_40], xmm1
0x180018ae3  mov     [rbp+70h+var_78], r14
0x180018ae7  mov     byte ptr [rbp+70h+arg_0], r14b
0x180018aee  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180018af3  mov     ebx, eax
0x180018af5  test    eax, eax
0x180018af7  jns     short loc_180018B1F
0x180018af9  mov     edx, 2BC1h; void *
0x180018afe  mov     rcx, [rbp+78h]; this
0x180018b02  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018b09  mov     r9d, ebx; char *
0x180018b0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b11  lea     rcx, [rbp+70h+var_90]; this
0x180018b15  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180018b1a  jmp     loc_180018A92
0x180018b1f  cmp     byte ptr [rbp+70h+arg_0], r14b
0x180018b26  jz      loc_180018D3D
0x180018b2c  mov     r14, qword ptr [rbp+70h+var_50+8]
0x180018b30  xor     ecx, ecx
0x180018b32  test    r14, r14
0x180018b35  jz      loc_180018BD9
0x180018b3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018b3f  inc     rax
0x180018b42  cmp     [r14+rax*2], cx
0x180018b47  jnz     short loc_180018B3F
0x180018b49  add     rax, 4
0x180018b4d  lea     rcx, [rbp+70h+lpString1]
0x180018b54  add     rax, rsi
0x180018b57  xor     edx, edx
0x180018b59  mov     r8, rax
0x180018b5c  mov     [rbp+70h+var_B0], rax
0x180018b60  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180018b65  mov     rbx, [rbp+70h+lpString1]
0x180018b6c  test    rbx, rbx
0x180018b6f  jz      loc_180018CCC
0x180018b75  cmp     word ptr [r13+rsi*2-2], 5Ch ; '\'
0x180018b7c  lea     rax, aSS_0; "%s%s"
0x180018b83  mov     rdx, [rbp+70h+var_B0]; unsigned __int64
0x180018b87  lea     r8, aSS; "%s\\%s"
0x180018b8e  cmovz   r8, rax; unsigned __int16 *
0x180018b92  mov     qword ptr [rsp+170h+bIgnoreCase], r14; int
0x180018b97  mov     r9, r13
0x180018b9a  mov     rcx, rbx; unsigned __int16 *
0x180018b9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018ba2  mov     r14d, eax
0x180018ba5  test    eax, eax
0x180018ba7  js      loc_180018C5D
0x180018bad  or      r9d, 0FFFFFFFFh; cchCount2
0x180018bb1  mov     [rsp+170h+bIgnoreCase], 1; bIgnoreCase
0x180018bb9  or      edx, r9d; cchCount1
0x180018bbc  mov     r8, r15; lpString2
0x180018bbf  mov     rcx, rbx; lpString1
0x180018bc2  call    cs:__imp_CompareStringOrdinal
0x180018bc8  lea     rcx, [rbp+70h+lpString1]
0x180018bcf  cmp     eax, 2
0x180018bd2  jz      short loc_180018C09
0x180018bd4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018bd9  inc     [rsp+170h+var_138]
0x180018bdd  lea     r9, [rbp+70h+arg_0]
0x180018be4  lea     r8, [rbp+70h+var_90]
0x180018be8  lea     rcx, [rsp+170h+var_140]
0x180018bed  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180018bf2  xor     r14d, r14d
0x180018bf5  mov     ebx, eax
0x180018bf7  test    eax, eax
0x180018bf9  jns     loc_180018B1F
0x180018bff  mov     edx, 2BDDh
0x180018c04  jmp     loc_180018AFE
0x180018c09  mov     byte ptr [rdi], 1
0x180018c0c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018c11  lea     rcx, [rbp+70h+var_90]; this
0x180018c15  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180018c1a  mov     rcx, [rsp+170h+var_140]
0x180018c1f  xor     ebx, ebx
0x180018c21  mov     [rsp+170h+var_140], rbx
0x180018c26  test    rcx, rcx
0x180018c29  jz      short loc_180018C31
0x180018c2b  call    cs:__imp_SRCacheContext_Close
0x180018c31  lea     rcx, [rsp+170h+var_120]; this
0x180018c36  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180018c3b  mov     rcx, [rbp+70h+arg_10]
0x180018c42  mov     [rbp+70h+arg_10], rbx
0x180018c49  test    rcx, rcx
0x180018c4c  jz      loc_180018D98
0x180018c52  call    cs:__imp_SRCacheManager_Close
0x180018c58  jmp     loc_180018D98
0x180018c5d  mov     rcx, [rbp+78h]; this
0x180018c61  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018c68  mov     r9d, r14d; char *
0x180018c6b  mov     edx, 2BD3h; void *
0x180018c70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018c75  lea     rcx, [rbp+70h+lpString1]
0x180018c7c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018c81  lea     rcx, [rbp+70h+var_90]; this
0x180018c85  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180018c8a  mov     rcx, [rsp+170h+var_140]
0x180018c8f  xor     ebx, ebx
0x180018c91  mov     [rsp+170h+var_140], rbx
0x180018c96  test    rcx, rcx
0x180018c99  jz      short loc_180018CA1
0x180018c9b  call    cs:__imp_SRCacheContext_Close
0x180018ca1  lea     rcx, [rsp+170h+var_120]; this
0x180018ca6  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180018cab  mov     rcx, [rbp+70h+arg_10]
0x180018cb2  mov     [rbp+70h+arg_10], rbx
0x180018cb9  test    rcx, rcx
0x180018cbc  jz      short loc_180018CC4
0x180018cbe  call    cs:__imp_SRCacheManager_Close
0x180018cc4  mov     eax, r14d
0x180018cc7  jmp     loc_180018D9A
0x180018ccc  mov     rcx, [rbp+78h]; this
0x180018cd0  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018cd7  mov     r9d, 8007000Eh; char *
0x180018cdd  mov     edx, 2BCBh; void *
0x180018ce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ce7  lea     rcx, [rbp+70h+lpString1]
0x180018cee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018cf3  lea     rcx, [rbp+70h+var_90]; this
0x180018cf7  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180018cfc  mov     rcx, [rsp+170h+var_140]
0x180018d01  xor     ebx, ebx
0x180018d03  mov     [rsp+170h+var_140], rbx
0x180018d08  test    rcx, rcx
0x180018d0b  jz      short loc_180018D13
0x180018d0d  call    cs:__imp_SRCacheContext_Close
0x180018d13  lea     rcx, [rsp+170h+var_120]; this
0x180018d18  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180018d1d  mov     rcx, [rbp+70h+arg_10]
0x180018d24  mov     [rbp+70h+arg_10], rbx
  ... truncated ...
```
