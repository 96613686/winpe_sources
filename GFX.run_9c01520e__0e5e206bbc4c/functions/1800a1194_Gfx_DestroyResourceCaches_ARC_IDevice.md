# Gfx::DestroyResourceCaches(ARC::IDevice &)

- ea: `0x1800a1194`
- end: `0x1800a13f6`
- name: `?DestroyResourceCaches@Gfx@@YAXAEAUIDevice@ARC@@@Z`
- size: `610`
- prototype: `void __fastcall(Gfx *__hidden this, struct ARC::IDevice *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800a0ee0`

## callees

- `0x1800578b0`
- `0x180057e70`
- `0x180076df0`
- `0x180077780`
- `0x180087d64`
- `0x1800a1194`
- `0x1800a13f8`
- `0x1800a19ac`
- `0x1800a1a44`
- `0x1800a2338`
- `0x1800a371c`
- `0x1800a7808`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800a11fe`
- `KERNEL32!GetCurrentThreadId` at `0x1800a11fe`
- `MSVCP140!_Mtx_unlock` at `0x1800a12c3`
- `MSVCP140!_Mtx_unlock` at `0x1800a133b`
- `MSVCP140!_Mtx_unlock` at `0x1800a1383`
- `MSVCP140!_Mtx_unlock` at `0x1800a13cb`
- `MSVCP140!_Mtx_unlock` at `0x1800a12c3`
- `MSVCP140!_Mtx_unlock` at `0x1800a133b`
- `MSVCP140!_Mtx_unlock` at `0x1800a1383`
- `MSVCP140!_Mtx_unlock` at `0x1800a13cb`

## string_xrefs

- `0x1800a120f`: `ThreadId`
- `0x1800a123a`: `Clearing Gfx resource caches`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Gfx::DestroyResourceCaches(Gfx *this, struct ARC::IDevice *a2)
{
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rsi
  struct _Mtx_internal_imp_t *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rsi
  struct _Mtx_internal_imp_t *v10; // rdi
  __int64 v11; // rsi
  struct _Mtx_internal_imp_t *v12; // rdi
  __int64 v13; // rdi
  struct _Mtx_internal_imp_t *v14; // rbx
  const char *v15; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v16[2]; // [rsp+48h] [rbp-41h] BYREF
  DWORD CurrentThreadId; // [rsp+58h] [rbp-31h]
  __int16 v18; // [rsp+5Ch] [rbp-2Dh]
  _OWORD v19[2]; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v20[3]; // [rsp+80h] [rbp-9h] BYREF
  __int16 v21; // [rsp+98h] [rbp+Fh]
  _OWORD v22[2]; // [rsp+A0h] [rbp+17h] BYREF

  v20[0] = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
  v20[1] = "Device address";
  v20[2] = this;
  v21 = 4;
  v22[0] = 0;
  v22[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v22[0]) = 0;
  v16[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
  v16[1] = "ThreadId";
  CurrentThreadId = GetCurrentThreadId();
  v18 = 4;
  v19[0] = 0;
  v19[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19[0]) = 0;
  v15 = "Clearing Gfx resource caches";
  Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>>(
    7198044,
    175,
    v3,
    v4,
    (__int64)&v15,
    (__int64)v16,
    (__int64)v20);
  std::wstring::~wstring(v19);
  std::wstring::~wstring(v22);
  v5 = (*(__int64 (__fastcall **)(Gfx *))(*(_QWORD *)this + 24LL))(this);
  v6 = Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::ArcTargetCache,ARC::IFactory>::CacheMap>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::ArcTargetCache,ARC::IFactory>::CacheMap>::s_pInstance >= 2 )
  {
    std::_Mutex_base::lock(Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::ArcTargetCache,ARC::IFactory>::CacheMap>::s_pInstance);
    v15 = (const char *)v5;
    std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::ArcTargetCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::ArcTargetCache>>>,0>>::erase(
      (char *)v6 + 80,
      &v15);
    _Mtx_unlock(v6);
  }
  v7 = (*(__int64 (__fastcall **)(Gfx *))(*(_QWORD *)this + 24LL))(this);
  Gfx::TResourceCacheMultitonImpl<Gfx::FadeTextureCache,ARC::IFactory>::DestroyResourceCache(v7);
  v8 = (*(__int64 (__fastcall **)(Gfx *))(*(_QWORD *)this + 24LL))(this);
  Gfx::TResourceCacheMultitonImpl<Gfx::MeshCache,ARC::IFactory>::DestroyResourceCache(v8);
  v9 = (*(__int64 (__fastcall **)(Gfx *))(*(_QWORD *)this + 24LL))(this);
  v10 = Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::QuadCache,ARC::IFactory>::CacheMap>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::QuadCache,ARC::IFactory>::CacheMap>::s_pInstance >= 2 )
  {
    std::_Mutex_base::lock(Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::QuadCache,ARC::IFactory>::CacheMap>::s_pInstance);
    v15 = (const char *)v9;
    std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::QuadCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::QuadCache>>>,0>>::erase(
      (char *)v10 + 80,
      &v15);
    _Mtx_unlock(v10);
  }
  v11 = (*(__int64 (__fastcall **)(Gfx *))(*(_QWORD *)this + 24LL))(this);
  v12 = Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::RasterizerCache,ARC::IFactory>::CacheMap>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::RasterizerCache,ARC::IFactory>::CacheMap>::s_pInstance >= 2 )
  {
    std::_Mutex_base::lock(Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::RasterizerCache,ARC::IFactory>::CacheMap>::s_pInstance);
    v15 = (const char *)v11;
    std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::RasterizerCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::RasterizerCache>>>,0>>::erase(
      (char *)v12 + 80,
      &v15);
    _Mtx_unlock(v12);
  }
  v13 = (*(__int64 (__fastcall **)(Gfx *))(*(_QWORD *)this + 24LL))(this);
  v14 = Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::SpriteCache,ARC::IFactory>::CacheMap>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::SpriteCache,ARC::IFactory>::CacheMap>::s_pInstance >= 2 )
  {
    std::_Mutex_base::lock(Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::SpriteCache,ARC::IFactory>::CacheMap>::s_pInstance);
    v15 = (const char *)v13;
    std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::SpriteCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::SpriteCache>>>,0>>::erase(
      (char *)v14 + 80,
      &v15);
    _Mtx_unlock(v14);
  }
}

```

