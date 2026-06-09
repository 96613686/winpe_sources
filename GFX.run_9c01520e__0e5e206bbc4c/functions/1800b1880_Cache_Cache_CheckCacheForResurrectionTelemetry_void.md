# Cache::Cache::CheckCacheForResurrectionTelemetry(void)

- ea: `0x1800b1880`
- end: `0x1800b2033`
- name: `?CheckCacheForResurrectionTelemetry@Cache@1@QEAAXXZ`
- size: `1971`
- prototype: `void __fastcall(Cache::Cache *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800b17dc`

## callees

- `0x18000d6bc`
- `0x18000e0b0`
- `0x18000e0f0`
- `0x18000e560`
- `0x1800200a0`
- `0x1800578b0`
- `0x180077780`
- `0x1800b1880`
- `0x1800b2034`
- `0x1800b20d8`
- `0x1800b2190`
- `0x1800b21f8`
- `0x1800b2230`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b1ff0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b1ff0`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x1800b18c1`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x1800b18c1`

## string_xrefs

- `0x1800b1900`: `cacheType`
- `0x1800b1dbe`: `cacheType`
- `0x1800b1e01`: `Gfx::Cache::EvictedMapTelemetryRollUp. Remove stale evicted items.`
- `0x1800b19bb`: `m_sizeOfCachedObjectBeingResurrectedBytes`
- `0x1800b1975`: `m_totalCacheSize`
- `0x1800b1a01`: `m_timeToCreateResurrectedObjectMS`
- `0x1800b1b04`: `Gfx::Cache::Evicted cache items that were needed later.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Cache::Cache::CheckCacheForResurrectionTelemetry(Cache::Cache *this)
{
  __int64 v2; // rsi
  __m128i si128; // xmm6
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // r15
  void **v8; // rsi
  __int64 *v9; // rbx
  __int64 v10; // rax
  int v11; // edx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 **v15; // rax
  __int64 *j; // rcx
  __int64 *i; // rax
  _QWORD *v18; // r8
  void *v19; // rcx
  Cache::Cache *v20; // rbx
  __int64 v21; // [rsp+0h] [rbp-2A8h] BYREF
  void *Block; // [rsp+60h] [rbp-248h] BYREF
  void *v23; // [rsp+68h] [rbp-240h]
  const char *v24; // [rsp+70h] [rbp-238h] BYREF
  Cache::Cache *v25; // [rsp+78h] [rbp-230h]
  char v26[16]; // [rsp+80h] [rbp-228h] BYREF
  void **v27; // [rsp+90h] [rbp-218h] BYREF
  const char *v28; // [rsp+98h] [rbp-210h]
  __int64 v29; // [rsp+A0h] [rbp-208h] BYREF
  __int16 v30; // [rsp+A8h] [rbp-200h]
  __int128 v31; // [rsp+B0h] [rbp-1F8h] BYREF
  __m128i v32; // [rsp+C0h] [rbp-1E8h]
  int v33; // [rsp+D0h] [rbp-1D8h]
  __int64 v34; // [rsp+D8h] [rbp-1D0h]
  int v35; // [rsp+E0h] [rbp-1C8h]
  void **v36; // [rsp+F0h] [rbp-1B8h] BYREF
  const char *v37; // [rsp+F8h] [rbp-1B0h]
  int v38; // [rsp+100h] [rbp-1A8h]
  __int16 v39; // [rsp+104h] [rbp-1A4h]
  __int128 v40; // [rsp+108h] [rbp-1A0h] BYREF
  __m128i v41; // [rsp+118h] [rbp-190h]
  void **v42; // [rsp+128h] [rbp-180h] BYREF
  const char *v43; // [rsp+130h] [rbp-178h]
  int v44; // [rsp+138h] [rbp-170h]
  __int16 v45; // [rsp+13Ch] [rbp-16Ch]
  __int128 v46; // [rsp+140h] [rbp-168h] BYREF
  __m128i v47; // [rsp+150h] [rbp-158h]
  void **v48; // [rsp+160h] [rbp-148h] BYREF
  const char *v49; // [rsp+168h] [rbp-140h]
  __int64 v50; // [rsp+170h] [rbp-138h]
  __int16 v51; // [rsp+178h] [rbp-130h]
  __int128 v52; // [rsp+180h] [rbp-128h] BYREF
  __m128i v53; // [rsp+190h] [rbp-118h]
  void **v54; // [rsp+1A0h] [rbp-108h] BYREF
  const char *v55; // [rsp+1A8h] [rbp-100h]
  __int64 v56; // [rsp+1B0h] [rbp-F8h]
  __int16 v57; // [rsp+1B8h] [rbp-F0h]
  __int128 v58; // [rsp+1C0h] [rbp-E8h] BYREF
  __m128i v59; // [rsp+1D0h] [rbp-D8h]
  void **v60; // [rsp+1E0h] [rbp-C8h] BYREF
  const char *v61; // [rsp+1E8h] [rbp-C0h]
  __int64 v62; // [rsp+1F0h] [rbp-B8h]
  __int16 v63; // [rsp+1F8h] [rbp-B0h]
  __int128 v64; // [rsp+200h] [rbp-A8h] BYREF
  __m128i v65; // [rsp+210h] [rbp-98h]
  _QWORD v66[3]; // [rsp+220h] [rbp-88h] BYREF
  __int16 v67; // [rsp+238h] [rbp-70h]
  _OWORD v68[2]; // [rsp+240h] [rbp-68h] BYREF

  v25 = this;
  if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(48) )
  {
    try
    {
      std::map<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems>::map<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems>(&Block);
      v2 = sub_18000D6BC(*((unsigned int *)this + 28));
      v4 = *((_QWORD *)this + 8);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( v4 != *((_QWORD *)this + 9) )
      {
        v42 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v43 = "m_resurrectionCount";
        v44 = *(_DWORD *)(v4 + 72);
        v45 = 4;
        v46 = 0;
        v47 = si128;
        LOWORD(v46) = 0;
        v27 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
        v28 = "m_totalCacheSize";
        v29 = *(_QWORD *)(v4 + 64);
        v30 = 4;
        v31 = 0;
        v32 = si128;
        LOWORD(v31) = 0;
        v60 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
        v61 = "m_sizeOfCachedObjectBeingResurrectedBytes";
        v62 = *(_QWORD *)(v4 + 48);
        v63 = 4;
        v64 = 0;
        v65 = si128;
        LOWORD(v64) = 0;
        v54 = &Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable';
        v55 = "m_timeToCreateResurrectedObjectMS";
        v56 = *(_QWORD *)(v4 + 40);
        v57 = 4;
        v58 = 0;
        v59 = si128;
        LOWORD(v58) = 0;
        v36 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v37 = "m_sequence";
        v38 = *(_DWORD *)(v4 + 32);
        v39 = 4;
        v40 = 0;
        v41 = si128;
        LOWORD(v40) = 0;
        v48 = &Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable';
        v49 = "m_timeSinceLastEviction";
        v50 = *(_QWORD *)(v4 + 24);
        v51 = 4;
        v52 = 0;
        v53 = si128;
        LOWORD(v52) = 0;
        v66[0] = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
        v66[1] = "cacheType";
        v66[2] = v2;
        v67 = 4;
        v68[0] = 0;
        v68[1] = si128;
        LOWORD(v68[0]) = 0;
        v24 = "Gfx::Cache::Evicted cache items that were needed later.";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
          (unsigned int)&Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable',
          (unsigned int)&Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable',
          (unsigned int)&Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable',
          (unsigned int)"cacheType",
          (__int64)&v24,
          (__int64)v66,
          (__int64)&v48,
          (__int64)&v36,
          (__int64)&v54,
          (__int64)&v60,
          (__int64)&v27,
          (__int64)&v42);
        std::wstring::~wstring(v68);
        std::wstring::~wstring(&v52);
        std::wstring::~wstring(&v40);
        std::wstring::~wstring(&v58);
        std::wstring::~wstring(&v64);
        std::wstring::~wstring(&v31);
        std::wstring::~wstring(&v46);
        v4 += 80;
      }
      std::vector<Cache::Cache::ValueResurrectedCacheItems>::clear(
        (char *)this + 64,
        &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable',
        &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable',
        "cacheType");
      v7 = *(_QWORD *)std::chrono::steady_clock::now(&v24) / 1000000000LL;
      v8 = (void **)((char *)this + 48);
      v9 = (__int64 *)**((_QWORD **)this + 6);
      while ( !*((_BYTE *)v9 + 25) )
      {
        v10 = v9[9];
        if ( v7 - v10 == *((_QWORD *)this + 12) || v7 - v10 < *((_QWORD *)this + 12) )
        {
          Cache::KeyHolder::KeyHolder((Cache::KeyHolder *)&v27, (const struct Cache::KeyHolder *)(v9 + 4));
          Cache::KeyHolder::KeyHolder((Cache::KeyHolder *)&v29, (const struct Cache::KeyHolder *)(v9 + 6));
          LODWORD(v31) = *((_DWORD *)v9 + 16);
          *((_QWORD *)&v31 + 1) = v9[9];
          v32.m128i_i32[0] = *((_DWORD *)v9 + 20);
          v32.m128i_i64[1] = v9[11];
          v33 = *((_DWORD *)v9 + 24);
          v34 = v9[13];
          v35 = *((_DWORD *)v9 + 28);
          std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>>,0>>::_Emplace<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>>(
            &Block,
            v26,
            &v27);
          Cache::KeyHolder::~KeyHolder((Cache::KeyHolder *)&v29);
          Cache::KeyHolder::~KeyHolder((Cache::KeyHolder *)&v27);
        }
        else
        {
          v48 = &Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable';
          v49 = "m_timeOfLastResurrection";
          v50 = v9[13];
          v51 = 4;
          v52 = 0;
          v53 = si128;
          LOWORD(v52) = 0;
          v36 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
          v37 = "m_resurrectionCount";
          v38 = *((_DWORD *)v9 + 24);
          v39 = 4;
          v40 = 0;
          v41 = si128;
          LOWORD(v40) = 0;
          v54 = &Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable';
          v55 = "m_timeOfLastEviction";
          v56 = v9[11];
          v57 = 4;
          v58 = 0;
          v59 = si128;
          LOWORD(v58) = 0;
          v42 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
          v43 = "m_EvictionCount";
          v44 = *((_DWORD *)v9 + 20);
          v45 = 4;
          v46 = 0;
          v47 = si128;
          LOWORD(v46) = 0;
          v60 = &Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable';
          v61 = "m_timeOfFirstEviction";
          v62 = v10;
          v63 = 4;
          v64 = 0;
          v65 = si128;
          LOWORD(v64) = 0;
          v27 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
          v28 = "cacheType";
          v29 = sub_18000D6BC(*((unsigned int *)this + 28));
          v30 = 4;
          v31 = 0;
          v32 = si128;
          LOWORD(v31) = 0;
          v24 = "Gfx::Cache::EvictedMapTelemetryRollUp. Remove stale evicted items.";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>>(
            v12,
            v11,
            v13,
            v14,
            (__int64)&v24,
            (__int64)&v27,
            (__int64)&v60,
            (__int64)&v42,
            (__int64)&v54,
            (__int64)&v36,
            (__int64)&v48);
          std::wstring::~wstring(&v31);
          std::wstring::~wstring(&v64);
          std::wstring::~wstring(&v46);
          std::wstring::~wstring(&v58);
          std::wstring::~wstring(&v40);
          std::wstring::~wstring(&v52);
        }
        v15 = (__int64 **)v9[2];
        if ( *((_BYTE *)v15 + 25) )
        {
          for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v9 = i;
          v9 = i;
        }
        else
        {
          v9 = (__int64 *)v9[2];
          for ( j = *v15; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v9 = j;
        }
      }
    }
    catch ( ... )
    {
      v20 = v25;
      std::vector<Cache::Cache::ValueResurrectedCacheItems>::clear((char *)v25 + 64, &v21, v5, v6);
      std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>>,0>>::clear((char *)v20 + 48);
      Mso::Logging::MsoSendTraceTag(
        592545544,
        48,
        15,
        L"Gfx::Cache::CheckCacheForResurrectionTelemetry - An exception thrown while accessing evicted or resurrected cach"
         "e items for telemetry. Resurrected cache telemetry data may be invalid.");
      return;
    }
    if ( v8 == &Block )
    {
      v18 = Block;
    }
    else
    {
      v18 = *v8;
      *v8 = Block;
      Block = v18;
      v19 = v8[1];
      v8[1] = v23;
      v23 = v19;
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>,void *>>>(
      &Block,
      &Block,
      v18[1]);
    free(Block);
  }
}

