# Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::create(ushort const *,std::shared_ptr<Utility::SharedMemoryCache> const &,Utility::MemoryCacheDuplicateItemPolicy)

- ea: `0x180046494`
- end: `0x180046533`
- name: `?create@?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@SA?AV?$shared_ptr@V?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@std@@PEBGAEBV?$shared_ptr@VSharedMemoryCache@Utility@@@4@W4MemoryCacheDuplicateItemPolicy@2@@Z`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180043b1c`

## callees

- `0x18000d49c`
- `0x180011d90`
- `0x180016770`
- `0x1800411bc`
- `0x180043940`
- `0x180043970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800464f8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800464f8`

## string_xrefs

- `0x1800464d3`: `GenerationsManagerVersionsCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::create(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  RTL_SRWLOCK *v6; // [rsp+48h] [rbp+10h]

  v6 = (RTL_SRWLOCK *)operator new(0xD8u);
  v6->Ptr = 0;
  v6[1].Ptr = 0;
  std::wstring::wstring(&v6[3], L"GenerationsManagerVersionsCache");
  LODWORD(v6[7].Ptr) = 0;
  std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
    &v6[8],
    a3);
  InitializeSRWLock(v6 + 10);
  std::unordered_multimap<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>>::unordered_multimap<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>>(&v6[11]);
  std::unordered_multimap<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::PinnedCacheEntry>>::unordered_multimap<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::PinnedCacheEntry>>(&v6[19]);
  std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>>::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>>(
    a1,
    v6);
  return a1;
}

```

## disassembly

```asm
0x180046494  mov     [rsp+arg_0], rbx
0x180046499  mov     [rsp+arg_10], rsi
0x18004649e  mov     [rsp+arg_8], rdx
0x1800464a3  push    rdi
0x1800464a4  sub     rsp, 30h
0x1800464a8  mov     rbx, r8
0x1800464ab  mov     rsi, rcx
0x1800464ae  mov     ecx, 0D8h; Size
0x1800464b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800464b8  mov     rdi, rax
0x1800464bb  mov     [rsp+38h+arg_8], rax
0x1800464c0  mov     qword ptr [rax], 0
0x1800464c7  mov     qword ptr [rax+8], 0
0x1800464cf  lea     rcx, [rax+18h]
0x1800464d3  lea     rdx, aGenerationsman; "GenerationsManagerVersionsCache"
0x1800464da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800464df  nop
0x1800464e0  mov     dword ptr [rdi+38h], 0
0x1800464e7  lea     rcx, [rdi+40h]
0x1800464eb  mov     rdx, rbx
0x1800464ee  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x1800464f3  nop
0x1800464f4  lea     rcx, [rdi+50h]; SRWLock
0x1800464f8  call    cs:__imp_InitializeSRWLock
0x1800464fe  lea     rcx, [rdi+58h]
0x180046502  call    ??0?$unordered_multimap@VVersionRequestId@MapControl@@V?$shared_ptr@VCacheEntry@?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@std@@U?$hash@VVersionRequestId@MapControl@@@4@U?$equal_to@VVersionRequestId@MapControl@@@4@V?$allocator@U?$pair@$$CBVVersionRequestId@MapControl@@V?$shared_ptr@VCacheEntry@?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@std@@@std@@@4@@std@@QEAA@XZ; std::unordered_multimap<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>>::unordered_multimap<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>>(void)
0x180046507  nop
0x180046508  lea     rcx, [rdi+98h]
0x18004650f  call    ??0?$unordered_multimap@VVersionRequestId@MapControl@@V?$shared_ptr@VPinnedCacheEntry@?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@std@@U?$hash@VVersionRequestId@MapControl@@@4@U?$equal_to@VVersionRequestId@MapControl@@@4@V?$allocator@U?$pair@$$CBVVersionRequestId@MapControl@@V?$shared_ptr@VPinnedCacheEntry@?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@std@@@std@@@4@@std@@QEAA@XZ; std::unordered_multimap<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::PinnedCacheEntry>>::unordered_multimap<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::PinnedCacheEntry>>(void)
0x180046514  nop
0x180046515  mov     rdx, rdi
0x180046518  mov     rcx, rsi
0x18004651b  call    ??$?0V?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@$0A@@?$shared_ptr@V?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@std@@QEAA@PEAV?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>>::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>>(Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>> *)
0x180046520  mov     rax, rsi
0x180046523  mov     rbx, [rsp+38h+arg_0]
0x180046528  mov     rsi, [rsp+38h+arg_10]
0x18004652d  add     rsp, 30h
0x180046531  pop     rdi
0x180046532  retn
```
