# GetFullPathToAUMIDExecutable(void *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180032118`
- end: `0x180032609`
- name: `?GetFullPathToAUMIDExecutable@@YAJPEAXPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1265`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
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
- `0x18002dae8`
- `0x180032118`
- `0x1800326dc`
- `0x18003854c`
- `0x1800385b8`
- `0x1800385f4`
- `0x180039554`
- `0x180039f3c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800321ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003224a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800324f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800325de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800321ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003224a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800324f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800325de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032411`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800324c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800325a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180032411`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800324c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800325a8`

## string_xrefs

- `0x180032157`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003218b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800321d6`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003221f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032274`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800322db`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032353`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003238e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800323ef`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800324a0`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
      (void *)0x1935,
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
      (void *)0x1937,
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
      (void *)0x193B,
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
      (void *)0x193F,
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
                (void *)0x1942,
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
      (void *)0x1948,
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
    v22 = 6475;
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
    v22 = 6476;
    goto LABEL_23;
  }
  if ( (v49 & 0x20000000000000LL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x194D,
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
    v23 = 6484;
    goto LABEL_31;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl) )
  {
    if ( (_BYTE)Block )
      goto LABEL_39;
    Package = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(&v43, v44, v47);
    if ( Package < 0 )
    {
      v23 = 6492;
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
    v26 = 6496;
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
    v26 = 6503;
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
0x180032118  mov     [rsp-8+arg_0], rbx
0x18003211d  mov     [rsp-8+arg_8], rsi
0x180032122  push    rbp
0x180032123  push    rdi
0x180032124  push    r12
0x180032126  push    r14
0x180032128  push    r15
0x18003212a  lea     rbp, [rsp-20h]
0x18003212f  sub     rsp, 120h
0x180032136  mov     rdi, rcx
0x180032139  mov     r15, r8
0x18003213c  xor     r8d, r8d; unsigned __int64 *
0x18003213f  mov     rcx, rdx; unsigned __int16 *
0x180032142  mov     rsi, rdx
0x180032145  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003214a  xor     r12d, r12d
0x18003214d  mov     ebx, eax
0x18003214f  test    eax, eax
0x180032151  jns     short loc_180032172
0x180032153  mov     rcx, [rbp+48h]; this
0x180032157  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003215e  mov     r9d, eax; char *
0x180032161  mov     edx, 1935h; void *
0x180032166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003216b  mov     eax, ebx
0x18003216d  jmp     loc_1800325EC
0x180032172  lea     rcx, [rsp+140h+var_110]
0x180032177  mov     [rsp+140h+var_110], r12
0x18003217c  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x180032181  mov     ebx, eax
0x180032183  test    eax, eax
0x180032185  jns     short loc_1800321BC
0x180032187  mov     rcx, [rbp+48h]; this
0x18003218b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032192  mov     r9d, eax; char *
0x180032195  mov     edx, 1937h; void *
0x18003219a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003219f  mov     rcx, [rsp+140h+var_110]
0x1800321a4  mov     [rsp+140h+var_110], r12
0x1800321a9  test    rcx, rcx
0x1800321ac  jz      short loc_18003216B
0x1800321ae  call    cs:__imp_SRCacheManager_Close
0x1800321b5  nop     dword ptr [rax+rax+00h]
0x1800321ba  jmp     short loc_18003216B
0x1800321bc  mov     rdx, rdi
0x1800321bf  mov     [rbp+40h+Block], r12
0x1800321c3  lea     rcx, [rbp+40h+Block]
0x1800321c7  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800321cc  mov     ebx, eax
0x1800321ce  test    eax, eax
0x1800321d0  jns     short loc_1800321FA
0x1800321d2  mov     rcx, [rbp+48h]; this
0x1800321d6  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800321dd  mov     r9d, eax; char *
0x1800321e0  mov     edx, 193Bh; void *
0x1800321e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800321ea  mov     rcx, [rbp+40h+Block]; Block
0x1800321ee  test    rcx, rcx
0x1800321f1  jz      short loc_18003219F
0x1800321f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800321f8  jmp     short loc_18003219F
0x1800321fa  mov     rbx, [rbp+40h+Block]
0x1800321fe  lea     r8, [rsp+140h+var_108]; __int64 *
0x180032203  lea     rcx, [rsp+140h+var_110]; struct StateRepository::Cache::Manager_NoThrow *
0x180032208  mov     rdx, [rbx]; void *
0x18003220b  mov     [rsp+140h+var_108], r12
0x180032210  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180032215  mov     edi, eax
0x180032217  test    eax, eax
0x180032219  jns     short loc_18003225D
0x18003221b  mov     rcx, [rbp+48h]; this
0x18003221f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032226  mov     r9d, eax; char *
0x180032229  mov     edx, 193Fh; void *
0x18003222e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032233  mov     rcx, rbx; Block
0x180032236  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003223b  mov     rcx, [rsp+140h+var_110]
0x180032240  mov     [rsp+140h+var_110], r12
0x180032245  test    rcx, rcx
0x180032248  jz      short loc_180032256
0x18003224a  call    cs:__imp_SRCacheManager_Close
0x180032251  nop     dword ptr [rax+rax+00h]
0x180032256  mov     eax, edi
0x180032258  jmp     loc_1800325EC
0x18003225d  mov     rdx, [rsp+140h+var_108]
0x180032262  test    rdx, rdx
0x180032265  jnz     short loc_180032284
0x180032267  mov     rcx, [rbp+48h]; this
0x18003226b  lea     r9d, [rdx+2]; char *
0x18003226f  mov     edx, 1942h; void *
0x180032274  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003227b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032280  mov     edi, eax
0x180032282  jmp     short loc_180032233
0x180032284  xorps   xmm0, xmm0
0x180032287  mov     [rbp+40h+var_70], r12
0x18003228b  xorps   xmm1, xmm1
0x18003228e  movdqa  xmmword ptr [rbp+40h+var_80], xmm0
0x180032293  lea     rax, [rbp+40h+Block]
0x180032297  mov     [rbp+40h+var_68], r12
0x18003229b  mov     [rsp+140h+var_118], rax
0x1800322a0  lea     rcx, [rsp+140h+var_110]
0x1800322a5  lea     rax, [rbp+40h+var_80]
0x1800322a9  movdqa  [rbp+40h+var_60], xmm0
0x1800322ae  xor     r9d, r9d
0x1800322b1  mov     qword ptr [rsp+140h+var_120], rax; int
0x1800322b6  mov     r8, rsi
0x1800322b9  movdqa  [rbp+40h+var_50], xmm1
0x1800322be  movdqa  xmmword ptr [rbp+40h+var_40], xmm0
0x1800322c3  movdqa  [rbp+40h+var_30], xmm1
0x1800322c8  mov     byte ptr [rbp+40h+Block], r12b
0x1800322cc  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x1800322d1  mov     edi, eax
0x1800322d3  test    eax, eax
0x1800322d5  jns     short loc_1800322FD
0x1800322d7  mov     rcx, [rbp+48h]; this
0x1800322db  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800322e2  mov     r9d, eax; char *
0x1800322e5  mov     edx, 1948h; void *
0x1800322ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800322ef  lea     rcx, [rbp+40h+var_80]; this
0x1800322f3  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800322f8  jmp     loc_180032233
0x1800322fd  xorps   xmm0, xmm0
0x180032300  mov     [rsp+140h+var_D0], r12
0x180032305  lea     r9, [rbp+40h+Block]; bool *
0x180032309  movdqa  [rsp+140h+var_E0], xmm0
0x18003230f  lea     r8, [rsp+140h+var_E0]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x180032314  movdqa  [rbp+40h+var_A0], xmm0
0x180032319  lea     rdx, [rsp+140h+var_110]; struct StateRepository::Cache::Manager_NoThrow *
0x18003231e  mov     [rsp+140h+var_C8], r12
0x180032323  lea     rcx, [rbp+40h+var_80]; this
0x180032327  mov     [rbp+40h+var_C0], r12
0x18003232b  mov     [rbp+40h+var_B8], r12
0x18003232f  mov     [rbp+40h+var_B0], r12
0x180032333  mov     [rbp+40h+var_A8], r12
0x180032337  mov     [rbp+40h+var_90], r12d
0x18003233b  mov     [rbp+40h+var_88], r12
0x18003233f  call    ?GetPackage@Application_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180032344  mov     edi, eax
0x180032346  test    eax, eax
0x180032348  jns     short loc_18003236E
0x18003234a  mov     edx, 194Bh; void *
0x18003234f  mov     rcx, [rbp+48h]; this
0x180032353  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003235a  mov     r9d, edi; char *
0x18003235d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032362  lea     rcx, [rsp+140h+var_E0]; this
0x180032367  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003236c  jmp     short loc_1800322EF
0x18003236e  cmp     byte ptr [rbp+40h+Block], r12b
0x180032372  jnz     short loc_180032380
0x180032374  mov     edi, 80070490h
0x180032379  mov     edx, 194Ch
0x18003237e  jmp     short loc_18003234F
0x180032380  test    dword ptr [rsp+140h+var_C8+4], 200000h
0x180032388  jnz     short loc_1800323AA
0x18003238a  mov     rcx, [rbp+48h]; this
0x18003238e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032395  mov     r9d, 80070057h; char *
0x18003239b  mov     edx, 194Dh; void *
0x1800323a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800323a5  jmp     loc_1800324CD
0x1800323aa  mov     r8, qword ptr [rsp+140h+var_E0]
0x1800323af  lea     rax, [rbp+40h+Block]
0x1800323b3  mov     [rsp+140h+var_118], rax
0x1800323b8  lea     rcx, [rsp+140h+var_110]
0x1800323bd  lea     rax, [rsp+140h+var_100]
0x1800323c2  xorps   xmm0, xmm0
0x1800323c5  xorps   xmm1, xmm1
0x1800323c8  mov     qword ptr [rsp+140h+var_120], rax; int
0x1800323cd  xor     edx, edx
0x1800323cf  movdqu  xmmword ptr [rsp+140h+var_100], xmm0
0x1800323d5  movdqu  xmmword ptr [rsp+140h+var_F0], xmm1
0x1800323db  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x1800323e0  mov     edi, eax
0x1800323e2  test    eax, eax
0x1800323e4  jns     short loc_180032422
0x1800323e6  mov     edx, 1954h; void *
0x1800323eb  mov     rcx, [rbp+48h]; this
0x1800323ef  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800323f6  mov     r9d, edi; char *
0x1800323f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800323fe  mov     rcx, [rsp+140h+var_F0+8]
0x180032403  mov     [rsp+140h+var_F0+8], r12
0x180032408  test    rcx, rcx
0x18003240b  jz      loc_180032362
0x180032411  call    cs:__imp_SRCache_Free
0x180032418  nop     dword ptr [rax+rax+00h]
0x18003241d  jmp     loc_180032362
0x180032422  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch> `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl(void)'::`2'::impl
0x180032429  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(void)
0x18003242e  test    al, al
0x180032430  jz      short loc_18003246F
0x180032432  cmp     byte ptr [rbp+40h+Block], r12b
0x180032436  jnz     short loc_18003247C
0x180032438  mov     r8, qword ptr [rsp+140h+var_E0]
0x18003243d  lea     rax, [rbp+40h+Block]
0x180032441  mov     rdx, [rsp+140h+var_108]
0x180032446  lea     rcx, [rsp+140h+var_110]
0x18003244b  mov     [rsp+140h+var_118], rax
0x180032450  lea     rax, [rsp+140h+var_100]
0x180032455  mov     qword ptr [rsp+140h+var_120], rax
0x18003245a  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18003245f  mov     edi, eax
0x180032461  test    eax, eax
0x180032463  jns     short loc_18003246F
0x180032465  mov     edx, 195Ch
0x18003246a  jmp     loc_1800323EB
0x18003246f  cmp     byte ptr [rbp+40h+Block], r12b
0x180032473  jnz     short loc_18003247C
0x180032475  mov     edx, 1960h
0x18003247a  jmp     short loc_18003249C
0x18003247c  mov     rcx, [rsp+140h+var_F0+8]
0x180032481  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180032485  mov     rax, rdx
0x180032488  inc     rax
0x18003248b  cmp     [rcx+rax*2], r12w
0x180032490  jnz     short loc_180032488
0x180032492  test    rax, rax
0x180032495  jnz     short loc_18003250D
0x180032497  mov     edx, 1967h; void *
0x18003249c  mov     rcx, [rbp+48h]; this
0x1800324a0  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800324a7  mov     r9d, 80070057h; char *
0x1800324ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800324b2  mov     rcx, [rsp+140h+var_F0+8]
0x1800324b7  mov     [rsp+140h+var_F0+8], r12
0x1800324bc  test    rcx, rcx
0x1800324bf  jz      short loc_1800324CD
0x1800324c1  call    cs:__imp_SRCache_Free
0x1800324c8  nop     dword ptr [rax+rax+00h]
0x1800324cd  lea     rcx, [rsp+140h+var_E0]; this
0x1800324d2  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800324d7  lea     rcx, [rbp+40h+var_80]; this
0x1800324db  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800324e0  mov     rcx, rbx; Block
0x1800324e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800324e8  mov     rcx, [rsp+140h+var_110]
0x1800324ed  mov     [rsp+140h+var_110], r12
0x1800324f2  test    rcx, rcx
0x1800324f5  jz      short loc_180032503
0x1800324f7  call    cs:__imp_SRCacheManager_Close
0x1800324fe  nop     dword ptr [rax+rax+00h]
0x180032503  mov     eax, 80070057h
0x180032508  jmp     loc_1800325EC
0x18003250d  movzx   r14d, word ptr [rcx+rax*2-2]
0x180032513  mov     rcx, [rbp+40h+var_40+8]
0x180032517  inc     rdx
0x18003251a  cmp     [rcx+rdx*2], r12w
0x18003251f  jnz     short loc_180032517
0x180032521  mov     rcx, r12
0x180032524  cmp     r14w, 5Ch ; '\'
0x180032529  setnz   cl
0x18003252c  add     rax, rdx
0x18003252f  add     rcx, rax
0x180032532  xor     edx, edx
0x180032534  lea     rax, ds:2[rcx*2]
0x18003253c  mov     r8d, eax
0x18003253f  lea     rcx, [rbp+40h+Block]
0x180032543  mov     esi, eax
0x180032545  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003254a  mov     rdi, [rbp+40h+Block]
0x18003254e  mov     edx, esi; unsigned __int64
0x180032550  mov     r8, [rsp+140h+var_F0+8]; unsigned __int16 *
0x180032555  mov     rcx, rdi; unsigned __int16 *
0x180032558  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003255d  cmp     r14w, 5Ch ; '\'
0x180032562  jz      short loc_180032575
0x180032564  lea     r8, asc_18004C1CC; "\\"
0x18003256b  mov     edx, esi; unsigned __int64
0x18003256d  mov     rcx, rdi; unsigned __int16 *
0x180032570  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180032575  mov     r8, [rbp+40h+var_40+8]; unsigned __int16 *
0x180032579  mov     rdx, rsi; unsigned __int64
0x18003257c  mov     rcx, rdi; unsigned __int16 *
0x18003257f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180032584  lea     rdx, [rbp+40h+Block]
0x180032588  mov     rcx, r15
0x18003258b  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180032590  lea     rcx, [rbp+40h+Block]
0x180032594  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032599  mov     rcx, [rsp+140h+var_F0+8]
0x18003259e  mov     [rsp+140h+var_F0+8], r12
0x1800325a3  test    rcx, rcx
0x1800325a6  jz      short loc_1800325B4
0x1800325a8  call    cs:__imp_SRCache_Free
0x1800325af  nop     dword ptr [rax+rax+00h]
0x1800325b4  lea     rcx, [rsp+140h+var_E0]; this
0x1800325b9  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800325be  lea     rcx, [rbp+40h+var_80]; this
0x1800325c2  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800325c7  mov     rcx, rbx; Block
0x1800325ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800325cf  mov     rcx, [rsp+140h+var_110]
0x1800325d4  mov     [rsp+140h+var_110], r12
0x1800325d9  test    rcx, rcx
0x1800325dc  jz      short loc_1800325EA
0x1800325de  call    cs:__imp_SRCacheManager_Close
  ... truncated ...
```
