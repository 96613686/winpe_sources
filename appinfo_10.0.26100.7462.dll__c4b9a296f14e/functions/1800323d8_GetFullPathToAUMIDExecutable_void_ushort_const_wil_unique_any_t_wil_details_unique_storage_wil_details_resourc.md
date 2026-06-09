# GetFullPathToAUMIDExecutable(void *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800323d8`
- end: `0x1800328c9`
- name: `?GetFullPathToAUMIDExecutable@@YAJPEAXPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1265`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
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
- `0x18002dbb8`
- `0x1800323d8`
- `0x18003299c`
- `0x18003888c`
- `0x1800388f8`
- `0x180038934`
- `0x1800398d0`
- `0x18003a2bc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003246e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003250a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800327b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003289e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003246e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003250a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800327b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003289e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800326d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032781`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032868`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800326d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032781`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032868`

## string_xrefs

- `0x180032417`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003244b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032496`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800324df`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032534`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003259b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032613`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003264e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800326af`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032760`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall GetFullPathToAUMIDExecutable(__int64 a1, const unsigned __int16 *a2, __int64 a3)
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
  __int64 v24; // rdx
  unsigned __int16 *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  unsigned __int16 *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rcx
  unsigned __int16 v34; // r14
  unsigned __int64 v35; // rsi
  unsigned __int16 *v36; // rdi
  __int64 v37; // rdx
  unsigned __int16 *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rcx
  unsigned int v42; // [rsp+20h] [rbp-E0h]
  __int64 v43; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+38h] [rbp-C8h] BYREF
  int v45[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v46[2]; // [rsp+50h] [rbp-B0h]
  __int128 v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h]
  __int64 v49; // [rsp+78h] [rbp-88h]
  __int64 v50; // [rsp+80h] [rbp-80h]
  __int64 v51; // [rsp+88h] [rbp-78h]
  __int64 v52; // [rsp+90h] [rbp-70h]
  __int64 v53; // [rsp+98h] [rbp-68h]
  __int128 v54; // [rsp+A0h] [rbp-60h]
  int v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  int v57[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-30h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  __int128 v60; // [rsp+E0h] [rbp-20h]
  __int128 v61; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v62[2]; // [rsp+100h] [rbp+0h]
  __int128 v63; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  void *Block; // [rsp+168h] [rbp+68h] BYREF

  v6 = StringCchLengthW(a2, (unsigned __int64)a2, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x196C,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v6,
      v42);
    return v7;
  }
  v43 = 0;
  v9 = StateRepository::Cache::Manager_NoThrow::Open(&v43);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x196E,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v9,
      v42);
LABEL_6:
    v12 = v43;
    v43 = 0;
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
      (void *)0x1972,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)token_information,
      v42);
    if ( Block )
      operator delete(Block);
    goto LABEL_6;
  }
  v14 = Block;
  v15 = *(void **)Block;
  v44 = 0;
  v16 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
          (struct StateRepository::Cache::Manager_NoThrow *)&v43,
          v15,
          &v44);
  Package = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1976,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v16,
      v42);
LABEL_13:
    operator delete(v14);
    v20 = v43;
    v43 = 0;
    if ( v20 )
      SRCacheManager_Close(v20, v18, v19);
    return (unsigned int)Package;
  }
  if ( !v44 )
  {
    Package = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1979,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)2,
                v42);
    goto LABEL_13;
  }
  v58 = 0;
  *(_OWORD *)v57 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  *(_OWORD *)v62 = 0;
  v63 = 0;
  LOBYTE(Block) = 0;
  v21 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(&v43, v44, a2, 0);
  Package = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x197F,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v21,
      (int)v57);
LABEL_20:
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v57);
    goto LABEL_13;
  }
  v48 = 0;
  v47 = 0;
  v54 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v55 = 0;
  v56 = 0;
  Package = StateRepository::Cache::Entity::Application_NoThrow::GetPackage(
              (StateRepository::Cache::Entity::Application_NoThrow *)v57,
              (struct StateRepository::Cache::Manager_NoThrow *)&v43,
              (struct StateRepository::Cache::Entity::Package_NoThrow *)&v47,
              (bool *)&Block);
  if ( Package < 0 )
  {
    v22 = 6530;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)Package,
      (int)v57);
LABEL_24:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v47);
    goto LABEL_20;
  }
  if ( !(_BYTE)Block )
  {
    Package = -2147023728;
    v22 = 6531;
    goto LABEL_23;
  }
  if ( (v49 & 0x20000000000000LL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1984,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v57);
LABEL_45:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v47);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v57);
    operator delete(v14);
    v33 = v43;
    v43 = 0;
    if ( v33 )
      SRCacheManager_Close(v33, v31, v32);
    return 2147942487LL;
  }
  *(_OWORD *)v45 = 0;
  *(_OWORD *)v46 = 0;
  Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v43, 0, v47);
  if ( Package < 0 )
  {
    v23 = 6539;
    goto LABEL_31;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl) )
  {
    if ( (_BYTE)Block )
      goto LABEL_39;
    Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v43, v44, v47);
    if ( Package < 0 )
    {
      v23 = 6547;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)Package,
        (int)v45);
      v25 = v46[1];
      v46[1] = 0;
      if ( v25 )
        SRCache_Free(v25, v24);
      goto LABEL_24;
    }
  }
  if ( !(_BYTE)Block )
  {
    v26 = 6551;
    goto LABEL_43;
  }
LABEL_39:
  v27 = -1;
  v28 = -1;
  do
    ++v28;
  while ( v46[1][v28] );
  if ( !v28 )
  {
    v26 = 6558;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      (int)v45);
    v30 = v46[1];
    v46[1] = 0;
    if ( v30 )
      SRCache_Free(v30, v29);
    goto LABEL_45;
  }
  v34 = v46[1][v28 - 1];
  do
    ++v27;
  while ( v62[1][v27] );
  v35 = 2 * ((_DWORD)v27 + (_DWORD)v28 + (unsigned int)(v34 != 92)) + 2;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &Block,
    0,
    v35);
  v36 = (unsigned __int16 *)Block;
  StringCbCopyW((unsigned __int16 *)Block, (unsigned int)v35, v46[1]);
  if ( v34 != 92 )
    StringCbCatW(v36, (unsigned int)v35, L"\\");
  StringCbCatW(v36, v35, v62[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
    a3,
    &Block);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Block);
  v38 = v46[1];
  v46[1] = 0;
  if ( v38 )
    SRCache_Free(v38, v37);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v47);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v57);
  operator delete(v14);
  v41 = v43;
  v43 = 0;
  if ( v41 )
    SRCacheManager_Close(v41, v39, v40);
  return 0;
}

```

