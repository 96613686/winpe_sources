# VerifyExecutableHasProperConditionalACE(void *,ushort const *,bool &)

- ea: `0x180018228`
- end: `0x1800187e9`
- name: `?VerifyExecutableHasProperConditionalACE@@YAJPEAXPEBGAEA_N@Z`
- size: `1473`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `20`
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
- `0x180018228`
- `0x180018dbc`
- `0x180018ed0`
- `0x180019fa0`
- `0x18001d494`
- `0x18001e7bc`
- `0x180031f90`
- `0x180035c84`
- `0x180038880`
- `0x18003b2ac`
- `0x18003b320`
- `0x18003b370`
- `0x180046e50`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180018702`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180018702`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018310`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018650`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800187b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018310`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018650`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800187b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018572`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001861c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018783`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018572`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001861c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018783`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800182b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800182b6`

## string_xrefs

- `0x1800182d2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18001827f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800182ed`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001833a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018388`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800183c4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018430`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800184ac`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800184ec`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018550`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800185fb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018713`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180018754`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall VerifyExecutableHasProperConditionalACE(void *a1, const unsigned __int16 *a2, bool *a3)
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
  __int64 v21; // rax
  __int64 v22; // rcx
  unsigned __int16 *v23; // rcx
  __int64 v24; // rcx
  unsigned __int16 v25; // r14
  int v26; // r8d
  unsigned __int64 v27; // rsi
  unsigned __int16 *v28; // rbx
  unsigned int v29; // eax
  int v30; // eax
  unsigned __int16 *v31; // rcx
  __int64 v32; // rcx
  unsigned int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  int packageRelativeApplicationIdb; // [rsp+20h] [rbp-E0h]
  unsigned int packageRelativeApplicationIda; // [rsp+20h] [rbp-E0h]
  bool v36; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  int v39[4]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v40[2]; // [rsp+58h] [rbp-A8h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+68h] [rbp-98h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  __int128 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+98h] [rbp-68h]
  __int64 v47; // [rsp+A0h] [rbp-60h]
  __int64 v48; // [rsp+A8h] [rbp-58h]
  __int64 v49; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h]
  __int128 v51; // [rsp+C0h] [rbp-40h]
  int v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+D8h] [rbp-28h]
  __int64 v54; // [rsp+E0h] [rbp-20h]
  int v55[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v56; // [rsp+100h] [rbp+0h]
  __int64 v57; // [rsp+108h] [rbp+8h]
  __int128 v58; // [rsp+110h] [rbp+10h]
  __int128 v59; // [rsp+120h] [rbp+20h]
  unsigned __int16 *v60[2]; // [rsp+130h] [rbp+30h]
  __int128 v61; // [rsp+140h] [rbp+40h]
  __int64 *v62; // [rsp+150h] [rbp+50h] BYREF
  __int64 v63; // [rsp+158h] [rbp+58h] BYREF
  char v64; // [rsp+160h] [rbp+60h]
  WCHAR packageFamilyName[72]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR v66[72]; // [rsp+200h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  *a3 = 0;
  v6 = StringCchLengthW(a2, (unsigned __int64)a2, 0);
  Package = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5F,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v6,
      packageRelativeApplicationId);
    return (unsigned int)Package;
  }
  v37 = 0;
  v62 = &v37;
  v63 = 0;
  v64 = 1;
  Package = SRCacheManager_Open(0, &v63);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v62);
  if ( Package < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)Package,
      packageRelativeApplicationId);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B61,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      packageRelativeApplicationIdb);
    goto LABEL_6;
  }
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a1);
  Package = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B65,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)token_information,
      packageRelativeApplicationId);
    v11 = Block;
    if ( !Block )
      goto LABEL_6;
    goto LABEL_10;
  }
  v12 = Block;
  v13 = *(void **)Block;
  v43 = 0;
  v14 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
          (struct StateRepository::Cache::Manager_NoThrow *)&v37,
          v13,
          &v43);
  Package = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B69,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v14,
      packageRelativeApplicationId);
