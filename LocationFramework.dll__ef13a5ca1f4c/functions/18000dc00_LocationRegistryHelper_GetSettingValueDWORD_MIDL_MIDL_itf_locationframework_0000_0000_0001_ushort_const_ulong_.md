# LocationRegistryHelper::GetSettingValueDWORD(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort const *,ulong,ulong *)

- ea: `0x18000dc00`
- end: `0x18000e944`
- name: `?GetSettingValueDWORD@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEBGKPEAK@Z`
- size: `3396`
- prototype: `__int64 __fastcall(int, __int64, int, _DWORD *)`
- caller_count: `16`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f2a8`
- `0x180020800`
- `0x180020a1c`
- `0x180060e1c`
- `0x180070280`
- `0x180074288`
- `0x180079530`
- `0x180087f08`
- `0x1800dde30`
- `0x1800df118`
- `0x1800df61c`
- `0x1800f9958`
- `0x1800fb0e0`
- `0x18010b7ec`
- `0x18010ff00`
- `0x180124638`

## callees

- `0x18000dc00`
- `0x18000f040`
- `0x18008fa98`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000dd4b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e3ff`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000dd4b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e3ff`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18000e149`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x18000e149`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000dcda`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000dcda`

## string_xrefs

- `0x18000dd3c`: `Components\`
- `0x18000dec9`: `SYSTEM\CurrentControlSet\Services\lfsvc\Components\`
- `0x18000dccc`: `SYSTEM\CurrentControlSet\Services\lfsvc\`
- `0x18000e194`: `LocationWebServiceProxy`
- `0x18000e1a0`: `LocationWebServiceProxy`
- `0x18000e650`: `onecoreuap\drivers\MobilePC\Location\Product\idk\LocationRegistryHelper.h`
- `0x18000e634`: `Path is too long. buff len: %zu. subPath len: %zu`
- `0x18000e644`: `CLocationPersistedRegPathHelper::GetPersistedRegPath`
- `0x18000e200`: `LocationProviderComposite`
- `0x18000e422`: `LocationProviderComposite`
- `0x18000e230`: `LocationMovementDetector`
- `0x18000e452`: `LocationMovementDetector`
- `0x18000e32c`: `LocationBackgroundBroker`
- `0x18000e54e`: `LocationBackgroundBroker`
- `0x18000e3ad`: `GeofenceAppServices`
- `0x18000e5cf`: `GeofenceAppServices`

## pseudocode

```c
__int64 __fastcall LocationRegistryHelper::GetSettingValueDWORD(int a1, __int64 a2, int a3, _DWORD *a4)
{
  __int64 v4; // rsi
  const wchar_t *v8; // rdi
  const wchar_t *v9; // r12
  int PersistedRegistryLocationW; // eax
  __int64 v11; // rbx
  const wchar_t *v12; // r15
  signed int v13; // r14d
  __int64 v14; // rdx
  unsigned __int16 *v15; // rcx
  int v16; // edx
  __int64 v17; // rdx
  unsigned __int16 *v18; // rax
  unsigned int v19; // r8d
  __int64 v20; // rsi
  __int64 v21; // rcx
  _WORD *v22; // r9
  const wchar_t *v23; // r8
  _WORD *v24; // rcx
  int v25; // ebp
  __int64 v26; // rdx
  unsigned __int16 *v27; // rax
  const wchar_t *v28; // rdi
  __int64 v29; // rcx
  const wchar_t *v30; // r8
  _WORD *v31; // r9
  _WORD *v32; // rcx
  int v33; // eax
  __int64 v34; // rdx
  unsigned __int16 *v35; // rax
  __int64 v36; // rcx
  _WORD *v37; // r8
  _WORD *v38; // rcx
  unsigned int v39; // r9d
  unsigned __int16 *v40; // rax
  _WORD *v41; // rdx
  _WORD *v42; // rcx
  __int64 result; // rax
  wil::details *v44; // [rsp+28h] [rbp-680h]
  __int64 v46; // [rsp+58h] [rbp-650h] BYREF
  unsigned __int16 v47[256]; // [rsp+60h] [rbp-648h] BYREF
  unsigned __int16 v48[255]; // [rsp+260h] [rbp-448h] BYREF
  _BYTE v49[2]; // [rsp+45Eh] [rbp-24Ah] BYREF
  unsigned __int16 v50[255]; // [rsp+460h] [rbp-248h] BYREF
  _BYTE v51[2]; // [rsp+65Eh] [rbp-4Ah] BYREF
  __int64 v52; // [rsp+688h] [rbp-20h]
  wil::details::in1diag5 *retaddr; // [rsp+6A8h] [rbp+0h]

  v46 = a2;
  memset_0(v50, 0, sizeof(v50));
  memset_0(v48, 0, sizeof(v48));
  if ( !a4 )
    return 2147500035LL;
  v52 = v4;
  *a4 = a3;
  memset_0(v47, 0, 0x1FEu);
  switch ( a1 )
  {
    case 6:
      v8 = L"ServerTileInformation";
      break;
    case 2:
      v8 = L"LocationSession";
      break;
    case 512:
      v8 = L"General";
      break;
    default:
      if ( a1 > 256 )
      {
        switch ( a1 )
        {
          case 257:
            v8 = L"GeofenceManager";
            goto LABEL_4;
          case 258:
            v8 = L"GeofenceSettings";
            goto LABEL_4;
          case 259:
            v8 = L"GeofenceEventSubscriptions";
            goto LABEL_4;
          case 260:
            v8 = L"GeofenceAppServices";
            goto LABEL_4;
          case 261:
            v8 = L"GeofenceStore";
            goto LABEL_4;
          case 262:
            v8 = L"LocationCivicAddrAdapter";
            goto LABEL_4;
          case 272:
            v8 = L"VisitClientBoundary";
            goto LABEL_4;
          case 273:
            v8 = L"VisitInformation";
            goto LABEL_4;
          case 288:
            v8 = L"LocationAdapterBluetooth";
            goto LABEL_4;
          default:
            return (unsigned int)-2147024809;
        }
      }
      if ( a1 != 256 )
      {
        switch ( a1 )
        {
          case 1:
            v9 = L"LocationProviderHelper";
            v8 = L"LocationProviderHelper";
            goto LABEL_5;
          case 3:
            v8 = L"LocationInformation";
            goto LABEL_4;
          case 4:
            v8 = L"LocationWebServiceProxy";
            goto LABEL_4;
          case 7:
            v8 = L"LocationPermissionManager";
            goto LABEL_4;
          case 8:
            v8 = L"LocationUserHandles";
            goto LABEL_4;
          case 16:
            v8 = L"LocationProviderComposite";
            goto LABEL_4;
          case 17:
            v8 = L"LocationAcquireSingleShotCpe";
            goto LABEL_4;
          case 18:
            v8 = L"LocationAcquireEmulatedTrackingCpe";
            goto LABEL_4;
          case 19:
            v8 = L"LocationAcquireOffloadedTrackingCpe";
            goto LABEL_4;
          case 20:
            v8 = L"LocationMovementDetector";
            goto LABEL_4;
          case 21:
            v8 = L"LocationAcquireOverrideCpe";
            goto LABEL_4;
          case 32:
            v8 = L"LocationProviderWiFi";
            goto LABEL_4;
          case 33:
            v8 = L"LocationAdapterWiFi";
            goto LABEL_4;
          case 34:
            v8 = L"LocationAcquireSingleShotWiFi";
            goto LABEL_4;
          case 48:
            v8 = L"LocationProviderCell";
            goto LABEL_4;
          case 49:
            v8 = L"LocationAdapterCell";
            goto LABEL_4;
          case 50:
            v8 = L"LocationAcquireSingleShotCell";
            goto LABEL_4;
          case 64:
            v8 = L"LocationProviderGnss";
            goto LABEL_4;
          case 65:
            v8 = L"LocationAcquireSingleShotGnss";
            goto LABEL_4;
          case 66:
            v8 = L"LocationAcquirePeriodicTrackingGnss";
            goto LABEL_4;
          case 67:
            v8 = L"LocationAcquireDistanceTrackingGnsss";
            goto LABEL_4;
          case 80:
            v8 = L"LocationGnssAdapter";
            goto LABEL_4;
          case 96:
            v8 = L"LocationCrowdsource";
            goto LABEL_4;
          case 97:
            v8 = L"LocationDcpAdapter";
            goto LABEL_4;
          case 114:
            v8 = L"LocationBackgroundBroker";
            goto LABEL_4;
          case 115:
            v8 = L"LocationSystemNotificationsCenter";
            goto LABEL_4;
          case 117:
            v8 = L"LocationPalMisc";
            goto LABEL_4;
          case 128:
            v8 = L"LocationProviderLegacyWinLocation";
            goto LABEL_4;
          case 129:
            v8 = L"LocationAcquireSingleShotLegacyWinLocation";
            goto LABEL_4;
          case 130:
            v8 = L"LocationAcquirePeriodicTrackingLegacyWinLocation";
            goto LABEL_4;
          case 144:
            v8 = L"LocationProviderIP";
            goto LABEL_4;
          case 145:
            v8 = L"LocationAcquireSingleShotIP";
            goto LABEL_4;
          default:
            return (unsigned int)-2147024809;
        }
      }
      v8 = L"GeofenceTracker";
      break;
  }
LABEL_4:
  v9 = L"LocationProviderHelper";
LABEL_5:
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"LfSvc",
                                 L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\",
                                 v47,
                                 510,
                                 0);
  v11 = 255;
  v12 = L"\\";
  v13 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      v13 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( v13 < 0 )
      return (unsigned int)v13;
  }
  else
  {
    v14 = -1;
    do
      ++v14;
    while ( v47[v14] );
    if ( (unsigned __int64)(v14 + 12) >= 0xFF )
    {
      v13 = -2147418113;
      LODWORD(v44) = -2147418113;
      wil::details::in1diag5::Return_HrMsg(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\idk\\LocationRegistryHelper.h",
        "CLocationPersistedRegPathHelper::GetPersistedRegPath",
        "E_UNEXPECTED",
        v44,
        (__int64)"Path is too long. buff len: %zu. subPath len: %zu",
        (const char *)v14,
        11);
      return (unsigned int)v13;
    }
    v15 = &v47[v14 - 1];
    v16 = *v15 - 92;
    if ( *v15 == 92 )
      v16 = v15[1];
    if ( v16 )
      _o_wcscat_s(v47, 255, L"\\");
    _o_wcscat_s(v47, 255, L"Components\\");
  }
  v13 = StringCchPrintfW(v50, 0xFFu, L"%s%s", v47, v8);
  if ( v13 < 0 )
    return (unsigned int)v13;
  v17 = 255;
  v18 = v50;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  v19 = -2147024809;
  if ( !v17 )
    return v19;
  v20 = 2147483646;
  v21 = 2147483646;
  v22 = &v51[-2 * v17];
  v23 = L"\\";
  do
  {
    if ( !v21 )
      break;
    if ( !*v23 )
      break;
    *v22++ = *v23++;
    --v21;
    --v17;
  }
  while ( v17 );
  v24 = v22 - 1;
  v25 = -2147024774;
  v19 = -2147024774;
  if ( v17 )
  {
    v24 = v22;
    v19 = 0;
  }
  *v24 = 0;
  if ( !v17 )
    return v19;
  v26 = 255;
  v27 = v50;
  do
  {
    if ( !*v27 )
      break;
    ++v27;
    --v26;
  }
  while ( v26 );
  v28 = L"Settings";
  v19 = -2147024809;
  if ( v26 )
  {
    v29 = 2147483646;
    v30 = L"Settings";
    v31 = &v51[-2 * v26];
    do
    {
      if ( !v29 )
        break;
      if ( !*v30 )
        break;
      *v31++ = *v30++;
      --v29;
      --v26;
    }
    while ( v26 );
    v32 = v31 - 1;
    v19 = -2147024774;
    if ( v26 )
    {
      v32 = v31;
      v19 = 0;
    }
    *v32 = 0;
  }
  if ( (v19 & 0x80000000) != 0 )
    return v19;
  memset_0(v47, 0, 0x1FEu);
  switch ( a1 )
  {
    case 6:
      v9 = L"ServerTileInformation";
      break;
    case 2:
      v9 = L"LocationSession";
      break;
    case 512:
      v9 = L"General";
      break;
    default:
      if ( a1 > 256 )
      {
        switch ( a1 )
        {
          case 257:
            v9 = L"GeofenceManager";
            goto LABEL_40;
          case 258:
            v9 = L"GeofenceSettings";
            goto LABEL_40;
          case 259:
            v9 = L"GeofenceEventSubscriptions";
            goto LABEL_40;
          case 260:
            v9 = L"GeofenceAppServices";
            goto LABEL_40;
          case 261:
            v9 = L"GeofenceStore";
            goto LABEL_40;
          case 262:
            v9 = L"LocationCivicAddrAdapter";
            goto LABEL_40;
          case 272:
            v9 = L"VisitClientBoundary";
            goto LABEL_40;
          case 273:
            v9 = L"VisitInformation";
            goto LABEL_40;
          case 288:
            v9 = L"LocationAdapterBluetooth";
            goto LABEL_40;
          default:
            return (unsigned int)-2147024809;
        }
      }
      if ( a1 != 256 )
      {
        switch ( a1 )
        {
          case 1:
            goto LABEL_40;
          case 3:
            v9 = L"LocationInformation";
            goto LABEL_40;
          case 4:
            v9 = L"LocationWebServiceProxy";
            goto LABEL_40;
          case 7:
            v9 = L"LocationPermissionManager";
            goto LABEL_40;
          case 8:
            v9 = L"LocationUserHandles";
            goto LABEL_40;
          case 16:
            v9 = L"LocationProviderComposite";
            goto LABEL_40;
          case 17:
            v9 = L"LocationAcquireSingleShotCpe";
            goto LABEL_40;
          case 18:
            v9 = L"LocationAcquireEmulatedTrackingCpe";
            goto LABEL_40;
          case 19:
            v9 = L"LocationAcquireOffloadedTrackingCpe";
            goto LABEL_40;
          case 20:
            v9 = L"LocationMovementDetector";
            goto LABEL_40;
          case 21:
            v9 = L"LocationAcquireOverrideCpe";
            goto LABEL_40;
          case 32:
            v9 = L"LocationProviderWiFi";
            goto LABEL_40;
          case 33:
            v9 = L"LocationAdapterWiFi";
            goto LABEL_40;
          case 34:
            v9 = L"LocationAcquireSingleShotWiFi";
            goto LABEL_40;
          case 48:
            v9 = L"LocationProviderCell";
            goto LABEL_40;
          case 49:
            v9 = L"LocationAdapterCell";
            goto LABEL_40;
          case 50:
            v9 = L"LocationAcquireSingleShotCell";
            goto LABEL_40;
          case 64:
            v9 = L"LocationProviderGnss";
            goto LABEL_40;
          case 65:
            v9 = L"LocationAcquireSingleShotGnss";
            goto LABEL_40;
          case 66:
            v9 = L"LocationAcquirePeriodicTrackingGnss";
            goto LABEL_40;
          case 67:
            v9 = L"LocationAcquireDistanceTrackingGnsss";
            goto LABEL_40;
          case 80:
            v9 = L"LocationGnssAdapter";
            goto LABEL_40;
          case 96:
            v9 = L"LocationCrowdsource";
            goto LABEL_40;
          case 97:
            v9 = L"LocationDcpAdapter";
            goto LABEL_40;
          case 114:
            v9 = L"LocationBackgroundBroker";
            goto LABEL_40;
          case 115:
            v9 = L"LocationSystemNotificationsCenter";
            goto LABEL_40;
          case 117:
            v9 = L"LocationPalMisc";
            goto LABEL_40;
          case 128:
            v9 = L"LocationProviderLegacyWinLocation";
            goto LABEL_40;
          case 129:
            v9 = L"LocationAcquireSingleShotLegacyWinLocation";
            goto LABEL_40;
          case 130:
            v9 = L"LocationAcquirePeriodicTrackingLegacyWinLocation";
            goto LABEL_40;
          case 144:
            v9 = L"LocationProviderIP";
            goto LABEL_40;
          case 145:
            v9 = L"LocationAcquireSingleShotIP";
            goto LABEL_40;
          default:
            return (unsigned int)-2147024809;
        }
      }
      v9 = L"GeofenceTracker";
      break;
  }
