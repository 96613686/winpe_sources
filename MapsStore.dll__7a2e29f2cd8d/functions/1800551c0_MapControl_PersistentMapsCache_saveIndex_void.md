# MapControl::PersistentMapsCache::saveIndex(void)

- ea: `0x1800551c0`
- end: `0x1800554c6`
- name: `?saveIndex@PersistentMapsCache@MapControl@@UEAAXXZ`
- size: `774`
- prototype: `void __fastcall(MapControl::PersistentMapsCache *__hidden this)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x18000d090`
- `0x18000dcb0`
- `0x180011d28`
- `0x180011d90`
- `0x180012720`
- `0x1800140f0`
- `0x180016770`
- `0x180016cbc`
- `0x180017aa8`
- `0x18001b9e0`
- `0x18001d0e4`
- `0x18002dd30`
- `0x18002de08`
- `0x18002f724`
- `0x18002f774`
- `0x18002f7b4`
- `0x18002f99c`
- `0x18002f9c4`
- `0x180039a9c`
- `0x18003c84c`
- `0x18003f138`
- `0x1800403ac`
- `0x18004df64`
- `0x18004f5c4`
- `0x1800551c0`
- `0x1800554cc`
- `0x180077bdc`
- `0x180077ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005523f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005523f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055313`

## string_xrefs

