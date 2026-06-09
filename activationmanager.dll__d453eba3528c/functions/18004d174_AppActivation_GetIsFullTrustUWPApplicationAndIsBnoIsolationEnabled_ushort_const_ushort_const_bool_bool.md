# AppActivation::GetIsFullTrustUWPApplicationAndIsBnoIsolationEnabled(ushort const *,ushort const *,bool *,bool *)

- ea: `0x18004d174`
- end: `0x18004d5a4`
- name: `?GetIsFullTrustUWPApplicationAndIsBnoIsolationEnabled@AppActivation@@AEAAJPEBG0PEA_N1@Z`
- size: `1072`
- prototype: `int(AppActivation *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180042ca8`

## callees

- `0x180006530`
- `0x180008ec0`
- `0x18000b5c0`
- `0x18002c900`
- `0x18002cc58`
- `0x18004d174`
- `0x18004d5ac`
- `0x18004d634`
- `0x18004d6ec`
- `0x180056fe8`
- `0x18008408c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18004d1d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18004d1d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004d233`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004d2a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004d581`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004d233`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004d2a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004d581`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004d3ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004d55e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004d3ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004d55e`

## string_xrefs

- `0x18004d1f1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18004d38c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18004d4bf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall AppActivation::GetIsFullTrustUWPApplicationAndIsBnoIsolationEnabled(
        AppActivation *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        bool *a4,
        bool *a5)
{
  bool *v5; // r12
  char v7; // bl
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  bool v16; // r15
  char v17; // r14
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // r8
  __int16 v23; // ax
  char v24; // cl
  int v25; // eax
  bool v26; // cl
  char v27; // al
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+38h] [rbp-C8h]
  __int64 v36; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  char v40; // [rsp+60h] [rbp-A0h]
  __int64 v41[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  __int128 v44; // [rsp+90h] [rbp-70h]
  __int128 v45; // [rsp+A0h] [rbp-60h]
  __int128 v46; // [rsp+B0h] [rbp-50h]
  __int128 v47; // [rsp+C0h] [rbp-40h]
  __int128 v48; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  __int128 v51; // [rsp+F0h] [rbp-10h]
  __int128 v52; // [rsp+100h] [rbp+0h]
  __int64 v53; // [rsp+110h] [rbp+10h]
  int v54; // [rsp+118h] [rbp+18h]
  __int128 v55; // [rsp+120h] [rbp+20h] BYREF
  int v56; // [rsp+130h] [rbp+30h]
  __int64 v57; // [rsp+138h] [rbp+38h]
  __int128 v58; // [rsp+140h] [rbp+40h]
  __int128 v59; // [rsp+150h] [rbp+50h]
  __int64 v60; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  AppActivation *v62; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v63; // [rsp+1C8h] [rbp+C8h] BYREF

  v62 = this;
  v5 = a5;
  v38 = &v63;
  *a4 = 0;
  v7 = 1;
  v63 = 0;
  *v5 = 0;
  v39 = 0;
  v40 = 1;
  v10 = SRCacheManager_Open(0, &v39);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v38);
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)v10,
      v30);
    v11 = 195;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)v10,
      v30);
    v12 = v63;
    v63 = 0;
LABEL_4:
    if ( v12 )
      SRCacheManager_Close();
    return v10;
  }
  v37 = 0;
  v10 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
          (struct StateRepository::Cache::Manager_NoThrow *)&v63,
          0,
          &v37);
  if ( (v10 & 0x80000000) != 0 )
  {
    v11 = 198;
    goto LABEL_3;
  }
  if ( !v37 )
  {
    v14 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)0x80070490LL,
      v30);
LABEL_11:
    v15 = v63;
    v63 = 0;
    if ( v15 )
      SRCacheManager_Close();
    return v14;
  }
  v42 = 0;
  *(_OWORD *)v41 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  LOBYTE(v62) = 0;
  StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(
    (struct StateRepository::Cache::Manager_NoThrow *)&v63,
    v37,
    a2,
    0,
    (__int64)v41,
    (bool *)&v62);
  if ( !(_BYTE)v62 )
  {
    v14 = -2144927141;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)0x8027025BLL,
      v31);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v41);
    goto LABEL_11;
  }
  v16 = (v42 & 0x400000000LL) != 0;
  v17 = BYTE5(v42) & 1;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v18 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
          (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v34,
          (struct StateRepository::Cache::Manager_NoThrow *)&v63,
          v41[0],
          a3);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v18,
      v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)v10,
      v32);
LABEL_18:
    v20 = v34;
    v34 = 0;
    if ( v20 )
      SRCacheContext_Close(v20);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v41);
    v12 = v63;
    v63 = 0;
    goto LABEL_4;
  }
  v49 = 0;
  v48 = 0;
  v51 = 0;
  v52 = 0;
  v50 = 0;
  v53 = 0;
  v54 = 0;
  LOBYTE(v62) = 0;
  v21 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(&v34, v19, &v48, &v62);
  v10 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v21,
      v31);
LABEL_23:
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v48);
    goto LABEL_18;
  }
  v23 = 0;
  v24 = 0;
  v55 = 0;
  v56 = 0;
  v58 = 0;
  v59 = 0;
  LOBYTE(a5) = 0;
  v57 = 0;
  v60 = 0;
  if ( (_BYTE)v62 )
  {
    v25 = StateRepository::Cache::Entity::Activation_NoThrow::Get(&v63, v51, v22, &v55);
    v10 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x360,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
        (const char *)(unsigned int)v25,
        (int)&a5);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)v10,
        v33);
      StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v55);
      goto LABEL_23;
    }
    v23 = v56;
    v24 = (char)a5;
  }
  if ( v24 )
  {
    v26 = (v23 & 4) != 0;
    v27 = HIBYTE(v23) & 1;
  }
  else
  {
    v27 = v17;
    v26 = v16;
  }
  if ( v26 && v27 )
  {
    *a4 = 1;
  }
  else
  {
    *a4 = 0;
    if ( !v26 )
    {
LABEL_36:
      v7 = 0;
      goto LABEL_37;
    }
  }
  if ( (v42 & 0x4000000000LL) == 0 )
    goto LABEL_36;
LABEL_37:
  *v5 = v7;
  StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v55);
  StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v48);
  v28 = v34;
  v34 = 0;
  if ( v28 )
    SRCacheContext_Close(v28);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v41);
  v29 = v63;
  v63 = 0;
  if ( v29 )
    SRCacheManager_Close();
  return 0;
}

```

