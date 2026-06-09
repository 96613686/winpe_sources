# FontCacheServer::GetPerUserContext(DWrite::RefString const &)

- ea: `0x18002a37c`
- end: `0x18002a757`
- name: `?GetPerUserContext@FontCacheServer@@AEAA?AV?$ComPtr@VServerSidePerUserContext@@@@AEBVRefString@DWrite@@@Z`
- size: `987`
- prototype: `__int64 __fastcall(FontCacheServer *this)`
- caller_count: `6`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b9a0`
- `0x18000bfa0`
- `0x18002a200`
- `0x18002bee0`
- `0x1800b1e70`
- `0x1800b1f10`

## callees

- `0x18000bc70`
- `0x180010ca0`
- `0x180028c50`
- `0x18002a37c`
- `0x18002b670`
- `0x18002bb98`
- `0x18004d664`
- `0x180067cbc`
- `0x1800688d0`
- `0x180068cc0`
- `0x1800987a0`
- `0x18009a364`
- `0x18009b3b0`
- `0x1800a4b4c`
- `0x1800a7c6c`
- `0x1800aaa58`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a4c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a4c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a3d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a3d8`

## string_xrefs

- `0x18002a585`: `UserCacheSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall FontCacheServer::GetPerUserContext(struct IDWriteFontFileLoader **this, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // r15
  FontCacheServer *v5; // rsi
  struct ISessionFontSetManager *v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  char *v8; // r13
  struct ISessionFontSetManager *v9; // r8
  __int64 v10; // rdx
  int v11; // eax
  unsigned int i; // eax
  __int64 v13; // r12
  char *v14; // r14
  char *v15; // rax
  volatile signed __int32 **v16; // r12
  struct IFontSetCache *v18; // rbx
  struct IFontSetCache *v19; // r14
  struct ServerSideFontFaceContext *v20; // rsi
  SessionFontSetManager *v21; // rax
  struct ISessionFontSetManager *v22; // rax
  ServerSidePerUserContext *v23; // r15
  struct ServerSideFontFaceContext *v24; // rsi
  struct IDWriteFontFileLoader *v25; // r14
  volatile signed __int32 **CacheFolderPath; // rax
  ServerSidePerUserContext *v27; // rax
  ServerSidePerUserContext *v28; // rsi
  volatile signed __int32 *v29; // rcx
  volatile signed __int32 *v30; // rcx
  volatile signed __int32 **v31; // rax
  volatile signed __int32 ***v32; // rax
  _OWORD *v33; // rbx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  struct IFontSetCache *v36; // [rsp+50h] [rbp-21h] BYREF
  struct DWrite::RefString::Data *v37; // [rsp+58h] [rbp-19h] BYREF
  char *v38; // [rsp+60h] [rbp-11h]
  char *v39; // [rsp+68h] [rbp-9h]
  char *v40; // [rsp+70h] [rbp-1h]
  ServerSidePerUserContext *v41; // [rsp+78h] [rbp+7h] BYREF
  __int64 v44; // [rsp+E8h] [rbp+77h] BYREF
  struct ISessionFontSetManager *v45; // [rsp+F0h] [rbp+7Fh]

  v44 = a3;
  v4 = a2;
  v5 = (FontCacheServer *)this;
  v6 = (struct ISessionFontSetManager *)HashBlob(
                                          (const void *)(*(_QWORD *)a3 + 8LL),
                                          2LL * *(unsigned int *)(*(_QWORD *)a3 + 4LL),
                                          *(_DWORD *)(*(_QWORD *)a3 + 4LL));
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 264);
  v40 = (char *)v5 + 264;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 264));
  v8 = (char *)v5 + 304;
  v9 = (struct ISessionFontSetManager *)(unsigned int)v6;
  v45 = v6;
  v10 = *((_QWORD *)v5 + 40) + 24LL * *((unsigned int *)v5 + 82);
  v36 = (struct IFontSetCache *)v10;
  v11 = *((_DWORD *)v5 + 78);
  if ( v11 )
  {
    for ( i = *(_DWORD *)(*(_QWORD *)v8 + 4LL * ((unsigned int)v6 & (v11 - 1))); ; i = *(_DWORD *)(v13 + 16) )
    {
      if ( !i )
      {
        v10 = (__int64)v36;
        goto LABEL_15;
      }
      if ( i > *((_DWORD *)v5 + 82) )
        break;
      v10 = 3LL * (i - 1);
      v13 = *((_QWORD *)v5 + 40) + 24LL * (i - 1);
      if ( v9 == *(struct ISessionFontSetManager **)v13 )
      {
        if ( (unsigned __int8)HashTable<DWrite::RefString,FontCacheServer::UserCacheReference>::IsEqualKeyWrapper(
                                a3,
                                *(_QWORD *)(v13 + 8)) )
          goto LABEL_7;
        v9 = v45;
      }
    }
    FailAssert(0x53u, (const char *)v10);
    goto LABEL_30;
  }
LABEL_15:
  v13 = v10;
LABEL_7:
  if ( v13 == *((_QWORD *)v5 + 40) + 24LL * *((unsigned int *)v5 + 82) )
  {
LABEL_30:
    v33 = operator new(0x30u);
    *v33 = 0;
    v33[1] = 0;
    v33[2] = 0;
    *((_QWORD *)v33 + 3) = &DWrite::RefString::empty_;
    v36 = (struct IFontSetCache *)v33;
    DWrite::RefString::operator=((char *)v33 + 24, a3);
    v13 = *(_QWORD *)HashTableImpl::Add((char *)v5 + 304, &v41, v45, v33);
    v36 = 0;
    v34 = *((_QWORD *)v5 + 46);
    v35 = *(_QWORD **)(v34 + 8);
    *(_QWORD *)v33 = v34;
    *((_QWORD *)v33 + 1) = v35;
    *(_QWORD *)(v34 + 8) = v33;
    *v35 = v33;
    *((_BYTE *)v33 + 16) = 1;
    ScopedPtr<FontCacheServer::UserCacheReference>::~ScopedPtr<FontCacheServer::UserCacheReference>(&v36);
  }
  v14 = (char *)v5 + 344;
  v38 = (char *)v5 + 344;
  v15 = (char *)*((_QWORD *)v5 + 43);
  v39 = v15;
  v16 = *(volatile signed __int32 ***)(v13 + 8);
  if ( !v16[4] )
  {
    FontCacheServer::CreateUserFontSetCache(v5, &v36, v44);
    v18 = v36;
    (*(void (__fastcall **)(struct IFontSetCache *))(*(_QWORD *)v36 + 32LL))(v36);
    v19 = (struct IFontSetCache *)*((_QWORD *)v5 + 10);
    v20 = (struct ServerSideFontFaceContext *)*((_QWORD *)v5 + 9);
    v21 = (SessionFontSetManager *)operator new(0xC0u);
    v22 = SessionFontSetManager::SessionFontSetManager(v21, v20, v19, v18);
    v45 = v22;
    if ( v22 )
      (*(void (__fastcall **)(struct ISessionFontSetManager *))(*(_QWORD *)v22 + 8LL))(v22);
    v23 = (ServerSidePerUserContext *)operator new(0x278u);
    v41 = v23;
    v24 = this[9];
    v25 = this[8];
    v44 = GetCacheSize(L"UserCacheSize", 0x800000u, &g_userCacheSize) | 0x125C00000000LL;
    CacheFolderPath = (volatile signed __int32 **)FontCacheServer::GetCacheFolderPath((__int64)this, (__int64)&v37);
    v27 = ServerSidePerUserContext::ServerSidePerUserContext(
            v23,
            CacheFolderPath,
            (const struct CacheGrowthPolicy *)&v44,
            v25,
            v16 + 3,
            v24,
            v45,
            (struct ScheduleCloseCacheContextWorkCallback *)(this + 51));
    v28 = v27;
    if ( v27 )
      (*(void (__fastcall **)(ServerSidePerUserContext *))(*(_QWORD *)v27 + 8LL))(v27);
    v29 = v16[4];
    v16[4] = (volatile signed __int32 *)v28;
    if ( v29 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
    DWrite::RefString::DecrementRef(v37);
    v16[5] = (volatile signed __int32 *)*((_QWORD *)v16[4] + 76);
    v30 = *v16;
    v31 = (volatile signed __int32 **)v16[1];
    *((_QWORD *)v30 + 1) = v31;
    *v31 = v30;
    *((_BYTE *)v16 + 16) = 0;
    v14 = v38;
    v32 = (volatile signed __int32 ***)*((_QWORD *)v38 + 1);
    *v16 = (volatile signed __int32 *)v38;
    v16[1] = (volatile signed __int32 *)v32;
    *((_QWORD *)v14 + 1) = v16;
    *v32 = v16;
    *((_BYTE *)v16 + 16) = 1;
    if ( v45 )
      (*(void (__fastcall **)(struct ISessionFontSetManager *))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v18 )
      (*(void (__fastcall **)(struct IFontSetCache *))(*(_QWORD *)v18 + 16LL))(v18);
    v5 = (FontCacheServer *)this;
    v4 = a2;
    v15 = v39;
  }
  if ( (v15 == v14 || (unsigned int)(*((_DWORD *)v8 + 6) - *((_DWORD *)v8 + 7)) > *((_DWORD *)v5 + 98))
    && *((FontCacheServer **)v5 + 46) != (FontCacheServer *)((char *)v5 + 368) )
  {
    FontCacheServer::ScheduleCloseCacheContextWork(v5);
  }
  *v4 = v16[4];
  ComPtr<FileCleanup>::AddRef(v4);
  LeaveCriticalSection(v7);
  return v4;
}

```