LABEL_40:
  v33 = StringCchPrintfW(v48, 0xFFu, L"%s%s", L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Components\\", v9);
  if ( v33 < 0 )
    return (unsigned int)v33;
  v34 = 255;
  v35 = v48;
  do
  {
    if ( !*v35 )
      break;
    ++v35;
    --v34;
  }
  while ( v34 );
  if ( !v34 )
    return (unsigned int)-2147024809;
  v36 = 2147483646;
  v37 = &v49[-2 * v34];
  do
  {
    if ( !v36 )
      break;
    if ( !*v12 )
      break;
    *v37++ = *v12++;
    --v36;
    --v34;
  }
  while ( v34 );
  v38 = v37 - 1;
  v39 = -2147024774;
  if ( v34 )
  {
    v38 = v37;
    v39 = 0;
  }
  *v38 = 0;
  if ( !v34 )
    return v39;
  v40 = v48;
  do
  {
    if ( !*v40 )
      break;
    ++v40;
    --v11;
  }
  while ( v11 );
  if ( v11 )
  {
    v41 = &v49[-2 * v11];
    do
    {
      if ( !v20 )
        break;
      if ( !*v28 )
        break;
      *v41++ = *v28++;
      --v20;
      --v11;
    }
    while ( v11 );
    v42 = v41 - 1;
    if ( v11 )
    {
      v42 = v41;
      v25 = 0;
    }
    *v42 = 0;
  }
  else
  {
    v25 = -2147024809;
  }
  if ( v25 < 0 )
    return (unsigned int)v25;
  result = GetRegistryValueWithFallbackW(-2147483646, v50, -2147483646, v48, v46, 16, 0, a4, 4, 0);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000dc00  push    rbx
0x18000dc02  push    rdi
0x18000dc03  push    r13
0x18000dc05  sub     rsp, 690h
0x18000dc0c  mov     rax, cs:__security_cookie
0x18000dc13  xor     rax, rsp
0x18000dc16  mov     [rsp+6A8h+var_48], rax
0x18000dc1e  mov     ebx, r8d
0x18000dc21  mov     [rsp+6A8h+var_650], rdx
0x18000dc26  mov     r13d, ecx
0x18000dc29  mov     [rsp+6A8h+var_658], r9
0x18000dc2e  xor     edx, edx; Val
0x18000dc30  lea     rcx, [rsp+6A8h+var_248]; void *
0x18000dc38  mov     r8d, 1FEh; Size
0x18000dc3e  mov     rdi, r9
0x18000dc41  call    memset_0
0x18000dc46  xor     edx, edx; Val
0x18000dc48  lea     rcx, [rsp+6A8h+var_448]; void *
0x18000dc50  mov     r8d, 1FEh; Size
0x18000dc56  call    memset_0
0x18000dc5b  test    rdi, rdi
0x18000dc5e  jz      loc_18000E1DE
0x18000dc64  mov     [rsp+6A8h+arg_0], rbp
0x18000dc6c  lea     rcx, [rsp+6A8h+var_648]; void *
0x18000dc71  mov     [rsp+6A8h+var_20], rsi
0x18000dc79  xor     edx, edx; Val
0x18000dc7b  mov     [rsp+6A8h+var_28], r12
0x18000dc83  mov     r8d, 1FEh; Size
0x18000dc89  mov     [rsp+6A8h+var_30], r14
0x18000dc91  mov     [rsp+6A8h+var_38], r15
0x18000dc99  mov     [rdi], ebx
0x18000dc9b  call    memset_0
0x18000dca0  cmp     r13d, 6
0x18000dca4  jnz     loc_18000E035
0x18000dcaa  lea     rdi, aServertileinfo; "ServerTileInformation"
0x18000dcb1  lea     r12, aLocationprovid_1; "LocationProviderHelper"
0x18000dcb8  mov     r9d, 1FEh
0x18000dcbe  mov     [rsp+6A8h+var_688], 0
0x18000dcc7  lea     r8, [rsp+6A8h+var_648]
0x18000dccc  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18000dcd3  lea     rcx, aLfsvc_1; "LfSvc"
0x18000dcda  call    cs:__imp_GetPersistedRegistryLocationW
0x18000dce0  mov     ebx, 0FFh
0x18000dce5  lea     r15, asc_18016EDDC; "\\"
0x18000dcec  mov     r14d, eax
0x18000dcef  test    eax, eax
0x18000dcf1  jnz     loc_18000E1CF
0x18000dcf7  lea     rax, [rsp+6A8h+var_648]
0x18000dcfc  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000dd03  inc     rdx
0x18000dd06  cmp     word ptr [rax+rdx*2], 0
0x18000dd0b  jnz     short loc_18000DD03
0x18000dd0d  lea     rax, [rdx+0Ch]
0x18000dd11  cmp     rax, rbx
0x18000dd14  jnb     loc_18000E62C
0x18000dd1a  lea     rcx, [rsp+rdx*2+6A8h+var_650+6]
0x18000dd1f  movzx   edx, word ptr [rsp+rdx*2+6A8h+var_650+6]
0x18000dd24  sub     edx, 5Ch ; '\'
0x18000dd27  jnz     short loc_18000DD34
0x18000dd29  movzx   edx, word ptr [rcx+2]
0x18000dd2d  xor     eax, eax
0x18000dd2f  movzx   ecx, ax
0x18000dd32  sub     edx, ecx
0x18000dd34  test    edx, edx
0x18000dd36  jnz     loc_18000E3F4
0x18000dd3c  lea     r8, aComponents; "Components\\"
0x18000dd43  mov     rdx, rbx
0x18000dd46  lea     rcx, [rsp+6A8h+var_648]
0x18000dd4b  call    cs:__imp__o_wcscat_s
0x18000dd51  lea     r9, [rsp+6A8h+var_648]
0x18000dd56  mov     [rsp+6A8h+var_688], rdi
0x18000dd5b  lea     r8, aSS_1; "%s%s"
0x18000dd62  mov     rdx, rbx; unsigned __int64
0x18000dd65  lea     rcx, [rsp+6A8h+var_248]; unsigned __int16 *
0x18000dd6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dd72  mov     r14d, eax
0x18000dd75  test    eax, eax
0x18000dd77  js      loc_18000E1C4
0x18000dd7d  mov     rdx, rbx
0x18000dd80  lea     rax, [rsp+6A8h+var_248]
0x18000dd88  cmp     word ptr [rax], 0
0x18000dd8c  jz      short loc_18000DD98
0x18000dd8e  add     rax, 2
0x18000dd92  sub     rdx, 1
0x18000dd96  jnz     short loc_18000DD88
0x18000dd98  xor     eax, eax
0x18000dd9a  mov     r14d, 80070057h
0x18000dda0  test    rdx, rdx
0x18000dda3  mov     r8d, r14d
0x18000dda6  cmovnz  r8d, eax
0x18000ddaa  jz      loc_18000E1C7
0x18000ddb0  mov     esi, 7FFFFFFEh
0x18000ddb5  lea     rax, [rdx+rdx]
0x18000ddb9  lea     r9, [rsp+6A8h+var_4A]
0x18000ddc1  mov     ecx, esi
0x18000ddc3  sub     r9, rax
0x18000ddc6  mov     r8, r15
0x18000ddc9  nop     dword ptr [rax+00000000h]
0x18000ddd0  test    rcx, rcx
0x18000ddd3  jz      short loc_18000DDF3
0x18000ddd5  movzx   eax, word ptr [r8]
0x18000ddd9  test    ax, ax
0x18000dddc  jz      short loc_18000DDF3
0x18000ddde  mov     [r9], ax
0x18000dde2  add     r8, 2
0x18000dde6  add     r9, 2
0x18000ddea  dec     rcx
0x18000dded  sub     rdx, 1
0x18000ddf1  jnz     short loc_18000DDD0
0x18000ddf3  xor     eax, eax
0x18000ddf5  lea     rcx, [r9-2]
0x18000ddf9  test    rdx, rdx
0x18000ddfc  mov     ebp, 8007007Ah
0x18000de01  mov     r8d, ebp
0x18000de04  cmovnz  rcx, r9
0x18000de08  cmovnz  r8d, eax
0x18000de0c  mov     [rcx], ax
0x18000de0f  jz      loc_18000E1C7
0x18000de15  mov     rdx, rbx
0x18000de18  lea     rax, [rsp+6A8h+var_248]
0x18000de20  cmp     word ptr [rax], 0
0x18000de24  jz      short loc_18000DE30
0x18000de26  add     rax, 2
0x18000de2a  sub     rdx, 1
0x18000de2e  jnz     short loc_18000DE20
0x18000de30  xor     eax, eax
0x18000de32  lea     rdi, aSettings; "Settings"
0x18000de39  test    rdx, rdx
0x18000de3c  mov     r8d, r14d
0x18000de3f  cmovnz  r8d, eax
0x18000de43  jz      short loc_18000DE9D
0x18000de45  lea     rax, [rdx+rdx]
0x18000de49  mov     rcx, rsi
0x18000de4c  lea     r9, [rsp+6A8h+var_4A]
0x18000de54  mov     r8, rdi
0x18000de57  sub     r9, rax
0x18000de5a  nop     word ptr [rax+rax+00h]
0x18000de60  test    rcx, rcx
0x18000de63  jz      short loc_18000DE83
0x18000de65  movzx   eax, word ptr [r8]
0x18000de69  test    ax, ax
0x18000de6c  jz      short loc_18000DE83
0x18000de6e  mov     [r9], ax
0x18000de72  add     r8, 2
0x18000de76  add     r9, 2
0x18000de7a  dec     rcx
0x18000de7d  sub     rdx, 1
0x18000de81  jnz     short loc_18000DE60
0x18000de83  test    rdx, rdx
0x18000de86  lea     rcx, [r9-2]
0x18000de8a  mov     r8d, ebp
0x18000de8d  cmovnz  rcx, r9
0x18000de91  xor     eax, eax
0x18000de93  test    rdx, rdx
0x18000de96  cmovnz  r8d, eax
0x18000de9a  mov     [rcx], ax
0x18000de9d  test    r8d, r8d
0x18000dea0  js      loc_18000E1C7
0x18000dea6  xor     edx, edx; Val
0x18000dea8  lea     rcx, [rsp+6A8h+var_648]; void *
0x18000dead  mov     r8d, 1FEh; Size
0x18000deb3  call    memset_0
0x18000deb8  cmp     r13d, 6
0x18000debc  jnz     loc_18000E097
0x18000dec2  lea     r12, aServertileinfo; "ServerTileInformation"
0x18000dec9  lea     r9, aSystemCurrentc; jumptable 000000018000E0EB case 1
0x18000ded0  mov     [rsp+6A8h+var_688], r12
0x18000ded5  lea     r8, aSS_1; "%s%s"
0x18000dedc  mov     rdx, rbx; unsigned __int64
0x18000dedf  lea     rcx, [rsp+6A8h+var_448]; unsigned __int16 *
0x18000dee7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000deec  test    eax, eax
0x18000deee  js      loc_18000E60E
0x18000def4  mov     rdx, rbx
0x18000def7  lea     rax, [rsp+6A8h+var_448]
0x18000deff  nop
0x18000df00  cmp     word ptr [rax], 0
0x18000df04  jz      short loc_18000DF10
0x18000df06  add     rax, 2
0x18000df0a  sub     rdx, 1
0x18000df0e  jnz     short loc_18000DF00
0x18000df10  xor     eax, eax
0x18000df12  mov     ecx, r14d
0x18000df15  test    rdx, rdx
0x18000df18  cmovnz  ecx, eax
0x18000df1b  jz      loc_18000E625
0x18000df21  lea     rax, [rdx+rdx]
0x18000df25  mov     rcx, rsi
0x18000df28  lea     r8, [rsp+6A8h+var_24A]
0x18000df30  sub     r8, rax
0x18000df33  test    rcx, rcx
0x18000df36  jz      short loc_18000DF56
0x18000df38  movzx   eax, word ptr [r15]
0x18000df3c  test    ax, ax
0x18000df3f  jz      short loc_18000DF56
0x18000df41  mov     [r8], ax
0x18000df45  add     r15, 2
0x18000df49  add     r8, 2
0x18000df4d  dec     rcx
0x18000df50  sub     rdx, 1
0x18000df54  jnz     short loc_18000DF33
0x18000df56  xor     eax, eax
0x18000df58  lea     rcx, [r8-2]
0x18000df5c  test    rdx, rdx
0x18000df5f  mov     r9d, ebp
0x18000df62  cmovnz  rcx, r8
0x18000df66  cmovnz  r9d, eax
0x18000df6a  mov     [rcx], ax
0x18000df6d  jz      loc_18000E61D
0x18000df73  lea     rax, [rsp+6A8h+var_448]
0x18000df7b  nop     dword ptr [rax+rax+00h]
0x18000df80  cmp     word ptr [rax], 0
0x18000df84  jz      short loc_18000DF90
0x18000df86  add     rax, 2
0x18000df8a  sub     rbx, 1
0x18000df8e  jnz     short loc_18000DF80
0x18000df90  xor     eax, eax
0x18000df92  test    rbx, rbx
0x18000df95  cmovnz  r14d, eax
0x18000df99  jz      loc_18000E615
0x18000df9f  lea     rax, [rbx+rbx]
0x18000dfa3  lea     rdx, [rsp+6A8h+var_24A]
0x18000dfab  sub     rdx, rax
0x18000dfae  xchg    ax, ax
0x18000dfb0  test    rsi, rsi
0x18000dfb3  jz      short loc_18000DFD1
0x18000dfb5  movzx   eax, word ptr [rdi]
0x18000dfb8  test    ax, ax
0x18000dfbb  jz      short loc_18000DFD1
0x18000dfbd  mov     [rdx], ax
0x18000dfc0  add     rdi, 2
0x18000dfc4  add     rdx, 2
0x18000dfc8  dec     rsi
0x18000dfcb  sub     rbx, 1
0x18000dfcf  jnz     short loc_18000DFB0
0x18000dfd1  test    rbx, rbx
0x18000dfd4  lea     rcx, [rdx-2]
0x18000dfd8  cmovnz  rcx, rdx
0x18000dfdc  xor     eax, eax
0x18000dfde  test    rbx, rbx
0x18000dfe1  cmovnz  ebp, eax
0x18000dfe4  mov     [rcx], ax
0x18000dfe7  test    ebp, ebp
0x18000dfe9  jns     loc_18000E0F9
0x18000dfef  mov     eax, ebp
0x18000dff1  mov     r14, [rsp+6A8h+var_30]
0x18000dff9  mov     r12, [rsp+6A8h+var_28]
0x18000e001  mov     rsi, [rsp+6A8h+var_20]
0x18000e009  mov     rbp, [rsp+6A8h+arg_0]
0x18000e011  mov     r15, [rsp+6A8h+var_38]
0x18000e019  mov     rcx, [rsp+6A8h+var_48]
0x18000e021  xor     rcx, rsp; StackCookie
0x18000e024  call    __security_check_cookie
0x18000e029  add     rsp, 690h
0x18000e030  pop     r13
0x18000e032  pop     rdi
0x18000e033  pop     rbx
0x18000e034  retn
0x18000e035  cmp     r13d, 2
0x18000e039  jz      loc_18000E164
0x18000e03f  cmp     r13d, 200h
0x18000e046  jz      loc_18000E17C
0x18000e04c  cmp     r13d, 100h
0x18000e053  jg      loc_18000E350
0x18000e059  jz      loc_18000E344
0x18000e05f  lea     eax, [r13-1]; switch 145 cases
0x18000e063  cmp     eax, 90h
0x18000e068  ja      def_18000E089; jumptable 000000018000E089 default case, cases 2,5,6,9-15,22-31,35-47,51-63,68-79,81-95,98-113,116,118-127,131-143
0x18000e06e  lea     rsi, __ImageBase
0x18000e075  cdqe
0x18000e077  movzx   eax, ds:(byte_18000E708 - 180000000h)[rsi+rax]
0x18000e07f  mov     ecx, ds:(jpt_18000E089 - 180000000h)[rsi+rax*4]
0x18000e086  add     rcx, rsi
0x18000e089  jmp     rcx; switch jump
0x18000e08b  lea     rdi, aLocationinform; jumptable 000000018000E089 case 3
0x18000e092  jmp     loc_18000DCB1
0x18000e097  cmp     r13d, 2
0x18000e09b  jz      loc_18000E170
0x18000e0a1  cmp     r13d, 200h
0x18000e0a8  jz      loc_18000E188
0x18000e0ae  cmp     r13d, 100h
0x18000e0b5  jg      loc_18000E572
0x18000e0bb  jz      loc_18000E566
0x18000e0c1  lea     eax, [r13-1]; switch 145 cases
0x18000e0c5  cmp     eax, 90h
0x18000e0ca  ja      def_18000E0EB; jumptable 000000018000E0EB default case, cases 2,5,6,9-15,22-31,35-47,51-63,68-79,81-95,98-113,116,118-127,131-143
0x18000e0d0  lea     rdx, __ImageBase
0x18000e0d7  cdqe
0x18000e0d9  movzx   eax, ds:(byte_18000E820 - 180000000h)[rdx+rax]
0x18000e0e1  mov     ecx, ds:(jpt_18000E0EB - 180000000h)[rdx+rax*4]
0x18000e0e8  add     rcx, rdx
0x18000e0eb  jmp     rcx; switch jump
0x18000e0ed  lea     r12, aLocationinform; jumptable 000000018000E0EB case 3
0x18000e0f4  jmp     loc_18000DEC9; jumptable 000000018000E0EB case 1
0x18000e0f9  mov     rax, [rsp+6A8h+var_658]
0x18000e0fe  lea     r9, [rsp+6A8h+var_448]
0x18000e106  mov     [rsp+6A8h+var_660], 0
0x18000e10f  lea     rdx, [rsp+6A8h+var_248]
0x18000e117  mov     dword ptr [rsp+6A8h+var_668], 4
0x18000e11f  mov     r8, 0FFFFFFFF80000002h
  ... truncated ...
```
