# PackagedCreateProcess::GetMatchingAppExtensionIfPresent(ushort const *,_FILE_ID_INFO const &,ushort const *,ushort const *,bool,ushort const *,ushort const *,StateRepository::Cache::Entity::Application_NoThrow const &,ushort const *,StateRepository::Cache::Manager_NoThrow &,ExtendedPackagedAppContext *,bool)

- ea: `0x18012a29c`
- end: `0x18012a683`
- name: `?GetMatchingAppExtensionIfPresent@PackagedCreateProcess@@CAJPEBGAEBU_FILE_ID_INFO@@00_N00AEBVApplication_NoThrow@Entity@Cache@StateRepository@@0AEAVManager_NoThrow@56@PEAVExtendedPackagedAppContext@@2@Z`
- size: `999`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _FILE_ID_INFO *, const unsigned __int16 *, const unsigned __int16 *, bool, const unsigned __int16 *, const unsigned __int16 *, const struct StateRepository::Cache::Entity::Application_NoThrow *, wchar_t *String2, struct StateRepository::Cache::Manager_NoThrow *, struct ExtendedPackagedAppContext *, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18015626c`
- `0x180156620`

## callees

- `0x1800309b0`
- `0x180058768`
- `0x1800c9f18`
- `0x1800ca304`
- `0x180108a44`
- `0x18010a640`
- `0x18012a29c`
- `0x18012a68c`
- `0x180156990`
- `0x1801572ec`
- `0x18015736c`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18012a3e5`
- `ntdll!_wcsicmp` at `0x18012a406`
- `ntdll!_wcsicmp` at `0x18012a484`
- `ntdll!_wcsicmp` at `0x18012a5d0`
- `ntdll!_wcsicmp` at `0x18012a3e5`
- `ntdll!_wcsicmp` at `0x18012a406`
- `ntdll!_wcsicmp` at `0x18012a484`
- `ntdll!_wcsicmp` at `0x18012a5d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012a338`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012a603`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012a338`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012a603`

## string_xrefs

- `0x18012a315`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18012a397`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18012a628`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18012a666`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18012a2fd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall PackagedCreateProcess::GetMatchingAppExtensionIfPresent(
        const unsigned __int16 *a1,
        const struct _FILE_ID_INFO *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const struct StateRepository::Cache::Entity::Application_NoThrow *a8,
        wchar_t *String2,
        struct StateRepository::Cache::Manager_NoThrow *a10,
        struct ExtendedPackagedAppContext *a11,
        bool a12)
{
  const struct StateRepository::Cache::Entity::Application_NoThrow *v12; // r15
  unsigned __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  int MatchingPackageLocation; // ebx
  __int64 v17; // rcx
  __int64 v19; // rdx
  struct ExtendedPackagedAppContext *v20; // rdi
  wchar_t *v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // r8
  const unsigned __int16 *v24; // r14
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  bool *pszPath; // [rsp+28h] [rbp-E0h]
  int pszPatha; // [rsp+28h] [rbp-E0h]
  bool v31[8]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h]
  __m256i v34; // [rsp+70h] [rbp-98h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp-78h]
  __int128 v36; // [rsp+98h] [rbp-70h]
  __int128 v37; // [rsp+A8h] [rbp-60h]
  __int64 v38; // [rsp+B8h] [rbp-50h]
  __int64 v39; // [rsp+C0h] [rbp-48h]
  __int128 v40; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-30h]
  __int64 v42; // [rsp+E0h] [rbp-28h]
  wchar_t *v43[2]; // [rsp+E8h] [rbp-20h]
  __int128 v44; // [rsp+F8h] [rbp-10h]
  __int64 v45; // [rsp+108h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v12 = a8;
  v32 = 0;
  LODWORD(v33) = 0;
  v13 = *(_QWORD *)a8;
  v34.m256i_i64[0] = 0;
  v14 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(
          (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v32,
          a10,
          v13);
  MatchingPackageLocation = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v14,
      (int)pszPath);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)MatchingPackageLocation,
      pszPatha);
LABEL_3:
    v17 = v32;
    v32 = 0;
LABEL_4:
    if ( v17 )
      SRCacheContext_Close(v17);
    return (unsigned int)MatchingPackageLocation;
  }
  v39 = 0;
  memset(&v34.m256i_u64[1], 0, 24);
  v36 = 0;
  v37 = 0;
  String1 = 0;
  v38 = 0;
  LOBYTE(a8) = 0;
  MatchingPackageLocation = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(
                              &v32,
                              v15,
                              &v34.m256i_u64[1],
                              &a8);
  if ( MatchingPackageLocation < 0 )
  {
    v19 = 267;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)MatchingPackageLocation,
      (int)pszPath);
