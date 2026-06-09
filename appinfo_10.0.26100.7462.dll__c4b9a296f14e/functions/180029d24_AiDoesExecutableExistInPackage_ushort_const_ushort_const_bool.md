# AiDoesExecutableExistInPackage(ushort const *,ushort const *,bool *)

- ea: `0x180029d24`
- end: `0x18002a2a0`
- name: `?AiDoesExecutableExistInPackage@@YAJPEBG0PEA_N@Z`
- size: `1404`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a2a8`

## callees

- `0x180006510`
- `0x180007b30`
- `0x180007c78`
- `0x18000a1f0`
- `0x18000dca8`
- `0x18000dd90`
- `0x18001053c`
- `0x180012634`
- `0x180018530`
- `0x180026910`
- `0x180029d24`
- `0x18002bf84`
- `0x18002d40c`
- `0x180035744`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a049`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a049`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002a254`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002a254`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180029d99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a103`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a1b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a229`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180029d99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a103`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a1b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a229`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180029f3b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a0dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a136`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a191`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a206`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180029f3b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a0dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a136`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a191`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a206`

## string_xrefs

- `0x180029efc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180029d78`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029e11`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029e44`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029e84`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029f14`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029f9c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a15a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a1cc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall AiDoesExecutableExistInPackage(const unsigned __int16 *a1, const unsigned __int16 *a2, bool *a3)
{
  int v6; // eax
  int IsTrustedAndInPackage; // ebx
  __int64 v8; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r13
  __int64 v14; // rcx
  __int64 v15; // rdi
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r14
  __int64 v22; // rax
  const WCHAR *v23; // rbx
  const unsigned __int16 *v24; // r8
  int v25; // eax
  unsigned int v26; // r14d
  const unsigned __int16 *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
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
  unsigned __int64 v51; // [rsp+B0h] [rbp-50h]
  __int128 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+D8h] [rbp-28h]
  __int128 v55; // [rsp+E0h] [rbp-20h]
  __int128 v56; // [rsp+F0h] [rbp-10h]
  int v57[4]; // [rsp+100h] [rbp+0h]
  __int128 v58; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  unsigned int v60; // [rsp+160h] [rbp+60h] BYREF
  __int64 v61; // [rsp+170h] [rbp+70h] BYREF
  LPCWCH lpString1; // [rsp+178h] [rbp+78h] BYREF

  *a3 = 0;
  if ( !a1 || !a2 )
  {
    *a3 = 1;
    return 0;
  }
  v61 = 0;
  v6 = StateRepository::Cache::Manager_NoThrow::Open(&v61);
  IsTrustedAndInPackage = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24AC,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
LABEL_5:
    v8 = v61;
    v61 = 0;
    if ( v8 )
      SRCacheManager_Close();
    return (unsigned int)IsTrustedAndInPackage;
  }
  v42 = 0;
  *(_OWORD *)v41 = 0;
  v48 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v49 = 0;
  v50 = 0;
  LOBYTE(v60) = 0;
  IsTrustedAndInPackage = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
                            (struct StateRepository::Cache::Manager_NoThrow *)&v61,
                            a1,
                            304,
                            (__int64)v41,
                            (bool *)&v60);
  if ( IsTrustedAndInPackage < 0 )
  {
    v10 = 9399;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCasea);
LABEL_11:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
    goto LABEL_5;
  }
  if ( !(_BYTE)v60 )
  {
    v11 = 2;
    v12 = 9403;
LABEL_14:
    IsTrustedAndInPackage = wil::details::in1diag3::Return_Win32(
                              retaddr,
                              (void *)v12,
                              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                              (const char *)v11,
                              bIgnoreCasea);
    goto LABEL_11;
  }
  v11 = 3;
  if ( HIDWORD(v44) == 3 && (v44 & 0x10) != 0 || (v44 & 0x20) != 0 )
  {
    v60 = 0;
    IsTrustedAndInPackage = VerifyFileIsTrustedAndInPackage(a2, a1, &v60);
    if ( IsTrustedAndInPackage < 0 )
    {
      v10 = 9414;
      goto LABEL_10;
    }
    *a3 = v60 != 0;
LABEL_44:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
    v29 = v61;
    v61 = 0;
    if ( v29 )
      SRCacheManager_Close();
    return 0;
  }
  v13 = v47;
  if ( !v47 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24CC,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x8007000ELL,
      bIgnoreCasea);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
    v14 = v61;
    v61 = 0;
    goto LABEL_57;
  }
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v47 + 2 * v15) );
  if ( !v15 )
  {
    v12 = 9425;
    goto LABEL_14;
  }
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v16 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
          (StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *)&v38,
          (struct StateRepository::Cache::Manager_NoThrow *)&v61,
          v41[0]);
  IsTrustedAndInPackage = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v16,
      bIgnoreCasea);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24D5,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCasec);
LABEL_26:
    v18 = v38;
    v38 = 0;
    if ( v18 )
      SRCacheContext_Close(v18);
    goto LABEL_11;
  }
  v53 = 0;
  v52 = 0;
  v55 = 0;
  v56 = 0;
  *(_OWORD *)v57 = 0;
  v58 = 0;
  v54 = 0;
  LOBYTE(v60) = 0;
  IsTrustedAndInPackage = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v38, v17, &v52, &v60);
  if ( IsTrustedAndInPackage < 0 )
  {
    v20 = 9435;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCasea);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v52);
    goto LABEL_26;
  }
  while ( 1 )
  {
    if ( !(_BYTE)v60 )
    {
      v27 = AipJustFileName(a2);
      AipLogDesktopAppXProcessStartFailure(8, 0, a1, v27, &String2, L"[AiDoesExecutableExistInPackage]");
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v52);
      v28 = v38;
      v38 = 0;
      if ( v28 )
        SRCacheContext_Close(v28);
      goto LABEL_44;
    }
    v21 = *(_QWORD *)&v57[2];
    if ( !*(_QWORD *)&v57[2] )
      goto LABEL_40;
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(*(_QWORD *)&v57[2] + 2 * v22) );
    v51 = v15 + v22 + 4;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpString1,
      0,
      v51);
    v23 = lpString1;
    if ( !lpString1 )
      break;
    v24 = L"%s\\%s";
    if ( *(_WORD *)(v13 + 2 * v15 - 2) == 92 )
      v24 = L"%s%s";
    v25 = StringCchPrintfW((unsigned __int16 *)lpString1, v51, v24, v13, v21);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24ED,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v25,
        bIgnoreCaseb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v52);
      v31 = v38;
      v38 = 0;
      if ( v31 )
        SRCacheContext_Close(v31);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
      v32 = v61;
      v61 = 0;
      if ( v32 )
        SRCacheManager_Close();
      return v26;
    }
    if ( CompareStringOrdinal(v23, -1, a2, -1, 1) == 2 )
    {
      *a3 = 1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v52);
      v30 = v38;
      v38 = 0;
      if ( v30 )
        SRCacheContext_Close(v30);
      goto LABEL_44;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
LABEL_40:
    ++v39;
    IsTrustedAndInPackage = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v38, v19, &v52, &v60);
    if ( IsTrustedAndInPackage < 0 )
    {
      v20 = 9463;
      goto LABEL_30;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x24E5,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
    (const char *)0x8007000ELL,
    bIgnoreCasea);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v52);
  v33 = v38;
  v38 = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v41);
  v14 = v61;
  v61 = 0;
LABEL_57:
  if ( v14 )
    SRCacheManager_Close();
  return 2147942414LL;
}

```