LABEL_13:
    if ( !v12 )
    {
LABEL_6:
      v9 = v37;
      v37 = 0;
      if ( v9 )
        SRCacheManager_Close();
      return (unsigned int)Package;
    }
    v11 = v12;
LABEL_10:
    operator delete(v11);
    goto LABEL_6;
  }
  if ( !v43 )
  {
    Package = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1B6C,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)2,
                packageRelativeApplicationId);
    goto LABEL_13;
  }
  v56 = 0;
  *(_OWORD *)v55 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  *(_OWORD *)v60 = 0;
  v61 = 0;
  v36 = 0;
  v15 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(&v37, v43, a2, 0);
  Package = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B72,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v15,
      (int)v55);
LABEL_19:
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v55);
    goto LABEL_13;
  }
  v45 = 0;
  v44 = 0;
  v51 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  Package = StateRepository::Cache::Entity::Application_NoThrow::GetPackage(
              (StateRepository::Cache::Entity::Application_NoThrow *)v55,
              (struct StateRepository::Cache::Manager_NoThrow *)&v37,
              (struct StateRepository::Cache::Entity::Package_NoThrow *)&v44,
              &v36);
  if ( Package < 0 )
  {
    v16 = 7029;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      (int)v55);
LABEL_23:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v44);
    goto LABEL_19;
  }
  if ( !v36 )
  {
    Package = -2147023728;
    v16 = 7030;
    goto LABEL_22;
  }
  if ( (v46 & 0x20000000000000LL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B77,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v55);
LABEL_44:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v44);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v55);
    if ( v12 )
      operator delete(v12);
    v24 = v37;
    v37 = 0;
    if ( v24 )
      SRCacheManager_Close();
    return 2147942487LL;
  }
  *(_OWORD *)v39 = 0;
  *(_OWORD *)v40 = 0;
  Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v37, 0, v44);
  if ( Package < 0 )
  {
    v18 = 7038;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      (int)v39);
    goto LABEL_31;
  }
  LOBYTE(v17) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl,
    v17);
  if ( !v36 )
  {
    Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v37, v43, v44);
    if ( Package < 0 )
    {
      v18 = 7044;
      goto LABEL_30;
    }
    if ( !v36 )
    {
      v20 = 7047;
      goto LABEL_42;
    }
  }
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( v40[1][v22] );
  if ( !v22 )
  {
    v20 = 7054;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v39);
    v23 = v40[1];
    v40[1] = 0;
    if ( v23 )
      SRCache_Free();
    goto LABEL_44;
  }
  v25 = v40[1][v22 - 1];
  v26 = 0;
  do
    ++v21;
  while ( v60[1][v21] );
  LOBYTE(v26) = v25 != 92;
  v27 = (unsigned int)(2 * (v22 + v26 + v21) + 2);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &Block,
    0,
    v27);
  v28 = (unsigned __int16 *)Block;
  StringCbCopyW((unsigned __int16 *)Block, (unsigned int)v27, v40[1]);
  if ( v25 != 92 )
    StringCbCatW(v28, (unsigned int)v27, L"\\");
  StringCbCatW(v28, v27, v60[1]);
  packageFamilyNameLength = 65;
  packageRelativeApplicationIdLength = 65;
  v29 = ParseApplicationUserModelId(
          a2,
          &packageFamilyNameLength,
          packageFamilyName,
          &packageRelativeApplicationIdLength,
          v66);
  if ( v29 )
  {
    Package = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1BA4,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)v29,
                packageRelativeApplicationIda);
LABEL_55:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Block);
LABEL_31:
    v19 = v40[1];
    v40[1] = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_23;
  }
  v30 = CheckPackageFamilyNameACEFromPath(v28, packageFamilyName, a3);
  Package = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BA7,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v30,
      packageRelativeApplicationIda);
    goto LABEL_55;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Block);
  v31 = v40[1];
  v40[1] = 0;
  if ( v31 )
    SRCache_Free();
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v44);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v55);
  if ( v12 )
    operator delete(v12);
  v32 = v37;
  v37 = 0;
  if ( v32 )
    SRCacheManager_Close();
  return 0;
}

