# GetFullPathToAUMIDExecutable(void *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180035698`
- end: `0x180035bb7`
- name: `?GetFullPathToAUMIDExecutable@@YAJPEAXPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1311`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180035dbc`

## callees

- `0x180005160`
- `0x180005220`
- `0x18000720c`
- `0x18000b0a4`
- `0x18000b2c0`
- `0x18000d3d0`
- `0x180011414`
- `0x180018dbc`
- `0x180019fa0`
- `0x18001d494`
- `0x18001e7bc`
- `0x180031f90`
- `0x180035698`
- `0x180035c84`
- `0x180038880`
- `0x18003b2ac`
- `0x18003b320`
- `0x18003b370`
- `0x18003c73c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180035762`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180035aa8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180035b93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180035762`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180035aa8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180035b93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800359c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035a73`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035b5e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800359c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035a73`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035b5e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18003570e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18003570e`

## string_xrefs

- `0x180035727`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1800356d7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003573f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003578a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800357d9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180035812`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003587f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800358fe`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003593f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800359a3`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180035a52`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall GetFullPathToAUMIDExecutable(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  int v6; // eax
  int Package; // ebx
  __int64 v9; // rcx
  int token_information; // eax
  void *v11; // rcx
  void *v12; // rdi
  void *v13; // rdx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int16 *v23; // rcx
  __int64 v24; // rcx
  unsigned __int16 v25; // r14
  int v26; // r8d
  unsigned __int64 v27; // rsi
  unsigned __int16 *v28; // rbx
  unsigned __int16 *v29; // rcx
  __int64 v30; // rcx
  unsigned int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  int v35[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v36[2]; // [rsp+50h] [rbp-B0h]
  __int128 v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h]
  __int64 v39; // [rsp+78h] [rbp-88h]
  __int64 v40; // [rsp+80h] [rbp-80h]
  __int64 v41; // [rsp+88h] [rbp-78h]
  __int64 v42; // [rsp+90h] [rbp-70h]
  __int64 v43; // [rsp+98h] [rbp-68h]
  __int128 v44; // [rsp+A0h] [rbp-60h]
  int v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  int v48[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  __int128 v51; // [rsp+F0h] [rbp-10h]
  __int128 v52; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v53[2]; // [rsp+110h] [rbp+10h]
  __int128 v54; // [rsp+120h] [rbp+20h]
  __int64 *v55; // [rsp+130h] [rbp+30h] BYREF
  __int64 v56; // [rsp+138h] [rbp+38h] BYREF
  char v57; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  void *Block; // [rsp+198h] [rbp+98h] BYREF

  v6 = StringCchLengthW(a2, (unsigned __int64)a2, 0);
  Package = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BB1,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v6,
      v31);
    return (unsigned int)Package;
  }
  v33 = 0;
  v55 = &v33;
  v56 = 0;
  v57 = 1;
  Package = SRCacheManager_Open(0, &v56);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v55);
  if ( Package < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)Package,
      v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BB3,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      v32);
    goto LABEL_6;
  }
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a1);
  Package = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BB7,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)token_information,
      v31);
    v11 = Block;
    if ( !Block )
      goto LABEL_6;
    goto LABEL_10;
  }
  v12 = Block;
  v13 = *(void **)Block;
  v34 = 0;
  v14 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
          (struct StateRepository::Cache::Manager_NoThrow *)&v33,
          v13,
          &v34);
  Package = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BBB,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v14,
      v31);
LABEL_13:
    if ( !v12 )
    {
LABEL_6:
      v9 = v33;
      v33 = 0;
      if ( v9 )
        SRCacheManager_Close();
      return (unsigned int)Package;
    }
    v11 = v12;
LABEL_10:
    operator delete(v11);
    goto LABEL_6;
  }
  if ( !v34 )
  {
    Package = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1BBE,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)2,
                v31);
    goto LABEL_13;
  }
  v49 = 0;
  *(_OWORD *)v48 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  *(_OWORD *)v53 = 0;
  v54 = 0;
  LOBYTE(Block) = 0;
  v15 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(&v33, v34, a2, 0);
  Package = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC4,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v15,
      (int)v48);
LABEL_19:
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v48);
    goto LABEL_13;
  }
  v38 = 0;
  v37 = 0;
  v44 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  Package = StateRepository::Cache::Entity::Application_NoThrow::GetPackage(
              (StateRepository::Cache::Entity::Application_NoThrow *)v48,
              (struct StateRepository::Cache::Manager_NoThrow *)&v33,
              (struct StateRepository::Cache::Entity::Package_NoThrow *)&v37,
              (bool *)&Block);
  if ( Package < 0 )
  {
    v16 = 7111;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      (int)v48);
LABEL_23:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v37);
    goto LABEL_19;
  }
  if ( !(_BYTE)Block )
  {
    Package = -2147023728;
    v16 = 7112;
    goto LABEL_22;
  }
  if ( (v39 & 0x20000000000000LL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC9,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v48);
LABEL_43:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v37);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v48);
    if ( v12 )
      operator delete(v12);
    v24 = v33;
    v33 = 0;
    if ( v24 )
      SRCacheManager_Close();
    return 2147942487LL;
  }
  *(_OWORD *)v35 = 0;
  *(_OWORD *)v36 = 0;
  Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v33, 0, v37);
  if ( Package < 0 )
  {
    v18 = 7120;
    goto LABEL_30;
  }
  LOBYTE(v17) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl,
    v17);
  if ( !(_BYTE)Block )
  {
    Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v33, v34, v37);
    if ( Package < 0 )
    {
      v18 = 7128;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)Package,
        (int)v35);
      v19 = v36[1];
      v36[1] = 0;
      if ( v19 )
        SRCache_Free();
      goto LABEL_23;
    }
    if ( !(_BYTE)Block )
    {
      v20 = 7132;
      goto LABEL_41;
    }
  }
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( v36[1][v22] );
  if ( !v22 )
  {
    v20 = 7139;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v35);
    v23 = v36[1];
    v36[1] = 0;
    if ( v23 )
      SRCache_Free();
    goto LABEL_43;
  }
  v25 = v36[1][v22 - 1];
  v26 = 0;
  do
    ++v21;
  while ( v53[1][v21] );
  LOBYTE(v26) = v25 != 92;
  v27 = (unsigned int)(2 * (v21 + v26 + v22) + 2);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &Block,
    0,
    v27);
  v28 = (unsigned __int16 *)Block;
  StringCbCopyW((unsigned __int16 *)Block, (unsigned int)v27, v36[1]);
  if ( v25 != 92 )
    StringCbCatW(v28, (unsigned int)v27, L"\\");
  StringCbCatW(v28, v27, v53[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
    a3,
    &Block);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Block);
  v29 = v36[1];
  v36[1] = 0;
  if ( v29 )
    SRCache_Free();
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v37);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v48);
  if ( v12 )
    operator delete(v12);
  v30 = v33;
  v33 = 0;
  if ( v30 )
    SRCacheManager_Close();
  return 0;
}

```

