# LocationRegistryHelper::GetComponentRegKeyPath(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort *,ulong,int)

- ea: `0x18000d650`
- end: `0x18000dbf4`
- name: `?GetComponentRegKeyPath@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEAGKH@Z`
- size: `1444`
- prototype: `__int64 __fastcall(int, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d430`

## callees

- `0x18000d650`
- `0x18000f040`
- `0x18008fa98`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d734`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000da33`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d734`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000da33`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000d6ca`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000d6ca`

## string_xrefs

- `0x18000d723`: `Components\`
- `0x18000d69c`: `SYSTEM\CurrentControlSet\Services\lfsvc\Components\`
- `0x18000d6bc`: `SYSTEM\CurrentControlSet\Services\lfsvc\`
- `0x18000d7e3`: `LocationWebServiceProxy`
- `0x18000da56`: `onecoreuap\drivers\MobilePC\Location\Product\idk\LocationRegistryHelper.h`
- `0x18000da67`: `Path is too long. buff len: %zu. subPath len: %zu`
- `0x18000da46`: `CLocationPersistedRegPathHelper::GetPersistedRegPath`
- `0x18000d82f`: `LocationProviderComposite`
- `0x18000d85f`: `LocationMovementDetector`
- `0x18000d95b`: `LocationBackgroundBroker`
- `0x18000d9dc`: `GeofenceAppServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LocationRegistryHelper::GetComponentRegKeyPath(int a1, unsigned __int16 *a2, __int64 a3, int a4)
{
  const wchar_t *v7; // rsi
  const wchar_t *v8; // r9
  int PersistedRegistryLocationW; // eax
  signed int v10; // ebx
  __int64 v11; // rax
  int v12; // edx
  __int64 result; // rax
  wil::details *v14; // [rsp+28h] [rbp-260h]
  _WORD v16[256]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+288h] [rbp+0h]

  memset_0(v16, 0, 0x1FEu);
  switch ( a1 )
  {
    case 6:
      v7 = L"ServerTileInformation";
      break;
    case 2:
      v7 = L"LocationSession";
      break;
    case 512:
      v7 = L"General";
      break;
    default:
      if ( a1 > 256 )
      {
        switch ( a1 )
        {
          case 257:
            v7 = L"GeofenceManager";
            goto LABEL_3;
          case 258:
            v7 = L"GeofenceSettings";
            goto LABEL_3;
          case 259:
            v7 = L"GeofenceEventSubscriptions";
            goto LABEL_3;
          case 260:
            v7 = L"GeofenceAppServices";
            goto LABEL_3;
          case 261:
            v7 = L"GeofenceStore";
            goto LABEL_3;
          case 262:
            v7 = L"LocationCivicAddrAdapter";
            goto LABEL_3;
          case 272:
            v7 = L"VisitClientBoundary";
            goto LABEL_3;
          case 273:
            v7 = L"VisitInformation";
            goto LABEL_3;
          case 288:
            v7 = L"LocationAdapterBluetooth";
            goto LABEL_3;
          default:
LABEL_70:
            result = 2147942487LL;
            break;
        }
        return result;
      }
      if ( a1 != 256 )
      {
        switch ( a1 )
        {
          case 1:
            v7 = L"LocationProviderHelper";
            goto LABEL_3;
          case 3:
            v7 = L"LocationInformation";
            goto LABEL_3;
          case 4:
            v7 = L"LocationWebServiceProxy";
            goto LABEL_3;
          case 7:
            v7 = L"LocationPermissionManager";
            goto LABEL_3;
          case 8:
            v7 = L"LocationUserHandles";
            goto LABEL_3;
          case 16:
            v7 = L"LocationProviderComposite";
            goto LABEL_3;
          case 17:
            v7 = L"LocationAcquireSingleShotCpe";
            goto LABEL_3;
          case 18:
            v7 = L"LocationAcquireEmulatedTrackingCpe";
            goto LABEL_3;
          case 19:
            v7 = L"LocationAcquireOffloadedTrackingCpe";
            goto LABEL_3;
          case 20:
            v7 = L"LocationMovementDetector";
            goto LABEL_3;
          case 21:
            v7 = L"LocationAcquireOverrideCpe";
            goto LABEL_3;
          case 32:
            v7 = L"LocationProviderWiFi";
            goto LABEL_3;
          case 33:
            v7 = L"LocationAdapterWiFi";
            goto LABEL_3;
          case 34:
            v7 = L"LocationAcquireSingleShotWiFi";
            goto LABEL_3;
          case 48:
            v7 = L"LocationProviderCell";
            goto LABEL_3;
          case 49:
            v7 = L"LocationAdapterCell";
            goto LABEL_3;
          case 50:
            v7 = L"LocationAcquireSingleShotCell";
            goto LABEL_3;
          case 64:
            v7 = L"LocationProviderGnss";
            goto LABEL_3;
          case 65:
            v7 = L"LocationAcquireSingleShotGnss";
            goto LABEL_3;
          case 66:
            v7 = L"LocationAcquirePeriodicTrackingGnss";
            goto LABEL_3;
          case 67:
            v7 = L"LocationAcquireDistanceTrackingGnsss";
            goto LABEL_3;
          case 80:
            v7 = L"LocationGnssAdapter";
            goto LABEL_3;
          case 96:
            v7 = L"LocationCrowdsource";
            goto LABEL_3;
          case 97:
            v7 = L"LocationDcpAdapter";
            goto LABEL_3;
          case 114:
            v7 = L"LocationBackgroundBroker";
            goto LABEL_3;
          case 115:
            v7 = L"LocationSystemNotificationsCenter";
            goto LABEL_3;
          case 117:
            v7 = L"LocationPalMisc";
            goto LABEL_3;
          case 128:
            v7 = L"LocationProviderLegacyWinLocation";
            goto LABEL_3;
          case 129:
            v7 = L"LocationAcquireSingleShotLegacyWinLocation";
            goto LABEL_3;
          case 130:
            v7 = L"LocationAcquirePeriodicTrackingLegacyWinLocation";
            goto LABEL_3;
          case 144:
            v7 = L"LocationProviderIP";
            goto LABEL_3;
          case 145:
            v7 = L"LocationAcquireSingleShotIP";
            goto LABEL_3;
          default:
            goto LABEL_70;
        }
      }
      v7 = L"GeofenceTracker";
      break;
  }
