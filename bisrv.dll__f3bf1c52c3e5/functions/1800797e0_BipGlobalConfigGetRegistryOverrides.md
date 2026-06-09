# BipGlobalConfigGetRegistryOverrides

- ea: `0x1800797e0`
- end: `0x180079f41`
- name: `BipGlobalConfigGetRegistryOverrides`
- size: `1889`
- prototype: `__int64 __fastcall(_OWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800747d0`

## callees

- `0x18004e4f0`
- `0x1800797e0`
- `0x1800946a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800798d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007994b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800799bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079a11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079a5c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079ab5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079b01`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079b4d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079b9e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079bed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079c39`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079c8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079cd3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079d13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079d55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079d9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079deb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079e2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079e6f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800798d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007994b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800799bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079a11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079a5c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079ab5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079b01`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079b4d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079b9e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079bed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079c39`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079c8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079cd3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079d13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079d55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079d9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079deb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079e2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079e6f`

## string_xrefs

- `0x180079891`: `SYSTEM\CurrentControlSet\Services\BrokerInfrastructure\Parameters`
- `0x180079909`: `SYSTEM\CurrentControlSet\Services\BrokerInfrastructure\Parameters`
- `0x180079987`: `SYSTEM\CurrentControlSet\Services\BrokerInfrastructure\Parameters`
- `0x1800799ff`: `SYSTEM\CurrentControlSet\Services\BrokerInfrastructure\Parameters`
- `0x180079a4d`: `SYSTEM\CurrentControlSet\Services\BrokerInfrastructure\Parameters`
- `0x180079a8f`: `SYSTEM\CurrentControlSet\Services\BrokerInfrastructure\Parameters`
- `0x180079887`: `UnlockBrokerInfrastructure`
- `0x180079bce`: `StandbyBudgetCommonPortionPercent`
- `0x180079cdc`: `FailingTaskPenaltyTimeMinutes`
- `0x180079cb4`: `MaxConsecutiveTaskFailures`
- `0x180079dcc`: `GlobalCoalesceMaxAdditionalTasksPerWake`
- `0x180079e34`: `WaitForNewSessionComplete`

## pseudocode

