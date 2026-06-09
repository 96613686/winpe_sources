# DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext(DeclaredConfigurationScopeData *,ushort const *,bool)

- ea: `0x1800ac47c`
- end: `0x1800ac95c`
- name: `?DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext@@YAJPEAUDeclaredConfigurationScopeData@@PEBG_N@Z`
- size: `1248`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800ac970`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x180019d38`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18001d37c`
- `0x180060854`
- `0x180060dec`
- `0x1800725e0`
- `0x180076c10`
- `0x1800aab60`
- `0x1800ac47c`
- `0x1800f5c8c`
- `0x1800f9cb4`
- `0x1800f9d70`
- `0x180100ad8`

## string_xrefs

- `0x1800ac525`: `DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey`
- `0x1800ac695`: `DeclaredConfigurationStore_GetPersistedDocument`
- `0x1800ac895`: `DeclaredConfigurationExtension_DeleteConfigurationsGivenCurrentDoc`
- `0x1800ac729`: `DeclaredConfigurationStore_GetRefreshFlag`
- `0x1800ac807`: `DeclaredConfigurationExtension_GetSettingsGivenInventoryDoc`
- `0x1800ac5a8`: `DCCDNUtil_GetRegistryString:Get MostRecentVersion`
- `0x1800ac52c`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac55f`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac5af`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac5e2`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac69c`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac6d9`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac730`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac76a`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac7bf`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac80e`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac84b`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac89c`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac8d9`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac919`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext(
        struct DeclaredConfigurationScopeData *a1,
        const unsigned __int16 *a2)
{
  CDeclaredConfigurationLogger *Logger; // rax
  int RefreshFlag; // ebx
  CDeclaredConfigurationLogger *v6; // rax
  CDeclaredConfigurationLogger *v7; // rax
  CDeclaredConfigurationLogger *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // r8
  _WORD *v11; // rdx
  __int64 v12; // r8
  CDeclaredConfigurationLogger *v13; // rax
  CDeclaredConfigurationLogger *v14; // rax
  CDeclaredConfigurationLogger *v15; // rax
  CDeclaredConfigurationLogger *v16; // rax
  CDeclaredConfigurationLogger *v17; // rax
  CDeclaredConfigurationLogger *v18; // rax
  CDeclaredConfigurationLogger *v19; // rax
  CDeclaredConfigurationLogger *v20; // rax
  CDeclaredConfigurationLogger *v21; // rax
  CDeclaredConfigurationLogger *v22; // rax
  int EnrollmentIdSidStateDocIdKey; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v26; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v27; // [rsp+48h] [rbp-B8h] BYREF
  HKEY *v28; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v29; // [rsp+58h] [rbp-A8h] BYREF
  char v30; // [rsp+60h] [rbp-A0h]
  void **p_Block; // [rsp+68h] [rbp-98h]
  int *v32; // [rsp+70h] [rbp-90h]
  char v33; // [rsp+78h] [rbp-88h]
  char *v34[8]; // [rsp+80h] [rbp-80h] BYREF
  char *v35; // [rsp+C0h] [rbp-40h] BYREF
  char *v36; // [rsp+E0h] [rbp-20h] BYREF
  int v37; // [rsp+190h] [rbp+90h]

  EnrollmentIdSidStateDocIdKey = 0;
  Block = 0;
  v27 = 0;
  p_Block = &Block;
  v32 = &EnrollmentIdSidStateDocIdKey;
  v33 = 1;
  v28 = &v27;
  v29 = 0;
  v30 = 1;
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(a1, a2, &v29, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v28);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      Logger,
      L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
      L"DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey",
      &word_180142E98,
      EnrollmentIdSidStateDocIdKey);
    RefreshFlag = EnrollmentIdSidStateDocIdKey;
    operator delete(Block);
    Block = 0;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v6 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v6,
        L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
        EnrollmentIdSidStateDocIdKey);
    }
    goto LABEL_41;
  }
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v27, 0, L"MostRecentVersion", (unsigned __int16 **)&Block);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    v7 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v7,
      L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
      L"DCCDNUtil_GetRegistryString:Get MostRecentVersion",
      &word_180142E98,
      EnrollmentIdSidStateDocIdKey);
    RefreshFlag = EnrollmentIdSidStateDocIdKey;
    operator delete(Block);
    Block = 0;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v8 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v8,
        L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
        EnrollmentIdSidStateDocIdKey);
    }
    goto LABEL_41;
  }
  DCDocument::DCDocument((DCDocument *)v34);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  std::wstring::_Assign<unsigned short>(v34, a2, (char *)v10);
  v11 = (_WORD *)*((_QWORD *)a1 + 1);
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  std::wstring::_Assign<unsigned short>(&v35, v11, (char *)v12);
  do
    ++v9;
  while ( *((_WORD *)Block + v9) );
  std::wstring::_Assign<unsigned short>(&v36, Block, (char *)v9);
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetPersistedDocument(
                                   a1,
                                   v27,
                                   (__int64)Block,
                                   0,
                                   (__int64)v34,
                                   2);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    v13 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v13,
      L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
      L"DeclaredConfigurationStore_GetPersistedDocument",
      &word_180142E98,
      EnrollmentIdSidStateDocIdKey);
    RefreshFlag = EnrollmentIdSidStateDocIdKey;
    DCDocument::~DCDocument((DCDocument *)v34);
    operator delete(Block);
    Block = 0;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v14 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v14,
        L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
        EnrollmentIdSidStateDocIdKey);
    }
    goto LABEL_41;
  }
  v26 = 0;
  RefreshFlag = DeclaredConfigurationStore_GetRefreshFlag(*(OLECHAR **)a1, a2, &v26);
  if ( (int)(RefreshFlag + 0x80000000) >= 0 && RefreshFlag != -2147024894 )
  {
    v15 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v15,
      L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
      L"DeclaredConfigurationStore_GetRefreshFlag",
      &word_180142E98,
      RefreshFlag);
    DCDocument::~DCDocument((DCDocument *)v34);
    operator delete(Block);
    Block = 0;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v16 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v16,
        L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
        EnrollmentIdSidStateDocIdKey);
    }
    goto LABEL_41;
  }
  if ( v37 != 2 )
  {
    if ( v37 != 4 )
    {
      DCDocument::~DCDocument((DCDocument *)v34);
      operator delete(Block);
      Block = 0;
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v17 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v17,
          L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
          EnrollmentIdSidStateDocIdKey);
      }
      RefreshFlag = -2147418113;
      goto LABEL_41;
    }
    RefreshFlag = DeclaredConfigurationExtension_GetSettingsGivenInventoryDoc(a1, (struct DCDocument *)v34);
    EnrollmentIdSidStateDocIdKey = RefreshFlag;
    if ( RefreshFlag < 0 )
    {
      v18 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v18,
        L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
        L"DeclaredConfigurationExtension_GetSettingsGivenInventoryDoc",
        &word_180142E98,
        EnrollmentIdSidStateDocIdKey);
      RefreshFlag = EnrollmentIdSidStateDocIdKey;
      DCDocument::~DCDocument((DCDocument *)v34);
      operator delete(Block);
      Block = 0;
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v19 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v19,
          L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
          EnrollmentIdSidStateDocIdKey);
      }
      goto LABEL_41;
    }
    goto LABEL_39;
  }
  if ( v26 )
  {
    RefreshFlag = EnrollmentIdSidStateDocIdKey;
LABEL_39:
    DCDocument::~DCDocument((DCDocument *)v34);
    operator delete(Block);
    Block = 0;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v22 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v22,
        L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
        EnrollmentIdSidStateDocIdKey);
    }
    goto LABEL_41;
  }
  RefreshFlag = DeclaredConfigurationExtension_DeleteConfigurationsGivenCurrentDoc(a1, (struct DCDocument *)v34);
  EnrollmentIdSidStateDocIdKey = RefreshFlag;
  if ( RefreshFlag >= 0 )
    goto LABEL_39;
  v20 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
    v20,
    L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
    L"DeclaredConfigurationExtension_DeleteConfigurationsGivenCurrentDoc",
    &word_180142E98,
    EnrollmentIdSidStateDocIdKey);
  RefreshFlag = EnrollmentIdSidStateDocIdKey;
  DCDocument::~DCDocument((DCDocument *)v34);
  operator delete(Block);
  Block = 0;
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    v21 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v21,
      L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
      EnrollmentIdSidStateDocIdKey);
  }
