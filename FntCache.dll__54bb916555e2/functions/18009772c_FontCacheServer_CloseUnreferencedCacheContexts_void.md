# FontCacheServer::CloseUnreferencedCacheContexts(void)

- ea: `0x18009772c`
- end: `0x180097a20`
- name: `?CloseUnreferencedCacheContexts@FontCacheServer@@AEAAXXZ`
- size: `756`
- prototype: `void __fastcall(FontCacheServer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1800976f0`

## callees

- `0x18000e920`
- `0x180028c50`
- `0x18002bcb8`
- `0x18002bd5c`
- `0x18009772c`
- `0x180097a28`
- `0x180098744`
- `0x18009b3b0`
- `0x1800a4268`
- `0x1800b1a5c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800978f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800978f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180097762`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180097762`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180097998`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800979b6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180097998`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800979b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800977e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800977e9`

## pseudocode

```c
void __fastcall FontCacheServer::CloseUnreferencedCacheContexts(FontCacheServer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 **i; // rbx
  __int64 *v4; // rcx
  __int64 *v5; // r12
  __int64 *v6; // rcx
  __int64 **v7; // rax
  __int64 *v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r15
  unsigned int v11; // r12d
  FontCacheServer::UserCacheReference ***v12; // r13
  FontCacheServer::UserCacheReference **v13; // rbx
  FontCacheServer::UserCacheReference *v14; // rcx
  FontCacheServer::UserCacheReference **v15; // rax
  FontCacheServer::UserCacheReference **v16; // rax
  unsigned int HashCode; // eax
  FontCacheServer::UserCacheReference *v18; // rbx
  __int64 *v19; // r12
  __int64 *CacheFolderPath; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 UserFontSetCacheFileName; // rax
  FontCacheServer::UserCacheReference *v25; // rcx
  __int64 v26; // rdx
  _QWORD *v27; // rax
  __int128 v28; // [rsp+20h] [rbp-88h] BYREF
  __int128 v29; // [rsp+30h] [rbp-78h] BYREF
  __int64 v30; // [rsp+40h] [rbp-68h]
  __int64 v31; // [rsp+48h] [rbp-60h]
  FontCacheServer::UserCacheReference *v32; // [rsp+50h] [rbp-58h] BYREF
  FontCacheServer::UserCacheReference **v33; // [rsp+58h] [rbp-50h]
  char v34; // [rsp+60h] [rbp-48h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+8h] BYREF
  struct DWrite::RefString::Data *v36; // [rsp+B8h] [rbp+10h] BYREF
  struct DWrite::RefString::Data *v37; // [rsp+C0h] [rbp+18h] BYREF
  struct DWrite::RefString::Data *v38; // [rsp+C8h] [rbp+20h] BYREF

  v34 = 0;
  v32 = (FontCacheServer::UserCacheReference *)&v32;
  v33 = &v32;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 264);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  for ( i = (__int64 **)*((_QWORD *)this + 43); (__int64 **)((char *)this + 344) != i; i = (__int64 **)v5 )
  {
    v4 = i[4];
    v5 = *i;
    if ( *((_DWORD *)v4 + 2) == 1 )
    {
      i[5] = (__int64 *)v4[76];
      i[4] = 0;
      if ( v4 )
        (*(void (__fastcall **)(__int64 *))(*v4 + 16))(v4);
      v6 = *i;
      v7 = (__int64 **)i[1];
      v6[1] = (__int64)v7;
      *v7 = v6;
      *((_BYTE *)i + 16) = 0;
      v8 = (__int64 *)*((_QWORD *)this + 47);
      *i = (__int64 *)((char *)this + 368);
      i[1] = v8;
      *((_QWORD *)this + 47) = i;
      *v8 = (__int64)i;
      *((_BYTE *)i + 16) = 1;
    }
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v36 = (struct DWrite::RefString::Data *)SystemTimeAsFileTime;
  v9 = 10000000LL * *((unsigned int *)this + 99);
  if ( *(_QWORD *)&SystemTimeAsFileTime <= v9 )
    v10 = 0;
  else
    v10 = *(_QWORD *)&SystemTimeAsFileTime - v9;
  v11 = *((_DWORD *)this + 82) - *((_DWORD *)this + 83);
  v12 = (FontCacheServer::UserCacheReference ***)((char *)this + 368);
  while ( 1 )
  {
    v13 = *v12;
    if ( *v12 == (FontCacheServer::UserCacheReference **)v12
      || v11 <= *((_DWORD *)this + 98) && (unsigned __int64)v13[5] >= v10 )
    {
      break;
    }
    v14 = *v13;
    v15 = (FontCacheServer::UserCacheReference **)v13[1];
    *((_QWORD *)v14 + 1) = v15;
    *v15 = v14;
    *((_BYTE *)v13 + 16) = 0;
    v16 = v33;
    *v13 = (FontCacheServer::UserCacheReference *)&v32;
    v13[1] = (FontCacheServer::UserCacheReference *)v16;
    v33 = v13;
    *v16 = (FontCacheServer::UserCacheReference *)v13;
    *((_BYTE *)v13 + 16) = 1;
    HashCode = DWrite::RefString::GetHashCode((DWrite::RefString *)(v13 + 3));
    HashTable<DWrite::RefString,FontCacheServer::UserCacheReference>::Find((char *)this + 304, &v28, HashCode, v13 + 3);
    if ( (_QWORD)v28 != *((_QWORD *)this + 40) + 24LL * *((unsigned int *)this + 82) )
    {
      v29 = v28;
      HashTableImpl::Remove((char *)this + 304, &v29);
    }
    --v11;
  }
  LeaveCriticalSection(v2);
  v18 = v32;
  try
  {
    while ( &v32 != (FontCacheServer::UserCacheReference **)v18 )
    {
      v19 = (__int64 *)ServerSidePerUserContext::FileNameFromSidString(&v37, (char *)v18 + 24);
      CacheFolderPath = (__int64 *)FontCacheServer::GetCacheFolderPath((__int64)this, (__int64)&v36);
      v21 = *v19;
      v22 = *CacheFolderPath;
      *(_QWORD *)&v29 = *CacheFolderPath + 8;
      *((_QWORD *)&v29 + 1) = *(unsigned int *)(v22 + 4);
      v30 = v21 + 8;
      v31 = *(unsigned int *)(v21 + 4);
      DWrite::RefString::RefString(&SystemTimeAsFileTime, &v29);
      DWrite::RefString::DecrementRef(v36);
      DWrite::RefString::DecrementRef(v37);
      DeleteFileW((LPCWSTR)(*(_QWORD *)&SystemTimeAsFileTime + 8LL));
      UserFontSetCacheFileName = FontCacheServer::GetUserFontSetCacheFileName(v23, &v38, (char *)v18 + 24);
      DeleteFileW((LPCWSTR)(*(_QWORD *)UserFontSetCacheFileName + 8LL));
      DWrite::RefString::DecrementRef(v38);
      DWrite::RefString::DecrementRef(*(struct DWrite::RefString::Data **)&SystemTimeAsFileTime);
      v18 = *(FontCacheServer::UserCacheReference **)v18;
    }
  }
  catch ( ... )
  {
  }
  while ( 1 )
  {
    v25 = v32;
    if ( v32 == (FontCacheServer::UserCacheReference *)&v32 )
      break;
    v26 = *(_QWORD *)v32;
    v27 = (_QWORD *)*((_QWORD *)v32 + 1);
    *(_QWORD *)(v26 + 8) = v27;
    *v27 = v26;
    *((_BYTE *)v25 + 16) = 0;
    if ( v25 )
      FontCacheServer::UserCacheReference::`scalar deleting destructor'(v25, v26);
  }
}

