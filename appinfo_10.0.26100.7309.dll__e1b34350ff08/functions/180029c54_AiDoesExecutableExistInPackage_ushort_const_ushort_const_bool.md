# AiDoesExecutableExistInPackage(ushort const *,ushort const *,bool *)

- ea: `0x180029c54`
- end: `0x18002a1d0`
- name: `?AiDoesExecutableExistInPackage@@YAJPEBG0PEA_N@Z`
- size: `1404`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a1d8`

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
- `0x180026840`
- `0x180029c54`
- `0x18002beb4`
- `0x18002d33c`
- `0x180035484`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029f79`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029f79`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002a184`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002a184`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180029cc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a033`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a0e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a159`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180029cc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a033`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a0e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002a159`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180029e6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a00c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a066`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a0c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a136`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180029e6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a00c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a066`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a0c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002a136`

## string_xrefs

- `0x180029e2c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180029ca8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029d41`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029d74`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029db4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029e44`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029ecc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a08a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a0fc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall AiDoesExecutableExistInPackage(const unsigned __int16 *a1, const unsigned __int16 *a2, bool *a3)
{
  int v6; // eax
  int IsTrustedAndInPackage; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r13
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rdi
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // r14
  __int64 v26; // rax
  const WCHAR *v27; // rbx
  const unsigned __int16 *v28; // r8
  int v29; // eax
  unsigned int v30; // r14d
  const unsigned __int16 *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  int v45; // [rsp+38h] [rbp-C8h]
  __int64 v46; // [rsp+40h] [rbp-C0h]
  __int64 v47[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h]
  __int64 v51; // [rsp+78h] [rbp-88h]
  __int64 v52; // [rsp+80h] [rbp-80h]
  __int64 v53; // [rsp+88h] [rbp-78h]
  __int128 v54; // [rsp+90h] [rbp-70h]
  int v55; // [rsp+A0h] [rbp-60h]
  __int64 v56; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v57; // [rsp+B0h] [rbp-50h]
  __int128 v58; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v59; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+D8h] [rbp-28h]
  __int128 v61; // [rsp+E0h] [rbp-20h]
  __int128 v62; // [rsp+F0h] [rbp-10h]
  int v63[4]; // [rsp+100h] [rbp+0h]
  __int128 v64; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  unsigned int v66; // [rsp+160h] [rbp+60h] BYREF
  __int64 v67; // [rsp+170h] [rbp+70h] BYREF
  LPCWCH lpString1; // [rsp+178h] [rbp+78h] BYREF

  *a3 = 0;
  if ( !a1 || !a2 )
  {
    *a3 = 1;
    return 0;
  }
  v67 = 0;
  v6 = StateRepository::Cache::Manager_NoThrow::Open(&v67);
  IsTrustedAndInPackage = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2475,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
LABEL_5:
    v10 = v67;
    v67 = 0;
    if ( v10 )
      SRCacheManager_Close(v10, v8, v9);
    return (unsigned int)IsTrustedAndInPackage;
  }
  v48 = 0;
  *(_OWORD *)v47 = 0;
  v54 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v55 = 0;
  v56 = 0;
  LOBYTE(v66) = 0;
  IsTrustedAndInPackage = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
                            (struct StateRepository::Cache::Manager_NoThrow *)&v67,
                            a1,
                            304,
                            (__int64)v47,
                            (bool *)&v66);
  if ( IsTrustedAndInPackage < 0 )
  {
    v12 = 9344;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCasea);
LABEL_11:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v47);
    goto LABEL_5;
  }
  if ( !(_BYTE)v66 )
  {
    v13 = 2;
    v14 = 9348;
LABEL_14:
    IsTrustedAndInPackage = wil::details::in1diag3::Return_Win32(
                              retaddr,
                              (void *)v14,
                              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                              (const char *)v13,
                              bIgnoreCasea);
    goto LABEL_11;
  }
  v13 = 3;
  if ( HIDWORD(v50) == 3 && (v50 & 0x10) != 0 || (v50 & 0x20) != 0 )
  {
    v66 = 0;
    IsTrustedAndInPackage = VerifyFileIsTrustedAndInPackage(a2, a1, &v66);
    if ( IsTrustedAndInPackage < 0 )
    {
      v12 = 9359;
      goto LABEL_10;
    }
    *a3 = v66 != 0;
LABEL_44:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v47);
    v35 = v67;
    v67 = 0;
    if ( v35 )
      SRCacheManager_Close(v35, v33, v34);
    return 0;
  }
  v15 = v53;
  if ( !v53 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2495,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x8007000ELL,
      bIgnoreCasea);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v47);
    v18 = v67;
    v67 = 0;
    goto LABEL_57;
  }
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)(v53 + 2 * v19) );
  if ( !v19 )
  {
    v14 = 9370;
    goto LABEL_14;
  }
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v20 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
          (StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *)&v44,
          (struct StateRepository::Cache::Manager_NoThrow *)&v67,
          v47[0]);
  IsTrustedAndInPackage = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v20,
      bIgnoreCasea);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249E,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCasec);
LABEL_26:
    v22 = v44;
    v44 = 0;
    if ( v22 )
      SRCacheContext_Close(v22);
    goto LABEL_11;
  }
  v59 = 0;
  v58 = 0;
  v61 = 0;
  v62 = 0;
  *(_OWORD *)v63 = 0;
  v64 = 0;
  v60 = 0;
  LOBYTE(v66) = 0;
  IsTrustedAndInPackage = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v44, v21, &v58, &v66);
  if ( IsTrustedAndInPackage < 0 )
  {
    v24 = 9380;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)IsTrustedAndInPackage,
      bIgnoreCasea);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v58);
    goto LABEL_26;
  }
  while ( 1 )
  {
    if ( !(_BYTE)v66 )
    {
      v31 = AipJustFileName(a2);
      AipLogDesktopAppXProcessStartFailure(8, 0, a1, v31);
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v58);
      v32 = v44;
      v44 = 0;
      if ( v32 )
        SRCacheContext_Close(v32);
      goto LABEL_44;
    }
    v25 = *(_QWORD *)&v63[2];
    if ( !*(_QWORD *)&v63[2] )
      goto LABEL_40;
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(*(_QWORD *)&v63[2] + 2 * v26) );
    v57 = v19 + v26 + 4;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpString1,
      0,
      v57);
    v27 = lpString1;
    if ( !lpString1 )
      break;
    v28 = L"%s\\%s";
    if ( *(_WORD *)(v15 + 2 * v19 - 2) == 92 )
      v28 = L"%s%s";
    v29 = StringCchPrintfW((unsigned __int16 *)lpString1, v57, v28, v15, v25);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24B6,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v29,
        bIgnoreCaseb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v58);
      v37 = v44;
      v44 = 0;
      if ( v37 )
        SRCacheContext_Close(v37);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v47);
      v38 = v67;
      v67 = 0;
      if ( v38 )
        ((void (*)(void))SRCacheManager_Close)();
      return v30;
    }
    if ( CompareStringOrdinal(v27, -1, a2, -1, 1) == 2 )
    {
      *a3 = 1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v58);
      v36 = v44;
      v44 = 0;
      if ( v36 )
        SRCacheContext_Close(v36);
      goto LABEL_44;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
LABEL_40:
    ++v45;
    IsTrustedAndInPackage = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v44, v23, &v58, &v66);
    if ( IsTrustedAndInPackage < 0 )
    {
      v24 = 9408;
      goto LABEL_30;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x24AE,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
    (const char *)0x8007000ELL,
    bIgnoreCasea);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v58);
  v39 = v44;
  v44 = 0;
  if ( v39 )
    SRCacheContext_Close(v39);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v47);
  v18 = v67;
  v67 = 0;
LABEL_57:
  if ( v18 )
    SRCacheManager_Close(v18, v16, v17);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180029c54  mov     [rsp-8+arg_8], rbx
0x180029c59  push    rbp
0x180029c5a  push    rsi
0x180029c5b  push    rdi
0x180029c5c  push    r12
0x180029c5e  push    r13
0x180029c60  push    r14
0x180029c62  push    r15
0x180029c64  lea     rbp, [rsp-20h]
0x180029c69  sub     rsp, 120h
0x180029c70  xor     r14d, r14d
0x180029c73  mov     rsi, r8
0x180029c76  mov     [r8], r14b
0x180029c79  mov     r15, rdx
0x180029c7c  mov     r12, rcx
0x180029c7f  test    rcx, rcx
0x180029c82  jz      loc_18002A1AE
0x180029c88  test    rdx, rdx
0x180029c8b  jz      loc_18002A1AE
0x180029c91  lea     rcx, [rbp+50h+arg_10]
0x180029c95  mov     [rbp+50h+arg_10], r14
0x180029c99  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x180029c9e  mov     ebx, eax
0x180029ca0  test    eax, eax
0x180029ca2  jns     short loc_180029CDC
0x180029ca4  mov     rcx, [rbp+58h]; this
0x180029ca8  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029caf  mov     r9d, eax; char *
0x180029cb2  mov     edx, 2475h; void *
0x180029cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029cbc  mov     rcx, [rbp+50h+arg_10]
0x180029cc0  mov     [rbp+50h+arg_10], r14
0x180029cc4  test    rcx, rcx
0x180029cc7  jz      short loc_180029CD5
0x180029cc9  call    cs:__imp_SRCacheManager_Close
0x180029cd0  nop     dword ptr [rax+rax+00h]
0x180029cd5  mov     eax, ebx
0x180029cd7  jmp     loc_18002A1B4
0x180029cdc  xorps   xmm0, xmm0
0x180029cdf  mov     [rsp+150h+var_F0], r14
0x180029ce4  lea     rax, [rbp+50h+arg_0]
0x180029ce8  movdqa  xmmword ptr [rsp+150h+var_100], xmm0
0x180029cee  lea     r9, [rsp+150h+var_100]
0x180029cf3  movdqa  [rbp+50h+var_C0], xmm0
0x180029cf8  mov     r8d, 130h
0x180029cfe  mov     qword ptr [rsp+150h+bIgnoreCase], rax; int
0x180029d03  mov     rdx, r12
0x180029d06  mov     [rsp+150h+var_E8], r14
0x180029d0b  lea     rcx, [rbp+50h+arg_10]
0x180029d0f  mov     [rsp+150h+var_E0], r14
0x180029d14  mov     [rsp+150h+var_D8], r14
0x180029d19  mov     [rbp+50h+var_D0], r14
0x180029d1d  mov     [rbp+50h+var_C8], r14
0x180029d21  mov     [rbp+50h+var_B0], r14d
0x180029d25  mov     [rbp+50h+var_A8], r14
0x180029d29  mov     byte ptr [rbp+50h+arg_0], r14b
0x180029d2d  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180029d32  mov     ebx, eax
0x180029d34  test    eax, eax
0x180029d36  jns     short loc_180029D5F
0x180029d38  mov     edx, 2480h; void *
0x180029d3d  mov     rcx, [rbp+58h]; this
0x180029d41  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029d48  mov     r9d, ebx; char *
0x180029d4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d50  lea     rcx, [rsp+150h+var_100]; this
0x180029d55  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180029d5a  jmp     loc_180029CBC
0x180029d5f  cmp     byte ptr [rbp+50h+arg_0], r14b
0x180029d63  jnz     short loc_180029D84
0x180029d65  mov     r9d, 2; char *
0x180029d6b  mov     edx, 2484h; void *
0x180029d70  mov     rcx, [rbp+58h]; this
0x180029d74  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029d7b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180029d80  mov     ebx, eax
0x180029d82  jmp     short loc_180029D50
0x180029d84  mov     r9d, 3
0x180029d8a  cmp     dword ptr [rsp+150h+var_E0+4], r9d
0x180029d8f  jnz     short loc_180029D9C
0x180029d91  test    byte ptr [rsp+150h+var_E0], 10h
0x180029d96  jnz     loc_18002A176
0x180029d9c  test    byte ptr [rsp+150h+var_E0], 20h
0x180029da1  jnz     loc_18002A176
0x180029da7  mov     r13, [rbp+50h+var_C8]
0x180029dab  test    r13, r13
0x180029dae  jnz     short loc_180029DE2
0x180029db0  mov     rcx, [rbp+58h]; this
0x180029db4  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029dbb  mov     r9d, 8007000Eh; char *
0x180029dc1  mov     edx, 2495h; void *
0x180029dc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029dcb  lea     rcx, [rsp+150h+var_100]; this
0x180029dd0  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180029dd5  mov     rcx, [rbp+50h+arg_10]
0x180029dd9  mov     [rbp+50h+arg_10], r14
0x180029ddd  jmp     loc_18002A154
0x180029de2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029de6  inc     rdi
0x180029de9  cmp     [r13+rdi*2+0], r14w
0x180029def  jnz     short loc_180029DE6
0x180029df1  test    rdi, rdi
0x180029df4  jnz     short loc_180029E00
0x180029df6  mov     edx, 249Ah
0x180029dfb  jmp     loc_180029D70
0x180029e00  mov     r8, [rsp+150h+var_100]; __int64
0x180029e05  lea     rdx, [rbp+50h+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x180029e09  lea     rcx, [rsp+150h+var_120]; this
0x180029e0e  mov     [rsp+150h+var_120], r14
0x180029e13  mov     [rsp+150h+var_118], r14d
0x180029e18  mov     [rsp+150h+var_110], r14
0x180029e1d  call    ?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)
0x180029e22  mov     ebx, eax
0x180029e24  test    eax, eax
0x180029e26  jns     short loc_180029E7C
0x180029e28  mov     rcx, [rbp+58h]; this
0x180029e2c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180029e33  mov     r9d, eax; char *
0x180029e36  mov     edx, 47Bh; void *
0x180029e3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e40  mov     rcx, [rbp+58h]; this
0x180029e44  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029e4b  mov     r9d, ebx; char *
0x180029e4e  mov     edx, 249Eh; void *
0x180029e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e58  mov     rcx, [rsp+150h+var_120]
0x180029e5d  mov     [rsp+150h+var_120], r14
0x180029e62  test    rcx, rcx
0x180029e65  jz      loc_180029D50
0x180029e6b  call    cs:__imp_SRCacheContext_Close
0x180029e72  nop     dword ptr [rax+rax+00h]
0x180029e77  jmp     loc_180029D50
0x180029e7c  xorps   xmm0, xmm0
0x180029e7f  mov     [rbp+50h+var_80], r14
0x180029e83  xorps   xmm1, xmm1
0x180029e86  movdqa  [rbp+50h+var_90], xmm0
0x180029e8b  lea     r9, [rbp+50h+arg_0]
0x180029e8f  movdqa  [rbp+50h+var_70], xmm0
0x180029e94  lea     r8, [rbp+50h+var_90]
0x180029e98  movdqa  [rbp+50h+var_60], xmm1
0x180029e9d  lea     rcx, [rsp+150h+var_120]
0x180029ea2  movdqa  xmmword ptr [rbp+50h+var_50], xmm0
0x180029ea7  movdqa  [rbp+50h+var_40], xmm1
0x180029eac  mov     [rbp+50h+var_78], r14
0x180029eb0  mov     byte ptr [rbp+50h+arg_0], r14b
0x180029eb4  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180029eb9  mov     ebx, eax
0x180029ebb  test    eax, eax
0x180029ebd  jns     loc_180029FBA
0x180029ec3  mov     edx, 24A4h; void *
0x180029ec8  mov     rcx, [rbp+58h]; this
0x180029ecc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180029ed3  mov     r9d, ebx; char *
0x180029ed6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029edb  lea     rcx, [rbp+50h+var_90]; this
0x180029edf  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180029ee4  jmp     loc_180029E58
0x180029ee9  mov     r14, qword ptr [rbp+50h+var_50+8]
0x180029eed  xor     ecx, ecx
0x180029eef  test    r14, r14
0x180029ef2  jz      loc_180029F97
0x180029ef8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029efc  inc     rax
0x180029eff  cmp     [r14+rax*2], cx
0x180029f04  jnz     short loc_180029EFC
0x180029f06  add     rax, 4
0x180029f0a  lea     rcx, [rbp+50h+lpString1]
0x180029f0e  add     rax, rdi
0x180029f11  xor     edx, edx
0x180029f13  mov     r8, rax
0x180029f16  mov     [rbp+50h+var_A0], rax
0x180029f1a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180029f1f  mov     rbx, [rbp+50h+lpString1]
0x180029f23  test    rbx, rbx
0x180029f26  jz      loc_18002A0F8
0x180029f2c  cmp     word ptr [r13+rdi*2-2], 5Ch ; '\'
0x180029f33  lea     rax, aSS_0; "%s%s"
0x180029f3a  mov     rdx, [rbp+50h+var_A0]; unsigned __int64
0x180029f3e  lea     r8, aSS; "%s\\%s"
0x180029f45  cmovz   r8, rax; unsigned __int16 *
0x180029f49  mov     qword ptr [rsp+150h+bIgnoreCase], r14; int
0x180029f4e  mov     r9, r13
0x180029f51  mov     rcx, rbx; unsigned __int16 *
0x180029f54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029f59  mov     r14d, eax
0x180029f5c  test    eax, eax
0x180029f5e  js      loc_18002A086
0x180029f64  or      r9d, 0FFFFFFFFh; cchCount2
0x180029f68  mov     [rsp+150h+bIgnoreCase], 1; int
0x180029f70  or      edx, r9d; cchCount1
0x180029f73  mov     r8, r15; lpString2
0x180029f76  mov     rcx, rbx; lpString1
0x180029f79  call    cs:__imp_CompareStringOrdinal
0x180029f80  nop     dword ptr [rax+rax+00h]
0x180029f85  lea     rcx, [rbp+50h+lpString1]
0x180029f89  cmp     eax, 2
0x180029f8c  jz      loc_18002A044
0x180029f92  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029f97  inc     [rsp+150h+var_118]
0x180029f9b  lea     r9, [rbp+50h+arg_0]
0x180029f9f  lea     r8, [rbp+50h+var_90]
0x180029fa3  lea     rcx, [rsp+150h+var_120]
0x180029fa8  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180029fad  xor     r14d, r14d
0x180029fb0  mov     ebx, eax
0x180029fb2  test    eax, eax
0x180029fb4  js      loc_18002A16C
0x180029fba  cmp     byte ptr [rbp+50h+arg_0], r14b
0x180029fbe  jnz     loc_180029EE9
0x180029fc4  mov     rcx, r15; unsigned __int16 *
0x180029fc7  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x180029fcc  mov     r9, rax
0x180029fcf  xor     edx, edx
0x180029fd1  lea     rax, aAidoesexecutab; "[AiDoesExecutableExistInPackage]"
0x180029fd8  mov     r8, r12
0x180029fdb  mov     [rsp+150h+var_128], rax
0x180029fe0  lea     rax, String2
0x180029fe7  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x180029fec  lea     ecx, [rdx+8]
0x180029fef  call    ?AipLogDesktopAppXProcessStartFailure@@YAXW4DesktopAppXProcessStartFailureCheckpoint@@JPEBG111@Z; AipLogDesktopAppXProcessStartFailure(DesktopAppXProcessStartFailureCheckpoint,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x180029ff4  lea     rcx, [rbp+50h+var_90]; this
0x180029ff8  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180029ffd  mov     rcx, [rsp+150h+var_120]
0x18002a002  mov     [rsp+150h+var_120], r14
0x18002a007  test    rcx, rcx
0x18002a00a  jz      short loc_18002A018
0x18002a00c  call    cs:__imp_SRCacheContext_Close
0x18002a013  nop     dword ptr [rax+rax+00h]
0x18002a018  lea     rcx, [rsp+150h+var_100]; this
0x18002a01d  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002a022  mov     rcx, [rbp+50h+arg_10]
0x18002a026  mov     [rbp+50h+arg_10], r14
0x18002a02a  test    rcx, rcx
0x18002a02d  jz      loc_18002A1B2
0x18002a033  call    cs:__imp_SRCacheManager_Close
0x18002a03a  nop     dword ptr [rax+rax+00h]
0x18002a03f  jmp     loc_18002A1B2
0x18002a044  mov     byte ptr [rsi], 1
0x18002a047  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a04c  lea     rcx, [rbp+50h+var_90]; this
0x18002a050  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002a055  mov     rcx, [rsp+150h+var_120]
0x18002a05a  xor     ebx, ebx
0x18002a05c  mov     [rsp+150h+var_120], rbx
0x18002a061  test    rcx, rcx
0x18002a064  jz      short loc_18002A072
0x18002a066  call    cs:__imp_SRCacheContext_Close
0x18002a06d  nop     dword ptr [rax+rax+00h]
0x18002a072  lea     rcx, [rsp+150h+var_100]; this
0x18002a077  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002a07c  mov     rcx, [rbp+50h+arg_10]
0x18002a080  mov     [rbp+50h+arg_10], rbx
0x18002a084  jmp     short loc_18002A02A
0x18002a086  mov     rcx, [rbp+58h]; this
0x18002a08a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002a091  mov     r9d, r14d; char *
0x18002a094  mov     edx, 24B6h; void *
0x18002a099  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a09e  lea     rcx, [rbp+50h+lpString1]
0x18002a0a2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a0a7  lea     rcx, [rbp+50h+var_90]; this
0x18002a0ab  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18002a0b0  mov     rcx, [rsp+150h+var_120]
0x18002a0b5  xor     ebx, ebx
0x18002a0b7  mov     [rsp+150h+var_120], rbx
0x18002a0bc  test    rcx, rcx
0x18002a0bf  jz      short loc_18002A0CD
0x18002a0c1  call    cs:__imp_SRCacheContext_Close
0x18002a0c8  nop     dword ptr [rax+rax+00h]
0x18002a0cd  lea     rcx, [rsp+150h+var_100]; this
0x18002a0d2  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002a0d7  mov     rcx, [rbp+50h+arg_10]
0x18002a0db  mov     [rbp+50h+arg_10], rbx
0x18002a0df  test    rcx, rcx
0x18002a0e2  jz      short loc_18002A0F0
0x18002a0e4  call    cs:__imp_SRCacheManager_Close
0x18002a0eb  nop     dword ptr [rax+rax+00h]
0x18002a0f0  mov     eax, r14d
0x18002a0f3  jmp     loc_18002A1B4
0x18002a0f8  mov     rcx, [rbp+58h]; this
0x18002a0fc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002a103  mov     r9d, 8007000Eh; char *
0x18002a109  mov     edx, 24AEh; void *
0x18002a10e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a113  lea     rcx, [rbp+50h+lpString1]
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
0x18002a154  test    rcx, rcx
  ... truncated ...
```
