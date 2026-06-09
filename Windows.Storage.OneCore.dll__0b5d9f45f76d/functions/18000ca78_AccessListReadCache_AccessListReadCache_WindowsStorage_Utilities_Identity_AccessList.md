# AccessListReadCache::AccessListReadCache(WindowsStorage::Utilities::Identity &,AccessList)

- ea: `0x18000ca78`
- end: `0x18000cd37`
- name: `??0AccessListReadCache@@QEAA@AEAVIdentity@Utilities@WindowsStorage@@W4AccessList@@@Z`
- size: `703`
- prototype: `__int64 __fastcall(__int64, WindowsStorage::Utilities::Identity *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180015484`

## callees

- `0x180002be0`
- `0x180004a98`
- `0x18000bfcc`
- `0x18000c538`
- `0x18000c980`
- `0x18000c9dc`
- `0x18000ca78`
- `0x18000d31c`
- `0x18000d504`
- `0x18000d524`
- `0x18000d5a0`
- `0x18000d8cc`
- `0x18000d93c`
- `0x18000f680`
- `0x180010654`
- `0x180010670`
- `0x1800106b0`
- `0x180010828`
- `0x180010dc8`
- `0x180010fdc`
- `0x180011344`
- `0x1800140d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb4d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetSystemAppDataKey` at `0x18000cb38`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetSystemAppDataKey` at `0x18000cbbb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetSystemAppDataKey` at `0x18000cb38`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetSystemAppDataKey` at `0x18000cbbb`

## string_xrefs

- `0x18000cd25`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cccb`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`
- `0x18000cce3`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`
- `0x18000ccfb`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`
- `0x18000cd10`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`

## pseudocode

```c
__int64 __fastcall AccessListReadCache::AccessListReadCache(
        __int64 a1,
        WindowsStorage::Utilities::Identity *a2,
        int a3)
{
  __int64 v3; // rbx
  const WCHAR *v6; // r12
  void *v7; // rax
  const char *v8; // r9
  const char *v9; // r9
  LPCWSTR v10; // rbx
  void *v11; // rax
  const char *v12; // r9
  __int64 v13; // rax
  __int64 v14; // r9
  int v16; // [rsp+20h] [rbp-E0h]
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v19; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[15]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[352]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v3 = a3;
  lpSubKey[1] = (LPCWSTR)a1;
  LODWORD(phkResult) = 0;
  *(_QWORD *)a1 = &AccessListReadCache::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::map<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>::map<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>((_QWORD *)(a1 + 32));
  WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>(a1 + 48);
  start_scoped_activity<TraceProvider::AccessListReadCacheActivity>((__int64)v24);
  if ( (unsigned int)v3 > 2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
      (const char *)0x80070057LL,
      v16);
  v6 = off_180026A28[v3];
  v17 = 0;
  v7 = WindowsStorage::Utilities::Identity::StateHandle(a2);
  if ( (unsigned int)GetSystemAppDataKey(v7, 0, 0, &v17) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
      (const char *)0x8000FFFFLL,
      v16);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
      v8);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    lpSubKey,
    0,
    v17,
    v8);
  LODWORD(phkResult) = 2;
  v10 = lpSubKey[0];
  if ( !lpSubKey[0] )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xFF8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v9);
  ++v17;
  v19 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v19,
    0);
  v11 = WindowsStorage::Utilities::Identity::StateHandle(a2);
  if ( !(unsigned int)GetSystemAppDataKey(v11, &v19, v10, &v17) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
      v12);
  WindowsStorage::Utilities::registry_open_key((unsigned int)&hKey, v19, lpSubKey[0]);
  v13 = WindowsStorage::Utilities::registry_create_key(&phkResult, hKey, v6);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
    a1 + 8,
    v13);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  v23[0] = off_180026180;
  v23[1] = a1;
  v23[13] = v23;
  phkResult = 0;
  LOBYTE(v14) = 1;
  wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    &phkResult,
    hKey,
    v6,
    v14,
    v22);
  wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>>::operator=(
    a1 + 16,
    &phkResult);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&phkResult);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v22);
  AccessListReadCache::Update((AccessListReadCache *)a1);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
  wil::details::lambda_call<_lambda_813137d3af17c759d10d64d1d352cabc_>::~lambda_call<_lambda_813137d3af17c759d10d64d1d352cabc_>((TraceProvider::AccessListReadCacheActivity *)v24);
  return a1;
}

