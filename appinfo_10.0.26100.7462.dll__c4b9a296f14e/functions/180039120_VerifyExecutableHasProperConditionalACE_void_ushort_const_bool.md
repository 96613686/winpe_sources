# VerifyExecutableHasProperConditionalACE(void *,ushort const *,bool &)

- ea: `0x180039120`
- end: `0x1800396e3`
- name: `?VerifyExecutableHasProperConditionalACE@@YAJPEAXPEBGAEA_N@Z`
- size: `1475`
- prototype: `int(void *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180032ad0`

## callees

- `0x180005880`
- `0x180007b30`
- `0x180007c78`
- `0x1800096c0`
- `0x18000dca8`
- `0x18000dd90`
- `0x180012634`
- `0x1800182bc`
- `0x180018530`
- `0x18001b494`
- `0x180026910`
- `0x18002c448`
- `0x18002dbb8`
- `0x18003299c`
- `0x18003888c`
- `0x1800388f8`
- `0x180038934`
- `0x180039120`
- `0x1800398d0`
- `0x180044a20`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800395ee`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800395ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800391d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180039277`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180039535`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800396aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800391d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180039277`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180039535`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800396aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003944b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039500`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039675`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003944b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039500`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039675`

## string_xrefs

- `0x180039177`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800391ae`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800391fe`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003924c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800392a4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039310`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039388`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800393c5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039429`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800394df`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039605`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039646`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall VerifyExecutableHasProperConditionalACE(void *a1, const unsigned __int16 *a2, bool *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  __int64 v10; // rcx
  int token_information; // eax
  void *v12; // rbx
  void *v13; // rdx
  int v14; // eax
  int Package; // edi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned __int16 *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rax
  unsigned __int16 *v24; // rcx
  __int64 v25; // rcx
  unsigned __int16 v26; // r14
  unsigned __int64 v27; // rsi
  unsigned __int16 *v28; // rdi
  unsigned int v29; // eax
  int v30; // eax
  unsigned __int16 *v31; // rcx
  __int64 v32; // rcx
  unsigned int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  unsigned int packageRelativeApplicationIda; // [rsp+20h] [rbp-E0h]
  bool v35; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  int v38[4]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v39[2]; // [rsp+58h] [rbp-A8h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+68h] [rbp-98h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  __int128 v43; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+98h] [rbp-68h]
  __int64 v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  int v51; // [rsp+D0h] [rbp-30h]
  __int64 v52; // [rsp+D8h] [rbp-28h]
  int v53[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v54; // [rsp+F0h] [rbp-10h]
  __int64 v55; // [rsp+F8h] [rbp-8h]
  __int128 v56; // [rsp+100h] [rbp+0h]
  __int128 v57; // [rsp+110h] [rbp+10h]
  unsigned __int16 *v58[2]; // [rsp+120h] [rbp+20h]
  __int128 v59; // [rsp+130h] [rbp+30h]
  WCHAR packageFamilyName[72]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR v61[72]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a3 = 0;
  v6 = StringCchLengthW(a2, (unsigned __int64)a2, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1917,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v6,
      packageRelativeApplicationId);
    return v7;
  }
  v36 = 0;
  v9 = StateRepository::Cache::Manager_NoThrow::Open(&v36);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1919,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v9,
      packageRelativeApplicationId);
LABEL_6:
    v10 = v36;
    v36 = 0;
    if ( v10 )
      SRCacheManager_Close();
    return v7;
  }
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a1);
  v7 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191D,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)token_information,
      packageRelativeApplicationId);
    if ( Block )
      operator delete(Block);
    goto LABEL_6;
  }
  v12 = Block;
  v13 = *(void **)Block;
  v42 = 0;
  v14 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
          (struct StateRepository::Cache::Manager_NoThrow *)&v36,
          v13,
          &v42);
  Package = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1921,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v14,
      packageRelativeApplicationId);
LABEL_13:
    operator delete(v12);
    v16 = v36;
    v36 = 0;
    if ( v16 )
      SRCacheManager_Close();
    return (unsigned int)Package;
  }
  if ( !v42 )
  {
    Package = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1924,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)2,
                packageRelativeApplicationId);
    goto LABEL_13;
  }
  v54 = 0;
  *(_OWORD *)v53 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  *(_OWORD *)v58 = 0;
  v59 = 0;
  v35 = 0;
  v17 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(&v36, v42, a2, 0);
  Package = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192A,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v17,
      (int)v53);
LABEL_20:
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v53);
    goto LABEL_13;
  }
  v44 = 0;
  v43 = 0;
  v50 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v51 = 0;
  v52 = 0;
  Package = StateRepository::Cache::Entity::Application_NoThrow::GetPackage(
              (StateRepository::Cache::Entity::Application_NoThrow *)v53,
              (struct StateRepository::Cache::Manager_NoThrow *)&v36,
              (struct StateRepository::Cache::Entity::Package_NoThrow *)&v43,
              &v35);
  if ( Package < 0 )
  {
    v18 = 6445;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      (int)v53);
LABEL_24:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
    goto LABEL_20;
  }
  if ( !v35 )
  {
    Package = -2147023728;
    v18 = 6446;
    goto LABEL_23;
  }
  if ( (v45 & 0x20000000000000LL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192F,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v53);
LABEL_46:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v53);
    operator delete(v12);
    v25 = v36;
    v36 = 0;
    if ( v25 )
      SRCacheManager_Close();
    return 2147942487LL;
  }
  *(_OWORD *)v38 = 0;
  *(_OWORD *)v39 = 0;
  Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v36, 0, v43);
  if ( Package < 0 )
  {
    v19 = 6454;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      (int)v38);
    goto LABEL_32;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl) )
  {
    if ( v35 )
      goto LABEL_40;
    Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v36, v42, v43);
    if ( Package < 0 )
    {
      v19 = 6462;
      goto LABEL_31;
    }
  }
  if ( !v35 )
  {
    v21 = 6466;
    goto LABEL_44;
  }
LABEL_40:
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( v39[1][v23] );
  if ( !v23 )
  {
    v21 = 6473;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v38);
    v24 = v39[1];
    v39[1] = 0;
    if ( v24 )
      SRCache_Free();
    goto LABEL_46;
  }
  v26 = v39[1][v23 - 1];
  do
    ++v22;
  while ( v58[1][v22] );
  v27 = 2 * ((_DWORD)v22 + (_DWORD)v23 + (unsigned int)(v26 != 92)) + 2;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &Block,
    0,
    v27);
  v28 = (unsigned __int16 *)Block;
  StringCbCopyW((unsigned __int16 *)Block, (unsigned int)v27, v39[1]);
  if ( v26 != 92 )
    StringCbCatW(v28, (unsigned int)v27, L"\\");
  StringCbCatW(v28, v27, v58[1]);
  packageFamilyNameLength = 65;
  packageRelativeApplicationIdLength = 65;
  v29 = ParseApplicationUserModelId(
          a2,
          &packageFamilyNameLength,
          packageFamilyName,
          &packageRelativeApplicationIdLength,
          v61);
  if ( v29 )
  {
    Package = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x195F,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)v29,
                packageRelativeApplicationIda);
LABEL_55:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Block);
LABEL_32:
    v20 = v39[1];
    v39[1] = 0;
    if ( v20 )
      SRCache_Free();
    goto LABEL_24;
  }
  v30 = CheckPackageFamilyNameACEFromPath(v28, packageFamilyName, a3);
  Package = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1962,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v30,
      packageRelativeApplicationIda);
    goto LABEL_55;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Block);
  v31 = v39[1];
  v39[1] = 0;
  if ( v31 )
    SRCache_Free();
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v53);
  operator delete(v12);
  v32 = v36;
  v36 = 0;
  if ( v32 )
    SRCacheManager_Close();
  return 0;
}

```