```

## disassembly

```asm
0x18009772c  mov     r11, rsp
0x18009772f  push    rbx
0x180097730  push    rsi
0x180097731  push    rdi
0x180097732  push    r12
0x180097734  push    r13
0x180097736  push    r14
0x180097738  push    r15
0x18009773a  sub     rsp, 70h
0x18009773e  mov     r14, rcx
0x180097741  xor     esi, esi
0x180097743  mov     [rsp+0A8h+var_48], sil
0x180097748  lea     rax, [r11-58h]
0x18009774c  mov     [r11-58h], rax
0x180097750  lea     rax, [r11-58h]
0x180097754  mov     [r11-50h], rax
0x180097758  lea     rdi, [rcx+108h]
0x18009775f  mov     rcx, rdi; lpCriticalSection
0x180097762  call    cs:__imp_EnterCriticalSection
0x180097768  lea     r15, [r14+158h]
0x18009776f  mov     rbx, [r15]
0x180097772  cmp     r15, rbx
0x180097775  jz      short loc_1800977D9
0x180097777  mov     rcx, [rbx+20h]
0x18009777b  mov     r12, [rbx]
0x18009777e  cmp     dword ptr [rcx+8], 1
0x180097782  jnz     short loc_1800977D4
0x180097784  mov     rax, [rcx+260h]
0x18009778b  mov     [rbx+28h], rax
0x18009778f  mov     [rbx+20h], rsi
0x180097793  test    rcx, rcx
0x180097796  jz      short loc_1800977A5
0x180097798  mov     rax, [rcx]
0x18009779b  mov     rax, [rax+10h]
0x18009779f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800977a4  nop
0x1800977a5  mov     rcx, [rbx]
0x1800977a8  mov     rax, [rbx+8]
0x1800977ac  mov     [rcx+8], rax
0x1800977b0  mov     [rax], rcx
0x1800977b3  mov     [rbx+10h], sil
0x1800977b7  lea     rcx, [r14+170h]
0x1800977be  mov     rax, [rcx+8]
0x1800977c2  mov     [rbx], rcx
0x1800977c5  mov     [rbx+8], rax
0x1800977c9  mov     [rcx+8], rbx
0x1800977cd  mov     [rax], rbx
0x1800977d0  mov     byte ptr [rbx+10h], 1
0x1800977d4  mov     rbx, r12
0x1800977d7  jmp     short loc_180097772
0x1800977d9  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1800977e1  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800977e9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800977ef  mov     eax, [rsp+0A8h+SystemTimeAsFileTime.dwHighDateTime]
0x1800977f6  mov     dword ptr [rsp+0A8h+arg_8+4], eax
0x1800977fd  mov     eax, [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x180097804  mov     dword ptr [rsp+0A8h+arg_8], eax
0x18009780b  mov     eax, [r14+18Ch]
0x180097812  imul    rcx, rax, 989680h
0x180097819  mov     r15, [rsp+0A8h+arg_8]
0x180097821  cmp     r15, rcx
0x180097824  jbe     short loc_18009782B
0x180097826  sub     r15, rcx
0x180097829  jmp     short loc_18009782E
0x18009782b  mov     r15, rsi
0x18009782e  mov     r12d, [r14+148h]
0x180097835  sub     r12d, [r14+14Ch]
0x18009783c  lea     r13, [r14+170h]
0x180097843  mov     rbx, [r13+0]
0x180097847  cmp     rbx, r13
0x18009784a  jz      loc_1800978F3
0x180097850  cmp     r12d, [r14+188h]
0x180097857  ja      short loc_180097863
0x180097859  cmp     [rbx+28h], r15
0x18009785d  jnb     loc_1800978F3
0x180097863  mov     rcx, [rbx]
0x180097866  mov     rax, [rbx+8]
0x18009786a  mov     [rcx+8], rax
0x18009786e  mov     [rax], rcx
0x180097871  mov     [rbx+10h], sil
0x180097875  mov     rax, [rsp+0A8h+var_50]
0x18009787a  lea     rcx, [rsp+0A8h+var_58]
0x18009787f  mov     [rbx], rcx
0x180097882  mov     [rbx+8], rax
0x180097886  mov     [rsp+0A8h+var_50], rbx
0x18009788b  mov     [rax], rbx
0x18009788e  mov     byte ptr [rbx+10h], 1
0x180097892  lea     rcx, [rbx+18h]; this
0x180097896  call    ?GetHashCode@RefString@DWrite@@QEBAIXZ; DWrite::RefString::GetHashCode(void)
0x18009789b  mov     r8d, eax
0x18009789e  lea     r9, [rbx+18h]
0x1800978a2  lea     rdx, [rsp+0A8h+var_88]
0x1800978a7  lea     rbx, [r14+130h]
0x1800978ae  mov     rcx, rbx
0x1800978b1  call    ?Find@?$HashTable@VRefString@DWrite@@UUserCacheReference@FontCacheServer@@@@QEBA?AViterator@1@_KAEBVRefString@DWrite@@@Z; HashTable<DWrite::RefString,FontCacheServer::UserCacheReference>::Find(unsigned __int64,DWrite::RefString const &)
0x1800978b6  mov     eax, [r14+148h]
0x1800978bd  lea     rdx, [rax+rax*2]
0x1800978c1  mov     rax, [r14+140h]
0x1800978c8  lea     rdx, [rax+rdx*8]
0x1800978cc  cmp     qword ptr [rsp+0A8h+var_88], rdx
0x1800978d1  jz      short loc_1800978EB
0x1800978d3  movaps  xmm0, [rsp+0A8h+var_88]
0x1800978d8  movdqa  [rsp+0A8h+var_78], xmm0
0x1800978de  lea     rdx, [rsp+0A8h+var_78]
0x1800978e3  mov     rcx, rbx
0x1800978e6  call    ?Remove@HashTableImpl@@QEAAXViterator@1@@Z; HashTableImpl::Remove(HashTableImpl::iterator)
0x1800978eb  dec     r12d
0x1800978ee  jmp     loc_180097843
0x1800978f3  mov     rcx, rdi; lpCriticalSection
0x1800978f6  call    cs:__imp_LeaveCriticalSection
0x1800978fc  nop
0x1800978fd  mov     rbx, [rsp+0A8h+var_58]
0x180097902  lea     rdi, [rsp+0A8h+var_58]
0x180097907  cmp     rdi, rbx
0x18009790a  jz      loc_1800979DF
0x180097910  lea     rdx, [rbx+18h]
0x180097914  lea     rcx, [rsp+0A8h+arg_10]
0x18009791c  call    ?FileNameFromSidString@ServerSidePerUserContext@@SA?AVRefString@DWrite@@AEBV23@@Z; ServerSidePerUserContext::FileNameFromSidString(DWrite::RefString const &)
0x180097921  mov     r12, rax
0x180097924  lea     rdx, [rsp+0A8h+arg_8]
0x18009792c  mov     rcx, r14
0x18009792f  call    ?GetCacheFolderPath@FontCacheServer@@QEBA?AVRefString@DWrite@@XZ; FontCacheServer::GetCacheFolderPath(void)
0x180097934  nop
0x180097935  mov     rdx, [r12]
0x180097939  mov     rcx, [rax]
0x18009793c  lea     rax, [rcx+8]
0x180097940  mov     qword ptr [rsp+0A8h+var_78], rax
0x180097945  mov     eax, [rcx+4]
0x180097948  mov     qword ptr [rsp+0A8h+var_78+8], rax
0x18009794d  lea     rax, [rdx+8]
0x180097951  mov     [rsp+0A8h+var_68], rax
0x180097956  mov     eax, [rdx+4]
0x180097959  mov     [rsp+0A8h+var_60], rax
0x18009795e  lea     rdx, [rsp+0A8h+var_78]
0x180097963  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]
0x18009796b  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x180097970  nop
0x180097971  mov     rcx, [rsp+0A8h+arg_8]; struct DWrite::RefString::Data *
0x180097979  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18009797e  nop
0x18009797f  mov     rcx, [rsp+0A8h+arg_10]; struct DWrite::RefString::Data *
0x180097987  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18009798c  mov     rcx, qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x180097994  add     rcx, 8; lpFileName
0x180097998  call    cs:__imp_DeleteFileW
0x18009799e  lea     r8, [rbx+18h]
0x1800979a2  lea     rdx, [rsp+0A8h+arg_18]
0x1800979aa  call    ?GetUserFontSetCacheFileName@FontCacheServer@@AEBA?AVRefString@DWrite@@AEBV23@@Z; FontCacheServer::GetUserFontSetCacheFileName(DWrite::RefString const &)
0x1800979af  mov     rcx, [rax]
0x1800979b2  add     rcx, 8; lpFileName
0x1800979b6  call    cs:__imp_DeleteFileW
0x1800979bc  mov     rcx, [rsp+0A8h+arg_18]; struct DWrite::RefString::Data *
0x1800979c4  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800979c9  nop
0x1800979ca  mov     rcx, qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]; struct DWrite::RefString::Data *
0x1800979d2  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800979d7  mov     rbx, [rbx]
0x1800979da  jmp     loc_180097907
0x1800979df  jmp     short loc_1800979E3
0x1800979e1  xor     esi, esi
0x1800979e3  lea     rax, [rsp+0A8h+var_58]
0x1800979e8  mov     rcx, [rsp+0A8h+var_58]; this
0x1800979ed  cmp     rcx, rax
0x1800979f0  jz      short loc_180097A10
0x1800979f2  mov     rdx, [rcx]; unsigned int
0x1800979f5  mov     rax, [rcx+8]
0x1800979f9  mov     [rdx+8], rax
0x1800979fd  mov     [rax], rdx
0x180097a00  mov     [rcx+10h], sil
0x180097a04  test    rcx, rcx
0x180097a07  jz      short loc_1800979E3
0x180097a09  call    ??_GUserCacheReference@FontCacheServer@@QEAAPEAXI@Z; FontCacheServer::UserCacheReference::`scalar deleting destructor'(uint)
0x180097a0e  jmp     short loc_1800979E3
0x180097a10  add     rsp, 70h
0x180097a14  pop     r15
0x180097a16  pop     r14
0x180097a18  pop     r13
0x180097a1a  pop     r12
0x180097a1c  pop     rdi
0x180097a1d  pop     rsi
0x180097a1e  pop     rbx
0x180097a1f  retn
```