LABEL_41:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
  return (unsigned int)RefreshFlag;
}

```

## disassembly

```asm
0x1800ac47c  mov     [rsp-8+arg_10], rbx
0x1800ac481  mov     [rsp-8+arg_18], rsi
0x1800ac486  push    rbp
0x1800ac487  push    rdi
0x1800ac488  push    r14
0x1800ac48a  lea     rbp, [rsp-280h]
0x1800ac492  sub     rsp, 380h
0x1800ac499  mov     rax, cs:__security_cookie
0x1800ac4a0  xor     rax, rsp
0x1800ac4a3  mov     [rbp+290h+var_20], rax
0x1800ac4aa  mov     rsi, rdx
0x1800ac4ad  mov     rdi, rcx
0x1800ac4b0  xor     r14d, r14d
0x1800ac4b3  mov     [rsp+390h+var_360], r14d
0x1800ac4b8  mov     [rsp+390h+Block], r14
0x1800ac4bd  mov     [rsp+390h+var_348], r14
0x1800ac4c2  lea     rax, [rsp+390h+Block]
0x1800ac4c7  mov     [rsp+390h+var_328], rax
0x1800ac4cc  lea     rax, [rsp+390h+var_360]
0x1800ac4d1  mov     [rsp+390h+var_320], rax
0x1800ac4d6  mov     [rsp+390h+var_318], 1
0x1800ac4db  lea     rax, [rsp+390h+var_348]
0x1800ac4e0  mov     [rsp+390h+var_340], rax
0x1800ac4e5  mov     [rsp+390h+var_338], r14
0x1800ac4ea  mov     [rsp+390h+var_330], 1
0x1800ac4ef  xor     r9d, r9d; int
0x1800ac4f2  lea     r8, [rsp+390h+var_338]; HKEY *
0x1800ac4f7  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x1800ac4fc  mov     [rsp+390h+var_360], eax
0x1800ac500  lea     rcx, [rsp+390h+var_340]
0x1800ac505  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800ac50a  cmp     [rsp+390h+var_360], r14d
0x1800ac50f  jge     short loc_1800AC574
0x1800ac511  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac516  mov     ecx, [rsp+390h+var_360]
0x1800ac51a  mov     [rsp+390h+var_370], ecx; int
0x1800ac51e  lea     r9, word_180142E98; unsigned __int16 *
0x1800ac525  lea     r8, aDeclaredconfig_208; "DeclaredConfigurationStore_GetEnrollmen"...
0x1800ac52c  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac533  mov     rcx, rax; this
0x1800ac536  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800ac53b  mov     ebx, [rsp+390h+var_360]
0x1800ac53f  mov     rcx, [rsp+390h+Block]; Block
0x1800ac544  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac549  mov     [rsp+390h+Block], r14
0x1800ac54e  cmp     [rsp+390h+var_360], r14d
0x1800ac553  jge     short loc_1800AC56F
0x1800ac555  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac55a  mov     r8d, [rsp+390h+var_360]; int
0x1800ac55f  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac566  mov     rcx, rax; this
0x1800ac569  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800ac56e  nop
0x1800ac56f  jmp     loc_1800AC929
0x1800ac574  lea     r9, [rsp+390h+Block]; unsigned __int16 **
0x1800ac579  lea     r8, aMostrecentvers; "MostRecentVersion"
0x1800ac580  xor     edx, edx; unsigned __int16 *
0x1800ac582  mov     rcx, [rsp+390h+var_348]; HKEY
0x1800ac587  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800ac58c  mov     [rsp+390h+var_360], eax
0x1800ac590  test    eax, eax
0x1800ac592  jns     short loc_1800AC5F7
0x1800ac594  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac599  mov     ecx, [rsp+390h+var_360]
0x1800ac59d  mov     [rsp+390h+var_370], ecx; int
0x1800ac5a1  lea     r9, word_180142E98; unsigned __int16 *
0x1800ac5a8  lea     r8, aDccdnutilGetre_4; "DCCDNUtil_GetRegistryString:Get MostRec"...
0x1800ac5af  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac5b6  mov     rcx, rax; this
0x1800ac5b9  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800ac5be  mov     ebx, [rsp+390h+var_360]
0x1800ac5c2  mov     rcx, [rsp+390h+Block]; Block
0x1800ac5c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac5cc  mov     [rsp+390h+Block], r14
0x1800ac5d1  cmp     [rsp+390h+var_360], r14d
0x1800ac5d6  jge     short loc_1800AC5F2
0x1800ac5d8  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac5dd  mov     r8d, [rsp+390h+var_360]; int
0x1800ac5e2  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac5e9  mov     rcx, rax; this
0x1800ac5ec  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800ac5f1  nop
0x1800ac5f2  jmp     loc_1800AC929
0x1800ac5f7  lea     rcx, [rbp+290h+var_310]; this
0x1800ac5fb  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x1800ac600  nop
0x1800ac601  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ac605  mov     r8, rbx
0x1800ac608  inc     r8
0x1800ac60b  cmp     [rsi+r8*2], r14w
0x1800ac610  jnz     short loc_1800AC608
0x1800ac612  mov     rdx, rsi
0x1800ac615  lea     rcx, [rbp+290h+var_310]
0x1800ac619  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ac61e  mov     rdx, [rdi+8]
0x1800ac622  mov     r8, rbx
0x1800ac625  inc     r8
0x1800ac628  cmp     [rdx+r8*2], r14w
0x1800ac62d  jnz     short loc_1800AC625
0x1800ac62f  lea     rcx, [rbp+290h+var_2D0]
0x1800ac633  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ac638  mov     rdx, [rsp+390h+Block]
0x1800ac63d  inc     rbx
0x1800ac640  cmp     [rdx+rbx*2], r14w
0x1800ac645  jnz     short loc_1800AC63D
0x1800ac647  mov     r8, rbx
0x1800ac64a  lea     rcx, [rbp+290h+var_2B0]
0x1800ac64e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ac653  mov     [rsp+390h+var_368], 2
0x1800ac65b  lea     rax, [rbp+290h+var_310]
0x1800ac65f  mov     qword ptr [rsp+390h+var_370], rax
0x1800ac664  xor     r9d, r9d
0x1800ac667  mov     r8, [rsp+390h+Block]
0x1800ac66c  mov     rdx, [rsp+390h+var_348]
0x1800ac671  mov     rcx, rdi
0x1800ac674  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x1800ac679  mov     [rsp+390h+var_360], eax
0x1800ac67d  test    eax, eax
0x1800ac67f  jns     short loc_1800AC6EE
0x1800ac681  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac686  mov     ecx, [rsp+390h+var_360]
0x1800ac68a  mov     [rsp+390h+var_370], ecx; int
0x1800ac68e  lea     r9, word_180142E98; unsigned __int16 *
0x1800ac695  lea     r8, aDeclaredconfig_143; "DeclaredConfigurationStore_GetPersisted"...
0x1800ac69c  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac6a3  mov     rcx, rax; this
0x1800ac6a6  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800ac6ab  mov     ebx, [rsp+390h+var_360]
0x1800ac6af  lea     rcx, [rbp+290h+var_310]; this
0x1800ac6b3  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800ac6b8  nop
0x1800ac6b9  mov     rcx, [rsp+390h+Block]; Block
0x1800ac6be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac6c3  mov     [rsp+390h+Block], r14
0x1800ac6c8  cmp     [rsp+390h+var_360], r14d
0x1800ac6cd  jge     short loc_1800AC6E9
0x1800ac6cf  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac6d4  mov     r8d, [rsp+390h+var_360]; int
0x1800ac6d9  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac6e0  mov     rcx, rax; this
0x1800ac6e3  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800ac6e8  nop
0x1800ac6e9  jmp     loc_1800AC929
0x1800ac6ee  mov     [rsp+390h+var_350], r14d
0x1800ac6f3  lea     r8, [rsp+390h+var_350]; unsigned int *
0x1800ac6f8  mov     rdx, rsi; unsigned __int16 *
0x1800ac6fb  mov     rcx, [rdi]; psz
0x1800ac6fe  call    ?DeclaredConfigurationStore_GetRefreshFlag@@YAJPEBG0PEAK@Z; DeclaredConfigurationStore_GetRefreshFlag(ushort const *,ushort const *,ulong *)
0x1800ac703  mov     ebx, eax
0x1800ac705  mov     eax, 80000000h
0x1800ac70a  lea     ecx, [rbx+rax]
0x1800ac70d  test    eax, ecx
0x1800ac70f  jnz     short loc_1800AC77F
0x1800ac711  cmp     ebx, 80070002h
0x1800ac717  jz      short loc_1800AC77F
0x1800ac719  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac71e  mov     [rsp+390h+var_370], ebx; int
0x1800ac722  lea     r9, word_180142E98; unsigned __int16 *
0x1800ac729  lea     r8, aDeclaredconfig_237; "DeclaredConfigurationStore_GetRefreshFl"...
0x1800ac730  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac737  mov     rcx, rax; this
0x1800ac73a  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800ac73f  nop
0x1800ac740  lea     rcx, [rbp+290h+var_310]; this
0x1800ac744  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800ac749  nop
0x1800ac74a  mov     rcx, [rsp+390h+Block]; Block
0x1800ac74f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac754  mov     [rsp+390h+Block], r14
0x1800ac759  cmp     [rsp+390h+var_360], r14d
0x1800ac75e  jge     short loc_1800AC77A
0x1800ac760  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac765  mov     r8d, [rsp+390h+var_360]; int
0x1800ac76a  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac771  mov     rcx, rax; this
0x1800ac774  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800ac779  nop
0x1800ac77a  jmp     loc_1800AC929
0x1800ac77f  cmp     [rbp+290h+var_200], 2
0x1800ac786  jz      loc_1800AC860
0x1800ac78c  cmp     [rbp+290h+var_200], 4
0x1800ac793  jz      short loc_1800AC7D9
0x1800ac795  lea     rcx, [rbp+290h+var_310]; this
0x1800ac799  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800ac79e  nop
0x1800ac79f  mov     rcx, [rsp+390h+Block]; Block
0x1800ac7a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac7a9  mov     [rsp+390h+Block], r14
0x1800ac7ae  cmp     [rsp+390h+var_360], r14d
0x1800ac7b3  jge     short loc_1800AC7CF
0x1800ac7b5  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac7ba  mov     r8d, [rsp+390h+var_360]; int
0x1800ac7bf  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac7c6  mov     rcx, rax; this
0x1800ac7c9  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800ac7ce  nop
0x1800ac7cf  mov     ebx, 8000FFFFh
0x1800ac7d4  jmp     loc_1800AC929
0x1800ac7d9  lea     rdx, [rbp+290h+var_310]; struct DCDocument *
0x1800ac7dd  mov     rcx, rdi; struct DeclaredConfigurationScopeData *
0x1800ac7e0  call    ?DeclaredConfigurationExtension_GetSettingsGivenInventoryDoc@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@@Z; DeclaredConfigurationExtension_GetSettingsGivenInventoryDoc(DeclaredConfigurationScopeData *,DCDocument *)
0x1800ac7e5  mov     ebx, eax
0x1800ac7e7  mov     [rsp+390h+var_360], eax
0x1800ac7eb  test    eax, eax
0x1800ac7ed  jns     loc_1800AC8EF
0x1800ac7f3  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac7f8  mov     ecx, [rsp+390h+var_360]
0x1800ac7fc  mov     [rsp+390h+var_370], ecx; int
0x1800ac800  lea     r9, word_180142E98; unsigned __int16 *
0x1800ac807  lea     r8, aDeclaredconfig_254; "DeclaredConfigurationExtension_GetSetti"...
0x1800ac80e  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac815  mov     rcx, rax; this
0x1800ac818  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800ac81d  mov     ebx, [rsp+390h+var_360]
0x1800ac821  lea     rcx, [rbp+290h+var_310]; this
0x1800ac825  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800ac82a  nop
0x1800ac82b  mov     rcx, [rsp+390h+Block]; Block
0x1800ac830  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac835  mov     [rsp+390h+Block], r14
0x1800ac83a  cmp     [rsp+390h+var_360], r14d
0x1800ac83f  jge     short loc_1800AC85B
0x1800ac841  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac846  mov     r8d, [rsp+390h+var_360]; int
0x1800ac84b  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac852  mov     rcx, rax; this
0x1800ac855  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800ac85a  nop
0x1800ac85b  jmp     loc_1800AC929
0x1800ac860  cmp     [rsp+390h+var_350], r14d
0x1800ac865  jnz     loc_1800AC8EB
0x1800ac86b  lea     rdx, [rbp+290h+var_310]; struct DCDocument *
0x1800ac86f  mov     rcx, rdi; struct DeclaredConfigurationScopeData *
0x1800ac872  call    ?DeclaredConfigurationExtension_DeleteConfigurationsGivenCurrentDoc@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@@Z; DeclaredConfigurationExtension_DeleteConfigurationsGivenCurrentDoc(DeclaredConfigurationScopeData *,DCDocument *)
0x1800ac877  mov     ebx, eax
0x1800ac879  mov     [rsp+390h+var_360], eax
0x1800ac87d  test    eax, eax
0x1800ac87f  jns     short loc_1800AC8EF
0x1800ac881  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac886  mov     ecx, [rsp+390h+var_360]
0x1800ac88a  mov     [rsp+390h+var_370], ecx; int
0x1800ac88e  lea     r9, word_180142E98; unsigned __int16 *
0x1800ac895  lea     r8, aDeclaredconfig_207; "DeclaredConfigurationExtension_DeleteCo"...
0x1800ac89c  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac8a3  mov     rcx, rax; this
0x1800ac8a6  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800ac8ab  mov     ebx, [rsp+390h+var_360]
0x1800ac8af  lea     rcx, [rbp+290h+var_310]; this
0x1800ac8b3  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800ac8b8  nop
0x1800ac8b9  mov     rcx, [rsp+390h+Block]; Block
0x1800ac8be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac8c3  mov     [rsp+390h+Block], r14
0x1800ac8c8  cmp     [rsp+390h+var_360], r14d
0x1800ac8cd  jge     short loc_1800AC8E9
0x1800ac8cf  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac8d4  mov     r8d, [rsp+390h+var_360]; int
0x1800ac8d9  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac8e0  mov     rcx, rax; this
0x1800ac8e3  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800ac8e8  nop
0x1800ac8e9  jmp     short loc_1800AC929
0x1800ac8eb  mov     ebx, [rsp+390h+var_360]
0x1800ac8ef  lea     rcx, [rbp+290h+var_310]; this
0x1800ac8f3  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800ac8f8  nop
0x1800ac8f9  mov     rcx, [rsp+390h+Block]; Block
0x1800ac8fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac903  mov     [rsp+390h+Block], r14
0x1800ac908  cmp     [rsp+390h+var_360], r14d
0x1800ac90d  jge     short loc_1800AC929
0x1800ac90f  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac914  mov     r8d, [rsp+390h+var_360]; int
0x1800ac919  lea     rdx, aDeclaredconfig_119; "DeclaredConfigurationStore_GetInventory"...
0x1800ac920  mov     rcx, rax; this
0x1800ac923  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800ac928  nop
0x1800ac929  lea     rcx, [rsp+390h+var_348]
0x1800ac92e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ac933  mov     eax, ebx
0x1800ac935  mov     rcx, [rbp+290h+var_20]
0x1800ac93c  xor     rcx, rsp; StackCookie
0x1800ac93f  call    __security_check_cookie
0x1800ac944  lea     r11, [rsp+390h+var_10]
0x1800ac94c  mov     rbx, [r11+30h]
0x1800ac950  mov     rsi, [r11+38h]
0x1800ac954  mov     rsp, r11
0x1800ac957  pop     r14
0x1800ac959  pop     rdi
0x1800ac95a  pop     rbp
0x1800ac95b  retn
```