## disassembly

```asm
0x18002a37c  mov     rax, rsp
0x18002a37f  mov     [rax+18h], r8
0x18002a383  mov     [rax+10h], rdx
0x18002a387  mov     [rax+8], rcx
0x18002a38b  push    rbp
0x18002a38c  push    rbx
0x18002a38d  push    rsi
0x18002a38e  push    rdi
0x18002a38f  push    r12
0x18002a391  push    r13
0x18002a393  push    r14
0x18002a395  push    r15
0x18002a397  lea     rbp, [rax-5Fh]
0x18002a39b  sub     rsp, 88h
0x18002a3a2  mov     r14, r8
0x18002a3a5  mov     r15, rdx
0x18002a3a8  mov     rsi, rcx
0x18002a3ab  mov     [rbp+57h+var_80], 0
0x18002a3b2  mov     rcx, [r8]
0x18002a3b5  mov     r8d, [rcx+4]; unsigned int
0x18002a3b9  mov     edx, r8d
0x18002a3bc  add     rdx, rdx; unsigned __int64
0x18002a3bf  add     rcx, 8; void *
0x18002a3c3  call    ?HashBlob@@YAIPEBX_KI@Z; HashBlob(void const *,unsigned __int64,uint)
0x18002a3c8  mov     ebx, eax
0x18002a3ca  lea     rdi, [rsi+108h]
0x18002a3d1  mov     [rbp+57h+var_58], rdi
0x18002a3d5  mov     rcx, rdi; lpCriticalSection
0x18002a3d8  call    cs:__imp_EnterCriticalSection
0x18002a3de  nop
0x18002a3df  lea     r13, [rsi+130h]
0x18002a3e6  mov     r8d, ebx
0x18002a3e9  mov     [rbp+57h+arg_18], rbx
0x18002a3ed  mov     eax, [r13+18h]
0x18002a3f1  lea     rcx, [rax+rax*2]
0x18002a3f5  mov     rax, [r13+10h]
0x18002a3f9  lea     rdx, [rax+rcx*8]; char *
0x18002a3fd  mov     [rbp+57h+var_78], rdx
0x18002a401  mov     eax, [r13+8]
0x18002a405  test    eax, eax
0x18002a407  jz      loc_18002A4F1
0x18002a40d  lea     ecx, [rax-1]
0x18002a410  and     rcx, rbx
0x18002a413  mov     rax, [r13+0]
0x18002a417  mov     eax, [rax+rcx*4]
0x18002a41a  test    eax, eax
0x18002a41c  jz      loc_18002A4ED
0x18002a422  cmp     eax, [r13+18h]
0x18002a426  ja      loc_18002A6CD
0x18002a42c  dec     eax
0x18002a42e  lea     rdx, [rax+rax*2]
0x18002a432  mov     rax, [r13+10h]
0x18002a436  lea     r12, [rax+rdx*8]
0x18002a43a  cmp     r8, [r12]
0x18002a43e  jnz     loc_18002A4E3
0x18002a444  mov     rdx, [r12+8]
0x18002a449  mov     rcx, r14
0x18002a44c  call    ?IsEqualKeyWrapper@?$HashTable@VRefString@DWrite@@UUserCacheReference@FontCacheServer@@@@CA_NPEBX0@Z; HashTable<DWrite::RefString,FontCacheServer::UserCacheReference>::IsEqualKeyWrapper(void const *,void const *)
0x18002a451  test    al, al
0x18002a453  jz      loc_18002A4DF
0x18002a459  mov     eax, [r13+18h]
0x18002a45d  lea     rcx, [rax+rax*2]
0x18002a461  mov     rax, [r13+10h]
0x18002a465  lea     rdx, [rax+rcx*8]
0x18002a469  cmp     r12, rdx
0x18002a46c  jz      loc_18002A6D8
0x18002a472  lea     r14, [rsi+158h]
0x18002a479  mov     [rbp+57h+var_68], r14
0x18002a47d  mov     rax, [r14]
0x18002a480  mov     [rbp+57h+var_60], rax
0x18002a484  mov     r12, [r12+8]
0x18002a489  cmp     qword ptr [r12+20h], 0
0x18002a48f  jz      short loc_18002A4F9
0x18002a491  cmp     rax, r14
0x18002a494  jz      loc_18002A6B0
0x18002a49a  mov     eax, [r13+18h]
0x18002a49e  sub     eax, [r13+1Ch]
0x18002a4a2  cmp     eax, [rsi+188h]
0x18002a4a8  ja      loc_18002A6B0
0x18002a4ae  mov     rax, [r12+20h]
0x18002a4b3  mov     [r15], rax
0x18002a4b6  mov     rcx, r15
0x18002a4b9  call    ?AddRef@?$ComPtr@VFileCleanup@@@@AEBAXXZ; ComPtr<FileCleanup>::AddRef(void)
0x18002a4be  nop
0x18002a4bf  mov     rcx, rdi; lpCriticalSection
0x18002a4c2  call    cs:__imp_LeaveCriticalSection
0x18002a4c8  mov     rax, r15
0x18002a4cb  add     rsp, 88h
0x18002a4d2  pop     r15
0x18002a4d4  pop     r14
0x18002a4d6  pop     r13
0x18002a4d8  pop     r12
0x18002a4da  pop     rdi
0x18002a4db  pop     rsi
0x18002a4dc  pop     rbx
0x18002a4dd  pop     rbp
0x18002a4de  retn
0x18002a4df  mov     r8, [rbp+57h+arg_18]
0x18002a4e3  mov     eax, [r12+10h]
0x18002a4e8  jmp     loc_18002A41A
0x18002a4ed  mov     rdx, [rbp+57h+var_78]
0x18002a4f1  mov     r12, rdx
0x18002a4f4  jmp     loc_18002A459
0x18002a4f9  mov     r8, [rbp+57h+arg_10]
0x18002a4fd  lea     rdx, [rbp+57h+var_78]
0x18002a501  mov     rcx, rsi
0x18002a504  call    ?CreateUserFontSetCache@FontCacheServer@@AEBA?AV?$ComPtr@UIFontSetCache@@@@AEBVRefString@DWrite@@@Z; FontCacheServer::CreateUserFontSetCache(DWrite::RefString const &)
0x18002a509  nop
0x18002a50a  mov     rbx, [rbp+57h+var_78]
0x18002a50e  mov     rax, [rbx]
0x18002a511  mov     rcx, rbx
0x18002a514  mov     rax, [rax+20h]
0x18002a518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a51d  mov     r14, [rsi+50h]
0x18002a521  mov     rsi, [rsi+48h]
0x18002a525  mov     ecx, 0C0h; Size
0x18002a52a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a52f  mov     r9, rbx; struct IFontSetCache *
0x18002a532  mov     r8, r14; struct IFontSetCache *
0x18002a535  mov     rdx, rsi; struct ServerSideFontFaceContext *
0x18002a538  mov     rcx, rax; this
0x18002a53b  call    ??0SessionFontSetManager@@AEAA@PEAVServerSideFontFaceContext@@PEAUIFontSetCache@@1@Z; SessionFontSetManager::SessionFontSetManager(ServerSideFontFaceContext *,IFontSetCache *,IFontSetCache *)
0x18002a540  mov     rdx, rax
0x18002a543  mov     [rbp+57h+arg_18], rax
0x18002a547  test    rax, rax
0x18002a54a  jz      short loc_18002A55C
0x18002a54c  mov     rcx, [rax]
0x18002a54f  mov     rax, [rcx+8]
0x18002a553  mov     rcx, rdx
0x18002a556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a55b  nop
0x18002a55c  mov     ecx, 278h; Size
0x18002a561  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a566  mov     r15, rax
0x18002a569  mov     [rbp+57h+var_50], rax
0x18002a56d  mov     rax, [rbp+57h+arg_0]
0x18002a571  mov     rsi, [rax+48h]
0x18002a575  mov     r14, [rax+40h]
0x18002a579  lea     r8, ?g_userCacheSize@@3IA; unsigned int *
0x18002a580  mov     edx, 800000h; unsigned int
0x18002a585  lea     rcx, ?FontCacheServiceUserCacheSizeValue@@3QB_WB; "UserCacheSize"
0x18002a58c  call    ?GetCacheSize@@YAIPEB_WIAEAI@Z; GetCacheSize(wchar_t const *,uint,uint &)
0x18002a591  mov     dword ptr [rbp+57h+arg_10], eax
0x18002a594  mov     dword ptr [rbp+57h+arg_10+4], 125Ch
0x18002a59b  mov     rcx, [rbp+57h+arg_10]
0x18002a59f  mov     [rbp+57h+arg_10], rcx
0x18002a5a3  lea     rdx, [rbp+57h+var_70]
0x18002a5a7  mov     rcx, [rbp+57h+arg_0]
0x18002a5ab  call    ?GetCacheFolderPath@FontCacheServer@@QEBA?AVRefString@DWrite@@XZ; FontCacheServer::GetCacheFolderPath(void)
0x18002a5b0  nop
0x18002a5b1  mov     [rbp+57h+var_80], 5
0x18002a5b8  mov     rcx, [rbp+57h+arg_0]
0x18002a5bc  add     rcx, 198h
0x18002a5c3  lea     rdx, [r12+18h]
0x18002a5c8  mov     [rsp+38h], rcx; struct ScheduleCloseCacheContextWorkCallback *
0x18002a5cd  mov     rcx, [rbp+57h+arg_18]
0x18002a5d1  mov     [rsp+0C0h+var_90], rcx; struct ISessionFontSetManager *
0x18002a5d6  mov     [rsp+0C0h+var_98], rsi; struct ServerSideFontFaceContext *
0x18002a5db  mov     [rsp+0C0h+var_A0], rdx; struct DWrite::RefString *
0x18002a5e0  mov     r9, r14; struct IDWriteFontFileLoader *
0x18002a5e3  lea     r8, [rbp+57h+arg_10]; struct CacheGrowthPolicy *
0x18002a5e7  mov     rdx, rax; struct DWrite::RefString *
0x18002a5ea  mov     rcx, r15; this
0x18002a5ed  call    ??0ServerSidePerUserContext@@QEAA@AEBVRefString@DWrite@@AEBUCacheGrowthPolicy@@PEAUIDWriteFontFileLoader@@0PEAVServerSideFontFaceContext@@PEAUISessionFontSetManager@@AEAUScheduleCloseCacheContextWorkCallback@@@Z; ServerSidePerUserContext::ServerSidePerUserContext(DWrite::RefString const &,CacheGrowthPolicy const &,IDWriteFontFileLoader *,DWrite::RefString const &,ServerSideFontFaceContext *,ISessionFontSetManager *,ScheduleCloseCacheContextWorkCallback &)
0x18002a5f2  mov     rsi, rax
0x18002a5f5  test    rax, rax
0x18002a5f8  jz      short loc_18002A60A
0x18002a5fa  mov     rcx, [rax]
0x18002a5fd  mov     rax, [rcx+8]
0x18002a601  mov     rcx, rsi
0x18002a604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a609  nop
0x18002a60a  mov     rcx, [r12+20h]
0x18002a60f  mov     [r12+20h], rsi
0x18002a614  test    rcx, rcx
0x18002a617  jz      short loc_18002A626
0x18002a619  mov     rax, [rcx]
0x18002a61c  mov     rax, [rax+10h]
0x18002a620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a625  nop
0x18002a626  mov     rcx, [rbp+57h+var_70]; struct DWrite::RefString::Data *
0x18002a62a  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18002a62f  mov     rax, [r12+20h]
0x18002a634  mov     rcx, [rax+260h]
0x18002a63b  mov     [r12+28h], rcx
0x18002a640  mov     rcx, [r12]
0x18002a644  mov     rax, [r12+8]
0x18002a649  mov     [rcx+8], rax
0x18002a64d  mov     [rax], rcx
0x18002a650  mov     byte ptr [r12+10h], 0
0x18002a656  mov     r14, [rbp+57h+var_68]
0x18002a65a  mov     rax, [r14+8]
0x18002a65e  mov     [r12], r14
0x18002a662  mov     [r12+8], rax
0x18002a667  mov     [r14+8], r12
0x18002a66b  mov     [rax], r12
0x18002a66e  mov     byte ptr [r12+10h], 1
0x18002a674  mov     rcx, [rbp+57h+arg_18]
0x18002a678  test    rcx, rcx
0x18002a67b  jz      short loc_18002A68A
0x18002a67d  mov     rax, [rcx]
0x18002a680  mov     rax, [rax+10h]
0x18002a684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a689  nop
0x18002a68a  test    rbx, rbx
0x18002a68d  jz      short loc_18002A69F
0x18002a68f  mov     rax, [rbx]
0x18002a692  mov     rcx, rbx
0x18002a695  mov     rax, [rax+10h]
0x18002a699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a69e  nop
0x18002a69f  mov     rsi, [rbp+57h+arg_0]
0x18002a6a3  mov     r15, [rbp+57h+arg_8]
0x18002a6a7  mov     rax, [rbp+57h+var_60]
0x18002a6ab  jmp     loc_18002A491
0x18002a6b0  lea     rax, [rsi+170h]
0x18002a6b7  cmp     [rax], rax
0x18002a6ba  jz      loc_18002A4AE
0x18002a6c0  mov     rcx, rsi; this
0x18002a6c3  call    ?ScheduleCloseCacheContextWork@FontCacheServer@@QEAAXXZ; FontCacheServer::ScheduleCloseCacheContextWork(void)
0x18002a6c8  jmp     loc_18002A4AE
0x18002a6cd  mov     ecx, 53h ; 'S'; unsigned int
0x18002a6d2  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x18002a6d7  nop
0x18002a6d8  mov     ecx, 30h ; '0'; Size
0x18002a6dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a6e2  mov     rbx, rax
0x18002a6e5  xorps   xmm0, xmm0
0x18002a6e8  movups  xmmword ptr [rax], xmm0
0x18002a6eb  movups  xmmword ptr [rax+10h], xmm0
0x18002a6ef  movups  xmmword ptr [rax+20h], xmm0
0x18002a6f3  lea     rcx, [rax+18h]
0x18002a6f7  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18002a6fe  mov     [rcx], rax
0x18002a701  mov     [rbp+57h+var_78], rbx
0x18002a705  mov     rdx, r14
0x18002a708  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x18002a70d  mov     r9, rbx
0x18002a710  mov     r8, [rbp+57h+arg_18]
0x18002a714  lea     rdx, [rbp+57h+var_50]
0x18002a718  mov     rcx, r13
0x18002a71b  call    ?Add@HashTableImpl@@QEAA?AViterator@1@_KPEAX@Z; HashTableImpl::Add(unsigned __int64,void *)
0x18002a720  mov     r12, [rax]
0x18002a723  mov     [rbp+57h+var_78], 0
0x18002a72b  mov     rcx, [rsi+170h]
0x18002a732  mov     rax, [rcx+8]
0x18002a736  mov     [rbx], rcx
0x18002a739  mov     [rbx+8], rax
0x18002a73d  mov     [rcx+8], rbx
0x18002a741  mov     [rax], rbx
0x18002a744  mov     byte ptr [rbx+10h], 1
0x18002a748  lea     rcx, [rbp+57h+var_78]
0x18002a74c  call    ??1?$ScopedPtr@UUserCacheReference@FontCacheServer@@@@QEAA@XZ; ScopedPtr<FontCacheServer::UserCacheReference>::~ScopedPtr<FontCacheServer::UserCacheReference>(void)
0x18002a751  jmp     loc_18002A472
```
