# CSyncRootManagerCache::_EnsureCachedValues(LockCacheAndFreeStale &,SPGSP_FLAGS)

- ea: `0x180009374`
- end: `0x1800095f5`
- name: `?_EnsureCachedValues@CSyncRootManagerCache@@AEAAJAEAVLockCacheAndFreeStale@@W4SPGSP_FLAGS@@@Z`
- size: `641`
- prototype: ``
- caller_count: `12`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008130`
- `0x1800083f0`
- `0x180008a40`
- `0x1800092d0`
- `0x180034524`
- `0x18006770c`
- `0x1800686ec`
- `0x18006898c`
- `0x180068abc`
- `0x180068e7c`
- `0x180069dac`
- `0x18006aa8c`

## callees

- `0x180003278`
- `0x180003890`
- `0x180003914`
- `0x180004d48`
- `0x1800077c8`
- `0x180009374`
- `0x18000c7b8`
- `0x18000ed8c`
- `0x18000ee04`
- `0x180016124`
- `0x1800165bc`
- `0x180016bd8`
- `0x180016d28`
- `0x1800202c0`
- `0x180021d14`
- `0x180037780`
- `0x180059d14`
- `0x18006c4cc`

## import_xrefs

- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800093a3`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800095cd`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800093a3`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800095cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000959d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000959d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000945b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000945b`

## string_xrefs

- `0x18000941d`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSyncRootManagerCache::_EnsureCachedValues(__int64 a1, _QWORD *a2, int a3)
{
  const unsigned __int16 **v6; // rdx
  int v7; // edi
  int SyncRootManagerRegistryLocation; // eax
  int v9; // eax
  bool v10; // sf
  __int64 *v11; // rcx
  _QWORD *v12; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[64]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[8]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v22[13]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v23; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( *(_DWORD *)(a1 + 16) != SHGlobalCounterGetValue(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER)
    || (v7 = 0, (a3 & *(_DWORD *)(a1 + 20)) != a3) )
  {
    a2[1] = *(_QWORD *)(a1 + 32);
    a2[3] = *(_QWORD *)(a1 + 48);
    a2[2] = *(_QWORD *)(a1 + 40);
    a2[4] = *(_QWORD *)(a1 + 56);
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 48) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_QWORD *)(a1 + 56) = 0;
    lpSubKey = 0;
    SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                        (Windows::Internal::SyncRootHelpers *)&lpSubKey,
                                        v6);
    v7 = SyncRootManagerRegistryLocation;
    if ( SyncRootManagerRegistryLocation >= 0 )
    {
      hKey = 0;
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
      v10 = v9 < 0;
      if ( v9 > 0 )
      {
        v9 = (unsigned __int16)v9 | 0x80070000;
        v10 = v9 < 0;
      }
      if ( v10 )
      {
        v7 = HResultIgnoreNotFound(v9);
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SafeRegistryWatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SafeRegistryWatcher>::GetImpl'::`2'::impl) )
        {
          v22[0] = off_18008DD30;
          v23 = v22;
          v18 = 0;
          wil::safe_registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(
            &v18,
            hKey);
          if ( (__int64 *)(a1 + 72) != &v18 )
            wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::replace(
              a1 + 72,
              &v18);
          v11 = &v18;
        }
        else
        {
          v22[0] = off_18008DD58;
          v23 = v22;
          v17 = 0;
          wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(
            &v17,
            hKey);
          if ( (__int64 *)(a1 + 64) != &v17 )
            wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::replace(
              a1 + 64,
              &v17);
          v11 = &v17;
        }
        wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(v11);
        wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v21);
        lpSubKey = 0;
        v12 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(&lpSubKey);
        tip2::details::shared_data<0,0,0>::start(*v12 + 8LL, v19);
        tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::watch_errors(
          &lpSubKey,
          v20);
        v7 = CSyncRootManagerCache::InitializeStorageProviderInfosCache(a1, hKey, (__int64)&lpSubKey, a3);
        if ( lpSubKey )
          tip2::details::shared_data<0,0,0>::complete_without_lock(lpSubKey + 4);
        RegCloseKey(hKey);
        tip2::test_watcher<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::~test_watcher<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>(v20);
        wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>(&lpSubKey);
      }
      if ( v7 >= 0 )
      {
        *(_DWORD *)(a1 + 16) = SHGlobalCounterGetValue(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
        *(_DWORD *)(a1 + 20) = a3;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF34,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)SyncRootManagerRegistryLocation,
        phkResult);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009374  push    rbp