```c
__int64 __fastcall BipGlobalConfigGetRegistryOverrides(_OWORD *a1)
{
  _OWORD *v1; // rdi
  _OWORD *v2; // rax
  int *v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  int v17; // eax
  int v18; // esi
  int v19; // r15d
  int v20; // r14d
  int v21; // r14d
  unsigned int v22; // r14d
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // eax
  LSTATUS ValueW; // eax
  unsigned int v30; // ecx
  LSTATUS v31; // eax
  unsigned int v32; // ecx
  LSTATUS v33; // eax
  unsigned int v34; // edx
  __int64 v35; // rax
  int *v36; // rax
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int64 result; // rax
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-BCh] BYREF
  int v50; // [rsp+50h] [rbp-B0h] BYREF
  int v51; // [rsp+54h] [rbp-ACh]
  int v52; // [rsp+58h] [rbp-A8h]
  unsigned int v53; // [rsp+5Ch] [rbp-A4h]
  unsigned int v54; // [rsp+60h] [rbp-A0h]
  unsigned int v55; // [rsp+64h] [rbp-9Ch]
  unsigned int v56; // [rsp+68h] [rbp-98h]
  unsigned int v57; // [rsp+6Ch] [rbp-94h]
  int v58; // [rsp+70h] [rbp-90h]
  unsigned int v59; // [rsp+74h] [rbp-8Ch]
  unsigned int v60; // [rsp+78h] [rbp-88h]
  unsigned int v61; // [rsp+7Ch] [rbp-84h]
  unsigned int v62; // [rsp+80h] [rbp-80h]
  int v63; // [rsp+84h] [rbp-7Ch]
  int v64; // [rsp+88h] [rbp-78h]
  unsigned int v65; // [rsp+8Ch] [rbp-74h]
  unsigned int v66; // [rsp+90h] [rbp-70h]
  unsigned __int16 v67[262]; // [rsp+94h] [rbp-6Ch] BYREF

  v1 = a1;
  v2 = a1;
  pvData = 0;
  v3 = &v50;
  v4 = 4;
  v5 = 4;
  do
  {
    v6 = v2[1];
    *(_OWORD *)v3 = *v2;
    v7 = v2[2];
    *((_OWORD *)v3 + 1) = v6;
    v8 = v2[3];
    *((_OWORD *)v3 + 2) = v7;
    v9 = v2[4];
    *((_OWORD *)v3 + 3) = v8;
    v10 = v2[5];
    *((_OWORD *)v3 + 4) = v9;
    v11 = v2[6];
    *((_OWORD *)v3 + 5) = v10;
    v12 = v2[7];
    v2 += 8;
    *((_OWORD *)v3 + 6) = v11;
    *((_OWORD *)v3 + 7) = v12;
    v3 += 32;
    --v5;
  }
  while ( v5 );
  v13 = *v2;
  pcbData[0] = 4;
  v14 = v2[1];
  *(_OWORD *)v3 = v13;
  v15 = v2[2];
  *((_OWORD *)v3 + 1) = v14;
  v16 = v2[3];
  v17 = *((_DWORD *)v2 + 16);
  *((_OWORD *)v3 + 2) = v15;
  *((_OWORD *)v3 + 3) = v16;
  v3[16] = v17;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
         L"UnlockBrokerInfrastructure",
         0x18u,
         0,
         &pvData,
         pcbData)
    || !pvData )
  {
    v18 = v50;
  }
  else
  {
    v18 = v50 | 1;
    v50 |= 1u;
  }
  pcbData[0] = 4;
  v19 = v18 & 1;
  v20 = v19 != 0 ? 60000 : 300000;
  v51 = v20;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"SessionStateTimeout",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    if ( pvData - 5000 <= 0x48057 )
      v20 = pvData;
    v51 = v20;
  }
  pcbData[0] = 4;
  v21 = v19 != 0 ? 10000 : 5000;
  v52 = v21;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"AlternateCancellationTimeout",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    if ( pvData - 1000 <= 0x36B0 )
      v21 = pvData;
    v52 = v21;
  }
  pcbData[0] = 4;
  v22 = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"ActivityCheckTimerPeriodMs",
          0x18u,
          0,
          &pvData,
          pcbData)
    && pvData
    && pvData < v53 )
  {
    v22 = pvData;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"ActivityCheckTimerLowPowerPeriodMs",
          0x18u,
          0,
          &pvData,
          pcbData)
    && v22
    && pvData
    && pvData < v22 )
  {
    v54 = pvData;
    v53 = v22;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"StandbyBudgetMinAppCount",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    v23 = v55;
    if ( pvData - 4 <= 0x1A )
      v23 = pvData;
    v55 = v23;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"StandbyBudgetHourPeriodsForLimit",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    v24 = v56;
    if ( pvData - 1 <= 0x17 )
      v24 = pvData;
    v56 = v24;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"StandbyBudgetRuntimeMsLimitPerHour",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    v25 = v57;
    if ( pvData - 2000 <= 0x1B6F70 )
      v25 = pvData;
    v57 = v25;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"StandbyBudgetWakeLimitPerHour",
          0x18u,
          0,
          &pvData,
          pcbData)
    && pvData - 1 <= 0xC7 )
  {
    v58 = 1000 * pvData;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"StandbyBudgetCommonPortionPercent",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    v26 = v59;
    if ( pvData - 10 <= 0x5A )
      v26 = pvData;
    v59 = v26;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"StandbyBudgetRefillPeriodMs",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    v27 = v60;
    if ( pvData - 60000 <= 0x360420 )
      v27 = pvData;
    v60 = v27;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"StandbyBudgetTrendWeightPercent",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    v28 = v61;
    if ( pvData <= 0x64 )
      v28 = pvData;
    v61 = v28;
  }
  pcbData[0] = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
             L"MaxConsecutiveTaskFailures",
             0x18u,
             0,
             &pvData,
             pcbData);
  v30 = v62;
  pcbData[0] = 4;
  if ( !ValueW )
    v30 = pvData;
  v62 = v30;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"FailingTaskPenaltyTimeMinutes",
          0x18u,
          0,
          &pvData,
          pcbData) )
    v63 = 60000 * pvData;
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"DisableTriggerCoalescing",
          0x18u,
          0,
          &pvData,
          pcbData)
    && pvData )
  {
    v18 |= 2u;
    v50 = v18;
  }
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"DefaultTriggerCoalescingTime",
          0x18u,
          0,
          &pvData,
          pcbData)
    && pvData - 60000 <= 0x360420 )
  {
    v64 = -600000000 * pvData;
  }
  pcbData[0] = 4;
  v31 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"GlobalCoalesceMaxAdditionalTasksPerWake",
          0x18u,
          0,
          &pvData,
          pcbData);
  v32 = v65;
  pcbData[0] = 4;
  if ( !v31 )
    v32 = pvData;
  v65 = v32;
  v33 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
          L"GlobalCoalesceMaxEarlyFireWindowMs",
          0x18u,
          0,
          &pvData,
          pcbData);
  v34 = v66;
  pcbData[0] = 4;
  if ( !v33 )
    v34 = pvData;
  v66 = v34;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\BackgroundModel",
          L"WaitForNewSessionComplete",
          0x18u,
          0,
          &pvData,
          pcbData)
    && pvData == 1 )
  {
    v50 = v18 | 4;
  }
  v35 = -1;
  do
    ++v35;
  while ( v67[v35] );
  if ( !v35 )
    BipStorageGetRootFolder(v67);
  v36 = &v50;
  do
  {
    v37 = *((_OWORD *)v36 + 1);
    *v1 = *(_OWORD *)v36;
    v38 = *((_OWORD *)v36 + 2);
    v1[1] = v37;
    v39 = *((_OWORD *)v36 + 3);
    v1[2] = v38;
    v40 = *((_OWORD *)v36 + 4);
    v1[3] = v39;
    v41 = *((_OWORD *)v36 + 5);
    v1[4] = v40;
    v42 = *((_OWORD *)v36 + 6);
    v1[5] = v41;
    v43 = *((_OWORD *)v36 + 7);
    v36 += 32;
    v1[6] = v42;
    v1[7] = v43;
    v1 += 8;
    --v4;
  }
  while ( v4 );
  v44 = *((_OWORD *)v36 + 1);
  *v1 = *(_OWORD *)v36;
  v45 = *((_OWORD *)v36 + 2);
  v1[1] = v44;
  v46 = *((_OWORD *)v36 + 3);
  result = (unsigned int)v36[16];
  v1[2] = v45;
  v1[3] = v46;
  *((_DWORD *)v1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x1800797e0  push    rbp
0x1800797e2  push    rbx
0x1800797e3  push    rsi
0x1800797e4  push    rdi
0x1800797e5  push    r12
0x1800797e7  push    r13
0x1800797e9  push    r14
0x1800797eb  push    r15
0x1800797ed  lea     rbp, [rsp-1B8h]
0x1800797f5  sub     rsp, 2B8h
0x1800797fc  mov     rax, cs:__security_cookie
0x180079803  xor     rax, rsp
0x180079806  mov     [rbp+1F0h+var_50], rax
0x18007980d  xor     r12d, r12d
0x180079810  mov     rdi, rcx
0x180079813  mov     rax, rcx
0x180079816  mov     [rsp+2F0h+var_2B0], r12d
0x18007981b  lea     rcx, [rsp+2F0h+var_2A0]
0x180079820  lea     ebx, [r12+4]
0x180079825  mov     edx, ebx
0x180079827  lea     r8d, [rbx+7Ch]
0x18007982b  movups  xmm0, xmmword ptr [rax]
0x18007982e  movups  xmm1, xmmword ptr [rax+10h]
0x180079832  movups  xmmword ptr [rcx], xmm0
0x180079835  movups  xmm0, xmmword ptr [rax+20h]
0x180079839  movups  xmmword ptr [rcx+10h], xmm1
0x18007983d  movups  xmm1, xmmword ptr [rax+30h]
0x180079841  movups  xmmword ptr [rcx+20h], xmm0
0x180079845  movups  xmm0, xmmword ptr [rax+40h]
0x180079849  movups  xmmword ptr [rcx+30h], xmm1
0x18007984d  movups  xmm1, xmmword ptr [rax+50h]
0x180079851  movups  xmmword ptr [rcx+40h], xmm0
0x180079855  movups  xmm0, xmmword ptr [rax+60h]
0x180079859  movups  xmmword ptr [rcx+50h], xmm1
0x18007985d  movups  xmm1, xmmword ptr [rax+70h]
0x180079861  add     rax, r8
0x180079864  movups  xmmword ptr [rcx+60h], xmm0
0x180079868  movups  xmmword ptr [rcx+70h], xmm1
0x18007986c  add     rcx, r8
0x18007986f  sub     rdx, 1
0x180079873  jnz     short loc_18007982B
0x180079875  movups  xmm0, xmmword ptr [rax]
0x180079878  lea     r13d, [rdx+18h]
0x18007987c  mov     [rsp+2F0h+var_2AC], ebx
0x180079880  movups  xmm1, xmmword ptr [rax+10h]
0x180079884  mov     r9d, r13d; dwFlags
0x180079887  lea     r8, aUnlockbrokerin; "UnlockBrokerInfrastructure"
0x18007988e  movups  xmmword ptr [rcx], xmm0
0x180079891  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Br"...
0x180079898  movups  xmm0, xmmword ptr [rax+20h]
0x18007989c  movups  xmmword ptr [rcx+10h], xmm1
0x1800798a0  movups  xmm1, xmmword ptr [rax+30h]
0x1800798a4  mov     eax, [rax+40h]
0x1800798a7  movups  xmmword ptr [rcx+20h], xmm0
0x1800798ab  movups  xmmword ptr [rcx+30h], xmm1
0x1800798af  mov     [rcx+40h], eax
0x1800798b2  lea     rax, [rsp+2F0h+var_2AC]
0x1800798b7  mov     [rsp+2F0h+pcbData], rax; pcbData
0x1800798bc  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800798c3  lea     rax, [rsp+2F0h+var_2B0]
0x1800798c8  mov     [rsp+2F0h+pvData], rax; pvData
0x1800798cd  mov     [rsp+2F0h+pdwType], r12; pdwType
0x1800798d2  call    cs:__imp_RegGetValueW
0x1800798d8  test    eax, eax
0x1800798da  jnz     short loc_1800798F0
0x1800798dc  cmp     [rsp+2F0h+var_2B0], r12d
0x1800798e1  jz      short loc_1800798F0
0x1800798e3  mov     esi, [rsp+2F0h+var_2A0]
0x1800798e7  or      esi, 1
0x1800798ea  mov     [rsp+2F0h+var_2A0], esi
0x1800798ee  jmp     short loc_1800798F4
0x1800798f0  mov     esi, [rsp+2F0h+var_2A0]
0x1800798f4  mov     r15d, esi
0x1800798f7  mov     [rsp+2F0h+var_2AC], ebx
0x1800798fb  and     r15d, 1
0x1800798ff  lea     r8, aSessionstateti; "SessionStateTimeout"
0x180079906  mov     eax, r15d
0x180079909  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Br"...
0x180079910  neg     eax
0x180079912  mov     r9d, r13d; dwFlags
0x180079915  lea     rax, [rsp+2F0h+var_2AC]
0x18007991a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180079921  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079926  sbb     r14d, r14d
0x180079929  lea     rax, [rsp+2F0h+var_2B0]
0x18007992e  and     r14d, 0FFFC5680h
0x180079935  mov     [rsp+2F0h+pvData], rax; pvData
0x18007993a  add     r14d, 493E0h
0x180079941  mov     [rsp+2F0h+var_29C], r14d
0x180079946  mov     [rsp+2F0h+pdwType], r12; pdwType
0x18007994b  call    cs:__imp_RegGetValueW
0x180079951  test    eax, eax
0x180079953  jnz     short loc_18007996D
0x180079955  mov     ecx, [rsp+2F0h+var_2B0]
0x180079959  lea     eax, [rcx-1388h]
0x18007995f  cmp     eax, 48057h
0x180079964  cmovbe  r14d, ecx
0x180079968  mov     [rsp+2F0h+var_29C], r14d
0x18007996d  mov     eax, 1388h
0x180079972  mov     [rsp+2F0h+var_2AC], ebx
0x180079976  neg     r15d
0x180079979  lea     r8, aAlternatecance; "AlternateCancellationTimeout"
0x180079980  mov     r15, 0FFFFFFFF80000002h
0x180079987  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Br"...
0x18007998e  sbb     r14d, r14d
0x180079991  mov     r9d, r13d; dwFlags
0x180079994  and     r14d, eax
0x180079997  mov     rcx, r15; hkey
0x18007999a  add     r14d, eax
0x18007999d  lea     rax, [rsp+2F0h+var_2AC]
0x1800799a2  mov     [rsp+2F0h+pcbData], rax; pcbData
0x1800799a7  lea     rax, [rsp+2F0h+var_2B0]
0x1800799ac  mov     [rsp+2F0h+pvData], rax; pvData
0x1800799b1  mov     [rsp+2F0h+pdwType], r12; pdwType
0x1800799b6  mov     [rsp+2F0h+var_298], r14d
0x1800799bb  call    cs:__imp_RegGetValueW
0x1800799c1  test    eax, eax
0x1800799c3  jnz     short loc_1800799DD
0x1800799c5  mov     ecx, [rsp+2F0h+var_2B0]
0x1800799c9  lea     eax, [rcx-3E8h]
0x1800799cf  cmp     eax, 36B0h
0x1800799d4  cmovbe  r14d, ecx
0x1800799d8  mov     [rsp+2F0h+var_298], r14d
0x1800799dd  lea     rax, [rsp+2F0h+var_2AC]
0x1800799e2  mov     [rsp+2F0h+var_2AC], ebx
0x1800799e6  mov     [rsp+2F0h+pcbData], rax; pcbData
0x1800799eb  lea     r8, aActivitycheckt_0; "ActivityCheckTimerPeriodMs"
0x1800799f2  lea     rax, [rsp+2F0h+var_2B0]
0x1800799f7  mov     r9d, r13d; dwFlags
0x1800799fa  mov     [rsp+2F0h+pvData], rax; pvData
0x1800799ff  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Br"...
0x180079a06  mov     rcx, r15; hkey
0x180079a09  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079a0e  mov     r14d, r12d
0x180079a11  call    cs:__imp_RegGetValueW
0x180079a17  test    eax, eax
0x180079a19  jnz     short loc_180079A2B
0x180079a1b  mov     eax, [rsp+2F0h+var_2B0]
0x180079a1f  test    eax, eax
0x180079a21  jz      short loc_180079A2B
0x180079a23  cmp     eax, [rsp+2F0h+var_294]
0x180079a27  cmovb   r14d, eax
0x180079a2b  lea     rax, [rsp+2F0h+var_2AC]
0x180079a30  mov     [rsp+2F0h+var_2AC], ebx
0x180079a34  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079a39  lea     r8, aActivitycheckt; "ActivityCheckTimerLowPowerPeriodMs"
0x180079a40  lea     rax, [rsp+2F0h+var_2B0]
0x180079a45  mov     r9d, r13d; dwFlags
0x180079a48  mov     [rsp+2F0h+pvData], rax; pvData
0x180079a4d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Br"...
0x180079a54  mov     rcx, r15; hkey
0x180079a57  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079a5c  call    cs:__imp_RegGetValueW
0x180079a62  test    eax, eax
0x180079a64  jnz     short loc_180079A81
0x180079a66  test    r14d, r14d
0x180079a69  jz      short loc_180079A81
0x180079a6b  mov     eax, [rsp+2F0h+var_2B0]
0x180079a6f  test    eax, eax
0x180079a71  jz      short loc_180079A81
0x180079a73  cmp     eax, r14d
0x180079a76  jnb     short loc_180079A81
0x180079a78  mov     [rsp+2F0h+var_290], eax
0x180079a7c  mov     [rsp+2F0h+var_294], r14d
0x180079a81  lea     rax, [rsp+2F0h+var_2AC]
0x180079a86  mov     [rsp+2F0h+var_2AC], ebx
0x180079a8a  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079a8f  lea     r14, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Br"...
0x180079a96  lea     rax, [rsp+2F0h+var_2B0]
0x180079a9b  mov     r9d, r13d; dwFlags
0x180079a9e  mov     [rsp+2F0h+pvData], rax; pvData
0x180079aa3  lea     r8, aStandbybudgetm; "StandbyBudgetMinAppCount"
0x180079aaa  mov     rdx, r14; lpSubKey
0x180079aad  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079ab2  mov     rcx, r15; hkey
0x180079ab5  call    cs:__imp_RegGetValueW
0x180079abb  test    eax, eax
0x180079abd  jnz     short loc_180079AD4
0x180079abf  mov     edx, [rsp+2F0h+var_2B0]
0x180079ac3  mov     ecx, [rsp+2F0h+var_28C]
0x180079ac7  lea     eax, [rdx-4]
0x180079aca  cmp     eax, 1Ah
0x180079acd  cmovbe  ecx, edx
0x180079ad0  mov     [rsp+2F0h+var_28C], ecx
0x180079ad4  lea     rax, [rsp+2F0h+var_2AC]
0x180079ad9  mov     [rsp+2F0h+var_2AC], ebx
0x180079add  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079ae2  lea     r8, aStandbybudgeth; "StandbyBudgetHourPeriodsForLimit"
0x180079ae9  lea     rax, [rsp+2F0h+var_2B0]
0x180079aee  mov     r9d, r13d; dwFlags
0x180079af1  mov     [rsp+2F0h+pvData], rax; pvData
0x180079af6  mov     rdx, r14; lpSubKey
0x180079af9  mov     rcx, r15; hkey
0x180079afc  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079b01  call    cs:__imp_RegGetValueW
0x180079b07  test    eax, eax
0x180079b09  jnz     short loc_180079B20
0x180079b0b  mov     edx, [rsp+2F0h+var_2B0]
0x180079b0f  mov     ecx, [rsp+2F0h+var_288]
0x180079b13  lea     eax, [rdx-1]
0x180079b16  cmp     eax, 17h
0x180079b19  cmovbe  ecx, edx
0x180079b1c  mov     [rsp+2F0h+var_288], ecx
0x180079b20  lea     rax, [rsp+2F0h+var_2AC]
0x180079b25  mov     [rsp+2F0h+var_2AC], ebx
0x180079b29  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079b2e  lea     r8, aStandbybudgetr_0; "StandbyBudgetRuntimeMsLimitPerHour"
0x180079b35  lea     rax, [rsp+2F0h+var_2B0]
0x180079b3a  mov     r9d, r13d; dwFlags
0x180079b3d  mov     [rsp+2F0h+pvData], rax; pvData
0x180079b42  mov     rdx, r14; lpSubKey
0x180079b45  mov     rcx, r15; hkey
0x180079b48  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079b4d  call    cs:__imp_RegGetValueW
0x180079b53  test    eax, eax
0x180079b55  jnz     short loc_180079B71
0x180079b57  mov     edx, [rsp+2F0h+var_2B0]
0x180079b5b  mov     ecx, [rsp+2F0h+var_284]
0x180079b5f  lea     eax, [rdx-7D0h]
0x180079b65  cmp     eax, 1B6F70h
0x180079b6a  cmovbe  ecx, edx
0x180079b6d  mov     [rsp+2F0h+var_284], ecx
0x180079b71  lea     rax, [rsp+2F0h+var_2AC]
0x180079b76  mov     [rsp+2F0h+var_2AC], ebx
0x180079b7a  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079b7f  lea     r8, aStandbybudgetw; "StandbyBudgetWakeLimitPerHour"
0x180079b86  lea     rax, [rsp+2F0h+var_2B0]
0x180079b8b  mov     r9d, r13d; dwFlags
0x180079b8e  mov     [rsp+2F0h+pvData], rax; pvData
0x180079b93  mov     rdx, r14; lpSubKey
0x180079b96  mov     rcx, r15; hkey
0x180079b99  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079b9e  call    cs:__imp_RegGetValueW
0x180079ba4  test    eax, eax
0x180079ba6  jnz     short loc_180079BC0
0x180079ba8  mov     ecx, [rsp+2F0h+var_2B0]
0x180079bac  lea     eax, [rcx-1]
0x180079baf  cmp     eax, 0C7h
0x180079bb4  ja      short loc_180079BC0
0x180079bb6  imul    eax, ecx, 3E8h
0x180079bbc  mov     [rsp+2F0h+var_280], eax
0x180079bc0  lea     rax, [rsp+2F0h+var_2AC]
0x180079bc5  mov     [rsp+2F0h+var_2AC], ebx
0x180079bc9  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079bce  lea     r8, aStandbybudgetc; "StandbyBudgetCommonPortionPercent"
0x180079bd5  lea     rax, [rsp+2F0h+var_2B0]
0x180079bda  mov     r9d, r13d; dwFlags
0x180079bdd  mov     [rsp+2F0h+pvData], rax; pvData
0x180079be2  mov     rdx, r14; lpSubKey
0x180079be5  mov     rcx, r15; hkey
0x180079be8  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079bed  call    cs:__imp_RegGetValueW
0x180079bf3  test    eax, eax
0x180079bf5  jnz     short loc_180079C0C
0x180079bf7  mov     edx, [rsp+2F0h+var_2B0]
0x180079bfb  mov     ecx, [rsp+2F0h+var_27C]
0x180079bff  lea     eax, [rdx-0Ah]
0x180079c02  cmp     eax, 5Ah ; 'Z'
0x180079c05  cmovbe  ecx, edx
0x180079c08  mov     [rsp+2F0h+var_27C], ecx
0x180079c0c  lea     rax, [rsp+2F0h+var_2AC]
0x180079c11  mov     [rsp+2F0h+var_2AC], ebx
0x180079c15  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079c1a  lea     r8, aStandbybudgetr; "StandbyBudgetRefillPeriodMs"
0x180079c21  lea     rax, [rsp+2F0h+var_2B0]
0x180079c26  mov     r9d, r13d; dwFlags
0x180079c29  mov     [rsp+2F0h+pvData], rax; pvData
0x180079c2e  mov     rdx, r14; lpSubKey
0x180079c31  mov     rcx, r15; hkey
0x180079c34  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079c39  call    cs:__imp_RegGetValueW
0x180079c3f  test    eax, eax
0x180079c41  jnz     short loc_180079C5D
0x180079c43  mov     edx, [rsp+2F0h+var_2B0]
0x180079c47  mov     ecx, [rsp+2F0h+var_278]
0x180079c4b  lea     eax, [rdx-0EA60h]
0x180079c51  cmp     eax, 360420h
0x180079c56  cmovbe  ecx, edx
0x180079c59  mov     [rsp+2F0h+var_278], ecx
0x180079c5d  lea     rax, [rsp+2F0h+var_2AC]
0x180079c62  mov     [rsp+2F0h+var_2AC], ebx
0x180079c66  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079c6b  lea     r8, aStandbybudgett; "StandbyBudgetTrendWeightPercent"
0x180079c72  lea     rax, [rsp+2F0h+var_2B0]
0x180079c77  mov     r9d, r13d; dwFlags
0x180079c7a  mov     [rsp+2F0h+pvData], rax; pvData
0x180079c7f  mov     rdx, r14; lpSubKey
0x180079c82  mov     rcx, r15; hkey
0x180079c85  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180079c8a  call    cs:__imp_RegGetValueW
0x180079c90  test    eax, eax
0x180079c92  jnz     short loc_180079CA6
0x180079c94  mov     eax, [rsp+2F0h+var_274]
0x180079c98  cmp     [rsp+2F0h+var_2B0], 64h ; 'd'
0x180079c9d  cmovbe  eax, [rsp+2F0h+var_2B0]
0x180079ca2  mov     [rsp+2F0h+var_274], eax
0x180079ca6  lea     rax, [rsp+2F0h+var_2AC]
0x180079cab  mov     [rsp+2F0h+var_2AC], ebx
0x180079caf  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180079cb4  lea     r8, aMaxconsecutive; "MaxConsecutiveTaskFailures"
  ... truncated ...
```
