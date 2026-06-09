# VerifyExecutableHasProperConditionalACE(void *,ushort const *,bool &)

- ea: `0x180038de0`
- end: `0x1800393a3`
- name: `?VerifyExecutableHasProperConditionalACE@@YAJPEAXPEBGAEA_N@Z`
- size: `1475`
- prototype: `int(void *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180032810`

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
- `0x180026840`
- `0x18002c378`
- `0x18002dae8`
- `0x1800326dc`
- `0x18003854c`
- `0x1800385b8`
- `0x1800385f4`
- `0x180038de0`
- `0x180039554`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800392ae`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800392ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038e91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038f37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800391f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003936a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038e91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180038f37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800391f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003936a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003910b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039335`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003910b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039335`

## string_xrefs

- `0x180038e37`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038e6e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038ebe`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038f0c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038f64`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180038fd0`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039048`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039085`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800390e9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003919f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800392c5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039306`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall VerifyExecutableHasProperConditionalACE(void *a1, const unsigned __int16 *a2, bool *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx
  int token_information; // eax
  void *v14; // rbx
  void *v15; // rdx
  int v16; // eax
  int Package; // edi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rax
  unsigned __int16 *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rcx
  unsigned __int16 v32; // r14
  unsigned __int64 v33; // rsi
  unsigned __int16 *v34; // rdi
  unsigned int v35; // eax
  int v36; // eax
  unsigned __int16 *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rcx
  unsigned int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  unsigned int packageRelativeApplicationIda; // [rsp+20h] [rbp-E0h]
  bool v43; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  int v46[4]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v47[2]; // [rsp+58h] [rbp-A8h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+68h] [rbp-98h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  __int128 v51; // [rsp+80h] [rbp-80h] BYREF
  __int64 v52; // [rsp+90h] [rbp-70h]
  __int64 v53; // [rsp+98h] [rbp-68h]
  __int64 v54; // [rsp+A0h] [rbp-60h]
  __int64 v55; // [rsp+A8h] [rbp-58h]
  __int64 v56; // [rsp+B0h] [rbp-50h]
  __int64 v57; // [rsp+B8h] [rbp-48h]
  __int128 v58; // [rsp+C0h] [rbp-40h]
  int v59; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+D8h] [rbp-28h]
  int v61[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-10h]
  __int64 v63; // [rsp+F8h] [rbp-8h]
  __int128 v64; // [rsp+100h] [rbp+0h]
  __int128 v65; // [rsp+110h] [rbp+10h]
  unsigned __int16 *v66[2]; // [rsp+120h] [rbp+20h]
  __int128 v67; // [rsp+130h] [rbp+30h]
  WCHAR packageFamilyName[72]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR v69[72]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a3 = 0;
  v6 = StringCchLengthW(a2, (unsigned __int64)a2, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E0,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v6,
      packageRelativeApplicationId);
    return v7;
  }
  v44 = 0;
  v9 = StateRepository::Cache::Manager_NoThrow::Open(&v44);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E2,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v9,
      packageRelativeApplicationId);
LABEL_6:
    v12 = v44;
    v44 = 0;
    if ( v12 )
      SRCacheManager_Close(v12, v10, v11);
    return v7;
  }
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a1);
  v7 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E6,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)token_information,
      packageRelativeApplicationId);
    if ( Block )
      operator delete(Block);
    goto LABEL_6;
  }
  v14 = Block;
  v15 = *(void **)Block;
  v50 = 0;
  v16 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
          (struct StateRepository::Cache::Manager_NoThrow *)&v44,
          v15,
          &v50);
  Package = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18EA,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v16,
      packageRelativeApplicationId);
LABEL_13:
    operator delete(v14);
    v20 = v44;
    v44 = 0;
    if ( v20 )
      SRCacheManager_Close(v20, v18, v19);
    return (unsigned int)Package;
  }
  if ( !v50 )
  {
    Package = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x18ED,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)2,
                packageRelativeApplicationId);
    goto LABEL_13;
  }
  v62 = 0;
  *(_OWORD *)v61 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  *(_OWORD *)v66 = 0;
  v67 = 0;
  v43 = 0;
  v21 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(&v44, v50, a2, 0);
  Package = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F3,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v21,
      (int)v61);
LABEL_20:
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v61);
    goto LABEL_13;
  }
  v52 = 0;
  v51 = 0;
  v58 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v59 = 0;
  v60 = 0;
  Package = StateRepository::Cache::Entity::Application_NoThrow::GetPackage(
              (StateRepository::Cache::Entity::Application_NoThrow *)v61,
              (struct StateRepository::Cache::Manager_NoThrow *)&v44,
              (struct StateRepository::Cache::Entity::Package_NoThrow *)&v51,
              &v43);
  if ( Package < 0 )
  {
    v22 = 6390;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      (int)v61);
LABEL_24:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v51);
    goto LABEL_20;
  }
  if ( !v43 )
  {
    Package = -2147023728;
    v22 = 6391;
    goto LABEL_23;
  }
  if ( (v53 & 0x20000000000000LL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F8,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v61);
LABEL_46:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v51);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v61);
    operator delete(v14);
    v31 = v44;
    v44 = 0;
    if ( v31 )
      SRCacheManager_Close(v31, v29, v30);
    return 2147942487LL;
  }
  *(_OWORD *)v46 = 0;
  *(_OWORD *)v47 = 0;
  Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v44, 0, v51);
  if ( Package < 0 )
  {
    v23 = 6399;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      (int)v46);
    goto LABEL_32;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl) )
  {
    if ( v43 )
      goto LABEL_40;
    Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v44, v50, v51);
    if ( Package < 0 )
    {
      v23 = 6407;
      goto LABEL_31;
    }
  }
  if ( !v43 )
  {
    v25 = 6411;
    goto LABEL_44;
  }
LABEL_40:
  v26 = -1;
  v27 = -1;
  do
    ++v27;
  while ( v47[1][v27] );
  if ( !v27 )
  {
    v25 = 6418;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v46);
    v28 = v47[1];
    v47[1] = 0;
    if ( v28 )
      SRCache_Free();
    goto LABEL_46;
  }
  v32 = v47[1][v27 - 1];
  do
    ++v26;
  while ( v66[1][v26] );
  v33 = 2 * ((_DWORD)v26 + (_DWORD)v27 + (unsigned int)(v32 != 92)) + 2;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &Block,
    0,
    v33);
  v34 = (unsigned __int16 *)Block;
  StringCbCopyW((unsigned __int16 *)Block, (unsigned int)v33, v47[1]);
  if ( v32 != 92 )
    StringCbCatW(v34, (unsigned int)v33, L"\\");
  StringCbCatW(v34, v33, v66[1]);
  packageFamilyNameLength = 65;
  packageRelativeApplicationIdLength = 65;
  v35 = ParseApplicationUserModelId(
          a2,
          &packageFamilyNameLength,
          packageFamilyName,
          &packageRelativeApplicationIdLength,
          v69);
  if ( v35 )
  {
    Package = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1928,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)v35,
                packageRelativeApplicationIda);
LABEL_55:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Block);
LABEL_32:
    v24 = v47[1];
    v47[1] = 0;
    if ( v24 )
      SRCache_Free();
    goto LABEL_24;
  }
  v36 = CheckPackageFamilyNameACEFromPath(v34, packageFamilyName, a3);
  Package = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192B,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v36,
      packageRelativeApplicationIda);
    goto LABEL_55;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Block);
  v37 = v47[1];
  v47[1] = 0;
  if ( v37 )
    SRCache_Free();
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v51);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v61);
  operator delete(v14);
  v40 = v44;
  v44 = 0;
  if ( v40 )
    SRCacheManager_Close(v40, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x180038de0  mov     [rsp-8+arg_18], rbx
0x180038de5  push    rbp
0x180038de6  push    rsi
0x180038de7  push    rdi
0x180038de8  push    r12
0x180038dea  push    r13
0x180038dec  push    r14
0x180038dee  push    r15
0x180038df0  lea     rbp, [rsp-170h]
0x180038df8  sub     rsp, 270h
0x180038dff  mov     rax, cs:__security_cookie
0x180038e06  xor     rax, rsp
0x180038e09  mov     [rbp+1A0h+var_40], rax
0x180038e10  mov     rdi, rcx
0x180038e13  xor     r13d, r13d
0x180038e16  mov     [r8], r13b
0x180038e19  mov     r12, r8
0x180038e1c  xor     r8d, r8d; unsigned __int64 *
0x180038e1f  mov     rcx, rdx; unsigned __int16 *
0x180038e22  mov     r15, rdx
0x180038e25  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180038e2a  mov     ebx, eax
0x180038e2c  test    eax, eax
0x180038e2e  jns     short loc_180038E52
0x180038e30  mov     rcx, [rbp+1A8h]; this
0x180038e37  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180038e3e  mov     r9d, eax; char *
0x180038e41  mov     edx, 18E0h; void *
0x180038e46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038e4b  mov     eax, ebx
0x180038e4d  jmp     loc_180039378
0x180038e52  lea     rcx, [rsp+2A0h+var_268]
0x180038e57  mov     [rsp+2A0h+var_268], r13
0x180038e5c  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x180038e61  mov     ebx, eax
0x180038e63  test    eax, eax
0x180038e65  jns     short loc_180038E9F
0x180038e67  mov     rcx, [rbp+1A8h]; this
0x180038e6e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180038e75  mov     r9d, eax; char *
0x180038e78  mov     edx, 18E2h; void *
0x180038e7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038e82  mov     rcx, [rsp+2A0h+var_268]
0x180038e87  mov     [rsp+2A0h+var_268], r13
0x180038e8c  test    rcx, rcx
0x180038e8f  jz      short loc_180038E4B
0x180038e91  call    cs:__imp_SRCacheManager_Close
0x180038e98  nop     dword ptr [rax+rax+00h]
0x180038e9d  jmp     short loc_180038E4B
0x180038e9f  mov     rdx, rdi
0x180038ea2  mov     [rsp+2A0h+Block], r13
0x180038ea7  lea     rcx, [rsp+2A0h+Block]
0x180038eac  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180038eb1  mov     ebx, eax
0x180038eb3  test    eax, eax
0x180038eb5  jns     short loc_180038EE3
0x180038eb7  mov     rcx, [rbp+1A8h]; this
0x180038ebe  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180038ec5  mov     r9d, eax; char *
0x180038ec8  mov     edx, 18E6h; void *
0x180038ecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038ed2  mov     rcx, [rsp+2A0h+Block]; Block
0x180038ed7  test    rcx, rcx
0x180038eda  jz      short loc_180038E82
0x180038edc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180038ee1  jmp     short loc_180038E82
0x180038ee3  mov     rbx, [rsp+2A0h+Block]
0x180038ee8  lea     r8, [rsp+2A0h+var_230]; __int64 *
0x180038eed  lea     rcx, [rsp+2A0h+var_268]; struct StateRepository::Cache::Manager_NoThrow *
0x180038ef2  mov     rdx, [rbx]; void *
0x180038ef5  mov     [rsp+2A0h+var_230], r13
0x180038efa  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180038eff  mov     edi, eax
0x180038f01  test    eax, eax
0x180038f03  jns     short loc_180038F4A
0x180038f05  mov     rcx, [rbp+1A8h]; this
0x180038f0c  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180038f13  mov     r9d, eax; char *
0x180038f16  mov     edx, 18EAh; void *
0x180038f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038f20  mov     rcx, rbx; Block
0x180038f23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180038f28  mov     rcx, [rsp+2A0h+var_268]
0x180038f2d  mov     [rsp+2A0h+var_268], r13
0x180038f32  test    rcx, rcx
0x180038f35  jz      short loc_180038F43
0x180038f37  call    cs:__imp_SRCacheManager_Close
0x180038f3e  nop     dword ptr [rax+rax+00h]
0x180038f43  mov     eax, edi
0x180038f45  jmp     loc_180039378
0x180038f4a  mov     rdx, [rsp+2A0h+var_230]
0x180038f4f  test    rdx, rdx
0x180038f52  jnz     short loc_180038F74
0x180038f54  mov     rcx, [rbp+1A8h]; this
0x180038f5b  lea     r9d, [rdx+2]; char *
0x180038f5f  mov     edx, 18EDh; void *
0x180038f64  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180038f6b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180038f70  mov     edi, eax
0x180038f72  jmp     short loc_180038F20
0x180038f74  xorps   xmm0, xmm0
0x180038f77  mov     [rbp+1A0h+var_1B0], r13
0x180038f7b  xorps   xmm1, xmm1
0x180038f7e  movdqa  xmmword ptr [rbp+1A0h+var_1C0], xmm0
0x180038f83  lea     rax, [rsp+2A0h+var_270]
0x180038f88  mov     [rbp+1A0h+var_1A8], r13
0x180038f8c  mov     [rsp+2A0h+var_278], rax
0x180038f91  lea     rcx, [rsp+2A0h+var_268]
0x180038f96  lea     rax, [rbp+1A0h+var_1C0]
0x180038f9a  movdqa  [rbp+1A0h+var_1A0], xmm0
0x180038f9f  xor     r9d, r9d
0x180038fa2  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x180038fa7  mov     r8, r15
0x180038faa  movdqa  [rbp+1A0h+var_190], xmm1
0x180038faf  movdqa  xmmword ptr [rbp+1A0h+var_180], xmm0
0x180038fb4  movdqa  [rbp+1A0h+var_170], xmm1
0x180038fb9  mov     [rsp+2A0h+var_270], r13b
0x180038fbe  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180038fc3  mov     edi, eax
0x180038fc5  test    eax, eax
0x180038fc7  jns     short loc_180038FF2
0x180038fc9  mov     rcx, [rbp+1A8h]; this
0x180038fd0  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180038fd7  mov     r9d, eax; char *
0x180038fda  mov     edx, 18F3h; void *
0x180038fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038fe4  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180038fe8  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180038fed  jmp     loc_180038F20
0x180038ff2  xorps   xmm0, xmm0
0x180038ff5  mov     [rbp+1A0h+var_210], r13
0x180038ff9  lea     r9, [rsp+2A0h+var_270]; bool *
0x180038ffe  movdqa  [rbp+1A0h+var_220], xmm0
0x180039003  lea     r8, [rbp+1A0h+var_220]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x180039007  movdqa  [rbp+1A0h+var_1E0], xmm0
0x18003900c  lea     rdx, [rsp+2A0h+var_268]; struct StateRepository::Cache::Manager_NoThrow *
0x180039011  mov     [rbp+1A0h+var_208], r13
0x180039015  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180039019  mov     [rbp+1A0h+var_200], r13
0x18003901d  mov     [rbp+1A0h+var_1F8], r13
0x180039021  mov     [rbp+1A0h+var_1F0], r13
0x180039025  mov     [rbp+1A0h+var_1E8], r13
0x180039029  mov     [rbp+1A0h+var_1D0], r13d
0x18003902d  mov     [rbp+1A0h+var_1C8], r13
0x180039031  call    ?GetPackage@Application_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180039036  mov     edi, eax
0x180039038  test    eax, eax
0x18003903a  jns     short loc_180039062
0x18003903c  mov     edx, 18F6h; void *
0x180039041  mov     rcx, [rbp+1A8h]; this
0x180039048  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003904f  mov     r9d, edi; char *
0x180039052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039057  lea     rcx, [rbp+1A0h+var_220]; this
0x18003905b  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180039060  jmp     short loc_180038FE4
0x180039062  cmp     [rsp+2A0h+var_270], r13b
0x180039067  jnz     short loc_180039075
0x180039069  mov     edi, 80070490h
0x18003906e  mov     edx, 18F7h
0x180039073  jmp     short loc_180039041
0x180039075  test    dword ptr [rbp+1A0h+var_208+4], 200000h
0x18003907c  jnz     short loc_1800390A1
0x18003907e  mov     rcx, [rbp+1A8h]; this
0x180039085  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003908c  mov     r9d, 80070057h; char *
0x180039092  mov     edx, 18F8h; void *
0x180039097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003909c  jmp     loc_1800391CC
0x1800390a1  mov     r8, qword ptr [rbp+1A0h+var_220]
0x1800390a5  lea     rax, [rsp+2A0h+var_270]
0x1800390aa  mov     [rsp+2A0h+var_278], rax
0x1800390af  lea     rcx, [rsp+2A0h+var_268]
0x1800390b4  lea     rax, [rsp+2A0h+var_258]
0x1800390b9  xorps   xmm0, xmm0
0x1800390bc  xorps   xmm1, xmm1
0x1800390bf  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x1800390c4  xor     edx, edx
0x1800390c6  movdqu  xmmword ptr [rsp+2A0h+var_258], xmm0
0x1800390cc  movdqu  xmmword ptr [rsp+2A0h+var_248], xmm1
0x1800390d2  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x1800390d7  mov     edi, eax
0x1800390d9  test    eax, eax
0x1800390db  jns     short loc_18003911C
0x1800390dd  mov     edx, 18FFh; void *
0x1800390e2  mov     rcx, [rbp+1A8h]; this
0x1800390e9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800390f0  mov     r9d, edi; char *
0x1800390f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800390f8  mov     rcx, [rsp+2A0h+var_248+8]
0x1800390fd  mov     [rsp+2A0h+var_248+8], r13
0x180039102  test    rcx, rcx
0x180039105  jz      loc_180039057
0x18003910b  call    cs:__imp_SRCache_Free
0x180039112  nop     dword ptr [rax+rax+00h]
0x180039117  jmp     loc_180039057
0x18003911c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch> `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl(void)'::`2'::impl
0x180039123  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(void)
0x180039128  test    al, al
0x18003912a  jz      short loc_18003916A
0x18003912c  cmp     [rsp+2A0h+var_270], r13b
0x180039131  jnz     short loc_180039178
0x180039133  mov     r8, qword ptr [rbp+1A0h+var_220]
0x180039137  lea     rax, [rsp+2A0h+var_270]
0x18003913c  mov     rdx, [rsp+2A0h+var_230]
0x180039141  lea     rcx, [rsp+2A0h+var_268]
0x180039146  mov     [rsp+2A0h+var_278], rax
0x18003914b  lea     rax, [rsp+2A0h+var_258]
0x180039150  mov     [rsp+2A0h+packageRelativeApplicationId], rax
0x180039155  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18003915a  mov     edi, eax
0x18003915c  test    eax, eax
0x18003915e  jns     short loc_18003916A
0x180039160  mov     edx, 1907h
0x180039165  jmp     loc_1800390E2
0x18003916a  cmp     [rsp+2A0h+var_270], r13b
0x18003916f  jnz     short loc_180039178
0x180039171  mov     edx, 190Bh
0x180039176  jmp     short loc_180039198
0x180039178  mov     rcx, [rsp+2A0h+var_248+8]
0x18003917d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180039181  mov     rax, rdx
0x180039184  inc     rax
0x180039187  cmp     [rcx+rax*2], r13w
0x18003918c  jnz     short loc_180039184
0x18003918e  test    rax, rax
0x180039191  jnz     short loc_18003920B
0x180039193  mov     edx, 1912h; void *
0x180039198  mov     rcx, [rbp+1A8h]; this
0x18003919f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800391a6  mov     r9d, 80070057h; char *
0x1800391ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800391b1  mov     rcx, [rsp+2A0h+var_248+8]
0x1800391b6  mov     [rsp+2A0h+var_248+8], r13
0x1800391bb  test    rcx, rcx
0x1800391be  jz      short loc_1800391CC
0x1800391c0  call    cs:__imp_SRCache_Free
0x1800391c7  nop     dword ptr [rax+rax+00h]
0x1800391cc  lea     rcx, [rbp+1A0h+var_220]; this
0x1800391d0  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800391d5  lea     rcx, [rbp+1A0h+var_1C0]; this
0x1800391d9  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800391de  mov     rcx, rbx; Block
0x1800391e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800391e6  mov     rcx, [rsp+2A0h+var_268]
0x1800391eb  mov     [rsp+2A0h+var_268], r13
0x1800391f0  test    rcx, rcx
0x1800391f3  jz      short loc_180039201
0x1800391f5  call    cs:__imp_SRCacheManager_Close
0x1800391fc  nop     dword ptr [rax+rax+00h]
0x180039201  mov     eax, 80070057h
0x180039206  jmp     loc_180039378
0x18003920b  movzx   r14d, word ptr [rcx+rax*2-2]
0x180039211  mov     rcx, [rbp+1A0h+var_180+8]
0x180039215  inc     rdx
0x180039218  cmp     [rcx+rdx*2], r13w
0x18003921d  jnz     short loc_180039215
0x18003921f  mov     rcx, r13
0x180039222  cmp     r14w, 5Ch ; '\'
0x180039227  setnz   cl
0x18003922a  add     rax, rdx
0x18003922d  add     rcx, rax
0x180039230  xor     edx, edx
0x180039232  lea     rax, ds:2[rcx*2]
0x18003923a  mov     r8d, eax
0x18003923d  lea     rcx, [rsp+2A0h+Block]
0x180039242  mov     esi, eax
0x180039244  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180039249  mov     rdi, [rsp+2A0h+Block]
0x18003924e  mov     edx, esi; unsigned __int64
0x180039250  mov     r8, [rsp+2A0h+var_248+8]; unsigned __int16 *
0x180039255  mov     rcx, rdi; unsigned __int16 *
0x180039258  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003925d  cmp     r14w, 5Ch ; '\'
0x180039262  jz      short loc_180039275
0x180039264  lea     r8, asc_18004C1CC; "\\"
0x18003926b  mov     edx, esi; unsigned __int64
0x18003926d  mov     rcx, rdi; unsigned __int16 *
0x180039270  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180039275  mov     r8, [rbp+1A0h+var_180+8]; unsigned __int16 *
0x180039279  mov     rdx, rsi; unsigned __int64
0x18003927c  mov     rcx, rdi; unsigned __int16 *
0x18003927f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180039284  mov     eax, 41h ; 'A'
0x180039289  lea     r9, [rsp+2A0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18003928e  mov     [rsp+2A0h+packageFamilyNameLength], eax
0x180039292  lea     r8, [rbp+1A0h+packageFamilyName]; packageFamilyName
0x180039296  mov     [rsp+2A0h+packageRelativeApplicationIdLength], eax
0x18003929a  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x18003929f  lea     rax, [rbp+1A0h+var_D0]
0x1800392a6  mov     rcx, r15; applicationUserModelId
0x1800392a9  mov     [rsp+2A0h+packageRelativeApplicationId], rax; int
0x1800392ae  call    cs:__imp_ParseApplicationUserModelId
0x1800392b5  nop     dword ptr [rax+rax+00h]
0x1800392ba  test    eax, eax
0x1800392bc  jz      short loc_1800392EA
0x1800392be  mov     rcx, [rbp+1A8h]; this
0x1800392c5  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800392cc  mov     r9d, eax; char *
0x1800392cf  mov     edx, 1928h; void *
  ... truncated ...
```
