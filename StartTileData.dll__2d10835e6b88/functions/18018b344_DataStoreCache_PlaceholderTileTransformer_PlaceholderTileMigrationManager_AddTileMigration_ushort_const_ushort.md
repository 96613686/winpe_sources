# DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager::AddTileMigration(ushort const *,ushort const *)

- ea: `0x18018b344`
- end: `0x18018b5f9`
- name: `?AddTileMigration@PlaceholderTileMigrationManager@PlaceholderTileTransformer@DataStoreCache@@QEAAXPEBG0@Z`
- size: `693`
- prototype: `void(DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1803621a0`

## callees

- `0x18007ce8c`
- `0x18008d550`
- `0x180154ea0`
- `0x1801819b4`
- `0x18018b344`
- `0x18018b600`
- `0x18018b694`
- `0x18018b6ec`
- `0x18018b744`
- `0x18018b79c`
- `0x180368dfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18018b512`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18018b512`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18018b3c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18018b3c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18018b37f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18018b37f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b394`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b444`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b4d9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b589`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b5b1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b394`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b444`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b4d9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b589`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18018b5b1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b3a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b451`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b4e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b596`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b5be`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b3a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b451`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b4e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b596`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18018b5be`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager::AddTileMigration(
        RTL_SRWLOCK *this,
        WCHAR *a2,
        WCHAR *a3)
{
  LPWSTR FileNameW; // rbx
  RTL_SRWLOCK *v7; // r14
  char *Ptr; // rcx
  LPWSTR v9; // rbx
  char *v10; // rdx
  char *v11; // rcx
  const WCHAR *v13; // rdi
  LPWSTR v14; // rax
  const WCHAR *v15; // rdi
  LPWSTR v16; // [rsp+30h] [rbp-39h] BYREF
  RTL_SRWLOCK *v17; // [rsp+38h] [rbp-31h] BYREF
  PVOID v18; // [rsp+40h] [rbp-29h] BYREF
  __int64 v19; // [rsp+48h] [rbp-21h]
  char *v20; // [rsp+50h] [rbp-19h]
  PVOID v21; // [rsp+58h] [rbp-11h] BYREF
  __int64 v22; // [rsp+60h] [rbp-9h]
  char *v23; // [rsp+68h] [rbp-1h]
  _BYTE v24[16]; // [rsp+70h] [rbp+7h] BYREF
  char *v25; // [rsp+80h] [rbp+17h]
  LPCWSTR v26; // [rsp+D8h] [rbp+6Fh] BYREF
  LPCWSTR pszPath; // [rsp+E0h] [rbp+77h] BYREF
  char *v28; // [rsp+E8h] [rbp+7Fh] BYREF

  pszPath = a3;
  v26 = a2;
  if ( CompareStringOrdinal(a2, -1, a3, -1, 1) == 2 )
  {
    FileNameW = 0;
    if ( a2 )
    {
      if ( PathIsFileSpecW(a2) )
        FileNameW = a2;
      else
        FileNameW = PathFindFileNameW(a2);
    }
    v28 = (char *)FileNameW;
    StartPlaceHolderTelemetry::PlaceholderTileMigrationToSameTileId<unsigned short const *>(&v28);
    return;
  }
  AcquireSRWLockShared(this + 6);
  v28 = (char *)&this[6];
  v7 = this + 7;
  Ptr = (char *)this[10].Ptr;
  v9 = 0;
  v19 = 0;
  v20 = &Ptr[(unsigned __int64)this[11].Ptr];
  if ( this == (RTL_SRWLOCK *)-56LL )
    v18 = 0;
  else
    v18 = v7->Ptr;
  v22 = 0;
  v23 = Ptr;
  if ( this == (RTL_SRWLOCK *)-56LL )
    v21 = 0;
  else
    v21 = v7->Ptr;
  std::find_if_std::_Deque_iterator_std::_Deque_val_std::_Deque_simple_types_DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileMigration_______lambda_97363aa2548fbc046894ce4d818af6ea___(
    v24,
    &v21,
    &v18,
    a3);
  v10 = (char *)this[10].Ptr;
  v11 = &v10[(unsigned __int64)this[11].Ptr];
  if ( v25 != v11 )
  {
    if ( a3 )
    {
      if ( PathIsFileSpecW(a3) )
        v9 = a3;
      else
        v9 = PathFindFileNameW(a3);
    }
    v16 = v9;
    StartPlaceHolderTelemetry::PlaceholderTileMigrationToExistingSource<unsigned short const *>(&v16);
LABEL_19:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v28);
    return;
  }
  v22 = 0;
  v23 = v11;
  if ( this == (RTL_SRWLOCK *)-56LL )
    v21 = 0;
  else
    v21 = v7->Ptr;
  v19 = 0;
  v20 = v10;
  if ( this == (RTL_SRWLOCK *)-56LL )
    v18 = 0;
  else
    v18 = v7->Ptr;
  if ( *(PVOID *)(std::find_if_std::_Deque_iterator_std::_Deque_val_std::_Deque_simple_types_DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileMigration_______lambda_97363aa2548fbc046894ce4d818af6ea___(
                    v24,
                    &v18,
                    &v21,
                    a2)
                + 16) != (char *)this[11].Ptr + (unsigned __int64)this[10].Ptr )
  {
    if ( a2 )
    {
      if ( PathIsFileSpecW(a2) )
        v9 = a2;
      else
        v9 = PathFindFileNameW(a2);
    }
    v16 = v9;
    StartPlaceHolderTelemetry::PlaceholderTileMigrationFromExistingSource<unsigned short const *>(&v16);
    goto LABEL_19;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v28);
  AcquireSRWLockExclusive(this + 6);
  v17 = this + 6;
  if ( this[11].Ptr >= (PVOID)0x200 )
  {
    ImageResourceInfo::~ImageResourceInfo(*((ImageResourceInfo **)this[8].Ptr
                                          + ((__int64)this[10].Ptr & ((__int64)this[9].Ptr - 1))));
    if ( this[11].Ptr-- == (PVOID)1 )
      this[10].Ptr = 0;
    else
      ++this[10].Ptr;
  }
  v28 = (char *)this[12].Ptr + 1;
  std::deque<DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileMigration>::emplace_back<unsigned __int64,unsigned short const * &,unsigned short const * &>(
    &this[7],
    &v28,
    &v26,
    &pszPath);
  ++this[12].Ptr;
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager::WriteMigrationsToRegistry((DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager *)this);
  v13 = pszPath;
  v14 = 0;
  if ( pszPath )
  {
    if ( PathIsFileSpecW(pszPath) )
      v14 = (LPWSTR)v13;
    else
      v14 = PathFindFileNameW(v13);
  }
  v28 = (char *)v14;
  v15 = v26;
  if ( v26 )
  {
    if ( PathIsFileSpecW(v26) )
      v9 = (LPWSTR)v15;
    else
      v9 = PathFindFileNameW(v15);
  }
  v16 = v9;
  StartPlaceHolderTelemetry::PlaceholderTileIdMigrated<unsigned short const *,unsigned short const *>(&v16, &v28);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v17);
}

```

