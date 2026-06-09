# CellularUxBackupRestoreHandler::BackupMeteredToogle(Windows::Data::NetworkUX::Cellular::CellularSettings &)

- ea: `0x1800f255c`
- end: `0x1800f28fc`
- name: `?BackupMeteredToogle@CellularUxBackupRestoreHandler@@AEAA_NAEAUCellularSettings@Cellular@NetworkUX@Data@Windows@@@Z`
- size: `928`
- prototype: `bool __fastcall(CellularUxBackupRestoreHandler *__hidden this, struct Windows::Data::NetworkUX::Cellular::CellularSettings *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f2fe0`

## callees

- `0x18000c6e0`
- `0x18001cf84`
- `0x18001d0a8`
- `0x18001daf4`
- `0x18001faa8`
- `0x18002498c`
- `0x180031774`
- `0x1800bf3dc`
- `0x1800d0b4c`
- `0x1800d256c`
- `0x1800ee2c8`
- `0x1800f0ccc`
- `0x1800f0cf8`
- `0x1800f112c`
- `0x1800f1818`
- `0x1800f184c`
- `0x1800f2034`
- `0x1800f21c8`
- `0x1800f255c`
- `0x1800f2e28`
- `0x1800f4198`
- `0x1800f41c8`
- `0x1800f4260`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x1800f25f4`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800f25f4`
- `ADVAPI32!RegGetValueW` at `0x1800f26ef`
- `ADVAPI32!RegGetValueW` at `0x1800f26ef`
- `ADVAPI32!RegEnumKeyExW` at `0x1800f2771`
- `ADVAPI32!RegEnumKeyExW` at `0x1800f280d`
- `ADVAPI32!RegEnumKeyExW` at `0x1800f2771`
- `ADVAPI32!RegEnumKeyExW` at `0x1800f280d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f263e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f2681`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f263e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f2681`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall CellularUxBackupRestoreHandler::BackupMeteredToogle(
        CellularUxBackupRestoreHandler *this,
        struct Windows::Data::NetworkUX::Cellular::CellularSettings *a2)
{
  __int64 v3; // rax
  const WCHAR *v4; // rax
  unsigned int v5; // eax
  int v6; // esi
  DWORD i; // edx
  int v8; // edi
  DWORD j; // edx
  int v10; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v14; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  int pvData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  DWORD pdwType; // [rsp+74h] [rbp-8Ch] BYREF
  _BYTE v22[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h]
  _BYTE v24[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v25[16]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v26[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v27[32]; // [rsp+C8h] [rbp-38h] BYREF
  int v28[6]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Name[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SubKey[264]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  v17 = 0;
  v16 = std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>>>(this);
  v26[0] = 0;
  v26[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v26[0]) = 0;
  std::wstring::resize(v26, 256);
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
  if ( (int)RtlGetPersistedStateLocation(
              L"WcmSvcRoot",
              0,
              L"SOFTWARE\\Microsoft\\WcmSvc\\SubscriptionManager",
              0,
              v3,
              512,
              0) < 0 )
    std::wstring::_Assign<unsigned short>(v26, L"SOFTWARE\\Microsoft\\WcmSvc\\SubscriptionManager", 45);
  hKey = 0;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x18C,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\cellularuxbackuprestorehandler.cpp",
      (const char *)v5,
      phkResult);
  v6 = 1;
  for ( i = 0; ; i = v6++ )
  {
    v14 = 260;
    if ( RegEnumKeyExW(hKey, i, SubKey, &v14, 0, 0, 0, 0) )
      break;
    hkey = 0;
    if ( RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hkey) )
      goto LABEL_19;
    Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs::ImsiMeteredPairs((Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs *)v22);
    v8 = 1;
    for ( j = 0; ; j = v8++ )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hkey, j, Name, &cchName, 0, 0, 0, 0) )
        break;
      pdwType = 4;
      pcbData = 4;
      pvData = 0;
      if ( RegGetValueW(hkey, Name, L"UserCost", 0x10u, &pdwType, &pvData, &pcbData) )
        continue;
      if ( pvData )
      {
        if ( pvData != 1 )
        {
          CloudRestoreLauncherTelemetry::UnsupportedMeteredValueSkipped();
          continue;
        }
        v10 = 1;
      }
      else
      {
        v10 = 0;
      }
      std::wstring::wstring(v27, Name);
      v28[0] = v10;
      std::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>>,0>>::insert<0,0>(
        v22,
        v24,
        v27);
      std::wstring::_Tidy_deallocate(v27);
    }
    if ( v23 )
    {
      std::wstring::wstring(v27, SubKey);
      std::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>(
        v28,
        v22);
      std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>,0>>::insert<0,0>(
        &v16,
        v25,
        v27);
      std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>::~pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>(v27);
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,enum Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,enum Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>,void *>>>(
      v22,
      v22);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  if ( !v17 )
  {
    CloudRestoreLauncherTelemetry::NoMeteredBackupValuesToBackupEvent();
    goto LABEL_23;
  }
  if ( !*((_BYTE *)a2 + 8) )
    goto LABEL_29;
  if ( !(unsigned __int8)std::operator!=<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>>(
                           (char *)a2 + 16,
                           &v16) )
  {
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v26);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>>>(
      &v16,
      &v16);
    return 0;
  }
  if ( !*((_BYTE *)a2 + 8) )
  {
LABEL_29:
    boost::optional_detail::optional_base<std::map<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>::construct(
      (char *)a2 + 8,
      &v16);
    goto LABEL_30;
  }
  if ( (__int64 *)((char *)a2 + 16) != &v16 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>,0>>::clear((char *)a2 + 16);
    std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>,0>>::_Copy<0>(
      (char *)a2 + 16,
      &v16);
  }
LABEL_30:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v26);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>>>(
    &v16,
    &v16);
  return 1;
}

```

