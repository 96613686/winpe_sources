# MapsStoreManager::FetchCopyrightAsync(void)

- ea: `0x180018968`
- end: `0x180018b13`
- name: `?FetchCopyrightAsync@MapsStoreManager@@AEAAXXZ`
- size: `427`
- prototype: `void __fastcall(MapsStoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x180018bf4`

## callees

- `0x18000d090`
- `0x1800126c4`
- `0x180012720`
- `0x1800140f0`
- `0x180015e8c`
- `0x1800160ac`
- `0x1800161d4`
- `0x1800162a0`
- `0x180016770`
- `0x180016d58`
- `0x1800172c8`
- `0x180018968`
- `0x18001b9e0`
- `0x18001cc74`
- `0x18001fb58`

## import_xrefs

- `BingOnlineServices!?ExecuteAsync@CopyrightRequest@BingOnlineServices@@QEAA?AV?$task@VCopyrightData@BingOnlineServices@@@pplx@@AEBV?$vector@HV?$allocator@H@std@@@std@@@Z` at `0x180018a5c`
- `BingOnlineServices!?ExecuteAsync@CopyrightRequest@BingOnlineServices@@QEAA?AV?$task@VCopyrightData@BingOnlineServices@@@pplx@@AEBV?$vector@HV?$allocator@H@std@@@std@@@Z` at `0x180018a5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001899c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001899c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall MapsStoreManager::FetchCopyrightAsync(MapsStoreManager *this)
{
  char *v2; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  __int64 v4; // r8
  __int64 v5; // r9
  const char *v6; // rax
  _BYTE v7[8]; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v8; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v9; // [rsp+40h] [rbp-98h] BYREF
  std::_Ref_count_base *v10; // [rsp+48h] [rbp-90h]
  _QWORD v11[2]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v12; // [rsp+60h] [rbp-78h] BYREF
  std::_Ref_count_base *v13; // [rsp+68h] [rbp-70h]
  _QWORD v14[3]; // [rsp+70h] [rbp-68h] BYREF
  const std::exception *v15; // [rsp+88h] [rbp-50h] BYREF
  _BYTE v16[8]; // [rsp+90h] [rbp-48h] BYREF
  std::_Ref_count_base *v17; // [rsp+98h] [rbp-40h]
  _BYTE v18[32]; // [rsp+A8h] [rbp-30h] BYREF

  v2 = (char *)this + 624;
  v3 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 78);
  EnterCriticalSection(v3);
  if ( *(_DWORD *)(*(_QWORD *)v2 + 76LL) )
  {
    LeaveCriticalSection(v3);
  }
  else
  {
    *(_DWORD *)(*(_QWORD *)v2 + 76LL) = 1;
    LeaveCriticalSection(v3);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(v14);
    std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
      &v12,
      v2);
    MapsRegionCatalogHelper::getFirstLocale(v18, (char *)this + 536);
    LODWORD(v8) = 48;
    std::vector<int>::emplace_back<int>(v14, &v8);
    v7[0] = 0;
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
    v11[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 592);
    std::make_unique<BingOnlineServices::CopyrightRequest,unsigned short const *,unsigned short const *,bool,0>(
      &v8,
      v11,
      &v9,
      v7);
    try
    {
      BingOnlineServices::CopyrightRequest::ExecuteAsync(v8, &v9, v14);
      v4 = lambda_800d2937b385c066ed776b1df55f27db_::_lambda_800d2937b385c066ed776b1df55f27db_(v16, &v12, this);
      pplx::task_BingOnlineServices::CopyrightData_::then__lambda_463403af73c19f5d1214a3baa98735ac___(v5, v11, v4);
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v11);
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      if ( v10 )
        std::_Ref_count_base::_Decref(v10);
    }
    catch ( const std::exception *v15 )
    {
      *(_DWORD *)(v12 + 76) = 3;
      v6 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v15 + 8LL))(v15);
      ZTraceHelperNoThis(
        0,
        "MapsStoreManager::FetchCopyrightAsync",
        1113,
        "Exception executing Bing imagery copyright response: %s",
        v6);
    }
    std::unique_ptr<BingOnlineServices::CopyrightRequest>::~unique_ptr<BingOnlineServices::CopyrightRequest>(&v8);
    std::wstring::_Tidy_deallocate(v18);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    std::vector<enum MapControl::PersistentDataType>::_Tidy(v14);
  }
}

```

## disassembly