0x180009376  push    rbx
0x180009377  push    rsi
0x180009378  push    rdi
0x180009379  push    r14
0x18000937b  lea     rbp, [rsp-20h]
0x180009380  sub     rsp, 120h
0x180009387  mov     rax, cs:__security_cookie
0x18000938e  xor     rax, rsp
0x180009391  mov     [rbp+40h+var_28], rax
0x180009395  mov     esi, r8d
0x180009398  mov     r14, rdx
0x18000939b  mov     rbx, rcx
0x18000939e  mov     ecx, 39h ; '9'; id
0x1800093a3  call    cs:__imp_SHGlobalCounterGetValue
0x1800093a9  cmp     [rbx+10h], eax
0x1800093ac  jnz     short loc_1800093BD
0x1800093ae  xor     edi, edi
0x1800093b0  mov     eax, [rbx+14h]
0x1800093b3  and     eax, esi
0x1800093b5  cmp     eax, esi
0x1800093b7  jz      loc_1800095D9
0x1800093bd  mov     rax, [rbx+20h]
0x1800093c1  mov     [r14+8], rax
0x1800093c5  mov     rax, [rbx+30h]
0x1800093c9  mov     [r14+18h], rax
0x1800093cd  mov     rax, [rbx+28h]
0x1800093d1  mov     [r14+10h], rax
0x1800093d5  mov     rax, [rbx+38h]
0x1800093d9  mov     [r14+20h], rax
0x1800093dd  mov     qword ptr [rbx+20h], 0
0x1800093e5  mov     qword ptr [rbx+30h], 0
0x1800093ed  mov     qword ptr [rbx+28h], 0
0x1800093f5  mov     qword ptr [rbx+38h], 0
0x1800093fd  mov     [rsp+140h+lpSubKey], 0
0x180009406  lea     rcx, [rsp+140h+lpSubKey]; this
0x18000940b  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x180009410  mov     edi, eax
0x180009412  test    eax, eax
0x180009414  jns     short loc_180009433
0x180009416  mov     rcx, [rbp+48h]; this
0x18000941a  mov     r9d, eax; char *
0x18000941d  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180009424  mov     edx, 0F34h; void *
0x180009429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000942e  jmp     loc_1800095D9
0x180009433  mov     [rsp+140h+hKey], 0
0x18000943c  lea     rax, [rsp+140h+hKey]
0x180009441  mov     qword ptr [rsp+140h+phkResult], rax; phkResult
0x180009446  mov     r9d, 20119h; samDesired
0x18000944c  xor     r8d, r8d; ulOptions
0x18000944f  mov     rdx, [rsp+140h+lpSubKey]; lpSubKey
0x180009454  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000945b  call    cs:__imp_RegOpenKeyExW
0x180009461  test    eax, eax
0x180009463  jle     short loc_18000946F
0x180009465  movzx   eax, ax
0x180009468  or      eax, 80070000h
0x18000946d  test    eax, eax
0x18000946f  js      loc_1800095BB
0x180009475  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SafeRegistryWatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SafeRegistryWatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SafeRegistryWatcher> `wil::Feature<__WilFeatureTraits_Feature_SafeRegistryWatcher>::GetImpl(void)'::`2'::impl
0x18000947c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SafeRegistryWatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SafeRegistryWatcher>::__private_IsEnabled(void)
0x180009481  test    al, al
0x180009483  jnz     short loc_1800094D9
0x180009485  lea     rax, off_18008DD58
0x18000948c  mov     [rbp+40h+var_98], rax
0x180009490  lea     rax, [rbp+40h+var_98]
0x180009494  mov     [rbp+40h+var_30], rax
0x180009498  mov     [rsp+140h+var_100], 0
0x1800094a1  lea     rax, [rbp+40h+var_A0]
0x1800094a5  mov     qword ptr [rsp+140h+phkResult], rax
0x1800094aa  mov     rdx, [rsp+140h+hKey]
0x1800094af  lea     rcx, [rsp+140h+var_100]
0x1800094b4  call    ?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800094b9  nop
0x1800094ba  lea     rcx, [rbx+40h]
0x1800094be  lea     rax, [rsp+140h+var_100]
0x1800094c3  cmp     rcx, rax
0x1800094c6  jz      short loc_1800094D2
0x1800094c8  lea     rdx, [rsp+140h+var_100]
0x1800094cd  call    ?replace@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@IEAAX$$QEAV123@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::replace(wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>> &&)
0x1800094d2  lea     rcx, [rsp+140h+var_100]
0x1800094d7  jmp     short loc_18000952B
0x1800094d9  lea     rax, off_18008DD30
0x1800094e0  mov     [rbp+40h+var_98], rax
0x1800094e4  lea     rax, [rbp+40h+var_98]
0x1800094e8  mov     [rbp+40h+var_30], rax
0x1800094ec  mov     [rsp+140h+var_F8], 0
0x1800094f5  lea     rax, [rbp+40h+var_A0]
0x1800094f9  mov     qword ptr [rsp+140h+phkResult], rax
0x1800094fe  mov     rdx, [rsp+140h+hKey]
0x180009503  lea     rcx, [rsp+140h+var_F8]
0x180009508  call    ?create@?$safe_registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::safe_registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18000950d  nop
0x18000950e  lea     rcx, [rbx+48h]
0x180009512  lea     rax, [rsp+140h+var_F8]
0x180009517  cmp     rcx, rax
0x18000951a  jz      short loc_180009526
0x18000951c  lea     rdx, [rsp+140h+var_F8]
0x180009521  call    ?replace@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@IEAAX$$QEAV123@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::replace(wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>> &&)
0x180009526  lea     rcx, [rsp+140h+var_F8]
0x18000952b  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x180009530  lea     rcx, [rbp+40h+var_A0]
0x180009534  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x180009539  mov     [rsp+140h+lpSubKey], 0
0x180009542  lea     rcx, [rsp+140h+lpSubKey]
0x180009547  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(void)
0x18000954c  mov     rcx, [rax]
0x18000954f  add     rcx, 8
0x180009553  lea     rdx, [rsp+140h+var_F0]
0x180009558  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18000955d  nop
0x18000955e  lea     rdx, [rsp+140h+var_E0]
0x180009563  lea     rcx, [rsp+140h+lpSubKey]
0x180009568  call    ?watch_errors@?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::watch_errors(void)
0x18000956d  nop
0x18000956e  mov     r9d, esi
0x180009571  lea     r8, [rsp+140h+lpSubKey]
0x180009576  mov     rdx, [rsp+140h+hKey]
0x18000957b  mov     rcx, rbx
0x18000957e  call    ?InitializeStorageProviderInfosCache@CSyncRootManagerCache@@AEAAJPEAUHKEY__@@AEAV?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@W4SPGSP_FLAGS@@@Z; CSyncRootManagerCache::InitializeStorageProviderInfosCache(HKEY__ *,tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>> &,SPGSP_FLAGS)
0x180009583  mov     edi, eax
0x180009585  mov     rcx, [rsp+140h+lpSubKey]
0x18000958a  test    rcx, rcx
0x18000958d  jz      short loc_180009598
0x18000958f  add     rcx, 8
0x180009593  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180009598  mov     rcx, [rsp+140h+hKey]; hKey
0x18000959d  call    cs:__imp_RegCloseKey
0x1800095a3  nop
0x1800095a4  lea     rcx, [rsp+140h+var_E0]
0x1800095a9  call    ??1?$test_watcher@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::~test_watcher<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>(void)
0x1800095ae  nop
0x1800095af  lea     rcx, [rsp+140h+lpSubKey]
0x1800095b4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>(void)
0x1800095b9  jmp     short loc_1800095C4
0x1800095bb  mov     ecx, eax; int
0x1800095bd  call    ?HResultIgnoreNotFound@@YAJJ@Z; HResultIgnoreNotFound(long)
0x1800095c2  mov     edi, eax
0x1800095c4  test    edi, edi
0x1800095c6  js      short loc_1800095D9
0x1800095c8  mov     ecx, 39h ; '9'; id
0x1800095cd  call    cs:__imp_SHGlobalCounterGetValue
0x1800095d3  mov     [rbx+10h], eax
0x1800095d6  mov     [rbx+14h], esi
0x1800095d9  mov     eax, edi
0x1800095db  mov     rcx, [rbp+40h+var_28]
0x1800095df  xor     rcx, rsp; StackCookie
0x1800095e2  call    __security_check_cookie
0x1800095e7  add     rsp, 120h
0x1800095ee  pop     r14
0x1800095f0  pop     rdi
0x1800095f1  pop     rsi
0x1800095f2  pop     rbx
0x1800095f3  pop     rbp
0x1800095f4  retn
```