## disassembly

```asm
0x18004d174  mov     [rsp-8+arg_8], rbx
0x18004d179  mov     [rsp-8+arg_0], rcx
0x18004d17e  push    rbp
0x18004d17f  push    rsi
0x18004d180  push    rdi
0x18004d181  push    r12
0x18004d183  push    r13
0x18004d185  push    r14
0x18004d187  push    r15
0x18004d189  lea     rbp, [rsp-70h]
0x18004d18e  sub     rsp, 170h
0x18004d195  mov     r12, [rbp+0A0h+arg_20]
0x18004d19c  lea     rax, [rbp+0A0h+arg_18]
0x18004d1a3  xor     r15d, r15d
0x18004d1a6  mov     [rsp+1A0h+var_150], rax
0x18004d1ab  mov     r14, rdx
0x18004d1ae  mov     [r9], r15b
0x18004d1b1  mov     bl, 1
0x18004d1b3  mov     [rbp+0A0h+arg_18], r15
0x18004d1ba  lea     rdx, [rsp+1A0h+var_148]
0x18004d1bf  mov     [r12], r15b
0x18004d1c3  xor     ecx, ecx
0x18004d1c5  mov     [rsp+1A0h+var_148], r15
0x18004d1ca  mov     rsi, r9
0x18004d1cd  mov     [rsp+1A0h+var_140], bl
0x18004d1d1  mov     r13, r8
0x18004d1d4  call    cs:__imp_SRCacheManager_Open
0x18004d1da  lea     rcx, [rsp+1A0h+var_150]
0x18004d1df  mov     edi, eax
0x18004d1e1  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18004d1e6  test    edi, edi
0x18004d1e8  jns     short loc_18004D240
0x18004d1ea  mov     rcx, [rbp+0A8h]; this
0x18004d1f1  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004d1f8  mov     r9d, edi; char *
0x18004d1fb  mov     edx, 0A5h; void *
0x18004d200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d205  mov     edx, 0C3h; void *
0x18004d20a  mov     rcx, [rbp+0A8h]; this
0x18004d211  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004d218  mov     r9d, edi; char *
0x18004d21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d220  mov     rcx, [rbp+0A0h+arg_18]
0x18004d227  mov     [rbp+0A0h+arg_18], r15
0x18004d22e  test    rcx, rcx
0x18004d231  jz      short loc_18004D239
0x18004d233  call    cs:__imp_SRCacheManager_Close
0x18004d239  mov     eax, edi
0x18004d23b  jmp     loc_18004D589
0x18004d240  lea     r8, [rsp+1A0h+var_158]; __int64 *
0x18004d245  mov     [rsp+1A0h+var_158], r15
0x18004d24a  xor     edx, edx; void *
0x18004d24c  lea     rcx, [rbp+0A0h+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x18004d253  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18004d258  mov     edi, eax
0x18004d25a  test    eax, eax
0x18004d25c  jns     short loc_18004D265
0x18004d25e  mov     edx, 0C6h
0x18004d263  jmp     short loc_18004D20A
0x18004d265  mov     rdx, [rsp+1A0h+var_158]
0x18004d26a  test    rdx, rdx
0x18004d26d  jnz     short loc_18004D2AF
0x18004d26f  mov     rcx, [rbp+0A8h]; this
0x18004d276  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004d27d  mov     ebx, 80070490h
0x18004d282  mov     edx, 0C7h; void *
0x18004d287  mov     r9d, ebx; char *
0x18004d28a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d28f  mov     rcx, [rbp+0A0h+arg_18]
0x18004d296  mov     [rbp+0A0h+arg_18], r15
0x18004d29d  test    rcx, rcx
0x18004d2a0  jz      short loc_18004D2A8
0x18004d2a2  call    cs:__imp_SRCacheManager_Close
0x18004d2a8  mov     eax, ebx
0x18004d2aa  jmp     loc_18004D589
0x18004d2af  xorps   xmm0, xmm0
0x18004d2b2  mov     [rbp+0A0h+var_120], r15
0x18004d2b6  xorps   xmm1, xmm1
0x18004d2b9  movdqa  xmmword ptr [rsp+1A0h+var_130], xmm0
0x18004d2bf  lea     rax, [rbp+0A0h+arg_0]
0x18004d2c6  mov     [rbp+0A0h+var_118], r15
0x18004d2ca  mov     [rsp+1A0h+var_178], rax
0x18004d2cf  lea     rcx, [rbp+0A0h+arg_18]
0x18004d2d6  lea     rax, [rsp+1A0h+var_130]
0x18004d2db  movdqa  [rbp+0A0h+var_110], xmm0
0x18004d2e0  xor     r9d, r9d
0x18004d2e3  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18004d2e8  mov     r8, r14
0x18004d2eb  movdqa  [rbp+0A0h+var_100], xmm1
0x18004d2f0  movdqa  [rbp+0A0h+var_F0], xmm0
0x18004d2f5  movdqa  [rbp+0A0h+var_E0], xmm1
0x18004d2fa  mov     byte ptr [rbp+0A0h+arg_0], r15b
0x18004d301  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18004d306  cmp     byte ptr [rbp+0A0h+arg_0], r15b
0x18004d30d  jnz     short loc_18004D33E
0x18004d30f  mov     rcx, [rbp+0A8h]; this
0x18004d316  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004d31d  mov     ebx, 8027025Bh
0x18004d322  mov     edx, 0D2h; void *
0x18004d327  mov     r9d, ebx; char *
0x18004d32a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d32f  lea     rcx, [rsp+1A0h+var_130]; this
0x18004d334  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18004d339  jmp     loc_18004D28F
0x18004d33e  mov     r14d, dword ptr [rbp+0A0h+var_120+4]
0x18004d342  lea     rdx, [rbp+0A0h+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x18004d349  mov     r8, [rsp+1A0h+var_130]; __int64
0x18004d34e  lea     rcx, [rsp+1A0h+var_170]; this
0x18004d353  xor     eax, eax
0x18004d355  mov     r15d, r14d
0x18004d358  shr     r15d, 2
0x18004d35c  mov     r9, r13; unsigned __int16 *
0x18004d35f  shr     r14d, 8
0x18004d363  and     r15b, bl
0x18004d366  and     r14b, bl
0x18004d369  mov     [rsp+1A0h+var_170], rax
0x18004d36e  mov     [rsp+1A0h+var_168], eax
0x18004d372  mov     [rsp+1A0h+var_160], rax
0x18004d377  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x18004d37c  xor     r13d, r13d
0x18004d37f  mov     edi, eax
0x18004d381  test    eax, eax
0x18004d383  jns     short loc_18004D3ED
0x18004d385  mov     rcx, [rbp+0A8h]; this
0x18004d38c  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004d393  mov     r9d, eax; char *
0x18004d396  mov     edx, 3B9h; void *
0x18004d39b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d3a0  mov     rcx, [rbp+0A8h]; this
0x18004d3a7  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004d3ae  mov     r9d, edi; char *
0x18004d3b1  mov     edx, 0D8h; void *
0x18004d3b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d3bb  mov     rcx, [rsp+1A0h+var_170]
0x18004d3c0  mov     [rsp+1A0h+var_170], r13
0x18004d3c5  test    rcx, rcx
0x18004d3c8  jz      short loc_18004D3D0
0x18004d3ca  call    cs:__imp_SRCacheContext_Close
0x18004d3d0  lea     rcx, [rsp+1A0h+var_130]; this
0x18004d3d5  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18004d3da  mov     rcx, [rbp+0A0h+arg_18]
0x18004d3e1  mov     [rbp+0A0h+arg_18], r13
0x18004d3e8  jmp     loc_18004D22E
0x18004d3ed  xorps   xmm0, xmm0
0x18004d3f0  mov     [rbp+0A0h+var_C0], r13
0x18004d3f4  xorps   xmm1, xmm1
0x18004d3f7  movdqa  [rbp+0A0h+var_D0], xmm0
0x18004d3fc  lea     r9, [rbp+0A0h+arg_0]
0x18004d403  movdqa  [rbp+0A0h+var_B0], xmm0
0x18004d408  lea     r8, [rbp+0A0h+var_D0]
0x18004d40c  movdqa  [rbp+0A0h+var_A0], xmm1
0x18004d411  lea     rcx, [rsp+1A0h+var_170]
0x18004d416  mov     [rbp+0A0h+var_B8], r13
0x18004d41a  mov     [rbp+0A0h+var_90], r13
0x18004d41e  mov     [rbp+0A0h+var_88], r13d
0x18004d422  mov     byte ptr [rbp+0A0h+arg_0], r13b
0x18004d429  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x18004d42e  mov     edi, eax
0x18004d430  test    eax, eax
0x18004d432  jns     short loc_18004D45D
0x18004d434  mov     rcx, [rbp+0A8h]; this
0x18004d43b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004d442  mov     r9d, eax; char *
0x18004d445  mov     edx, 0DCh; void *
0x18004d44a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d44f  lea     rcx, [rbp+0A0h+var_D0]; this
0x18004d453  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18004d458  jmp     loc_18004D3BB
0x18004d45d  xorps   xmm0, xmm0
0x18004d460  mov     eax, r13d
0x18004d463  xorps   xmm1, xmm1
0x18004d466  mov     cl, r13b
0x18004d469  movdqa  [rbp+0A0h+var_80], xmm0
0x18004d46e  mov     [rbp+0A0h+var_70], eax
0x18004d471  movdqa  [rbp+0A0h+var_60], xmm0
0x18004d476  movdqa  [rbp+0A0h+var_50], xmm1
0x18004d47b  mov     byte ptr [rbp+0A0h+arg_20], cl
0x18004d481  mov     [rbp+0A0h+var_68], r13
0x18004d485  mov     [rbp+0A0h+var_40], r13
0x18004d489  cmp     byte ptr [rbp+0A0h+arg_0], r13b
0x18004d490  jz      short loc_18004D505
0x18004d492  mov     rdx, qword ptr [rbp+0A0h+var_B0]
0x18004d496  lea     rax, [rbp+0A0h+arg_20]
0x18004d49d  lea     r9, [rbp+0A0h+var_80]
0x18004d4a1  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18004d4a6  lea     rcx, [rbp+0A0h+arg_18]
0x18004d4ad  call    ?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x18004d4b2  mov     edi, eax
0x18004d4b4  test    eax, eax
0x18004d4b6  jns     short loc_18004D4FC
0x18004d4b8  mov     rcx, [rbp+0A8h]; this
0x18004d4bf  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004d4c6  mov     r9d, eax; char *
0x18004d4c9  mov     edx, 360h; void *
0x18004d4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d4d3  mov     rcx, [rbp+0A8h]; this
0x18004d4da  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004d4e1  mov     r9d, edi; char *
0x18004d4e4  mov     edx, 0E2h; void *
0x18004d4e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d4ee  lea     rcx, [rbp+0A0h+var_80]; this
0x18004d4f2  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18004d4f7  jmp     loc_18004D44F
0x18004d4fc  mov     eax, [rbp+0A0h+var_70]
0x18004d4ff  mov     cl, byte ptr [rbp+0A0h+arg_20]
0x18004d505  test    cl, cl
0x18004d507  jz      short loc_18004D517
0x18004d509  mov     ecx, eax
0x18004d50b  shr     eax, 8
0x18004d50e  shr     ecx, 2
0x18004d511  and     cl, bl
0x18004d513  and     al, bl
0x18004d515  jmp     short loc_18004D51D
0x18004d517  mov     al, r14b
0x18004d51a  mov     cl, r15b
0x18004d51d  test    cl, cl
0x18004d51f  jz      short loc_18004D529
0x18004d521  test    al, al
0x18004d523  jz      short loc_18004D529
0x18004d525  mov     [rsi], bl
0x18004d527  jmp     short loc_18004D530
0x18004d529  mov     [rsi], r13b
0x18004d52c  test    cl, cl
0x18004d52e  jz      short loc_18004D536
0x18004d530  test    byte ptr [rbp+0A0h+var_120+4], 40h
0x18004d534  jnz     short loc_18004D539
0x18004d536  mov     bl, r13b
0x18004d539  lea     rcx, [rbp+0A0h+var_80]; this
0x18004d53d  mov     [r12], bl
0x18004d541  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18004d546  lea     rcx, [rbp+0A0h+var_D0]; this
0x18004d54a  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18004d54f  mov     rcx, [rsp+1A0h+var_170]
0x18004d554  mov     [rsp+1A0h+var_170], r13
0x18004d559  test    rcx, rcx
0x18004d55c  jz      short loc_18004D564
0x18004d55e  call    cs:__imp_SRCacheContext_Close
0x18004d564  lea     rcx, [rsp+1A0h+var_130]; this
0x18004d569  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18004d56e  mov     rcx, [rbp+0A0h+arg_18]
0x18004d575  mov     [rbp+0A0h+arg_18], r13
0x18004d57c  test    rcx, rcx
0x18004d57f  jz      short loc_18004D587
0x18004d581  call    cs:__imp_SRCacheManager_Close
0x18004d587  xor     eax, eax
0x18004d589  mov     rbx, [rsp+1A0h+arg_8]
0x18004d591  add     rsp, 170h
0x18004d598  pop     r15
0x18004d59a  pop     r14
0x18004d59c  pop     r13
0x18004d59e  pop     r12
0x18004d5a0  pop     rdi
0x18004d5a1  pop     rsi
0x18004d5a2  pop     rbp
0x18004d5a3  retn
```
