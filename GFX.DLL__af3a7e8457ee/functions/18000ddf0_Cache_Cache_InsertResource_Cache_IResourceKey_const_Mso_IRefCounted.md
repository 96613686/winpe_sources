# Cache::Cache::InsertResource(Cache::IResourceKey const &,Mso::IRefCounted &)

- ea: `0x18000ddf0`
- end: `0x18000e487`
- name: `?InsertResource@Cache@1@QEAAXAEBUIResourceKey@1@AEAUIRefCounted@Mso@@@Z`
- size: `1687`
- prototype: `void __fastcall(Cache::Cache *__hidden this, const struct Cache::IResourceKey *, struct Mso::IRefCounted *)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800078d0`
- `0x18000db54`

## callees

- `0x180007a40`
- `0x1800089b0`
- `0x18000a100`
- `0x18000d7fc`
- `0x18000d91c`
- `0x18000da60`
- `0x18000ddf0`
- `0x18000e488`
- `0x18000edd0`
- `0x18000f040`
- `0x18000f890`
- `0x18001f6c0`
- `0x180020254`
- `0x180022970`
- `0x180056ee0`
- `0x1800573f0`
- `0x180067254`
- `0x180067298`
- `0x180067430`
- `0x18007aa30`
- `0x1801fcbe0`
- `0x1801fcc80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000e1ee`
- `KERNEL32!GetCurrentThreadId` at `0x18000e38f`
- `KERNEL32!GetCurrentThreadId` at `0x18000e1ee`
- `KERNEL32!GetCurrentThreadId` at `0x18000e38f`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18000e07f`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18000e07f`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x18000dfc1`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x18000dfc1`

## string_xrefs

- `0x18000e1f8`: `threadID`
- `0x18000e399`: `threadID`
- `0x18000de83`: `KeyHolder copy ctor should not set m_pKeyVal as null`
- `0x18000e232`: `cacheType`
- `0x18000e3d3`: `cacheType`
- `0x18000e265`: `Gfx::Cache::Insert`
- `0x18000e406`: `Gfx::Cache::Insert`
- `0x18000e1ce`: `newCacheObjectCount`
- `0x18000e36f`: `newCacheObjectCount`
- `0x18000e124`: `objectMemSizeBytes`

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
  const struct Cache::IResourceState *CachedResourceStateForObject; // rax
  __int64 v16; // r9
  GEL::MipmapInstanceCacheKey *v17; // rcx
  void (__fastcall *v18)(Cache::IResourceKey *__hidden); // rax
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
    Mso::TCntPtr<Mso::IRefCounted>::operator=((void *)(v11 + 48));
    *(_DWORD *)(v11 + 56) = v10;
    if ( byte_18051EEE0 < 0 )
      v12 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18051EEE0);
    else
      v12 = byte_18051EEE0 != 0;
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
        v70 = v22 + v23;
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
        v26 = sub_18000D7FC(this[28]);
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
        v34 = sub_18000D7FC(this[28]);
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
    LOBYTE(v16) = 1;
    Cache::Cache::RefreshEvictedMap(this, &v38, 1, v16);
    Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(&v41);
    v38 = &Cache::KeyHolder::`vftable';
    v17 = v39;
    if ( v39 )
      goto LABEL_19;
  }
  else
  {
    v38 = &Cache::KeyHolder::`vftable';
    v17 = v39;
    if ( v39 )
    {
LABEL_19:
      v18 = *(void (__fastcall **)(Cache::IResourceKey *__hidden))(*(_QWORD *)v17 + 16LL);
      if ( v18 == Cache::IResourceKey::Destroy )
        Cache::IResourceKey::Destroy(v17);
      else
        ((void (__fastcall *)(GEL::MipmapInstanceCacheKey *, void (__fastcall *)(Cache::IResourceKey *__hidden)))v18)(
          v17,
          Cache::IResourceKey::Destroy);
    }
  }
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
}