- `0x18005540a`: `mapscache`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall MapControl::PersistentMapsCache::saveIndex(MapControl::PersistentMapsCache *this)
{
  RTL_SRWLOCK *Instance; // rbx
  unsigned __int64 v3; // rbx
  char *v4; // rdi
  char *v5; // rax
  size_t v6; // rbx
  __int64 v7; // r14
  _QWORD **v8; // rdi
  _QWORD *i; // rbx
  char *v10; // rcx
  MapControl::PersistentMapsCache *v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  bool v14; // bl
  __int64 v15; // rax
  unsigned __int16 DirectorySeparator; // ax
  char *v17; // [rsp+30h] [rbp-D0h] BYREF
  void *v18[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h]
  char v20[8]; // [rsp+50h] [rbp-B0h] BYREF
  MapControl::PersistentMapsCache *v21; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v22; // [rsp+60h] [rbp-A0h]
  std::_Ref_count_base *v23[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall *v24)(); // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h] BYREF
  char v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  _BYTE v28[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v29[40]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v30[3]; // [rsp+D0h] [rbp-30h] BYREF
  char v31; // [rsp+E8h] [rbp-18h]
  __int64 v32; // [rsp+F0h] [rbp-10h]
  _QWORD *v33; // [rsp+108h] [rbp+8h]

  Instance = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<MapControl::DataLoaderPerformanceTracer>::getInstance();
  Pal::PerformanceTracer::traceEvent<>(Instance, (struct Pal::PerformanceEventId *)&dword_1800F10C0);
  Pal::ScopedPerformanceSpan::ScopedPerformanceSpan(
    (Pal::ScopedPerformanceSpan *)v28,
    (struct Pal::PerformanceTracer *)Instance,
    (const struct Pal::PerformanceEventId *)&dword_1800F10CC);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(v18);
  Pal::ManualResetEvent::ManualResetEvent((Pal::ManualResetEvent *)v20);
  *(_OWORD *)v23 = 0;
  v21 = (MapControl::PersistentMapsCache *)((char *)this + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  v3 = 32LL * *((_QWORD *)this + 29) + 8;
  v4 = (char *)v18[1];
  if ( v3 < (char *)v18[1] - (char *)v18[0] )
  {
    v5 = (char *)v18[0] + v3;
LABEL_7:
    v18[1] = v5;
    goto LABEL_8;
  }
  if ( v3 > (char *)v18[1] - (char *)v18[0] )
  {
    if ( v3 <= v19 - (unsigned __int64)v18[0] )
    {
      v6 = v3 - ((char *)v18[1] - (char *)v18[0]);
      memset_0(v18[1], 0, v6);
      v5 = &v4[v6];
      goto LABEL_7;
    }
    std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(v18, 32LL * *((_QWORD *)this + 29) + 8);
  }
LABEL_8:
  *(_QWORD *)v18[0] = 0x32302E312049434DLL;
  v7 = 8;
  v8 = (_QWORD **)*((_QWORD *)this + 28);
  for ( i = *v8; i != v8; i = (_QWORD *)*i )
  {
    std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
      &v21,
      i + 4);
    v10 = (char *)v18[0];
    v11 = v21;
    *(_OWORD *)((char *)v18[0] + v7) = *(_OWORD *)v21;
    *(_OWORD *)&v10[v7 + 16] = *((_OWORD *)v11 + 1);
    v7 += 32;
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  v12 = Pal::IO::beginWriteFile((unsigned int)&v21, (int)this + 304, v18[0], v7, *((_DWORD *)this + 96));
  std::shared_ptr<MapControl::LocalIndex>::operator=(v23, v12);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  v17 = v20;
  v21 = this;
  v24 = MapControl::PersistentMapsCache::indexWriteDone;
  std::tuple<MapControl::PersistentMapsCache *,std::_Ph<1>,Pal::ManualResetEvent *>::tuple<MapControl::PersistentMapsCache *,std::_Ph<1>,Pal::ManualResetEvent *>(
    &v25,
    &v21,
    v13,
    &v17);
  v30[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::PersistentMapsCache::*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),MapControl::PersistentMapsCache *,std::_Ph<1> const &,Pal::ManualResetEvent *>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable';
  v30[1] = v24;
  v30[2] = v25;
  v31 = v26;
  v32 = v27;
  v33 = v30;
  Pal::AsyncOperation<unsigned __int64>::setCallback(v23[0], v30);
  std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>> &>::_Tidy(v30);
  Pal::ManualResetEvent::wait((Pal::ManualResetEvent *)v20);
  v14 = 0;
  LODWORD(v17) = 0;
  v15 = Pal::LocalSettingsSingleton<MapControl::DataLoaderLocalSettings>::getInstance();
  if ( (unsigned __int8)Pal::LocalSettings::querySetting<int>(
                          v15,
                          &MapControl::DataLoaderLocalSettings::sSavePersistentMapCacheIndexAsCsvSetting,
                          &v17) )
    v14 = (_DWORD)v17 != 0;
  std::wstring::wstring(v29, L"mapscache");
  DirectorySeparator = Pal::IO::getDirectorySeparator();
  std::wstring::append(v29, 1, DirectorySeparator);
  std::wstring::append(v29, L"index.csv");
  if ( v14 )
    MapControl::PersistentMapsCache::saveIndexAsCsv((__int64)this, (int)v29);
  std::wstring::_Tidy_deallocate(v29);
  if ( v23[1] )
    std::_Ref_count_base::_Decref(v23[1]);
  std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(v20);
  if ( v18[0] )
  {
    std::_Deallocate<16>(v18[0], v19 - (unsigned __int64)v18[0]);
    *(_OWORD *)v18 = 0;
    v19 = 0;
  }
  Pal::ScopedPerformanceSpan::~ScopedPerformanceSpan((Pal::ScopedPerformanceSpan *)v28);
}

```

## disassembly

```asm
0x1800551c0  push    rbp
0x1800551c2  push    rbx
0x1800551c3  push    rsi
0x1800551c4  push    rdi
0x1800551c5  push    r14
0x1800551c7  push    r15
0x1800551c9  lea     rbp, [rsp-28h]
0x1800551ce  sub     rsp, 128h
0x1800551d5  mov     rax, cs:__security_cookie
0x1800551dc  xor     rax, rsp
0x1800551df  mov     [rbp+50h+var_40], rax
0x1800551e3  mov     r15, rcx
0x1800551e6  call    ?getInstance@?$PerformanceTracerSingleton@VDataLoaderPerformanceTracer@MapControl@@@Pal@@KAAEAVDataLoaderPerformanceTracer@MapControl@@XZ; Pal::PerformanceTracerSingleton<MapControl::DataLoaderPerformanceTracer>::getInstance(void)
0x1800551eb  mov     rbx, rax
0x1800551ee  lea     rdx, dword_1800F10C0; struct Pal::PerformanceEventId *
0x1800551f5  mov     rcx, rax; SRWLock
0x1800551f8  call    ??$traceEvent@$$V@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@@Z; Pal::PerformanceTracer::traceEvent<>(Pal::PerformanceEventId const &)
0x1800551fd  lea     r8, dword_1800F10CC; struct Pal::PerformanceEventId *
0x180055204  mov     rdx, rbx; struct Pal::PerformanceTracer *
0x180055207  lea     rcx, [rbp+50h+var_B8]; this
0x18005520b  call    ??0ScopedPerformanceSpan@Pal@@QEAA@PEAVPerformanceTracer@1@AEBVPerformanceEventId@1@@Z; Pal::ScopedPerformanceSpan::ScopedPerformanceSpan(Pal::PerformanceTracer *,Pal::PerformanceEventId const &)
0x180055210  nop
0x180055211  lea     rcx, [rsp+150h+var_118]; void *
0x180055216  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(std::allocator<std::pair<std::wstring const,std::pair<int,unsigned __int64>>> const &)
0x18005521b  nop
0x18005521c  lea     rcx, [rsp+150h+var_100]; this
0x180055221  call    ??0ManualResetEvent@Pal@@QEAA@XZ; Pal::ManualResetEvent::ManualResetEvent(void)
0x180055226  nop
0x180055227  xorps   xmm0, xmm0
0x18005522a  movdqu  xmmword ptr [rsp+150h+var_E8], xmm0
0x180055230  lea     rsi, [r15+0B0h]
0x180055237  mov     [rsp+150h+var_F8], rsi
0x18005523c  mov     rcx, rsi; lpCriticalSection
0x18005523f  call    cs:__imp_EnterCriticalSection
0x180055245  nop
0x180055246  mov     rbx, [r15+0E8h]
0x18005524d  shl     rbx, 5
0x180055251  add     rbx, 8
0x180055255  mov     rdx, [rsp+150h+var_118]
0x18005525a  mov     rdi, [rsp+150h+var_118+8]
0x18005525f  mov     rcx, rdi
0x180055262  sub     rcx, rdx
0x180055265  cmp     rbx, rcx
0x180055268  jnb     short loc_180055270
0x18005526a  lea     rax, [rbx+rdx]
0x18005526e  jmp     short loc_1800552A2
0x180055270  jbe     short loc_1800552A7
0x180055272  mov     rax, [rsp+150h+var_108]
0x180055277  sub     rax, rdx
0x18005527a  cmp     rbx, rax
0x18005527d  jbe     short loc_18005528E
0x18005527f  mov     rdx, rbx
0x180055282  lea     rcx, [rsp+150h+var_118]
0x180055287  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005528c  jmp     short loc_1800552A7
0x18005528e  sub     rbx, rcx
0x180055291  mov     r8, rbx; Size
0x180055294  xor     edx, edx; Val
0x180055296  mov     rcx, rdi; void *
0x180055299  call    memset_0
0x18005529e  lea     rax, [rbx+rdi]
0x1800552a2  mov     [rsp+150h+var_118+8], rax
0x1800552a7  mov     rcx, 32302E312049434Dh
0x1800552b1  mov     rax, [rsp+150h+var_118]
0x1800552b6  mov     [rax], rcx
0x1800552b9  mov     r14d, 8
0x1800552bf  mov     rdi, [r15+0E0h]
0x1800552c6  mov     rbx, [rdi]
0x1800552c9  cmp     rbx, rdi
0x1800552cc  jz      short loc_180055310
0x1800552ce  lea     rdx, [rbx+20h]
0x1800552d2  lea     rcx, [rsp+150h+var_F8]
0x1800552d7  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x1800552dc  mov     rcx, [rsp+150h+var_118]
0x1800552e1  mov     rax, [rsp+150h+var_F8]
0x1800552e6  movups  xmm0, xmmword ptr [rax]
0x1800552e9  movups  xmmword ptr [rcx+r14], xmm0
0x1800552ee  movups  xmm1, xmmword ptr [rax+10h]
0x1800552f2  movups  xmmword ptr [rcx+r14+10h], xmm1
0x1800552f8  add     r14, 20h ; ' '
0x1800552fc  mov     rcx, [rsp+150h+var_F0]; this
0x180055301  test    rcx, rcx
0x180055304  jz      short loc_18005530B
0x180055306  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005530b  mov     rbx, [rbx]
0x18005530e  jmp     short loc_1800552C9
0x180055310  mov     rcx, rsi; lpCriticalSection
0x180055313  call    cs:__imp_LeaveCriticalSection
0x180055319  lea     rdx, [r15+130h]
0x180055320  mov     eax, [r15+180h]
0x180055327  mov     [rsp+150h+var_130], eax
0x18005532b  mov     r9, r14
0x18005532e  mov     r8, [rsp+150h+var_118]
0x180055333  lea     rcx, [rsp+150h+var_F8]
0x180055338  call    ?beginWriteFile@IO@Pal@@SA?AV?$shared_ptr@V?$AsyncOperation@_K@Pal@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEBX_KW4FileLocation@2@@Z; Pal::IO::beginWriteFile(std::wstring const &,void const *,unsigned __int64,Pal::FileLocation)
0x18005533d  mov     rdx, rax
0x180055340  lea     rcx, [rsp+150h+var_E8]
0x180055345  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x18005534a  mov     rcx, [rsp+150h+var_F0]; this
0x18005534f  test    rcx, rcx
0x180055352  jz      short loc_180055359
0x180055354  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180055359  lea     rax, [rsp+150h+var_100]
0x18005535e  mov     [rsp+150h+var_120], rax
0x180055363  mov     [rsp+150h+var_F8], r15
0x180055368  lea     rax, ?indexWriteDone@PersistentMapsCache@MapControl@@AEAAXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@4@@Z; MapControl::PersistentMapsCache::indexWriteDone(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *)
0x18005536f  mov     [rsp+150h+var_D8], rax
0x180055374  lea     r9, [rsp+150h+var_120]
0x180055379  lea     rdx, [rsp+150h+var_F8]
0x18005537e  lea     rcx, [rbp+50h+var_D0]
0x180055382  call    ??$?0PEAVPersistentMapsCache@MapControl@@AEBU?$_Ph@$00@std@@PEAVManualResetEvent@Pal@@$0A@@?$tuple@PEAVPersistentMapsCache@MapControl@@U?$_Ph@$00@std@@PEAVManualResetEvent@Pal@@@std@@QEAA@$$QEAPEAVPersistentMapsCache@MapControl@@AEBU?$_Ph@$00@1@$$QEAPEAVManualResetEvent@Pal@@@Z; std::tuple<MapControl::PersistentMapsCache *,std::_Ph<1>,Pal::ManualResetEvent *>::tuple<MapControl::PersistentMapsCache *,std::_Ph<1>,Pal::ManualResetEvent *>(MapControl::PersistentMapsCache * &&,std::_Ph<1> const &,Pal::ManualResetEvent * &&)
0x180055387  lea     rcx, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8PersistentMapsCache@MapControl@@EAAXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@6@@ZPEAV34@AEBU?$_Ph@$00@2@PEAV76@@std@@XAEAV?$AsyncOperation@_K@Pal@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::PersistentMapsCache::*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),MapControl::PersistentMapsCache *,std::_Ph<1> const &,Pal::ManualResetEvent *>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable'
0x18005538e  mov     [rbp+50h+var_80], rcx
0x180055392  mov     rax, [rsp+150h+var_D8]
0x180055397  mov     [rbp+50h+var_78], rax
0x18005539b  mov     rax, [rbp+50h+var_D0]
0x18005539f  mov     [rbp+50h+var_70], rax
0x1800553a3  mov     al, [rbp+50h+var_C8]
0x1800553a6  mov     [rbp+50h+var_68], al
0x1800553a9  mov     rax, [rbp+50h+var_C0]
0x1800553ad  mov     [rbp+50h+var_60], rax
0x1800553b1  lea     rax, [rbp+50h+var_80]
0x1800553b5  mov     [rbp+50h+var_48], rax
0x1800553b9  lea     rdx, [rbp+50h+var_80]
0x1800553bd  mov     rcx, [rsp+150h+var_E8]
0x1800553c2  call    ?setCallback@?$AsyncOperation@_K@Pal@@QEAAXAEBV?$function@$$A6AXAEAV?$AsyncOperation@_K@Pal@@@Z@std@@@Z; Pal::AsyncOperation<unsigned __int64>::setCallback(std::function<void (Pal::AsyncOperation<unsigned __int64> &)> const &)
0x1800553c7  nop
0x1800553c8  lea     rcx, [rbp+50h+var_80]
0x1800553cc  call    ?_Tidy@?$_Func_class@XAEAV?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@IEAAXXZ; std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>> &>::_Tidy(void)
0x1800553d1  lea     rcx, [rsp+150h+var_100]; this
0x1800553d6  call    ?wait@ManualResetEvent@Pal@@QEAAXXZ; Pal::ManualResetEvent::wait(void)
0x1800553db  xor     bl, bl
0x1800553dd  mov     dword ptr [rsp+150h+var_120], 0
0x1800553e5  call    ?getInstance@?$LocalSettingsSingleton@VDataLoaderLocalSettings@MapControl@@@Pal@@KAAEAVDataLoaderLocalSettings@MapControl@@XZ; Pal::LocalSettingsSingleton<MapControl::DataLoaderLocalSettings>::getInstance(void)
0x1800553ea  lea     r8, [rsp+150h+var_120]
0x1800553ef  lea     rdx, ?sSavePersistentMapCacheIndexAsCsvSetting@DataLoaderLocalSettings@MapControl@@0VLocalSettingId@Pal@@B; Pal::LocalSettingId const MapControl::DataLoaderLocalSettings::sSavePersistentMapCacheIndexAsCsvSetting
0x1800553f6  mov     rcx, rax
0x1800553f9  call    ??$querySetting@H@LocalSettings@Pal@@IEAA_NAEBVLocalSettingId@1@PEAH@Z; Pal::LocalSettings::querySetting<int>(Pal::LocalSettingId const &,int *)
0x1800553fe  test    al, al
0x180055400  jz      short loc_18005540A
0x180055402  cmp     dword ptr [rsp+150h+var_120], 0
0x180055407  setnz   bl
0x18005540a  lea     rdx, aMapscache_0; "mapscache"
0x180055411  lea     rcx, [rbp+50h+var_A8]
0x180055415  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005541a  nop
0x18005541b  call    ?getDirectorySeparator@IO@Pal@@SAGXZ; Pal::IO::getDirectorySeparator(void)
0x180055420  movzx   r8d, ax
0x180055424  mov     edx, 1
0x180055429  lea     rcx, [rbp+50h+var_A8]
0x18005542d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180055432  lea     rdx, aIndexCsv; "index.csv"
0x180055439  lea     rcx, [rbp+50h+var_A8]
0x18005543d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180055442  test    bl, bl
0x180055444  jz      short loc_180055453
0x180055446  lea     rdx, [rbp+50h+var_A8]
0x18005544a  mov     rcx, r15
0x18005544d  call    ?saveIndexAsCsv@PersistentMapsCache@MapControl@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::PersistentMapsCache::saveIndexAsCsv(std::wstring const &)
0x180055452  nop
0x180055453  lea     rcx, [rbp+50h+var_A8]
0x180055457  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005545c  nop
0x18005545d  mov     rcx, [rsp+150h+var_E8+8]; this
0x180055462  test    rcx, rcx
0x180055465  jz      short loc_18005546D
0x180055467  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005546c  nop
0x18005546d  lea     rcx, [rsp+150h+var_100]
0x180055472  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x180055477  nop
0x180055478  mov     rcx, [rsp+150h+var_118]
0x18005547d  test    rcx, rcx
0x180055480  jz      short loc_1800554A1
0x180055482  mov     rdx, [rsp+150h+var_108]
0x180055487  sub     rdx, rcx
0x18005548a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005548f  xorps   xmm0, xmm0
0x180055492  movdqu  xmmword ptr [rsp+150h+var_118], xmm0
0x180055498  mov     [rsp+150h+var_108], 0
0x1800554a1  lea     rcx, [rbp+50h+var_B8]; this
0x1800554a5  call    ??1ScopedPerformanceSpan@Pal@@QEAA@XZ; Pal::ScopedPerformanceSpan::~ScopedPerformanceSpan(void)
0x1800554aa  mov     rcx, [rbp+50h+var_40]
0x1800554ae  xor     rcx, rsp; StackCookie
0x1800554b1  call    __security_check_cookie
0x1800554b6  add     rsp, 128h
0x1800554bd  pop     r15
0x1800554bf  pop     r14
0x1800554c1  pop     rdi
0x1800554c2  pop     rsi
0x1800554c3  pop     rbx
0x1800554c4  pop     rbp
0x1800554c5  retn
```
