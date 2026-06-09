# Cache::Cache::InsertResource(Cache::IResourceKey const &,Mso::IRefCounted &)

- ea: `0x18000e880`
- end: `0x18000ef20`
- name: `?InsertResource@Cache@1@QEAAXAEBUIResourceKey@1@AEAUIRefCounted@Mso@@@Z`
- size: `1696`
- prototype: `void __fastcall(Cache::Cache *__hidden this, const struct Cache::IResourceKey *, struct Mso::IRefCounted *)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180007354`
- `0x18000e5d8`

## callees

- `0x1800074c0`
- `0x180009510`
- `0x1800097a0`
- `0x18000d6bc`
- `0x18000d7e0`
- `0x18000d920`
- `0x18000da20`
- `0x18000e36c`
- `0x18000e880`
- `0x18000ef20`
- `0x18000f1b0`
- `0x18000f790`
- `0x18001f854`
- `0x180021624`
- `0x180022fc0`
- `0x1800578b0`
- `0x180057e70`
- `0x180077780`
- `0x1800963c0`
- `0x180096404`
- `0x1801fff14`
- `0x1801fffb0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000ec87`
- `KERNEL32!GetCurrentThreadId` at `0x18000ee28`
- `KERNEL32!GetCurrentThreadId` at `0x18000ec87`
- `KERNEL32!GetCurrentThreadId` at `0x18000ee28`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18000eaee`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18000eaee`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x18000ea30`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x18000ea30`

## string_xrefs

