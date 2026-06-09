# FontSetCache::Update(uint)

- ea: `0x18006a2dc`
- end: `0x18006ab29`
- name: `?Update@FontSetCache@@AEAAJI@Z`
- size: `2125`
- prototype: `__int64 __fastcall(FontSetCache *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `35`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180068494`
- `0x180068b20`

## callees

- `0x180004810`
- `0x180007668`
- `0x18000d55c`
- `0x18000ff38`
- `0x180010cc4`
- `0x180010d4c`
- `0x180010dc4`
- `0x1800113a4`
- `0x180011a2c`
- `0x1800124b8`
- `0x1800124f4`
- `0x180013e1c`
- `0x18002bc8c`
- `0x180041d18`
- `0x18004fecc`
- `0x180067e1c`
- `0x18006a2dc`
- `0x18006ab30`
- `0x18006ab6c`
- `0x18006ab98`
- `0x18006abbc`
- `0x18006abdc`
- `0x18006bc24`
- `0x18006bf70`
- `0x18006c090`
- `0x18006c0ec`
- `0x18006c198`
- `0x1800a2230`
- `0x1800a3560`
- `0x1800a4120`
- `0x1800a4868`
- `0x1800aaa58`
- `0x1800b0218`
- `0x1800b8024`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a36d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a36d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006aa96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006aa96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a9dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a9dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall FontSetCache::Update(FontSetCache *this, unsigned int a2)
{
  struct CacheWriter *v3; // rsi
  bool v4; // bl
  unsigned int v5; // r14d
  int v6; // ebx
  bool v7; // dl
  __int64 v8; // rdi
  struct CacheWriter **v9; // rax
  struct CacheWriter *v10; // rbx
  __int64 v11; // rcx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  struct FontCacheStorage *v14; // rbx
  unsigned int v15; // edx
  struct FontSetBuilder **v16; // rcx
  struct FontSetBuilder *v17; // rax
  unsigned int v18; // r11d
  unsigned int v19; // r10d
  unsigned __int8 v20; // cl
  __int64 v21; // rbx
  FontCacheStorage *v22; // rax
  FontCacheStorage *v23; // rax
  _QWORD *v24; // rax
  unsigned int v25; // r9d
  volatile signed __int32 *v26; // rcx
  unsigned int v27; // edx
  struct IExceptionHandler *v28; // rcx
  int v30; // [rsp+28h] [rbp-1F0h]
  unsigned int v31; // [rsp+50h] [rbp-1C8h]
  bool v32[4]; // [rsp+54h] [rbp-1C4h]
  bool v33[4]; // [rsp+54h] [rbp-1C4h]
  unsigned int v34; // [rsp+58h] [rbp-1C0h]
  unsigned int v35; // [rsp+5Ch] [rbp-1BCh]
  unsigned int v36; // [rsp+60h] [rbp-1B8h]
  void *v37; // [rsp+68h] [rbp-1B0h] BYREF
  int v38; // [rsp+70h] [rbp-1A8h]
  int v39; // [rsp+74h] [rbp-1A4h]
  unsigned int v40; // [rsp+78h] [rbp-1A0h]
  struct FontSetBuilder *v41; // [rsp+80h] [rbp-198h]
  struct FontCacheStorage *v42; // [rsp+88h] [rbp-190h] BYREF
  unsigned int v43[2]; // [rsp+90h] [rbp-188h]
  struct CacheWriter *v44; // [rsp+98h] [rbp-180h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-178h] BYREF
  struct FontSetBuilder *v46; // [rsp+A8h] [rbp-170h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-168h] BYREF
  _BYTE v48[8]; // [rsp+B8h] [rbp-160h] BYREF
  _BYTE v49[24]; // [rsp+C0h] [rbp-158h] BYREF
  __int64 v50; // [rsp+D8h] [rbp-140h] BYREF
  _BYTE v51[8]; // [rsp+E0h] [rbp-138h] BYREF
  _BYTE v52[24]; // [rsp+E8h] [rbp-130h] BYREF
  __int64 v53; // [rsp+100h] [rbp-118h] BYREF
  FontCollectionBuilder *v54; // [rsp+108h] [rbp-110h] BYREF
  struct FontCacheStorage *v55; // [rsp+110h] [rbp-108h]
  void *v56[3]; // [rsp+118h] [rbp-100h] BYREF
  _BYTE v57[40]; // [rsp+130h] [rbp-E8h] BYREF
  _BYTE v58[8]; // [rsp+158h] [rbp-C0h] BYREF
  _BYTE v59[8]; // [rsp+160h] [rbp-B8h] BYREF
  _BYTE v60[8]; // [rsp+168h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+170h] [rbp-A8h] BYREF
  __int64 v62; // [rsp+178h] [rbp-A0h]
  _BYTE v63[16]; // [rsp+190h] [rbp-88h] BYREF
  _BYTE v64[24]; // [rsp+1A0h] [rbp-78h] BYREF
  _BYTE v65[96]; // [rsp+1B8h] [rbp-60h] BYREF
  DWriteTraceLogging::TraceLoggingEventSink *v67; // [rsp+230h] [rbp+18h]
  unsigned __int8 v68; // [rsp+230h] [rbp+18h]
  unsigned __int8 MissingRequiredFonts; // [rsp+238h] [rbp+20h]

  v3 = 0;
  v38 = 0;
  v56[1] = (void *)0x657461647075LL;
  v40 = 0;
  *((_QWORD *)this + 3) = 0x657461647075LL;
  EventLogger::LogEvent<EventTag,unsigned int>((_DWORD)this + 16, 1953394502, 1952543859, 1633972341, a2);
  v67 = (DWriteTraceLogging::TraceLoggingEventSink *)operator new(0x20u);
  v4 = *((_DWORD *)this + 8) == 0;
  DWriteTraceLogging::TraceLoggingEventSink::TraceLoggingEventSink(v67);
  *(_QWORD *)v67 = &DWriteTraceLogging::FontSetTraceLoggingEventSink::`vftable';
  *((_DWORD *)v67 + 4) = GetCurrentThreadId();
  *((_DWORD *)v67 + 5) = 0;
  *((_BYTE *)v67 + 24) = v4;
  *((_BYTE *)v67 + 25) = 0;
  EventSinkSetter<DWriteTraceLogging::FontSetTraceLoggingEventSink>::EventSinkSetter<DWriteTraceLogging::FontSetTraceLoggingEventSink>(
    &v45,
    v67);
  v5 = 0;
  v35 = 0;
  *(_QWORD *)v43 = 0;
  v39 = 0;
  MissingRequiredFonts = 0;
  BYTE2(v31) = 0;
  v68 = 0;
  LOBYTE(v31) = 0;
  v6 = 0;
  *(_DWORD *)v32 = 0;
  v44 = 0;
  FontSetCache::GetCurrentFontCacheStorage(this, &v53);
  try
  {
    v8 = v53;
    if ( v53 )
    {
      v9 = (struct CacheWriter **)(*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v53 + 72LL))(v53, &v37);
      v10 = 0;
      if ( v9 != &v44 )
      {
        v3 = *v9;
        *v9 = 0;
        v44 = v3;
        ReleaseReference<CacheWriter>(0);
        v10 = v3;
      }
      ReleaseReference<CacheWriter>((volatile signed __int32 *)v37);
      v5 = *(_DWORD *)(*((_QWORD *)v10 + 9) + 32LL);
      v35 = v5;
      FontSetCache::GetFontCollectionFromCacheWriter(v57, v3);
      *(_QWORD *)v43 = 0xAAAAAAAAAAAAAAABuLL * ((v62 - v61) >> 2);
      v39 = -1431655765 * ((v62 - v61) >> 2);
      if ( !*((_DWORD *)this + 8) )
      {
        MissingRequiredFonts = FontSetCache::GetMissingRequiredFonts(v57);
        BYTE2(v31) = MissingRequiredFonts;
      }
      std::vector<GlyphDependencyRegion::GlyphToListMapping>::_Tidy(v65);
      std::vector<unsigned __int64>::~vector<unsigned __int64>(v64);
      std::_Tree_val<std::_Tree_simple_types<std::pair<StringCheckedPtr const,unsigned int>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<StringCheckedPtr const,unsigned int>,void *>>>(
        v63,
        v63);
      std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(&v61);
      RefCountedArray<unsigned char>::~RefCountedArray<unsigned char>(v60);
      IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(v59);
      RefCountedArray<unsigned char>::~RefCountedArray<unsigned char>(v58);
      v6 = 0;
    }
    v11 = *((_QWORD *)this + 11);
    if ( !v11
      || (BYTE1(v31) = 1,
          !(*(unsigned int (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v11 + 80LL))(
             v11,
             (char *)this + 104,
             v5)) )
    {
      BYTE1(v31) = 0;
    }
    v12 = 0x80000000;
    if ( v5 != -1 )
      v12 = v5 + 1;
    v36 = v12;
    v42 = 0;
    v47 = 0;
    ManualResetEvent::ManualResetEvent((ManualResetEvent *)v48, v7);
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v49);
    while ( 1 )
    {
      *(_DWORD *)(v45 + 20) = v6;
      v41 = 0;
      v46 = 0;
      v50 = 0;
      ManualResetEvent::ManualResetEvent((ManualResetEvent *)v51, v13);
      std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v52);
      v14 = 0;
      v55 = 0;
      LOBYTE(v30) = BYTE1(v31);
      v16 = (struct FontSetBuilder **)FontSetCache::EnumerateAndCreateBuilderIfNeeded(this, &v54, a2, v3, &v50, v30);
      v37 = 0;
      if ( v16 != &v46 )
      {
        v41 = *v16;
        v17 = v41;
        *v16 = 0;
        v46 = v17;
        v37 = v17;
      }
      if ( v54 )
        FontCollectionBuilder::`scalar deleting destructor'(v54, v15);
      if ( v37 )
      {
        *((_QWORD *)this + 3) = 0x646C6975626572LL;
        EventLogger::LogEvent<EventTag>(
          (unsigned int *)this + 4,
          0x746553746E6F46LL,
          0x6574617473LL,
          0x646C6975626572LL);
        FontSetCache::AddFontProviderFonts(this, v41, v36);
        v21 = *((_QWORD *)this + 8);
        EventLogger::LogEvent<EventTag>((unsigned int *)this + 4, 0x746553746E6F46LL, 1701536109, 0x656761726F7453LL);
        v22 = (FontCacheStorage *)operator new(0x70u);
        v23 = FontCacheStorage::FontCacheStorage(v22, (const wchar_t *)(v21 + 8));
        v14 = v23;
        if ( v23 )
          (*(void (__fastcall **)(FontCacheStorage *))(*(_QWORD *)v23 + 8LL))(v23);
        v55 = v14;
        ComPtr<FontCacheStorage>::Deref(0);
        FontSetCache::CreateFontSetCacheInstance(
          v14,
          (FontSetCache *)((char *)this + 56),
          (const wchar_t *)(*((_QWORD *)this + 8) + 8LL),
          v3,
          v36,
          v41);
        v24 = (_QWORD *)(*(__int64 (__fastcall **)(struct FontCacheStorage *, void **))(*(_QWORD *)v14 + 72LL))(
                          v14,
                          v56);
        FontSetCache::GetFontCollectionFromCacheWriter(v57, *v24);
        ReleaseReference<CacheWriter>((volatile signed __int32 *)v56[0]);
        v34 = v36;
        v37 = (void *)(0xAAAAAAAAAAAAAAABuLL * ((v62 - v61) >> 2));
        if ( !*((_DWORD *)this + 8) )
        {
          v68 = FontSetCache::GetMissingRequiredFonts(v57);
          LOBYTE(v31) = v68;
        }
        v38 |= 3u;
        std::vector<GlyphDependencyRegion::GlyphToListMapping>::_Tidy(v65);
        std::vector<unsigned __int64>::~vector<unsigned __int64>(v64);
        std::_Tree_val<std::_Tree_simple_types<std::pair<StringCheckedPtr const,unsigned int>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<StringCheckedPtr const,unsigned int>,void *>>>(
          v63,
          v63);
        std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(&v61);
        RefCountedArray<unsigned char>::~RefCountedArray<unsigned char>(v60);
        IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(v59);
        RefCountedArray<unsigned char>::~RefCountedArray<unsigned char>(v58);
        v19 = (unsigned int)v37;
        v18 = v43[0];
        v20 = v68;
        LOBYTE(v15) = MissingRequiredFonts;
      }
      else
      {
        v34 = v35;
        v18 = v43[0];
        v19 = v43[0];
        LOBYTE(v15) = MissingRequiredFonts;
        v20 = MissingRequiredFonts;
        v68 = MissingRequiredFonts;
        LOBYTE(v31) = MissingRequiredFonts;
      }
      if ( !*(_BYTE *)(v45 + 25) && !v20 && !(_BYTE)v15 && !*(_DWORD *)v32 )
        break;
      v25 = (unsigned __int8)v15;
      LOBYTE(v15) = *((_DWORD *)this + 8) == 0;
      DWriteTraceLogging::LogFontSetCacheUpdateResult(
        v20 != 0 ? (DWriteTraceLogging *)0x88985002LL : 0,
        v15,
        1,
        v32[0],
        v35,
        v18,
        v25,
        v34,
        v19,
        v20,
        v31);
      if ( *(_DWORD *)v33 || !v68 )
        break;
      v26 = (volatile signed __int32 *)v3;
      v3 = 0;
      v44 = 0;
      ReleaseReference<CacheWriter>(v26);
      if ( v14 )
        (*(void (__fastcall **)(struct FontCacheStorage *))(*(_QWORD *)v14 + 16LL))(v14);
      std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Tidy(v52);
      Event::~Event((Event *)v51);
      RegistryKey::Close((RegistryKey *)&v50);
      if ( v41 )
        FontCollectionBuilder::`scalar deleting destructor'(v41, v13);
      v6 = *(_DWORD *)v33 + 1;
      *(_DWORD *)v32 = *(_DWORD *)v33 + 1;
    }
    RegistryKey::operator=(&v47, &v50);
    ScopedHandle<EventHandlePolicy,void *>::operator=(v48, v51);
    std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::operator=(v49, v52);
    v42 = v14;
    ComPtr<FontCacheStorage>::Deref(0);
    std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Tidy(v52);
    Event::~Event((Event *)v51);
    RegistryKey::Close((RegistryKey *)&v50);
    if ( v41 )
      FontCollectionBuilder::`scalar deleting destructor'(v41, v27);
    if ( v14 )
      FontCacheStorage::Flush(
        (HANDLE *)v14,
        (FontSetCache *)((char *)this + 56),
        (const wchar_t *)(*((_QWORD *)this + 8) + 8LL));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    if ( v14 )
    {
      ComPtr<FontCacheStorage>::operator=((char *)this + 256, &v42);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 56LL))(v8);
      v14 = v42;
    }
    std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::operator=((char *)this + 192, v49);
    ScopedHandle<EventHandlePolicy,void *>::operator=((char *)this + 184, v48);
    if ( &v47 != (__int64 *)((char *)this + 176) )
    {
      RegistryKey::Close((FontSetCache *)((char *)this + 176));
      *((_QWORD *)this + 22) = v47;
      v47 = 0;
    }
    *((_QWORD *)this + 3) = 0x64696C6176LL;
    EventLogger::LogEvent<EventTag>((unsigned int *)this + 4, 0x746553746E6F46LL, 0x6574617473LL, 0x64696C6176LL);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Tidy(v49);
    Event::~Event((Event *)v48);
    RegistryKey::Close((RegistryKey *)&v47);
    if ( v14 )
      (*(void (__fastcall **)(struct FontCacheStorage *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    ReleaseReference<CacheWriter>((volatile signed __int32 *)v3);
  }
  catch ( ... )
  {
    MapExceptionToHresult(v28);
  }
  EventSinkSetter<DWriteTraceLogging::FontSetTraceLoggingEventSink>::~EventSinkSetter<DWriteTraceLogging::FontSetTraceLoggingEventSink>(&v45);
  return v40;
}

```

## disassembly

```asm
0x18006a2dc  mov     [rsp+arg_8], edx
0x18006a2e0  mov     [rsp+arg_0], rcx
0x18006a2e5  push    rbx
0x18006a2e6  push    rsi
0x18006a2e7  push    rdi
0x18006a2e8  push    r12
0x18006a2ea  push    r13
0x18006a2ec  push    r14
0x18006a2ee  push    r15
0x18006a2f0  sub     rsp, 1E0h
0x18006a2f7  mov     r13, rcx
0x18006a2fa  xor     esi, esi
0x18006a2fc  mov     [rsp+218h+var_1A8], esi
0x18006a300  mov     r9, 657461647075h
0x18006a30a  mov     [rsp+218h+var_F8], r9
0x18006a312  mov     [rsp+218h+var_1A0], esi
0x18006a316  mov     [rcx+18h], r9
0x18006a31a  mov     r12, 6574617473h
0x18006a324  add     rcx, 10h
0x18006a328  mov     r15, 746553746E6F46h
0x18006a332  mov     [rsp+218h+var_1F8], edx
0x18006a336  mov     r8, r12
0x18006a339  mov     rdx, r15
0x18006a33c  call    ??$LogEvent@VEventTag@@I@EventLogger@@QEBAXVEventTag@@00I@Z; EventLogger::LogEvent<EventTag,uint>(EventTag,EventTag,EventTag,uint)
0x18006a341  lea     ecx, [rsi+20h]; Size
0x18006a344  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a349  mov     rdi, rax
0x18006a34c  mov     [rsp+218h+arg_10], rax
0x18006a354  cmp     [r13+20h], esi
0x18006a358  setz    bl
0x18006a35b  mov     rcx, rax; this
0x18006a35e  call    ??0TraceLoggingEventSink@DWriteTraceLogging@@QEAA@XZ; DWriteTraceLogging::TraceLoggingEventSink::TraceLoggingEventSink(void)
0x18006a363  lea     rcx, ??_7FontSetTraceLoggingEventSink@DWriteTraceLogging@@6B@; const DWriteTraceLogging::FontSetTraceLoggingEventSink::`vftable'
0x18006a36a  mov     [rdi], rcx
0x18006a36d  call    cs:__imp_GetCurrentThreadId
0x18006a373  mov     [rdi+10h], eax
0x18006a376  mov     [rdi+14h], esi
0x18006a379  mov     [rdi+18h], bl
0x18006a37c  mov     [rdi+19h], sil
0x18006a380  mov     rdx, rdi
0x18006a383  lea     rcx, [rsp+218h+var_178]
0x18006a38b  call    ??0?$EventSinkSetter@VFontSetTraceLoggingEventSink@DWriteTraceLogging@@@@QEAA@PEAVFontSetTraceLoggingEventSink@DWriteTraceLogging@@@Z; EventSinkSetter<DWriteTraceLogging::FontSetTraceLoggingEventSink>::EventSinkSetter<DWriteTraceLogging::FontSetTraceLoggingEventSink>(DWriteTraceLogging::FontSetTraceLoggingEventSink *)
0x18006a390  nop
0x18006a391  mov     r14d, esi
0x18006a394  mov     [rsp+218h+var_1BC], esi
0x18006a398  mov     eax, esi
0x18006a39a  mov     qword ptr [rsp+218h+var_188], rax
0x18006a3a2  mov     [rsp+218h+var_1A4], eax
0x18006a3a6  mov     al, sil
0x18006a3a9  mov     [rsp+218h+arg_18], al
0x18006a3b0  mov     byte ptr [rsp+218h+var_1C8+2], al
0x18006a3b4  mov     [rsp+218h+var_1C0], esi
0x18006a3b8  mov     [rsp+218h+var_1B4], esi
0x18006a3bc  mov     byte ptr [rsp+218h+arg_10], al
0x18006a3c3  mov     byte ptr [rsp+218h+var_1C8], al
0x18006a3c7  mov     ebx, esi
0x18006a3c9  mov     dword ptr [rsp+218h+var_1C4], ebx
0x18006a3cd  mov     [rsp+218h+var_180], rsi
0x18006a3d5  lea     rdx, [rsp+218h+var_118]
0x18006a3dd  mov     rcx, r13
0x18006a3e0  call    ?GetCurrentFontCacheStorage@FontSetCache@@UEBA?AV?$ComPtr@UIFontCacheStorageInternal@@@@XZ; FontSetCache::GetCurrentFontCacheStorage(void)
0x18006a3e5  nop
0x18006a3e6  mov     rdi, [rsp+218h+var_118]
0x18006a3ee  test    rdi, rdi
0x18006a3f1  jz      loc_18006A50E
0x18006a3f7  mov     rax, [rdi]
0x18006a3fa  lea     rdx, [rsp+218h+var_1B0]
0x18006a3ff  mov     rcx, rdi
0x18006a402  mov     rax, [rax+48h]
0x18006a406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a40b  xor     ebx, ebx
0x18006a40d  lea     rcx, [rsp+218h+var_180]
0x18006a415  cmp     rax, rcx
0x18006a418  jz      short loc_18006A432
0x18006a41a  mov     rsi, [rax]
0x18006a41d  mov     [rax], rbx
0x18006a420  mov     [rsp+218h+var_180], rsi
0x18006a428  xor     ecx, ecx; void *
0x18006a42a  call    ??$ReleaseReference@VCacheWriter@@@@YAXPEAVCacheWriter@@@Z; ReleaseReference<CacheWriter>(CacheWriter *)
0x18006a42f  mov     rbx, rsi
0x18006a432  mov     rcx, [rsp+218h+var_1B0]; void *
0x18006a437  call    ??$ReleaseReference@VCacheWriter@@@@YAXPEAVCacheWriter@@@Z; ReleaseReference<CacheWriter>(CacheWriter *)
0x18006a43c  mov     rax, [rbx+48h]
0x18006a440  mov     r14d, [rax+20h]
0x18006a444  mov     [rsp+218h+var_1BC], r14d
0x18006a449  mov     rdx, rsi
0x18006a44c  lea     rcx, [rsp+218h+var_E8]
0x18006a454  call    ?GetFontCollectionFromCacheWriter@FontSetCache@@SA?AVFontCollection@@PEAVCacheWriter@@@Z; FontSetCache::GetFontCollectionFromCacheWriter(CacheWriter *)
0x18006a459  nop
0x18006a45a  mov     rbx, [rsp+218h+var_A0]
0x18006a462  sub     rbx, [rsp+218h+var_A8]
0x18006a46a  sar     rbx, 2
0x18006a46e  mov     rax, 0AAAAAAAAAAAAAAABh
0x18006a478  imul    rbx, rax
0x18006a47c  mov     qword ptr [rsp+218h+var_188], rbx
0x18006a484  mov     [rsp+218h+var_1A4], ebx
0x18006a488  cmp     dword ptr [r13+20h], 0
0x18006a48d  jnz     short loc_18006A4A7
0x18006a48f  lea     rcx, [rsp+218h+var_E8]
0x18006a497  call    ?GetMissingRequiredFonts@FontSetCache@@SA?AW4RequiredFonts@1@AEBVFontSet@@@Z; FontSetCache::GetMissingRequiredFonts(FontSet const &)
0x18006a49c  mov     [rsp+218h+arg_18], al
0x18006a4a3  mov     byte ptr [rsp+218h+var_1C8+2], al
0x18006a4a7  lea     rcx, [rsp+218h+var_60]
0x18006a4af  call    ?_Tidy@?$vector@UGlyphToListMapping@GlyphDependencyRegion@@V?$allocator@UGlyphToListMapping@GlyphDependencyRegion@@@std@@@std@@AEAAXXZ; std::vector<GlyphDependencyRegion::GlyphToListMapping>::_Tidy(void)
0x18006a4b4  lea     rcx, [rsp+218h+var_78]
0x18006a4bc  call    ??1?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::~vector<unsigned __int64>(void)
0x18006a4c1  lea     rdx, [rsp+218h+var_88]
0x18006a4c9  lea     rcx, [rsp+218h+var_88]
0x18006a4d1  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBVStringCheckedPtr@@I@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVStringCheckedPtr@@I@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVStringCheckedPtr@@I@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<StringCheckedPtr const,uint>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<StringCheckedPtr const,uint>,void *>>>(std::allocator<std::_Tree_node<std::pair<StringCheckedPtr const,uint>,void *>> &)
0x18006a4d6  lea     rcx, [rsp+218h+var_A8]
0x18006a4de  call    ?_Tidy@?$vector@UFeature@FontFeatureCoverageRegionBuilder@@V?$allocator@UFeature@FontFeatureCoverageRegionBuilder@@@std@@@std@@AEAAXXZ; std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(void)
0x18006a4e3  lea     rcx, [rsp+218h+var_B0]
0x18006a4eb  call    ??1?$RefCountedArray@E@@QEAA@XZ; RefCountedArray<uchar>::~RefCountedArray<uchar>(void)
0x18006a4f0  lea     rcx, [rsp+218h+var_B8]
0x18006a4f8  call    ??1?$IntrusivePtr@VICacheReference@@@@QEAA@XZ; IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(void)
0x18006a4fd  lea     rcx, [rsp+218h+var_C0]
0x18006a505  call    ??1?$RefCountedArray@E@@QEAA@XZ; RefCountedArray<uchar>::~RefCountedArray<uchar>(void)
0x18006a50a  mov     ebx, dword ptr [rsp+218h+var_1C4]
0x18006a50e  mov     rcx, [r13+58h]
0x18006a512  test    rcx, rcx
0x18006a515  jz      short loc_18006A533
0x18006a517  mov     rax, [rcx]
0x18006a51a  lea     rdx, [r13+68h]
0x18006a51e  mov     r8d, r14d
0x18006a521  mov     rax, [rax+50h]
0x18006a525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a52a  test    eax, eax
0x18006a52c  mov     byte ptr [rsp+218h+var_1C8+1], 1
0x18006a531  jnz     short loc_18006A538
0x18006a533  mov     byte ptr [rsp+218h+var_1C8+1], 0
0x18006a538  lea     eax, [r14+1]
0x18006a53c  mov     ecx, 80000000h
0x18006a541  test    eax, eax
0x18006a543  cmovnz  ecx, eax
0x18006a546  mov     [rsp+218h+var_1B8], ecx
0x18006a54a  mov     [rsp+218h+var_190], 0
0x18006a556  mov     [rsp+218h+var_168], 0
0x18006a562  lea     rcx, [rsp+218h+var_160]; this
0x18006a56a  call    ??0ManualResetEvent@@QEAA@_N@Z; ManualResetEvent::ManualResetEvent(bool)
0x18006a56f  lea     rcx, [rsp+218h+var_158]; void *
0x18006a577  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18006a57c  nop
0x18006a57d  mov     r14, 646C6975626572h
0x18006a587  mov     rax, [rsp+218h+var_178]
0x18006a58f  mov     [rax+14h], ebx
0x18006a592  xor     eax, eax
0x18006a594  mov     [rsp+218h+var_198], rax
0x18006a59c  mov     [rsp+218h+var_170], rax
0x18006a5a4  mov     [rsp+218h+var_140], rax
0x18006a5ac  lea     rcx, [rsp+218h+var_138]; this
0x18006a5b4  call    ??0ManualResetEvent@@QEAA@_N@Z; ManualResetEvent::ManualResetEvent(bool)
0x18006a5b9  lea     rcx, [rsp+218h+var_130]; void *
0x18006a5c1  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18006a5c6  nop
0x18006a5c7  xor     ebx, ebx
0x18006a5c9  mov     [rsp+218h+var_108], rbx
0x18006a5d1  mov     al, byte ptr [rsp+218h+var_1C8+1]
0x18006a5d5  mov     byte ptr [rsp+218h+var_1F0], al
0x18006a5d9  lea     rax, [rsp+218h+var_140]
0x18006a5e1  mov     qword ptr [rsp+218h+var_1F8], rax
0x18006a5e6  mov     r9, rsi
0x18006a5e9  mov     r8d, [rsp+218h+arg_8]
0x18006a5f1  lea     rdx, [rsp+218h+var_110]
0x18006a5f9  mov     rcx, r13
0x18006a5fc  call    ?EnumerateAndCreateBuilderIfNeeded@FontSetCache@@AEAA?AV?$ScopedPtr@VFontCollectionBuilder@@@@IPEAVCacheWriter@@AEAUInstalledFontChangeInfo@@_N@Z; FontSetCache::EnumerateAndCreateBuilderIfNeeded(uint,CacheWriter *,InstalledFontChangeInfo &,bool)
0x18006a601  mov     rcx, rax
0x18006a604  mov     [rsp+218h+var_1B0], rbx
0x18006a609  lea     rax, [rsp+218h+var_170]
0x18006a611  cmp     rcx, rax
0x18006a614  jz      short loc_18006A631
0x18006a616  mov     rax, [rcx]
0x18006a619  mov     [rsp+218h+var_198], rax
0x18006a621  mov     [rcx], rbx
0x18006a624  mov     [rsp+218h+var_170], rax
0x18006a62c  mov     [rsp+218h+var_1B0], rax
0x18006a631  mov     rcx, [rsp+218h+var_110]; this
0x18006a639  test    rcx, rcx
0x18006a63c  jz      short loc_18006A643
0x18006a63e  call    ??_GFontCollectionBuilder@@QEAAPEAXI@Z; FontCollectionBuilder::`scalar deleting destructor'(uint)
0x18006a643  cmp     [rsp+218h+var_1B0], 0
0x18006a649  jnz     short loc_18006A67C
0x18006a64b  mov     eax, [rsp+218h+var_1BC]
0x18006a64f  mov     [rsp+218h+var_1C0], eax
0x18006a653  mov     r11, qword ptr [rsp+218h+var_188]
0x18006a65b  mov     r10d, r11d
0x18006a65e  mov     [rsp+218h+var_1B4], r11d
0x18006a663  mov     dl, [rsp+218h+arg_18]
0x18006a66a  mov     cl, dl
0x18006a66c  mov     byte ptr [rsp+218h+arg_10], dl
0x18006a673  mov     byte ptr [rsp+218h+var_1C8], dl
0x18006a677  jmp     loc_18006A83D
0x18006a67c  mov     [r13+18h], r14
0x18006a680  mov     r9, r14
0x18006a683  mov     r8, r12
0x18006a686  mov     rdx, r15
0x18006a689  lea     rcx, [r13+10h]
0x18006a68d  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x18006a692  mov     r8d, [rsp+218h+var_1B8]; unsigned int
0x18006a697  mov     rdx, [rsp+218h+var_198]; struct FontSetBuilder *
0x18006a69f  mov     rcx, r13; this
0x18006a6a2  call    ?AddFontProviderFonts@FontSetCache@@AEAAXPEAVFontSetBuilder@@I@Z; FontSetCache::AddFontProviderFonts(FontSetBuilder *,uint)
0x18006a6a7  mov     rbx, [r13+40h]
0x18006a6ab  mov     r9, 656761726F7453h
0x18006a6b5  mov     r8d, 656B616Dh
0x18006a6bb  mov     rdx, r15
0x18006a6be  lea     rcx, [r13+10h]
0x18006a6c2  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x18006a6c7  mov     ecx, 70h ; 'p'; Size
0x18006a6cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a6d1  lea     rdx, [rbx+8]; wchar_t *
0x18006a6d5  mov     rcx, rax; this
0x18006a6d8  call    ??0FontCacheStorage@@QEAA@PEB_W@Z; FontCacheStorage::FontCacheStorage(wchar_t const *)
0x18006a6dd  mov     rbx, rax
0x18006a6e0  test    rax, rax
0x18006a6e3  jz      short loc_18006A6F5
0x18006a6e5  mov     rax, [rax]
0x18006a6e8  mov     rcx, rbx
0x18006a6eb  mov     rax, [rax+8]
0x18006a6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a6f4  nop
0x18006a6f5  mov     [rsp+218h+var_108], rbx
0x18006a6fd  xor     ecx, ecx
0x18006a6ff  call    ?Deref@?$ComPtr@VFontCacheStorage@@@@CAXPEAVFontCacheStorage@@@Z; ComPtr<FontCacheStorage>::Deref(FontCacheStorage *)
0x18006a704  nop
0x18006a705  mov     r8, [r13+40h]
0x18006a709  add     r8, 8; wchar_t *
0x18006a70d  lea     rdx, [r13+38h]; struct DWrite::RefString *
0x18006a711  mov     rax, [rsp+218h+var_198]
0x18006a719  mov     [rsp+218h+var_1F0], rax; struct FontCollectionBuilder *
0x18006a71e  mov     eax, [rsp+218h+var_1B8]
0x18006a722  mov     [rsp+218h+var_1F8], eax; unsigned int
0x18006a726  mov     r9, rsi; struct CacheWriter *
0x18006a729  mov     rcx, rbx; struct FontCacheStorage *
0x18006a72c  call    ?CreateFontSetCacheInstance@FontSetCache@@SAXPEAVFontCacheStorage@@AEBVRefString@DWrite@@PEB_WPEAVCacheWriter@@IPEAVFontCollectionBuilder@@@Z; FontSetCache::CreateFontSetCacheInstance(FontCacheStorage *,DWrite::RefString const &,wchar_t const *,CacheWriter *,uint,FontCollectionBuilder *)
0x18006a731  mov     rax, [rbx]
0x18006a734  lea     rdx, [rsp+218h+var_100]
0x18006a73c  mov     rcx, rbx
0x18006a73f  mov     rax, [rax+48h]
0x18006a743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a748  nop
0x18006a749  mov     rdx, [rax]
0x18006a74c  lea     rcx, [rsp+218h+var_E8]
0x18006a754  call    ?GetFontCollectionFromCacheWriter@FontSetCache@@SA?AVFontCollection@@PEAVCacheWriter@@@Z; FontSetCache::GetFontCollectionFromCacheWriter(CacheWriter *)
0x18006a759  nop
0x18006a75a  mov     rcx, [rsp+218h+var_100]; void *
0x18006a762  call    ??$ReleaseReference@VCacheWriter@@@@YAXPEAVCacheWriter@@@Z; ReleaseReference<CacheWriter>(CacheWriter *)
0x18006a767  nop
0x18006a768  mov     eax, [rsp+218h+var_1B8]
0x18006a76c  mov     [rsp+218h+var_1C0], eax
0x18006a770  mov     rax, [rsp+218h+var_A0]
0x18006a778  sub     rax, [rsp+218h+var_A8]
0x18006a780  sar     rax, 2
0x18006a784  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18006a78e  imul    rax, rcx
0x18006a792  mov     [rsp+218h+var_1B0], rax
0x18006a797  mov     [rsp+218h+var_1B4], eax
0x18006a79b  cmp     dword ptr [r13+20h], 0
0x18006a7a0  jnz     short loc_18006A7BA
0x18006a7a2  lea     rcx, [rsp+218h+var_E8]
0x18006a7aa  call    ?GetMissingRequiredFonts@FontSetCache@@SA?AW4RequiredFonts@1@AEBVFontSet@@@Z; FontSetCache::GetMissingRequiredFonts(FontSet const &)
0x18006a7af  mov     byte ptr [rsp+218h+arg_10], al
0x18006a7b6  mov     byte ptr [rsp+218h+var_1C8], al; unsigned int
0x18006a7ba  or      [rsp+218h+var_1A8], 3
0x18006a7bf  lea     rcx, [rsp+218h+var_60]
0x18006a7c7  call    ?_Tidy@?$vector@UGlyphToListMapping@GlyphDependencyRegion@@V?$allocator@UGlyphToListMapping@GlyphDependencyRegion@@@std@@@std@@AEAAXXZ; std::vector<GlyphDependencyRegion::GlyphToListMapping>::_Tidy(void)
0x18006a7cc  lea     rcx, [rsp+218h+var_78]
0x18006a7d4  call    ??1?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::~vector<unsigned __int64>(void)
0x18006a7d9  lea     rdx, [rsp+218h+var_88]
0x18006a7e1  lea     rcx, [rsp+218h+var_88]
0x18006a7e9  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBVStringCheckedPtr@@I@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVStringCheckedPtr@@I@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVStringCheckedPtr@@I@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<StringCheckedPtr const,uint>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<StringCheckedPtr const,uint>,void *>>>(std::allocator<std::_Tree_node<std::pair<StringCheckedPtr const,uint>,void *>> &)
0x18006a7ee  lea     rcx, [rsp+218h+var_A8]
0x18006a7f6  call    ?_Tidy@?$vector@UFeature@FontFeatureCoverageRegionBuilder@@V?$allocator@UFeature@FontFeatureCoverageRegionBuilder@@@std@@@std@@AEAAXXZ; std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(void)
0x18006a7fb  lea     rcx, [rsp+218h+var_B0]
0x18006a803  call    ??1?$RefCountedArray@E@@QEAA@XZ; RefCountedArray<uchar>::~RefCountedArray<uchar>(void)
0x18006a808  lea     rcx, [rsp+218h+var_B8]
0x18006a810  call    ??1?$IntrusivePtr@VICacheReference@@@@QEAA@XZ; IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(void)
0x18006a815  lea     rcx, [rsp+218h+var_C0]
0x18006a81d  call    ??1?$RefCountedArray@E@@QEAA@XZ; RefCountedArray<uchar>::~RefCountedArray<uchar>(void)
0x18006a822  mov     r10, [rsp+218h+var_1B0]
0x18006a827  mov     r11, qword ptr [rsp+218h+var_188]
0x18006a82f  mov     cl, byte ptr [rsp+218h+arg_10]
0x18006a836  mov     dl, [rsp+218h+arg_18]
0x18006a83d  mov     rax, [rsp+218h+var_178]
0x18006a845  cmp     byte ptr [rax+19h], 0
0x18006a849  jnz     short loc_18006A85E
0x18006a84b  test    cl, cl
0x18006a84d  jnz     short loc_18006A85E
0x18006a84f  test    dl, dl
0x18006a851  jnz     short loc_18006A85E
0x18006a853  cmp     dword ptr [rsp+218h+var_1C4], 0
0x18006a858  jz      loc_18006A930
0x18006a85e  movzx   r8d, cl
0x18006a862  movzx   r9d, dl
0x18006a866  cmp     dword ptr [r13+20h], 0
0x18006a86b  setz    dl; int
0x18006a86e  mov     al, cl
0x18006a870  neg     al
0x18006a872  sbb     ecx, ecx
0x18006a874  and     ecx, 88985002h; this
0x18006a87a  mov     [rsp+218h+var_1D0], r8d; unsigned int
  ... truncated ...
```
