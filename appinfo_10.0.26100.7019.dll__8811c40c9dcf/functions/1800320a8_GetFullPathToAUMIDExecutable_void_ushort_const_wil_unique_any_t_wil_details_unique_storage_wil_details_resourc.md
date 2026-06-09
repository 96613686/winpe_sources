# GetFullPathToAUMIDExecutable(void *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800320a8`
- end: `0x180032599`
- name: `?GetFullPathToAUMIDExecutable@@YAJPEAXPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1265`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
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
- `0x18002f108`
- `0x1800320a8`
- `0x18003266c`
- `0x180037eac`
- `0x180037f18`
- `0x180037f54`
- `0x180038eb4`
- `0x18003972c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800323a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032451`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032538`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800323a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032451`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032538`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003213e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800321da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180032487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003256e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003213e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800321da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180032487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003256e`

## string_xrefs

- `0x1800320e7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003211b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032166`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800321af`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032204`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003226b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800322e3`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003231e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003237f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032430`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
      (void *)0x1868,
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
      (void *)0x186A,
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
      (void *)0x186E,
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
      (void *)0x1872,
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
                (void *)0x1875,
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
      (void *)0x187B,
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
    v22 = 6270;
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
    v22 = 6271;
    goto LABEL_23;
  }
  if ( (v49 & 0x20000000000000LL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1880,
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
    v23 = 6279;
    goto LABEL_31;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl) )
  {
    if ( (_BYTE)Block )
      goto LABEL_39;
    Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v43, v44, v47);
    if ( Package < 0 )
    {
      v23 = 6287;
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
    v26 = 6291;
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
    v26 = 6298;
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
0x1800320a8  mov     [rsp-8+arg_0], rbx
0x1800320ad  mov     [rsp-8+arg_8], rsi
0x1800320b2  push    rbp
0x1800320b3  push    rdi
0x1800320b4  push    r12
0x1800320b6  push    r14
0x1800320b8  push    r15
0x1800320ba  lea     rbp, [rsp-20h]
0x1800320bf  sub     rsp, 120h
0x1800320c6  mov     rdi, rcx
0x1800320c9  mov     r15, r8
0x1800320cc  xor     r8d, r8d; unsigned __int64 *
0x1800320cf  mov     rcx, rdx; unsigned __int16 *
0x1800320d2  mov     rsi, rdx
0x1800320d5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800320da  xor     r12d, r12d
0x1800320dd  mov     ebx, eax
0x1800320df  test    eax, eax
0x1800320e1  jns     short loc_180032102
0x1800320e3  mov     rcx, [rbp+48h]; this
0x1800320e7  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800320ee  mov     r9d, eax; char *
0x1800320f1  mov     edx, 1868h; void *
0x1800320f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800320fb  mov     eax, ebx
0x1800320fd  jmp     loc_18003257C
0x180032102  lea     rcx, [rsp+140h+var_110]
0x180032107  mov     [rsp+140h+var_110], r12
0x18003210c  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x180032111  mov     ebx, eax
0x180032113  test    eax, eax
0x180032115  jns     short loc_18003214C
0x180032117  mov     rcx, [rbp+48h]; this
0x18003211b  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032122  mov     r9d, eax; char *
0x180032125  mov     edx, 186Ah; void *
0x18003212a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003212f  mov     rcx, [rsp+140h+var_110]
0x180032134  mov     [rsp+140h+var_110], r12
0x180032139  test    rcx, rcx
0x18003213c  jz      short loc_1800320FB
0x18003213e  call    cs:__imp_SRCacheManager_Close
0x180032145  nop     dword ptr [rax+rax+00h]
0x18003214a  jmp     short loc_1800320FB
0x18003214c  mov     rdx, rdi
0x18003214f  mov     [rbp+40h+Block], r12
0x180032153  lea     rcx, [rbp+40h+Block]
0x180032157  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18003215c  mov     ebx, eax
0x18003215e  test    eax, eax
0x180032160  jns     short loc_18003218A
0x180032162  mov     rcx, [rbp+48h]; this
0x180032166  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003216d  mov     r9d, eax; char *
0x180032170  mov     edx, 186Eh; void *
0x180032175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003217a  mov     rcx, [rbp+40h+Block]; Block
0x18003217e  test    rcx, rcx
0x180032181  jz      short loc_18003212F
0x180032183  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032188  jmp     short loc_18003212F
0x18003218a  mov     rbx, [rbp+40h+Block]
0x18003218e  lea     r8, [rsp+140h+var_108]; __int64 *
0x180032193  lea     rcx, [rsp+140h+var_110]; struct StateRepository::Cache::Manager_NoThrow *
0x180032198  mov     rdx, [rbx]; void *
0x18003219b  mov     [rsp+140h+var_108], r12
0x1800321a0  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x1800321a5  mov     edi, eax
0x1800321a7  test    eax, eax
0x1800321a9  jns     short loc_1800321ED
0x1800321ab  mov     rcx, [rbp+48h]; this
0x1800321af  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800321b6  mov     r9d, eax; char *
0x1800321b9  mov     edx, 1872h; void *
0x1800321be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800321c3  mov     rcx, rbx; Block
0x1800321c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800321cb  mov     rcx, [rsp+140h+var_110]
0x1800321d0  mov     [rsp+140h+var_110], r12
0x1800321d5  test    rcx, rcx
0x1800321d8  jz      short loc_1800321E6
0x1800321da  call    cs:__imp_SRCacheManager_Close
0x1800321e1  nop     dword ptr [rax+rax+00h]
0x1800321e6  mov     eax, edi
0x1800321e8  jmp     loc_18003257C
0x1800321ed  mov     rdx, [rsp+140h+var_108]
0x1800321f2  test    rdx, rdx
0x1800321f5  jnz     short loc_180032214
0x1800321f7  mov     rcx, [rbp+48h]; this
0x1800321fb  lea     r9d, [rdx+2]; char *
0x1800321ff  mov     edx, 1875h; void *
0x180032204  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003220b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032210  mov     edi, eax
0x180032212  jmp     short loc_1800321C3
0x180032214  xorps   xmm0, xmm0
0x180032217  mov     [rbp+40h+var_70], r12
0x18003221b  xorps   xmm1, xmm1
0x18003221e  movdqa  xmmword ptr [rbp+40h+var_80], xmm0
0x180032223  lea     rax, [rbp+40h+Block]
0x180032227  mov     [rbp+40h+var_68], r12
0x18003222b  mov     [rsp+140h+var_118], rax
0x180032230  lea     rcx, [rsp+140h+var_110]
0x180032235  lea     rax, [rbp+40h+var_80]
0x180032239  movdqa  [rbp+40h+var_60], xmm0
0x18003223e  xor     r9d, r9d
0x180032241  mov     qword ptr [rsp+140h+var_120], rax; int
0x180032246  mov     r8, rsi
0x180032249  movdqa  [rbp+40h+var_50], xmm1
0x18003224e  movdqa  xmmword ptr [rbp+40h+var_40], xmm0
0x180032253  movdqa  [rbp+40h+var_30], xmm1
0x180032258  mov     byte ptr [rbp+40h+Block], r12b
0x18003225c  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180032261  mov     edi, eax
0x180032263  test    eax, eax
0x180032265  jns     short loc_18003228D
0x180032267  mov     rcx, [rbp+48h]; this
0x18003226b  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032272  mov     r9d, eax; char *
0x180032275  mov     edx, 187Bh; void *
0x18003227a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003227f  lea     rcx, [rbp+40h+var_80]; this
0x180032283  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180032288  jmp     loc_1800321C3
0x18003228d  xorps   xmm0, xmm0
0x180032290  mov     [rsp+140h+var_D0], r12
0x180032295  lea     r9, [rbp+40h+Block]; bool *
0x180032299  movdqa  [rsp+140h+var_E0], xmm0
0x18003229f  lea     r8, [rsp+140h+var_E0]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x1800322a4  movdqa  [rbp+40h+var_A0], xmm0
0x1800322a9  lea     rdx, [rsp+140h+var_110]; struct StateRepository::Cache::Manager_NoThrow *
0x1800322ae  mov     [rsp+140h+var_C8], r12
0x1800322b3  lea     rcx, [rbp+40h+var_80]; this
0x1800322b7  mov     [rbp+40h+var_C0], r12
0x1800322bb  mov     [rbp+40h+var_B8], r12
0x1800322bf  mov     [rbp+40h+var_B0], r12
0x1800322c3  mov     [rbp+40h+var_A8], r12
0x1800322c7  mov     [rbp+40h+var_90], r12d
0x1800322cb  mov     [rbp+40h+var_88], r12
0x1800322cf  call    ?GetPackage@Application_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1800322d4  mov     edi, eax
0x1800322d6  test    eax, eax
0x1800322d8  jns     short loc_1800322FE
0x1800322da  mov     edx, 187Eh; void *
0x1800322df  mov     rcx, [rbp+48h]; this
0x1800322e3  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800322ea  mov     r9d, edi; char *
0x1800322ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800322f2  lea     rcx, [rsp+140h+var_E0]; this
0x1800322f7  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800322fc  jmp     short loc_18003227F
0x1800322fe  cmp     byte ptr [rbp+40h+Block], r12b
0x180032302  jnz     short loc_180032310
0x180032304  mov     edi, 80070490h
0x180032309  mov     edx, 187Fh
0x18003230e  jmp     short loc_1800322DF
0x180032310  test    dword ptr [rsp+140h+var_C8+4], 200000h
0x180032318  jnz     short loc_18003233A
0x18003231a  mov     rcx, [rbp+48h]; this
0x18003231e  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032325  mov     r9d, 80070057h; char *
0x18003232b  mov     edx, 1880h; void *
0x180032330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032335  jmp     loc_18003245D
0x18003233a  mov     r8, qword ptr [rsp+140h+var_E0]
0x18003233f  lea     rax, [rbp+40h+Block]
0x180032343  mov     [rsp+140h+var_118], rax
0x180032348  lea     rcx, [rsp+140h+var_110]
0x18003234d  lea     rax, [rsp+140h+var_100]
0x180032352  xorps   xmm0, xmm0
0x180032355  xorps   xmm1, xmm1
0x180032358  mov     qword ptr [rsp+140h+var_120], rax; int
0x18003235d  xor     edx, edx
0x18003235f  movdqu  xmmword ptr [rsp+140h+var_100], xmm0
0x180032365  movdqu  xmmword ptr [rsp+140h+var_F0], xmm1
0x18003236b  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x180032370  mov     edi, eax
0x180032372  test    eax, eax
0x180032374  jns     short loc_1800323B2
0x180032376  mov     edx, 1887h; void *
0x18003237b  mov     rcx, [rbp+48h]; this
0x18003237f  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032386  mov     r9d, edi; char *
0x180032389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003238e  mov     rcx, [rsp+140h+var_F0+8]
0x180032393  mov     [rsp+140h+var_F0+8], r12
0x180032398  test    rcx, rcx
0x18003239b  jz      loc_1800322F2
0x1800323a1  call    cs:__imp_SRCache_Free
0x1800323a8  nop     dword ptr [rax+rax+00h]
0x1800323ad  jmp     loc_1800322F2
0x1800323b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch> `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl(void)'::`2'::impl
0x1800323b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(void)
0x1800323be  test    al, al
0x1800323c0  jz      short loc_1800323FF
0x1800323c2  cmp     byte ptr [rbp+40h+Block], r12b
0x1800323c6  jnz     short loc_18003240C
0x1800323c8  mov     r8, qword ptr [rsp+140h+var_E0]
0x1800323cd  lea     rax, [rbp+40h+Block]
0x1800323d1  mov     rdx, [rsp+140h+var_108]
0x1800323d6  lea     rcx, [rsp+140h+var_110]
0x1800323db  mov     [rsp+140h+var_118], rax
0x1800323e0  lea     rax, [rsp+140h+var_100]
0x1800323e5  mov     qword ptr [rsp+140h+var_120], rax
0x1800323ea  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x1800323ef  mov     edi, eax
0x1800323f1  test    eax, eax
0x1800323f3  jns     short loc_1800323FF
0x1800323f5  mov     edx, 188Fh
0x1800323fa  jmp     loc_18003237B
0x1800323ff  cmp     byte ptr [rbp+40h+Block], r12b
0x180032403  jnz     short loc_18003240C
0x180032405  mov     edx, 1893h
0x18003240a  jmp     short loc_18003242C
0x18003240c  mov     rcx, [rsp+140h+var_F0+8]
0x180032411  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180032415  mov     rax, rdx
0x180032418  inc     rax
0x18003241b  cmp     [rcx+rax*2], r12w
0x180032420  jnz     short loc_180032418
0x180032422  test    rax, rax
0x180032425  jnz     short loc_18003249D
0x180032427  mov     edx, 189Ah; void *
0x18003242c  mov     rcx, [rbp+48h]; this
0x180032430  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032437  mov     r9d, 80070057h; char *
0x18003243d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032442  mov     rcx, [rsp+140h+var_F0+8]
0x180032447  mov     [rsp+140h+var_F0+8], r12
0x18003244c  test    rcx, rcx
0x18003244f  jz      short loc_18003245D
0x180032451  call    cs:__imp_SRCache_Free
0x180032458  nop     dword ptr [rax+rax+00h]
0x18003245d  lea     rcx, [rsp+140h+var_E0]; this
0x180032462  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180032467  lea     rcx, [rbp+40h+var_80]; this
0x18003246b  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180032470  mov     rcx, rbx; Block
0x180032473  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032478  mov     rcx, [rsp+140h+var_110]
0x18003247d  mov     [rsp+140h+var_110], r12
0x180032482  test    rcx, rcx
0x180032485  jz      short loc_180032493
0x180032487  call    cs:__imp_SRCacheManager_Close
0x18003248e  nop     dword ptr [rax+rax+00h]
0x180032493  mov     eax, 80070057h
0x180032498  jmp     loc_18003257C
0x18003249d  movzx   r14d, word ptr [rcx+rax*2-2]
0x1800324a3  mov     rcx, [rbp+40h+var_40+8]
0x1800324a7  inc     rdx
0x1800324aa  cmp     [rcx+rdx*2], r12w
0x1800324af  jnz     short loc_1800324A7
0x1800324b1  mov     rcx, r12
0x1800324b4  cmp     r14w, 5Ch ; '\'
0x1800324b9  setnz   cl
0x1800324bc  add     rax, rdx
0x1800324bf  add     rcx, rax
0x1800324c2  xor     edx, edx
0x1800324c4  lea     rax, ds:2[rcx*2]
0x1800324cc  mov     r8d, eax
0x1800324cf  lea     rcx, [rbp+40h+Block]
0x1800324d3  mov     esi, eax
0x1800324d5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800324da  mov     rdi, [rbp+40h+Block]
0x1800324de  mov     edx, esi; unsigned __int64
0x1800324e0  mov     r8, [rsp+140h+var_F0+8]; unsigned __int16 *
0x1800324e5  mov     rcx, rdi; unsigned __int16 *
0x1800324e8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800324ed  cmp     r14w, 5Ch ; '\'
0x1800324f2  jz      short loc_180032505
0x1800324f4  lea     r8, asc_18004A24C; "\\"
0x1800324fb  mov     edx, esi; unsigned __int64
0x1800324fd  mov     rcx, rdi; unsigned __int16 *
0x180032500  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180032505  mov     r8, [rbp+40h+var_40+8]; unsigned __int16 *
0x180032509  mov     rdx, rsi; unsigned __int64
0x18003250c  mov     rcx, rdi; unsigned __int16 *
0x18003250f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180032514  lea     rdx, [rbp+40h+Block]
0x180032518  mov     rcx, r15
0x18003251b  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180032520  lea     rcx, [rbp+40h+Block]
0x180032524  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032529  mov     rcx, [rsp+140h+var_F0+8]
0x18003252e  mov     [rsp+140h+var_F0+8], r12
0x180032533  test    rcx, rcx
0x180032536  jz      short loc_180032544
0x180032538  call    cs:__imp_SRCache_Free
0x18003253f  nop     dword ptr [rax+rax+00h]
0x180032544  lea     rcx, [rsp+140h+var_E0]; this
0x180032549  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003254e  lea     rcx, [rbp+40h+var_80]; this
0x180032552  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180032557  mov     rcx, rbx; Block
0x18003255a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003255f  mov     rcx, [rsp+140h+var_110]
0x180032564  mov     [rsp+140h+var_110], r12
0x180032569  test    rcx, rcx
0x18003256c  jz      short loc_18003257A
0x18003256e  call    cs:__imp_SRCacheManager_Close
  ... truncated ...
```
