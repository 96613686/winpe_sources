# VerifyExecutableHasProperConditionalACE(void *,ushort const *,bool &)

- ea: `0x180038740`
- end: `0x180038d03`
- name: `?VerifyExecutableHasProperConditionalACE@@YAJPEAXPEBGAEA_N@Z`
- size: `1475`
- prototype: `int(void *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800327a0`

## callees

- `0x180005880`
- `0x180007b30`
- `0x180007c78`
- `0x1800096c0`
- `0x18000dd68`
- `0x18000de50`
- `0x1800124f4`
- `0x18001800c`
- `0x180018280`
- `0x18001b0c4`
- `0x180027e80`
- `0x18002d998`
- `0x18002f108`
- `0x18003266c`
- `0x180037eac`
- `0x180037f18`
- `0x180037f54`
- `0x180038740`
- `0x180038eb4`
- `0x180042950`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180038c0e`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180038c0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038a6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038b20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038c95`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038a6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038b20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038c95`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800387f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038897`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038b55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038cca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800387f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038897`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038b55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038cca`

## string_xrefs

- `0x180038797`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800387ce`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003881e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003886c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800388c4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038930`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800389a8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800389e5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038a49`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038aff`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038c25`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038c66`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
      (void *)0x1813,
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
      (void *)0x1815,
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
      (void *)0x1819,
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
      (void *)0x181D,
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
                (void *)0x1820,
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
      (void *)0x1826,
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
    v18 = 6185;
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
    v18 = 6186;
    goto LABEL_23;
  }
  if ( (v45 & 0x20000000000000LL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182B,
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
    v19 = 6194;
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
      v19 = 6202;
      goto LABEL_31;
    }
  }
  if ( !v35 )
  {
    v21 = 6206;
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
    v21 = 6213;
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
                (void *)0x185B,
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
      (void *)0x185E,
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
0x180038740  mov     [rsp-8+arg_18], rbx
0x180038745  push    rbp
0x180038746  push    rsi
0x180038747  push    rdi
0x180038748  push    r12
0x18003874a  push    r13
0x18003874c  push    r14
0x18003874e  push    r15
0x180038750  lea     rbp, [rsp-170h]
0x180038758  sub     rsp, 270h
0x18003875f  mov     rax, cs:__security_cookie
0x180038766  xor     rax, rsp
0x180038769  mov     [rbp+1A0h+var_40], rax
0x180038770  mov     rdi, rcx
0x180038773  xor     r13d, r13d
0x180038776  mov     [r8], r13b
0x180038779  mov     r12, r8
0x18003877c  xor     r8d, r8d; unsigned __int64 *
0x18003877f  mov     rcx, rdx; unsigned __int16 *
0x180038782  mov     r15, rdx
0x180038785  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003878a  mov     ebx, eax
0x18003878c  test    eax, eax
0x18003878e  jns     short loc_1800387B2
0x180038790  mov     rcx, [rbp+1A8h]; this
0x180038797  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003879e  mov     r9d, eax; char *
0x1800387a1  mov     edx, 1813h; void *
0x1800387a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800387ab  mov     eax, ebx
0x1800387ad  jmp     loc_180038CD8
0x1800387b2  lea     rcx, [rsp+2A0h+var_268]
0x1800387b7  mov     [rsp+2A0h+var_268], r13
0x1800387bc  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x1800387c1  mov     ebx, eax
0x1800387c3  test    eax, eax
0x1800387c5  jns     short loc_1800387FF
0x1800387c7  mov     rcx, [rbp+1A8h]; this
0x1800387ce  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800387d5  mov     r9d, eax; char *
0x1800387d8  mov     edx, 1815h; void *
0x1800387dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800387e2  mov     rcx, [rsp+2A0h+var_268]
0x1800387e7  mov     [rsp+2A0h+var_268], r13
0x1800387ec  test    rcx, rcx
0x1800387ef  jz      short loc_1800387AB
0x1800387f1  call    cs:__imp_SRCacheManager_Close
0x1800387f8  nop     dword ptr [rax+rax+00h]
0x1800387fd  jmp     short loc_1800387AB
0x1800387ff  mov     rdx, rdi
0x180038802  mov     [rsp+2A0h+Block], r13
0x180038807  lea     rcx, [rsp+2A0h+Block]
0x18003880c  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180038811  mov     ebx, eax
0x180038813  test    eax, eax
0x180038815  jns     short loc_180038843
0x180038817  mov     rcx, [rbp+1A8h]; this
0x18003881e  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180038825  mov     r9d, eax; char *
0x180038828  mov     edx, 1819h; void *
0x18003882d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038832  mov     rcx, [rsp+2A0h+Block]; Block
0x180038837  test    rcx, rcx
0x18003883a  jz      short loc_1800387E2
0x18003883c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180038841  jmp     short loc_1800387E2
0x180038843  mov     rbx, [rsp+2A0h+Block]
0x180038848  lea     r8, [rsp+2A0h+var_230]; __int64 *
0x18003884d  lea     rcx, [rsp+2A0h+var_268]; struct StateRepository::Cache::Manager_NoThrow *
0x180038852  mov     rdx, [rbx]; void *
0x180038855  mov     [rsp+2A0h+var_230], r13
0x18003885a  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18003885f  mov     edi, eax
0x180038861  test    eax, eax
0x180038863  jns     short loc_1800388AA
0x180038865  mov     rcx, [rbp+1A8h]; this
0x18003886c  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180038873  mov     r9d, eax; char *
0x180038876  mov     edx, 181Dh; void *
0x18003887b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038880  mov     rcx, rbx; Block
0x180038883  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180038888  mov     rcx, [rsp+2A0h+var_268]
0x18003888d  mov     [rsp+2A0h+var_268], r13
0x180038892  test    rcx, rcx
0x180038895  jz      short loc_1800388A3
0x180038897  call    cs:__imp_SRCacheManager_Close
0x18003889e  nop     dword ptr [rax+rax+00h]
0x1800388a3  mov     eax, edi
0x1800388a5  jmp     loc_180038CD8
0x1800388aa  mov     rdx, [rsp+2A0h+var_230]
0x1800388af  test    rdx, rdx
0x1800388b2  jnz     short loc_1800388D4
0x1800388b4  mov     rcx, [rbp+1A8h]; this
0x1800388bb  lea     r9d, [rdx+2]; char *
0x1800388bf  mov     edx, 1820h; void *
0x1800388c4  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800388cb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800388d0  mov     edi, eax
0x1800388d2  jmp     short loc_180038880
0x1800388d4  xorps   xmm0, xmm0
0x1800388d7  mov     [rbp+1A0h+var_1B0], r13
0x1800388db  xorps   xmm1, xmm1
0x1800388de  movdqa  xmmword ptr [rbp+1A0h+var_1C0], xmm0
0x1800388e3  lea     rax, [rsp+2A0h+var_270]
0x1800388e8  mov     [rbp+1A0h+var_1A8], r13
0x1800388ec  mov     [rsp+2A0h+var_278], rax
0x1800388f1  lea     rcx, [rsp+2A0h+var_268]
0x1800388f6  lea     rax, [rbp+1A0h+var_1C0]
0x1800388fa  movdqa  [rbp+1A0h+var_1A0], xmm0
0x1800388ff  xor     r9d, r9d
0x180038902  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x180038907  mov     r8, r15
0x18003890a  movdqa  [rbp+1A0h+var_190], xmm1
0x18003890f  movdqa  xmmword ptr [rbp+1A0h+var_180], xmm0
0x180038914  movdqa  [rbp+1A0h+var_170], xmm1
0x180038919  mov     [rsp+2A0h+var_270], r13b
0x18003891e  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180038923  mov     edi, eax
0x180038925  test    eax, eax
0x180038927  jns     short loc_180038952
0x180038929  mov     rcx, [rbp+1A8h]; this
0x180038930  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180038937  mov     r9d, eax; char *
0x18003893a  mov     edx, 1826h; void *
0x18003893f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038944  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180038948  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18003894d  jmp     loc_180038880
0x180038952  xorps   xmm0, xmm0
0x180038955  mov     [rbp+1A0h+var_210], r13
0x180038959  lea     r9, [rsp+2A0h+var_270]; bool *
0x18003895e  movdqa  [rbp+1A0h+var_220], xmm0
0x180038963  lea     r8, [rbp+1A0h+var_220]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x180038967  movdqa  [rbp+1A0h+var_1E0], xmm0
0x18003896c  lea     rdx, [rsp+2A0h+var_268]; struct StateRepository::Cache::Manager_NoThrow *
0x180038971  mov     [rbp+1A0h+var_208], r13
0x180038975  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180038979  mov     [rbp+1A0h+var_200], r13
0x18003897d  mov     [rbp+1A0h+var_1F8], r13
0x180038981  mov     [rbp+1A0h+var_1F0], r13
0x180038985  mov     [rbp+1A0h+var_1E8], r13
0x180038989  mov     [rbp+1A0h+var_1D0], r13d
0x18003898d  mov     [rbp+1A0h+var_1C8], r13
0x180038991  call    ?GetPackage@Application_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180038996  mov     edi, eax
0x180038998  test    eax, eax
0x18003899a  jns     short loc_1800389C2
0x18003899c  mov     edx, 1829h; void *
0x1800389a1  mov     rcx, [rbp+1A8h]; this
0x1800389a8  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800389af  mov     r9d, edi; char *
0x1800389b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800389b7  lea     rcx, [rbp+1A0h+var_220]; this
0x1800389bb  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800389c0  jmp     short loc_180038944
0x1800389c2  cmp     [rsp+2A0h+var_270], r13b
0x1800389c7  jnz     short loc_1800389D5
0x1800389c9  mov     edi, 80070490h
0x1800389ce  mov     edx, 182Ah
0x1800389d3  jmp     short loc_1800389A1
0x1800389d5  test    dword ptr [rbp+1A0h+var_208+4], 200000h
0x1800389dc  jnz     short loc_180038A01
0x1800389de  mov     rcx, [rbp+1A8h]; this
0x1800389e5  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800389ec  mov     r9d, 80070057h; char *
0x1800389f2  mov     edx, 182Bh; void *
0x1800389f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800389fc  jmp     loc_180038B2C
0x180038a01  mov     r8, qword ptr [rbp+1A0h+var_220]
0x180038a05  lea     rax, [rsp+2A0h+var_270]
0x180038a0a  mov     [rsp+2A0h+var_278], rax
0x180038a0f  lea     rcx, [rsp+2A0h+var_268]
0x180038a14  lea     rax, [rsp+2A0h+var_258]
0x180038a19  xorps   xmm0, xmm0
0x180038a1c  xorps   xmm1, xmm1
0x180038a1f  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x180038a24  xor     edx, edx
0x180038a26  movdqu  xmmword ptr [rsp+2A0h+var_258], xmm0
0x180038a2c  movdqu  xmmword ptr [rsp+2A0h+var_248], xmm1
0x180038a32  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x180038a37  mov     edi, eax
0x180038a39  test    eax, eax
0x180038a3b  jns     short loc_180038A7C
0x180038a3d  mov     edx, 1832h; void *
0x180038a42  mov     rcx, [rbp+1A8h]; this
0x180038a49  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180038a50  mov     r9d, edi; char *
0x180038a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038a58  mov     rcx, [rsp+2A0h+var_248+8]
0x180038a5d  mov     [rsp+2A0h+var_248+8], r13
0x180038a62  test    rcx, rcx
0x180038a65  jz      loc_1800389B7
0x180038a6b  call    cs:__imp_SRCache_Free
0x180038a72  nop     dword ptr [rax+rax+00h]
0x180038a77  jmp     loc_1800389B7
0x180038a7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch> `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl(void)'::`2'::impl
0x180038a83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(void)
0x180038a88  test    al, al
0x180038a8a  jz      short loc_180038ACA
0x180038a8c  cmp     [rsp+2A0h+var_270], r13b
0x180038a91  jnz     short loc_180038AD8
0x180038a93  mov     r8, qword ptr [rbp+1A0h+var_220]
0x180038a97  lea     rax, [rsp+2A0h+var_270]
0x180038a9c  mov     rdx, [rsp+2A0h+var_230]
0x180038aa1  lea     rcx, [rsp+2A0h+var_268]
0x180038aa6  mov     [rsp+2A0h+var_278], rax
0x180038aab  lea     rax, [rsp+2A0h+var_258]
0x180038ab0  mov     [rsp+2A0h+packageRelativeApplicationId], rax
0x180038ab5  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x180038aba  mov     edi, eax
0x180038abc  test    eax, eax
0x180038abe  jns     short loc_180038ACA
0x180038ac0  mov     edx, 183Ah
0x180038ac5  jmp     loc_180038A42
0x180038aca  cmp     [rsp+2A0h+var_270], r13b
0x180038acf  jnz     short loc_180038AD8
0x180038ad1  mov     edx, 183Eh
0x180038ad6  jmp     short loc_180038AF8
0x180038ad8  mov     rcx, [rsp+2A0h+var_248+8]
0x180038add  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180038ae1  mov     rax, rdx
0x180038ae4  inc     rax
0x180038ae7  cmp     [rcx+rax*2], r13w
0x180038aec  jnz     short loc_180038AE4
0x180038aee  test    rax, rax
0x180038af1  jnz     short loc_180038B6B
0x180038af3  mov     edx, 1845h; void *
0x180038af8  mov     rcx, [rbp+1A8h]; this
0x180038aff  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180038b06  mov     r9d, 80070057h; char *
0x180038b0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b11  mov     rcx, [rsp+2A0h+var_248+8]
0x180038b16  mov     [rsp+2A0h+var_248+8], r13
0x180038b1b  test    rcx, rcx
0x180038b1e  jz      short loc_180038B2C
0x180038b20  call    cs:__imp_SRCache_Free
0x180038b27  nop     dword ptr [rax+rax+00h]
0x180038b2c  lea     rcx, [rbp+1A0h+var_220]; this
0x180038b30  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180038b35  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180038b39  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180038b3e  mov     rcx, rbx; Block
0x180038b41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180038b46  mov     rcx, [rsp+2A0h+var_268]
0x180038b4b  mov     [rsp+2A0h+var_268], r13
0x180038b50  test    rcx, rcx
0x180038b53  jz      short loc_180038B61
0x180038b55  call    cs:__imp_SRCacheManager_Close
0x180038b5c  nop     dword ptr [rax+rax+00h]
0x180038b61  mov     eax, 80070057h
0x180038b66  jmp     loc_180038CD8
0x180038b6b  movzx   r14d, word ptr [rcx+rax*2-2]
0x180038b71  mov     rcx, [rbp+1A0h+var_180+8]
0x180038b75  inc     rdx
0x180038b78  cmp     [rcx+rdx*2], r13w
0x180038b7d  jnz     short loc_180038B75
0x180038b7f  mov     rcx, r13
0x180038b82  cmp     r14w, 5Ch ; '\'
0x180038b87  setnz   cl
0x180038b8a  add     rax, rdx
0x180038b8d  add     rcx, rax
0x180038b90  xor     edx, edx
0x180038b92  lea     rax, ds:2[rcx*2]
0x180038b9a  mov     r8d, eax
0x180038b9d  lea     rcx, [rsp+2A0h+Block]
0x180038ba2  mov     esi, eax
0x180038ba4  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180038ba9  mov     rdi, [rsp+2A0h+Block]
0x180038bae  mov     edx, esi; unsigned __int64
0x180038bb0  mov     r8, [rsp+2A0h+var_248+8]; unsigned __int16 *
0x180038bb5  mov     rcx, rdi; unsigned __int16 *
0x180038bb8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180038bbd  cmp     r14w, 5Ch ; '\'
0x180038bc2  jz      short loc_180038BD5
0x180038bc4  lea     r8, asc_18004A24C; "\\"
0x180038bcb  mov     edx, esi; unsigned __int64
0x180038bcd  mov     rcx, rdi; unsigned __int16 *
0x180038bd0  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180038bd5  mov     r8, [rbp+1A0h+var_180+8]; unsigned __int16 *
0x180038bd9  mov     rdx, rsi; unsigned __int64
0x180038bdc  mov     rcx, rdi; unsigned __int16 *
0x180038bdf  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180038be4  mov     eax, 41h ; 'A'
0x180038be9  lea     r9, [rsp+2A0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180038bee  mov     [rsp+2A0h+packageFamilyNameLength], eax
0x180038bf2  lea     r8, [rbp+1A0h+packageFamilyName]; packageFamilyName
0x180038bf6  mov     [rsp+2A0h+packageRelativeApplicationIdLength], eax
0x180038bfa  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x180038bff  lea     rax, [rbp+1A0h+var_D0]
0x180038c06  mov     rcx, r15; applicationUserModelId
0x180038c09  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x180038c0e  call    cs:__imp_ParseApplicationUserModelId
0x180038c15  nop     dword ptr [rax+rax+00h]
0x180038c1a  test    eax, eax
0x180038c1c  jz      short loc_180038C4A
0x180038c1e  mov     rcx, [rbp+1A8h]; this
0x180038c25  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180038c2c  mov     r9d, eax; char *
0x180038c2f  mov     edx, 185Bh; void *
  ... truncated ...
```
