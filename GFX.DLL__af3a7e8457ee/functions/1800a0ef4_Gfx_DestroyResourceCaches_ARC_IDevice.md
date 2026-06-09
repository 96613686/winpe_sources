# Gfx::DestroyResourceCaches(ARC::IDevice &)

- ea: `0x1800a0ef4`
- end: `0x1800a1156`
- name: `?DestroyResourceCaches@Gfx@@YAXAEAUIDevice@ARC@@@Z`
- size: `610`
- prototype: `void __fastcall(Gfx *__hidden this, struct ARC::IDevice *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800a0c40`

## callees

- `0x180056ee0`
- `0x1800573f0`
- `0x1800795a0`
- `0x18007aa30`
- `0x180090148`
- `0x1800a0ef4`
- `0x1800a1158`
- `0x1800a11f0`
- `0x1800a17b0`
- `0x1800a2058`
- `0x1800a36d0`
- `0x1800a3c58`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800a0f5e`
- `KERNEL32!GetCurrentThreadId` at `0x1800a0f5e`
- `MSVCP140!_Mtx_unlock` at `0x1800a1023`
- `MSVCP140!_Mtx_unlock` at `0x1800a109b`
- `MSVCP140!_Mtx_unlock` at `0x1800a10e3`
- `MSVCP140!_Mtx_unlock` at `0x1800a112b`
- `MSVCP140!_Mtx_unlock` at `0x1800a1023`
- `MSVCP140!_Mtx_unlock` at `0x1800a109b`
- `MSVCP140!_Mtx_unlock` at `0x1800a10e3`
- `MSVCP140!_Mtx_unlock` at `0x1800a112b`

## string_xrefs

- `0x1800a0f6f`: `ThreadId`
- `0x1800a0f9a`: `Clearing Gfx resource caches`

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
0x1800a0ef4  mov     [rsp-8+arg_8], rbx
0x1800a0ef9  mov     [rsp-8+arg_10], rsi
0x1800a0efe  push    rbp
0x1800a0eff  push    rdi
0x1800a0f00  push    r14
0x1800a0f02  lea     rbp, [rsp-47h]
0x1800a0f07  sub     rsp, 0D0h
0x1800a0f0e  mov     rax, cs:__security_cookie
0x1800a0f15  xor     rax, rsp
0x1800a0f18  mov     [rbp+57h+var_20], rax
0x1800a0f1c  mov     rbx, rcx
0x1800a0f1f  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x1800a0f26  mov     [rbp+57h+var_60], rax
0x1800a0f2a  lea     rax, aDeviceAddress; "Device address"
0x1800a0f31  mov     [rbp+57h+var_58], rax
0x1800a0f35  mov     [rbp+57h+var_50], rcx
0x1800a0f39  mov     edi, 4
0x1800a0f3e  mov     [rbp+57h+var_48], di
0x1800a0f42  xorps   xmm0, xmm0
0x1800a0f45  movups  [rbp+57h+var_40], xmm0
0x1800a0f49  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a0f51  movdqa  [rbp+57h+var_30], xmm1
0x1800a0f56  xor     r14d, r14d
0x1800a0f59  mov     word ptr [rbp+57h+var_40], r14w
0x1800a0f5e  call    cs:__imp_GetCurrentThreadId
0x1800a0f64  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800a0f6b  mov     [rbp+57h+var_98], rcx
0x1800a0f6f  lea     rcx, aThreadid_0; "ThreadId"
0x1800a0f76  mov     [rbp+57h+var_90], rcx
0x1800a0f7a  mov     [rbp+57h+var_88], eax
0x1800a0f7d  mov     [rbp+57h+var_84], di
0x1800a0f81  xorps   xmm0, xmm0
0x1800a0f84  movups  [rbp+57h+var_80], xmm0
0x1800a0f88  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a0f90  movdqu  [rbp+57h+var_70], xmm1
0x1800a0f95  mov     word ptr [rbp+57h+var_80], r14w
0x1800a0f9a  lea     rax, aClearingGfxRes; "Clearing Gfx resource caches"
0x1800a0fa1  mov     [rbp+57h+var_A0], rax
0x1800a0fa5  lea     rax, [rbp+57h+var_60]
0x1800a0fa9  mov     [rsp+0E0h+var_B0], rax
0x1800a0fae  lea     rax, [rbp+57h+var_98]
0x1800a0fb2  mov     [rsp+0E0h+var_B8], rax
0x1800a0fb7  lea     rax, [rbp+57h+var_A0]
0x1800a0fbb  mov     [rsp+0E0h+var_C0], rax
0x1800a0fc0  mov     edx, 0AFh
0x1800a0fc5  mov     ecx, 6DD55Ch
0x1800a0fca  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@PEBX@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@PEBX@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<void const *> &&)
0x1800a0fcf  lea     rcx, [rbp+57h+var_80]
0x1800a0fd3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a0fd8  lea     rcx, [rbp+57h+var_40]
0x1800a0fdc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a0fe1  mov     rax, [rbx]
0x1800a0fe4  mov     rcx, rbx
0x1800a0fe7  mov     rax, [rax+18h]
0x1800a0feb  call    cs:__guard_dispatch_icall_fptr
0x1800a0ff1  mov     rsi, rax
0x1800a0ff4  mov     rdi, cs:?s_pInstance@?$TSingleton@VCacheMap@?$TResourceCacheMultitonImpl@UArcTargetCache@Gfx@@UIFactory@ARC@@@Gfx@@@Ofc@@0PEAVCacheMap@?$TResourceCacheMultitonImpl@UArcTargetCache@Gfx@@UIFactory@ARC@@@Gfx@@EA; Gfx::TResourceCacheMultitonImpl<Gfx::ArcTargetCache,ARC::IFactory>::CacheMap * Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::ArcTargetCache,ARC::IFactory>::CacheMap>::s_pInstance
0x1800a0ffb  cmp     rdi, 1
0x1800a0fff  jbe     short loc_1800A1029
0x1800a1001  test    rdi, rdi
0x1800a1004  jz      short loc_1800A1029
0x1800a1006  mov     rcx, rdi; this
0x1800a1009  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a100e  mov     [rbp+57h+var_A0], rsi
0x1800a1012  lea     rcx, [rdi+50h]
0x1800a1016  lea     rdx, [rbp+57h+var_A0]
0x1800a101a  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAUIFactory@ARC@@V?$unique_ptr@UArcTargetCache@Gfx@@U?$default_delete@UArcTargetCache@Gfx@@@std@@@std@@U?$less@PEAUIFactory@ARC@@@4@V?$allocator@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@UArcTargetCache@Gfx@@U?$default_delete@UArcTargetCache@Gfx@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBQEAUIFactory@ARC@@@Z; std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::ArcTargetCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::ArcTargetCache>>>,0>>::erase(ARC::IFactory * const &)
0x1800a101f  nop
0x1800a1020  mov     rcx, rdi; _Mtx_t
0x1800a1023  call    cs:__imp__Mtx_unlock
0x1800a1029  mov     rax, [rbx]
0x1800a102c  mov     rcx, rbx
0x1800a102f  mov     rax, [rax+18h]
0x1800a1033  call    cs:__guard_dispatch_icall_fptr
0x1800a1039  mov     rcx, rax
0x1800a103c  call    ?DestroyResourceCache@?$TResourceCacheMultitonImpl@UFadeTextureCache@Gfx@@UIFactory@ARC@@@Gfx@@SA_NAEAUIFactory@ARC@@@Z; Gfx::TResourceCacheMultitonImpl<Gfx::FadeTextureCache,ARC::IFactory>::DestroyResourceCache(ARC::IFactory &)
0x1800a1041  mov     rax, [rbx]
0x1800a1044  mov     rcx, rbx
0x1800a1047  mov     rax, [rax+18h]
0x1800a104b  call    cs:__guard_dispatch_icall_fptr
0x1800a1051  mov     rcx, rax
0x1800a1054  call    ?DestroyResourceCache@?$TResourceCacheMultitonImpl@UMeshCache@Gfx@@UIFactory@ARC@@@Gfx@@SA_NAEAUIFactory@ARC@@@Z; Gfx::TResourceCacheMultitonImpl<Gfx::MeshCache,ARC::IFactory>::DestroyResourceCache(ARC::IFactory &)
0x1800a1059  mov     rax, [rbx]
0x1800a105c  mov     rcx, rbx
0x1800a105f  mov     rax, [rax+18h]
0x1800a1063  call    cs:__guard_dispatch_icall_fptr
0x1800a1069  mov     rsi, rax
0x1800a106c  mov     rdi, cs:?s_pInstance@?$TSingleton@VCacheMap@?$TResourceCacheMultitonImpl@UQuadCache@Gfx@@UIFactory@ARC@@@Gfx@@@Ofc@@0PEAVCacheMap@?$TResourceCacheMultitonImpl@UQuadCache@Gfx@@UIFactory@ARC@@@Gfx@@EA; Gfx::TResourceCacheMultitonImpl<Gfx::QuadCache,ARC::IFactory>::CacheMap * Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::QuadCache,ARC::IFactory>::CacheMap>::s_pInstance
0x1800a1073  cmp     rdi, 1
0x1800a1077  jbe     short loc_1800A10A1
0x1800a1079  test    rdi, rdi
0x1800a107c  jz      short loc_1800A10A1
0x1800a107e  mov     rcx, rdi; this
0x1800a1081  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a1086  nop
0x1800a1087  mov     [rbp+57h+var_A0], rsi
0x1800a108b  lea     rcx, [rdi+50h]
0x1800a108f  lea     rdx, [rbp+57h+var_A0]
0x1800a1093  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAUIFactory@ARC@@V?$unique_ptr@UQuadCache@Gfx@@U?$default_delete@UQuadCache@Gfx@@@std@@@std@@U?$less@PEAUIFactory@ARC@@@4@V?$allocator@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@UQuadCache@Gfx@@U?$default_delete@UQuadCache@Gfx@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBQEAUIFactory@ARC@@@Z; std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::QuadCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::QuadCache>>>,0>>::erase(ARC::IFactory * const &)
0x1800a1098  mov     rcx, rdi; _Mtx_t
0x1800a109b  call    cs:__imp__Mtx_unlock
0x1800a10a1  mov     rax, [rbx]
0x1800a10a4  mov     rcx, rbx
0x1800a10a7  mov     rax, [rax+18h]
0x1800a10ab  call    cs:__guard_dispatch_icall_fptr
0x1800a10b1  mov     rsi, rax
0x1800a10b4  mov     rdi, cs:?s_pInstance@?$TSingleton@VCacheMap@?$TResourceCacheMultitonImpl@URasterizerCache@Gfx@@UIFactory@ARC@@@Gfx@@@Ofc@@0PEAVCacheMap@?$TResourceCacheMultitonImpl@URasterizerCache@Gfx@@UIFactory@ARC@@@Gfx@@EA; Gfx::TResourceCacheMultitonImpl<Gfx::RasterizerCache,ARC::IFactory>::CacheMap * Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::RasterizerCache,ARC::IFactory>::CacheMap>::s_pInstance
0x1800a10bb  cmp     rdi, 1
0x1800a10bf  jbe     short loc_1800A10E9
0x1800a10c1  test    rdi, rdi
0x1800a10c4  jz      short loc_1800A10E9
0x1800a10c6  mov     rcx, rdi; this
0x1800a10c9  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a10ce  mov     [rbp+57h+var_A0], rsi
0x1800a10d2  lea     rcx, [rdi+50h]
0x1800a10d6  lea     rdx, [rbp+57h+var_A0]
0x1800a10da  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAUIFactory@ARC@@V?$unique_ptr@URasterizerCache@Gfx@@U?$default_delete@URasterizerCache@Gfx@@@std@@@std@@U?$less@PEAUIFactory@ARC@@@4@V?$allocator@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@URasterizerCache@Gfx@@U?$default_delete@URasterizerCache@Gfx@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBQEAUIFactory@ARC@@@Z; std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::RasterizerCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::RasterizerCache>>>,0>>::erase(ARC::IFactory * const &)
0x1800a10df  nop
0x1800a10e0  mov     rcx, rdi; _Mtx_t
0x1800a10e3  call    cs:__imp__Mtx_unlock
0x1800a10e9  mov     rax, [rbx]
0x1800a10ec  mov     rcx, rbx
0x1800a10ef  mov     rax, [rax+18h]
0x1800a10f3  call    cs:__guard_dispatch_icall_fptr
0x1800a10f9  mov     rdi, rax
0x1800a10fc  mov     rbx, cs:?s_pInstance@?$TSingleton@VCacheMap@?$TResourceCacheMultitonImpl@USpriteCache@Gfx@@UIFactory@ARC@@@Gfx@@@Ofc@@0PEAVCacheMap@?$TResourceCacheMultitonImpl@USpriteCache@Gfx@@UIFactory@ARC@@@Gfx@@EA; Gfx::TResourceCacheMultitonImpl<Gfx::SpriteCache,ARC::IFactory>::CacheMap * Ofc::TSingleton<Gfx::TResourceCacheMultitonImpl<Gfx::SpriteCache,ARC::IFactory>::CacheMap>::s_pInstance
0x1800a1103  cmp     rbx, 1
0x1800a1107  jbe     short loc_1800A1132
0x1800a1109  test    rbx, rbx
0x1800a110c  jz      short loc_1800A1132
0x1800a110e  mov     rcx, rbx; this
0x1800a1111  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a1116  nop
0x1800a1117  mov     [rbp+57h+var_A0], rdi
0x1800a111b  lea     rcx, [rbx+50h]
0x1800a111f  lea     rdx, [rbp+57h+var_A0]
0x1800a1123  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAUIFactory@ARC@@V?$unique_ptr@USpriteCache@Gfx@@U?$default_delete@USpriteCache@Gfx@@@std@@@std@@U?$less@PEAUIFactory@ARC@@@4@V?$allocator@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@USpriteCache@Gfx@@U?$default_delete@USpriteCache@Gfx@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBQEAUIFactory@ARC@@@Z; std::_Tree<std::_Tmap_traits<ARC::IFactory *,std::unique_ptr<Gfx::SpriteCache>,std::less<ARC::IFactory *>,std::allocator<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::SpriteCache>>>,0>>::erase(ARC::IFactory * const &)
0x1800a1128  mov     rcx, rbx; _Mtx_t
0x1800a112b  call    cs:__imp__Mtx_unlock
0x1800a1131  nop
0x1800a1132  mov     rcx, [rbp+57h+var_20]
0x1800a1136  xor     rcx, rsp; StackCookie
0x1800a1139  call    __security_check_cookie
0x1800a113e  lea     r11, [rsp+0E0h+var_10]
0x1800a1146  mov     rbx, [r11+28h]
0x1800a114a  mov     rsi, [r11+30h]
0x1800a114e  mov     rsp, r11
0x1800a1151  pop     r14
0x1800a1153  pop     rdi
0x1800a1154  pop     rbp
0x1800a1155  retn
```
