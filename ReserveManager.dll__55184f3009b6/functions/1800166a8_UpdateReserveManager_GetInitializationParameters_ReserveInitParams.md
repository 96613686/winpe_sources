# UpdateReserveManager::GetInitializationParameters(ReserveInitParams *)

- ea: `0x1800166a8`
- end: `0x180016bb3`
- name: `?GetInitializationParameters@UpdateReserveManager@@AEAAJPEAUReserveInitParams@@@Z`
- size: `1291`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, struct ReserveInitParams *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180019634`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x1800127c8`
- `0x180015ad0`
- `0x1800166a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016729`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800167b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001681b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016958`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800169ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016729`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800167b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001681b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016958`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800169ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a6b`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180016858`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180016858`

## string_xrefs

- `0x180016735`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800167c1`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180016871`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800168a7`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800168e9`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180016b3d`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001688f`: `EnsureBOOL(::GetDiskFreeSpaceW(m_WindowsDirPath, &SectorsPerCluster, &BytesPerSector, &NumberOfFreeClusters, &TotalNumberOfClusters))`
- `0x180016748`: `UpdateReserveManager::GetInitializationParameters`
- `0x1800167d4`: `UpdateReserveManager::GetInitializationParameters`
- `0x180016884`: `UpdateReserveManager::GetInitializationParameters`
- `0x1800168b2`: `UpdateReserveManager::GetInitializationParameters`
- `0x1800168fc`: `UpdateReserveManager::GetInitializationParameters`
- `0x180016b50`: `UpdateReserveManager::GetInitializationParameters`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetInitializationParameters(
        UpdateReserveManager *this,
        struct ReserveInitParams *a2)
{
  __int64 result; // rax
  __int64 v5; // r12
  HKEY v6; // rcx
  int ValueW; // ebx
  const char *v8; // rax
  bool v9; // cc
  HKEY v10; // rcx
  HKEY v11; // rcx
  __int64 v12; // r14
  const char *v13; // rax
  HKEY v14; // rcx
  unsigned __int64 v15; // rsi
  __int64 v16; // r13
  unsigned int v17; // eax
  unsigned __int128 v18; // rax
  unsigned __int64 v19; // kr00_8
  unsigned __int128 v20; // rtt
  __int64 v21; // rcx
  unsigned __int64 v22; // rax
  unsigned int v23; // eax
  unsigned __int64 v24; // r9
  const char *v25; // [rsp+40h] [rbp-59h] BYREF
  const char *v26; // [rsp+48h] [rbp-51h]
  __int64 v27; // [rsp+50h] [rbp-49h]
  const char *v28; // [rsp+58h] [rbp-41h]
  DWORD pcbData; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v30; // [rsp+68h] [rbp-31h] BYREF
  int v31; // [rsp+70h] [rbp-29h] BYREF
  int v32; // [rsp+74h] [rbp-25h] BYREF
  DWORD BytesPerSector; // [rsp+78h] [rbp-21h] BYREF
  DWORD SectorsPerCluster; // [rsp+7Ch] [rbp-1Dh] BYREF
  DWORD TotalNumberOfClusters; // [rsp+80h] [rbp-19h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+84h] [rbp-15h] BYREF
  DWORD v37; // [rsp+88h] [rbp-11h] BYREF
  __int64 v38; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int64 v39; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int64 pvData; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v41; // [rsp+A8h] [rbp+Fh] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode(this);
  v5 = 0;
  if ( (int)result < 0 )
    return result;
  v6 = (HKEY)*((_QWORD *)this + 13);
  pvData = 0;
  pcbData = 8;
  ValueW = RegGetValueW(
             v6,
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
             L"BaseHardReserveSize",
             0x40u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW )
  {
    v27 = 2171;
    v25 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v26 = "UpdateReserveManager::GetInitializationParameters";
    v8 = "::RegGetValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\"BaseHardReserve"
         "Size\", 0x00000040, nullptr, &BaseHardReserveSize, &DataMax)";
LABEL_4:
    v9 = ValueW <= 0;
LABEL_5:
    v28 = v8;
    if ( !v9 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    RtlReportErrorOrigination(&v25, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
    return (unsigned int)ValueW;
  }
  v10 = (HKEY)*((_QWORD *)this + 13);
  v41 = 0;
  pcbData = 8;
  ValueW = RegGetValueW(
             v10,
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
             L"BaseSoftReserveSize",
             0x40u,
             0,
             &v41,
             &pcbData);
  if ( ValueW )
  {
    v27 = 2181;
    v25 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v26 = "UpdateReserveManager::GetInitializationParameters";
    v8 = "::RegGetValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\"BaseSoftReserve"
         "Size\", 0x00000040, nullptr, &BaseSoftReserveSize, &DataMax)";
    goto LABEL_4;
  }
  v11 = (HKEY)*((_QWORD *)this + 13);
  v38 = 0;
  pcbData = 8;
  ValueW = RegGetValueW(
             v11,
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
             L"HardReserveAdjustment",
             0x40u,
             0,
             &v38,
             &pcbData);
  if ( ValueW == 2 )
  {
    v38 = 0;
  }
  else
  {
    v9 = ValueW <= 0;
    if ( ValueW )
    {
      v27 = 2199;
LABEL_18:
      v25 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v26 = "UpdateReserveManager::GetInitializationParameters";
      v8 = "RetValue";
      goto LABEL_5;
    }
  }
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  NumberOfFreeClusters = 0;
  TotalNumberOfClusters = 0;
  if ( !GetDiskFreeSpaceW(
          (LPCWSTR)this + 68,
          &SectorsPerCluster,
          &BytesPerSector,
          &NumberOfFreeClusters,
          &TotalNumberOfClusters) )
  {
    if ( GetLastError() )
    {
      ValueW = GetLastError();
      if ( !ValueW )
        INTERNAL_ERROR_ACTION(-1073741595);
    }
    else
    {
      ValueW = 14077;
    }
    v27 = 2203;
    v25 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v26 = "UpdateReserveManager::GetInitializationParameters";
    v8 = "EnsureBOOL(::GetDiskFreeSpaceW(m_WindowsDirPath, &SectorsPerCluster, &BytesPerSector, &NumberOfFreeClusters, &T"
         "otalNumberOfClusters))";
    goto LABEL_4;
  }
  v12 = pvData + v38;
  if ( pvData + v38 < pvData )
  {
    v27 = 2213;
    v25 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v26 = "UpdateReserveManager::GetInitializationParameters";
    v13 = "::ULongLongAdd(BaseHardReserveSize, HardReserveAdjustment, &TargetHardReserveSize)";
LABEL_47:
    v28 = v13;
    RtlReportErrorOrigination(&v25, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
    return 2147942934LL;
  }
  v14 = (HKEY)*((_QWORD *)this + 13);
  v15 = SectorsPerCluster * BytesPerSector;
  v16 = v41;
  v31 = 0;
  v37 = 4;
  ValueW = RegGetValueW(
             v14,
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
             L"PostUpgradeFreeSpace",
             0x10u,
             0,
             &v31,
             &v37);
  if ( ValueW == 2 )
  {
    v17 = 100;
    v31 = 100;
    goto LABEL_28;
  }
  v9 = ValueW <= 0;
  if ( ValueW )
  {
    v27 = 2263;
    goto LABEL_18;
  }
  v17 = v31;
LABEL_28:
  v19 = v17;
  v18 = v17 * (unsigned __int128)0x100000uLL;
  v39 = 0;
  if ( !is_mul_ok(v19, 0x100000u) )
  {
    v27 = 2268;
    v25 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v26 = "UpdateReserveManager::GetInitializationParameters";
    v13 = "::ULongLongMult(PostUpgradeFreeSpaceValue, 1048576, &PostUpgradeFreeSpace)";
    goto LABEL_47;
  }
  v30 = 0;
  pcbData = 8;
  *(_QWORD *)&v20 = v18 + v15 - 1;
  *((_QWORD *)&v20 + 1) = *((_QWORD *)&v18 + 1);
  v21 = v20 - v20 % v15;
  if ( v21 )
    v5 = v21;
  ValueW = RegGetValueW(
             *((HKEY *)this + 13),
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
             L"UserFreeSpaceMarker",
             0x40u,
             0,
             &v30,
             &pcbData);
  if ( ValueW == 2 )
  {
    v22 = 0;
    goto LABEL_36;
  }
  v9 = ValueW <= 0;
  if ( ValueW )
  {
    v27 = 2295;
    goto LABEL_18;
  }
  v22 = v30;
LABEL_36:
  v32 = 0;
  pcbData = 4;
  v30 = v22 + v15 - 1 - (v22 + v15 - 1) % v15;
  ValueW = RegGetValueW(
             *((HKEY *)this + 13),
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
             L"UserFreeSpaceBuffer",
             0x10u,
             0,
             &v32,
             &pcbData);
  if ( ValueW == 2 )
  {
    v23 = 314572800;
    v32 = 314572800;
    goto LABEL_41;
  }
  v9 = ValueW <= 0;
  if ( ValueW )
  {
    v27 = 2315;
    goto LABEL_18;
  }
  v23 = v32;
LABEL_41:
  if ( v30 >= v23 )
    v30 -= v23;
  else
    v30 = 0;
  v39 = 0;
  result = UpdateReserveManager::CalculateTotalPendingScratchIncrease((HKEY *)this, &v39);
  if ( (int)result >= 0 )
  {
    v24 = v39;
    *(_QWORD *)a2 = v15;
    *((_QWORD *)a2 + 1) = v5;
    *((_QWORD *)a2 + 2) = v30;
    *((_QWORD *)a2 + 6) = v15 + v24 - 1 - (v15 + v24 - 1) % v15;
    *((_QWORD *)a2 + 3) = v15 + v12 - 1 - (v15 + v12 - 1) % v15;
    *((_QWORD *)a2 + 4) = v15 + v16 - 1 - (v15 + v16 - 1) % v15;
    *((_QWORD *)a2 + 5) = v15 + 2684354559u - (v15 + 2684354559u) % v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800166a8  mov     [rsp-8+arg_10], rbx
0x1800166ad  push    rbp
0x1800166ae  push    rsi
0x1800166af  push    rdi
0x1800166b0  push    r12
0x1800166b2  push    r13
0x1800166b4  push    r14
0x1800166b6  push    r15
0x1800166b8  lea     rbp, [rsp-27h]
0x1800166bd  sub     rsp, 0C0h
0x1800166c4  mov     rax, cs:__security_cookie
0x1800166cb  xor     rax, rsp
0x1800166ce  mov     [rbp+57h+var_40], rax
0x1800166d2  mov     r15, rdx
0x1800166d5  mov     rdi, rcx
0x1800166d8  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x1800166dd  xor     r12d, r12d
0x1800166e0  test    eax, eax
0x1800166e2  js      loc_180016B81
0x1800166e8  mov     rcx, [rdi+68h]; hkey
0x1800166ec  lea     rax, [rbp+57h+var_90]
0x1800166f0  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800166f5  lea     r13d, [r12+40h]
0x1800166fa  lea     rax, [rbp+57h+var_50]
0x1800166fe  mov     [rbp+57h+var_50], r12
0x180016702  mov     [rsp+0F0h+pvData], rax; pvData
0x180016707  lea     rsi, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001670e  lea     r14d, [r12+8]
0x180016713  mov     [rsp+0F0h+pdwType], r12; pdwType
0x180016718  mov     r9d, r13d; dwFlags
0x18001671b  mov     [rbp+57h+var_90], r14d
0x18001671f  lea     r8, aBasehardreserv; "BaseHardReserveSize"
0x180016726  mov     rdx, rsi; lpSubKey
0x180016729  call    cs:__imp_RegGetValueW
0x18001672f  mov     ebx, eax
0x180016731  test    eax, eax
0x180016733  jz      short loc_180016785
0x180016735  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001673c  mov     [rbp+57h+var_A0], 87Bh
0x180016744  mov     [rbp+57h+var_B0], rax
0x180016748  lea     rax, aUpdatereservem_38; "UpdateReserveManager::GetInitialization"...
0x18001674f  mov     [rbp+57h+var_A8], rax
0x180016753  lea     rax, aReggetvaluewMS; "::RegGetValueW(m_SoftwareKey, L\"Micros"...
0x18001675a  test    ebx, ebx
0x18001675c  mov     [rbp+57h+var_98], rax
0x180016760  jle     short loc_18001676B
0x180016762  movzx   ebx, bx
0x180016765  or      ebx, 80070000h
0x18001676b  mov     r8d, ebx
0x18001676e  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180016775  lea     rcx, [rbp+57h+var_B0]
0x180016779  call    RtlReportErrorOrigination
0x18001677e  mov     eax, ebx
0x180016780  jmp     loc_180016B81
0x180016785  mov     rcx, [rdi+68h]; hkey
0x180016789  lea     rax, [rbp+57h+var_90]
0x18001678d  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180016792  lea     r8, aBasesoftreserv; "BaseSoftReserveSize"
0x180016799  lea     rax, [rbp+57h+var_48]
0x18001679d  mov     [rbp+57h+var_48], r12
0x1800167a1  mov     [rsp+0F0h+pvData], rax; pvData
0x1800167a6  mov     r9d, r13d; dwFlags
0x1800167a9  mov     rdx, rsi; lpSubKey
0x1800167ac  mov     [rsp+0F0h+pdwType], r12; pdwType
0x1800167b1  mov     [rbp+57h+var_90], r14d
0x1800167b5  call    cs:__imp_RegGetValueW
0x1800167bb  mov     ebx, eax
0x1800167bd  test    eax, eax
0x1800167bf  jz      short loc_1800167EB
0x1800167c1  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800167c8  mov     [rbp+57h+var_A0], 885h
0x1800167d0  mov     [rbp+57h+var_B0], rax
0x1800167d4  lea     rax, aUpdatereservem_38; "UpdateReserveManager::GetInitialization"...
0x1800167db  mov     [rbp+57h+var_A8], rax
0x1800167df  lea     rax, aReggetvaluewMS_1; "::RegGetValueW(m_SoftwareKey, L\"Micros"...
0x1800167e6  jmp     loc_18001675A
0x1800167eb  mov     rcx, [rdi+68h]; hkey
0x1800167ef  lea     rax, [rbp+57h+var_90]
0x1800167f3  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800167f8  lea     r8, aHardreserveadj; "HardReserveAdjustment"
0x1800167ff  lea     rax, [rbp+57h+var_60]
0x180016803  mov     [rbp+57h+var_60], r12
0x180016807  mov     [rsp+0F0h+pvData], rax; pvData
0x18001680c  mov     r9d, r13d; dwFlags
0x18001680f  mov     rdx, rsi; lpSubKey
0x180016812  mov     [rsp+0F0h+pdwType], r12; pdwType
0x180016817  mov     [rbp+57h+var_90], r14d
0x18001681b  call    cs:__imp_RegGetValueW
0x180016821  mov     ebx, eax
0x180016823  cmp     eax, 2
0x180016826  jnz     short loc_18001689B
0x180016828  mov     [rbp+57h+var_60], r12
0x18001682c  lea     rax, [rbp+57h+TotalNumberOfClusters]
0x180016830  mov     [rbp+57h+SectorsPerCluster], r12d
0x180016834  lea     rcx, [rdi+88h]; lpRootPathName
0x18001683b  mov     [rsp+0F0h+pdwType], rax; lpTotalNumberOfClusters
0x180016840  lea     r9, [rbp+57h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x180016844  mov     [rbp+57h+BytesPerSector], r12d
0x180016848  lea     r8, [rbp+57h+BytesPerSector]; lpBytesPerSector
0x18001684c  mov     [rbp+57h+NumberOfFreeClusters], r12d
0x180016850  lea     rdx, [rbp+57h+SectorsPerCluster]; lpSectorsPerCluster
0x180016854  mov     [rbp+57h+TotalNumberOfClusters], r12d
0x180016858  call    cs:__imp_GetDiskFreeSpaceW
0x18001685e  test    eax, eax
0x180016860  jnz     short loc_1800168DB
0x180016862  call    cs:__imp_GetLastError
0x180016868  test    eax, eax
0x18001686a  jnz     short loc_1800168C9
0x18001686c  mov     ebx, 36FDh
0x180016871  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180016878  mov     [rbp+57h+var_A0], 89Bh
0x180016880  mov     [rbp+57h+var_B0], rax
0x180016884  lea     rax, aUpdatereservem_38; "UpdateReserveManager::GetInitialization"...
0x18001688b  mov     [rbp+57h+var_A8], rax
0x18001688f  lea     rax, aEnsureboolGetd_2; "EnsureBOOL(::GetDiskFreeSpaceW(m_Window"...
0x180016896  jmp     loc_18001675A
0x18001689b  test    ebx, ebx
0x18001689d  jz      short loc_18001682C
0x18001689f  mov     [rbp+57h+var_A0], 897h
0x1800168a7  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800168ae  mov     [rbp+57h+var_B0], rax
0x1800168b2  lea     rax, aUpdatereservem_38; "UpdateReserveManager::GetInitialization"...
0x1800168b9  mov     [rbp+57h+var_A8], rax
0x1800168bd  lea     rax, aRetvalue; "RetValue"
0x1800168c4  jmp     loc_18001675C
0x1800168c9  call    cs:__imp_GetLastError
0x1800168cf  mov     ebx, eax
0x1800168d1  test    eax, eax
0x1800168d3  jz      loc_180016BA8
0x1800168d9  jmp     short loc_180016871
0x1800168db  mov     r14, [rbp+57h+var_60]
0x1800168df  add     r14, [rbp+57h+var_50]
0x1800168e3  cmp     r14, [rbp+57h+var_50]
0x1800168e7  jnb     short loc_180016913
0x1800168e9  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800168f0  mov     [rbp+57h+var_A0], 8A5h
0x1800168f8  mov     [rbp+57h+var_B0], rax
0x1800168fc  lea     rax, aUpdatereservem_38; "UpdateReserveManager::GetInitialization"...
0x180016903  mov     [rbp+57h+var_A8], rax
0x180016907  lea     rax, aUlonglongaddBa; "::ULongLongAdd(BaseHardReserveSize, Har"...
0x18001690e  jmp     loc_180016B62
0x180016913  mov     esi, [rbp+57h+BytesPerSector]
0x180016916  lea     rax, [rbp+57h+var_68]
0x18001691a  mov     rcx, [rdi+68h]; hkey
0x18001691e  lea     r8, aPostupgradefre; "PostUpgradeFreeSpace"
0x180016925  imul    esi, [rbp+57h+SectorsPerCluster]
0x180016929  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180016930  mov     r13, [rbp+57h+var_48]
0x180016934  mov     r9d, 10h; dwFlags
0x18001693a  mov     [rsp+0F0h+pcbData], rax; pcbData
0x18001693f  lea     rax, [rbp+57h+var_80]
0x180016943  mov     [rsp+0F0h+pvData], rax; pvData
0x180016948  mov     [rsp+0F0h+pdwType], r12; pdwType
0x18001694d  mov     [rbp+57h+var_80], r12d
0x180016951  mov     [rbp+57h+var_68], 4
0x180016958  call    cs:__imp_RegGetValueW
0x18001695e  mov     ebx, eax
0x180016960  cmp     eax, 2
0x180016963  jnz     short loc_18001696D
0x180016965  lea     eax, [rbx+62h]
0x180016968  mov     [rbp+57h+var_80], eax
0x18001696b  jmp     short loc_180016981
0x18001696d  test    ebx, ebx
0x18001696f  jz      short loc_18001697E
0x180016971  mov     [rbp+57h+var_A0], 8D7h
0x180016979  jmp     loc_1800168A7
0x18001697e  mov     eax, [rbp+57h+var_80]
0x180016981  mov     ecx, eax
0x180016983  mov     eax, 100000h
0x180016988  mul     rcx
0x18001698b  mov     [rbp+57h+var_58], r12
0x18001698f  test    rdx, rdx
0x180016992  jnz     loc_180016B3D
0x180016998  lea     rcx, [rsi-1]
0x18001699c  mov     [rbp+57h+var_88], 0
0x1800169a4  add     rcx, rax
0x1800169a7  mov     [rbp+57h+var_90], 8
0x1800169ae  mov     rax, rcx
0x1800169b1  lea     r8, aUserfreespacem; "UserFreeSpaceMarker"
0x1800169b8  div     rsi
0x1800169bb  lea     rax, [rbp+57h+var_90]
0x1800169bf  mov     r9d, 40h ; '@'; dwFlags
0x1800169c5  sub     rcx, rdx
0x1800169c8  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800169cd  lea     rax, [rbp+57h+var_88]
0x1800169d1  cmovnz  r12, rcx
0x1800169d5  mov     [rsp+0F0h+pvData], rax; pvData
0x1800169da  mov     rcx, [rdi+68h]; hkey
0x1800169de  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x1800169e5  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800169ee  call    cs:__imp_RegGetValueW
0x1800169f4  mov     ebx, eax
0x1800169f6  cmp     eax, 2
0x1800169f9  jnz     short loc_1800169FF
0x1800169fb  xor     eax, eax
0x1800169fd  jmp     short loc_180016A14
0x1800169ff  test    ebx, ebx
0x180016a01  jz      short loc_180016A10
0x180016a03  mov     [rbp+57h+var_A0], 8F7h
0x180016a0b  jmp     loc_1800168A7
0x180016a10  mov     rax, [rbp+57h+var_88]
0x180016a14  xor     edx, edx
0x180016a16  mov     [rbp+57h+var_7C], 0
0x180016a1d  lea     rcx, [rsi-1]
0x180016a21  mov     [rbp+57h+var_90], 4
0x180016a28  add     rcx, rax
0x180016a2b  lea     r8, aUserfreespaceb; "UserFreeSpaceBuffer"
0x180016a32  mov     rax, rcx
0x180016a35  mov     r9d, 10h; dwFlags
0x180016a3b  div     rsi
0x180016a3e  lea     rax, [rbp+57h+var_90]
0x180016a42  sub     rcx, rdx
0x180016a45  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180016a4a  lea     rax, [rbp+57h+var_7C]
0x180016a4e  mov     [rbp+57h+var_88], rcx
0x180016a52  mov     rcx, [rdi+68h]; hkey
0x180016a56  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180016a5d  mov     [rsp+0F0h+pvData], rax; pvData
0x180016a62  mov     [rsp+0F0h+pdwType], 0; pdwType
0x180016a6b  call    cs:__imp_RegGetValueW
0x180016a71  mov     ebx, eax
0x180016a73  cmp     eax, 2
0x180016a76  jnz     short loc_180016A82
0x180016a78  mov     eax, 12C00000h
0x180016a7d  mov     [rbp+57h+var_7C], eax
0x180016a80  jmp     short loc_180016A96
0x180016a82  test    ebx, ebx
0x180016a84  jz      short loc_180016A93
0x180016a86  mov     [rbp+57h+var_A0], 90Bh
0x180016a8e  jmp     loc_1800168A7
0x180016a93  mov     eax, [rbp+57h+var_7C]
0x180016a96  mov     ecx, eax
0x180016a98  mov     rax, [rbp+57h+var_88]
0x180016a9c  cmp     rax, rcx
0x180016a9f  jnb     short loc_180016AAB
0x180016aa1  mov     [rbp+57h+var_88], 0
0x180016aa9  jmp     short loc_180016AB2
0x180016aab  sub     rax, rcx
0x180016aae  mov     [rbp+57h+var_88], rax
0x180016ab2  lea     rdx, [rbp+57h+var_58]; unsigned __int64 *
0x180016ab6  mov     [rbp+57h+var_58], 0
0x180016abe  mov     rcx, rdi; this
0x180016ac1  call    ?CalculateTotalPendingScratchIncrease@UpdateReserveManager@@AEAAJPEA_K@Z; UpdateReserveManager::CalculateTotalPendingScratchIncrease(unsigned __int64 *)
0x180016ac6  test    eax, eax
0x180016ac8  js      loc_180016B81
0x180016ace  mov     r9, [rbp+57h+var_58]
0x180016ad2  lea     rcx, [r14-1]
0x180016ad6  xor     edx, edx
0x180016ad8  mov     [r15], rsi
0x180016adb  dec     r9
0x180016ade  mov     [r15+8], r12
0x180016ae2  add     r9, rsi
0x180016ae5  lea     r8, [r13-1]
0x180016ae9  mov     rax, r9
0x180016aec  add     rcx, rsi
0x180016aef  div     rsi
0x180016af2  mov     rax, [rbp+57h+var_88]
0x180016af6  add     r8, rsi
0x180016af9  sub     r9, rdx
0x180016afc  mov     [r15+10h], rax
0x180016b00  xor     edx, edx
0x180016b02  mov     [r15+30h], r9
0x180016b06  mov     rax, rcx
0x180016b09  div     rsi
0x180016b0c  mov     rax, r8
0x180016b0f  sub     rcx, rdx
0x180016b12  xor     edx, edx
0x180016b14  div     rsi
0x180016b17  mov     [r15+18h], rcx
0x180016b1b  mov     ecx, 9FFFFFFFh
0x180016b20  sub     r8, rdx
0x180016b23  add     rcx, rsi
0x180016b26  xor     edx, edx
0x180016b28  mov     [r15+20h], r8
0x180016b2c  mov     rax, rcx
0x180016b2f  div     rsi
0x180016b32  sub     rcx, rdx
0x180016b35  mov     [r15+28h], rcx
0x180016b39  xor     eax, eax
0x180016b3b  jmp     short loc_180016B81
0x180016b3d  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180016b44  mov     [rbp+57h+var_A0], 8DCh
0x180016b4c  mov     [rbp+57h+var_B0], rax
0x180016b50  lea     rax, aUpdatereservem_38; "UpdateReserveManager::GetInitialization"...
0x180016b57  mov     [rbp+57h+var_A8], rax
0x180016b5b  lea     rax, aUlonglongmultP; "::ULongLongMult(PostUpgradeFreeSpaceVal"...
0x180016b62  mov     r8d, 80070216h
0x180016b68  mov     [rbp+57h+var_98], rax
0x180016b6c  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180016b73  lea     rcx, [rbp+57h+var_B0]
0x180016b77  call    RtlReportErrorOrigination
0x180016b7c  mov     eax, 80070216h
0x180016b81  mov     rcx, [rbp+57h+var_40]
0x180016b85  xor     rcx, rsp; StackCookie
0x180016b88  call    __security_check_cookie
0x180016b8d  mov     rbx, [rsp+0F0h+arg_10]
0x180016b95  add     rsp, 0C0h
0x180016b9c  pop     r15
0x180016b9e  pop     r14
0x180016ba0  pop     r13
  ... truncated ...
```