```

## disassembly

```asm
0x18000ddf0  mov     rax, rsp
0x18000ddf3  mov     [rax+20h], rbx
0x18000ddf7  push    rbp
0x18000ddf8  push    rsi
0x18000ddf9  push    rdi
0x18000ddfa  push    r12
0x18000ddfc  push    r13
0x18000ddfe  push    r14
0x18000de00  push    r15
0x18000de02  lea     rbp, [rax-158h]
0x18000de09  sub     rsp, 220h
0x18000de10  movaps  xmmword ptr [rax-48h], xmm6
0x18000de14  mov     rax, cs:__security_cookie
0x18000de1b  xor     rax, rsp
0x18000de1e  mov     [rbp+150h+var_50], rax
0x18000de25  mov     r15, r8
0x18000de28  mov     rbx, rdx
0x18000de2b  mov     r14, rcx
0x18000de2e  mov     dl, 1
0x18000de30  lea     rcx, [rbp+150h+var_1C0]
0x18000de34  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x18000de39  mov     rdx, rbx; struct Cache::IResourceKey *
0x18000de3c  lea     rcx, [rsp+250h+var_1F0]; this
0x18000de41  call    ??0KeyHolder@Cache@@QEAA@AEBUIResourceKey@1@@Z; Cache::KeyHolder::KeyHolder(Cache::IResourceKey const &)
0x18000de46  lea     r12, ??_7KeyHolder@Cache@@6B@; const Cache::KeyHolder::`vftable'
0x18000de4d  mov     [rbp+150h+var_1D0], r12
0x18000de51  mov     rcx, [rsp+250h+var_1E8]
0x18000de56  mov     rax, [rcx]
0x18000de59  lea     rdx, [rsp+250h+var_1E0]
0x18000de5e  mov     rax, [rax+8]
0x18000de62  call    cs:__guard_dispatch_icall_fptr
0x18000de68  mov     rdi, [rax]
0x18000de6b  xor     r13d, r13d
0x18000de6e  mov     [rax], r13
0x18000de71  mov     [rbp+150h+var_1C8], rdi
0x18000de75  mov     rcx, [rsp+250h+var_1E0]
0x18000de7a  test    rcx, rcx
0x18000de7d  jnz     loc_18000E0AA
0x18000de83  lea     rax, aKeyholderCopyC; "KeyHolder copy ctor should not set m_pK"...
0x18000de8a  mov     [rsp+250h+var_1E0], rax
0x18000de8f  lea     rdx, [rsp+250h+var_1E0]
0x18000de94  lea     rcx, [rbp+150h+var_1D0]
0x18000de98  call    ?TrackICachedResourceKey@KeyHolder@Cache@@AEBAXAEBV?$StringLiteral@D@StringLiterals@Mso@@@Z; Cache::KeyHolder::TrackICachedResourceKey(Mso::StringLiterals::StringLiteral<char> const &)
0x18000de9d  lea     rsi, [r14+20h]
0x18000dea1  lea     rdx, [rbp+150h+var_1D0]
0x18000dea5  mov     rcx, rsi
0x18000dea8  call    ??$_Find@VKeyHolder@Cache@@@?$_Tree@V?$_Tmap_traits@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@1@AEBVKeyHolder@Cache@@@Z; std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::_Find<Cache::KeyHolder>(Cache::KeyHolder const &)
0x18000dead  mov     rbx, rax
0x18000deb0  lea     rdx, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000deb7  test    rdi, rdi
0x18000deba  jz      short loc_18000DEDB
0x18000debc  mov     rax, [rdi]
0x18000debf  mov     rax, [rax+10h]
0x18000dec3  mov     rcx, rdi; this
0x18000dec6  cmp     rax, rdx
0x18000dec9  jnz     loc_18000E094
0x18000decf  call    ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000ded4  lea     rdx, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000dedb  cmp     rbx, [rsi]
0x18000dede  jnz     loc_18000E067
0x18000dee4  mov     rcx, r14; this
0x18000dee7  cmp     dword ptr [r14+88h], 1
0x18000deef  jnz     loc_18000E08A
0x18000def5  mov     r8, r15; struct Mso::IRefCounted *
0x18000def8  lea     rdx, [rsp+250h+var_1F0]; struct Cache::KeyHolder *
0x18000defd  call    ?EnforceMemoryEvictionPolicy@Cache@1@AEAAXAEBVKeyHolder@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::EnforceMemoryEvictionPolicy(Cache::KeyHolder const &,Mso::IRefCounted const &)
0x18000df02  mov     r12d, [r14+68h]
0x18000df06  mov     [rbp+150h+var_1D0], r15
0x18000df0a  lea     rcx, [rbp+150h+var_1D0]; void **
0x18000df0e  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x18000df13  mov     dword ptr [rbp+150h+var_1C8], r12d
0x18000df17  lea     r8, [rsp+250h+var_1F0]
0x18000df1c  lea     rdx, [rsp+250h+var_1E0]
0x18000df21  mov     rcx, rsi
0x18000df24  call    ??$_Try_emplace@AEBVKeyHolder@Cache@@$$V@?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@std@@_N@1@AEBVKeyHolder@Cache@@@Z; std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(Cache::KeyHolder const &)
0x18000df29  mov     rbx, [rax]
0x18000df2c  lea     rdx, [rbp+150h+var_1D0]
0x18000df30  lea     rcx, [rbx+30h]
0x18000df34  call    ??4?$TCntPtr@UIRefCounted@Mso@@@Mso@@QEAAAEAV01@AEBV01@@Z; Mso::TCntPtr<Mso::IRefCounted>::operator=(Mso::TCntPtr<Mso::IRefCounted> const &)
0x18000df39  mov     [rbx+38h], r12d
0x18000df3d  mov     al, cs:byte_18051EEE0
0x18000df43  test    al, al
0x18000df45  js      loc_18000E078
0x18000df4b  setnz   al
0x18000df4e  test    al, al
0x18000df50  jz      short loc_18000DFB1
0x18000df52  cmp     dword ptr [r14+88h], 1
0x18000df5a  jnz     short loc_18000DFB1
0x18000df5c  mov     rcx, [rsp+250h+var_1E8]; this
0x18000df61  mov     rax, [rcx]
0x18000df64  mov     rax, [rax+20h]
0x18000df68  lea     rdx, ?GetEstimatedMemSizeBytes@MipmapInstanceCacheKey@GEL@@UEBA_KXZ; GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(void)
0x18000df6f  cmp     rax, rdx
0x18000df72  jnz     loc_18000E0C0
0x18000df78  call    ?GetEstimatedMemSizeBytes@MipmapInstanceCacheKey@GEL@@UEBA_KXZ; GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(void)
0x18000df7d  mov     rcx, rax
0x18000df80  add     [r14+90h], rax
0x18000df87  test    r15, r15
0x18000df8a  jz      short loc_18000DFB1
0x18000df8c  mov     rdx, r15; struct Mso::IRefCounted *
0x18000df8f  mov     rcx, r14; this
0x18000df92  call    ?GetCachedResourceStateForObject@Cache@1@QEBAAEBUIResourceState@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::GetCachedResourceStateForObject(Mso::IRefCounted const &)
0x18000df97  mov     rdx, rax
0x18000df9a  mov     rcx, [rax]
0x18000df9d  mov     rax, [rcx+10h]
0x18000dfa1  mov     rcx, rdx
0x18000dfa4  call    cs:__guard_dispatch_icall_fptr
0x18000dfaa  add     [r14+90h], rax
0x18000dfb1  mov     rcx, r14; this
0x18000dfb4  call    ?IncrementNextMRUVal@Cache@1@IEAAXXZ; Cache::Cache::IncrementNextMRUVal(void)
0x18000dfb9  mov     edx, 64h ; 'd'
0x18000dfbe  lea     ecx, [rdx-34h]
0x18000dfc1  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z; Mso::Logging::MsoShouldTrace(Mso::Logging::Category,Mso::Logging::Severity)
0x18000dfc7  test    al, al
0x18000dfc9  jnz     loc_18000E0CB
0x18000dfcf  mov     r9b, 1
0x18000dfd2  mov     r8d, 1
0x18000dfd8  lea     rdx, [rsp+250h+var_1F0]
0x18000dfdd  mov     rcx, r14
0x18000dfe0  call    ?RefreshEvictedMap@Cache@1@AEAAXAEBVKeyHolder@1@W4EvictionType@1@_N@Z; Cache::Cache::RefreshEvictedMap(Cache::KeyHolder const &,Cache::EvictionType,bool)
0x18000dfe5  nop
0x18000dfe6  lea     rcx, [rbp+150h+var_1D0]; void *
0x18000dfea  call    ??1?$TCntPtr@VPlanarProjectionTexturer@Gfx@@@Mso@@QEAA@XZ; Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(void)
0x18000dfef  lea     rax, ??_7KeyHolder@Cache@@6B@; const Cache::KeyHolder::`vftable'
0x18000dff6  mov     [rsp+250h+var_1F0], rax
0x18000dffb  mov     rcx, [rsp+250h+var_1E8]; this
0x18000e000  test    rcx, rcx
0x18000e003  jz      short loc_18000E022
0x18000e005  lea     rdx, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000e00c  mov     rax, [rcx]
0x18000e00f  mov     rax, [rax+10h]
0x18000e013  cmp     rax, rdx
0x18000e016  jnz     loc_18000E09F
0x18000e01c  call    ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18000e021  nop
0x18000e022  mov     rcx, [rbp+150h+var_1C0]
0x18000e026  test    rcx, rcx
0x18000e029  jz      short loc_18000E038
0x18000e02b  mov     rax, [rcx]
0x18000e02e  mov     rax, [rax+8]
0x18000e032  call    cs:__guard_dispatch_icall_fptr
0x18000e038  mov     rcx, [rbp+150h+var_50]
0x18000e03f  xor     rcx, rsp; StackCookie
0x18000e042  call    __security_check_cookie
0x18000e047  lea     r11, [rsp+250h+var_30]
0x18000e04f  mov     rbx, [r11+58h]
0x18000e053  movaps  xmm6, xmmword ptr [r11-10h]
0x18000e058  mov     rsp, r11
0x18000e05b  pop     r15
0x18000e05d  pop     r14
0x18000e05f  pop     r13
0x18000e061  pop     r12
0x18000e063  pop     rdi
0x18000e064  pop     rsi
0x18000e065  pop     rbp
0x18000e066  retn
0x18000e067  mov     [rsp+250h+var_1F0], r12
0x18000e06c  mov     rcx, [rsp+250h+var_1E8]
0x18000e071  test    rcx, rcx
0x18000e074  jnz     short loc_18000E00C
0x18000e076  jmp     short loc_18000E022
0x18000e078  lea     rcx, byte_18051EEE0
0x18000e07f  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x18000e085  jmp     loc_18000DF4E
0x18000e08a  call    ?EnforceCountEvictionPolicy@Cache@1@AEAAXXZ; Cache::Cache::EnforceCountEvictionPolicy(void)
0x18000e08f  jmp     loc_18000DF02
0x18000e094  call    cs:__guard_dispatch_icall_fptr
0x18000e09a  jmp     loc_18000DED4
0x18000e09f  call    cs:__guard_dispatch_icall_fptr
0x18000e0a5  jmp     loc_18000E022
0x18000e0aa  mov     rax, [rcx]
0x18000e0ad  mov     edx, 1
0x18000e0b2  mov     rax, [rax]
0x18000e0b5  call    cs:__guard_dispatch_icall_fptr
0x18000e0bb  jmp     loc_18000DE83
0x18000e0c0  call    cs:__guard_dispatch_icall_fptr
0x18000e0c6  jmp     loc_18000DF7D
0x18000e0cb  cmp     dword ptr [r14+88h], 1
0x18000e0d3  jnz     loc_18000E2F8
0x18000e0d9  mov     rsi, [rsp+250h+var_1E8]
0x18000e0de  mov     rdx, r15; struct Mso::IRefCounted *
0x18000e0e1  mov     rcx, r14; this
0x18000e0e4  call    ?GetCachedResourceStateForObject@Cache@1@QEBAAEBUIResourceState@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::GetCachedResourceStateForObject(Mso::IRefCounted const &)
0x18000e0e9  mov     rdx, rax
0x18000e0ec  mov     rcx, [rsi]
0x18000e0ef  mov     rdi, [rcx+20h]
0x18000e0f3  mov     rcx, [rax]
0x18000e0f6  mov     rax, [rcx+10h]
0x18000e0fa  mov     rcx, rdx
0x18000e0fd  call    cs:__guard_dispatch_icall_fptr
0x18000e103  mov     rbx, rax
0x18000e106  mov     rcx, rsi
0x18000e109  mov     rax, rdi
0x18000e10c  call    cs:__guard_dispatch_icall_fptr
0x18000e112  lea     rcx, [rbx+rax]
0x18000e116  lea     rax, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x18000e11d  mov     [rbp+150h+var_D0], rax
0x18000e124  lea     rax, aObjectmemsizeb; "objectMemSizeBytes"
0x18000e12b  mov     [rbp+150h+var_C8], rax
0x18000e132  mov     [rbp+150h+var_C0], rcx
0x18000e139  mov     ebx, 4
0x18000e13e  mov     [rbp+150h+var_B8], bx
0x18000e145  xorps   xmm0, xmm0
0x18000e148  movups  [rbp+150h+var_B0], xmm0
0x18000e14f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000e157  movdqa  [rbp+150h+var_A0], xmm6
0x18000e15f  mov     word ptr [rbp+150h+var_B0], r13w
0x18000e167  lea     rdi, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18000e16e  mov     [rbp+150h+var_148], rdi
0x18000e172  lea     rax, aObjectmruval; "objectMRUVal"
0x18000e179  mov     [rbp+150h+var_140], rax
0x18000e17d  mov     [rbp+150h+var_138], r12d
0x18000e181  mov     [rbp+150h+var_134], bx
0x18000e185  movups  [rbp+150h+var_130], xmm0
0x18000e189  movdqu  [rbp+150h+var_120], xmm6
0x18000e18e  mov     word ptr [rbp+150h+var_130], r13w
0x18000e193  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x18000e19a  mov     [rbp+150h+var_110], rax
0x18000e19e  lea     rax, aObjectptr; "objectPtr"
0x18000e1a5  mov     [rbp+150h+var_108], rax
0x18000e1a9  mov     [rbp+150h+var_100], r15
0x18000e1ad  mov     [rbp+150h+var_F8], bx
0x18000e1b1  movups  [rbp+150h+var_F0], xmm0
0x18000e1b5  movdqa  [rbp+150h+var_E0], xmm6
0x18000e1ba  mov     word ptr [rbp+150h+var_F0], r13w
0x18000e1bf  mov     eax, [r14+28h]
0x18000e1c3  lea     rcx, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x18000e1ca  mov     [rbp+150h+var_180], rcx
0x18000e1ce  lea     rcx, aNewcacheobject; "newCacheObjectCount"
0x18000e1d5  mov     [rbp+150h+var_178], rcx
0x18000e1d9  mov     [rbp+150h+var_170], eax
0x18000e1dc  mov     [rbp+150h+var_16C], bx
0x18000e1e0  movups  [rbp+150h+var_168], xmm0
0x18000e1e4  movdqu  [rbp+150h+var_158], xmm6
0x18000e1e9  mov     word ptr [rbp+150h+var_168], r13w
0x18000e1ee  call    cs:__imp_GetCurrentThreadId
0x18000e1f4  mov     [rbp+150h+var_1B8], rdi
0x18000e1f8  lea     rcx, aThreadid; "threadID"
0x18000e1ff  mov     [rbp+150h+var_1B0], rcx
0x18000e203  mov     [rbp+150h+var_1A8], eax
0x18000e206  mov     [rbp+150h+var_1A4], bx
0x18000e20a  xorps   xmm0, xmm0
0x18000e20d  movups  [rbp+150h+var_1A0], xmm0
0x18000e211  movdqu  [rbp+150h+var_190], xmm6
0x18000e216  mov     word ptr [rbp+150h+var_1A0], r13w
0x18000e21b  mov     ecx, [r14+70h]
0x18000e21f  call    sub_18000D7FC
0x18000e224  lea     rcx, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x18000e22b  mov     [rbp+150h+var_90], rcx
0x18000e232  lea     rcx, aCachetype; "cacheType"
0x18000e239  mov     [rbp+150h+var_88], rcx
0x18000e240  mov     [rbp+150h+var_80], rax
0x18000e247  mov     [rbp+150h+var_78], bx
0x18000e24e  movups  [rbp+150h+var_70], xmm0
0x18000e255  movdqa  [rbp+150h+var_60], xmm6
0x18000e25d  mov     word ptr [rbp+150h+var_70], r13w
0x18000e265  lea     rax, aGfxCacheInsert; "Gfx::Cache::Insert"
0x18000e26c  mov     [rsp+250h+var_1E0], rax
0x18000e271  lea     rax, [rbp+150h+var_D0]
0x18000e278  mov     [rsp+250h+var_200], rax
0x18000e27d  lea     rax, [rbp+150h+var_148]
0x18000e281  mov     [rsp+250h+var_208], rax
0x18000e286  lea     rax, [rbp+150h+var_110]
0x18000e28a  mov     [rsp+250h+var_210], rax
0x18000e28f  lea     rax, [rbp+150h+var_180]
0x18000e293  mov     [rsp+250h+var_218], rax
0x18000e298  lea     rax, [rbp+150h+var_1B8]
0x18000e29c  mov     [rsp+250h+var_220], rax
0x18000e2a1  lea     rax, [rbp+150h+var_90]
0x18000e2a8  mov     [rsp+250h+var_228], rax
0x18000e2ad  lea     rax, [rsp+250h+var_1E0]
0x18000e2b2  mov     [rsp+250h+var_230], rax
0x18000e2b7  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@I@23@U?$ClassifiedStructuredObject@H@23@U?$ClassifiedStructuredObject@PEBX@23@U423@U?$ClassifiedStructuredObject@_K@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@H@01@$$QEAU?$ClassifiedStructuredObject@PEBX@01@5$$QEAU?$ClassifiedStructuredObject@_K@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<int> &&,Mso::Diagnostics::ClassifiedStructuredObject<void const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x18000e2bc  lea     rcx, [rbp+150h+var_70]
0x18000e2c3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2c8  lea     rcx, [rbp+150h+var_1A0]
0x18000e2cc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2d1  lea     rcx, [rbp+150h+var_168]
0x18000e2d5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2da  lea     rcx, [rbp+150h+var_F0]
0x18000e2de  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2e3  lea     rcx, [rbp+150h+var_130]
0x18000e2e7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2ec  lea     rcx, [rbp+150h+var_B0]
0x18000e2f3  jmp     loc_18000E47C
0x18000e2f8  lea     rdi, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18000e2ff  mov     [rbp+150h+var_1B8], rdi
0x18000e303  lea     rax, aObjectmruval; "objectMRUVal"
0x18000e30a  mov     [rbp+150h+var_1B0], rax
0x18000e30e  mov     [rbp+150h+var_1A8], r12d
0x18000e312  mov     ebx, 4
0x18000e317  mov     [rbp+150h+var_1A4], bx
0x18000e31b  xorps   xmm0, xmm0
0x18000e31e  movups  [rbp+150h+var_1A0], xmm0
0x18000e322  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000e32a  movdqu  [rbp+150h+var_190], xmm6
0x18000e32f  mov     word ptr [rbp+150h+var_1A0], r13w
0x18000e334  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x18000e33b  mov     [rbp+150h+var_110], rax
0x18000e33f  lea     rax, aObjectptr; "objectPtr"
  ... truncated ...
```