## disassembly

```asm
0x1800a1194  mov     [rsp-8+arg_8], rbx
0x1800a1199  mov     [rsp-8+arg_10], rsi
0x1800a119e  push    rbp
0x1800a119f  push    rdi
0x1800a11a0  push    r14
0x1800a11a2  lea     rbp, [rsp-47h]
0x1800a11a7  sub     rsp, 0D0h
0x1800a11ae  mov     rax, cs:__security_cookie
0x1800a11b5  xor     rax, rsp
0x1800a11b8  mov     [rbp+57h+var_20], rax
0x1800a11bc  mov     rbx, rcx
0x1800a11bf  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x1800a11c6  mov     [rbp+57h+var_60], rax
0x1800a11ca  lea     rax, aDeviceAddress; "Device address"
0x1800a11d1  mov     [rbp+57h+var_58], rax
0x1800a11d5  mov     [rbp+57h+var_50], rcx
0x1800a11d9  mov     edi, 4
0x1800a11de  mov     [rbp+57h+var_48], di
0x1800a11e2  xorps   xmm0, xmm0
0x1800a11e5  movups  [rbp+57h+var_40], xmm0
0x1800a11e9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a11f1  movdqa  [rbp+57h+var_30], xmm1
0x1800a11f6  xor     r14d, r14d
0x1800a11f9  mov     word ptr [rbp+57h+var_40], r14w
0x1800a11fe  call    cs:__imp_GetCurrentThreadId
0x1800a1204  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800a120b  mov     [rbp+57h+var_98], rcx
0x1800a120f  lea     rcx, aThreadid_0; "ThreadId"
0x1800a1216  mov     [rbp+57h+var_90], rcx
0x1800a121a  mov     [rbp+57h+var_88], eax
0x1800a121d  mov     [rbp+57h+var_84], di
0x1800a1221  xorps   xmm0, xmm0
0x1800a1224  movups  [rbp+57h+var_80], xmm0
0x1800a1228  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a1230  movdqu  [rbp+57h+var_70], xmm1
0x1800a1235  mov     word ptr [rbp+57h+var_80], r14w
0x1800a123a  lea     rax, aClearingGfxRes; "Clearing Gfx resource caches"
0x1800a1241  mov     [rbp+57h+var_A0], rax
0x1800a1245  lea     rax, [rbp+57h+var_60]
0x1800a1249  mov     [rsp+0E0h+var_B0], rax
0x1800a124e  lea     rax, [rbp+57h+var_98]
0x1800a1252  mov     [rsp+0E0h+var_B8], rax
0x1800a1257  lea     rax, [rbp+57h+var_A0]
0x1800a125b  mov     [rsp+0E0h+var_C0], rax
0x1800a1260  mov     edx, 0AFh
0x1800a1265  mov     ecx, 6DD55Ch
0x1800a126a  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@PEBX@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@PEBX@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<void const *> &&)
0x1800a126f  lea     rcx, [rbp+57h+var_80]
0x1800a1273  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1278  lea     rcx, [rbp+57h+var_40]
0x1800a127c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1281  mov     rax, [rbx]
0x1800a1284  mov     rcx, rbx
0x1800a1287  mov     rax, [rax+18h]
0x1800a128b  call    cs:__guard_dispatch_icall_fptr
0x1800a1291  mov     rsi, rax
0x1800a1294  mov     rdi, cs:?s_pInstance@?$TSingleton@VCacheMap@?$TResourceCacheMultitonImpl@UArcTargetCache@Gfx@@UIFactory@ARC@@@Gfx@@@Ofc@@0PEAVCacheMap@?$TResourceCacheMultitonImpl@UArcTargetCache@Gfx@@UIFactory@ARC@@@Gfx@@EA; Gfx::TResourceCacheMultitonImpl<Gfx::ArcTargetCache,ARC::IFactory>::CacheMap * Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::ArcTargetCache,ARC::IFactory>::CacheMap>::s_pInstance
0x1800a129b  cmp     rdi, 1
0x1800a129f  jbe     short loc_1800A12C9
0x1800a12a1  test    rdi, rdi
0x1800a12a4  jz      short loc_1800A12C9
0x1800a12a6  mov     rcx, rdi; this
0x1800a12a9  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a12ae  mov     [rbp+57h+var_A0], rsi
0x1800a12b2  lea     rcx, [rdi+50h]
0x1800a12b6  lea     rdx, [rbp+57h+var_A0]
0x1800a12ba  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAUIFactory@ARC@@V?$unique_ptr@UArcTargetCache@Gfx@@U?$default_delete@UArcTargetCache@Gfx@@@std@@@std@@U?$less@PEAUIFactory@ARC@@@4@V?$allocator@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@UArcTargetCache@Gfx@@U?$default_delete@UArcTargetCache@Gfx@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBQEAUIFactory@ARC@@@Z; std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::ArcTargetCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::ArcTargetCache>>>,0>>::erase(ARC::IFactory * const &)
0x1800a12bf  nop
0x1800a12c0  mov     rcx, rdi; _Mtx_t
0x1800a12c3  call    cs:__imp__Mtx_unlock
0x1800a12c9  mov     rax, [rbx]
0x1800a12cc  mov     rcx, rbx
0x1800a12cf  mov     rax, [rax+18h]
0x1800a12d3  call    cs:__guard_dispatch_icall_fptr
0x1800a12d9  mov     rcx, rax
0x1800a12dc  call    ?DestroyResourceCache@?$TResourceCacheMultitonImpl@UFadeTextureCache@Gfx@@UIFactory@ARC@@@Gfx@@SA_NAEAUIFactory@ARC@@@Z; Gfx::TResourceCacheMultitonImpl<Gfx::FadeTextureCache,ARC::IFactory>::DestroyResourceCache(ARC::IFactory &)
0x1800a12e1  mov     rax, [rbx]
0x1800a12e4  mov     rcx, rbx
0x1800a12e7  mov     rax, [rax+18h]
0x1800a12eb  call    cs:__guard_dispatch_icall_fptr
0x1800a12f1  mov     rcx, rax
0x1800a12f4  call    ?DestroyResourceCache@?$TResourceCacheMultitonImpl@UMeshCache@Gfx@@UIFactory@ARC@@@Gfx@@SA_NAEAUIFactory@ARC@@@Z; Gfx::TResourceCacheMultitonImpl<Gfx::MeshCache,ARC::IFactory>::DestroyResourceCache(ARC::IFactory &)
0x1800a12f9  mov     rax, [rbx]
0x1800a12fc  mov     rcx, rbx
0x1800a12ff  mov     rax, [rax+18h]
0x1800a1303  call    cs:__guard_dispatch_icall_fptr
0x1800a1309  mov     rsi, rax
0x1800a130c  mov     rdi, cs:?s_pInstance@?$TSingleton@VCacheMap@?$TResourceCacheMultitonImpl@UQuadCache@Gfx@@UIFactory@ARC@@@Gfx@@@Ofc@@0PEAVCacheMap@?$TResourceCacheMultitonImpl@UQuadCache@Gfx@@UIFactory@ARC@@@Gfx@@EA; Gfx::TResourceCacheMultitonImpl<Gfx::QuadCache,ARC::IFactory>::CacheMap * Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::QuadCache,ARC::IFactory>::CacheMap>::s_pInstance
0x1800a1313  cmp     rdi, 1
0x1800a1317  jbe     short loc_1800A1341
0x1800a1319  test    rdi, rdi
0x1800a131c  jz      short loc_1800A1341
0x1800a131e  mov     rcx, rdi; this
0x1800a1321  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a1326  nop
0x1800a1327  mov     [rbp+57h+var_A0], rsi
0x1800a132b  lea     rcx, [rdi+50h]
0x1800a132f  lea     rdx, [rbp+57h+var_A0]
0x1800a1333  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAUIFactory@ARC@@V?$unique_ptr@UQuadCache@Gfx@@U?$default_delete@UQuadCache@Gfx@@@std@@@std@@U?$less@PEAUIFactory@ARC@@@4@V?$allocator@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@UQuadCache@Gfx@@U?$default_delete@UQuadCache@Gfx@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBQEAUIFactory@ARC@@@Z; std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::QuadCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::QuadCache>>>,0>>::erase(ARC::IFactory * const &)
0x1800a1338  mov     rcx, rdi; _Mtx_t
0x1800a133b  call    cs:__imp__Mtx_unlock
0x1800a1341  mov     rax, [rbx]
0x1800a1344  mov     rcx, rbx
0x1800a1347  mov     rax, [rax+18h]
0x1800a134b  call    cs:__guard_dispatch_icall_fptr
0x1800a1351  mov     rsi, rax
0x1800a1354  mov     rdi, cs:?s_pInstance@?$TSingleton@VCacheMap@?$TResourceCacheMultitonImpl@URasterizerCache@Gfx@@UIFactory@ARC@@@Gfx@@@Ofc@@0PEAVCacheMap@?$TResourceCacheMultitonImpl@URasterizerCache@Gfx@@UIFactory@ARC@@@Gfx@@EA; Gfx::TResourceCacheMultitonImpl<Gfx::RasterizerCache,ARC::IFactory>::CacheMap * Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::RasterizerCache,ARC::IFactory>::CacheMap>::s_pInstance
0x1800a135b  cmp     rdi, 1
0x1800a135f  jbe     short loc_1800A1389
0x1800a1361  test    rdi, rdi
0x1800a1364  jz      short loc_1800A1389
0x1800a1366  mov     rcx, rdi; this
0x1800a1369  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a136e  mov     [rbp+57h+var_A0], rsi
0x1800a1372  lea     rcx, [rdi+50h]
0x1800a1376  lea     rdx, [rbp+57h+var_A0]
0x1800a137a  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAUIFactory@ARC@@V?$unique_ptr@URasterizerCache@Gfx@@U?$default_delete@URasterizerCache@Gfx@@@std@@@std@@U?$less@PEAUIFactory@ARC@@@4@V?$allocator@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@URasterizerCache@Gfx@@U?$default_delete@URasterizerCache@Gfx@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBQEAUIFactory@ARC@@@Z; std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::RasterizerCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::RasterizerCache>>>,0>>::erase(ARC::IFactory * const &)
0x1800a137f  nop
0x1800a1380  mov     rcx, rdi; _Mtx_t
0x1800a1383  call    cs:__imp__Mtx_unlock
0x1800a1389  mov     rax, [rbx]
0x1800a138c  mov     rcx, rbx
0x1800a138f  mov     rax, [rax+18h]
0x1800a1393  call    cs:__guard_dispatch_icall_fptr
0x1800a1399  mov     rdi, rax
0x1800a139c  mov     rbx, cs:?s_pInstance@?$TSingleton@VCacheMap@?$TResourceCacheMultitonImpl@USpriteCache@Gfx@@UIFactory@ARC@@@Gfx@@@Ofc@@0PEAVCacheMap@?$TResourceCacheMultitonImpl@USpriteCache@Gfx@@UIFactory@ARC@@@Gfx@@EA; Gfx::TResourceCacheMultitonImpl<Gfx::SpriteCache,ARC::IFactory>::CacheMap * Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::SpriteCache,ARC::IFactory>::CacheMap>::s_pInstance
0x1800a13a3  cmp     rbx, 1
0x1800a13a7  jbe     short loc_1800A13D2
0x1800a13a9  test    rbx, rbx
0x1800a13ac  jz      short loc_1800A13D2
0x1800a13ae  mov     rcx, rbx; this
0x1800a13b1  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a13b6  nop
0x1800a13b7  mov     [rbp+57h+var_A0], rdi
0x1800a13bb  lea     rcx, [rbx+50h]
0x1800a13bf  lea     rdx, [rbp+57h+var_A0]
0x1800a13c3  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAUIFactory@ARC@@V?$unique_ptr@USpriteCache@Gfx@@U?$default_delete@USpriteCache@Gfx@@@std@@@std@@U?$less@PEAUIFactory@ARC@@@4@V?$allocator@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@USpriteCache@Gfx@@U?$default_delete@USpriteCache@Gfx@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBQEAUIFactory@ARC@@@Z; std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::SpriteCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::SpriteCache>>>,0>>::erase(ARC::IFactory * const &)
0x1800a13c8  mov     rcx, rbx; _Mtx_t
0x1800a13cb  call    cs:__imp__Mtx_unlock
0x1800a13d1  nop
0x1800a13d2  mov     rcx, [rbp+57h+var_20]
0x1800a13d6  xor     rcx, rsp; StackCookie
0x1800a13d9  call    __security_check_cookie
0x1800a13de  lea     r11, [rsp+0E0h+var_10]
0x1800a13e6  mov     rbx, [r11+28h]
0x1800a13ea  mov     rsi, [r11+30h]
0x1800a13ee  mov     rsp, r11
0x1800a13f1  pop     r14
0x1800a13f3  pop     rdi
0x1800a13f4  pop     rbp
0x1800a13f5  retn
```