## disassembly

```asm
0x1800f255c  push    rbp
0x1800f255e  push    rbx
0x1800f255f  push    rsi
0x1800f2560  push    rdi
0x1800f2561  push    r14
0x1800f2563  push    r15
0x1800f2565  lea     rbp, [rsp-438h]
0x1800f256d  sub     rsp, 538h
0x1800f2574  mov     rax, cs:__security_cookie
0x1800f257b  xor     rax, rsp
0x1800f257e  mov     [rbp+460h+var_40], rax
0x1800f2585  mov     r14, rdx
0x1800f2588  xor     r15d, r15d
0x1800f258b  mov     [rsp+560h+var_510], r15
0x1800f2590  mov     [rsp+560h+var_508], r15
0x1800f2595  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>> &)
0x1800f259a  mov     [rsp+560h+var_510], rax
0x1800f259f  xorps   xmm0, xmm0
0x1800f25a2  movups  [rbp+460h+var_4B8], xmm0
0x1800f25a6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800f25ae  movdqu  [rbp+460h+var_4A8], xmm1
0x1800f25b3  mov     word ptr [rbp+460h+var_4B8], r15w
0x1800f25b8  mov     edx, 100h
0x1800f25bd  lea     rcx, [rbp+460h+var_4B8]
0x1800f25c1  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800f25c6  lea     rcx, [rbp+460h+var_4B8]
0x1800f25ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f25cf  mov     [rsp+560h+pcbData], r15
0x1800f25d4  mov     dword ptr [rsp+560h+pvData], 200h
0x1800f25dc  mov     [rsp+560h+phkResult], rax
0x1800f25e1  xor     r9d, r9d
0x1800f25e4  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\WcmSvc\\Subscripti"...
0x1800f25eb  xor     edx, edx
0x1800f25ed  lea     rcx, aWcmsvcroot; "WcmSvcRoot"
0x1800f25f4  call    cs:__imp_RtlGetPersistedStateLocation
0x1800f25fa  test    eax, eax
0x1800f25fc  jns     short loc_1800F2613
0x1800f25fe  lea     r8d, [r15+2Dh]
0x1800f2602  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WcmSvc\\Subscripti"...
0x1800f2609  lea     rcx, [rbp+460h+var_4B8]
0x1800f260d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800f2612  nop
0x1800f2613  mov     [rsp+560h+hKey], r15
0x1800f2618  lea     rcx, [rbp+460h+var_4B8]
0x1800f261c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f2621  mov     rdx, rax; lpSubKey
0x1800f2624  lea     rax, [rsp+560h+hKey]
0x1800f2629  mov     [rsp+560h+phkResult], rax; unsigned int
0x1800f262e  mov     r9d, 20019h; samDesired
0x1800f2634  xor     r8d, r8d; ulOptions
0x1800f2637  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f263e  call    cs:__imp_RegOpenKeyExW
0x1800f2644  mov     rcx, [rbp+468h]; this
0x1800f264b  test    eax, eax
0x1800f264d  jnz     loc_1800F28E7
0x1800f2653  lea     esi, [rax+1]
0x1800f2656  xor     edx, edx
0x1800f2658  jmp     loc_1800F27E0
0x1800f265d  mov     [rsp+560h+hkey], r15
0x1800f2662  lea     rax, [rsp+560h+hkey]
0x1800f2667  mov     [rsp+560h+phkResult], rax; phkResult
0x1800f266c  mov     r9d, 20019h; samDesired
0x1800f2672  xor     r8d, r8d; ulOptions
0x1800f2675  lea     rdx, [rbp+460h+SubKey]; lpSubKey
0x1800f267c  mov     rcx, [rsp+560h+hKey]; hKey
0x1800f2681  call    cs:__imp_RegOpenKeyExW
0x1800f2687  test    eax, eax
0x1800f2689  jnz     loc_1800F27D2
0x1800f268f  lea     rcx, [rsp+560h+var_4E8]; this
0x1800f2694  call    ??0ImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@QEAA@XZ; Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs::ImsiMeteredPairs(void)
0x1800f2699  nop
0x1800f269a  mov     edi, 1
0x1800f269f  xor     edx, edx
0x1800f26a1  jmp     loc_1800F2747
0x1800f26a6  mov     [rsp+560h+pdwType], 4
0x1800f26ae  mov     [rsp+560h+var_4F0], 4
0x1800f26b6  mov     [rsp+560h+var_500], r15d
0x1800f26bb  lea     rax, [rsp+560h+var_4F0]
0x1800f26c0  mov     [rsp+560h+pcbData], rax; pcbData
0x1800f26c5  lea     rax, [rsp+560h+var_500]
0x1800f26ca  mov     [rsp+560h+pvData], rax; pvData
0x1800f26cf  lea     rax, [rsp+560h+pdwType]
0x1800f26d4  mov     [rsp+560h+phkResult], rax; pdwType
0x1800f26d9  mov     r9d, 10h; dwFlags
0x1800f26df  lea     r8, aUsercost; "UserCost"
0x1800f26e6  lea     rdx, [rbp+460h+Name]; lpSubKey
0x1800f26ea  mov     rcx, [rsp+560h+hkey]; hkey
0x1800f26ef  call    cs:__imp_RegGetValueW
0x1800f26f5  test    eax, eax
0x1800f26f7  jnz     short loc_1800F2743
0x1800f26f9  mov     eax, [rsp+560h+var_500]
0x1800f26fd  test    eax, eax
0x1800f26ff  jz      short loc_1800F2714
0x1800f2701  cmp     eax, 1
0x1800f2704  jz      short loc_1800F270D
0x1800f2706  call    ?UnsupportedMeteredValueSkipped@CloudRestoreLauncherTelemetry@@SAXXZ; CloudRestoreLauncherTelemetry::UnsupportedMeteredValueSkipped(void)
0x1800f270b  jmp     short loc_1800F2743
0x1800f270d  mov     ebx, 1
0x1800f2712  jmp     short loc_1800F2717
0x1800f2714  mov     ebx, r15d
0x1800f2717  lea     rdx, [rbp+460h+Name]
0x1800f271b  lea     rcx, [rbp+460h+var_498]
0x1800f271f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f2724  mov     [rbp+460h+var_478], ebx
0x1800f2727  lea     r8, [rbp+460h+var_498]
0x1800f272b  lea     rdx, [rbp+460h+var_4D8]
0x1800f272f  lea     rcx, [rsp+560h+var_4E8]
0x1800f2734  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MeteredValue@3_bond_enumerators@Cellular@NetworkUX@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MeteredValue@3_bond_enumerators@Cellular@NetworkUX@Data@Windows@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MeteredValue@3_bond_enumerators@Cellular@NetworkUX@Data@Windows@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MeteredValue@3_bond_enumerators@Cellular@NetworkUX@Data@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>>,0>>::insert<0,0>(std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue> &&)
0x1800f2739  nop
0x1800f273a  lea     rcx, [rbp+460h+var_498]
0x1800f273e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f2743  mov     edx, edi; dwIndex
0x1800f2745  inc     edi
0x1800f2747  mov     [rsp+560h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800f274c  mov     [rsp+560h+pcbData], r15; lpcchClass
0x1800f2751  mov     [rsp+560h+pvData], r15; lpClass
0x1800f2756  mov     [rsp+560h+phkResult], r15; lpReserved
0x1800f275b  mov     [rsp+560h+cchName], 104h
0x1800f2763  lea     r9, [rsp+560h+cchName]; lpcchName
0x1800f2768  lea     r8, [rbp+460h+Name]; lpName
0x1800f276c  mov     rcx, [rsp+560h+hkey]; hKey
0x1800f2771  call    cs:__imp_RegEnumKeyExW
0x1800f2777  test    eax, eax
0x1800f2779  jz      loc_1800F26A6
0x1800f277f  cmp     [rbp+460h+var_4E0], r15
0x1800f2783  jz      short loc_1800F27C2
0x1800f2785  lea     rdx, [rbp+460h+SubKey]
0x1800f278c  lea     rcx, [rbp+460h+var_498]
0x1800f2790  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f2795  nop
0x1800f2796  lea     rdx, [rsp+560h+var_4E8]
0x1800f279b  lea     rcx, [rbp+460h+var_478]
0x1800f279f  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>,void *>> &&)
0x1800f27a4  nop
0x1800f27a5  lea     r8, [rbp+460h+var_498]
0x1800f27a9  lea     rdx, [rbp+460h+var_4C8]
0x1800f27ad  lea     rcx, [rsp+560h+var_510]
0x1800f27b2  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>,0>>::insert<0,0>(std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs> &&)
0x1800f27b7  nop
0x1800f27b8  lea     rcx, [rbp+460h+var_498]
0x1800f27bc  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@QEAA@XZ; std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>::~pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>(void)
0x1800f27c1  nop
0x1800f27c2  lea     rdx, [rsp+560h+var_4E8]
0x1800f27c7  lea     rcx, [rsp+560h+var_4E8]
0x1800f27cc  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MeteredValue@3_bond_enumerators@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MeteredValue@3_bond_enumerators@Cellular@NetworkUX@Data@Windows@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MeteredValue@3_bond_enumerators@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>,void *>> &)
0x1800f27d1  nop
0x1800f27d2  lea     rcx, [rsp+560h+hkey]
0x1800f27d7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f27dc  mov     edx, esi; dwIndex
0x1800f27de  inc     esi
0x1800f27e0  mov     [rsp+560h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800f27e5  mov     [rsp+560h+pcbData], r15; lpcchClass
0x1800f27ea  mov     [rsp+560h+pvData], r15; lpClass
0x1800f27ef  mov     [rsp+560h+phkResult], r15; lpReserved
0x1800f27f4  mov     [rsp+560h+var_51C], 104h
0x1800f27fc  lea     r9, [rsp+560h+var_51C]; lpcchName
0x1800f2801  lea     r8, [rbp+460h+SubKey]; lpName
0x1800f2808  mov     rcx, [rsp+560h+hKey]; hKey
0x1800f280d  call    cs:__imp_RegEnumKeyExW
0x1800f2813  test    eax, eax
0x1800f2815  jz      loc_1800F265D
0x1800f281b  cmp     [rsp+560h+var_508], r15
0x1800f2820  jnz     short loc_1800F2850
0x1800f2822  call    ?NoMeteredBackupValuesToBackupEvent@CloudRestoreLauncherTelemetry@@SAXXZ; CloudRestoreLauncherTelemetry::NoMeteredBackupValuesToBackupEvent(void)
0x1800f2827  nop
0x1800f2828  lea     rcx, [rsp+560h+hKey]
0x1800f282d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f2832  nop
0x1800f2833  lea     rcx, [rbp+460h+var_4B8]
0x1800f2837  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f283c  nop
0x1800f283d  lea     rdx, [rsp+560h+var_510]
0x1800f2842  lea     rcx, [rsp+560h+var_510]
0x1800f2847  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>> &)
0x1800f284c  xor     al, al
0x1800f284e  jmp     short loc_1800F28C8
0x1800f2850  lea     rdi, [r14+8]
0x1800f2854  lea     rbx, [rdi+8]
0x1800f2858  cmp     [rdi], r15b
0x1800f285b  jz      short loc_1800F2894
0x1800f285d  lea     rdx, [rsp+560h+var_510]
0x1800f2862  mov     rcx, rbx
0x1800f2865  call    ??$?9V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@1@@std@@YA_NAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@2@@0@0@Z; std::operator!=<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>>(std::map<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs> const &,std::map<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs> const &)
0x1800f286a  test    al, al
0x1800f286c  jz      short loc_1800F2828
0x1800f286e  cmp     [rdi], r15b
0x1800f2871  jz      short loc_1800F2894
0x1800f2873  lea     rax, [rsp+560h+var_510]
0x1800f2878  cmp     rbx, rax
0x1800f287b  jz      short loc_1800F28A2
0x1800f287d  mov     rcx, rbx
0x1800f2880  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>,0>>::clear(void)
0x1800f2885  lea     rdx, [rsp+560h+var_510]
0x1800f288a  mov     rcx, rbx
0x1800f288d  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>,0>> const &)
0x1800f2892  jmp     short loc_1800F28A2
0x1800f2894  lea     rdx, [rsp+560h+var_510]
0x1800f2899  mov     rcx, rdi
0x1800f289c  call    ?construct@?$optional_base@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@2@@std@@@optional_detail@boost@@IEAAXAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@2@@std@@@Z; boost::optional_detail::optional_base<std::map<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>::construct(std::map<std::wstring,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs> const &)
0x1800f28a1  nop
0x1800f28a2  lea     rcx, [rsp+560h+hKey]
0x1800f28a7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f28ac  nop
0x1800f28ad  lea     rcx, [rbp+460h+var_4B8]
0x1800f28b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f28b6  nop
0x1800f28b7  lea     rdx, [rsp+560h+var_510]
0x1800f28bc  lea     rcx, [rsp+560h+var_510]
0x1800f28c1  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UImsiMeteredPairs@Cellular@NetworkUX@Data@Windows@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs>,void *>> &)
0x1800f28c6  mov     al, 1
0x1800f28c8  mov     rcx, [rbp+460h+var_40]
0x1800f28cf  xor     rcx, rsp; StackCookie
0x1800f28d2  call    __security_check_cookie
0x1800f28d7  add     rsp, 538h
0x1800f28de  pop     r15
0x1800f28e0  pop     r14
0x1800f28e2  pop     rdi
0x1800f28e3  pop     rsi
0x1800f28e4  pop     rbx
0x1800f28e5  pop     rbp
0x1800f28e6  retn
0x1800f28e7  mov     r9d, eax; char *
0x1800f28ea  lea     r8, aPcshellShellCl_37; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f28f1  mov     edx, 18Ch; void *
0x1800f28f6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
