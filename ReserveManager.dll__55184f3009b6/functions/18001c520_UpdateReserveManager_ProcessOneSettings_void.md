# UpdateReserveManager::ProcessOneSettings(void)

- ea: `0x18001c520`
- end: `0x18001c9cb`
- name: `?ProcessOneSettings@UpdateReserveManager@@AEAAJXZ`
- size: `1195`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800177f8`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180010ea4`
- `0x180010fe0`
- `0x18001c520`
- `0x180021e80`
- `0x1800248e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c989`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c5d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c5d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c657`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c97f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c657`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c97f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c6ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c7a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c8a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c6ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c7a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c8a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c721`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c813`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c919`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c721`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c813`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c919`

## string_xrefs

- `0x18001c5e9`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c6c2`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c72d`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c7b7`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c81f`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c8bd`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c925`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c69b`: `DisableDeletes`
- `0x18001c716`: `DisableDeletes`
- `0x18001c5f5`: `UpdateReserveManager::ProcessOneSettings`
- `0x18001c6ce`: `UpdateReserveManager::ProcessOneSettings`
- `0x18001c738`: `UpdateReserveManager::ProcessOneSettings`
- `0x18001c7c2`: `UpdateReserveManager::ProcessOneSettings`
- `0x18001c82a`: `UpdateReserveManager::ProcessOneSettings`
- `0x18001c8c8`: `UpdateReserveManager::ProcessOneSettings`
- `0x18001c930`: `UpdateReserveManager::ProcessOneSettings`
- `0x18001c60a`: `::RegCreateKeyExW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", 0, nullptr, (0x00000004L), ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))), nullptr, &ReserveManagerKey, nullptr)`
- `0x18001c74b`: `::RegSetValueExW(ReserveManagerKey, L"DisableDeletes", 0, ( 4ul ), reinterpret_cast<BYTE*>(&DisableDeletes), sizeof(DisableDeletes))`
- `0x18001c83d`: `::RegSetValueExW(ReserveManagerKey, L"UserFreeSpaceBuffer", 0, ( 4ul ), reinterpret_cast<BYTE*>(&UserFreeSpaceBuffer), sizeof(UserFreeSpaceBuffer))`
- `0x18001c943`: `::RegSetValueExW(ReserveManagerKey, L"DisableSnapshotsInReserves", 0, ( 4ul ), reinterpret_cast<BYTE*>(&DisableSnapshotsInReserves), sizeof(DisableSnapshotsInReserves))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ProcessOneSettings(HKEY *this)
{
  NTSTATUS v2; // eax
  int v3; // ebx
  const char **v4; // rcx
  LSTATUS ValueW; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  const char *v9; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v10; // [rsp+58h] [rbp-A8h]
  __int64 v11; // [rsp+60h] [rbp-A0h]
  const char *v12; // [rsp+68h] [rbp-98h]
  _QWORD v13[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v14[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v15[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v16[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v17[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v18[5]; // [rsp+110h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+138h] [rbp+38h] BYREF
  DWORD pcbData; // [rsp+140h] [rbp+40h] BYREF
  int pvData; // [rsp+144h] [rbp+44h] BYREF
  BYTE Data[4]; // [rsp+148h] [rbp+48h] BYREF
  BYTE v23[4]; // [rsp+14Ch] [rbp+4Ch] BYREF
  HANDLE v24; // [rsp+150h] [rbp+50h] BYREF
  char v25; // [rsp+158h] [rbp+58h]
  _DWORD v26[2]; // [rsp+160h] [rbp+60h] BYREF

  v18[4] = -2;
  v26[0] = 17;
  v26[1] = 18;
  v24 = 0;
  v25 = 0;
  v9 = (const char *)v26;
  v10 = 2;
  v2 = RtlSystemUtil::PrivilegeAcquisition::Acquire((__int64)&v24, (__int64)&v9);
  if ( v2 < 0 )
  {
    v3 = ConvertNtStatusToHResult(v2);
    goto LABEL_46;
  }
  hKey = 0;
  v3 = RegCreateKeyExW(this[13], L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", 0, 0, 4u, 0x2001Fu, 0, &hKey, 0);
  if ( v3 )
  {
    v9 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v10 = (__int64)"UpdateReserveManager::ProcessOneSettings";
    v11 = 4714;
    v12 = "::RegCreateKeyExW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", 0, nullptr, (0"
          "x00000004L), ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x"
          "0002) | (0x0004)) & (~(0x00100000L))), nullptr, &ReserveManagerKey, nullptr)";
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v4 = &v9;
LABEL_7:
    RtlReportErrorOrigination(v4, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v3);
    if ( hKey )
    {
      if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
      hKey = 0;
    }
    goto LABEL_46;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             this[13],
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager\\OneSettings",
             L"DisableDeletes",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v3 = ValueW;
  if ( ValueW != 2 )
  {
    if ( ValueW )
    {
      v13[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v13[1] = "UpdateReserveManager::ProcessOneSettings";
      v13[2] = 4727;
      v13[3] = "RetValue";
      if ( ValueW > 0 )
        v3 = (unsigned __int16)ValueW | 0x80070000;
      v4 = (const char **)v13;
      goto LABEL_7;
    }
    v3 = RegSetValueExW(hKey, L"DisableDeletes", 0, 4u, (const BYTE *)&pvData, 4u);
    if ( v3 )
    {
      v14[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v14[1] = "UpdateReserveManager::ProcessOneSettings";
      v14[2] = 4734;
      v14[3] = "::RegSetValueExW(ReserveManagerKey, L\"DisableDeletes\", 0, ( 4ul ), reinterpret_cast<BYTE*>(&DisableDele"
               "tes), sizeof(DisableDeletes))";
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      v4 = (const char **)v14;
      goto LABEL_7;
    }
  }
  *(_DWORD *)Data = 0;
  pcbData = 4;
  v6 = RegGetValueW(
         this[13],
         L"Microsoft\\Windows\\CurrentVersion\\ReserveManager\\OneSettings",
         L"UserFreeSpaceBuffer",
         0x10u,
         0,
         Data,
         &pcbData);
  v3 = v6;
  if ( v6 != 2 )
  {
    if ( v6 )
    {
      v15[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v15[1] = "UpdateReserveManager::ProcessOneSettings";
      v15[2] = 4748;
      v15[3] = "RetValue";
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      v4 = (const char **)v15;
      goto LABEL_7;
    }
    v3 = RegSetValueExW(hKey, L"UserFreeSpaceBuffer", 0, 4u, Data, 4u);
    if ( v3 )
    {
      v16[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v16[1] = "UpdateReserveManager::ProcessOneSettings";
      v16[2] = 4755;
      v16[3] = "::RegSetValueExW(ReserveManagerKey, L\"UserFreeSpaceBuffer\", 0, ( 4ul ), reinterpret_cast<BYTE*>(&UserFr"
               "eeSpaceBuffer), sizeof(UserFreeSpaceBuffer))";
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      v4 = (const char **)v16;
      goto LABEL_7;
    }
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
  {
    *(_DWORD *)v23 = 0;
    pcbData = 4;
    v7 = RegGetValueW(
           this[13],
           L"Microsoft\\Windows\\CurrentVersion\\ReserveManager\\OneSettings",
           L"DisableSnapshotsInReserves",
           0x10u,
           0,
           v23,
           &pcbData);
    v3 = v7;
    if ( v7 != 2 )
    {
      if ( v7 )
      {
        v17[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v17[1] = "UpdateReserveManager::ProcessOneSettings";
        v17[2] = 4771;
        v17[3] = "RetValue";
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
        v4 = (const char **)v17;
        goto LABEL_7;
      }
      v3 = RegSetValueExW(hKey, L"DisableSnapshotsInReserves", 0, 4u, v23, 4u);
      if ( v3 )
      {
        v18[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v18[1] = "UpdateReserveManager::ProcessOneSettings";
        v18[2] = 4778;
        v18[3] = "::RegSetValueExW(ReserveManagerKey, L\"DisableSnapshotsInReserves\", 0, ( 4ul ), reinterpret_cast<BYTE*"
                 ">(&DisableSnapshotsInReserves), sizeof(DisableSnapshotsInReserves))";
        if ( v3 > 0 )
          v3 = (unsigned __int16)v3 | 0x80070000;
        v4 = (const char **)v18;
        goto LABEL_7;
      }
    }
  }
  if ( hKey )
  {
    if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
    {
      GetLastError();
      __fastfail(7u);
    }
    hKey = 0;
  }
  v3 = 0;
LABEL_46:
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v24);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001c520  mov     rax, rsp
0x18001c523  push    rbp
0x18001c524  push    rdi
0x18001c525  push    r14
0x18001c527  lea     rbp, [rsp-70h]
0x18001c52c  sub     rsp, 170h
0x18001c533  mov     [rbp+80h+var_50], 0FFFFFFFFFFFFFFFEh
0x18001c53b  mov     [rax+10h], rbx
0x18001c53f  mov     [rax+18h], rsi
0x18001c543  mov     rax, cs:__security_cookie
0x18001c54a  xor     rax, rsp
0x18001c54d  mov     [rbp+80h+var_18], rax
0x18001c551  mov     rdi, rcx
0x18001c554  mov     [rbp+80h+var_20], 11h
0x18001c55b  mov     [rbp+80h+var_1C], 12h
0x18001c562  xor     esi, esi
0x18001c564  mov     [rbp+80h+var_30], rsi
0x18001c568  mov     [rbp+80h+var_28], sil
0x18001c56c  lea     rax, [rbp+80h+var_20]
0x18001c570  mov     [rsp+180h+var_130], rax
0x18001c575  mov     [rsp+180h+var_128], 2
0x18001c57e  lea     rdx, [rsp+180h+var_130]
0x18001c583  lea     rcx, [rbp+80h+var_30]
0x18001c587  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x18001c58c  test    eax, eax
0x18001c58e  jns     short loc_18001C59E
0x18001c590  mov     ecx, eax; Status
0x18001c592  call    ConvertNtStatusToHResult
0x18001c597  mov     ebx, eax
0x18001c599  jmp     loc_18001C99C
0x18001c59e  mov     [rbp+80h+hKey], rsi
0x18001c5a2  mov     [rsp+180h+lpdwDisposition], rsi; lpdwDisposition
0x18001c5a7  lea     rax, [rbp+80h+hKey]
0x18001c5ab  mov     [rsp+180h+phkResult], rax; phkResult
0x18001c5b0  mov     [rsp+180h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001c5b5  mov     [rsp+180h+samDesired], 2001Fh; samDesired
0x18001c5bd  mov     r14d, 4
0x18001c5c3  mov     [rsp+180h+dwOptions], r14d; dwOptions
0x18001c5c8  xor     r9d, r9d; lpClass
0x18001c5cb  xor     r8d, r8d; Reserved
0x18001c5ce  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001c5d5  mov     rcx, [rdi+68h]; hKey
0x18001c5d9  call    cs:__imp_RegCreateKeyExW
0x18001c5df  mov     ebx, eax
0x18001c5e1  test    eax, eax
0x18001c5e3  jz      loc_18001C677
0x18001c5e9  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c5f0  mov     [rsp+180h+var_130], rcx
0x18001c5f5  lea     rcx, aUpdatereservem_34; "UpdateReserveManager::ProcessOneSetting"...
0x18001c5fc  mov     [rsp+180h+var_128], rcx
0x18001c601  mov     [rsp+180h+var_120], 126Ah
0x18001c60a  lea     rax, aRegcreatekeyex_0; "::RegCreateKeyExW(m_SoftwareKey, L\"Mic"...
0x18001c611  mov     [rsp+180h+var_118], rax
0x18001c616  test    ebx, ebx
0x18001c618  jle     short loc_18001C623
0x18001c61a  movzx   ebx, bx
0x18001c61d  or      ebx, 80070000h
0x18001c623  lea     rcx, [rsp+180h+var_130]
0x18001c628  mov     r8d, ebx
0x18001c62b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001c632  call    RtlReportErrorOrigination
0x18001c637  nop
0x18001c638  mov     rcx, [rbp+80h+hKey]; hKey
0x18001c63c  test    rcx, rcx
0x18001c63f  jz      loc_18001C99C
0x18001c645  mov     rax, rcx
0x18001c648  mov     rdx, 0FFFFFFFF80000000h
0x18001c64f  and     rax, rdx
0x18001c652  cmp     rax, rdx
0x18001c655  jz      short loc_18001C66E
0x18001c657  call    cs:__imp_RegCloseKey
0x18001c65d  test    eax, eax
0x18001c65f  jz      short loc_18001C66E
0x18001c661  call    cs:__imp_GetLastError
0x18001c667  mov     ecx, 7
0x18001c66c  int     29h; Win8: RtlFailFast(ecx)
0x18001c66e  mov     [rbp+80h+hKey], rsi
0x18001c672  jmp     loc_18001C99C
0x18001c677  mov     [rbp+80h+pvData], esi
0x18001c67a  mov     [rbp+80h+pcbData], r14d
0x18001c67e  lea     rax, [rbp+80h+pcbData]
0x18001c682  mov     [rsp+180h+lpSecurityAttributes], rax; pcbData
0x18001c687  lea     rax, [rbp+80h+pvData]
0x18001c68b  mov     qword ptr [rsp+180h+samDesired], rax; pvData
0x18001c690  mov     qword ptr [rsp+180h+dwOptions], rsi; pdwType
0x18001c695  mov     r9d, 10h; dwFlags
0x18001c69b  lea     r8, aDisabledeletes; "DisableDeletes"
0x18001c6a2  lea     rdx, aMicrosoftWindo_3; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001c6a9  mov     rcx, [rdi+68h]; hkey
0x18001c6ad  call    cs:__imp_RegGetValueW
0x18001c6b3  mov     ebx, eax
0x18001c6b5  cmp     eax, 2
0x18001c6b8  jz      loc_18001C76C
0x18001c6be  test    eax, eax
0x18001c6c0  jz      short loc_18001C702
0x18001c6c2  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c6c9  mov     [rsp+180h+var_110], rcx
0x18001c6ce  lea     rcx, aUpdatereservem_34; "UpdateReserveManager::ProcessOneSetting"...
0x18001c6d5  mov     [rsp+180h+var_108], rcx
0x18001c6da  mov     [rbp+80h+var_100], 1277h
0x18001c6e2  lea     rax, aRetvalue; "RetValue"
0x18001c6e9  mov     [rbp+80h+var_F8], rax
0x18001c6ed  jle     short loc_18001C6F8
0x18001c6ef  movzx   ebx, bx
0x18001c6f2  or      ebx, 80070000h
0x18001c6f8  lea     rcx, [rsp+180h+var_110]
0x18001c6fd  jmp     loc_18001C628
0x18001c702  mov     [rsp+180h+samDesired], r14d; cbData
0x18001c707  lea     rax, [rbp+80h+pvData]
0x18001c70b  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18001c710  mov     r9d, r14d; dwType
0x18001c713  xor     r8d, r8d; Reserved
0x18001c716  lea     rdx, aDisabledeletes; "DisableDeletes"
0x18001c71d  mov     rcx, [rbp+80h+hKey]; hKey
0x18001c721  call    cs:__imp_RegSetValueExW
0x18001c727  mov     ebx, eax
0x18001c729  test    eax, eax
0x18001c72b  jz      short loc_18001C76C
0x18001c72d  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c734  mov     [rbp+80h+var_F0], rcx
0x18001c738  lea     rcx, aUpdatereservem_34; "UpdateReserveManager::ProcessOneSetting"...
0x18001c73f  mov     [rbp+80h+var_E8], rcx
0x18001c743  mov     [rbp+80h+var_E0], 127Eh
0x18001c74b  lea     rax, aRegsetvalueexw_0; "::RegSetValueExW(ReserveManagerKey, L\""...
0x18001c752  mov     [rbp+80h+var_D8], rax
0x18001c756  test    ebx, ebx
0x18001c758  jle     short loc_18001C763
0x18001c75a  movzx   ebx, bx
0x18001c75d  or      ebx, 80070000h
0x18001c763  lea     rcx, [rbp+80h+var_F0]
0x18001c767  jmp     loc_18001C628
0x18001c76c  mov     dword ptr [rbp+80h+Data], esi
0x18001c76f  mov     [rbp+80h+pcbData], r14d
0x18001c773  lea     rax, [rbp+80h+pcbData]
0x18001c777  mov     [rsp+180h+lpSecurityAttributes], rax; pcbData
0x18001c77c  lea     rax, [rbp+80h+Data]
0x18001c780  mov     qword ptr [rsp+180h+samDesired], rax; pvData
0x18001c785  mov     qword ptr [rsp+180h+dwOptions], rsi; pdwType
0x18001c78a  mov     r9d, 10h; dwFlags
0x18001c790  lea     r8, aUserfreespaceb; "UserFreeSpaceBuffer"
0x18001c797  lea     rdx, aMicrosoftWindo_3; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001c79e  mov     rcx, [rdi+68h]; hkey
0x18001c7a2  call    cs:__imp_RegGetValueW
0x18001c7a8  mov     ebx, eax
0x18001c7aa  cmp     eax, 2
0x18001c7ad  jz      loc_18001C85E
0x18001c7b3  test    eax, eax
0x18001c7b5  jz      short loc_18001C7F4
0x18001c7b7  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c7be  mov     [rbp+80h+var_D0], rcx
0x18001c7c2  lea     rcx, aUpdatereservem_34; "UpdateReserveManager::ProcessOneSetting"...
0x18001c7c9  mov     [rbp+80h+var_C8], rcx
0x18001c7cd  mov     [rbp+80h+var_C0], 128Ch
0x18001c7d5  lea     rax, aRetvalue; "RetValue"
0x18001c7dc  mov     [rbp+80h+var_B8], rax
0x18001c7e0  jle     short loc_18001C7EB
0x18001c7e2  movzx   ebx, bx
0x18001c7e5  or      ebx, 80070000h
0x18001c7eb  lea     rcx, [rbp+80h+var_D0]
0x18001c7ef  jmp     loc_18001C628
0x18001c7f4  mov     [rsp+180h+samDesired], r14d; cbData
0x18001c7f9  lea     rax, [rbp+80h+Data]
0x18001c7fd  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18001c802  mov     r9d, r14d; dwType
0x18001c805  xor     r8d, r8d; Reserved
0x18001c808  lea     rdx, aUserfreespaceb; "UserFreeSpaceBuffer"
0x18001c80f  mov     rcx, [rbp+80h+hKey]; hKey
0x18001c813  call    cs:__imp_RegSetValueExW
0x18001c819  mov     ebx, eax
0x18001c81b  test    eax, eax
0x18001c81d  jz      short loc_18001C85E
0x18001c81f  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c826  mov     [rbp+80h+var_B0], rcx
0x18001c82a  lea     rcx, aUpdatereservem_34; "UpdateReserveManager::ProcessOneSetting"...
0x18001c831  mov     [rbp+80h+var_A8], rcx
0x18001c835  mov     [rbp+80h+var_A0], 1293h
0x18001c83d  lea     rax, aRegsetvalueexw_1; "::RegSetValueExW(ReserveManagerKey, L\""...
0x18001c844  mov     [rbp+80h+var_98], rax
0x18001c848  test    ebx, ebx
0x18001c84a  jle     short loc_18001C855
0x18001c84c  movzx   ebx, bx
0x18001c84f  or      ebx, 80070000h
0x18001c855  lea     rcx, [rbp+80h+var_B0]
0x18001c859  jmp     loc_18001C628
0x18001c85e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18001c865  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18001c86a  test    al, al
0x18001c86c  jz      loc_18001C964
0x18001c872  mov     dword ptr [rbp+80h+var_34], esi
0x18001c875  mov     [rbp+80h+pcbData], r14d
0x18001c879  lea     rax, [rbp+80h+pcbData]
0x18001c87d  mov     [rsp+180h+lpSecurityAttributes], rax; pcbData
0x18001c882  lea     rax, [rbp+80h+var_34]
0x18001c886  mov     qword ptr [rsp+180h+samDesired], rax; pvData
0x18001c88b  mov     qword ptr [rsp+180h+dwOptions], rsi; pdwType
0x18001c890  mov     r9d, 10h; dwFlags
0x18001c896  lea     r8, aDisablesnapsho; "DisableSnapshotsInReserves"
0x18001c89d  lea     rdx, aMicrosoftWindo_3; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001c8a4  mov     rcx, [rdi+68h]; hkey
0x18001c8a8  call    cs:__imp_RegGetValueW
0x18001c8ae  mov     ebx, eax
0x18001c8b0  cmp     eax, 2
0x18001c8b3  jz      loc_18001C964
0x18001c8b9  test    eax, eax
0x18001c8bb  jz      short loc_18001C8FA
0x18001c8bd  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c8c4  mov     [rbp+80h+var_90], rcx
0x18001c8c8  lea     rcx, aUpdatereservem_34; "UpdateReserveManager::ProcessOneSetting"...
0x18001c8cf  mov     [rbp+80h+var_88], rcx
0x18001c8d3  mov     [rbp+80h+var_80], 12A3h
0x18001c8db  lea     rax, aRetvalue; "RetValue"
0x18001c8e2  mov     [rbp+80h+var_78], rax
0x18001c8e6  jle     short loc_18001C8F1
0x18001c8e8  movzx   ebx, bx
0x18001c8eb  or      ebx, 80070000h
0x18001c8f1  lea     rcx, [rbp+80h+var_90]
0x18001c8f5  jmp     loc_18001C628
0x18001c8fa  mov     [rsp+180h+samDesired], r14d; cbData
0x18001c8ff  lea     rax, [rbp+80h+var_34]
0x18001c903  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18001c908  mov     r9d, r14d; dwType
0x18001c90b  xor     r8d, r8d; Reserved
0x18001c90e  lea     rdx, aDisablesnapsho; "DisableSnapshotsInReserves"
0x18001c915  mov     rcx, [rbp+80h+hKey]; hKey
0x18001c919  call    cs:__imp_RegSetValueExW
0x18001c91f  mov     ebx, eax
0x18001c921  test    eax, eax
0x18001c923  jz      short loc_18001C964
0x18001c925  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c92c  mov     [rbp+80h+var_70], rcx
0x18001c930  lea     rcx, aUpdatereservem_34; "UpdateReserveManager::ProcessOneSetting"...
0x18001c937  mov     [rbp+80h+var_68], rcx
0x18001c93b  mov     [rbp+80h+var_60], 12AAh
0x18001c943  lea     rax, aRegsetvalueexw; "::RegSetValueExW(ReserveManagerKey, L\""...
0x18001c94a  mov     [rbp+80h+var_58], rax
0x18001c94e  test    ebx, ebx
0x18001c950  jle     short loc_18001C95B
0x18001c952  movzx   ebx, bx
0x18001c955  or      ebx, 80070000h
0x18001c95b  lea     rcx, [rbp+80h+var_70]
0x18001c95f  jmp     loc_18001C628
0x18001c964  mov     rcx, [rbp+80h+hKey]; hKey
0x18001c968  test    rcx, rcx
0x18001c96b  jz      short loc_18001C99A
0x18001c96d  mov     rax, rcx
0x18001c970  mov     rdx, 0FFFFFFFF80000000h
0x18001c977  and     rax, rdx
0x18001c97a  cmp     rax, rdx
0x18001c97d  jz      short loc_18001C996
0x18001c97f  call    cs:__imp_RegCloseKey
0x18001c985  test    eax, eax
0x18001c987  jz      short loc_18001C996
0x18001c989  call    cs:__imp_GetLastError
0x18001c98f  mov     ecx, 7
0x18001c994  int     29h; Win8: RtlFailFast(ecx)
0x18001c996  mov     [rbp+80h+hKey], rsi
0x18001c99a  mov     ebx, esi
0x18001c99c  lea     rcx, [rbp+80h+var_30]; this
0x18001c9a0  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001c9a5  mov     eax, ebx
0x18001c9a7  mov     rcx, [rbp+80h+var_18]
0x18001c9ab  xor     rcx, rsp; StackCookie
0x18001c9ae  call    __security_check_cookie
0x18001c9b3  lea     r11, [rsp+180h+var_10]
0x18001c9bb  mov     rbx, [r11+28h]
0x18001c9bf  mov     rsi, [r11+30h]
0x18001c9c3  mov     rsp, r11
0x18001c9c6  pop     r14
0x18001c9c8  pop     rdi
0x18001c9c9  pop     rbp
0x18001c9ca  retn
```