## disassembly

```asm
0x180039120  mov     [rsp-8+arg_18], rbx
0x180039125  push    rbp
0x180039126  push    rsi
0x180039127  push    rdi
0x180039128  push    r12
0x18003912a  push    r13
0x18003912c  push    r14
0x18003912e  push    r15
0x180039130  lea     rbp, [rsp-170h]
0x180039138  sub     rsp, 270h
0x18003913f  mov     rax, cs:__security_cookie
0x180039146  xor     rax, rsp
0x180039149  mov     [rbp+1A0h+var_40], rax
0x180039150  mov     rdi, rcx
0x180039153  xor     r13d, r13d
0x180039156  mov     [r8], r13b
0x180039159  mov     r12, r8
0x18003915c  xor     r8d, r8d; unsigned __int64 *
0x18003915f  mov     rcx, rdx; unsigned __int16 *
0x180039162  mov     r15, rdx
0x180039165  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003916a  mov     ebx, eax
0x18003916c  test    eax, eax
0x18003916e  jns     short loc_180039192
0x180039170  mov     rcx, [rbp+1A8h]; this
0x180039177  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003917e  mov     r9d, eax; char *
0x180039181  mov     edx, 1917h; void *
0x180039186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003918b  mov     eax, ebx
0x18003918d  jmp     loc_1800396B8
0x180039192  lea     rcx, [rsp+2A0h+var_268]
0x180039197  mov     [rsp+2A0h+var_268], r13
0x18003919c  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x1800391a1  mov     ebx, eax
0x1800391a3  test    eax, eax
0x1800391a5  jns     short loc_1800391DF
0x1800391a7  mov     rcx, [rbp+1A8h]; this
0x1800391ae  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800391b5  mov     r9d, eax; char *
0x1800391b8  mov     edx, 1919h; void *
0x1800391bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800391c2  mov     rcx, [rsp+2A0h+var_268]
0x1800391c7  mov     [rsp+2A0h+var_268], r13
0x1800391cc  test    rcx, rcx
0x1800391cf  jz      short loc_18003918B
0x1800391d1  call    cs:__imp_SRCacheManager_Close
0x1800391d8  nop     dword ptr [rax+rax+00h]
0x1800391dd  jmp     short loc_18003918B
0x1800391df  mov     rdx, rdi
0x1800391e2  mov     [rsp+2A0h+Block], r13
0x1800391e7  lea     rcx, [rsp+2A0h+Block]
0x1800391ec  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800391f1  mov     ebx, eax
0x1800391f3  test    eax, eax
0x1800391f5  jns     short loc_180039223
0x1800391f7  mov     rcx, [rbp+1A8h]; this
0x1800391fe  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039205  mov     r9d, eax; char *
0x180039208  mov     edx, 191Dh; void *
0x18003920d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039212  mov     rcx, [rsp+2A0h+Block]; Block
0x180039217  test    rcx, rcx
0x18003921a  jz      short loc_1800391C2
0x18003921c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039221  jmp     short loc_1800391C2
0x180039223  mov     rbx, [rsp+2A0h+Block]
0x180039228  lea     r8, [rsp+2A0h+var_230]; __int64 *
0x18003922d  lea     rcx, [rsp+2A0h+var_268]; struct StateRepository::Cache::Manager_NoThrow *
0x180039232  mov     rdx, [rbx]; void *
0x180039235  mov     [rsp+2A0h+var_230], r13
0x18003923a  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18003923f  mov     edi, eax
0x180039241  test    eax, eax
0x180039243  jns     short loc_18003928A
0x180039245  mov     rcx, [rbp+1A8h]; this
0x18003924c  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039253  mov     r9d, eax; char *
0x180039256  mov     edx, 1921h; void *
0x18003925b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039260  mov     rcx, rbx; Block
0x180039263  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039268  mov     rcx, [rsp+2A0h+var_268]
0x18003926d  mov     [rsp+2A0h+var_268], r13
0x180039272  test    rcx, rcx
0x180039275  jz      short loc_180039283
0x180039277  call    cs:__imp_SRCacheManager_Close
0x18003927e  nop     dword ptr [rax+rax+00h]
0x180039283  mov     eax, edi
0x180039285  jmp     loc_1800396B8
0x18003928a  mov     rdx, [rsp+2A0h+var_230]
0x18003928f  test    rdx, rdx
0x180039292  jnz     short loc_1800392B4
0x180039294  mov     rcx, [rbp+1A8h]; this
0x18003929b  lea     r9d, [rdx+2]; char *
0x18003929f  mov     edx, 1924h; void *
0x1800392a4  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800392ab  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800392b0  mov     edi, eax
0x1800392b2  jmp     short loc_180039260
0x1800392b4  xorps   xmm0, xmm0
0x1800392b7  mov     [rbp+1A0h+var_1B0], r13
0x1800392bb  xorps   xmm1, xmm1
0x1800392be  movdqa  xmmword ptr [rbp+1A0h+var_1C0], xmm0
0x1800392c3  lea     rax, [rsp+2A0h+var_270]
0x1800392c8  mov     [rbp+1A0h+var_1A8], r13
0x1800392cc  mov     [rsp+2A0h+var_278], rax
0x1800392d1  lea     rcx, [rsp+2A0h+var_268]
0x1800392d6  lea     rax, [rbp+1A0h+var_1C0]
0x1800392da  movdqa  [rbp+1A0h+var_1A0], xmm0
0x1800392df  xor     r9d, r9d
0x1800392e2  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x1800392e7  mov     r8, r15
0x1800392ea  movdqa  [rbp+1A0h+var_190], xmm1
0x1800392ef  movdqa  xmmword ptr [rbp+1A0h+var_180], xmm0
0x1800392f4  movdqa  [rbp+1A0h+var_170], xmm1
0x1800392f9  mov     [rsp+2A0h+var_270], r13b
0x1800392fe  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180039303  mov     edi, eax
0x180039305  test    eax, eax
0x180039307  jns     short loc_180039332
0x180039309  mov     rcx, [rbp+1A8h]; this
0x180039310  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039317  mov     r9d, eax; char *
0x18003931a  mov     edx, 192Ah; void *
0x18003931f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039324  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180039328  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18003932d  jmp     loc_180039260
0x180039332  xorps   xmm0, xmm0
0x180039335  mov     [rbp+1A0h+var_210], r13
0x180039339  lea     r9, [rsp+2A0h+var_270]; bool *
0x18003933e  movdqa  [rbp+1A0h+var_220], xmm0
0x180039343  lea     r8, [rbp+1A0h+var_220]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x180039347  movdqa  [rbp+1A0h+var_1E0], xmm0
0x18003934c  lea     rdx, [rsp+2A0h+var_268]; struct StateRepository::Cache::Manager_NoThrow *
0x180039351  mov     [rbp+1A0h+var_208], r13
0x180039355  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180039359  mov     [rbp+1A0h+var_200], r13
0x18003935d  mov     [rbp+1A0h+var_1F8], r13
0x180039361  mov     [rbp+1A0h+var_1F0], r13
0x180039365  mov     [rbp+1A0h+var_1E8], r13
0x180039369  mov     [rbp+1A0h+var_1D0], r13d
0x18003936d  mov     [rbp+1A0h+var_1C8], r13
0x180039371  call    ?GetPackage@Application_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180039376  mov     edi, eax
0x180039378  test    eax, eax
0x18003937a  jns     short loc_1800393A2
0x18003937c  mov     edx, 192Dh; void *
0x180039381  mov     rcx, [rbp+1A8h]; this
0x180039388  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003938f  mov     r9d, edi; char *
0x180039392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039397  lea     rcx, [rbp+1A0h+var_220]; this
0x18003939b  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800393a0  jmp     short loc_180039324
0x1800393a2  cmp     [rsp+2A0h+var_270], r13b
0x1800393a7  jnz     short loc_1800393B5
0x1800393a9  mov     edi, 80070490h
0x1800393ae  mov     edx, 192Eh
0x1800393b3  jmp     short loc_180039381
0x1800393b5  test    dword ptr [rbp+1A0h+var_208+4], 200000h
0x1800393bc  jnz     short loc_1800393E1
0x1800393be  mov     rcx, [rbp+1A8h]; this
0x1800393c5  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800393cc  mov     r9d, 80070057h; char *
0x1800393d2  mov     edx, 192Fh; void *
0x1800393d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800393dc  jmp     loc_18003950C
0x1800393e1  mov     r8, qword ptr [rbp+1A0h+var_220]
0x1800393e5  lea     rax, [rsp+2A0h+var_270]
0x1800393ea  mov     [rsp+2A0h+var_278], rax
0x1800393ef  lea     rcx, [rsp+2A0h+var_268]
0x1800393f4  lea     rax, [rsp+2A0h+var_258]
0x1800393f9  xorps   xmm0, xmm0
0x1800393fc  xorps   xmm1, xmm1
0x1800393ff  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x180039404  xor     edx, edx
0x180039406  movdqu  xmmword ptr [rsp+2A0h+var_258], xmm0
0x18003940c  movdqu  xmmword ptr [rsp+2A0h+var_248], xmm1
0x180039412  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x180039417  mov     edi, eax
0x180039419  test    eax, eax
0x18003941b  jns     short loc_18003945C
0x18003941d  mov     edx, 1936h; void *
0x180039422  mov     rcx, [rbp+1A8h]; this
0x180039429  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039430  mov     r9d, edi; char *
0x180039433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039438  mov     rcx, [rsp+2A0h+var_248+8]
0x18003943d  mov     [rsp+2A0h+var_248+8], r13
0x180039442  test    rcx, rcx
0x180039445  jz      loc_180039397
0x18003944b  call    cs:__imp_SRCache_Free
0x180039452  nop     dword ptr [rax+rax+00h]
0x180039457  jmp     loc_180039397
0x18003945c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch> `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl(void)'::`2'::impl
0x180039463  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(void)
0x180039468  test    al, al
0x18003946a  jz      short loc_1800394AA
0x18003946c  cmp     [rsp+2A0h+var_270], r13b
0x180039471  jnz     short loc_1800394B8
0x180039473  mov     r8, qword ptr [rbp+1A0h+var_220]
0x180039477  lea     rax, [rsp+2A0h+var_270]
0x18003947c  mov     rdx, [rsp+2A0h+var_230]
0x180039481  lea     rcx, [rsp+2A0h+var_268]
0x180039486  mov     [rsp+2A0h+var_278], rax
0x18003948b  lea     rax, [rsp+2A0h+var_258]
0x180039490  mov     [rsp+2A0h+packageRelativeApplicationId], rax
0x180039495  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18003949a  mov     edi, eax
0x18003949c  test    eax, eax
0x18003949e  jns     short loc_1800394AA
0x1800394a0  mov     edx, 193Eh
0x1800394a5  jmp     loc_180039422
0x1800394aa  cmp     [rsp+2A0h+var_270], r13b
0x1800394af  jnz     short loc_1800394B8
0x1800394b1  mov     edx, 1942h
0x1800394b6  jmp     short loc_1800394D8
0x1800394b8  mov     rcx, [rsp+2A0h+var_248+8]
0x1800394bd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800394c1  mov     rax, rdx
0x1800394c4  inc     rax
0x1800394c7  cmp     [rcx+rax*2], r13w
0x1800394cc  jnz     short loc_1800394C4
0x1800394ce  test    rax, rax
0x1800394d1  jnz     short loc_18003954B
0x1800394d3  mov     edx, 1949h; void *
0x1800394d8  mov     rcx, [rbp+1A8h]; this
0x1800394df  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800394e6  mov     r9d, 80070057h; char *
0x1800394ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800394f1  mov     rcx, [rsp+2A0h+var_248+8]
0x1800394f6  mov     [rsp+2A0h+var_248+8], r13
0x1800394fb  test    rcx, rcx
0x1800394fe  jz      short loc_18003950C
0x180039500  call    cs:__imp_SRCache_Free
0x180039507  nop     dword ptr [rax+rax+00h]
0x18003950c  lea     rcx, [rbp+1A0h+var_220]; this
0x180039510  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180039515  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180039519  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18003951e  mov     rcx, rbx; Block
0x180039521  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039526  mov     rcx, [rsp+2A0h+var_268]
0x18003952b  mov     [rsp+2A0h+var_268], r13
0x180039530  test    rcx, rcx
0x180039533  jz      short loc_180039541
0x180039535  call    cs:__imp_SRCacheManager_Close
0x18003953c  nop     dword ptr [rax+rax+00h]
0x180039541  mov     eax, 80070057h
0x180039546  jmp     loc_1800396B8
0x18003954b  movzx   r14d, word ptr [rcx+rax*2-2]
0x180039551  mov     rcx, [rbp+1A0h+var_180+8]
0x180039555  inc     rdx
0x180039558  cmp     [rcx+rdx*2], r13w
0x18003955d  jnz     short loc_180039555
0x18003955f  mov     rcx, r13
0x180039562  cmp     r14w, 5Ch ; '\'
0x180039567  setnz   cl
0x18003956a  add     rax, rdx
0x18003956d  add     rcx, rax
0x180039570  xor     edx, edx
0x180039572  lea     rax, ds:2[rcx*2]
0x18003957a  mov     r8d, eax
0x18003957d  lea     rcx, [rsp+2A0h+Block]
0x180039582  mov     esi, eax
0x180039584  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180039589  mov     rdi, [rsp+2A0h+Block]
0x18003958e  mov     edx, esi; unsigned __int64
0x180039590  mov     r8, [rsp+2A0h+var_248+8]; unsigned __int16 *
0x180039595  mov     rcx, rdi; unsigned __int16 *
0x180039598  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003959d  cmp     r14w, 5Ch ; '\'
0x1800395a2  jz      short loc_1800395B5
0x1800395a4  lea     r8, asc_18004D1CC; "\\"
0x1800395ab  mov     edx, esi; unsigned __int64
0x1800395ad  mov     rcx, rdi; unsigned __int16 *
0x1800395b0  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800395b5  mov     r8, [rbp+1A0h+var_180+8]; unsigned __int16 *
0x1800395b9  mov     rdx, rsi; unsigned __int64
0x1800395bc  mov     rcx, rdi; unsigned __int16 *
0x1800395bf  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800395c4  mov     eax, 41h ; 'A'
0x1800395c9  lea     r9, [rsp+2A0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x1800395ce  mov     [rsp+2A0h+packageFamilyNameLength], eax
0x1800395d2  lea     r8, [rbp+1A0h+packageFamilyName]; packageFamilyName
0x1800395d6  mov     [rsp+2A0h+packageRelativeApplicationIdLength], eax
0x1800395da  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800395df  lea     rax, [rbp+1A0h+var_D0]
0x1800395e6  mov     rcx, r15; applicationUserModelId
0x1800395e9  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x1800395ee  call    cs:__imp_ParseApplicationUserModelId
0x1800395f5  nop     dword ptr [rax+rax+00h]
0x1800395fa  test    eax, eax
0x1800395fc  jz      short loc_18003962A
0x1800395fe  mov     rcx, [rbp+1A8h]; this
0x180039605  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003960c  mov     r9d, eax; char *
0x18003960f  mov     edx, 195Fh; void *
  ... truncated ...
```