```

## disassembly

```asm
0x1800b1880  mov     rax, rsp
0x1800b1883  mov     [rax+10h], rbx
0x1800b1887  mov     [rax+18h], rsi
0x1800b188b  push    rdi
0x1800b188c  push    r12
0x1800b188e  push    r13
0x1800b1890  push    r14
0x1800b1892  push    r15
0x1800b1894  sub     rsp, 280h
0x1800b189b  movaps  xmmword ptr [rax-38h], xmm6
0x1800b189f  mov     rax, cs:__security_cookie
0x1800b18a6  xor     rax, rsp
0x1800b18a9  mov     [rsp+2A8h+var_48], rax
0x1800b18b1  mov     r14, rcx
0x1800b18b4  mov     [rsp+2A8h+var_230], rcx
0x1800b18b9  mov     edx, 32h ; '2'
0x1800b18be  lea     ecx, [rdx-2]
0x1800b18c1  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z; Mso::Logging::MsoShouldTrace(Mso::Logging::Category,Mso::Logging::Severity)
0x1800b18c7  xor     r12d, r12d
0x1800b18ca  test    al, al
0x1800b18cc  jz      loc_1800B1FF7
0x1800b18d2  lea     rcx, [rsp+2A8h+Block]
0x1800b18d7  call    ??0?$map@VKeyHolder@Cache@@UValueEvictedCacheItems@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@std@@@5@@std@@QEAA@XZ; std::map<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems>::map<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems>(void)
0x1800b18dc  mov     ecx, [r14+70h]
0x1800b18e0  call    sub_18000D6BC
0x1800b18e5  mov     rsi, rax
0x1800b18e8  mov     rbx, [r14+40h]
0x1800b18ec  lea     r13d, [r12+4]
0x1800b18f1  lea     r15, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x1800b18f8  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800b1900  lea     r9, aCachetype; "cacheType"
0x1800b1907  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1800b190e  lea     rcx, ??_7?$ClassifiedStructuredObject@_J@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable'
0x1800b1915  lea     rax, aMResurrectionc; "m_resurrectionCount"
0x1800b191c  lea     rdx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800b1923  cmp     rbx, [r14+48h]
0x1800b1927  jz      loc_1800B1BDE
0x1800b192d  mov     [rsp+2A8h+var_180], rdx
0x1800b1935  mov     [rsp+2A8h+var_178], rax
0x1800b193d  mov     eax, [rbx+48h]
0x1800b1940  mov     [rsp+2A8h+var_170], eax
0x1800b1947  mov     [rsp+2A8h+var_16C], r13w
0x1800b1950  xorps   xmm0, xmm0
0x1800b1953  movups  [rsp+2A8h+var_168], xmm0
0x1800b195b  movdqu  [rsp+2A8h+var_158], xmm6
0x1800b1964  mov     word ptr [rsp+2A8h+var_168], r12w
0x1800b196d  mov     [rsp+2A8h+var_218], r15
0x1800b1975  lea     rax, aMTotalcachesiz; "m_totalCacheSize"
0x1800b197c  mov     [rsp+2A8h+var_210], rax
0x1800b1984  mov     rax, [rbx+40h]
0x1800b1988  mov     [rsp+2A8h+var_208], rax
0x1800b1990  mov     [rsp+2A8h+var_200], r13w
0x1800b1999  movups  [rsp+2A8h+var_1F8], xmm0
0x1800b19a1  movdqa  [rsp+2A8h+var_1E8], xmm6
0x1800b19aa  mov     word ptr [rsp+2A8h+var_1F8], r12w
0x1800b19b3  mov     [rsp+2A8h+var_C8], r15
0x1800b19bb  lea     rax, aMSizeofcachedo; "m_sizeOfCachedObjectBeingResurrectedByt"...
0x1800b19c2  mov     [rsp+2A8h+var_C0], rax
0x1800b19ca  mov     rax, [rbx+30h]
0x1800b19ce  mov     [rsp+2A8h+var_B8], rax
0x1800b19d6  mov     [rsp+2A8h+var_B0], r13w
0x1800b19df  movups  [rsp+2A8h+var_A8], xmm0
0x1800b19e7  movdqa  [rsp+2A8h+var_98], xmm6
0x1800b19f0  mov     word ptr [rsp+2A8h+var_A8], r12w
0x1800b19f9  mov     [rsp+2A8h+var_108], rcx
0x1800b1a01  lea     rax, aMTimetocreater; "m_timeToCreateResurrectedObjectMS"
0x1800b1a08  mov     [rsp+2A8h+var_100], rax
0x1800b1a10  mov     rax, [rbx+28h]
0x1800b1a14  mov     [rsp+2A8h+var_F8], rax
0x1800b1a1c  mov     [rsp+2A8h+var_F0], r13w
0x1800b1a25  movups  [rsp+2A8h+var_E8], xmm0
0x1800b1a2d  movdqa  [rsp+2A8h+var_D8], xmm6
0x1800b1a36  mov     word ptr [rsp+2A8h+var_E8], r12w
0x1800b1a3f  mov     [rsp+2A8h+var_1B8], rdx
0x1800b1a47  lea     rax, aMSequence; "m_sequence"
0x1800b1a4e  mov     [rsp+2A8h+var_1B0], rax
0x1800b1a56  mov     eax, [rbx+20h]
0x1800b1a59  mov     [rsp+2A8h+var_1A8], eax
0x1800b1a60  mov     [rsp+2A8h+var_1A4], r13w
0x1800b1a69  movups  [rsp+2A8h+var_1A0], xmm0
0x1800b1a71  movdqu  [rsp+2A8h+var_190], xmm6
0x1800b1a7a  mov     word ptr [rsp+2A8h+var_1A0], r12w
0x1800b1a83  mov     [rsp+2A8h+var_148], rcx
0x1800b1a8b  lea     rax, aMTimesincelast; "m_timeSinceLastEviction"
0x1800b1a92  mov     [rsp+2A8h+var_140], rax
0x1800b1a9a  mov     rax, [rbx+18h]
0x1800b1a9e  mov     [rsp+2A8h+var_138], rax
0x1800b1aa6  mov     [rsp+2A8h+var_130], r13w
0x1800b1aaf  movups  [rsp+2A8h+var_128], xmm0
0x1800b1ab7  movdqa  [rsp+2A8h+var_118], xmm6
0x1800b1ac0  mov     word ptr [rsp+2A8h+var_128], r12w
0x1800b1ac9  mov     [rsp+2A8h+var_88], r8
0x1800b1ad1  mov     [rsp+2A8h+var_80], r9
0x1800b1ad9  mov     [rsp+2A8h+var_78], rsi
0x1800b1ae1  mov     [rsp+2A8h+var_70], r13w
0x1800b1aea  movups  [rsp+2A8h+var_68], xmm0
0x1800b1af2  movdqa  [rsp+2A8h+var_58], xmm6
0x1800b1afb  mov     word ptr [rsp+2A8h+var_68], r12w
0x1800b1b04  lea     rax, aGfxCacheEvicte; "Gfx::Cache::Evicted cache items that we"...
0x1800b1b0b  mov     [rsp+2A8h+var_238], rax
0x1800b1b10  lea     rax, [rsp+2A8h+var_180]
0x1800b1b18  mov     [rsp+2A8h+var_250], rax
0x1800b1b1d  lea     rax, [rsp+2A8h+var_218]
0x1800b1b25  mov     [rsp+2A8h+var_258], rax
0x1800b1b2a  lea     rax, [rsp+2A8h+var_C8]
0x1800b1b32  mov     [rsp+2A8h+var_260], rax
0x1800b1b37  lea     rax, [rsp+2A8h+var_108]
0x1800b1b3f  mov     [rsp+2A8h+var_268], rax
0x1800b1b44  lea     rax, [rsp+2A8h+var_1B8]
0x1800b1b4c  mov     [rsp+2A8h+var_270], rax
0x1800b1b51  lea     rax, [rsp+2A8h+var_148]
0x1800b1b59  mov     [rsp+2A8h+var_278], rax
0x1800b1b5e  lea     rax, [rsp+2A8h+var_88]
0x1800b1b66  mov     [rsp+2A8h+var_280], rax
0x1800b1b6b  lea     rax, [rsp+2A8h+var_238]
0x1800b1b70  mov     [rsp+2A8h+var_288], rax
0x1800b1b75  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@_J@23@U?$ClassifiedStructuredObject@I@23@U423@U?$ClassifiedStructuredObject@_K@23@U623@U523@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@_J@01@$$QEAU?$ClassifiedStructuredObject@I@01@5$$QEAU?$ClassifiedStructuredObject@_K@01@76@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&)
0x1800b1b7a  lea     rcx, [rsp+2A8h+var_68]
0x1800b1b82  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1b87  lea     rcx, [rsp+2A8h+var_128]
0x1800b1b8f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1b94  lea     rcx, [rsp+2A8h+var_1A0]
0x1800b1b9c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1ba1  lea     rcx, [rsp+2A8h+var_E8]
0x1800b1ba9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1bae  lea     rcx, [rsp+2A8h+var_A8]
0x1800b1bb6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1bbb  lea     rcx, [rsp+2A8h+var_1F8]
0x1800b1bc3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1bc8  lea     rcx, [rsp+2A8h+var_168]
0x1800b1bd0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1bd5  add     rbx, 50h ; 'P'
0x1800b1bd9  jmp     loc_1800B1900
0x1800b1bde  lea     rcx, [r14+40h]
0x1800b1be2  call    ?clear@?$vector@UValueResurrectedCacheItems@Cache@2@V?$allocator@UValueResurrectedCacheItems@Cache@2@@std@@@std@@QEAAXXZ; std::vector<Cache::Cache::ValueResurrectedCacheItems>::clear(void)
0x1800b1be7  lea     rcx, [rsp+2A8h+var_238]
0x1800b1bec  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800b1bf1  mov     rcx, [rax]
0x1800b1bf4  mov     rax, 112E0BE826D694B3h
0x1800b1bfe  imul    rcx
0x1800b1c01  mov     r15, rdx
0x1800b1c04  sar     r15, 1Ah
0x1800b1c08  mov     rax, r15
0x1800b1c0b  shr     rax, 3Fh
0x1800b1c0f  add     r15, rax
0x1800b1c12  lea     rsi, [r14+30h]
0x1800b1c16  mov     rbx, [rsi]
0x1800b1c19  mov     rbx, [rbx]
0x1800b1c1c  cmp     [rbx+19h], r12b
0x1800b1c20  jnz     loc_1800B1FAC
0x1800b1c26  lea     rdx, [rbx+20h]; struct Cache::KeyHolder *
0x1800b1c2a  lea     rdi, [rdx+10h]
0x1800b1c2e  mov     rax, [rdi+18h]
0x1800b1c32  mov     rcx, r15
0x1800b1c35  sub     rcx, rax
0x1800b1c38  cmp     rcx, [r14+60h]
0x1800b1c3c  jz      loc_1800B1EBD
0x1800b1c42  jl      loc_1800B1EBD
0x1800b1c48  lea     rdx, ??_7?$ClassifiedStructuredObject@_J@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable'
0x1800b1c4f  mov     [rsp+2A8h+var_148], rdx
0x1800b1c57  lea     rcx, aMTimeoflastres; "m_timeOfLastResurrection"
0x1800b1c5e  mov     [rsp+2A8h+var_140], rcx
0x1800b1c66  mov     rcx, [rdi+38h]
0x1800b1c6a  mov     [rsp+2A8h+var_138], rcx
0x1800b1c72  mov     [rsp+2A8h+var_130], r13w
0x1800b1c7b  xorps   xmm0, xmm0
0x1800b1c7e  movups  [rsp+2A8h+var_128], xmm0
0x1800b1c86  movdqa  [rsp+2A8h+var_118], xmm6
0x1800b1c8f  mov     word ptr [rsp+2A8h+var_128], r12w
0x1800b1c98  lea     r8, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800b1c9f  mov     [rsp+2A8h+var_1B8], r8
0x1800b1ca7  lea     rcx, aMResurrectionc; "m_resurrectionCount"
0x1800b1cae  mov     [rsp+2A8h+var_1B0], rcx
0x1800b1cb6  mov     ecx, [rdi+30h]
0x1800b1cb9  mov     [rsp+2A8h+var_1A8], ecx
0x1800b1cc0  mov     [rsp+2A8h+var_1A4], r13w
0x1800b1cc9  movups  [rsp+2A8h+var_1A0], xmm0
0x1800b1cd1  movdqu  [rsp+2A8h+var_190], xmm6
0x1800b1cda  mov     word ptr [rsp+2A8h+var_1A0], r12w
0x1800b1ce3  mov     [rsp+2A8h+var_108], rdx
0x1800b1ceb  lea     rcx, aMTimeoflastevi; "m_timeOfLastEviction"
0x1800b1cf2  mov     [rsp+2A8h+var_100], rcx
0x1800b1cfa  mov     rcx, [rdi+28h]
0x1800b1cfe  mov     [rsp+2A8h+var_F8], rcx
0x1800b1d06  mov     [rsp+2A8h+var_F0], r13w
0x1800b1d0f  movups  [rsp+2A8h+var_E8], xmm0
0x1800b1d17  movdqa  [rsp+2A8h+var_D8], xmm6
0x1800b1d20  mov     word ptr [rsp+2A8h+var_E8], r12w
0x1800b1d29  mov     [rsp+2A8h+var_180], r8
0x1800b1d31  lea     rcx, aMEvictioncount; "m_EvictionCount"
0x1800b1d38  mov     [rsp+2A8h+var_178], rcx
0x1800b1d40  mov     ecx, [rdi+20h]
0x1800b1d43  mov     [rsp+2A8h+var_170], ecx
0x1800b1d4a  mov     [rsp+2A8h+var_16C], r13w
0x1800b1d53  movups  [rsp+2A8h+var_168], xmm0
0x1800b1d5b  movdqu  [rsp+2A8h+var_158], xmm6
0x1800b1d64  mov     word ptr [rsp+2A8h+var_168], r12w
0x1800b1d6d  mov     [rsp+2A8h+var_C8], rdx
0x1800b1d75  lea     rcx, aMTimeoffirstev; "m_timeOfFirstEviction"
0x1800b1d7c  mov     [rsp+2A8h+var_C0], rcx
0x1800b1d84  mov     [rsp+2A8h+var_B8], rax
0x1800b1d8c  mov     [rsp+2A8h+var_B0], r13w
0x1800b1d95  movups  [rsp+2A8h+var_A8], xmm0
0x1800b1d9d  movdqa  [rsp+2A8h+var_98], xmm6
0x1800b1da6  mov     word ptr [rsp+2A8h+var_A8], r12w
0x1800b1daf  lea     rax, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1800b1db6  mov     [rsp+2A8h+var_218], rax
0x1800b1dbe  lea     rax, aCachetype; "cacheType"
0x1800b1dc5  mov     [rsp+2A8h+var_210], rax
0x1800b1dcd  mov     ecx, [r14+70h]
0x1800b1dd1  call    sub_18000D6BC
0x1800b1dd6  mov     [rsp+2A8h+var_208], rax
0x1800b1dde  mov     [rsp+2A8h+var_200], r13w
0x1800b1de7  movups  [rsp+2A8h+var_1F8], xmm0
0x1800b1def  movdqa  [rsp+2A8h+var_1E8], xmm6
0x1800b1df8  mov     word ptr [rsp+2A8h+var_1F8], r12w
0x1800b1e01  lea     rax, aGfxCacheEvicte_0; "Gfx::Cache::EvictedMapTelemetryRollUp. "...
0x1800b1e08  mov     [rsp+2A8h+var_238], rax
0x1800b1e0d  lea     rax, [rsp+2A8h+var_148]
0x1800b1e15  mov     [rsp+2A8h+var_258], rax
0x1800b1e1a  lea     rax, [rsp+2A8h+var_1B8]
0x1800b1e22  mov     [rsp+2A8h+var_260], rax
0x1800b1e27  lea     rax, [rsp+2A8h+var_108]
0x1800b1e2f  mov     [rsp+2A8h+var_268], rax
0x1800b1e34  lea     rax, [rsp+2A8h+var_180]
0x1800b1e3c  mov     [rsp+2A8h+var_270], rax
0x1800b1e41  lea     rax, [rsp+2A8h+var_C8]
0x1800b1e49  mov     [rsp+2A8h+var_278], rax
0x1800b1e4e  lea     rax, [rsp+2A8h+var_218]
0x1800b1e56  mov     [rsp+2A8h+var_280], rax
0x1800b1e5b  lea     rax, [rsp+2A8h+var_238]
0x1800b1e60  mov     [rsp+2A8h+var_288], rax
0x1800b1e65  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@_J@23@U?$ClassifiedStructuredObject@I@23@U423@U523@U423@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@_J@01@$$QEAU?$ClassifiedStructuredObject@I@01@565@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&)
0x1800b1e6a  lea     rcx, [rsp+2A8h+var_1F8]
0x1800b1e72  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1e77  lea     rcx, [rsp+2A8h+var_A8]
0x1800b1e7f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1e84  lea     rcx, [rsp+2A8h+var_168]
0x1800b1e8c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1e91  lea     rcx, [rsp+2A8h+var_E8]
0x1800b1e99  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1e9e  lea     rcx, [rsp+2A8h+var_1A0]
0x1800b1ea6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1eab  lea     rcx, [rsp+2A8h+var_128]
0x1800b1eb3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b1eb8  jmp     loc_1800B1F5D
0x1800b1ebd  lea     rcx, [rsp+2A8h+var_218]; this
0x1800b1ec5  call    ??0KeyHolder@Cache@@QEAA@AEBV01@@Z; Cache::KeyHolder::KeyHolder(Cache::KeyHolder const &)
0x1800b1eca  mov     rdx, rdi; struct Cache::KeyHolder *
0x1800b1ecd  lea     rcx, [rsp+2A8h+var_208]; this
0x1800b1ed5  call    ??0KeyHolder@Cache@@QEAA@AEBV01@@Z; Cache::KeyHolder::KeyHolder(Cache::KeyHolder const &)
0x1800b1eda  mov     eax, [rdi+10h]
0x1800b1edd  mov     dword ptr [rsp+2A8h+var_1F8], eax
0x1800b1ee4  mov     rax, [rdi+18h]
0x1800b1ee8  mov     qword ptr [rsp+2A8h+var_1F8+8], rax
0x1800b1ef0  mov     eax, [rdi+20h]
0x1800b1ef3  mov     dword ptr [rsp+2A8h+var_1E8], eax
0x1800b1efa  mov     rax, [rdi+28h]
0x1800b1efe  mov     qword ptr [rsp+2A8h+var_1E8+8], rax
0x1800b1f06  mov     eax, [rdi+30h]
0x1800b1f09  mov     [rsp+2A8h+var_1D8], eax
0x1800b1f10  mov     rax, [rdi+38h]
0x1800b1f14  mov     [rsp+2A8h+var_1D0], rax
0x1800b1f1c  mov     eax, [rdi+40h]
0x1800b1f1f  mov     [rsp+2A8h+var_1C8], eax
0x1800b1f26  lea     r8, [rsp+2A8h+var_218]
0x1800b1f2e  lea     rdx, [rsp+2A8h+var_228]
0x1800b1f36  lea     rcx, [rsp+2A8h+Block]
0x1800b1f3b  call    ??$_Emplace@U?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@std@@@?$_Tree@V?$_Tmap_traits@VKeyHolder@Cache@@UValueEvictedCacheItems@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@1@@Z; std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>>,0>>::_Emplace<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>>(std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems> &&)
0x1800b1f40  lea     rcx, [rsp+2A8h+var_208]; this
0x1800b1f48  call    ??1KeyHolder@Cache@@UEAA@XZ; Cache::KeyHolder::~KeyHolder(void)
0x1800b1f4d  nop     dword ptr [rax]
0x1800b1f50  lea     rcx, [rsp+2A8h+var_218]; this
0x1800b1f58  call    ??1KeyHolder@Cache@@UEAA@XZ; Cache::KeyHolder::~KeyHolder(void)
0x1800b1f5d  mov     rax, [rbx+10h]
0x1800b1f61  cmp     [rax+19h], r12b
0x1800b1f65  jnz     short loc_1800B1F8B
0x1800b1f67  mov     rbx, rax
0x1800b1f6a  mov     rcx, [rax]
0x1800b1f6d  cmp     [rcx+19h], r12b
0x1800b1f71  jnz     loc_1800B1C1C
0x1800b1f77  mov     rbx, rcx
0x1800b1f7a  mov     rax, [rcx]
0x1800b1f7d  mov     rcx, rax
0x1800b1f80  cmp     [rax+19h], r12b
0x1800b1f84  jz      short loc_1800B1F77
0x1800b1f86  jmp     loc_1800B1C1C
0x1800b1f8b  mov     rax, [rbx+8]
0x1800b1f8f  cmp     [rax+19h], r12b
0x1800b1f93  jnz     short loc_1800B1FA4
0x1800b1f95  cmp     rbx, [rax+10h]
0x1800b1f99  jnz     short loc_1800B1FA4
0x1800b1f9b  mov     rbx, rax
0x1800b1f9e  mov     rax, [rax+8]
0x1800b1fa2  jmp     short loc_1800B1F8F
0x1800b1fa4  mov     rbx, rax
0x1800b1fa7  jmp     loc_1800B1C1C
0x1800b1fac  lea     rax, [rsp+2A8h+Block]
0x1800b1fb1  cmp     rsi, rax
0x1800b1fb4  jz      short loc_1800B2029
  ... truncated ...
```