```

## disassembly

```asm
0x180018228  mov     [rsp-8+arg_18], rbx
0x18001822d  push    rbp
0x18001822e  push    rsi
0x18001822f  push    rdi
0x180018230  push    r12
0x180018232  push    r13
0x180018234  push    r14
0x180018236  push    r15
0x180018238  lea     rbp, [rsp-1A0h]
0x180018240  sub     rsp, 2A0h
0x180018247  mov     rax, cs:__security_cookie
0x18001824e  xor     rax, rsp
0x180018251  mov     [rbp+1D0h+var_40], rax
0x180018258  mov     rdi, rcx
0x18001825b  xor     r13d, r13d
0x18001825e  mov     [r8], r13b
0x180018261  mov     r12, r8
0x180018264  xor     r8d, r8d; unsigned __int64 *
0x180018267  mov     rcx, rdx; unsigned __int16 *
0x18001826a  mov     r15, rdx
0x18001826d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180018272  mov     ebx, eax
0x180018274  test    eax, eax
0x180018276  jns     short loc_18001829A
0x180018278  mov     rcx, [rbp+1D8h]; this
0x18001827f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018286  mov     r9d, eax; char *
0x180018289  mov     edx, 1B5Fh; void *
0x18001828e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018293  mov     eax, ebx
0x180018295  jmp     loc_1800187BF
0x18001829a  lea     rax, [rsp+2D0h+var_298]
0x18001829f  mov     [rsp+2D0h+var_298], r13
0x1800182a4  lea     rdx, [rbp+1D0h+var_178]
0x1800182a8  mov     [rbp+1D0h+var_180], rax
0x1800182ac  xor     ecx, ecx
0x1800182ae  mov     [rbp+1D0h+var_178], r13
0x1800182b2  mov     [rbp+1D0h+var_170], 1
0x1800182b6  call    cs:__imp_SRCacheManager_Open
0x1800182bc  lea     rcx, [rbp+1D0h+var_180]
0x1800182c0  mov     ebx, eax
0x1800182c2  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1800182c7  test    ebx, ebx
0x1800182c9  jns     short loc_18001831B
0x1800182cb  mov     rcx, [rbp+1D8h]; this
0x1800182d2  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800182d9  mov     r9d, ebx; char *
0x1800182dc  mov     edx, 0A5h; void *
0x1800182e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800182e6  mov     rcx, [rbp+1D8h]; this
0x1800182ed  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800182f4  mov     r9d, ebx; char *
0x1800182f7  mov     edx, 1B61h; void *
0x1800182fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018301  mov     rcx, [rsp+2D0h+var_298]
0x180018306  mov     [rsp+2D0h+var_298], r13
0x18001830b  test    rcx, rcx
0x18001830e  jz      short loc_180018293
0x180018310  call    cs:__imp_SRCacheManager_Close
0x180018316  jmp     loc_180018293
0x18001831b  mov     rdx, rdi
0x18001831e  mov     [rsp+2D0h+Block], r13
0x180018323  lea     rcx, [rsp+2D0h+Block]
0x180018328  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18001832d  mov     ebx, eax
0x18001832f  test    eax, eax
0x180018331  jns     short loc_18001835F
0x180018333  mov     rcx, [rbp+1D8h]; this
0x18001833a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018341  mov     r9d, eax; char *
0x180018344  mov     edx, 1B65h; void *
0x180018349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001834e  mov     rcx, [rsp+2D0h+Block]; Block
0x180018353  test    rcx, rcx
0x180018356  jz      short loc_180018301
0x180018358  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001835d  jmp     short loc_180018301
0x18001835f  mov     rdi, [rsp+2D0h+Block]
0x180018364  lea     r8, [rsp+2D0h+var_260]; __int64 *
0x180018369  lea     rcx, [rsp+2D0h+var_298]; struct StateRepository::Cache::Manager_NoThrow *
0x18001836e  mov     rdx, [rdi]; void *
0x180018371  mov     [rsp+2D0h+var_260], r13
0x180018376  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18001837b  mov     ebx, eax
0x18001837d  test    eax, eax
0x18001837f  jns     short loc_1800183AA
0x180018381  mov     rcx, [rbp+1D8h]; this
0x180018388  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18001838f  mov     r9d, eax; char *
0x180018392  mov     edx, 1B69h; void *
0x180018397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001839c  test    rdi, rdi
0x18001839f  jz      loc_180018301
0x1800183a5  mov     rcx, rdi
0x1800183a8  jmp     short loc_180018358
0x1800183aa  mov     rdx, [rsp+2D0h+var_260]
0x1800183af  test    rdx, rdx
0x1800183b2  jnz     short loc_1800183D4
0x1800183b4  mov     rcx, [rbp+1D8h]; this
0x1800183bb  lea     r9d, [rdx+2]; char *
0x1800183bf  mov     edx, 1B6Ch; void *
0x1800183c4  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800183cb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800183d0  mov     ebx, eax
0x1800183d2  jmp     short loc_18001839C
0x1800183d4  xorps   xmm0, xmm0
0x1800183d7  mov     [rbp+1D0h+var_1D0], r13
0x1800183db  xorps   xmm1, xmm1
0x1800183de  movdqa  xmmword ptr [rbp+1D0h+var_1E0], xmm0
0x1800183e3  lea     rax, [rsp+2D0h+var_2A0]
0x1800183e8  mov     [rbp+1D0h+var_1C8], r13
0x1800183ec  mov     [rsp+2D0h+var_2A8], rax
0x1800183f1  lea     rcx, [rsp+2D0h+var_298]
0x1800183f6  lea     rax, [rbp+1D0h+var_1E0]
0x1800183fa  movdqa  [rbp+1D0h+var_1C0], xmm0
0x1800183ff  xor     r9d, r9d
0x180018402  mov     [rsp+2D0h+packageRelativeApplicationId], rax; int
0x180018407  mov     r8, r15
0x18001840a  movdqa  [rbp+1D0h+var_1B0], xmm1
0x18001840f  movdqa  xmmword ptr [rbp+1D0h+var_1A0], xmm0
0x180018414  movdqa  [rbp+1D0h+var_190], xmm1
0x180018419  mov     [rsp+2D0h+var_2A0], r13b
0x18001841e  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180018423  mov     ebx, eax
0x180018425  test    eax, eax
0x180018427  jns     short loc_180018452
0x180018429  mov     rcx, [rbp+1D8h]; this
0x180018430  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018437  mov     r9d, eax; char *
0x18001843a  mov     edx, 1B72h; void *
0x18001843f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018444  lea     rcx, [rbp+1D0h+var_1E0]; this
0x180018448  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18001844d  jmp     loc_18001839C
0x180018452  xorps   xmm0, xmm0
0x180018455  mov     [rbp+1D0h+var_240], r13
0x180018459  lea     r9, [rsp+2D0h+var_2A0]; bool *
0x18001845e  movdqa  [rbp+1D0h+var_250], xmm0
0x180018463  lea     r8, [rbp+1D0h+var_250]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x180018467  movdqa  [rbp+1D0h+var_210], xmm0
0x18001846c  lea     rdx, [rsp+2D0h+var_298]; struct StateRepository::Cache::Manager_NoThrow *
0x180018471  mov     [rbp+1D0h+var_238], r13
0x180018475  lea     rcx, [rbp+1D0h+var_1E0]; this
0x180018479  mov     [rbp+1D0h+var_230], r13
0x18001847d  mov     [rbp+1D0h+var_228], r13
0x180018481  mov     [rbp+1D0h+var_220], r13
0x180018485  mov     [rbp+1D0h+var_218], r13
0x180018489  mov     [rbp+1D0h+var_200], r13d
0x18001848d  mov     [rbp+1D0h+var_1F8], r13
0x180018491  mov     [rbp+1D0h+var_1F0], r13
0x180018495  call    ?GetPackage@Application_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18001849a  mov     ebx, eax
0x18001849c  test    eax, eax
0x18001849e  jns     short loc_1800184C9
0x1800184a0  mov     edx, 1B75h; void *
0x1800184a5  mov     rcx, [rbp+1D8h]; this
0x1800184ac  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800184b3  mov     r9d, ebx; char *
0x1800184b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800184bb  lea     rcx, [rbp+1D0h+var_250]; this
0x1800184bf  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800184c4  jmp     loc_180018444
0x1800184c9  cmp     [rsp+2D0h+var_2A0], r13b
0x1800184ce  jnz     short loc_1800184DC
0x1800184d0  mov     ebx, 80070490h
0x1800184d5  mov     edx, 1B76h
0x1800184da  jmp     short loc_1800184A5
0x1800184dc  test    dword ptr [rbp+1D0h+var_238+4], 200000h
0x1800184e3  jnz     short loc_180018508
0x1800184e5  mov     rcx, [rbp+1D8h]; this
0x1800184ec  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800184f3  mov     r9d, 80070057h; char *
0x1800184f9  mov     edx, 1B77h; void *
0x1800184fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018503  jmp     loc_180018622
0x180018508  mov     r8, qword ptr [rbp+1D0h+var_250]
0x18001850c  lea     rax, [rsp+2D0h+var_2A0]
0x180018511  mov     [rsp+2D0h+var_2A8], rax
0x180018516  lea     rcx, [rsp+2D0h+var_298]
0x18001851b  lea     rax, [rsp+2D0h+var_288]
0x180018520  xorps   xmm0, xmm0
0x180018523  xorps   xmm1, xmm1
0x180018526  mov     [rsp+2D0h+packageRelativeApplicationId], rax; int
0x18001852b  xor     edx, edx
0x18001852d  movdqu  xmmword ptr [rsp+2D0h+var_288], xmm0
0x180018533  movdqu  xmmword ptr [rsp+2D0h+var_278], xmm1
0x180018539  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18001853e  mov     ebx, eax
0x180018540  test    eax, eax
0x180018542  jns     short loc_18001857D
0x180018544  mov     edx, 1B7Eh; void *
0x180018549  mov     rcx, [rbp+1D8h]; this
0x180018550  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018557  mov     r9d, ebx; char *
0x18001855a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001855f  mov     rcx, [rsp+2D0h+var_278+8]
0x180018564  mov     [rsp+2D0h+var_278+8], r13
0x180018569  test    rcx, rcx
0x18001856c  jz      loc_1800184BB
0x180018572  call    cs:__imp_SRCache_Free
0x180018578  jmp     loc_1800184BB
0x18001857d  mov     dl, 1
0x18001857f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch> `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl(void)'::`2'::impl
0x180018586  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001858b  cmp     [rsp+2D0h+var_2A0], r13b
0x180018590  jnz     short loc_1800185D4
0x180018592  mov     r8, qword ptr [rbp+1D0h+var_250]
0x180018596  lea     rax, [rsp+2D0h+var_2A0]
0x18001859b  mov     rdx, [rsp+2D0h+var_260]
0x1800185a0  lea     rcx, [rsp+2D0h+var_298]
0x1800185a5  mov     [rsp+2D0h+var_2A8], rax
0x1800185aa  lea     rax, [rsp+2D0h+var_288]
0x1800185af  mov     [rsp+2D0h+packageRelativeApplicationId], rax
0x1800185b4  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x1800185b9  mov     ebx, eax
0x1800185bb  test    eax, eax
0x1800185bd  jns     short loc_1800185C6
0x1800185bf  mov     edx, 1B84h
0x1800185c4  jmp     short loc_180018549
0x1800185c6  cmp     [rsp+2D0h+var_2A0], r13b
0x1800185cb  jnz     short loc_1800185D4
0x1800185cd  mov     edx, 1B87h
0x1800185d2  jmp     short loc_1800185F4
0x1800185d4  mov     rdx, [rsp+2D0h+var_278+8]
0x1800185d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800185dd  mov     rcx, rax
0x1800185e0  inc     rcx
0x1800185e3  cmp     [rdx+rcx*2], r13w
0x1800185e8  jnz     short loc_1800185E0
0x1800185ea  test    rcx, rcx
0x1800185ed  jnz     short loc_180018660
0x1800185ef  mov     edx, 1B8Eh; void *
0x1800185f4  mov     rcx, [rbp+1D8h]; this
0x1800185fb  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180018602  mov     r9d, 80070057h; char *
0x180018608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001860d  mov     rcx, [rsp+2D0h+var_278+8]
0x180018612  mov     [rsp+2D0h+var_278+8], r13
0x180018617  test    rcx, rcx
0x18001861a  jz      short loc_180018622
0x18001861c  call    cs:__imp_SRCache_Free
0x180018622  lea     rcx, [rbp+1D0h+var_250]; this
0x180018626  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18001862b  lea     rcx, [rbp+1D0h+var_1E0]; this
0x18001862f  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180018634  test    rdi, rdi
0x180018637  jz      short loc_180018641
0x180018639  mov     rcx, rdi; Block
0x18001863c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018641  mov     rcx, [rsp+2D0h+var_298]
0x180018646  mov     [rsp+2D0h+var_298], r13
0x18001864b  test    rcx, rcx
0x18001864e  jz      short loc_180018656
0x180018650  call    cs:__imp_SRCacheManager_Close
0x180018656  mov     eax, 80070057h
0x18001865b  jmp     loc_1800187BF
0x180018660  movzx   r14d, word ptr [rdx+rcx*2-2]
0x180018666  mov     r8d, r13d
0x180018669  mov     rdx, [rbp+1D0h+var_1A0+8]
0x18001866d  cmp     r14w, 5Ch ; '\'
0x180018672  setnz   r8b
0x180018676  inc     rax
0x180018679  cmp     [rdx+rax*2], r13w
0x18001867e  jnz     short loc_180018676
0x180018680  add     eax, r8d
0x180018683  xor     edx, edx
0x180018685  add     eax, ecx
0x180018687  lea     rcx, [rsp+2D0h+Block]
0x18001868c  lea     eax, ds:2[rax*2]
0x180018693  mov     r8d, eax
0x180018696  mov     esi, eax
0x180018698  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001869d  mov     rbx, [rsp+2D0h+Block]
0x1800186a2  mov     edx, esi; unsigned __int64
0x1800186a4  mov     r8, [rsp+2D0h+var_278+8]; unsigned __int16 *
0x1800186a9  mov     rcx, rbx; unsigned __int16 *
0x1800186ac  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800186b1  cmp     r14w, 5Ch ; '\'
0x1800186b6  jz      short loc_1800186C9
0x1800186b8  lea     r8, asc_18004F700; "\\"
0x1800186bf  mov     edx, esi; unsigned __int64
0x1800186c1  mov     rcx, rbx; unsigned __int16 *
0x1800186c4  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800186c9  mov     r8, [rbp+1D0h+var_1A0+8]; unsigned __int16 *
0x1800186cd  mov     rdx, rsi; unsigned __int64
0x1800186d0  mov     rcx, rbx; unsigned __int16 *
0x1800186d3  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800186d8  mov     eax, 41h ; 'A'
0x1800186dd  lea     r9, [rsp+2D0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x1800186e2  mov     [rsp+2D0h+packageFamilyNameLength], eax
0x1800186e6  lea     r8, [rbp+1D0h+packageFamilyName]; packageFamilyName
0x1800186ea  mov     [rsp+2D0h+packageRelativeApplicationIdLength], eax
0x1800186ee  lea     rdx, [rsp+2D0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800186f3  lea     rax, [rbp+1D0h+var_D0]
0x1800186fa  mov     rcx, r15; applicationUserModelId
0x1800186fd  mov     [rsp+2D0h+packageRelativeApplicationId], rax; int
0x180018702  call    cs:__imp_ParseApplicationUserModelId
0x180018708  test    eax, eax
0x18001870a  jz      short loc_180018738
0x18001870c  mov     rcx, [rbp+1D8h]; this
  ... truncated ...
```
