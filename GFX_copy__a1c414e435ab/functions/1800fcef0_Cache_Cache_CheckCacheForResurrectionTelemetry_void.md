# Cache::Cache::CheckCacheForResurrectionTelemetry(void)

- ea: `0x1800fcef0`
- end: `0x1800fd6a3`
- name: `?CheckCacheForResurrectionTelemetry@Cache@1@QEAAXXZ`
- size: `1971`
- prototype: `void __fastcall(Cache::Cache *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800fce4c`

## callees

- `0x18000d7fc`
- `0x18000eb10`
- `0x18000eb50`
- `0x18000efc0`
- `0x18001fce4`
- `0x180056ee0`
- `0x18007aa30`
- `0x1800fcef0`
- `0x1800fd6a4`
- `0x1800fd748`
- `0x1800fd800`
- `0x1800fd868`
- `0x1800fd8a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800fd660`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800fd660`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x1800fcf31`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x1800fcf31`

## string_xrefs

- `0x1800fcf70`: `cacheType`
- `0x1800fd42e`: `cacheType`
- `0x1800fd471`: `Gfx::Cache::EvictedMapTelemetryRollUp. Remove stale evicted items.`
- `0x1800fd02b`: `m_sizeOfCachedObjectBeingResurrectedBytes`
- `0x1800fcfe5`: `m_totalCacheSize`
- `0x1800fd071`: `m_timeToCreateResurrectedObjectMS`
- `0x1800fd174`: `Gfx::Cache::Evicted cache items that were needed later.`

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
      v2 = sub_18000D7FC(*((unsigned int *)this + 28));
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
          v29 = sub_18000D7FC(*((unsigned int *)this + 28));
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
0x1800fcef0  mov     rax, rsp
0x1800fcef3  mov     [rax+10h], rbx
0x1800fcef7  mov     [rax+18h], rsi
0x1800fcefb  push    rdi
0x1800fcefc  push    r12
0x1800fcefe  push    r13
0x1800fcf00  push    r14
0x1800fcf02  push    r15
0x1800fcf04  sub     rsp, 280h
0x1800fcf0b  movaps  xmmword ptr [rax-38h], xmm6
0x1800fcf0f  mov     rax, cs:__security_cookie
0x1800fcf16  xor     rax, rsp
0x1800fcf19  mov     [rsp+2A8h+var_48], rax
0x1800fcf21  mov     r14, rcx
0x1800fcf24  mov     [rsp+2A8h+var_230], rcx
0x1800fcf29  mov     edx, 32h ; '2'
0x1800fcf2e  lea     ecx, [rdx-2]
0x1800fcf31  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z; Mso::Logging::MsoShouldTrace(Mso::Logging::Category,Mso::Logging::Severity)
0x1800fcf37  xor     r12d, r12d
0x1800fcf3a  test    al, al
0x1800fcf3c  jz      loc_1800FD667
0x1800fcf42  lea     rcx, [rsp+2A8h+Block]
0x1800fcf47  call    ??0?$map@VKeyHolder@Cache@@UValueEvictedCacheItems@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@std@@@5@@std@@QEAA@XZ; std::map<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems>::map<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems>(void)
0x1800fcf4c  mov     ecx, [r14+70h]
0x1800fcf50  call    sub_18000D7FC
0x1800fcf55  mov     rsi, rax
0x1800fcf58  mov     rbx, [r14+40h]
0x1800fcf5c  lea     r13d, [r12+4]
0x1800fcf61  lea     r15, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x1800fcf68  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800fcf70  lea     r9, aCachetype; "cacheType"
0x1800fcf77  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1800fcf7e  lea     rcx, ??_7?$ClassifiedStructuredObject@_J@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable'
0x1800fcf85  lea     rax, aMResurrectionc; "m_resurrectionCount"
0x1800fcf8c  lea     rdx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800fcf93  cmp     rbx, [r14+48h]
0x1800fcf97  jz      loc_1800FD24E
0x1800fcf9d  mov     [rsp+2A8h+var_180], rdx
0x1800fcfa5  mov     [rsp+2A8h+var_178], rax
0x1800fcfad  mov     eax, [rbx+48h]
0x1800fcfb0  mov     [rsp+2A8h+var_170], eax
0x1800fcfb7  mov     [rsp+2A8h+var_16C], r13w
0x1800fcfc0  xorps   xmm0, xmm0
0x1800fcfc3  movups  [rsp+2A8h+var_168], xmm0
0x1800fcfcb  movdqu  [rsp+2A8h+var_158], xmm6
0x1800fcfd4  mov     word ptr [rsp+2A8h+var_168], r12w
0x1800fcfdd  mov     [rsp+2A8h+var_218], r15
0x1800fcfe5  lea     rax, aMTotalcachesiz; "m_totalCacheSize"
0x1800fcfec  mov     [rsp+2A8h+var_210], rax
0x1800fcff4  mov     rax, [rbx+40h]
0x1800fcff8  mov     [rsp+2A8h+var_208], rax
0x1800fd000  mov     [rsp+2A8h+var_200], r13w
0x1800fd009  movups  [rsp+2A8h+var_1F8], xmm0
0x1800fd011  movdqa  [rsp+2A8h+var_1E8], xmm6
0x1800fd01a  mov     word ptr [rsp+2A8h+var_1F8], r12w
0x1800fd023  mov     [rsp+2A8h+var_C8], r15
0x1800fd02b  lea     rax, aMSizeofcachedo; "m_sizeOfCachedObjectBeingResurrectedByt"...
0x1800fd032  mov     [rsp+2A8h+var_C0], rax
0x1800fd03a  mov     rax, [rbx+30h]
0x1800fd03e  mov     [rsp+2A8h+var_B8], rax
0x1800fd046  mov     [rsp+2A8h+var_B0], r13w
0x1800fd04f  movups  [rsp+2A8h+var_A8], xmm0
0x1800fd057  movdqa  [rsp+2A8h+var_98], xmm6
0x1800fd060  mov     word ptr [rsp+2A8h+var_A8], r12w
0x1800fd069  mov     [rsp+2A8h+var_108], rcx
0x1800fd071  lea     rax, aMTimetocreater; "m_timeToCreateResurrectedObjectMS"
0x1800fd078  mov     [rsp+2A8h+var_100], rax
0x1800fd080  mov     rax, [rbx+28h]
0x1800fd084  mov     [rsp+2A8h+var_F8], rax
0x1800fd08c  mov     [rsp+2A8h+var_F0], r13w
0x1800fd095  movups  [rsp+2A8h+var_E8], xmm0
0x1800fd09d  movdqa  [rsp+2A8h+var_D8], xmm6
0x1800fd0a6  mov     word ptr [rsp+2A8h+var_E8], r12w
0x1800fd0af  mov     [rsp+2A8h+var_1B8], rdx
0x1800fd0b7  lea     rax, aMSequence; "m_sequence"
0x1800fd0be  mov     [rsp+2A8h+var_1B0], rax
0x1800fd0c6  mov     eax, [rbx+20h]
0x1800fd0c9  mov     [rsp+2A8h+var_1A8], eax
0x1800fd0d0  mov     [rsp+2A8h+var_1A4], r13w
0x1800fd0d9  movups  [rsp+2A8h+var_1A0], xmm0
0x1800fd0e1  movdqu  [rsp+2A8h+var_190], xmm6
0x1800fd0ea  mov     word ptr [rsp+2A8h+var_1A0], r12w
0x1800fd0f3  mov     [rsp+2A8h+var_148], rcx
0x1800fd0fb  lea     rax, aMTimesincelast; "m_timeSinceLastEviction"
0x1800fd102  mov     [rsp+2A8h+var_140], rax
0x1800fd10a  mov     rax, [rbx+18h]
0x1800fd10e  mov     [rsp+2A8h+var_138], rax
0x1800fd116  mov     [rsp+2A8h+var_130], r13w
0x1800fd11f  movups  [rsp+2A8h+var_128], xmm0
0x1800fd127  movdqa  [rsp+2A8h+var_118], xmm6
0x1800fd130  mov     word ptr [rsp+2A8h+var_128], r12w
0x1800fd139  mov     [rsp+2A8h+var_88], r8
0x1800fd141  mov     [rsp+2A8h+var_80], r9
0x1800fd149  mov     [rsp+2A8h+var_78], rsi
0x1800fd151  mov     [rsp+2A8h+var_70], r13w
0x1800fd15a  movups  [rsp+2A8h+var_68], xmm0
0x1800fd162  movdqa  [rsp+2A8h+var_58], xmm6
0x1800fd16b  mov     word ptr [rsp+2A8h+var_68], r12w
0x1800fd174  lea     rax, aGfxCacheEvicte; "Gfx::Cache::Evicted cache items that we"...
0x1800fd17b  mov     [rsp+2A8h+var_238], rax
0x1800fd180  lea     rax, [rsp+2A8h+var_180]
0x1800fd188  mov     [rsp+2A8h+var_250], rax
0x1800fd18d  lea     rax, [rsp+2A8h+var_218]
0x1800fd195  mov     [rsp+2A8h+var_258], rax
0x1800fd19a  lea     rax, [rsp+2A8h+var_C8]
0x1800fd1a2  mov     [rsp+2A8h+var_260], rax
0x1800fd1a7  lea     rax, [rsp+2A8h+var_108]
0x1800fd1af  mov     [rsp+2A8h+var_268], rax
0x1800fd1b4  lea     rax, [rsp+2A8h+var_1B8]
0x1800fd1bc  mov     [rsp+2A8h+var_270], rax
0x1800fd1c1  lea     rax, [rsp+2A8h+var_148]
0x1800fd1c9  mov     [rsp+2A8h+var_278], rax
0x1800fd1ce  lea     rax, [rsp+2A8h+var_88]
0x1800fd1d6  mov     [rsp+2A8h+var_280], rax
0x1800fd1db  lea     rax, [rsp+2A8h+var_238]
0x1800fd1e0  mov     [rsp+2A8h+var_288], rax
0x1800fd1e5  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@_J@23@U?$ClassifiedStructuredObject@I@23@U423@U?$ClassifiedStructuredObject@_K@23@U623@U523@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@_J@01@$$QEAU?$ClassifiedStructuredObject@I@01@5$$QEAU?$ClassifiedStructuredObject@_K@01@76@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&)
0x1800fd1ea  lea     rcx, [rsp+2A8h+var_68]
0x1800fd1f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd1f7  lea     rcx, [rsp+2A8h+var_128]
0x1800fd1ff  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd204  lea     rcx, [rsp+2A8h+var_1A0]
0x1800fd20c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd211  lea     rcx, [rsp+2A8h+var_E8]
0x1800fd219  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd21e  lea     rcx, [rsp+2A8h+var_A8]
0x1800fd226  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd22b  lea     rcx, [rsp+2A8h+var_1F8]
0x1800fd233  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd238  lea     rcx, [rsp+2A8h+var_168]
0x1800fd240  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd245  add     rbx, 50h ; 'P'
0x1800fd249  jmp     loc_1800FCF70
0x1800fd24e  lea     rcx, [r14+40h]
0x1800fd252  call    ?clear@?$vector@UValueResurrectedCacheItems@Cache@2@V?$allocator@UValueResurrectedCacheItems@Cache@2@@std@@@std@@QEAAXXZ; std::vector<Cache::Cache::ValueResurrectedCacheItems>::clear(void)
0x1800fd257  lea     rcx, [rsp+2A8h+var_238]
0x1800fd25c  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800fd261  mov     rcx, [rax]
0x1800fd264  mov     rax, 112E0BE826D694B3h
0x1800fd26e  imul    rcx
0x1800fd271  mov     r15, rdx
0x1800fd274  sar     r15, 1Ah
0x1800fd278  mov     rax, r15
0x1800fd27b  shr     rax, 3Fh
0x1800fd27f  add     r15, rax
0x1800fd282  lea     rsi, [r14+30h]
0x1800fd286  mov     rbx, [rsi]
0x1800fd289  mov     rbx, [rbx]
0x1800fd28c  cmp     [rbx+19h], r12b
0x1800fd290  jnz     loc_1800FD61C
0x1800fd296  lea     rdx, [rbx+20h]; struct Cache::KeyHolder *
0x1800fd29a  lea     rdi, [rdx+10h]
0x1800fd29e  mov     rax, [rdi+18h]
0x1800fd2a2  mov     rcx, r15
0x1800fd2a5  sub     rcx, rax
0x1800fd2a8  cmp     rcx, [r14+60h]
0x1800fd2ac  jz      loc_1800FD52D
0x1800fd2b2  jl      loc_1800FD52D
0x1800fd2b8  lea     rdx, ??_7?$ClassifiedStructuredObject@_J@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<__int64>::`vftable'
0x1800fd2bf  mov     [rsp+2A8h+var_148], rdx
0x1800fd2c7  lea     rcx, aMTimeoflastres; "m_timeOfLastResurrection"
0x1800fd2ce  mov     [rsp+2A8h+var_140], rcx
0x1800fd2d6  mov     rcx, [rdi+38h]
0x1800fd2da  mov     [rsp+2A8h+var_138], rcx
0x1800fd2e2  mov     [rsp+2A8h+var_130], r13w
0x1800fd2eb  xorps   xmm0, xmm0
0x1800fd2ee  movups  [rsp+2A8h+var_128], xmm0
0x1800fd2f6  movdqa  [rsp+2A8h+var_118], xmm6
0x1800fd2ff  mov     word ptr [rsp+2A8h+var_128], r12w
0x1800fd308  lea     r8, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800fd30f  mov     [rsp+2A8h+var_1B8], r8
0x1800fd317  lea     rcx, aMResurrectionc; "m_resurrectionCount"
0x1800fd31e  mov     [rsp+2A8h+var_1B0], rcx
0x1800fd326  mov     ecx, [rdi+30h]
0x1800fd329  mov     [rsp+2A8h+var_1A8], ecx
0x1800fd330  mov     [rsp+2A8h+var_1A4], r13w
0x1800fd339  movups  [rsp+2A8h+var_1A0], xmm0
0x1800fd341  movdqu  [rsp+2A8h+var_190], xmm6
0x1800fd34a  mov     word ptr [rsp+2A8h+var_1A0], r12w
0x1800fd353  mov     [rsp+2A8h+var_108], rdx
0x1800fd35b  lea     rcx, aMTimeoflastevi; "m_timeOfLastEviction"
0x1800fd362  mov     [rsp+2A8h+var_100], rcx
0x1800fd36a  mov     rcx, [rdi+28h]
0x1800fd36e  mov     [rsp+2A8h+var_F8], rcx
0x1800fd376  mov     [rsp+2A8h+var_F0], r13w
0x1800fd37f  movups  [rsp+2A8h+var_E8], xmm0
0x1800fd387  movdqa  [rsp+2A8h+var_D8], xmm6
0x1800fd390  mov     word ptr [rsp+2A8h+var_E8], r12w
0x1800fd399  mov     [rsp+2A8h+var_180], r8
0x1800fd3a1  lea     rcx, aMEvictioncount; "m_EvictionCount"
0x1800fd3a8  mov     [rsp+2A8h+var_178], rcx
0x1800fd3b0  mov     ecx, [rdi+20h]
0x1800fd3b3  mov     [rsp+2A8h+var_170], ecx
0x1800fd3ba  mov     [rsp+2A8h+var_16C], r13w
0x1800fd3c3  movups  [rsp+2A8h+var_168], xmm0
0x1800fd3cb  movdqu  [rsp+2A8h+var_158], xmm6
0x1800fd3d4  mov     word ptr [rsp+2A8h+var_168], r12w
0x1800fd3dd  mov     [rsp+2A8h+var_C8], rdx
0x1800fd3e5  lea     rcx, aMTimeoffirstev; "m_timeOfFirstEviction"
0x1800fd3ec  mov     [rsp+2A8h+var_C0], rcx
0x1800fd3f4  mov     [rsp+2A8h+var_B8], rax
0x1800fd3fc  mov     [rsp+2A8h+var_B0], r13w
0x1800fd405  movups  [rsp+2A8h+var_A8], xmm0
0x1800fd40d  movdqa  [rsp+2A8h+var_98], xmm6
0x1800fd416  mov     word ptr [rsp+2A8h+var_A8], r12w
0x1800fd41f  lea     rax, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1800fd426  mov     [rsp+2A8h+var_218], rax
0x1800fd42e  lea     rax, aCachetype; "cacheType"
0x1800fd435  mov     [rsp+2A8h+var_210], rax
0x1800fd43d  mov     ecx, [r14+70h]
0x1800fd441  call    sub_18000D7FC
0x1800fd446  mov     [rsp+2A8h+var_208], rax
0x1800fd44e  mov     [rsp+2A8h+var_200], r13w
0x1800fd457  movups  [rsp+2A8h+var_1F8], xmm0
0x1800fd45f  movdqa  [rsp+2A8h+var_1E8], xmm6
0x1800fd468  mov     word ptr [rsp+2A8h+var_1F8], r12w
0x1800fd471  lea     rax, aGfxCacheEvicte_0; "Gfx::Cache::EvictedMapTelemetryRollUp. "...
0x1800fd478  mov     [rsp+2A8h+var_238], rax
0x1800fd47d  lea     rax, [rsp+2A8h+var_148]
0x1800fd485  mov     [rsp+2A8h+var_258], rax
0x1800fd48a  lea     rax, [rsp+2A8h+var_1B8]
0x1800fd492  mov     [rsp+2A8h+var_260], rax
0x1800fd497  lea     rax, [rsp+2A8h+var_108]
0x1800fd49f  mov     [rsp+2A8h+var_268], rax
0x1800fd4a4  lea     rax, [rsp+2A8h+var_180]
0x1800fd4ac  mov     [rsp+2A8h+var_270], rax
0x1800fd4b1  lea     rax, [rsp+2A8h+var_C8]
0x1800fd4b9  mov     [rsp+2A8h+var_278], rax
0x1800fd4be  lea     rax, [rsp+2A8h+var_218]
0x1800fd4c6  mov     [rsp+2A8h+var_280], rax
0x1800fd4cb  lea     rax, [rsp+2A8h+var_238]
0x1800fd4d0  mov     [rsp+2A8h+var_288], rax
0x1800fd4d5  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@_J@23@U?$ClassifiedStructuredObject@I@23@U423@U523@U423@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@_J@01@$$QEAU?$ClassifiedStructuredObject@I@01@565@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<__int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<__int64> &&)
0x1800fd4da  lea     rcx, [rsp+2A8h+var_1F8]
0x1800fd4e2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd4e7  lea     rcx, [rsp+2A8h+var_A8]
0x1800fd4ef  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd4f4  lea     rcx, [rsp+2A8h+var_168]
0x1800fd4fc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd501  lea     rcx, [rsp+2A8h+var_E8]
0x1800fd509  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd50e  lea     rcx, [rsp+2A8h+var_1A0]
0x1800fd516  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd51b  lea     rcx, [rsp+2A8h+var_128]
0x1800fd523  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fd528  jmp     loc_1800FD5CD
0x1800fd52d  lea     rcx, [rsp+2A8h+var_218]; this
0x1800fd535  call    ??0KeyHolder@Cache@@QEAA@AEBV01@@Z; Cache::KeyHolder::KeyHolder(Cache::KeyHolder const &)
0x1800fd53a  mov     rdx, rdi; struct Cache::KeyHolder *
0x1800fd53d  lea     rcx, [rsp+2A8h+var_208]; this
0x1800fd545  call    ??0KeyHolder@Cache@@QEAA@AEBV01@@Z; Cache::KeyHolder::KeyHolder(Cache::KeyHolder const &)
0x1800fd54a  mov     eax, [rdi+10h]
0x1800fd54d  mov     dword ptr [rsp+2A8h+var_1F8], eax
0x1800fd554  mov     rax, [rdi+18h]
0x1800fd558  mov     qword ptr [rsp+2A8h+var_1F8+8], rax
0x1800fd560  mov     eax, [rdi+20h]
0x1800fd563  mov     dword ptr [rsp+2A8h+var_1E8], eax
0x1800fd56a  mov     rax, [rdi+28h]
0x1800fd56e  mov     qword ptr [rsp+2A8h+var_1E8+8], rax
0x1800fd576  mov     eax, [rdi+30h]
0x1800fd579  mov     [rsp+2A8h+var_1D8], eax
0x1800fd580  mov     rax, [rdi+38h]
0x1800fd584  mov     [rsp+2A8h+var_1D0], rax
0x1800fd58c  mov     eax, [rdi+40h]
0x1800fd58f  mov     [rsp+2A8h+var_1C8], eax
0x1800fd596  lea     r8, [rsp+2A8h+var_218]
0x1800fd59e  lea     rdx, [rsp+2A8h+var_228]
0x1800fd5a6  lea     rcx, [rsp+2A8h+Block]
0x1800fd5ab  call    ??$_Emplace@U?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@std@@@?$_Tree@V?$_Tmap_traits@VKeyHolder@Cache@@UValueEvictedCacheItems@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CBVKeyHolder@Cache@@UValueEvictedCacheItems@22@@1@@Z; std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueEvictedCacheItems,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>>,0>>::_Emplace<std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems>>(std::pair<Cache::KeyHolder const,Cache::Cache::ValueEvictedCacheItems> &&)
0x1800fd5b0  lea     rcx, [rsp+2A8h+var_208]; this
0x1800fd5b8  call    ??1KeyHolder@Cache@@UEAA@XZ; Cache::KeyHolder::~KeyHolder(void)
0x1800fd5bd  nop     dword ptr [rax]
0x1800fd5c0  lea     rcx, [rsp+2A8h+var_218]; this
0x1800fd5c8  call    ??1KeyHolder@Cache@@UEAA@XZ; Cache::KeyHolder::~KeyHolder(void)
0x1800fd5cd  mov     rax, [rbx+10h]
0x1800fd5d1  cmp     [rax+19h], r12b
0x1800fd5d5  jnz     short loc_1800FD5FB
0x1800fd5d7  mov     rbx, rax
0x1800fd5da  mov     rcx, [rax]
0x1800fd5dd  cmp     [rcx+19h], r12b
0x1800fd5e1  jnz     loc_1800FD28C
0x1800fd5e7  mov     rbx, rcx
0x1800fd5ea  mov     rax, [rcx]
0x1800fd5ed  mov     rcx, rax
0x1800fd5f0  cmp     [rax+19h], r12b
0x1800fd5f4  jz      short loc_1800FD5E7
0x1800fd5f6  jmp     loc_1800FD28C
0x1800fd5fb  mov     rax, [rbx+8]
0x1800fd5ff  cmp     [rax+19h], r12b
0x1800fd603  jnz     short loc_1800FD614
0x1800fd605  cmp     rbx, [rax+10h]
0x1800fd609  jnz     short loc_1800FD614
0x1800fd60b  mov     rbx, rax
0x1800fd60e  mov     rax, [rax+8]
0x1800fd612  jmp     short loc_1800FD5FF
0x1800fd614  mov     rbx, rax
0x1800fd617  jmp     loc_1800FD28C
0x1800fd61c  lea     rax, [rsp+2A8h+Block]
0x1800fd621  cmp     rsi, rax
0x1800fd624  jz      short loc_1800FD699
  ... truncated ...
```