- `0x18000ec91`: `threadID`
- `0x18000ee32`: `threadID`
- `0x18000e913`: `KeyHolder copy ctor should not set m_pKeyVal as null`
- `0x18000eccb`: `cacheType`
- `0x18000ee6c`: `cacheType`
- `0x18000ebbd`: `objectMemSizeBytes`
- `0x18000ecfe`: `Gfx::Cache::Insert`
- `0x18000ee9f`: `Gfx::Cache::Insert`
- `0x18000ec67`: `newCacheObjectCount`
- `0x18000ee08`: `newCacheObjectCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Cache::Cache::InsertResource(
        DWORD *this,
        const struct Cache::IResourceKey *a2,
        struct Mso::IRefCounted *a3)
{
  const struct Cache::IResourceKey *v4; // rbx
  Cache::IResourceKey **v6; // rax
  Cache::IResourceKey *v7; // rdi
  __int64 v8; // rbx
  void (__fastcall *v9)(Cache::IResourceKey *__hidden); // rax
  DWORD v10; // r12d
  __int64 v11; // rbx
  bool v12; // al
  unsigned __int64 (__fastcall *v13)(GEL::MipmapInstanceCacheKey *__hidden); // rax
  unsigned __int64 v14; // rax
  __int64 v15; // r9
  GEL::MipmapInstanceCacheKey *v16; // rcx
  void (__fastcall *v17)(Cache::IResourceKey *__hidden); // rax
  const struct Cache::IResourceState *CachedResourceStateForObject; // rax
  GEL::MipmapInstanceCacheKey *v19; // rsi
  const struct Cache::IResourceState *v20; // rax
  __int64 (__fastcall *v21)(GEL::MipmapInstanceCacheKey *); // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  __m128i si128; // xmm6
  DWORD CurrentThreadId; // eax
  __int64 v26; // rax
  int v27; // edx
  int v28; // r8d
  int v29; // r9d
  __int128 *v30; // rcx
  __m128i v31; // xmm6
  DWORD v32; // eax
  DWORD v33; // eax
  __int64 v34; // rax
  int v35; // edx
  int v36; // r8d
  int v37; // r9d
  void **v38; // [rsp+68h] [rbp-A0h] BYREF
  GEL::MipmapInstanceCacheKey *v39; // [rsp+70h] [rbp-98h]
  _QWORD v40[2]; // [rsp+78h] [rbp-90h] BYREF
  void *v41; // [rsp+88h] [rbp-80h] BYREF
  Cache::IResourceKey *v42; // [rsp+90h] [rbp-78h]
  __int64 v43; // [rsp+98h] [rbp-70h] BYREF
  void **v44; // [rsp+A0h] [rbp-68h] BYREF
  const char *v45; // [rsp+A8h] [rbp-60h]
  DWORD v46; // [rsp+B0h] [rbp-58h]
  __int16 v47; // [rsp+B4h] [rbp-54h]
  __int128 v48; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v49; // [rsp+C8h] [rbp-40h]
  void **v50; // [rsp+D8h] [rbp-30h] BYREF
  const char *v51; // [rsp+E0h] [rbp-28h]
  int v52; // [rsp+E8h] [rbp-20h]
  __int16 v53; // [rsp+ECh] [rbp-1Ch]
  __int128 v54; // [rsp+F0h] [rbp-18h] BYREF
  __m128i v55; // [rsp+100h] [rbp-8h]
  void **v56; // [rsp+110h] [rbp+8h] BYREF
  const char *v57; // [rsp+118h] [rbp+10h]
  DWORD v58; // [rsp+120h] [rbp+18h]
  __int16 v59; // [rsp+124h] [rbp+1Ch]
  __int128 v60; // [rsp+128h] [rbp+20h] BYREF
  __m128i v61; // [rsp+138h] [rbp+30h]
  void **v62; // [rsp+148h] [rbp+40h] BYREF
  const char *v63; // [rsp+150h] [rbp+48h]
  struct Mso::IRefCounted *v64; // [rsp+158h] [rbp+50h]
  __int16 v65; // [rsp+160h] [rbp+58h]
  __int128 v66; // [rsp+168h] [rbp+60h] BYREF
  __m128i v67; // [rsp+178h] [rbp+70h]
  void **v68; // [rsp+188h] [rbp+80h] BYREF
  const char *v69; // [rsp+190h] [rbp+88h]
  __int64 v70; // [rsp+198h] [rbp+90h]
  __int16 v71; // [rsp+1A0h] [rbp+98h]
  __int128 v72; // [rsp+1A8h] [rbp+A0h] BYREF
  __m128i v73; // [rsp+1B8h] [rbp+B0h]
  _QWORD v74[3]; // [rsp+1C8h] [rbp+C0h] BYREF
  __int16 v75; // [rsp+1E0h] [rbp+D8h]
  _OWORD v76[2]; // [rsp+1E8h] [rbp+E0h] BYREF

  v4 = a2;
  LOBYTE(a2) = 1;
  Cache::CacheManager::AcquireLock(&v43, a2);
  Cache::KeyHolder::KeyHolder((Cache::KeyHolder *)&v38, v4);
  v41 = &Cache::KeyHolder::`vftable';
  v6 = (Cache::IResourceKey **)(*(__int64 (__fastcall **)(GEL::MipmapInstanceCacheKey *, _QWORD *))(*(_QWORD *)v39 + 8LL))(
                                 v39,
                                 v40);
  v7 = *v6;
  *v6 = 0;
  v42 = v7;
  if ( v40[0] )
    (**(void (__fastcall ***)(_QWORD, __int64))v40[0])(v40[0], 1);
  v40[0] = "KeyHolder copy ctor should not set m_pKeyVal as null";
  Cache::KeyHolder::TrackICachedResourceKey(&v41, v40);
  v8 = std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::_Find<Cache::KeyHolder>(
         this + 8,
         &v41);
  if ( v7 )
  {
    v9 = *(void (__fastcall **)(Cache::IResourceKey *__hidden))(*(_QWORD *)v7 + 16LL);
    if ( v9 == Cache::IResourceKey::Destroy )
      Cache::IResourceKey::Destroy(v7);
    else
      ((void (__fastcall *)(Cache::IResourceKey *, void (__fastcall *)(Cache::IResourceKey *__hidden)))v9)(
        v7,
        Cache::IResourceKey::Destroy);
  }
  if ( v8 == *((_QWORD *)this + 4) )
  {
    if ( this[34] == 1 )
      Cache::Cache::EnforceMemoryEvictionPolicy((Cache::Cache *)this, (const struct Cache::KeyHolder *)&v38, a3);
    else
      Cache::Cache::EnforceCountEvictionPolicy((Cache::Cache *)this);
    v10 = this[26];
    v41 = a3;
    Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(&v41);
    LODWORD(v42) = v10;
    v11 = *(_QWORD *)std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(
                       this + 8,
                       v40,
                       &v38);
    Mso::TCntPtr<Mso::IRefCounted>::operator=(v11 + 48, &v41);
    *(_DWORD *)(v11 + 56) = v10;
    if ( byte_180522F60 < 0 )
      v12 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180522F60);
    else
      v12 = byte_180522F60 != 0;
    if ( v12 && this[34] == 1 )
    {
      v13 = *(unsigned __int64 (__fastcall **)(GEL::MipmapInstanceCacheKey *__hidden))(*(_QWORD *)v39 + 32LL);
      v14 = v13 == GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes
          ? GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(v39)
          : ((__int64 (*)(void))v13)();
      *((_QWORD *)this + 18) += v14;
      if ( a3 )
      {
        CachedResourceStateForObject = Cache::Cache::GetCachedResourceStateForObject((Cache::Cache *)this, a3);
        *((_QWORD *)this + 18) += (*(__int64 (__fastcall **)(const struct Cache::IResourceState *))(*(_QWORD *)CachedResourceStateForObject
                                                                                                  + 16LL))(CachedResourceStateForObject);
      }
    }
    Cache::Cache::IncrementNextMRUVal((Cache::Cache *)this);
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(48) )
    {
      if ( this[34] == 1 )
      {
        v19 = v39;
        v20 = Cache::Cache::GetCachedResourceStateForObject((Cache::Cache *)this, a3);
        v21 = *(__int64 (__fastcall **)(GEL::MipmapInstanceCacheKey *))(*(_QWORD *)v19 + 32LL);
        v22 = (*(__int64 (__fastcall **)(const struct Cache::IResourceState *))(*(_QWORD *)v20 + 16LL))(v20);
        v23 = v21(v19);
        v68 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
        v69 = "objectMemSizeBytes";
        v70 = v23 + v22;
        v71 = 4;
        v72 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v73 = si128;
        LOWORD(v72) = 0;
        v56 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v57 = "objectMRUVal";
        v58 = v10;
        v59 = 4;
        v60 = 0;
        v61 = si128;
        LOWORD(v60) = 0;
        v62 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
        v63 = "objectPtr";
        v64 = a3;
        v65 = 4;
        v66 = 0;
        v67 = si128;
        LOWORD(v66) = 0;
        LODWORD(v23) = this[10];
        v50 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
        v51 = "newCacheObjectCount";
        v52 = v23;
        v53 = 4;
        v54 = 0;
        v55 = si128;
        LOWORD(v54) = 0;
        CurrentThreadId = GetCurrentThreadId();
        v44 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v45 = "threadID";
        v46 = CurrentThreadId;
        v47 = 4;
        v48 = 0;
        v49 = si128;
        LOWORD(v48) = 0;
        v26 = sub_18000D6BC(this[28]);
        v74[0] = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
        v74[1] = "cacheType";
        v74[2] = v26;
        v75 = 4;
        v76[0] = 0;
        v76[1] = si128;
        LOWORD(v76[0]) = 0;
        v40[0] = "Gfx::Cache::Insert";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
          (unsigned int)"cacheType",
          v27,
          v28,
          v29,
          (__int64)v40,
          (__int64)v74,
          (__int64)&v44,
          (__int64)&v50,
          (__int64)&v62,
          (__int64)&v56,
          (__int64)&v68);
        std::wstring::~wstring(v76);
        std::wstring::~wstring(&v48);
        std::wstring::~wstring(&v54);
        std::wstring::~wstring(&v66);
        std::wstring::~wstring(&v60);
        v30 = &v72;
      }
      else
      {
        v44 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v45 = "objectMRUVal";
        v46 = v10;
        v47 = 4;
        v48 = 0;
        v31 = _mm_load_si128((const __m128i *)&_xmm);
        v49 = v31;
        LOWORD(v48) = 0;
        v62 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
        v63 = "objectPtr";
        v64 = a3;
        v65 = 4;
        v66 = 0;
        v67 = v31;
        LOWORD(v66) = 0;
        v32 = this[10];
        v50 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
        v51 = "newCacheObjectCount";
        v52 = v32;
        v53 = 4;
        v54 = 0;
        v55 = v31;
        LOWORD(v54) = 0;
        v33 = GetCurrentThreadId();
        v56 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v57 = "threadID";
        v58 = v33;
        v59 = 4;
        v60 = 0;
        v61 = v31;
        LOWORD(v60) = 0;
        v34 = sub_18000D6BC(this[28]);
        v68 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
        v69 = "cacheType";
        v70 = v34;
        v71 = 4;
        v72 = 0;
        v73 = v31;
        LOWORD(v72) = 0;
        v40[0] = "Gfx::Cache::Insert";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
          (unsigned int)"cacheType",
          v35,
          v36,
          v37,
          (__int64)v40,
          (__int64)&v68,
          (__int64)&v56,
          (__int64)&v50,
          (__int64)&v62,
          (__int64)&v44);
        std::wstring::~wstring(&v72);
        std::wstring::~wstring(&v60);
        std::wstring::~wstring(&v54);
        std::wstring::~wstring(&v66);
        v30 = &v48;
      }
      std::wstring::~wstring(v30);
    }
    LOBYTE(v15) = 1;
    Cache::Cache::RefreshEvictedMap(this, &v38, 1, v15);
    Mso::TCntPtr<GEL::IScene>::~TCntPtr<GEL::IScene>(&v41);
    v38 = &Cache::KeyHolder::`vftable';
    v16 = v39;
    if ( v39 )
      goto LABEL_19;
  }
  else
  {
    v38 = &Cache::KeyHolder::`vftable';
    v16 = v39;
    if ( v39 )
    {
LABEL_19:
      v17 = *(void (__fastcall **)(Cache::IResourceKey *__hidden))(*(_QWORD *)v16 + 16LL);
      if ( v17 == Cache::IResourceKey::Destroy )
        Cache::IResourceKey::Destroy(v16);
      else
        ((void (__fastcall *)(GEL::MipmapInstanceCacheKey *, void (__fastcall *)(Cache::IResourceKey *__hidden)))v17)(
          v16,
          Cache::IResourceKey::Destroy);
    }
  }
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
}