```

## disassembly

```asm
0x18000ca78  push    rbp
0x18000ca7a  push    rbx
0x18000ca7b  push    rsi
0x18000ca7c  push    rdi
0x18000ca7d  push    r12
0x18000ca7f  push    r14
0x18000ca81  push    r15
0x18000ca83  lea     rbp, [rsp-150h]
0x18000ca8b  sub     rsp, 250h
0x18000ca92  mov     rax, cs:__security_cookie
0x18000ca99  xor     rax, rsp
0x18000ca9c  mov     [rbp+180h+var_40], rax
0x18000caa3  movsxd  rbx, r8d
0x18000caa6  mov     rsi, rdx
0x18000caa9  mov     rdi, rcx
0x18000caac  mov     [rsp+280h+var_228], rcx
0x18000cab1  mov     dword ptr [rsp+280h+phkResult], 0
0x18000cab9  lea     rax, ??_7AccessListReadCache@@6B@; const AccessListReadCache::`vftable'
0x18000cac0  mov     [rcx], rax
0x18000cac3  mov     qword ptr [rcx+8], 0
0x18000cacb  mov     qword ptr [rcx+10h], 0
0x18000cad3  mov     qword ptr [rcx+18h], 0
0x18000cadb  add     rcx, 20h ; ' '
0x18000cadf  call    ??0?$map@VNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@U?$less@VNtObjectPath@Utilities@WindowsStorage@@@std@@V?$allocator@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@7@@std@@QEAA@XZ; std::map<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>::map<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>(void)
0x18000cae4  nop
0x18000cae5  lea     rcx, [rdi+30h]
0x18000cae9  call    ??0?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>(void)
0x18000caee  nop
0x18000caef  lea     rcx, [rbp+180h+var_1A0]
0x18000caf3  call    ??$start_scoped_activity@VAccessListReadCacheActivity@TraceProvider@@@@YA?A_PXZ
0x18000caf8  nop
0x18000caf9  mov     rcx, [rbp+188h]; this
0x18000cb00  cmp     ebx, 2
0x18000cb03  ja      loc_18000CCDD
0x18000cb09  lea     r12, off_180026A28; "PersistedStorageItemTable\\ManagedByApp"
0x18000cb10  mov     r12, [r12+rbx*8]
0x18000cb14  mov     [rsp+280h+var_250], 0
0x18000cb1c  mov     rbx, [rbp+188h]
0x18000cb23  mov     rcx, rsi; this
0x18000cb26  call    ?StateHandle@Identity@Utilities@WindowsStorage@@QEAAPEAXXZ; WindowsStorage::Utilities::Identity::StateHandle(void)
0x18000cb2b  mov     rcx, rax
0x18000cb2e  lea     r9, [rsp+280h+var_250]
0x18000cb33  xor     r8d, r8d
0x18000cb36  xor     edx, edx
0x18000cb38  call    cs:__imp_GetSystemAppDataKey
0x18000cb3e  test    eax, eax
0x18000cb40  jnz     loc_18000CCF5
0x18000cb46  mov     rbx, [rbp+188h]
0x18000cb4d  call    cs:__imp_GetLastError
0x18000cb53  cmp     eax, 7Ah ; 'z'
0x18000cb56  jnz     loc_18000CD10
0x18000cb5c  mov     r8d, [rsp+280h+var_250]
0x18000cb61  xor     edx, edx
0x18000cb63  lea     rcx, [rsp+280h+lpSubKey]
0x18000cb68  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000cb6d  mov     dword ptr [rsp+280h+phkResult], 2
0x18000cb75  mov     rcx, [rbp+188h]; this
0x18000cb7c  mov     rbx, [rsp+280h+lpSubKey]
0x18000cb81  test    rbx, rbx
0x18000cb84  jz      loc_18000CD25
0x18000cb8a  inc     [rsp+280h+var_250]
0x18000cb8e  mov     [rsp+280h+var_240], 0
0x18000cb97  xor     edx, edx
0x18000cb99  lea     rcx, [rsp+280h+var_240]
0x18000cb9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000cba3  mov     rcx, rsi; this
0x18000cba6  call    ?StateHandle@Identity@Utilities@WindowsStorage@@QEAAPEAXXZ; WindowsStorage::Utilities::Identity::StateHandle(void)
0x18000cbab  lea     r9, [rsp+280h+var_250]
0x18000cbb0  mov     r8, rbx
0x18000cbb3  lea     rdx, [rsp+280h+var_240]
0x18000cbb8  mov     rcx, rax
0x18000cbbb  call    cs:__imp_GetSystemAppDataKey
0x18000cbc1  mov     rcx, [rbp+188h]; this
0x18000cbc8  test    eax, eax
0x18000cbca  jz      loc_18000CCCB
0x18000cbd0  mov     r8, [rsp+280h+lpSubKey]; lpSubKey
0x18000cbd5  mov     rdx, [rsp+280h+var_240]; hKey
0x18000cbda  lea     rcx, [rsp+280h+hKey]; unsigned int
0x18000cbdf  call    ?registry_open_key@Utilities@WindowsStorage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBGK@Z; WindowsStorage::Utilities::registry_open_key(HKEY__ *,ushort const *,ulong)
0x18000cbe4  nop
0x18000cbe5  mov     r8, r12; lpSubKey
0x18000cbe8  mov     rdx, [rsp+280h+hKey]; hKey
0x18000cbed  lea     rcx, [rsp+280h+phkResult]; phkResult
0x18000cbf2  call    ?registry_create_key@Utilities@WindowsStorage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBGK@Z; WindowsStorage::Utilities::registry_create_key(HKEY__ *,ushort const *,ulong)
0x18000cbf7  mov     rdx, rax
0x18000cbfa  lea     rcx, [rdi+8]
0x18000cbfe  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18000cc03  lea     rcx, [rsp+280h+phkResult]
0x18000cc08  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000cc0d  lea     rax, off_180026180
0x18000cc14  mov     [rsp+280h+var_218], rax
0x18000cc19  mov     [rsp+280h+var_210], rdi
0x18000cc1e  lea     rax, [rsp+280h+var_218]
0x18000cc23  mov     [rbp+180h+var_1B0], rax
0x18000cc27  mov     [rsp+280h+phkResult], 0
0x18000cc30  lea     rax, [rsp+280h+var_220]
0x18000cc35  mov     qword ptr [rsp+280h+var_260], rax
0x18000cc3a  mov     r9b, 1
0x18000cc3d  mov     r8, r12
0x18000cc40  mov     rdx, [rsp+280h+hKey]
0x18000cc45  lea     rcx, [rsp+280h+phkResult]
0x18000cc4a  call    ?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18000cc4f  nop
0x18000cc50  lea     rdx, [rsp+280h+phkResult]
0x18000cc55  lea     rcx, [rdi+10h]
0x18000cc59  call    ??4?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>>::operator=(wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>> &&)
0x18000cc5e  lea     rcx, [rsp+280h+phkResult]
0x18000cc63  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x18000cc68  nop
0x18000cc69  lea     rcx, [rsp+280h+var_220]
0x18000cc6e  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x18000cc73  mov     rcx, rdi; this
0x18000cc76  call    ?Update@AccessListReadCache@@UEAAXXZ; AccessListReadCache::Update(void)
0x18000cc7b  nop
0x18000cc7c  lea     rcx, [rsp+280h+hKey]
0x18000cc81  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000cc86  nop
0x18000cc87  lea     rcx, [rsp+280h+var_240]
0x18000cc8c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000cc91  nop
0x18000cc92  lea     rcx, [rsp+280h+lpSubKey]
0x18000cc97  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000cc9c  nop
0x18000cc9d  lea     rcx, [rbp+180h+var_1A0]; this
0x18000cca1  call    ??1?$lambda_call@V_lambda_813137d3af17c759d10d64d1d352cabc_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_813137d3af17c759d10d64d1d352cabc_>::~lambda_call<_lambda_813137d3af17c759d10d64d1d352cabc_>(void)
0x18000cca6  nop
0x18000cca7  mov     rax, rdi
0x18000ccaa  mov     rcx, [rbp+180h+var_40]
0x18000ccb1  xor     rcx, rsp; StackCookie
0x18000ccb4  call    __security_check_cookie
0x18000ccb9  add     rsp, 250h
0x18000ccc0  pop     r15
0x18000ccc2  pop     r14
0x18000ccc4  pop     r12
0x18000ccc6  pop     rdi
0x18000ccc7  pop     rsi
0x18000ccc8  pop     rbx
0x18000ccc9  pop     rbp
0x18000ccca  retn
0x18000cccb  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x18000ccd2  mov     edx, 2Bh ; '+'; void *
0x18000ccd7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000ccdd  mov     r9d, 80070057h; char *
0x18000cce3  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x18000ccea  mov     edx, 20h ; ' '; void *
0x18000ccef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ccf5  mov     r9d, 8000FFFFh; char *
0x18000ccfb  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x18000cd02  mov     edx, 24h ; '$'; void *
0x18000cd07  mov     rcx, rbx; this
0x18000cd0a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cd10  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x18000cd17  mov     edx, 25h ; '%'; void *
0x18000cd1c  mov     rcx, rbx; this
0x18000cd1f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000cd25  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cd2c  mov     edx, 0FF8h; void *
0x18000cd31  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