```asm
0x180018968  mov     [rsp+arg_8], rbx
0x18001896d  mov     [rsp+arg_10], rsi
0x180018972  push    rdi
0x180018973  sub     rsp, 0D0h
0x18001897a  mov     rax, cs:__security_cookie
0x180018981  xor     rax, rsp
0x180018984  mov     [rsp+0D8h+var_10], rax
0x18001898c  mov     rdi, rcx
0x18001898f  lea     rsi, [rcx+270h]
0x180018996  mov     rbx, [rsi]
0x180018999  mov     rcx, rbx; lpCriticalSection
0x18001899c  call    cs:__imp_EnterCriticalSection
0x1800189a2  mov     rax, [rsi]
0x1800189a5  mov     rcx, rbx; lpCriticalSection
0x1800189a8  cmp     dword ptr [rax+4Ch], 0
0x1800189ac  jz      short loc_1800189B9
0x1800189ae  call    cs:__imp_LeaveCriticalSection
0x1800189b4  jmp     loc_180018AEE
0x1800189b9  mov     dword ptr [rax+4Ch], 1
0x1800189c0  call    cs:__imp_LeaveCriticalSection
0x1800189c6  lea     rcx, [rsp+0D8h+var_68]; void *
0x1800189cb  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(std::allocator<std::pair<std::wstring const,std::pair<int,unsigned __int64>>> const &)
0x1800189d0  nop
0x1800189d1  mov     rdx, rsi
0x1800189d4  lea     rcx, [rsp+0D8h+var_78]
0x1800189d9  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x1800189de  nop
0x1800189df  lea     rdx, [rdi+218h]
0x1800189e6  lea     rcx, [rsp+0D8h+var_30]
0x1800189ee  call    ?getFirstLocale@MapsRegionCatalogHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; MapsRegionCatalogHelper::getFirstLocale(std::wstring const &)
0x1800189f3  nop
0x1800189f4  mov     dword ptr [rsp+0D8h+var_A0], 30h ; '0'
0x1800189fc  lea     rdx, [rsp+0D8h+var_A0]
0x180018a01  lea     rcx, [rsp+0D8h+var_68]
0x180018a06  call    ??$emplace_back@H@?$vector@HV?$allocator@H@std@@@std@@QEAAAEAH$$QEAH@Z; std::vector<int>::emplace_back<int>(int &&)
0x180018a0b  mov     [rsp+0D8h+var_A8], 0
0x180018a10  lea     rcx, [rsp+0D8h+var_30]
0x180018a18  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018a1d  mov     [rsp+0D8h+var_98], rax
0x180018a22  lea     rcx, [rdi+250h]
0x180018a29  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018a2e  mov     [rsp+0D8h+var_88], rax
0x180018a33  lea     r9, [rsp+0D8h+var_A8]
0x180018a38  lea     r8, [rsp+0D8h+var_98]
0x180018a3d  lea     rdx, [rsp+0D8h+var_88]
0x180018a42  lea     rcx, [rsp+0D8h+var_A0]
0x180018a47  call    ??$make_unique@VCopyrightRequest@BingOnlineServices@@PEBGPEBG_N$0A@@std@@YA?AV?$unique_ptr@VCopyrightRequest@BingOnlineServices@@U?$default_delete@VCopyrightRequest@BingOnlineServices@@@std@@@0@$$QEAPEBG0$$QEA_N@Z; std::make_unique<BingOnlineServices::CopyrightRequest,ushort const *,ushort const *,bool,0>(ushort const * &&,ushort const * &&,bool &&)
0x180018a4c  nop
0x180018a4d  lea     r8, [rsp+0D8h+var_68]
0x180018a52  lea     rdx, [rsp+0D8h+var_98]
0x180018a57  mov     rcx, [rsp+0D8h+var_A0]
0x180018a5c  call    cs:__imp_?ExecuteAsync@CopyrightRequest@BingOnlineServices@@QEAA?AV?$task@VCopyrightData@BingOnlineServices@@@pplx@@AEBV?$vector@HV?$allocator@H@std@@@std@@@Z; BingOnlineServices::CopyrightRequest::ExecuteAsync(std::vector<int> const &)
0x180018a62  mov     r9, rax
0x180018a65  mov     r8, rdi
0x180018a68  lea     rdx, [rsp+0D8h+var_78]
0x180018a6d  lea     rcx, [rsp+0D8h+var_48]
0x180018a75  call    _lambda_800d2937b385c066ed776b1df55f27db____lambda_800d2937b385c066ed776b1df55f27db_
0x180018a7a  nop
0x180018a7b  mov     r8, rax
0x180018a7e  lea     rdx, [rsp+0D8h+var_88]
0x180018a83  mov     rcx, r9
0x180018a86  call    pplx__task_BingOnlineServices__CopyrightData___then__lambda_463403af73c19f5d1214a3baa98735ac___
0x180018a8b  lea     rcx, [rsp+0D8h+var_88]
0x180018a90  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180018a95  nop
0x180018a96  mov     rcx, [rsp+0D8h+var_40]; this
0x180018a9e  test    rcx, rcx
0x180018aa1  jz      short loc_180018AA9
0x180018aa3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018aa8  nop
0x180018aa9  mov     rcx, [rsp+0D8h+var_90]; this
0x180018aae  test    rcx, rcx
0x180018ab1  jz      short loc_180018AB9
0x180018ab3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018ab8  nop
0x180018ab9  jmp     short $+2
0x180018abb  lea     rcx, [rsp+0D8h+var_A0]
0x180018ac0  call    ??1?$unique_ptr@VCopyrightRequest@BingOnlineServices@@U?$default_delete@VCopyrightRequest@BingOnlineServices@@@std@@@std@@QEAA@XZ; std::unique_ptr<BingOnlineServices::CopyrightRequest>::~unique_ptr<BingOnlineServices::CopyrightRequest>(void)
0x180018ac5  nop
0x180018ac6  lea     rcx, [rsp+0D8h+var_30]
0x180018ace  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018ad3  nop
0x180018ad4  mov     rcx, [rsp+0D8h+var_70]; this
0x180018ad9  test    rcx, rcx
0x180018adc  jz      short loc_180018AE4
0x180018ade  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018ae3  nop
0x180018ae4  lea     rcx, [rsp+0D8h+var_68]
0x180018ae9  call    ?_Tidy@?$vector@W4PersistentDataType@MapControl@@V?$allocator@W4PersistentDataType@MapControl@@@std@@@std@@AEAAXXZ; std::vector<MapControl::PersistentDataType>::_Tidy(void)
0x180018aee  mov     rcx, [rsp+0D8h+var_10]
0x180018af6  xor     rcx, rsp; StackCookie
0x180018af9  call    __security_check_cookie
0x180018afe  lea     r11, [rsp+0D8h+var_8]
0x180018b06  mov     rbx, [r11+18h]
0x180018b0a  mov     rsi, [r11+20h]
0x180018b0e  mov     rsp, r11
0x180018b11  pop     rdi
0x180018b12  retn
```
