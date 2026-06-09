# WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerFactory::GetInstance(Windows::System::IUser *,HSTRING__ *,uint,WindowsInternal::Shell::UnifiedTile::VisualCache::TileThemeSelector,WindowsInternal::Shell::UnifiedTile::VisualCache::VisualCacheOptions,WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager * *)

- ea: `0x18008ef20`
- end: `0x18008f27f`
- name: `?GetInstance@StartVisualCacheManagerFactory@VisualCache@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAUIUser@System@Windows@@PEAUHSTRING__@@IW4TileThemeSelector@2345@W4VisualCacheOptions@2345@PEAPEAUIStartVisualCacheManager@2345@@Z`
- size: `863`
- prototype: `int __high(struct Windows::System::IUser *, HSTRING, unsigned int, enum WindowsInternal::Shell::UnifiedTile::VisualCache::TileThemeSelector, enum WindowsInternal::Shell::UnifiedTile::VisualCache::VisualCacheOptions, struct WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18001dac0`
- `0x180021b78`
- `0x18004bda0`
- `0x18008d550`
- `0x18008ef20`
- `0x18008f64c`
- `0x18009019c`
- `0x180090814`
- `0x1800e8300`
- `0x1801593b0`
- `0x18027aae8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008f081`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008f081`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008f13a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008f13a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008ef9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008ef9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008effd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008effd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008ef7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008ef7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ef69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f03e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f1e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ef69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f03e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f1e7`

## string_xrefs