## disassembly

```asm
0x1800323d8  mov     [rsp-8+arg_0], rbx
0x1800323dd  mov     [rsp-8+arg_8], rsi
0x1800323e2  push    rbp
0x1800323e3  push    rdi
0x1800323e4  push    r12
0x1800323e6  push    r14
0x1800323e8  push    r15
0x1800323ea  lea     rbp, [rsp-20h]
0x1800323ef  sub     rsp, 120h
0x1800323f6  mov     rdi, rcx
0x1800323f9  mov     r15, r8
0x1800323fc  xor     r8d, r8d; unsigned __int64 *
0x1800323ff  mov     rcx, rdx; unsigned __int16 *
0x180032402  mov     rsi, rdx
0x180032405  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003240a  xor     r12d, r12d
0x18003240d  mov     ebx, eax
0x18003240f  test    eax, eax
0x180032411  jns     short loc_180032432
0x180032413  mov     rcx, [rbp+48h]; this
0x180032417  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003241e  mov     r9d, eax; char *
0x180032421  mov     edx, 196Ch; void *
0x180032426  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003242b  mov     eax, ebx
0x18003242d  jmp     loc_1800328AC
0x180032432  lea     rcx, [rsp+140h+var_110]
0x180032437  mov     [rsp+140h+var_110], r12
0x18003243c  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x180032441  mov     ebx, eax
0x180032443  test    eax, eax
0x180032445  jns     short loc_18003247C
0x180032447  mov     rcx, [rbp+48h]; this
0x18003244b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032452  mov     r9d, eax; char *
0x180032455  mov     edx, 196Eh; void *
0x18003245a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003245f  mov     rcx, [rsp+140h+var_110]
0x180032464  mov     [rsp+140h+var_110], r12
0x180032469  test    rcx, rcx
0x18003246c  jz      short loc_18003242B
0x18003246e  call    cs:__imp_SRCacheManager_Close
0x180032475  nop     dword ptr [rax+rax+00h]
0x18003247a  jmp     short loc_18003242B
0x18003247c  mov     rdx, rdi
0x18003247f  mov     [rbp+40h+Block], r12
0x180032483  lea     rcx, [rbp+40h+Block]
0x180032487  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18003248c  mov     ebx, eax
0x18003248e  test    eax, eax
0x180032490  jns     short loc_1800324BA
0x180032492  mov     rcx, [rbp+48h]; this
0x180032496  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003249d  mov     r9d, eax; char *
0x1800324a0  mov     edx, 1972h; void *
0x1800324a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800324aa  mov     rcx, [rbp+40h+Block]; Block
0x1800324ae  test    rcx, rcx
0x1800324b1  jz      short loc_18003245F
0x1800324b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800324b8  jmp     short loc_18003245F
0x1800324ba  mov     rbx, [rbp+40h+Block]
0x1800324be  lea     r8, [rsp+140h+var_108]; __int64 *
0x1800324c3  lea     rcx, [rsp+140h+var_110]; struct StateRepository::Cache::Manager_NoThrow *
0x1800324c8  mov     rdx, [rbx]; void *
0x1800324cb  mov     [rsp+140h+var_108], r12
0x1800324d0  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x1800324d5  mov     edi, eax
0x1800324d7  test    eax, eax
0x1800324d9  jns     short loc_18003251D
0x1800324db  mov     rcx, [rbp+48h]; this
0x1800324df  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800324e6  mov     r9d, eax; char *
0x1800324e9  mov     edx, 1976h; void *
0x1800324ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800324f3  mov     rcx, rbx; Block
0x1800324f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800324fb  mov     rcx, [rsp+140h+var_110]
0x180032500  mov     [rsp+140h+var_110], r12
0x180032505  test    rcx, rcx
0x180032508  jz      short loc_180032516
0x18003250a  call    cs:__imp_SRCacheManager_Close
0x180032511  nop     dword ptr [rax+rax+00h]
0x180032516  mov     eax, edi
0x180032518  jmp     loc_1800328AC
0x18003251d  mov     rdx, [rsp+140h+var_108]
0x180032522  test    rdx, rdx
0x180032525  jnz     short loc_180032544
0x180032527  mov     rcx, [rbp+48h]; this
0x18003252b  lea     r9d, [rdx+2]; char *
0x18003252f  mov     edx, 1979h; void *
0x180032534  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003253b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032540  mov     edi, eax
0x180032542  jmp     short loc_1800324F3
0x180032544  xorps   xmm0, xmm0
0x180032547  mov     [rbp+40h+var_70], r12
0x18003254b  xorps   xmm1, xmm1
0x18003254e  movdqa  xmmword ptr [rbp+40h+var_80], xmm0
0x180032553  lea     rax, [rbp+40h+Block]
0x180032557  mov     [rbp+40h+var_68], r12
0x18003255b  mov     [rsp+140h+var_118], rax
0x180032560  lea     rcx, [rsp+140h+var_110]
0x180032565  lea     rax, [rbp+40h+var_80]
0x180032569  movdqa  [rbp+40h+var_60], xmm0
0x18003256e  xor     r9d, r9d
0x180032571  mov     qword ptr [rsp+140h+var_120], rax; int
0x180032576  mov     r8, rsi
0x180032579  movdqa  [rbp+40h+var_50], xmm1
0x18003257e  movdqa  xmmword ptr [rbp+40h+var_40], xmm0
0x180032583  movdqa  [rbp+40h+var_30], xmm1
0x180032588  mov     byte ptr [rbp+40h+Block], r12b
0x18003258c  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180032591  mov     edi, eax
0x180032593  test    eax, eax
0x180032595  jns     short loc_1800325BD
0x180032597  mov     rcx, [rbp+48h]; this
0x18003259b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800325a2  mov     r9d, eax; char *
0x1800325a5  mov     edx, 197Fh; void *
0x1800325aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800325af  lea     rcx, [rbp+40h+var_80]; this
0x1800325b3  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800325b8  jmp     loc_1800324F3
0x1800325bd  xorps   xmm0, xmm0
0x1800325c0  mov     [rsp+140h+var_D0], r12
0x1800325c5  lea     r9, [rbp+40h+Block]; bool *
0x1800325c9  movdqa  [rsp+140h+var_E0], xmm0
0x1800325cf  lea     r8, [rsp+140h+var_E0]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x1800325d4  movdqa  [rbp+40h+var_A0], xmm0
0x1800325d9  lea     rdx, [rsp+140h+var_110]; struct StateRepository::Cache::Manager_NoThrow *
0x1800325de  mov     [rsp+140h+var_C8], r12
0x1800325e3  lea     rcx, [rbp+40h+var_80]; this
0x1800325e7  mov     [rbp+40h+var_C0], r12
0x1800325eb  mov     [rbp+40h+var_B8], r12
0x1800325ef  mov     [rbp+40h+var_B0], r12
0x1800325f3  mov     [rbp+40h+var_A8], r12
0x1800325f7  mov     [rbp+40h+var_90], r12d
0x1800325fb  mov     [rbp+40h+var_88], r12
0x1800325ff  call    ?GetPackage@Application_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180032604  mov     edi, eax
0x180032606  test    eax, eax
0x180032608  jns     short loc_18003262E
0x18003260a  mov     edx, 1982h; void *
0x18003260f  mov     rcx, [rbp+48h]; this
0x180032613  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003261a  mov     r9d, edi; char *
0x18003261d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032622  lea     rcx, [rsp+140h+var_E0]; this
0x180032627  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003262c  jmp     short loc_1800325AF
0x18003262e  cmp     byte ptr [rbp+40h+Block], r12b
0x180032632  jnz     short loc_180032640
0x180032634  mov     edi, 80070490h
0x180032639  mov     edx, 1983h
0x18003263e  jmp     short loc_18003260F
0x180032640  test    dword ptr [rsp+140h+var_C8+4], 200000h
0x180032648  jnz     short loc_18003266A
0x18003264a  mov     rcx, [rbp+48h]; this
0x18003264e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032655  mov     r9d, 80070057h; char *
0x18003265b  mov     edx, 1984h; void *
0x180032660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032665  jmp     loc_18003278D
0x18003266a  mov     r8, qword ptr [rsp+140h+var_E0]
0x18003266f  lea     rax, [rbp+40h+Block]
0x180032673  mov     [rsp+140h+var_118], rax
0x180032678  lea     rcx, [rsp+140h+var_110]
0x18003267d  lea     rax, [rsp+140h+var_100]
0x180032682  xorps   xmm0, xmm0
0x180032685  xorps   xmm1, xmm1
0x180032688  mov     qword ptr [rsp+140h+var_120], rax; int
0x18003268d  xor     edx, edx
0x18003268f  movdqu  xmmword ptr [rsp+140h+var_100], xmm0
0x180032695  movdqu  xmmword ptr [rsp+140h+var_F0], xmm1
0x18003269b  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x1800326a0  mov     edi, eax
0x1800326a2  test    eax, eax
0x1800326a4  jns     short loc_1800326E2
0x1800326a6  mov     edx, 198Bh; void *
0x1800326ab  mov     rcx, [rbp+48h]; this
0x1800326af  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800326b6  mov     r9d, edi; char *
0x1800326b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800326be  mov     rcx, [rsp+140h+var_F0+8]
0x1800326c3  mov     [rsp+140h+var_F0+8], r12
0x1800326c8  test    rcx, rcx
0x1800326cb  jz      loc_180032622
0x1800326d1  call    cs:__imp_SRCache_Free
0x1800326d8  nop     dword ptr [rax+rax+00h]
0x1800326dd  jmp     loc_180032622
0x1800326e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch> `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl(void)'::`2'::impl
0x1800326e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(void)
0x1800326ee  test    al, al
0x1800326f0  jz      short loc_18003272F
0x1800326f2  cmp     byte ptr [rbp+40h+Block], r12b
0x1800326f6  jnz     short loc_18003273C
0x1800326f8  mov     r8, qword ptr [rsp+140h+var_E0]
0x1800326fd  lea     rax, [rbp+40h+Block]
0x180032701  mov     rdx, [rsp+140h+var_108]
0x180032706  lea     rcx, [rsp+140h+var_110]
0x18003270b  mov     [rsp+140h+var_118], rax
0x180032710  lea     rax, [rsp+140h+var_100]
0x180032715  mov     qword ptr [rsp+140h+var_120], rax
0x18003271a  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18003271f  mov     edi, eax
0x180032721  test    eax, eax
0x180032723  jns     short loc_18003272F
0x180032725  mov     edx, 1993h
0x18003272a  jmp     loc_1800326AB
0x18003272f  cmp     byte ptr [rbp+40h+Block], r12b
0x180032733  jnz     short loc_18003273C
0x180032735  mov     edx, 1997h
0x18003273a  jmp     short loc_18003275C
0x18003273c  mov     rcx, [rsp+140h+var_F0+8]
0x180032741  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180032745  mov     rax, rdx
0x180032748  inc     rax
0x18003274b  cmp     [rcx+rax*2], r12w
0x180032750  jnz     short loc_180032748
0x180032752  test    rax, rax
0x180032755  jnz     short loc_1800327CD
0x180032757  mov     edx, 199Eh; void *
0x18003275c  mov     rcx, [rbp+48h]; this
0x180032760  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032767  mov     r9d, 80070057h; char *
0x18003276d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032772  mov     rcx, [rsp+140h+var_F0+8]
0x180032777  mov     [rsp+140h+var_F0+8], r12
0x18003277c  test    rcx, rcx
0x18003277f  jz      short loc_18003278D
0x180032781  call    cs:__imp_SRCache_Free
0x180032788  nop     dword ptr [rax+rax+00h]
0x18003278d  lea     rcx, [rsp+140h+var_E0]; this
0x180032792  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180032797  lea     rcx, [rbp+40h+var_80]; this
0x18003279b  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800327a0  mov     rcx, rbx; Block
0x1800327a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800327a8  mov     rcx, [rsp+140h+var_110]
0x1800327ad  mov     [rsp+140h+var_110], r12
0x1800327b2  test    rcx, rcx
0x1800327b5  jz      short loc_1800327C3
0x1800327b7  call    cs:__imp_SRCacheManager_Close
0x1800327be  nop     dword ptr [rax+rax+00h]
0x1800327c3  mov     eax, 80070057h
0x1800327c8  jmp     loc_1800328AC
0x1800327cd  movzx   r14d, word ptr [rcx+rax*2-2]
0x1800327d3  mov     rcx, [rbp+40h+var_40+8]
0x1800327d7  inc     rdx
0x1800327da  cmp     [rcx+rdx*2], r12w
0x1800327df  jnz     short loc_1800327D7
0x1800327e1  mov     rcx, r12
0x1800327e4  cmp     r14w, 5Ch ; '\'
0x1800327e9  setnz   cl
0x1800327ec  add     rax, rdx
0x1800327ef  add     rcx, rax
0x1800327f2  xor     edx, edx
0x1800327f4  lea     rax, ds:2[rcx*2]
0x1800327fc  mov     r8d, eax
0x1800327ff  lea     rcx, [rbp+40h+Block]
0x180032803  mov     esi, eax
0x180032805  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003280a  mov     rdi, [rbp+40h+Block]
0x18003280e  mov     edx, esi; unsigned __int64
0x180032810  mov     r8, [rsp+140h+var_F0+8]; unsigned __int16 *
0x180032815  mov     rcx, rdi; unsigned __int16 *
0x180032818  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003281d  cmp     r14w, 5Ch ; '\'
0x180032822  jz      short loc_180032835
0x180032824  lea     r8, asc_18004D1CC; "\\"
0x18003282b  mov     edx, esi; unsigned __int64
0x18003282d  mov     rcx, rdi; unsigned __int16 *
0x180032830  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180032835  mov     r8, [rbp+40h+var_40+8]; unsigned __int16 *
0x180032839  mov     rdx, rsi; unsigned __int64
0x18003283c  mov     rcx, rdi; unsigned __int16 *
0x18003283f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180032844  lea     rdx, [rbp+40h+Block]
0x180032848  mov     rcx, r15
0x18003284b  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180032850  lea     rcx, [rbp+40h+Block]
0x180032854  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032859  mov     rcx, [rsp+140h+var_F0+8]
0x18003285e  mov     [rsp+140h+var_F0+8], r12
0x180032863  test    rcx, rcx
0x180032866  jz      short loc_180032874
0x180032868  call    cs:__imp_SRCache_Free
0x18003286f  nop     dword ptr [rax+rax+00h]
0x180032874  lea     rcx, [rsp+140h+var_E0]; this
0x180032879  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003287e  lea     rcx, [rbp+40h+var_80]; this
0x180032882  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180032887  mov     rcx, rbx; Block
0x18003288a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003288f  mov     rcx, [rsp+140h+var_110]
0x180032894  mov     [rsp+140h+var_110], r12
0x180032899  test    rcx, rcx
0x18003289c  jz      short loc_1800328AA
0x18003289e  call    cs:__imp_SRCacheManager_Close
  ... truncated ...
```