LABEL_10:
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v34.m256i_u64[1]);
    goto LABEL_3;
  }
  v20 = a11;
  while ( 1 )
  {
    if ( !(_BYTE)a8 )
      goto LABEL_44;
    v21 = String1;
    if ( !_wcsicmp(String1, L"Windows.AppExecutionAlias") || !a12 && !_wcsicmp(v21, L"Windows.FullTrustProcess") )
    {
      v22 = v36;
      if ( (_QWORD)v36 )
        break;
    }
LABEL_23:
    LODWORD(v33) = v33 + 1;
    MatchingPackageLocation = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(
                                &v32,
                                v22,
                                &v34.m256i_u64[1],
                                &a8);
    if ( MatchingPackageLocation < 0 )
    {
      v19 = 312;
      goto LABEL_9;
    }
  }
  pszPath = v31;
  v40 = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  v31[0] = 0;
  v41 = 0;
  v42 = 0;
  v45 = 0;
  MatchingPackageLocation = StateRepository::Cache::Entity::Activation_NoThrow::Get(a10, v36, v23, &v40);
  if ( MatchingPackageLocation < 0 )
  {
    v27 = 287;
    goto LABEL_50;
  }
  if ( !v31[0] )
    goto LABEL_22;
  v24 = v43[0];
  if ( !_wcsicmp(v43[0], String2) )
    goto LABEL_22;
  v31[0] = 0;
  MatchingPackageLocation = PackagedCreateProcess::GetMatchingPackageLocation(a1, a2, v24, a3, a4, a5, a6, a7, v20, v31);
  if ( MatchingPackageLocation < 0 )
  {
    v25 = 296;
    goto LABEL_48;
  }
  if ( !v31[0] )
  {
LABEL_22:
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v40);
    goto LABEL_23;
  }
  MatchingPackageLocation = StringCchCopyW((unsigned __int16 *)v20 + 1, 0x82u, *((const unsigned __int16 **)v12 + 4));
  if ( MatchingPackageLocation < 0 )
  {
    v25 = 300;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)MatchingPackageLocation,
      (int)pszPath);
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v40);
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v34.m256i_u64[1]);
    v17 = v32;
    v32 = 0;
    goto LABEL_4;
  }
  if ( (v41 & 0x40) != 0 && (v41 & 0x100) != 0 )
  {
    v26 = 3;
  }
  else if ( (v41 & 8) != 0 && (v41 & 0x100) != 0 )
  {
    v26 = 2;
  }
  else if ( (v41 & 0x10) != 0 || (v41 & 0x200) != 0 )
  {
    v26 = 4;
  }
  else if ( (v41 & 0x20) != 0 )
  {
    v26 = 5;
  }
  else
  {
    v26 = ((unsigned int)v41 >> 8) & 1;
  }
  *((_DWORD *)v20 + 137) = v26;
  MatchingPackageLocation = ExtendedPackagedAppContext::SetExeLocation(v20, v24);
  if ( MatchingPackageLocation < 0 )
  {
    v27 = 302;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)MatchingPackageLocation,
      (int)pszPath);
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v40);
    goto LABEL_10;
  }
  MatchingPackageLocation = ExtendedPackagedAppContext::SetCategory(v20, v21);
  if ( MatchingPackageLocation < 0 )
  {
    v27 = 303;
    goto LABEL_50;
  }
  *((_BYTE *)v20 + 544) = _wcsicmp(v21, L"Windows.AppExecutionAlias") == 0;
  StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v40);
LABEL_44:
  StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v34.m256i_u64[1]);
  v28 = v32;
  v32 = 0;
  if ( v28 )
    SRCacheContext_Close(v28);
  return 0;
}