- `0x18008f24c`: `shellcommon\shell\tiles\sharedmodel\cache\lib\StartVisualCacheStatics.h`
- `0x18008f125`: `shellcommon\shell\tiles\sharedmodel\cache\lib\startvisualcachestatics.cpp`
- `0x18008f1ba`: `shellcommon\shell\tiles\sharedmodel\cache\lib\startvisualcachestatics.cpp`
- `0x18008f25e`: `shellcommon\shell\tiles\sharedmodel\cache\lib\startvisualcachestatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerFactory::GetInstance(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        int a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  _QWORD *v8; // rdi
  HRESULT v9; // eax
  __int64 v10; // rcx
  RTL_SRWLOCK *v11; // rbx
  PVOID Ptr; // rcx
  const char *v13; // r9
  _QWORD *v14; // rcx
  const char *v15; // r9
  _QWORD *v16; // rcx
  __int64 result; // rax
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // ebx
  _QWORD *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // ebx
  _QWORD *v26; // rax
  int v27; // [rsp+20h] [rbp-68h]
  int v28; // [rsp+20h] [rbp-68h]
  __int64 v29; // [rsp+30h] [rbp-58h] BYREF
  RTL_SRWLOCK *v30; // [rsp+38h] [rbp-50h] BYREF
  char v31[16]; // [rsp+40h] [rbp-48h] BYREF
  HSTRING newString; // [rsp+50h] [rbp-38h] BYREF
  int v33; // [rsp+58h] [rbp-30h]
  int v34; // [rsp+5Ch] [rbp-2Ch]
  int v35; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v37; // [rsp+98h] [rbp+10h] BYREF
  _QWORD *v38; // [rsp+A0h] [rbp+18h] BYREF
  int v39; // [rsp+A8h] [rbp+20h] BYREF

  v39 = a4;
  v38 = a3;
  v37 = a2;
  v8 = a7;
  *a7 = 0;
  a7 = 0;
  v33 = a4;
  v34 = a5;
  v35 = a6;
  WindowsDeleteString(0);
  newString = 0;
  v9 = WindowsDuplicateString(a3, &newString);
  try
  {
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\cache\\lib\\StartVisualCacheStatics.h",
        (const char *)(unsigned int)v9,
        v27);
    AcquireSRWLockShared(&WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerFactory::s_lock);
    std::_Hash<std::_Umap_traits<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,Microsoft::WRL::WeakRef,std::_Uhash_compare<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,std::hash<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>,std::equal_to<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>>,std::allocator<std::pair<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const,Microsoft::WRL::WeakRef>>,0>>::find(
      v10,
      &v30,
      &newString);
    v11 = v30;
    if ( v30 != (RTL_SRWLOCK *)qword_1804DC778 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a7);
      a7 = 0;
      Ptr = v11[5].Ptr;
      if ( Ptr )
        (*(void (__fastcall **)(PVOID, GUID *, _QWORD **))(*(_QWORD *)Ptr + 24LL))(
          Ptr,
          &GUID_5f3c6865_6d76_5a52_0db1_c8b6eee8b68f,
          &a7);
    }
    ReleaseSRWLockShared(&WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerFactory::s_lock);
    v14 = a7;
    if ( a7 )
      goto LABEL_7;
    AcquireSRWLockExclusive(&WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerFactory::s_lock);
    v30 = &WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerFactory::s_lock;
    std::_Hash<std::_Umap_traits<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,Microsoft::WRL::WeakRef,std::_Uhash_compare<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,std::hash<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>,std::equal_to<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>>,std::allocator<std::pair<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const,Microsoft::WRL::WeakRef>>,0>>::find(
      v18,
      &v29,
      &newString);
    if ( v29 != qword_1804DC778 )
      Microsoft::WRL::WeakRef::As<WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager>(
        v29 + 40,
        &a7);
    if ( !a7 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a7);
      v19 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerWinRT,WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager,Windows::System::IUser * &,HSTRING__ * &,unsigned int &,enum WindowsInternal::Shell::UnifiedTile::VisualCache::TileThemeSelector &,enum WindowsInternal::Shell::UnifiedTile::VisualCache::VisualCacheOptions &>(
              (unsigned int)&a7,
              (unsigned int)&v37,
              (unsigned int)&v38,
              (unsigned int)&v39,
              (__int64)&a5,
              (__int64)&a6);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x60,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\cache\\lib\\startvisualcachestatics.cpp",
          (const char *)(unsigned int)v19,
          v28);
        ReleaseSRWLockExclusive(&WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerFactory::s_lock);
        WindowsDeleteString(newString);
        newString = 0;
        v21 = a7;
        if ( a7 )
        {
          a7 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
        }
        return v20;
      }
      v29 = 0;
      v38 = &v29;
      v22 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v38);
      v23 = Microsoft::WRL::AsWeak<WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager>(a7, v22);
      v25 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\cache\\lib\\startvisualcachestatics.cpp",
          (const char *)(unsigned int)v23,
          v28);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v30);
        WindowsDeleteString(newString);
        newString = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a7);
        return v25;
      }
      v26 = (_QWORD *)std::_Hash<std::_Umap_traits<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,Microsoft::WRL::WeakRef,std::_Uhash_compare<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,std::hash<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>,std::equal_to<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>>,std::allocator<std::pair<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const,Microsoft::WRL::WeakRef>>,0>>::_Try_emplace<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const &,>(
                        v24,
                        v31,
                        &newString);
      Microsoft::WRL::ComPtr<Windows::Internal::Tiles::ITileQueryFilter>::operator=(*v26 + 40LL, &v29);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v30);
    v14 = a7;
LABEL_7:
    if ( !v14 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x67,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\cache\\lib\\startvisualcachestatics.cpp",
        v13);
    (*(void (__fastcall **)(_QWORD *))(*v14 + 8LL))(v14);
    *v8 = a7;
    WindowsDeleteString(newString);
    newString = 0;
    v16 = a7;
    if ( a7 )
    {
      a7 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x69,
                           (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\cache\\lib\\startvisualcachestatics.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18008ef20  mov     rax, rsp
0x18008ef23  mov     [rax+8], rbx
0x18008ef27  mov     [rax+20h], r9d
0x18008ef2b  mov     [rax+18h], r8
0x18008ef2f  mov     [rax+10h], rdx
0x18008ef33  push    rsi
0x18008ef34  push    rdi
0x18008ef35  push    r14
0x18008ef37  sub     rsp, 70h
0x18008ef3b  mov     rbx, r8
0x18008ef3e  xor     esi, esi
0x18008ef40  mov     rdi, [rsp+88h+arg_30]
0x18008ef48  mov     [rdi], rsi
0x18008ef4b  mov     [rax+38h], rsi
0x18008ef4f  mov     edx, [rax+30h]
0x18008ef52  mov     eax, [rax+28h]
0x18008ef55  mov     [rsp+88h+newString], rsi
0x18008ef5a  mov     [rsp+88h+var_30], r9d
0x18008ef5f  mov     [rsp+88h+var_2C], eax
0x18008ef63  mov     [rsp+88h+var_28], edx
0x18008ef67  xor     ecx, ecx; string
0x18008ef69  call    cs:__imp_WindowsDeleteString
0x18008ef6f  mov     [rsp+88h+newString], rsi
0x18008ef74  lea     rdx, [rsp+88h+newString]; newString
0x18008ef79  mov     rcx, rbx; string
0x18008ef7c  call    cs:__imp_WindowsDuplicateString
0x18008ef82  mov     rcx, [rsp+88h]; this
0x18008ef8a  test    eax, eax
0x18008ef8c  js      loc_18008F249
0x18008ef92  lea     r14, ?s_lock@StartVisualCacheManagerFactory@VisualCache@UnifiedTile@Shell@WindowsInternal@@0Vsrwlock@wil@@A; wil::srwlock WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerFactory::s_lock
0x18008ef99  mov     rcx, r14; SRWLock
0x18008ef9c  call    cs:__imp_AcquireSRWLockShared
0x18008efa2  lea     r8, [rsp+88h+newString]
0x18008efa7  lea     rdx, [rsp+88h+var_50]
0x18008efac  call    ?find@?$_Hash@V?$_Umap_traits@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@V?$_Uhash_compare@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@U?$hash@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@std@@U?$equal_to@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@7@@std@@V?$allocator@U?$pair@$$CBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@Z; std::_Hash<std::_Umap_traits<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,Microsoft::WRL::WeakRef,std::_Uhash_compare<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,std::hash<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>,std::equal_to<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>>,std::allocator<std::pair<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const,Microsoft::WRL::WeakRef>>,0>>::find(WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const &)
0x18008efb1  mov     rbx, [rsp+88h+var_50]
0x18008efb6  cmp     rbx, cs:qword_1804DC778
0x18008efbd  jz      short loc_18008EFFA
0x18008efbf  lea     rcx, [rsp+88h+arg_30]
0x18008efc7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008efcc  nop
0x18008efcd  mov     [rsp+88h+arg_30], rsi
0x18008efd5  mov     rcx, [rbx+28h]
0x18008efd9  test    rcx, rcx
0x18008efdc  jz      short loc_18008EFFA
0x18008efde  mov     rax, [rcx]
0x18008efe1  lea     r8, [rsp+88h+arg_30]
0x18008efe9  lea     rdx, _GUID_5f3c6865_6d76_5a52_0db1_c8b6eee8b68f
0x18008eff0  mov     rax, [rax+18h]
0x18008eff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eff9  nop
0x18008effa  mov     rcx, r14; SRWLock
0x18008effd  call    cs:__imp_ReleaseSRWLockShared
0x18008f003  mov     rcx, [rsp+88h+arg_30]
0x18008f00b  test    rcx, rcx
0x18008f00e  jz      short loc_18008F07E
0x18008f010  mov     rax, [rsp+88h]
0x18008f018  test    rcx, rcx
0x18008f01b  jz      loc_18008F25E
0x18008f021  mov     rax, [rcx]
0x18008f024  mov     rax, [rax+8]
0x18008f028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f02d  nop
0x18008f02e  mov     rax, [rsp+88h+arg_30]
0x18008f036  mov     [rdi], rax
0x18008f039  mov     rcx, [rsp+88h+newString]; string
0x18008f03e  call    cs:__imp_WindowsDeleteString
0x18008f044  mov     [rsp+88h+newString], rsi
0x18008f049  mov     rcx, [rsp+88h+arg_30]
0x18008f051  test    rcx, rcx
0x18008f054  jz      short loc_18008F06B
0x18008f056  mov     [rsp+88h+arg_30], rsi
0x18008f05e  mov     rax, [rcx]
0x18008f061  mov     rax, [rax+10h]
0x18008f065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f06a  nop
0x18008f06b  xor     eax, eax
0x18008f06d  mov     rbx, [rsp+88h+arg_0]
0x18008f075  add     rsp, 70h
0x18008f079  pop     r14
0x18008f07b  pop     rdi
0x18008f07c  pop     rsi
0x18008f07d  retn
0x18008f07e  mov     rcx, r14; SRWLock
0x18008f081  call    cs:__imp_AcquireSRWLockExclusive
0x18008f087  mov     [rsp+88h+var_50], r14
0x18008f08c  lea     r8, [rsp+88h+newString]
0x18008f091  lea     rdx, [rsp+88h+var_58]
0x18008f096  call    ?find@?$_Hash@V?$_Umap_traits@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@V?$_Uhash_compare@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@U?$hash@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@std@@U?$equal_to@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@7@@std@@V?$allocator@U?$pair@$$CBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@Z; std::_Hash<std::_Umap_traits<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,Microsoft::WRL::WeakRef,std::_Uhash_compare<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,std::hash<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>,std::equal_to<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>>,std::allocator<std::pair<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const,Microsoft::WRL::WeakRef>>,0>>::find(WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const &)
0x18008f09b  mov     rcx, [rsp+88h+var_58]
0x18008f0a0  cmp     rcx, cs:qword_1804DC778
0x18008f0a7  jz      short loc_18008F0BA
0x18008f0a9  add     rcx, 28h ; '('
0x18008f0ad  lea     rdx, [rsp+88h+arg_30]
0x18008f0b5  call    ??$As@UIStartVisualCacheManager@VisualCache@UnifiedTile@Shell@WindowsInternal@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStartVisualCacheManager@VisualCache@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager>>)
0x18008f0ba  cmp     [rsp+88h+arg_30], rsi
0x18008f0c2  jnz     loc_18008F232
0x18008f0c8  lea     rcx, [rsp+88h+arg_30]
0x18008f0d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f0d5  lea     rax, [rsp+88h+arg_28]
0x18008f0dd  mov     [rsp+88h+var_60], rax
0x18008f0e2  lea     rax, [rsp+88h+arg_20]
0x18008f0ea  mov     qword ptr [rsp+88h+var_68], rax; int
0x18008f0ef  lea     r9, [rsp+88h+arg_18]
0x18008f0f7  lea     r8, [rsp+88h+arg_10]
0x18008f0ff  lea     rdx, [rsp+88h+arg_8]
0x18008f107  lea     rcx, [rsp+88h+arg_30]
0x18008f10f  call    ??$MakeAndInitialize@VStartVisualCacheManagerWinRT@VisualCache@UnifiedTile@Shell@WindowsInternal@@UIStartVisualCacheManager@2345@AEAPEAUIUser@System@Windows@@AEAPEAUHSTRING__@@AEAIAEAW4TileThemeSelector@2345@AEAW4VisualCacheOptions@2345@@Details@WRL@Microsoft@@YAJPEAPEAUIStartVisualCacheManager@VisualCache@UnifiedTile@Shell@WindowsInternal@@AEAPEAUIUser@System@Windows@@AEAPEAUHSTRING__@@AEAIAEAW4TileThemeSelector@4567@AEAW4VisualCacheOptions@4567@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::VisualCache::StartVisualCacheManagerWinRT,WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager,Windows::System::IUser * &,HSTRING__ * &,uint &,WindowsInternal::Shell::UnifiedTile::VisualCache::TileThemeSelector &,WindowsInternal::Shell::UnifiedTile::VisualCache::VisualCacheOptions &>(WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager * *,Windows::System::IUser * &,HSTRING__ * &,uint &,WindowsInternal::Shell::UnifiedTile::VisualCache::TileThemeSelector &,WindowsInternal::Shell::UnifiedTile::VisualCache::VisualCacheOptions &)
0x18008f114  mov     ebx, eax
0x18008f116  test    eax, eax
0x18008f118  jns     short loc_18008F17A
0x18008f11a  mov     rcx, [rsp+88h]; this
0x18008f122  mov     r9d, eax; char *
0x18008f125  lea     r8, aShellcommonShe_125; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18008f12c  mov     edx, 60h ; '`'; void *
0x18008f131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f136  nop
0x18008f137  mov     rcx, r14; SRWLock
0x18008f13a  call    cs:__imp_ReleaseSRWLockExclusive
0x18008f140  nop
0x18008f141  mov     rcx, [rsp+88h+newString]; string
0x18008f146  call    cs:__imp_WindowsDeleteString
0x18008f14c  mov     [rsp+88h+newString], rsi
0x18008f151  mov     rcx, [rsp+88h+arg_30]
0x18008f159  test    rcx, rcx
0x18008f15c  jz      short loc_18008F173
0x18008f15e  mov     [rsp+88h+arg_30], rsi
0x18008f166  mov     rax, [rcx]
0x18008f169  mov     rax, [rax+10h]
0x18008f16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f172  nop
0x18008f173  mov     eax, ebx
0x18008f175  jmp     loc_18008F06D
0x18008f17a  mov     [rsp+88h+var_58], rsi
0x18008f17f  lea     rax, [rsp+88h+var_58]
0x18008f184  mov     [rsp+88h+arg_10], rax
0x18008f18c  lea     rcx, [rsp+88h+arg_10]
0x18008f194  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18008f199  mov     rdx, rax
0x18008f19c  mov     rcx, [rsp+88h+arg_30]
0x18008f1a4  call    ??$AsWeak@UIStartVisualCacheManager@VisualCache@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@YAJPEAUIStartVisualCacheManager@VisualCache@UnifiedTile@Shell@WindowsInternal@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager>(WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheManager *,Microsoft::WRL::WeakRef *)
0x18008f1a9  mov     ebx, eax
0x18008f1ab  test    eax, eax
0x18008f1ad  jns     short loc_18008F206
0x18008f1af  mov     rcx, [rsp+88h]; this
0x18008f1b7  mov     r9d, eax; char *
0x18008f1ba  lea     r8, aShellcommonShe_125; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18008f1c1  mov     edx, 62h ; 'b'; void *
0x18008f1c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f1cb  nop
0x18008f1cc  lea     rcx, [rsp+88h+var_58]
0x18008f1d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f1d6  nop
0x18008f1d7  lea     rcx, [rsp+88h+var_50]
0x18008f1dc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18008f1e1  nop
0x18008f1e2  mov     rcx, [rsp+88h+newString]; string
0x18008f1e7  call    cs:__imp_WindowsDeleteString
0x18008f1ed  mov     [rsp+88h+newString], rsi
0x18008f1f2  lea     rcx, [rsp+88h+arg_30]
0x18008f1fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f1ff  mov     eax, ebx
0x18008f201  jmp     loc_18008F06D
0x18008f206  lea     r8, [rsp+88h+newString]
0x18008f20b  lea     rdx, [rsp+88h+var_48]
0x18008f210  call    ??$_Try_emplace@AEBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@$$V@?$_Hash@V?$_Umap_traits@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@V?$_Uhash_compare@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@U?$hash@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@std@@U?$equal_to@UCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@7@@std@@V?$allocator@U?$pair@$$CBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@VWeakRef@WRL@Microsoft@@@std@@PEAX@std@@_N@1@AEBUCacheManagerIdentifier@VisualCache@UnifiedTile@Shell@WindowsInternal@@@Z; std::_Hash<std::_Umap_traits<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,Microsoft::WRL::WeakRef,std::_Uhash_compare<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier,std::hash<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>,std::equal_to<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier>>,std::allocator<std::pair<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const,Microsoft::WRL::WeakRef>>,0>>::_Try_emplace<WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const &,>(WindowsInternal::Shell::UnifiedTile::VisualCache::CacheManagerIdentifier const &)
0x18008f215  mov     rcx, [rax]
0x18008f218  add     rcx, 28h ; '('
0x18008f21c  lea     rdx, [rsp+88h+var_58]
0x18008f221  call    ??4?$ComPtr@UITileQueryFilter@Tiles@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Tiles::ITileQueryFilter>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::Tiles::ITileQueryFilter> const &)
0x18008f226  nop
0x18008f227  lea     rcx, [rsp+88h+var_58]
0x18008f22c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f231  nop
0x18008f232  lea     rcx, [rsp+88h+var_50]
0x18008f237  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18008f23c  mov     rcx, [rsp+88h+arg_30]
0x18008f244  jmp     loc_18008F010
0x18008f249  mov     r9d, eax; char *
0x18008f24c  lea     r8, aShellcommonShe_177; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18008f253  mov     edx, 17h; void *
0x18008f258  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008f25e  lea     r8, aShellcommonShe_125; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18008f265  mov     edx, 67h ; 'g'; void *
0x18008f26a  mov     rcx, rax; this
0x18008f26d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008f273  mov     eax, [rsp+88h+arg_28]
0x18008f27a  jmp     loc_18008F06D
```