LABEL_3:
  if ( !a4 )
  {
    v8 = L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Components\\";
    return StringCchPrintfW(a2, 0xFFu, L"%s%s", v8, v7);
  }
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"LfSvc",
                                 L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\",
                                 v16,
                                 510,
                                 0);
  v10 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      v10 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( v10 >= 0 )
      goto LABEL_14;
  }
  else
  {
    v11 = -1;
    do
      ++v11;
    while ( v16[v11] );
    if ( (unsigned __int64)(v11 + 12) < 0xFF )
    {
      v12 = (unsigned __int16)v16[v11 - 1] - 92;
      if ( v16[v11 - 1] == 92 )
        v12 = (unsigned __int16)v16[v11];
      if ( v12 )
        _o_wcscat_s(v16, 255, L"\\");
      _o_wcscat_s(v16, 255, L"Components\\");
LABEL_14:
      v8 = v16;
      return StringCchPrintfW(a2, 0xFFu, L"%s%s", v8, v7);
    }
    v10 = -2147418113;
    LODWORD(v14) = -2147418113;
    wil::details::in1diag5::Return_HrMsg(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\idk\\LocationRegistryHelper.h",
      "CLocationPersistedRegPathHelper::GetPersistedRegPath",
      "E_UNEXPECTED",
      v14,
      (__int64)"Path is too long. buff len: %zu. subPath len: %zu",
      (const char *)v11,
      11);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d650  push    rbx
0x18000d652  push    rbp
0x18000d653  push    rsi
0x18000d654  push    rdi
0x18000d655  sub     rsp, 268h
0x18000d65c  mov     rax, cs:__security_cookie
0x18000d663  xor     rax, rsp
0x18000d666  mov     [rsp+288h+var_38], rax
0x18000d66e  mov     rbp, rdx
0x18000d671  mov     ebx, ecx
0x18000d673  xor     edx, edx; Val
0x18000d675  lea     rcx, [rsp+288h+var_238]; void *
0x18000d67a  mov     r8d, 1FEh; Size
0x18000d680  mov     edi, r9d
0x18000d683  call    memset_0
0x18000d688  cmp     ebx, 6
0x18000d68b  jnz     loc_18000D774
0x18000d691  lea     rsi, aServertileinfo; "ServerTileInformation"
0x18000d698  test    edi, edi
0x18000d69a  jnz     short loc_18000D6A8
0x18000d69c  lea     r9, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18000d6a3  jmp     loc_18000D73F
0x18000d6a8  mov     r9d, 1FEh
0x18000d6ae  mov     [rsp+288h+var_268], 0
0x18000d6b7  lea     r8, [rsp+288h+var_238]
0x18000d6bc  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18000d6c3  lea     rcx, aLfsvc_1; "LfSvc"
0x18000d6ca  call    cs:__imp_GetPersistedRegistryLocationW
0x18000d6d0  mov     ebx, eax
0x18000d6d2  test    eax, eax
0x18000d6d4  jnz     loc_18000D80A
0x18000d6da  lea     rcx, [rsp+288h+var_238]
0x18000d6df  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d6e6  inc     rax
0x18000d6e9  cmp     word ptr [rcx+rax*2], 0
0x18000d6ee  jnz     short loc_18000D6E6
0x18000d6f0  lea     rcx, [rax+0Ch]
0x18000d6f4  cmp     rcx, 0FFh
0x18000d6fb  jnb     loc_18000DA3E
0x18000d701  movzx   edx, [rsp+rax*2+288h+var_23A]
0x18000d706  lea     rcx, [rsp+rax*2+288h+var_23A]
0x18000d70b  sub     edx, 5Ch ; '\'
0x18000d70e  jnz     short loc_18000D71B
0x18000d710  movzx   edx, word ptr [rcx+2]
0x18000d714  xor     eax, eax
0x18000d716  movzx   ecx, ax
0x18000d719  sub     edx, ecx
0x18000d71b  test    edx, edx
0x18000d71d  jnz     loc_18000DA22
0x18000d723  lea     r8, aComponents; "Components\\"
0x18000d72a  mov     edx, 0FFh
0x18000d72f  lea     rcx, [rsp+288h+var_238]
0x18000d734  call    cs:__imp__o_wcscat_s
0x18000d73a  lea     r9, [rsp+288h+var_238]
0x18000d73f  lea     r8, aSS_1; "%s%s"
0x18000d746  mov     [rsp+288h+var_268], rsi
0x18000d74b  mov     edx, 0FFh; unsigned __int64
0x18000d750  mov     rcx, rbp; unsigned __int16 *
0x18000d753  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d758  mov     rcx, [rsp+288h+var_38]
0x18000d760  xor     rcx, rsp; StackCookie
0x18000d763  call    __security_check_cookie
0x18000d768  add     rsp, 268h
0x18000d76f  pop     rdi
0x18000d770  pop     rsi
0x18000d771  pop     rbp
0x18000d772  pop     rbx
0x18000d773  retn
0x18000d774  cmp     ebx, 2
0x18000d777  jz      short loc_18000D7CB
0x18000d779  cmp     ebx, 200h
0x18000d77f  jz      short loc_18000D7D7
0x18000d781  cmp     ebx, 100h
0x18000d787  jg      loc_18000D97F
0x18000d78d  jz      loc_18000D973
0x18000d793  dec     ebx; switch 145 cases
0x18000d795  cmp     ebx, 90h
0x18000d79b  ja      def_18000D7BD; jumptable 000000018000D7BD default case, cases 2,5,6,9-15,22-31,35-47,51-63,68-79,81-95,98-113,116,118-127,131-143
0x18000d7a1  lea     rdx, __ImageBase
0x18000d7a8  movsxd  rax, ebx
0x18000d7ab  movzx   eax, ds:(byte_18000DB18 - 180000000h)[rdx+rax]
0x18000d7b3  mov     ecx, ds:(jpt_18000D7BD - 180000000h)[rdx+rax*4]
0x18000d7ba  add     rcx, rdx
0x18000d7bd  jmp     rcx; switch jump
0x18000d7bf  lea     rsi, aLocationinform; jumptable 000000018000D7BD case 3
0x18000d7c6  jmp     loc_18000D698
0x18000d7cb  lea     rsi, aLocationsessio; "LocationSession"
0x18000d7d2  jmp     loc_18000D698
0x18000d7d7  lea     rsi, aGeneral; "General"
0x18000d7de  jmp     loc_18000D698
0x18000d7e3  lea     rsi, aLocationwebser; jumptable 000000018000D7BD case 4
0x18000d7ea  jmp     loc_18000D698
0x18000d7ef  lea     rsi, aLocationprovid_1; jumptable 000000018000D7BD case 1
0x18000d7f6  jmp     loc_18000D698
0x18000d7fb  test    ebx, ebx
0x18000d7fd  jns     loc_18000D73A
0x18000d803  mov     eax, ebx
0x18000d805  jmp     loc_18000D758
0x18000d80a  jle     short loc_18000D7FB
0x18000d80c  movzx   ebx, ax
0x18000d80f  or      ebx, 80070000h
0x18000d815  jmp     short loc_18000D7FB
0x18000d817  lea     rsi, aLocationpermis; jumptable 000000018000D7BD case 7
0x18000d81e  jmp     loc_18000D698
0x18000d823  lea     rsi, aLocationuserha_0; jumptable 000000018000D7BD case 8
0x18000d82a  jmp     loc_18000D698
0x18000d82f  lea     rsi, aLocationprovid_3; jumptable 000000018000D7BD case 16
0x18000d836  jmp     loc_18000D698
0x18000d83b  lea     rsi, aLocationacquir_3; jumptable 000000018000D7BD case 17
0x18000d842  jmp     loc_18000D698
0x18000d847  lea     rsi, aLocationacquir_9; jumptable 000000018000D7BD case 18
0x18000d84e  jmp     loc_18000D698
0x18000d853  lea     rsi, aLocationacquir_5; jumptable 000000018000D7BD case 19
0x18000d85a  jmp     loc_18000D698
0x18000d85f  lea     rsi, aLocationmoveme; jumptable 000000018000D7BD case 20
0x18000d866  jmp     loc_18000D698
0x18000d86b  lea     rsi, aLocationacquir_0; jumptable 000000018000D7BD case 21
0x18000d872  jmp     loc_18000D698
0x18000d877  lea     rsi, aLocationprovid; jumptable 000000018000D7BD case 32
0x18000d87e  jmp     loc_18000D698
0x18000d883  lea     rsi, aLocationadapte_2; jumptable 000000018000D7BD case 33
0x18000d88a  jmp     loc_18000D698
0x18000d88f  lea     rsi, aLocationacquir_7; jumptable 000000018000D7BD case 34
0x18000d896  jmp     loc_18000D698
0x18000d89b  lea     rsi, aLocationprovid_4; jumptable 000000018000D7BD case 144
0x18000d8a2  jmp     loc_18000D698
0x18000d8a7  lea     rsi, aLocationacquir_10; jumptable 000000018000D7BD case 145
0x18000d8ae  jmp     loc_18000D698
0x18000d8b3  lea     rsi, aLocationprovid_2; jumptable 000000018000D7BD case 48
0x18000d8ba  jmp     loc_18000D698
0x18000d8bf  lea     rsi, aLocationadapte_0; jumptable 000000018000D7BD case 49
0x18000d8c6  jmp     loc_18000D698
0x18000d8cb  lea     rsi, aLocationacquir_4; jumptable 000000018000D7BD case 50
0x18000d8d2  jmp     loc_18000D698
0x18000d8d7  lea     rsi, aLocationprovid_0; jumptable 000000018000D7BD case 64
0x18000d8de  jmp     loc_18000D698
0x18000d8e3  lea     rsi, aLocationacquir; jumptable 000000018000D7BD case 65
0x18000d8ea  jmp     loc_18000D698
0x18000d8ef  lea     rsi, aLocationacquir_1; jumptable 000000018000D7BD case 66
0x18000d8f6  jmp     loc_18000D698
0x18000d8fb  lea     rsi, aLocationacquir_2; jumptable 000000018000D7BD case 67
0x18000d902  jmp     loc_18000D698
0x18000d907  lea     rsi, aLocationgnssad; jumptable 000000018000D7BD case 80
0x18000d90e  jmp     loc_18000D698
0x18000d913  lea     rsi, aLocationprovid_5; jumptable 000000018000D7BD case 128
0x18000d91a  jmp     loc_18000D698
0x18000d91f  lea     rsi, aLocationacquir_8; jumptable 000000018000D7BD case 129
0x18000d926  jmp     loc_18000D698
0x18000d92b  lea     rsi, aLocationacquir_6; jumptable 000000018000D7BD case 130
0x18000d932  jmp     loc_18000D698
0x18000d937  lea     rsi, aLocationcrowds; jumptable 000000018000D7BD case 96
0x18000d93e  jmp     loc_18000D698
0x18000d943  lea     rsi, aLocationdcpada; jumptable 000000018000D7BD case 97
0x18000d94a  jmp     loc_18000D698
0x18000d94f  lea     rsi, aLocationpalmis; jumptable 000000018000D7BD case 117
0x18000d956  jmp     loc_18000D698
0x18000d95b  lea     rsi, aLocationbackgr; jumptable 000000018000D7BD case 114
0x18000d962  jmp     loc_18000D698
0x18000d967  lea     rsi, aLocationsystem_1; jumptable 000000018000D7BD case 115
0x18000d96e  jmp     loc_18000D698
0x18000d973  lea     rsi, aGeofencetracke; "GeofenceTracker"
0x18000d97a  jmp     loc_18000D698
0x18000d97f  add     ebx, 0FFFFFEFFh; switch 32 cases
0x18000d985  cmp     ebx, 1Fh
0x18000d988  ja      def_18000D7BD; jumptable 000000018000D7BD default case, cases 2,5,6,9-15,22-31,35-47,51-63,68-79,81-95,98-113,116,118-127,131-143
0x18000d98e  lea     rdx, __ImageBase
0x18000d995  movsxd  rax, ebx
0x18000d998  movzx   eax, ds:(byte_18000DBD4 - 180000000h)[rdx+rax]
0x18000d9a0  mov     ecx, ds:(jpt_18000D9AA - 180000000h)[rdx+rax*4]
0x18000d9a7  add     rcx, rdx
0x18000d9aa  jmp     rcx; switch jump
0x18000d9ac  lea     rsi, aLocationadapte_3; jumptable 000000018000D9AA case 288
0x18000d9b3  jmp     loc_18000D698
0x18000d9b8  lea     rsi, aGeofencemanage; jumptable 000000018000D9AA case 257
0x18000d9bf  jmp     loc_18000D698
0x18000d9c4  lea     rsi, aGeofencesettin; jumptable 000000018000D9AA case 258
0x18000d9cb  jmp     loc_18000D698
0x18000d9d0  lea     rsi, aGeofenceevents; jumptable 000000018000D9AA case 259
0x18000d9d7  jmp     loc_18000D698
0x18000d9dc  lea     rsi, aGeofenceappser; jumptable 000000018000D9AA case 260
0x18000d9e3  jmp     loc_18000D698
0x18000d9e8  lea     rsi, aGeofencestore; jumptable 000000018000D9AA case 261
0x18000d9ef  jmp     loc_18000D698
0x18000d9f4  lea     rsi, aLocationcivica_3; jumptable 000000018000D9AA case 262
0x18000d9fb  jmp     loc_18000D698
0x18000da00  lea     rsi, aVisitclientbou; jumptable 000000018000D9AA case 272
0x18000da07  jmp     loc_18000D698
0x18000da0c  lea     rsi, aVisitinformati; jumptable 000000018000D9AA case 273
0x18000da13  jmp     loc_18000D698
0x18000da18  mov     eax, 80070057h; jumptable 000000018000D7BD default case, cases 2,5,6,9-15,22-31,35-47,51-63,68-79,81-95,98-113,116,118-127,131-143
0x18000da1d  jmp     loc_18000D758
0x18000da22  lea     r8, asc_18016EDDC; "\\"
0x18000da29  mov     edx, 0FFh
0x18000da2e  lea     rcx, [rsp+288h+var_238]
0x18000da33  call    cs:__imp__o_wcscat_s
0x18000da39  jmp     loc_18000D723
0x18000da3e  mov     rcx, [rsp+288h]; this
0x18000da46  lea     r9, aClocationpersi; "CLocationPersistedRegPathHelper::GetPer"...
0x18000da4d  mov     [rsp+288h+var_248], 0Bh
0x18000da56  lea     r8, aOnecoreuapDriv_0; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18000da5d  mov     [rsp+288h+var_250], rax; char *
0x18000da62  mov     ebx, 8000FFFFh
0x18000da67  lea     rax, aPathIsTooLongB; "Path is too long. buff len: %zu. subPat"...
0x18000da6e  mov     edx, 35h ; '5'; void *
0x18000da73  mov     [rsp+288h+var_258], rax; __int64
0x18000da78  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x18000da7f  mov     dword ptr [rsp+288h+var_260], ebx; wil::details *
0x18000da83  mov     [rsp+288h+var_268], rax; char *
0x18000da88  call    ?Return_HrMsg@in1diag5@details@wil@@YAXPEAXIPEBD11J1ZZ; wil::details::in1diag5::Return_HrMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x18000da8d  jmp     loc_18000D803
```