```

## disassembly

```asm
0x18012a29c  mov     rax, rsp
0x18012a29f  mov     [rax+20h], r9
0x18012a2a3  mov     [rax+18h], r8
0x18012a2a7  mov     [rax+10h], rdx
0x18012a2ab  mov     [rax+8], rcx
0x18012a2af  push    rbp
0x18012a2b0  push    rbx
0x18012a2b1  push    rsi
0x18012a2b2  push    rdi
0x18012a2b3  push    r12
0x18012a2b5  push    r13
0x18012a2b7  push    r14
0x18012a2b9  push    r15
0x18012a2bb  lea     rbp, [rax-58h]
0x18012a2bf  sub     rsp, 118h
0x18012a2c6  mov     r15, [rbp+50h+arg_38]
0x18012a2cd  lea     rcx, [rsp+150h+var_F8]; this
0x18012a2d2  mov     rdx, [rbp+50h+arg_48]; struct StateRepository::Cache::Manager_NoThrow *
0x18012a2d9  xor     r14d, r14d
0x18012a2dc  mov     [rsp+150h+var_F8], r14
0x18012a2e1  mov     dword ptr [rsp+150h+var_F0], r14d
0x18012a2e6  mov     r8, [r15]; __int64
0x18012a2e9  mov     qword ptr [rsp+150h+var_E8], r14
0x18012a2ee  call    ?OpenByApplication@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(StateRepository::Cache::Manager_NoThrow &,__int64)
0x18012a2f3  mov     ebx, eax
0x18012a2f5  test    eax, eax
0x18012a2f7  jns     short loc_18012A345
0x18012a2f9  mov     rcx, [rbp+58h]; this
0x18012a2fd  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012a304  mov     r9d, eax; char *
0x18012a307  mov     edx, 3AFh; void *
0x18012a30c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a311  mov     rcx, [rbp+58h]; this
0x18012a315  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x18012a31c  mov     r9d, ebx; char *
0x18012a31f  mov     edx, 106h; void *
0x18012a324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a329  mov     rcx, [rsp+150h+var_F8]
0x18012a32e  mov     [rsp+150h+var_F8], r14
0x18012a333  test    rcx, rcx
0x18012a336  jz      short loc_18012A33E
0x18012a338  call    cs:__imp_SRCacheContext_Close
0x18012a33e  mov     eax, ebx
0x18012a340  jmp     loc_18012A60B
0x18012a345  xorps   xmm0, xmm0
0x18012a348  mov     [rbp+50h+var_98], r14
0x18012a34c  xorps   xmm1, xmm1
0x18012a34f  movdqa  xmmword ptr [rsp+150h+var_E8+8], xmm0
0x18012a355  lea     r9, [rbp+50h+arg_38]
0x18012a35c  movdqa  [rbp+50h+var_C0], xmm0
0x18012a361  lea     r8, [rsp+150h+var_E8+8]
0x18012a366  movdqa  [rbp+50h+var_B0], xmm1
0x18012a36b  lea     rcx, [rsp+150h+var_F8]
0x18012a370  mov     [rbp+50h+var_D0], r14
0x18012a374  mov     [rbp+50h+String1], r14
0x18012a378  mov     [rbp+50h+var_A0], r14
0x18012a37c  mov     byte ptr [rbp+50h+arg_38], r14b
0x18012a383  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x18012a388  mov     ebx, eax
0x18012a38a  test    eax, eax
0x18012a38c  jns     short loc_18012A3B5
0x18012a38e  mov     edx, 10Bh; void *
0x18012a393  mov     rcx, [rbp+58h]; this
0x18012a397  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x18012a39e  mov     r9d, ebx; char *
0x18012a3a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a3a6  lea     rcx, [rsp+150h+var_E8+8]; this
0x18012a3ab  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18012a3b0  jmp     loc_18012A329
0x18012a3b5  mov     rdi, [rbp+50h+arg_50]
0x18012a3bc  mov     r12, [rbp+50h+arg_30]
0x18012a3c3  mov     r13, [rbp+50h+arg_28]
0x18012a3ca  cmp     byte ptr [rbp+50h+arg_38], r14b
0x18012a3d1  jz      loc_18012A5EA
0x18012a3d7  mov     rsi, [rbp+50h+String1]
0x18012a3db  lea     rdx, aWindowsAppexec; "Windows.AppExecutionAlias"
0x18012a3e2  mov     rcx, rsi; String1
0x18012a3e5  call    cs:__imp__wcsicmp
0x18012a3eb  test    eax, eax
0x18012a3ed  jz      short loc_18012A414
0x18012a3ef  cmp     [rbp+50h+arg_58], r14b
0x18012a3f6  jnz     loc_18012A4F0
0x18012a3fc  lea     rdx, aWindowsFulltru; "Windows.FullTrustProcess"
0x18012a403  mov     rcx, rsi; String1
0x18012a406  call    cs:__imp__wcsicmp
0x18012a40c  test    eax, eax
0x18012a40e  jnz     loc_18012A4F0
0x18012a414  mov     rdx, qword ptr [rbp+50h+var_C0]
0x18012a418  test    rdx, rdx
0x18012a41b  jz      loc_18012A4F0
0x18012a421  mov     rcx, [rbp+50h+arg_48]
0x18012a428  lea     rax, [rsp+150h+var_100]
0x18012a42d  xorps   xmm0, xmm0
0x18012a430  mov     [rsp+150h+pszPath], rax; int
0x18012a435  xorps   xmm1, xmm1
0x18012a438  movdqa  [rbp+50h+var_90], xmm0
0x18012a43d  lea     r9, [rbp+50h+var_90]
0x18012a441  movdqa  xmmword ptr [rbp+50h+var_70], xmm0
0x18012a446  movdqa  [rbp+50h+var_60], xmm1
0x18012a44b  mov     [rsp+150h+var_100], r14b
0x18012a450  mov     [rbp+50h+var_80], 0
0x18012a458  mov     [rbp+50h+var_78], r14
0x18012a45c  mov     [rbp+50h+var_50], r14
0x18012a460  call    ?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x18012a465  mov     ebx, eax
0x18012a467  test    eax, eax
0x18012a469  js      loc_18012A65D
0x18012a46f  cmp     [rsp+150h+var_100], r14b
0x18012a474  jz      short loc_18012A4E7
0x18012a476  mov     r14, [rbp+50h+var_70]
0x18012a47a  mov     rdx, [rbp+50h+String2]; String2
0x18012a481  mov     rcx, r14; String1
0x18012a484  call    cs:__imp__wcsicmp
0x18012a48a  test    eax, eax
0x18012a48c  jz      short loc_18012A4E4
0x18012a48e  mov     r9, [rbp+50h+arg_10]; unsigned __int16 *
0x18012a492  lea     rax, [rsp+150h+var_100]
0x18012a497  mov     rdx, [rbp+50h+arg_8]; struct _FILE_ID_INFO *
0x18012a49b  mov     r8, r14; unsigned __int16 *
0x18012a49e  mov     rcx, [rbp+50h+arg_0]; unsigned __int16 *
0x18012a4a2  mov     [rsp+150h+var_108], rax; bool *
0x18012a4a7  mov     al, [rbp+50h+arg_20]
0x18012a4ad  mov     [rsp+150h+var_110], rdi; struct ExtendedPackagedAppContext *
0x18012a4b2  mov     [rsp+150h+var_118], r12; unsigned __int16 *
0x18012a4b7  mov     [rsp+150h+var_120], r13; unsigned __int16 *
0x18012a4bc  mov     [rsp+150h+var_128], al; bool
0x18012a4c0  mov     rax, [rbp+50h+arg_18]
0x18012a4c4  mov     [rsp+150h+pszPath], rax; int
0x18012a4c9  mov     [rsp+150h+var_100], 0
0x18012a4ce  call    ?GetMatchingPackageLocation@PackagedCreateProcess@@CAJPEBGAEBU_FILE_ID_INFO@@000_N00PEAVExtendedPackagedAppContext@@AEA_N@Z; PackagedCreateProcess::GetMatchingPackageLocation(ushort const *,_FILE_ID_INFO const &,ushort const *,ushort const *,ushort const *,bool,ushort const *,ushort const *,ExtendedPackagedAppContext *,bool &)
0x18012a4d3  mov     ebx, eax
0x18012a4d5  test    eax, eax
0x18012a4d7  js      loc_18012A61F
0x18012a4dd  cmp     [rsp+150h+var_100], 0
0x18012a4e2  jnz     short loc_18012A51E
0x18012a4e4  xor     r14d, r14d
0x18012a4e7  lea     rcx, [rbp+50h+var_90]; this
0x18012a4eb  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18012a4f0  inc     dword ptr [rsp+150h+var_F0]
0x18012a4f4  lea     r9, [rbp+50h+arg_38]
0x18012a4fb  lea     r8, [rsp+150h+var_E8+8]
0x18012a500  lea     rcx, [rsp+150h+var_F8]
0x18012a505  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x18012a50a  mov     ebx, eax
0x18012a50c  test    eax, eax
0x18012a50e  jns     loc_18012A3CA
0x18012a514  mov     edx, 138h
0x18012a519  jmp     loc_18012A393
0x18012a51e  mov     r8, [r15+20h]; unsigned __int16 *
0x18012a522  lea     rcx, [rdi+2]; unsigned __int16 *
0x18012a526  mov     edx, 82h; unsigned __int64
0x18012a52b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012a530  mov     ebx, eax
0x18012a532  test    eax, eax
0x18012a534  jns     short loc_18012A540
0x18012a536  mov     edx, 12Ch
0x18012a53b  jmp     loc_18012A624
0x18012a540  mov     eax, dword ptr [rbp+50h+var_80]
0x18012a543  test    al, 40h
0x18012a545  jz      short loc_18012A554
0x18012a547  bt      eax, 8
0x18012a54b  jnb     short loc_18012A554
0x18012a54d  mov     eax, 3
0x18012a552  jmp     short loc_18012A587
0x18012a554  test    al, 8
0x18012a556  jz      short loc_18012A565
0x18012a558  bt      eax, 8
0x18012a55c  jnb     short loc_18012A565
0x18012a55e  mov     eax, 2
0x18012a563  jmp     short loc_18012A587
0x18012a565  test    al, 10h
0x18012a567  jnz     short loc_18012A582
0x18012a569  bt      eax, 9
0x18012a56d  jb      short loc_18012A582
0x18012a56f  test    al, 20h
0x18012a571  jz      short loc_18012A57A
0x18012a573  mov     eax, 5
0x18012a578  jmp     short loc_18012A587
0x18012a57a  shr     eax, 8
0x18012a57d  and     eax, 1
0x18012a580  jmp     short loc_18012A587
0x18012a582  mov     eax, 4
0x18012a587  mov     rdx, r14; unsigned __int16 *
0x18012a58a  mov     [rdi+224h], eax
0x18012a590  mov     rcx, rdi; this
0x18012a593  call    ?SetExeLocation@ExtendedPackagedAppContext@@QEAAJPEBG@Z; ExtendedPackagedAppContext::SetExeLocation(ushort const *)
0x18012a598  xor     r14d, r14d
0x18012a59b  mov     ebx, eax
0x18012a59d  test    eax, eax
0x18012a59f  jns     short loc_18012A5AB
0x18012a5a1  mov     edx, 12Eh
0x18012a5a6  jmp     loc_18012A662
0x18012a5ab  mov     rdx, rsi; unsigned __int16 *
0x18012a5ae  mov     rcx, rdi; this
0x18012a5b1  call    ?SetCategory@ExtendedPackagedAppContext@@QEAAJPEBG@Z; ExtendedPackagedAppContext::SetCategory(ushort const *)
0x18012a5b6  mov     ebx, eax
0x18012a5b8  test    eax, eax
0x18012a5ba  jns     short loc_18012A5C6
0x18012a5bc  mov     edx, 12Fh
0x18012a5c1  jmp     loc_18012A662
0x18012a5c6  lea     rdx, aWindowsAppexec; "Windows.AppExecutionAlias"
0x18012a5cd  mov     rcx, rsi; String1
0x18012a5d0  call    cs:__imp__wcsicmp
0x18012a5d6  test    eax, eax
0x18012a5d8  lea     rcx, [rbp+50h+var_90]; this
0x18012a5dc  setz    al
0x18012a5df  mov     [rdi+220h], al
0x18012a5e5  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18012a5ea  lea     rcx, [rsp+150h+var_E8+8]; this
0x18012a5ef  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18012a5f4  mov     rcx, [rsp+150h+var_F8]
0x18012a5f9  mov     [rsp+150h+var_F8], r14
0x18012a5fe  test    rcx, rcx
0x18012a601  jz      short loc_18012A609
0x18012a603  call    cs:__imp_SRCacheContext_Close
0x18012a609  xor     eax, eax
0x18012a60b  add     rsp, 118h
0x18012a612  pop     r15
0x18012a614  pop     r14
0x18012a616  pop     r13
0x18012a618  pop     r12
0x18012a61a  pop     rdi
0x18012a61b  pop     rsi
0x18012a61c  pop     rbx
0x18012a61d  pop     rbp
0x18012a61e  retn
0x18012a61f  mov     edx, 128h; void *
0x18012a624  mov     rcx, [rbp+58h]; this
0x18012a628  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x18012a62f  mov     r9d, ebx; char *
0x18012a632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a637  lea     rcx, [rbp+50h+var_90]; this
0x18012a63b  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18012a640  lea     rcx, [rsp+150h+var_E8+8]; this
0x18012a645  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18012a64a  mov     rcx, [rsp+150h+var_F8]
0x18012a64f  mov     [rsp+150h+var_F8], 0
0x18012a658  jmp     loc_18012A333
0x18012a65d  mov     edx, 11Fh; void *
0x18012a662  mov     rcx, [rbp+58h]; this
0x18012a666  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x18012a66d  mov     r9d, ebx; char *
0x18012a670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a675  lea     rcx, [rbp+50h+var_90]; this
0x18012a679  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18012a67e  jmp     loc_18012A3A6
```