## disassembly

```asm
0x18018b344  mov     [rsp-8+pszPath], r8
0x18018b349  mov     [rsp-8+arg_8], rdx
0x18018b34e  push    rbp
0x18018b34f  push    rbx
0x18018b350  push    rsi
0x18018b351  push    rdi
0x18018b352  push    r12
0x18018b354  push    r14
0x18018b356  push    r15
0x18018b358  lea     rbp, [rsp-27h]
0x18018b35d  sub     rsp, 90h
0x18018b364  mov     r15, r8
0x18018b367  mov     rsi, rdx
0x18018b36a  mov     rdi, rcx
0x18018b36d  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x18018b375  or      r9d, 0FFFFFFFFh; cchCount2
0x18018b379  or      edx, r9d; cchCount1
0x18018b37c  mov     rcx, rsi; lpString1
0x18018b37f  call    cs:__imp_CompareStringOrdinal
0x18018b385  cmp     eax, 2
0x18018b388  jnz     short loc_18018B3C1
0x18018b38a  xor     ebx, ebx
0x18018b38c  test    rsi, rsi
0x18018b38f  jz      short loc_18018B3AF
0x18018b391  mov     rcx, rsi; pszPath
0x18018b394  call    cs:__imp_PathIsFileSpecW
0x18018b39a  test    eax, eax
0x18018b39c  jnz     short loc_18018B3AC
0x18018b39e  mov     rcx, rsi; pszPath
0x18018b3a1  call    cs:__imp_PathFindFileNameW
0x18018b3a7  mov     rbx, rax
0x18018b3aa  jmp     short loc_18018B3AF
0x18018b3ac  mov     rbx, rsi
0x18018b3af  mov     [rbp+57h+arg_18], rbx
0x18018b3b3  lea     rcx, [rbp+57h+arg_18]
0x18018b3b7  call    ??$PlaceholderTileMigrationToSameTileId@PEBG@StartPlaceHolderTelemetry@@SAX$$QEAPEBG@Z; StartPlaceHolderTelemetry::PlaceholderTileMigrationToSameTileId<ushort const *>(ushort const * &&)
0x18018b3bc  jmp     loc_18018B5E7
0x18018b3c1  lea     r12, [rdi+30h]
0x18018b3c5  mov     rcx, r12; SRWLock
0x18018b3c8  call    cs:__imp_AcquireSRWLockShared
0x18018b3ce  mov     [rbp+57h+arg_18], r12
0x18018b3d2  lea     r14, [rdi+38h]
0x18018b3d6  mov     rcx, [r14+18h]
0x18018b3da  xor     ebx, ebx
0x18018b3dc  mov     [rbp+57h+var_78], rbx
0x18018b3e0  mov     rax, [r14+20h]
0x18018b3e4  add     rax, rcx
0x18018b3e7  mov     [rbp+57h+var_70], rax
0x18018b3eb  test    r14, r14
0x18018b3ee  jz      short loc_18018B3F9
0x18018b3f0  mov     rax, [r14]
0x18018b3f3  mov     [rbp+57h+var_80], rax
0x18018b3f7  jmp     short loc_18018B3FD
0x18018b3f9  mov     [rbp+57h+var_80], rbx
0x18018b3fd  mov     [rbp+57h+var_60], rbx
0x18018b401  mov     [rbp+57h+var_58], rcx
0x18018b405  test    r14, r14
0x18018b408  jz      short loc_18018B413
0x18018b40a  mov     rax, [r14]
0x18018b40d  mov     [rbp+57h+var_68], rax
0x18018b411  jmp     short loc_18018B417
0x18018b413  mov     [rbp+57h+var_68], rbx
0x18018b417  mov     r9, r15
0x18018b41a  lea     r8, [rbp+57h+var_80]
0x18018b41e  lea     rdx, [rbp+57h+var_68]
0x18018b422  lea     rcx, [rbp+57h+var_50]
0x18018b426  call    std__find_if_std___Deque_iterator_std___Deque_val_std___Deque_simple_types_DataStoreCache__PlaceholderTileTransformer__Internal__PlaceholderTileMigration_______lambda_97363aa2548fbc046894ce4d818af6ea___
0x18018b42b  mov     rdx, [rdi+50h]
0x18018b42f  mov     rcx, [rdi+58h]
0x18018b433  add     rcx, rdx
0x18018b436  cmp     [rbp+57h+var_40], rcx
0x18018b43a  jz      short loc_18018B47B
0x18018b43c  test    r15, r15
0x18018b43f  jz      short loc_18018B45F
0x18018b441  mov     rcx, r15; pszPath
0x18018b444  call    cs:__imp_PathIsFileSpecW
0x18018b44a  test    eax, eax
0x18018b44c  jnz     short loc_18018B45C
0x18018b44e  mov     rcx, r15; pszPath
0x18018b451  call    cs:__imp_PathFindFileNameW
0x18018b457  mov     rbx, rax
0x18018b45a  jmp     short loc_18018B45F
0x18018b45c  mov     rbx, r15
0x18018b45f  mov     [rbp+57h+var_90], rbx
0x18018b463  lea     rcx, [rbp+57h+var_90]
0x18018b467  call    ??$PlaceholderTileMigrationToExistingSource@PEBG@StartPlaceHolderTelemetry@@SAX$$QEAPEBG@Z; StartPlaceHolderTelemetry::PlaceholderTileMigrationToExistingSource<ushort const *>(ushort const * &&)
0x18018b46c  nop
0x18018b46d  lea     rcx, [rbp+57h+arg_18]
0x18018b471  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18018b476  jmp     loc_18018B5E7
0x18018b47b  mov     [rbp+57h+var_60], rbx
0x18018b47f  mov     [rbp+57h+var_58], rcx
0x18018b483  test    r14, r14
0x18018b486  jz      short loc_18018B491
0x18018b488  mov     rax, [r14]
0x18018b48b  mov     [rbp+57h+var_68], rax
0x18018b48f  jmp     short loc_18018B495
0x18018b491  mov     [rbp+57h+var_68], rbx
0x18018b495  mov     [rbp+57h+var_78], rbx
0x18018b499  mov     [rbp+57h+var_70], rdx
0x18018b49d  test    r14, r14
0x18018b4a0  jz      short loc_18018B4AB
0x18018b4a2  mov     rax, [r14]
0x18018b4a5  mov     [rbp+57h+var_80], rax
0x18018b4a9  jmp     short loc_18018B4AF
0x18018b4ab  mov     [rbp+57h+var_80], rbx
0x18018b4af  mov     r9, rsi
0x18018b4b2  lea     r8, [rbp+57h+var_68]
0x18018b4b6  lea     rdx, [rbp+57h+var_80]
0x18018b4ba  lea     rcx, [rbp+57h+var_50]
0x18018b4be  call    std__find_if_std___Deque_iterator_std___Deque_val_std___Deque_simple_types_DataStoreCache__PlaceholderTileTransformer__Internal__PlaceholderTileMigration_______lambda_97363aa2548fbc046894ce4d818af6ea___
0x18018b4c3  mov     rcx, [rdi+50h]
0x18018b4c7  add     rcx, [rdi+58h]
0x18018b4cb  cmp     [rax+10h], rcx
0x18018b4cf  jz      short loc_18018B506
0x18018b4d1  test    rsi, rsi
0x18018b4d4  jz      short loc_18018B4F4
0x18018b4d6  mov     rcx, rsi; pszPath
0x18018b4d9  call    cs:__imp_PathIsFileSpecW
0x18018b4df  test    eax, eax
0x18018b4e1  jnz     short loc_18018B4F1
0x18018b4e3  mov     rcx, rsi; pszPath
0x18018b4e6  call    cs:__imp_PathFindFileNameW
0x18018b4ec  mov     rbx, rax
0x18018b4ef  jmp     short loc_18018B4F4
0x18018b4f1  mov     rbx, rsi
0x18018b4f4  mov     [rbp+57h+var_90], rbx
0x18018b4f8  lea     rcx, [rbp+57h+var_90]
0x18018b4fc  call    ??$PlaceholderTileMigrationFromExistingSource@PEBG@StartPlaceHolderTelemetry@@SAX$$QEAPEBG@Z; StartPlaceHolderTelemetry::PlaceholderTileMigrationFromExistingSource<ushort const *>(ushort const * &&)
0x18018b501  jmp     loc_18018B46D
0x18018b506  lea     rcx, [rbp+57h+arg_18]
0x18018b50a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18018b50f  mov     rcx, r12; SRWLock
0x18018b512  call    cs:__imp_AcquireSRWLockExclusive
0x18018b518  mov     [rbp+57h+var_88], r12
0x18018b51c  cmp     qword ptr [rdi+58h], 200h
0x18018b524  jb      short loc_18018B54F
0x18018b526  mov     rax, [rdi+48h]
0x18018b52a  dec     rax
0x18018b52d  and     rax, [rdi+50h]
0x18018b531  mov     rcx, [rdi+40h]
0x18018b535  mov     rcx, [rcx+rax*8]; this
0x18018b539  call    ??1ImageResourceInfo@@QEAA@XZ; ImageResourceInfo::~ImageResourceInfo(void)
0x18018b53e  sub     qword ptr [rdi+58h], 1
0x18018b543  jnz     short loc_18018B54B
0x18018b545  mov     [rdi+50h], rbx
0x18018b549  jmp     short loc_18018B54F
0x18018b54b  inc     qword ptr [rdi+50h]
0x18018b54f  mov     rax, [rdi+60h]
0x18018b553  inc     rax
0x18018b556  mov     [rbp+57h+arg_18], rax
0x18018b55a  lea     r9, [rbp+57h+pszPath]
0x18018b55e  lea     r8, [rbp+57h+arg_8]
0x18018b562  lea     rdx, [rbp+57h+arg_18]
0x18018b566  mov     rcx, r14
0x18018b569  call    ??$emplace_back@_KAEAPEBGAEAPEBG@?$deque@UPlaceholderTileMigration@Internal@PlaceholderTileTransformer@DataStoreCache@@V?$allocator@UPlaceholderTileMigration@Internal@PlaceholderTileTransformer@DataStoreCache@@@std@@@std@@QEAAAEAUPlaceholderTileMigration@Internal@PlaceholderTileTransformer@DataStoreCache@@$$QEA_KAEAPEBG1@Z; std::deque<DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileMigration>::emplace_back<unsigned __int64,ushort const * &,ushort const * &>(unsigned __int64 &&,ushort const * &,ushort const * &)
0x18018b56e  inc     qword ptr [rdi+60h]
0x18018b572  mov     rcx, rdi; this
0x18018b575  call    ?WriteMigrationsToRegistry@PlaceholderTileMigrationManager@PlaceholderTileTransformer@DataStoreCache@@AEAAXXZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager::WriteMigrationsToRegistry(void)
0x18018b57a  mov     rdi, [rbp+57h+pszPath]
0x18018b57e  mov     rax, rbx
0x18018b581  test    rdi, rdi
0x18018b584  jz      short loc_18018B5A1
0x18018b586  mov     rcx, rdi; pszPath
0x18018b589  call    cs:__imp_PathIsFileSpecW
0x18018b58f  test    eax, eax
0x18018b591  jnz     short loc_18018B59E
0x18018b593  mov     rcx, rdi; pszPath
0x18018b596  call    cs:__imp_PathFindFileNameW
0x18018b59c  jmp     short loc_18018B5A1
0x18018b59e  mov     rax, rdi
0x18018b5a1  mov     [rbp+57h+arg_18], rax
0x18018b5a5  mov     rdi, [rbp+57h+arg_8]
0x18018b5a9  test    rdi, rdi
0x18018b5ac  jz      short loc_18018B5CC
0x18018b5ae  mov     rcx, rdi; pszPath
0x18018b5b1  call    cs:__imp_PathIsFileSpecW
0x18018b5b7  test    eax, eax
0x18018b5b9  jnz     short loc_18018B5C9
0x18018b5bb  mov     rcx, rdi; pszPath
0x18018b5be  call    cs:__imp_PathFindFileNameW
0x18018b5c4  mov     rbx, rax
0x18018b5c7  jmp     short loc_18018B5CC
0x18018b5c9  mov     rbx, rdi
0x18018b5cc  mov     [rbp+57h+var_90], rbx
0x18018b5d0  lea     rdx, [rbp+57h+arg_18]
0x18018b5d4  lea     rcx, [rbp+57h+var_90]
0x18018b5d8  call    ??$PlaceholderTileIdMigrated@PEBGPEBG@StartPlaceHolderTelemetry@@SAX$$QEAPEBG0@Z; StartPlaceHolderTelemetry::PlaceholderTileIdMigrated<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x18018b5dd  nop
0x18018b5de  lea     rcx, [rbp+57h+var_88]
0x18018b5e2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18018b5e7  add     rsp, 90h
0x18018b5ee  pop     r15
0x18018b5f0  pop     r14
0x18018b5f2  pop     r12
0x18018b5f4  pop     rdi
0x18018b5f5  pop     rsi
0x18018b5f6  pop     rbx
0x18018b5f7  pop     rbp
0x18018b5f8  retn
```