## disassembly

```asm
0x180029d24  mov     [rsp-8+arg_8], rbx
0x180029d29  push    rbp
0x180029d2a  push    rsi
0x180029d2b  push    rdi
0x180029d2c  push    r12
0x180029d2e  push    r13
0x180029d30  push    r14
0x180029d32  push    r15
0x180029d34  lea     rbp, [rsp-20h]
0x180029d39  sub     rsp, 120h
0x180029d40  xor     r14d, r14d
0x180029d43  mov     rsi, r8
0x180029d46  mov     [r8], r14b
0x180029d49  mov     r15, rdx
0x180029d4c  mov     r12, rcx
0x180029d4f  test    rcx, rcx
0x180029d52  jz      loc_18002A27E
0x180029d58  test    rdx, rdx
0x180029d5b  jz      loc_18002A27E
0x180029d61  lea     rcx, [rbp+50h+arg_10]
0x180029d65  mov     [rbp+50h+arg_10], r14
0x180029d69  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x180029d6e  mov     ebx, eax
0x180029d70  test    eax, eax
0x180029d72  jns     short loc_180029DAC
0x180029d74  mov     rcx, [rbp+58h]; this
0x180029d78  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029d7f  mov     r9d, eax; char *
0x180029d82  mov     edx, 24ACh; void *
0x180029d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d8c  mov     rcx, [rbp+50h+arg_10]
0x180029d90  mov     [rbp+50h+arg_10], r14
0x180029d94  test    rcx, rcx
0x180029d97  jz      short loc_180029DA5
0x180029d99  call    cs:__imp_SRCacheManager_Close
0x180029da0  nop     dword ptr [rax+rax+00h]
0x180029da5  mov     eax, ebx
0x180029da7  jmp     loc_18002A284
0x180029dac  xorps   xmm0, xmm0
0x180029daf  mov     [rsp+150h+var_F0], r14
0x180029db4  lea     rax, [rbp+50h+arg_0]
0x180029db8  movdqa  xmmword ptr [rsp+150h+var_100], xmm0
0x180029dbe  lea     r9, [rsp+150h+var_100]
0x180029dc3  movdqa  [rbp+50h+var_C0], xmm0
0x180029dc8  mov     r8d, 130h
0x180029dce  mov     qword ptr [rsp+150h+bIgnoreCase], rax; int
0x180029dd3  mov     rdx, r12
0x180029dd6  mov     [rsp+150h+var_E8], r14
0x180029ddb  lea     rcx, [rbp+50h+arg_10]
0x180029ddf  mov     [rsp+150h+var_E0], r14
0x180029de4  mov     [rsp+150h+var_D8], r14
0x180029de9  mov     [rbp+50h+var_D0], r14
0x180029ded  mov     [rbp+50h+var_C8], r14
0x180029df1  mov     [rbp+50h+var_B0], r14d
0x180029df5  mov     [rbp+50h+var_A8], r14
0x180029df9  mov     byte ptr [rbp+50h+arg_0], r14b
0x180029dfd  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180029e02  mov     ebx, eax
0x180029e04  test    eax, eax
0x180029e06  jns     short loc_180029E2F
0x180029e08  mov     edx, 24B7h; void *
0x180029e0d  mov     rcx, [rbp+58h]; this
0x180029e11  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029e18  mov     r9d, ebx; char *
0x180029e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e20  lea     rcx, [rsp+150h+var_100]; this
0x180029e25  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180029e2a  jmp     loc_180029D8C
0x180029e2f  cmp     byte ptr [rbp+50h+arg_0], r14b
0x180029e33  jnz     short loc_180029E54
0x180029e35  mov     r9d, 2; char *
0x180029e3b  mov     edx, 24BBh; void *
0x180029e40  mov     rcx, [rbp+58h]; this
0x180029e44  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029e4b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180029e50  mov     ebx, eax
0x180029e52  jmp     short loc_180029E20
0x180029e54  mov     r9d, 3
0x180029e5a  cmp     dword ptr [rsp+150h+var_E0+4], r9d
0x180029e5f  jnz     short loc_180029E6C
0x180029e61  test    byte ptr [rsp+150h+var_E0], 10h
0x180029e66  jnz     loc_18002A246
0x180029e6c  test    byte ptr [rsp+150h+var_E0], 20h
0x180029e71  jnz     loc_18002A246
0x180029e77  mov     r13, [rbp+50h+var_C8]
0x180029e7b  test    r13, r13
0x180029e7e  jnz     short loc_180029EB2
0x180029e80  mov     rcx, [rbp+58h]; this
0x180029e84  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029e8b  mov     r9d, 8007000Eh; char *
0x180029e91  mov     edx, 24CCh; void *
0x180029e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e9b  lea     rcx, [rsp+150h+var_100]; this
0x180029ea0  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180029ea5  mov     rcx, [rbp+50h+arg_10]
0x180029ea9  mov     [rbp+50h+arg_10], r14
0x180029ead  jmp     loc_18002A224
0x180029eb2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029eb6  inc     rdi
0x180029eb9  cmp     [r13+rdi*2+0], r14w
0x180029ebf  jnz     short loc_180029EB6
0x180029ec1  test    rdi, rdi
0x180029ec4  jnz     short loc_180029ED0
0x180029ec6  mov     edx, 24D1h
0x180029ecb  jmp     loc_180029E40
0x180029ed0  mov     r8, [rsp+150h+var_100]; __int64
0x180029ed5  lea     rdx, [rbp+50h+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x180029ed9  lea     rcx, [rsp+150h+var_120]; this
0x180029ede  mov     [rsp+150h+var_120], r14
0x180029ee3  mov     [rsp+150h+var_118], r14d
0x180029ee8  mov     [rsp+150h+var_110], r14
0x180029eed  call    ?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)
0x180029ef2  mov     ebx, eax
0x180029ef4  test    eax, eax
0x180029ef6  jns     short loc_180029F4C
0x180029ef8  mov     rcx, [rbp+58h]; this
0x180029efc  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180029f03  mov     r9d, eax; char *
0x180029f06  mov     edx, 47Bh; void *
0x180029f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029f10  mov     rcx, [rbp+58h]; this
0x180029f14  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029f1b  mov     r9d, ebx; char *
0x180029f1e  mov     edx, 24D5h; void *
0x180029f23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029f28  mov     rcx, [rsp+150h+var_120]
0x180029f2d  mov     [rsp+150h+var_120], r14
0x180029f32  test    rcx, rcx
0x180029f35  jz      loc_180029E20
0x180029f3b  call    cs:__imp_SRCacheContext_Close
0x180029f42  nop     dword ptr [rax+rax+00h]
0x180029f47  jmp     loc_180029E20
0x180029f4c  xorps   xmm0, xmm0
0x180029f4f  mov     [rbp+50h+var_80], r14
0x180029f53  xorps   xmm1, xmm1
0x180029f56  movdqa  [rbp+50h+var_90], xmm0
0x180029f5b  lea     r9, [rbp+50h+arg_0]
0x180029f5f  movdqa  [rbp+50h+var_70], xmm0
0x180029f64  lea     r8, [rbp+50h+var_90]
0x180029f68  movdqa  [rbp+50h+var_60], xmm1
0x180029f6d  lea     rcx, [rsp+150h+var_120]
0x180029f72  movdqa  xmmword ptr [rbp+50h+var_50], xmm0
0x180029f77  movdqa  [rbp+50h+var_40], xmm1
0x180029f7c  mov     [rbp+50h+var_78], r14
0x180029f80  mov     byte ptr [rbp+50h+arg_0], r14b
0x180029f84  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180029f89  mov     ebx, eax
0x180029f8b  test    eax, eax
0x180029f8d  jns     loc_18002A08A
0x180029f93  mov     edx, 24DBh; void *
0x180029f98  mov     rcx, [rbp+58h]; this
0x180029f9c  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029fa3  mov     r9d, ebx; char *
0x180029fa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029fab  lea     rcx, [rbp+50h+var_90]; this
0x180029faf  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180029fb4  jmp     loc_180029F28
0x180029fb9  mov     r14, qword ptr [rbp+50h+var_50+8]
0x180029fbd  xor     ecx, ecx
0x180029fbf  test    r14, r14
0x180029fc2  jz      loc_18002A067
0x180029fc8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029fcc  inc     rax
0x180029fcf  cmp     [r14+rax*2], cx
0x180029fd4  jnz     short loc_180029FCC
0x180029fd6  add     rax, 4
0x180029fda  lea     rcx, [rbp+50h+lpString1]
0x180029fde  add     rax, rdi
0x180029fe1  xor     edx, edx
0x180029fe3  mov     r8, rax
0x180029fe6  mov     [rbp+50h+var_A0], rax
0x180029fea  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180029fef  mov     rbx, [rbp+50h+lpString1]
0x180029ff3  test    rbx, rbx
0x180029ff6  jz      loc_18002A1C8
0x180029ffc  cmp     word ptr [r13+rdi*2-2], 5Ch ; '\'
0x18002a003  lea     rax, aSS_0; "%s%s"
0x18002a00a  mov     rdx, [rbp+50h+var_A0]; unsigned __int64
0x18002a00e  lea     r8, aSS; "%s\\%s"
0x18002a015  cmovz   r8, rax; unsigned __int16 *
0x18002a019  mov     qword ptr [rsp+150h+bIgnoreCase], r14; int
0x18002a01e  mov     r9, r13
0x18002a021  mov     rcx, rbx; unsigned __int16 *
0x18002a024  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a029  mov     r14d, eax
0x18002a02c  test    eax, eax
0x18002a02e  js      loc_18002A156
0x18002a034  or      r9d, 0FFFFFFFFh; cchCount2
0x18002a038  mov     [rsp+150h+bIgnoreCase], 1; int
0x18002a040  or      edx, r9d; cchCount1
0x18002a043  mov     r8, r15; lpString2
0x18002a046  mov     rcx, rbx; lpString1
0x18002a049  call    cs:__imp_CompareStringOrdinal
0x18002a050  nop     dword ptr [rax+rax+00h]
0x18002a055  lea     rcx, [rbp+50h+lpString1]
0x18002a059  cmp     eax, 2
0x18002a05c  jz      loc_18002A114
0x18002a062  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a067  inc     [rsp+150h+var_118]
0x18002a06b  lea     r9, [rbp+50h+arg_0]
0x18002a06f  lea     r8, [rbp+50h+var_90]
0x18002a073  lea     rcx, [rsp+150h+var_120]
0x18002a078  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18002a07d  xor     r14d, r14d
0x18002a080  mov     ebx, eax
0x18002a082  test    eax, eax
0x18002a084  js      loc_18002A23C
0x18002a08a  cmp     byte ptr [rbp+50h+arg_0], r14b
0x18002a08e  jnz     loc_180029FB9
0x18002a094  mov     rcx, r15; unsigned __int16 *
0x18002a097  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18002a09c  mov     r9, rax
0x18002a09f  xor     edx, edx
0x18002a0a1  lea     rax, aAidoesexecutab; "[AiDoesExecutableExistInPackage]"
0x18002a0a8  mov     r8, r12
0x18002a0ab  mov     [rsp+150h+var_128], rax
0x18002a0b0  lea     rax, String2
0x18002a0b7  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x18002a0bc  lea     ecx, [rdx+8]
0x18002a0bf  call    ?AipLogDesktopAppXProcessStartFailure@@YAXW4DesktopAppXProcessStartFailureCheckpoint@@JPEBG111@Z; AipLogDesktopAppXProcessStartFailure(DesktopAppXProcessStartFailureCheckpoint,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002a0c4  lea     rcx, [rbp+50h+var_90]; this
0x18002a0c8  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002a0cd  mov     rcx, [rsp+150h+var_120]
0x18002a0d2  mov     [rsp+150h+var_120], r14
0x18002a0d7  test    rcx, rcx
0x18002a0da  jz      short loc_18002A0E8
0x18002a0dc  call    cs:__imp_SRCacheContext_Close
0x18002a0e3  nop     dword ptr [rax+rax+00h]
0x18002a0e8  lea     rcx, [rsp+150h+var_100]; this
0x18002a0ed  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002a0f2  mov     rcx, [rbp+50h+arg_10]
0x18002a0f6  mov     [rbp+50h+arg_10], r14
0x18002a0fa  test    rcx, rcx
0x18002a0fd  jz      loc_18002A282
0x18002a103  call    cs:__imp_SRCacheManager_Close
0x18002a10a  nop     dword ptr [rax+rax+00h]
0x18002a10f  jmp     loc_18002A282
0x18002a114  mov     byte ptr [rsi], 1
0x18002a117  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a11c  lea     rcx, [rbp+50h+var_90]; this
0x18002a120  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002a125  mov     rcx, [rsp+150h+var_120]
0x18002a12a  xor     ebx, ebx
0x18002a12c  mov     [rsp+150h+var_120], rbx
0x18002a131  test    rcx, rcx
0x18002a134  jz      short loc_18002A142
0x18002a136  call    cs:__imp_SRCacheContext_Close
0x18002a13d  nop     dword ptr [rax+rax+00h]
0x18002a142  lea     rcx, [rsp+150h+var_100]; this
0x18002a147  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002a14c  mov     rcx, [rbp+50h+arg_10]
0x18002a150  mov     [rbp+50h+arg_10], rbx
0x18002a154  jmp     short loc_18002A0FA
0x18002a156  mov     rcx, [rbp+58h]; this
0x18002a15a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002a161  mov     r9d, r14d; char *
0x18002a164  mov     edx, 24EDh; void *
0x18002a169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a16e  lea     rcx, [rbp+50h+lpString1]
0x18002a172  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a177  lea     rcx, [rbp+50h+var_90]; this
0x18002a17b  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002a180  mov     rcx, [rsp+150h+var_120]
0x18002a185  xor     ebx, ebx
0x18002a187  mov     [rsp+150h+var_120], rbx
0x18002a18c  test    rcx, rcx
0x18002a18f  jz      short loc_18002A19D
0x18002a191  call    cs:__imp_SRCacheContext_Close
0x18002a198  nop     dword ptr [rax+rax+00h]
0x18002a19d  lea     rcx, [rsp+150h+var_100]; this
0x18002a1a2  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002a1a7  mov     rcx, [rbp+50h+arg_10]
0x18002a1ab  mov     [rbp+50h+arg_10], rbx
0x18002a1af  test    rcx, rcx
0x18002a1b2  jz      short loc_18002A1C0
0x18002a1b4  call    cs:__imp_SRCacheManager_Close
0x18002a1bb  nop     dword ptr [rax+rax+00h]
0x18002a1c0  mov     eax, r14d
0x18002a1c3  jmp     loc_18002A284
0x18002a1c8  mov     rcx, [rbp+58h]; this
0x18002a1cc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002a1d3  mov     r9d, 8007000Eh; char *
0x18002a1d9  mov     edx, 24E5h; void *
0x18002a1de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a1e3  lea     rcx, [rbp+50h+lpString1]
0x18002a1e7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a1ec  lea     rcx, [rbp+50h+var_90]; this
0x18002a1f0  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002a1f5  mov     rcx, [rsp+150h+var_120]
0x18002a1fa  xor     ebx, ebx
0x18002a1fc  mov     [rsp+150h+var_120], rbx
0x18002a201  test    rcx, rcx
0x18002a204  jz      short loc_18002A212
0x18002a206  call    cs:__imp_SRCacheContext_Close
0x18002a20d  nop     dword ptr [rax+rax+00h]
0x18002a212  lea     rcx, [rsp+150h+var_100]; this
0x18002a217  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002a21c  mov     rcx, [rbp+50h+arg_10]
0x18002a220  mov     [rbp+50h+arg_10], rbx
0x18002a224  test    rcx, rcx
  ... truncated ...
```