```

## disassembly

```asm
0x18000e880  mov     rax, rsp
0x18000e883  mov     [rax+20h], rbx
0x18000e887  push    rbp
0x18000e888  push    rsi
0x18000e889  push    rdi
0x18000e88a  push    r12
0x18000e88c  push    r13
0x18000e88e  push    r14
0x18000e890  push    r15
0x18000e892  lea     rbp, [rax-158h]
0x18000e899  sub     rsp, 220h
0x18000e8a0  movaps  xmmword ptr [rax-48h], xmm6
0x18000e8a4  mov     rax, cs:__security_cookie
0x18000e8ab  xor     rax, rsp
0x18000e8ae  mov     [rbp+150h+var_50], rax
0x18000e8b5  mov     r15, r8
0x18000e8b8  mov     rbx, rdx
0x18000e8bb  mov     r14, rcx
0x18000e8be  mov     dl, 1
0x18000e8c0  lea     rcx, [rbp+150h+var_1C0]
0x18000e8c4  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x18000e8c9  mov     rdx, rbx; struct Cache::IResourceKey *
0x18000e8cc  lea     rcx, [rsp+250h+var_1F0]; this
0x18000e8d1  call    ??0KeyHolder@Cache@@QEAA@AEBUIResourceKey@1@@Z; Cache::KeyHolder::KeyHolder(Cache::IResourceKey const &)
0x18000e8d6  lea     r12, ??_7KeyHolder@Cache@@6B@; const Cache::KeyHolder::`vftable'
0x18000e8dd  mov     [rbp+150h+var_1D0], r12
0x18000e8e1  mov     rcx, [rsp+250h+var_1E8]
0x18000e8e6  mov     rax, [rcx]
0x18000e8e9  lea     rdx, [rsp+250h+var_1E0]
0x18000e8ee  mov     rax, [rax+8]
0x18000e8f2  call    cs:__guard_dispatch_icall_fptr
0x18000e8f8  mov     rdi, [rax]
0x18000e8fb  xor     r13d, r13d
0x18000e8fe  mov     [rax], r13
0x18000e901  mov     [rbp+150h+var_1C8], rdi
0x18000e905  mov     rcx, [rsp+250h+var_1E0]
0x18000e90a  test    rcx, rcx
0x18000e90d  jnz     loc_18000EB43
0x18000e913  lea     rax, aKeyholderCopyC; "KeyHolder copy ctor should not set m_pK"...
0x18000e91a  mov     [rsp+250h+var_1E0], rax
0x18000e91f  lea     rdx, [rsp+250h+var_1E0]
0x18000e924  lea     rcx, [rbp+150h+var_1D0]
0x18000e928  call    ?TrackICachedResourceKey@KeyHolder@Cache@@AEBAXAEBV?$StringLiteral@D@StringLiterals@Mso@@@Z; Cache::KeyHolder::TrackICachedResourceKey(Mso::StringLiterals::StringLiteral<char> const &)
0x18000e92d  lea     rsi, [r14+20h]
0x18000e931  lea     rdx, [rbp+150h+var_1D0]
0x18000e935  mov     rcx, rsi
0x18000e938  call    ??$_Find@VKeyHolder@Cache@@@?$_Tree@V?$_Tmap_traits@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@1@AEBVKeyHolder@Cache@@@Z; std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::_Find<Cache::KeyHolder>(Cache::KeyHolder const &)
0x18000e93d  mov     rbx, rax
0x18000e940  lea     rdx, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000e947  test    rdi, rdi
0x18000e94a  jz      short loc_18000E96B
0x18000e94c  mov     rax, [rdi]
0x18000e94f  mov     rax, [rax+10h]
0x18000e953  mov     rcx, rdi; this
0x18000e956  cmp     rax, rdx
0x18000e959  jnz     loc_18000EB2D
0x18000e95f  call    ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000e964  lea     rdx, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000e96b  cmp     rbx, [rsi]
0x18000e96e  jnz     loc_18000EAD6
0x18000e974  mov     rcx, r14; this
0x18000e977  cmp     dword ptr [r14+88h], 1
0x18000e97f  jnz     loc_18000EAF9
0x18000e985  mov     r8, r15; struct Mso::IRefCounted *
0x18000e988  lea     rdx, [rsp+250h+var_1F0]; struct Cache::KeyHolder *
0x18000e98d  call    ?EnforceMemoryEvictionPolicy@Cache@1@AEAAXAEBVKeyHolder@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::EnforceMemoryEvictionPolicy(Cache::KeyHolder const &,Mso::IRefCounted const &)
0x18000e992  mov     r12d, [r14+68h]
0x18000e996  mov     [rbp+150h+var_1D0], r15
0x18000e99a  lea     rcx, [rbp+150h+var_1D0]; void **
0x18000e99e  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x18000e9a3  mov     dword ptr [rbp+150h+var_1C8], r12d
0x18000e9a7  lea     r8, [rsp+250h+var_1F0]
0x18000e9ac  lea     rdx, [rsp+250h+var_1E0]
0x18000e9b1  mov     rcx, rsi
0x18000e9b4  call    ??$_Try_emplace@AEBVKeyHolder@Cache@@$$V@?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@std@@_N@1@AEBVKeyHolder@Cache@@@Z; std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(Cache::KeyHolder const &)
0x18000e9b9  mov     rbx, [rax]
0x18000e9bc  lea     rdx, [rbp+150h+var_1D0]
0x18000e9c0  lea     rcx, [rbx+30h]
0x18000e9c4  call    ??4?$TCntPtr@UIRefCounted@Mso@@@Mso@@QEAAAEAV01@AEBV01@@Z; Mso::TCntPtr<Mso::IRefCounted>::operator=(Mso::TCntPtr<Mso::IRefCounted> const &)
0x18000e9c9  mov     [rbx+38h], r12d
0x18000e9cd  mov     al, cs:byte_180522F60
0x18000e9d3  test    al, al
0x18000e9d5  js      loc_18000EAE7
0x18000e9db  setnz   al
0x18000e9de  test    al, al
0x18000e9e0  jz      short loc_18000EA20
0x18000e9e2  cmp     dword ptr [r14+88h], 1
0x18000e9ea  jnz     short loc_18000EA20
0x18000e9ec  mov     rcx, [rsp+250h+var_1E8]; this
0x18000e9f1  mov     rax, [rcx]
0x18000e9f4  mov     rax, [rax+20h]
0x18000e9f8  lea     rdx, ?GetEstimatedMemSizeBytes@MipmapInstanceCacheKey@GEL@@UEBA_KXZ; GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(void)
0x18000e9ff  cmp     rax, rdx
0x18000ea02  jnz     loc_18000EB59
0x18000ea08  call    ?GetEstimatedMemSizeBytes@MipmapInstanceCacheKey@GEL@@UEBA_KXZ; GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(void)
0x18000ea0d  mov     rcx, rax
0x18000ea10  add     [r14+90h], rax
0x18000ea17  test    r15, r15
0x18000ea1a  jnz     loc_18000EB03
0x18000ea20  mov     rcx, r14; this
0x18000ea23  call    ?IncrementNextMRUVal@Cache@1@IEAAXXZ; Cache::Cache::IncrementNextMRUVal(void)
0x18000ea28  mov     edx, 64h ; 'd'
0x18000ea2d  lea     ecx, [rdx-34h]
0x18000ea30  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z; Mso::Logging::MsoShouldTrace(Mso::Logging::Category,Mso::Logging::Severity)
0x18000ea36  test    al, al
0x18000ea38  jnz     loc_18000EB64
0x18000ea3e  mov     r9b, 1
0x18000ea41  mov     r8d, 1
0x18000ea47  lea     rdx, [rsp+250h+var_1F0]
0x18000ea4c  mov     rcx, r14
0x18000ea4f  call    ?RefreshEvictedMap@Cache@1@AEAAXAEBVKeyHolder@1@W4EvictionType@1@_N@Z; Cache::Cache::RefreshEvictedMap(Cache::KeyHolder const &,Cache::EvictionType,bool)
0x18000ea54  nop
0x18000ea55  lea     rcx, [rbp+150h+var_1D0]
0x18000ea59  call    ??1?$TCntPtr@UIScene@GEL@@@Mso@@QEAA@XZ; Mso::TCntPtr<GEL::IScene>::~TCntPtr<GEL::IScene>(void)
0x18000ea5e  lea     rax, ??_7KeyHolder@Cache@@6B@; const Cache::KeyHolder::`vftable'
0x18000ea65  mov     [rsp+250h+var_1F0], rax
0x18000ea6a  mov     rcx, [rsp+250h+var_1E8]; this
0x18000ea6f  test    rcx, rcx
0x18000ea72  jz      short loc_18000EA91
0x18000ea74  lea     rdx, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000ea7b  mov     rax, [rcx]
0x18000ea7e  mov     rax, [rax+10h]
0x18000ea82  cmp     rax, rdx
0x18000ea85  jnz     loc_18000EB38
0x18000ea8b  call    ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000ea90  nop
0x18000ea91  mov     rcx, [rbp+150h+var_1C0]
0x18000ea95  test    rcx, rcx
0x18000ea98  jz      short loc_18000EAA7
0x18000ea9a  mov     rax, [rcx]
0x18000ea9d  mov     rax, [rax+8]
0x18000eaa1  call    cs:__guard_dispatch_icall_fptr
0x18000eaa7  mov     rcx, [rbp+150h+var_50]
0x18000eaae  xor     rcx, rsp; StackCookie
0x18000eab1  call    __security_check_cookie
0x18000eab6  lea     r11, [rsp+250h+var_30]
0x18000eabe  mov     rbx, [r11+58h]
0x18000eac2  movaps  xmm6, xmmword ptr [r11-10h]
0x18000eac7  mov     rsp, r11
0x18000eaca  pop     r15
0x18000eacc  pop     r14
0x18000eace  pop     r13
0x18000ead0  pop     r12
0x18000ead2  pop     rdi
0x18000ead3  pop     rsi
0x18000ead4  pop     rbp
0x18000ead5  retn
0x18000ead6  mov     [rsp+250h+var_1F0], r12
0x18000eadb  mov     rcx, [rsp+250h+var_1E8]
0x18000eae0  test    rcx, rcx
0x18000eae3  jnz     short loc_18000EA7B
0x18000eae5  jmp     short loc_18000EA91
0x18000eae7  lea     rcx, byte_180522F60
0x18000eaee  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x18000eaf4  jmp     loc_18000E9DE
0x18000eaf9  call    ?EnforceCountEvictionPolicy@Cache@1@AEAAXXZ; Cache::Cache::EnforceCountEvictionPolicy(void)
0x18000eafe  jmp     loc_18000E992
0x18000eb03  mov     rdx, r15; struct Mso::IRefCounted *
0x18000eb06  mov     rcx, r14; this
0x18000eb09  call    ?GetCachedResourceStateForObject@Cache@1@QEBAAEBUIResourceState@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::GetCachedResourceStateForObject(Mso::IRefCounted const &)
0x18000eb0e  mov     rdx, rax
0x18000eb11  mov     rcx, [rax]
0x18000eb14  mov     rax, [rcx+10h]
0x18000eb18  mov     rcx, rdx
0x18000eb1b  call    cs:__guard_dispatch_icall_fptr
0x18000eb21  add     [r14+90h], rax
0x18000eb28  jmp     loc_18000EA20
0x18000eb2d  call    cs:__guard_dispatch_icall_fptr
0x18000eb33  jmp     loc_18000E964
0x18000eb38  call    cs:__guard_dispatch_icall_fptr
0x18000eb3e  jmp     loc_18000EA91
0x18000eb43  mov     rax, [rcx]
0x18000eb46  mov     edx, 1
0x18000eb4b  mov     rax, [rax]
0x18000eb4e  call    cs:__guard_dispatch_icall_fptr
0x18000eb54  jmp     loc_18000E913
0x18000eb59  call    cs:__guard_dispatch_icall_fptr
0x18000eb5f  jmp     loc_18000EA0D
0x18000eb64  cmp     dword ptr [r14+88h], 1
0x18000eb6c  jnz     loc_18000ED91
0x18000eb72  mov     rsi, [rsp+250h+var_1E8]
0x18000eb77  mov     rdx, r15; struct Mso::IRefCounted *
0x18000eb7a  mov     rcx, r14; this
0x18000eb7d  call    ?GetCachedResourceStateForObject@Cache@1@QEBAAEBUIResourceState@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::GetCachedResourceStateForObject(Mso::IRefCounted const &)
0x18000eb82  mov     rdx, rax
0x18000eb85  mov     rcx, [rsi]
0x18000eb88  mov     rdi, [rcx+20h]
0x18000eb8c  mov     rcx, [rax]
0x18000eb8f  mov     rax, [rcx+10h]
0x18000eb93  mov     rcx, rdx
0x18000eb96  call    cs:__guard_dispatch_icall_fptr
0x18000eb9c  mov     rbx, rax
0x18000eb9f  mov     rcx, rsi
0x18000eba2  mov     rax, rdi
0x18000eba5  call    cs:__guard_dispatch_icall_fptr
0x18000ebab  lea     rcx, [rax+rbx]
0x18000ebaf  lea     rax, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x18000ebb6  mov     [rbp+150h+var_D0], rax
0x18000ebbd  lea     rax, aObjectmemsizeb; "objectMemSizeBytes"
0x18000ebc4  mov     [rbp+150h+var_C8], rax
0x18000ebcb  mov     [rbp+150h+var_C0], rcx
0x18000ebd2  mov     ebx, 4
0x18000ebd7  mov     [rbp+150h+var_B8], bx
0x18000ebde  xorps   xmm0, xmm0
0x18000ebe1  movups  [rbp+150h+var_B0], xmm0
0x18000ebe8  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000ebf0  movdqa  [rbp+150h+var_A0], xmm6
0x18000ebf8  mov     word ptr [rbp+150h+var_B0], r13w
0x18000ec00  lea     rdi, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18000ec07  mov     [rbp+150h+var_148], rdi
0x18000ec0b  lea     rax, aObjectmruval; "objectMRUVal"
0x18000ec12  mov     [rbp+150h+var_140], rax
0x18000ec16  mov     [rbp+150h+var_138], r12d
0x18000ec1a  mov     [rbp+150h+var_134], bx
0x18000ec1e  movups  [rbp+150h+var_130], xmm0
0x18000ec22  movdqu  [rbp+150h+var_120], xmm6
0x18000ec27  mov     word ptr [rbp+150h+var_130], r13w
0x18000ec2c  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x18000ec33  mov     [rbp+150h+var_110], rax
0x18000ec37  lea     rax, aObjectptr; "objectPtr"
0x18000ec3e  mov     [rbp+150h+var_108], rax
0x18000ec42  mov     [rbp+150h+var_100], r15
0x18000ec46  mov     [rbp+150h+var_F8], bx
0x18000ec4a  movups  [rbp+150h+var_F0], xmm0
0x18000ec4e  movdqa  [rbp+150h+var_E0], xmm6
0x18000ec53  mov     word ptr [rbp+150h+var_F0], r13w
0x18000ec58  mov     eax, [r14+28h]
0x18000ec5c  lea     rcx, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x18000ec63  mov     [rbp+150h+var_180], rcx
0x18000ec67  lea     rcx, aNewcacheobject; "newCacheObjectCount"
0x18000ec6e  mov     [rbp+150h+var_178], rcx
0x18000ec72  mov     [rbp+150h+var_170], eax
0x18000ec75  mov     [rbp+150h+var_16C], bx
0x18000ec79  movups  [rbp+150h+var_168], xmm0
0x18000ec7d  movdqu  [rbp+150h+var_158], xmm6
0x18000ec82  mov     word ptr [rbp+150h+var_168], r13w
0x18000ec87  call    cs:__imp_GetCurrentThreadId
0x18000ec8d  mov     [rbp+150h+var_1B8], rdi
0x18000ec91  lea     rcx, aThreadid; "threadID"
0x18000ec98  mov     [rbp+150h+var_1B0], rcx
0x18000ec9c  mov     [rbp+150h+var_1A8], eax
0x18000ec9f  mov     [rbp+150h+var_1A4], bx
0x18000eca3  xorps   xmm0, xmm0
0x18000eca6  movups  [rbp+150h+var_1A0], xmm0
0x18000ecaa  movdqu  [rbp+150h+var_190], xmm6
0x18000ecaf  mov     word ptr [rbp+150h+var_1A0], r13w
0x18000ecb4  mov     ecx, [r14+70h]
0x18000ecb8  call    sub_18000D6BC
0x18000ecbd  lea     rcx, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x18000ecc4  mov     [rbp+150h+var_90], rcx
0x18000eccb  lea     rcx, aCachetype; "cacheType"
0x18000ecd2  mov     [rbp+150h+var_88], rcx
0x18000ecd9  mov     [rbp+150h+var_80], rax
0x18000ece0  mov     [rbp+150h+var_78], bx
0x18000ece7  movups  [rbp+150h+var_70], xmm0
0x18000ecee  movdqa  [rbp+150h+var_60], xmm6
0x18000ecf6  mov     word ptr [rbp+150h+var_70], r13w
0x18000ecfe  lea     rax, aGfxCacheInsert; "Gfx::Cache::Insert"
0x18000ed05  mov     [rsp+250h+var_1E0], rax
0x18000ed0a  lea     rax, [rbp+150h+var_D0]
0x18000ed11  mov     [rsp+250h+var_200], rax
0x18000ed16  lea     rax, [rbp+150h+var_148]
0x18000ed1a  mov     [rsp+250h+var_208], rax
0x18000ed1f  lea     rax, [rbp+150h+var_110]
0x18000ed23  mov     [rsp+250h+var_210], rax
0x18000ed28  lea     rax, [rbp+150h+var_180]
0x18000ed2c  mov     [rsp+250h+var_218], rax
0x18000ed31  lea     rax, [rbp+150h+var_1B8]
0x18000ed35  mov     [rsp+250h+var_220], rax
0x18000ed3a  lea     rax, [rbp+150h+var_90]
0x18000ed41  mov     [rsp+250h+var_228], rax
0x18000ed46  lea     rax, [rsp+250h+var_1E0]
0x18000ed4b  mov     [rsp+250h+var_230], rax
0x18000ed50  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@I@23@U?$ClassifiedStructuredObject@H@23@U?$ClassifiedStructuredObject@PEBX@23@U423@U?$ClassifiedStructuredObject@_K@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@H@01@$$QEAU?$ClassifiedStructuredObject@PEBX@01@5$$QEAU?$ClassifiedStructuredObject@_K@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<int> &&,Mso::Diagnostics::ClassifiedStructuredObject<void const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x18000ed55  lea     rcx, [rbp+150h+var_70]
0x18000ed5c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed61  lea     rcx, [rbp+150h+var_1A0]
0x18000ed65  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed6a  lea     rcx, [rbp+150h+var_168]
0x18000ed6e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed73  lea     rcx, [rbp+150h+var_F0]
0x18000ed77  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed7c  lea     rcx, [rbp+150h+var_130]
0x18000ed80  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed85  lea     rcx, [rbp+150h+var_B0]
0x18000ed8c  jmp     loc_18000EF15
0x18000ed91  lea     rdi, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18000ed98  mov     [rbp+150h+var_1B8], rdi
0x18000ed9c  lea     rax, aObjectmruval; "objectMRUVal"
0x18000eda3  mov     [rbp+150h+var_1B0], rax
0x18000eda7  mov     [rbp+150h+var_1A8], r12d
0x18000edab  mov     ebx, 4
0x18000edb0  mov     [rbp+150h+var_1A4], bx
0x18000edb4  xorps   xmm0, xmm0
0x18000edb7  movups  [rbp+150h+var_1A0], xmm0
0x18000edbb  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000edc3  movdqu  [rbp+150h+var_190], xmm6
0x18000edc8  mov     word ptr [rbp+150h+var_1A0], r13w
0x18000edcd  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x18000edd4  mov     [rbp+150h+var_110], rax
  ... truncated ...
```
