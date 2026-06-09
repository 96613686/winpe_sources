# AiDoesExecutableExistInPackage(ushort const *,ushort const *,bool *)

- ea: `0x18002b2a4`
- end: `0x18002b820`
- name: `?AiDoesExecutableExistInPackage@@YAJPEBG0PEA_N@Z`
- size: `1404`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b828`

## callees

- `0x180006510`
- `0x180007b30`
- `0x180007c78`
- `0x18000a1f0`
- `0x18000dd68`
- `0x18000de50`
- `0x180010400`
- `0x1800124f4`
- `0x180018280`
- `0x180027e80`
- `0x18002b2a4`
- `0x18002d4d4`
- `0x18002e95c`
- `0x1800353d4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b5c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b5c9`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002b7d4`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002b7d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b319`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b683`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b734`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b7a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b319`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b683`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b734`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b7a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b4bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b65c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b6b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b711`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b786`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b4bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b65c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b6b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b711`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b786`

## string_xrefs

- `0x18002b47c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18002b2f8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002b391`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002b3c4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002b404`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002b494`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002b51c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002b6da`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002b74c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
      (void *)0x239D,
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
    v10 = 9128;
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
    v12 = 9132;
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
      v10 = 9143;
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
      (void *)0x23BD,
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
    v12 = 9154;
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
      (void *)0x23C6,
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
    v20 = 9164;
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
        (void *)0x23DE,
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
      v20 = 9192;
      goto LABEL_30;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23D6,
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
0x18002b2a4  mov     [rsp-8+arg_8], rbx
0x18002b2a9  push    rbp
0x18002b2aa  push    rsi
0x18002b2ab  push    rdi
0x18002b2ac  push    r12
0x18002b2ae  push    r13
0x18002b2b0  push    r14
0x18002b2b2  push    r15
0x18002b2b4  lea     rbp, [rsp-20h]
0x18002b2b9  sub     rsp, 120h
0x18002b2c0  xor     r14d, r14d
0x18002b2c3  mov     rsi, r8
0x18002b2c6  mov     [r8], r14b
0x18002b2c9  mov     r15, rdx
0x18002b2cc  mov     r12, rcx
0x18002b2cf  test    rcx, rcx
0x18002b2d2  jz      loc_18002B7FE
0x18002b2d8  test    rdx, rdx
0x18002b2db  jz      loc_18002B7FE
0x18002b2e1  lea     rcx, [rbp+50h+arg_10]
0x18002b2e5  mov     [rbp+50h+arg_10], r14
0x18002b2e9  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x18002b2ee  mov     ebx, eax
0x18002b2f0  test    eax, eax
0x18002b2f2  jns     short loc_18002B32C
0x18002b2f4  mov     rcx, [rbp+58h]; this
0x18002b2f8  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002b2ff  mov     r9d, eax; char *
0x18002b302  mov     edx, 239Dh; void *
0x18002b307  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b30c  mov     rcx, [rbp+50h+arg_10]
0x18002b310  mov     [rbp+50h+arg_10], r14
0x18002b314  test    rcx, rcx
0x18002b317  jz      short loc_18002B325
0x18002b319  call    cs:__imp_SRCacheManager_Close
0x18002b320  nop     dword ptr [rax+rax+00h]
0x18002b325  mov     eax, ebx
0x18002b327  jmp     loc_18002B804
0x18002b32c  xorps   xmm0, xmm0
0x18002b32f  mov     [rsp+150h+var_F0], r14
0x18002b334  lea     rax, [rbp+50h+arg_0]
0x18002b338  movdqa  xmmword ptr [rsp+150h+var_100], xmm0
0x18002b33e  lea     r9, [rsp+150h+var_100]
0x18002b343  movdqa  [rbp+50h+var_C0], xmm0
0x18002b348  mov     r8d, 130h
0x18002b34e  mov     qword ptr [rsp+150h+bIgnoreCase], rax; int
0x18002b353  mov     rdx, r12
0x18002b356  mov     [rsp+150h+var_E8], r14
0x18002b35b  lea     rcx, [rbp+50h+arg_10]
0x18002b35f  mov     [rsp+150h+var_E0], r14
0x18002b364  mov     [rsp+150h+var_D8], r14
0x18002b369  mov     [rbp+50h+var_D0], r14
0x18002b36d  mov     [rbp+50h+var_C8], r14
0x18002b371  mov     [rbp+50h+var_B0], r14d
0x18002b375  mov     [rbp+50h+var_A8], r14
0x18002b379  mov     byte ptr [rbp+50h+arg_0], r14b
0x18002b37d  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18002b382  mov     ebx, eax
0x18002b384  test    eax, eax
0x18002b386  jns     short loc_18002B3AF
0x18002b388  mov     edx, 23A8h; void *
0x18002b38d  mov     rcx, [rbp+58h]; this
0x18002b391  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002b398  mov     r9d, ebx; char *
0x18002b39b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b3a0  lea     rcx, [rsp+150h+var_100]; this
0x18002b3a5  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002b3aa  jmp     loc_18002B30C
0x18002b3af  cmp     byte ptr [rbp+50h+arg_0], r14b
0x18002b3b3  jnz     short loc_18002B3D4
0x18002b3b5  mov     r9d, 2; char *
0x18002b3bb  mov     edx, 23ACh; void *
0x18002b3c0  mov     rcx, [rbp+58h]; this
0x18002b3c4  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002b3cb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b3d0  mov     ebx, eax
0x18002b3d2  jmp     short loc_18002B3A0
0x18002b3d4  mov     r9d, 3
0x18002b3da  cmp     dword ptr [rsp+150h+var_E0+4], r9d
0x18002b3df  jnz     short loc_18002B3EC
0x18002b3e1  test    byte ptr [rsp+150h+var_E0], 10h
0x18002b3e6  jnz     loc_18002B7C6
0x18002b3ec  test    byte ptr [rsp+150h+var_E0], 20h
0x18002b3f1  jnz     loc_18002B7C6
0x18002b3f7  mov     r13, [rbp+50h+var_C8]
0x18002b3fb  test    r13, r13
0x18002b3fe  jnz     short loc_18002B432
0x18002b400  mov     rcx, [rbp+58h]; this
0x18002b404  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002b40b  mov     r9d, 8007000Eh; char *
0x18002b411  mov     edx, 23BDh; void *
0x18002b416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b41b  lea     rcx, [rsp+150h+var_100]; this
0x18002b420  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002b425  mov     rcx, [rbp+50h+arg_10]
0x18002b429  mov     [rbp+50h+arg_10], r14
0x18002b42d  jmp     loc_18002B7A4
0x18002b432  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002b436  inc     rdi
0x18002b439  cmp     [r13+rdi*2+0], r14w
0x18002b43f  jnz     short loc_18002B436
0x18002b441  test    rdi, rdi
0x18002b444  jnz     short loc_18002B450
0x18002b446  mov     edx, 23C2h
0x18002b44b  jmp     loc_18002B3C0
0x18002b450  mov     r8, [rsp+150h+var_100]; __int64
0x18002b455  lea     rdx, [rbp+50h+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x18002b459  lea     rcx, [rsp+150h+var_120]; this
0x18002b45e  mov     [rsp+150h+var_120], r14
0x18002b463  mov     [rsp+150h+var_118], r14d
0x18002b468  mov     [rsp+150h+var_110], r14
0x18002b46d  call    ?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)
0x18002b472  mov     ebx, eax
0x18002b474  test    eax, eax
0x18002b476  jns     short loc_18002B4CC
0x18002b478  mov     rcx, [rbp+58h]; this
0x18002b47c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002b483  mov     r9d, eax; char *
0x18002b486  mov     edx, 47Bh; void *
0x18002b48b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b490  mov     rcx, [rbp+58h]; this
0x18002b494  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002b49b  mov     r9d, ebx; char *
0x18002b49e  mov     edx, 23C6h; void *
0x18002b4a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b4a8  mov     rcx, [rsp+150h+var_120]
0x18002b4ad  mov     [rsp+150h+var_120], r14
0x18002b4b2  test    rcx, rcx
0x18002b4b5  jz      loc_18002B3A0
0x18002b4bb  call    cs:__imp_SRCacheContext_Close
0x18002b4c2  nop     dword ptr [rax+rax+00h]
0x18002b4c7  jmp     loc_18002B3A0
0x18002b4cc  xorps   xmm0, xmm0
0x18002b4cf  mov     [rbp+50h+var_80], r14
0x18002b4d3  xorps   xmm1, xmm1
0x18002b4d6  movdqa  [rbp+50h+var_90], xmm0
0x18002b4db  lea     r9, [rbp+50h+arg_0]
0x18002b4df  movdqa  [rbp+50h+var_70], xmm0
0x18002b4e4  lea     r8, [rbp+50h+var_90]
0x18002b4e8  movdqa  [rbp+50h+var_60], xmm1
0x18002b4ed  lea     rcx, [rsp+150h+var_120]
0x18002b4f2  movdqa  xmmword ptr [rbp+50h+var_50], xmm0
0x18002b4f7  movdqa  [rbp+50h+var_40], xmm1
0x18002b4fc  mov     [rbp+50h+var_78], r14
0x18002b500  mov     byte ptr [rbp+50h+arg_0], r14b
0x18002b504  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18002b509  mov     ebx, eax
0x18002b50b  test    eax, eax
0x18002b50d  jns     loc_18002B60A
0x18002b513  mov     edx, 23CCh; void *
0x18002b518  mov     rcx, [rbp+58h]; this
0x18002b51c  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002b523  mov     r9d, ebx; char *
0x18002b526  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b52b  lea     rcx, [rbp+50h+var_90]; this
0x18002b52f  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002b534  jmp     loc_18002B4A8
0x18002b539  mov     r14, qword ptr [rbp+50h+var_50+8]
0x18002b53d  xor     ecx, ecx
0x18002b53f  test    r14, r14
0x18002b542  jz      loc_18002B5E7
0x18002b548  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b54c  inc     rax
0x18002b54f  cmp     [r14+rax*2], cx
0x18002b554  jnz     short loc_18002B54C
0x18002b556  add     rax, 4
0x18002b55a  lea     rcx, [rbp+50h+lpString1]
0x18002b55e  add     rax, rdi
0x18002b561  xor     edx, edx
0x18002b563  mov     r8, rax
0x18002b566  mov     [rbp+50h+var_A0], rax
0x18002b56a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002b56f  mov     rbx, [rbp+50h+lpString1]
0x18002b573  test    rbx, rbx
0x18002b576  jz      loc_18002B748
0x18002b57c  cmp     word ptr [r13+rdi*2-2], 5Ch ; '\'
0x18002b583  lea     rax, aSS_0; "%s%s"
0x18002b58a  mov     rdx, [rbp+50h+var_A0]; unsigned __int64
0x18002b58e  lea     r8, aSS; "%s\\%s"
0x18002b595  cmovz   r8, rax; unsigned __int16 *
0x18002b599  mov     qword ptr [rsp+150h+bIgnoreCase], r14; int
0x18002b59e  mov     r9, r13
0x18002b5a1  mov     rcx, rbx; unsigned __int16 *
0x18002b5a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b5a9  mov     r14d, eax
0x18002b5ac  test    eax, eax
0x18002b5ae  js      loc_18002B6D6
0x18002b5b4  or      r9d, 0FFFFFFFFh; cchCount2
0x18002b5b8  mov     [rsp+150h+bIgnoreCase], 1; int
0x18002b5c0  or      edx, r9d; cchCount1
0x18002b5c3  mov     r8, r15; lpString2
0x18002b5c6  mov     rcx, rbx; lpString1
0x18002b5c9  call    cs:__imp_CompareStringOrdinal
0x18002b5d0  nop     dword ptr [rax+rax+00h]
0x18002b5d5  lea     rcx, [rbp+50h+lpString1]
0x18002b5d9  cmp     eax, 2
0x18002b5dc  jz      loc_18002B694
0x18002b5e2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b5e7  inc     [rsp+150h+var_118]
0x18002b5eb  lea     r9, [rbp+50h+arg_0]
0x18002b5ef  lea     r8, [rbp+50h+var_90]
0x18002b5f3  lea     rcx, [rsp+150h+var_120]
0x18002b5f8  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18002b5fd  xor     r14d, r14d
0x18002b600  mov     ebx, eax
0x18002b602  test    eax, eax
0x18002b604  js      loc_18002B7BC
0x18002b60a  cmp     byte ptr [rbp+50h+arg_0], r14b
0x18002b60e  jnz     loc_18002B539
0x18002b614  mov     rcx, r15; unsigned __int16 *
0x18002b617  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18002b61c  mov     r9, rax
0x18002b61f  xor     edx, edx
0x18002b621  lea     rax, aAidoesexecutab; "[AiDoesExecutableExistInPackage]"
0x18002b628  mov     r8, r12
0x18002b62b  mov     [rsp+150h+var_128], rax
0x18002b630  lea     rax, String2
0x18002b637  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x18002b63c  lea     ecx, [rdx+8]
0x18002b63f  call    ?AipLogDesktopAppXProcessStartFailure@@YAXW4DesktopAppXProcessStartFailureCheckpoint@@JPEBG111@Z; AipLogDesktopAppXProcessStartFailure(DesktopAppXProcessStartFailureCheckpoint,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002b644  lea     rcx, [rbp+50h+var_90]; this
0x18002b648  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002b64d  mov     rcx, [rsp+150h+var_120]
0x18002b652  mov     [rsp+150h+var_120], r14
0x18002b657  test    rcx, rcx
0x18002b65a  jz      short loc_18002B668
0x18002b65c  call    cs:__imp_SRCacheContext_Close
0x18002b663  nop     dword ptr [rax+rax+00h]
0x18002b668  lea     rcx, [rsp+150h+var_100]; this
0x18002b66d  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002b672  mov     rcx, [rbp+50h+arg_10]
0x18002b676  mov     [rbp+50h+arg_10], r14
0x18002b67a  test    rcx, rcx
0x18002b67d  jz      loc_18002B802
0x18002b683  call    cs:__imp_SRCacheManager_Close
0x18002b68a  nop     dword ptr [rax+rax+00h]
0x18002b68f  jmp     loc_18002B802
0x18002b694  mov     byte ptr [rsi], 1
0x18002b697  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b69c  lea     rcx, [rbp+50h+var_90]; this
0x18002b6a0  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002b6a5  mov     rcx, [rsp+150h+var_120]
0x18002b6aa  xor     ebx, ebx
0x18002b6ac  mov     [rsp+150h+var_120], rbx
0x18002b6b1  test    rcx, rcx
0x18002b6b4  jz      short loc_18002B6C2
0x18002b6b6  call    cs:__imp_SRCacheContext_Close
0x18002b6bd  nop     dword ptr [rax+rax+00h]
0x18002b6c2  lea     rcx, [rsp+150h+var_100]; this
0x18002b6c7  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002b6cc  mov     rcx, [rbp+50h+arg_10]
0x18002b6d0  mov     [rbp+50h+arg_10], rbx
0x18002b6d4  jmp     short loc_18002B67A
0x18002b6d6  mov     rcx, [rbp+58h]; this
0x18002b6da  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002b6e1  mov     r9d, r14d; char *
0x18002b6e4  mov     edx, 23DEh; void *
0x18002b6e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b6ee  lea     rcx, [rbp+50h+lpString1]
0x18002b6f2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b6f7  lea     rcx, [rbp+50h+var_90]; this
0x18002b6fb  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002b700  mov     rcx, [rsp+150h+var_120]
0x18002b705  xor     ebx, ebx
0x18002b707  mov     [rsp+150h+var_120], rbx
0x18002b70c  test    rcx, rcx
0x18002b70f  jz      short loc_18002B71D
0x18002b711  call    cs:__imp_SRCacheContext_Close
0x18002b718  nop     dword ptr [rax+rax+00h]
0x18002b71d  lea     rcx, [rsp+150h+var_100]; this
0x18002b722  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002b727  mov     rcx, [rbp+50h+arg_10]
0x18002b72b  mov     [rbp+50h+arg_10], rbx
0x18002b72f  test    rcx, rcx
0x18002b732  jz      short loc_18002B740
0x18002b734  call    cs:__imp_SRCacheManager_Close
0x18002b73b  nop     dword ptr [rax+rax+00h]
0x18002b740  mov     eax, r14d
0x18002b743  jmp     loc_18002B804
0x18002b748  mov     rcx, [rbp+58h]; this
0x18002b74c  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002b753  mov     r9d, 8007000Eh; char *
0x18002b759  mov     edx, 23D6h; void *
0x18002b75e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b763  lea     rcx, [rbp+50h+lpString1]
0x18002b767  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b76c  lea     rcx, [rbp+50h+var_90]; this
0x18002b770  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002b775  mov     rcx, [rsp+150h+var_120]
0x18002b77a  xor     ebx, ebx
0x18002b77c  mov     [rsp+150h+var_120], rbx
0x18002b781  test    rcx, rcx
0x18002b784  jz      short loc_18002B792
0x18002b786  call    cs:__imp_SRCacheContext_Close
0x18002b78d  nop     dword ptr [rax+rax+00h]
0x18002b792  lea     rcx, [rsp+150h+var_100]; this
0x18002b797  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002b79c  mov     rcx, [rbp+50h+arg_10]
0x18002b7a0  mov     [rbp+50h+arg_10], rbx
0x18002b7a4  test    rcx, rcx
  ... truncated ...
```