## disassembly

```asm
0x180035698  mov     [rsp-8+arg_0], rbx
0x18003569d  mov     [rsp-8+arg_8], rsi
0x1800356a2  push    rbp
0x1800356a3  push    rdi
0x1800356a4  push    r12
0x1800356a6  push    r14
0x1800356a8  push    r15
0x1800356aa  lea     rbp, [rsp-50h]
0x1800356af  sub     rsp, 150h
0x1800356b6  mov     rdi, rcx
0x1800356b9  mov     r15, r8
0x1800356bc  xor     r8d, r8d; unsigned __int64 *
0x1800356bf  mov     rcx, rdx; unsigned __int16 *
0x1800356c2  mov     rsi, rdx
0x1800356c5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800356ca  xor     r12d, r12d
0x1800356cd  mov     ebx, eax
0x1800356cf  test    eax, eax
0x1800356d1  jns     short loc_1800356F2
0x1800356d3  mov     rcx, [rbp+78h]; this
0x1800356d7  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800356de  mov     r9d, eax; char *
0x1800356e1  mov     edx, 1BB1h; void *
0x1800356e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800356eb  mov     eax, ebx
0x1800356ed  jmp     loc_180035B9B
0x1800356f2  lea     rax, [rsp+170h+var_140]
0x1800356f7  mov     [rsp+170h+var_140], r12
0x1800356fc  lea     rdx, [rbp+70h+var_38]
0x180035700  mov     [rbp+70h+var_40], rax
0x180035704  xor     ecx, ecx
0x180035706  mov     [rbp+70h+var_38], r12
0x18003570a  mov     [rbp+70h+var_30], 1
0x18003570e  call    cs:__imp_SRCacheManager_Open
0x180035714  lea     rcx, [rbp+70h+var_40]
0x180035718  mov     ebx, eax
0x18003571a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18003571f  test    ebx, ebx
0x180035721  jns     short loc_18003576A
0x180035723  mov     rcx, [rbp+78h]; this
0x180035727  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003572e  mov     r9d, ebx; char *
0x180035731  mov     edx, 0A5h; void *
0x180035736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003573b  mov     rcx, [rbp+78h]; this
0x18003573f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035746  mov     r9d, ebx; char *
0x180035749  mov     edx, 1BB3h; void *
0x18003574e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035753  mov     rcx, [rsp+170h+var_140]
0x180035758  mov     [rsp+170h+var_140], r12
0x18003575d  test    rcx, rcx
0x180035760  jz      short loc_1800356EB
0x180035762  call    cs:__imp_SRCacheManager_Close
0x180035768  jmp     short loc_1800356EB
0x18003576a  mov     rdx, rdi
0x18003576d  mov     [rbp+70h+Block], r12
0x180035774  lea     rcx, [rbp+70h+Block]
0x18003577b  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180035780  mov     ebx, eax
0x180035782  test    eax, eax
0x180035784  jns     short loc_1800357B1
0x180035786  mov     rcx, [rbp+78h]; this
0x18003578a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035791  mov     r9d, eax; char *
0x180035794  mov     edx, 1BB7h; void *
0x180035799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003579e  mov     rcx, [rbp+70h+Block]; Block
0x1800357a5  test    rcx, rcx
0x1800357a8  jz      short loc_180035753
0x1800357aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800357af  jmp     short loc_180035753
0x1800357b1  mov     rdi, [rbp+70h+Block]
0x1800357b8  lea     r8, [rsp+170h+var_138]; __int64 *
0x1800357bd  lea     rcx, [rsp+170h+var_140]; struct StateRepository::Cache::Manager_NoThrow *
0x1800357c2  mov     rdx, [rdi]; void *
0x1800357c5  mov     [rsp+170h+var_138], r12
0x1800357ca  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x1800357cf  mov     ebx, eax
0x1800357d1  test    eax, eax
0x1800357d3  jns     short loc_1800357FB
0x1800357d5  mov     rcx, [rbp+78h]; this
0x1800357d9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800357e0  mov     r9d, eax; char *
0x1800357e3  mov     edx, 1BBBh; void *
0x1800357e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800357ed  test    rdi, rdi
0x1800357f0  jz      loc_180035753
0x1800357f6  mov     rcx, rdi
0x1800357f9  jmp     short loc_1800357AA
0x1800357fb  mov     rdx, [rsp+170h+var_138]
0x180035800  test    rdx, rdx
0x180035803  jnz     short loc_180035822
0x180035805  mov     rcx, [rbp+78h]; this
0x180035809  lea     r9d, [rdx+2]; char *
0x18003580d  mov     edx, 1BBEh; void *
0x180035812  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035819  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003581e  mov     ebx, eax
0x180035820  jmp     short loc_1800357ED
0x180035822  xorps   xmm0, xmm0
0x180035825  mov     [rbp+70h+var_90], r12
0x180035829  xorps   xmm1, xmm1
0x18003582c  movdqa  xmmword ptr [rbp+70h+var_A0], xmm0
0x180035831  lea     rax, [rbp+70h+Block]
0x180035838  mov     [rbp+70h+var_88], r12
0x18003583c  mov     [rsp+170h+var_148], rax
0x180035841  lea     rcx, [rsp+170h+var_140]
0x180035846  lea     rax, [rbp+70h+var_A0]
0x18003584a  movdqa  [rbp+70h+var_80], xmm0
0x18003584f  xor     r9d, r9d
0x180035852  mov     qword ptr [rsp+170h+var_150], rax; int
0x180035857  mov     r8, rsi
0x18003585a  movdqa  [rbp+70h+var_70], xmm1
0x18003585f  movdqa  xmmword ptr [rbp+70h+var_60], xmm0
0x180035864  movdqa  [rbp+70h+var_50], xmm1
0x180035869  mov     byte ptr [rbp+70h+Block], r12b
0x180035870  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180035875  mov     ebx, eax
0x180035877  test    eax, eax
0x180035879  jns     short loc_1800358A1
0x18003587b  mov     rcx, [rbp+78h]; this
0x18003587f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035886  mov     r9d, eax; char *
0x180035889  mov     edx, 1BC4h; void *
0x18003588e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035893  lea     rcx, [rbp+70h+var_A0]; this
0x180035897  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18003589c  jmp     loc_1800357ED
0x1800358a1  xorps   xmm0, xmm0
0x1800358a4  mov     [rsp+170h+var_100], r12
0x1800358a9  lea     r9, [rbp+70h+Block]; bool *
0x1800358b0  movdqa  [rsp+170h+var_110], xmm0
0x1800358b6  lea     r8, [rsp+170h+var_110]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x1800358bb  movdqa  [rbp+70h+var_D0], xmm0
0x1800358c0  lea     rdx, [rsp+170h+var_140]; struct StateRepository::Cache::Manager_NoThrow *
0x1800358c5  mov     [rsp+170h+var_F8], r12
0x1800358ca  lea     rcx, [rbp+70h+var_A0]; this
0x1800358ce  mov     [rbp+70h+var_F0], r12
0x1800358d2  mov     [rbp+70h+var_E8], r12
0x1800358d6  mov     [rbp+70h+var_E0], r12
0x1800358da  mov     [rbp+70h+var_D8], r12
0x1800358de  mov     [rbp+70h+var_C0], r12d
0x1800358e2  mov     [rbp+70h+var_B8], r12
0x1800358e6  mov     [rbp+70h+var_B0], r12
0x1800358ea  call    ?GetPackage@Application_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1800358ef  mov     ebx, eax
0x1800358f1  test    eax, eax
0x1800358f3  jns     short loc_18003591C
0x1800358f5  mov     edx, 1BC7h; void *
0x1800358fa  mov     rcx, [rbp+78h]; this
0x1800358fe  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035905  mov     r9d, ebx; char *
0x180035908  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003590d  lea     rcx, [rsp+170h+var_110]; this
0x180035912  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180035917  jmp     loc_180035893
0x18003591c  cmp     byte ptr [rbp+70h+Block], r12b
0x180035923  jnz     short loc_180035931
0x180035925  mov     ebx, 80070490h
0x18003592a  mov     edx, 1BC8h
0x18003592f  jmp     short loc_1800358FA
0x180035931  test    dword ptr [rsp+170h+var_F8+4], 200000h
0x180035939  jnz     short loc_18003595B
0x18003593b  mov     rcx, [rbp+78h]; this
0x18003593f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035946  mov     r9d, 80070057h; char *
0x18003594c  mov     edx, 1BC9h; void *
0x180035951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035956  jmp     loc_180035A79
0x18003595b  mov     r8, qword ptr [rsp+170h+var_110]
0x180035960  lea     rax, [rbp+70h+Block]
0x180035967  mov     [rsp+170h+var_148], rax
0x18003596c  lea     rcx, [rsp+170h+var_140]
0x180035971  lea     rax, [rsp+170h+var_130]
0x180035976  xorps   xmm0, xmm0
0x180035979  xorps   xmm1, xmm1
0x18003597c  mov     qword ptr [rsp+170h+var_150], rax; int
0x180035981  xor     edx, edx
0x180035983  movdqu  xmmword ptr [rsp+170h+var_130], xmm0
0x180035989  movdqu  xmmword ptr [rsp+170h+var_120], xmm1
0x18003598f  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x180035994  mov     ebx, eax
0x180035996  test    eax, eax
0x180035998  jns     short loc_1800359D0
0x18003599a  mov     edx, 1BD0h; void *
0x18003599f  mov     rcx, [rbp+78h]; this
0x1800359a3  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800359aa  mov     r9d, ebx; char *
0x1800359ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800359b2  mov     rcx, [rsp+170h+var_120+8]
0x1800359b7  mov     [rsp+170h+var_120+8], r12
0x1800359bc  test    rcx, rcx
0x1800359bf  jz      loc_18003590D
0x1800359c5  call    cs:__imp_SRCache_Free
0x1800359cb  jmp     loc_18003590D
0x1800359d0  mov     dl, 1
0x1800359d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch> `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl(void)'::`2'::impl
0x1800359d9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800359de  cmp     byte ptr [rbp+70h+Block], r12b
0x1800359e5  jnz     short loc_180035A2E
0x1800359e7  mov     r8, qword ptr [rsp+170h+var_110]
0x1800359ec  lea     rax, [rbp+70h+Block]
0x1800359f3  mov     rdx, [rsp+170h+var_138]
0x1800359f8  lea     rcx, [rsp+170h+var_140]
0x1800359fd  mov     [rsp+170h+var_148], rax
0x180035a02  lea     rax, [rsp+170h+var_130]
0x180035a07  mov     qword ptr [rsp+170h+var_150], rax
0x180035a0c  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x180035a11  mov     ebx, eax
0x180035a13  test    eax, eax
0x180035a15  jns     short loc_180035A1E
0x180035a17  mov     edx, 1BD8h
0x180035a1c  jmp     short loc_18003599F
0x180035a1e  cmp     byte ptr [rbp+70h+Block], r12b
0x180035a25  jnz     short loc_180035A2E
0x180035a27  mov     edx, 1BDCh
0x180035a2c  jmp     short loc_180035A4E
0x180035a2e  mov     rdx, [rsp+170h+var_120+8]
0x180035a33  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180035a37  mov     rax, rcx
0x180035a3a  inc     rax
0x180035a3d  cmp     [rdx+rax*2], r12w
0x180035a42  jnz     short loc_180035A3A
0x180035a44  test    rax, rax
0x180035a47  jnz     short loc_180035AB8
0x180035a49  mov     edx, 1BE3h; void *
0x180035a4e  mov     rcx, [rbp+78h]; this
0x180035a52  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035a59  mov     r9d, 80070057h; char *
0x180035a5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a64  mov     rcx, [rsp+170h+var_120+8]
0x180035a69  mov     [rsp+170h+var_120+8], r12
0x180035a6e  test    rcx, rcx
0x180035a71  jz      short loc_180035A79
0x180035a73  call    cs:__imp_SRCache_Free
0x180035a79  lea     rcx, [rsp+170h+var_110]; this
0x180035a7e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180035a83  lea     rcx, [rbp+70h+var_A0]; this
0x180035a87  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180035a8c  test    rdi, rdi
0x180035a8f  jz      short loc_180035A99
0x180035a91  mov     rcx, rdi; Block
0x180035a94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035a99  mov     rcx, [rsp+170h+var_140]
0x180035a9e  mov     [rsp+170h+var_140], r12
0x180035aa3  test    rcx, rcx
0x180035aa6  jz      short loc_180035AAE
0x180035aa8  call    cs:__imp_SRCacheManager_Close
0x180035aae  mov     eax, 80070057h
0x180035ab3  jmp     loc_180035B9B
0x180035ab8  movzx   r14d, word ptr [rdx+rax*2-2]
0x180035abe  mov     r8d, r12d
0x180035ac1  mov     rdx, [rbp+70h+var_60+8]
0x180035ac5  cmp     r14w, 5Ch ; '\'
0x180035aca  setnz   r8b
0x180035ace  inc     rcx
0x180035ad1  cmp     [rdx+rcx*2], r12w
0x180035ad6  jnz     short loc_180035ACE
0x180035ad8  add     eax, r8d
0x180035adb  xor     edx, edx
0x180035add  add     eax, ecx
0x180035adf  lea     rcx, [rbp+70h+Block]
0x180035ae6  lea     eax, ds:2[rax*2]
0x180035aed  mov     r8d, eax
0x180035af0  mov     esi, eax
0x180035af2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180035af7  mov     rbx, [rbp+70h+Block]
0x180035afe  mov     edx, esi; unsigned __int64
0x180035b00  mov     r8, [rsp+170h+var_120+8]; unsigned __int16 *
0x180035b05  mov     rcx, rbx; unsigned __int16 *
0x180035b08  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180035b0d  cmp     r14w, 5Ch ; '\'
0x180035b12  jz      short loc_180035B25
0x180035b14  lea     r8, asc_18004F700; "\\"
0x180035b1b  mov     edx, esi; unsigned __int64
0x180035b1d  mov     rcx, rbx; unsigned __int16 *
0x180035b20  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180035b25  mov     r8, [rbp+70h+var_60+8]; unsigned __int16 *
0x180035b29  mov     rdx, rsi; unsigned __int64
0x180035b2c  mov     rcx, rbx; unsigned __int16 *
0x180035b2f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180035b34  lea     rdx, [rbp+70h+Block]
0x180035b3b  mov     rcx, r15
0x180035b3e  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180035b43  lea     rcx, [rbp+70h+Block]
0x180035b4a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180035b4f  mov     rcx, [rsp+170h+var_120+8]
0x180035b54  mov     [rsp+170h+var_120+8], r12
0x180035b59  test    rcx, rcx
0x180035b5c  jz      short loc_180035B64
0x180035b5e  call    cs:__imp_SRCache_Free
0x180035b64  lea     rcx, [rsp+170h+var_110]; this
0x180035b69  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180035b6e  lea     rcx, [rbp+70h+var_A0]; this
0x180035b72  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180035b77  test    rdi, rdi
0x180035b7a  jz      short loc_180035B84
0x180035b7c  mov     rcx, rdi; Block
0x180035b7f  call    ??3@YAXPEAX@Z; operator delete(void *)
  ... truncated ...
```
