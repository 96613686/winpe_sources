# LocationRegistryHelper::GetComponentRegSubKeyPath(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort const *,ushort *,ulong,int)

- ea: `0x18000e950`
- end: `0x18000f030`
- name: `?GetComponentRegSubKeyPath@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEBGPEAGKH@Z`
- size: `1760`
- prototype: `__int64 __fastcall(int, __int64, unsigned __int16 *, __int64, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009d8a0`
- `0x1800d5d38`
- `0x1800d5e30`

## callees

- `0x18000e950`
- `0x18000f040`
- `0x18008fa98`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000eb98`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000ee61`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000eb98`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000ee61`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000eb28`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000eb28`

## string_xrefs

- `0x18000eb89`: `Components\`
- `0x18000e9b8`: `SYSTEM\CurrentControlSet\Services\lfsvc\Components\`
- `0x18000eb1a`: `SYSTEM\CurrentControlSet\Services\lfsvc\`
- `0x18000ec17`: `LocationWebServiceProxy`
- `0x18000ee90`: `onecoreuap\drivers\MobilePC\Location\Product\idk\LocationRegistryHelper.h`
- `0x18000ee74`: `Path is too long. buff len: %zu. subPath len: %zu`
- `0x18000ee84`: `CLocationPersistedRegPathHelper::GetPersistedRegPath`
- `0x18000ec63`: `LocationProviderComposite`
- `0x18000ec93`: `LocationMovementDetector`
- `0x18000ed8f`: `LocationBackgroundBroker`
- `0x18000ee10`: `GeofenceAppServices`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall LocationRegistryHelper::GetComponentRegSubKeyPath(
        int a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  const wchar_t *v7; // rbx
  const wchar_t *v8; // rdi
  const wchar_t *v9; // r9
  signed int v10; // esi
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  unsigned int v13; // r9d
  __int64 v14; // r10
  __int64 v15; // rcx
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // rcx
  unsigned int v18; // r11d
  __int64 v19; // rdx
  unsigned __int16 *v20; // rax
  const wchar_t *v21; // rcx
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rcx
  int PersistedRegistryLocationW; // eax
  __int64 v26; // rdx
  unsigned __int16 *v27; // rcx
  int v28; // edx
  wil::details *v29; // [rsp+28h] [rbp-250h]
  _WORD v31[256]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+278h] [rbp+0h]

  memset_0(v31, 0, 0x1FEu);
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
            return (unsigned int)-2147024809;
        }
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
            return (unsigned int)-2147024809;
        }
      }
      v7 = L"GeofenceTracker";
      break;
  }
LABEL_3:
  v8 = L"\\";
  if ( a5 )
  {
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"LfSvc",
                                   L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\",
                                   v31,
                                   510,
                                   0);
    v10 = PersistedRegistryLocationW;
    if ( PersistedRegistryLocationW )
    {
      if ( PersistedRegistryLocationW > 0 )
        v10 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      if ( v10 < 0 )
        return (unsigned int)v10;
    }
    else
    {
      v26 = -1;
      do
        ++v26;
      while ( v31[v26] );
      if ( (unsigned __int64)(v26 + 12) >= 0xFF )
      {
        v10 = -2147418113;
        LODWORD(v29) = -2147418113;
        wil::details::in1diag5::Return_HrMsg(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\idk\\LocationRegistryHelper.h",
          "CLocationPersistedRegPathHelper::GetPersistedRegPath",
          "E_UNEXPECTED",
          v29,
          (__int64)"Path is too long. buff len: %zu. subPath len: %zu",
          (const char *)v26,
          11);
        return (unsigned int)v10;
      }
      v27 = &v31[v26 - 1];
      v28 = *v27 - 92;
      if ( *v27 == 92 )
        v28 = v27[1];
      if ( v28 )
        _o_wcscat_s(v31, 255, L"\\");
      _o_wcscat_s(v31, 255, L"Components\\");
    }
    v9 = v31;
  }
  else
  {
    v9 = L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Components\\";
  }
  v10 = StringCchPrintfW(a3, 0xFFu, L"%s%s", v9, v7);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v11 = 255;
  v12 = a3;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = -2147024809;
  if ( !v11 )
    return v13;
  v14 = 2147483646;
  v15 = 2147483646;
  v16 = &a3[255 - v11];
  do
  {
    if ( !v15 )
      break;
    if ( !*v8 )
      break;
    *v16++ = *v8++;
    --v15;
    --v11;
  }
  while ( v11 );
  v17 = v16 - 1;
  v18 = -2147024774;
  v13 = -2147024774;
  if ( v11 )
  {
    v17 = v16;
    v13 = 0;
  }
  *v17 = 0;
  if ( !v11 )
    return v13;
  v19 = 255;
  v20 = a3;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  if ( v19 )
  {
    v21 = L"Settings";
    v22 = &a3[255 - v19];
    do
    {
      if ( !v14 )
        break;
      if ( !*v21 )
        break;
      *v22++ = *v21++;
      --v14;
      --v19;
    }
    while ( v19 );
    v23 = v22 - 1;
    if ( v19 )
    {
      v23 = v22;
      v18 = 0;
    }
    *v23 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v18;
}

```

## disassembly

```asm
0x18000e950  mov     [rsp+arg_0], rbx
0x18000e955  mov     [rsp+arg_8], rbp
0x18000e95a  push    rsi
0x18000e95b  push    rdi
0x18000e95c  push    r14
0x18000e95e  sub     rsp, 260h
0x18000e965  mov     rax, cs:__security_cookie
0x18000e96c  xor     rax, rsp
0x18000e96f  mov     [rsp+278h+var_28], rax
0x18000e977  mov     r14, r8
0x18000e97a  mov     ebx, ecx
0x18000e97c  mov     r8d, 1FEh; Size
0x18000e982  lea     rcx, [rsp+278h+var_228]; void *
0x18000e987  xor     edx, edx; Val
0x18000e989  call    memset_0
0x18000e98e  cmp     ebx, 6
0x18000e991  jnz     loc_18000EBA8
0x18000e997  lea     rbx, aServertileinfo; "ServerTileInformation"
0x18000e99e  cmp     [rsp+278h+arg_20], 0
0x18000e9a6  lea     rdi, asc_18016EDDC; "\\"
0x18000e9ad  jnz     loc_18000EB06
0x18000e9b3  mov     ebp, 0FFh
0x18000e9b8  lea     r9, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18000e9bf  lea     r8, aSS_1; "%s%s"
0x18000e9c6  mov     rdx, rbp; unsigned __int64
0x18000e9c9  mov     rcx, r14; unsigned __int16 *
0x18000e9cc  mov     [rsp+278h+var_258], rbx
0x18000e9d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e9d6  mov     esi, eax
0x18000e9d8  test    eax, eax
0x18000e9da  js      loc_18000EC37
0x18000e9e0  mov     rdx, rbp
0x18000e9e3  mov     rax, r14
0x18000e9e6  cmp     word ptr [rax], 0
0x18000e9ea  jz      short loc_18000E9F6
0x18000e9ec  add     rax, 2
0x18000e9f0  sub     rdx, 1
0x18000e9f4  jnz     short loc_18000E9E6
0x18000e9f6  xor     eax, eax
0x18000e9f8  mov     esi, 80070057h
0x18000e9fd  test    rdx, rdx
0x18000ea00  mov     r9d, esi
0x18000ea03  cmovnz  r9d, eax
0x18000ea07  jz      loc_18000EEC8
0x18000ea0d  mov     rax, rbp
0x18000ea10  mov     r10d, 7FFFFFFEh
0x18000ea16  sub     rax, rdx
0x18000ea19  mov     ecx, r10d
0x18000ea1c  lea     r8, [r14+rax*2]
0x18000ea20  test    rcx, rcx
0x18000ea23  jz      short loc_18000EA42
0x18000ea25  movzx   eax, word ptr [rdi]
0x18000ea28  test    ax, ax
0x18000ea2b  jz      short loc_18000EA42
0x18000ea2d  mov     [r8], ax
0x18000ea31  add     rdi, 2
0x18000ea35  add     r8, 2
0x18000ea39  dec     rcx
0x18000ea3c  sub     rdx, 1
0x18000ea40  jnz     short loc_18000EA20
0x18000ea42  xor     eax, eax
0x18000ea44  lea     rcx, [r8-2]
0x18000ea48  test    rdx, rdx
0x18000ea4b  mov     r11d, 8007007Ah
0x18000ea51  mov     r9d, r11d
0x18000ea54  cmovnz  rcx, r8
0x18000ea58  cmovnz  r9d, eax
0x18000ea5c  mov     [rcx], ax
0x18000ea5f  jz      loc_18000EEC8
0x18000ea65  mov     rdx, rbp
0x18000ea68  mov     rax, r14
0x18000ea6b  nop     dword ptr [rax+rax+00h]
0x18000ea70  cmp     word ptr [rax], 0
0x18000ea74  jz      short loc_18000EA80
0x18000ea76  add     rax, 2
0x18000ea7a  sub     rdx, 1
0x18000ea7e  jnz     short loc_18000EA70
0x18000ea80  xor     eax, eax
0x18000ea82  test    rdx, rdx
0x18000ea85  cmovnz  esi, eax
0x18000ea88  jz      loc_18000EEC0
0x18000ea8e  sub     rbp, rdx
0x18000ea91  lea     rcx, aSettings; "Settings"
0x18000ea98  lea     rax, [r14+rbp*2]
0x18000ea9c  nop     dword ptr [rax+00h]
0x18000eaa0  test    r10, r10
0x18000eaa3  jz      short loc_18000EAC4
0x18000eaa5  movzx   r8d, word ptr [rcx]
0x18000eaa9  test    r8w, r8w
0x18000eaad  jz      short loc_18000EAC4
0x18000eaaf  mov     [rax], r8w
0x18000eab3  add     rcx, 2
0x18000eab7  add     rax, 2
0x18000eabb  dec     r10
0x18000eabe  sub     rdx, 1
0x18000eac2  jnz     short loc_18000EAA0
0x18000eac4  test    rdx, rdx
0x18000eac7  lea     rcx, [rax-2]
0x18000eacb  cmovnz  rcx, rax
0x18000eacf  xor     eax, eax
0x18000ead1  test    rdx, rdx
0x18000ead4  cmovnz  r11d, eax
0x18000ead8  mov     [rcx], ax
0x18000eadb  mov     eax, r11d
0x18000eade  mov     rcx, [rsp+278h+var_28]
0x18000eae6  xor     rcx, rsp; StackCookie
0x18000eae9  call    __security_check_cookie
0x18000eaee  lea     r11, [rsp+278h+var_18]
0x18000eaf6  mov     rbx, [r11+20h]
0x18000eafa  mov     rbp, [r11+28h]
0x18000eafe  mov     rsp, r11
0x18000eb01  pop     r14
0x18000eb03  pop     rdi
0x18000eb04  pop     rsi
0x18000eb05  retn
0x18000eb06  mov     r9d, 1FEh
0x18000eb0c  mov     [rsp+278h+var_258], 0
0x18000eb15  lea     r8, [rsp+278h+var_228]
0x18000eb1a  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18000eb21  lea     rcx, aLfsvc_1; "LfSvc"
0x18000eb28  call    cs:__imp_GetPersistedRegistryLocationW
0x18000eb2e  mov     esi, eax
0x18000eb30  mov     ebp, 0FFh
0x18000eb35  test    eax, eax
0x18000eb37  jnz     loc_18000EC3E
0x18000eb3d  lea     rax, [rsp+278h+var_228]
0x18000eb42  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000eb49  nop     dword ptr [rax+00000000h]
0x18000eb50  inc     rdx
0x18000eb53  cmp     word ptr [rax+rdx*2], 0
0x18000eb58  jnz     short loc_18000EB50
0x18000eb5a  lea     rax, [rdx+0Ch]
0x18000eb5e  cmp     rax, rbp
0x18000eb61  jnb     loc_18000EE6C
0x18000eb67  lea     rcx, [rsp+rdx*2+278h+var_22A]
0x18000eb6c  movzx   edx, [rsp+rdx*2+278h+var_22A]
0x18000eb71  sub     edx, 5Ch ; '\'
0x18000eb74  jnz     short loc_18000EB81
0x18000eb76  movzx   edx, word ptr [rcx+2]
0x18000eb7a  xor     eax, eax
0x18000eb7c  movzx   ecx, ax
0x18000eb7f  sub     edx, ecx
0x18000eb81  test    edx, edx
0x18000eb83  jnz     loc_18000EE56
0x18000eb89  lea     r8, aComponents; "Components\\"
0x18000eb90  mov     rdx, rbp
0x18000eb93  lea     rcx, [rsp+278h+var_228]
0x18000eb98  call    cs:__imp__o_wcscat_s
0x18000eb9e  lea     r9, [rsp+278h+var_228]
0x18000eba3  jmp     loc_18000E9BF
0x18000eba8  cmp     ebx, 2
0x18000ebab  jz      short loc_18000EBFF
0x18000ebad  cmp     ebx, 200h
0x18000ebb3  jz      short loc_18000EC0B
0x18000ebb5  cmp     ebx, 100h
0x18000ebbb  jg      loc_18000EDB3
0x18000ebc1  jz      loc_18000EDA7
0x18000ebc7  dec     ebx; switch 145 cases
0x18000ebc9  cmp     ebx, 90h
0x18000ebcf  ja      def_18000EBF1; jumptable 000000018000EBF1 default case, cases 2,5,6,9-15,22-31,35-47,51-63,68-79,81-95,98-113,116,118-127,131-143
0x18000ebd5  lea     rdx, __ImageBase
0x18000ebdc  movsxd  rax, ebx
0x18000ebdf  movzx   eax, ds:(byte_18000EF54 - 180000000h)[rdx+rax]
0x18000ebe7  mov     ecx, ds:(jpt_18000EBF1 - 180000000h)[rdx+rax*4]
0x18000ebee  add     rcx, rdx
0x18000ebf1  jmp     rcx; switch jump
0x18000ebf3  lea     rbx, aLocationinform; jumptable 000000018000EBF1 case 3
0x18000ebfa  jmp     loc_18000E99E
0x18000ebff  lea     rbx, aLocationsessio; "LocationSession"
0x18000ec06  jmp     loc_18000E99E
0x18000ec0b  lea     rbx, aGeneral; "General"
0x18000ec12  jmp     loc_18000E99E
0x18000ec17  lea     rbx, aLocationwebser; jumptable 000000018000EBF1 case 4
0x18000ec1e  jmp     loc_18000E99E
0x18000ec23  lea     rbx, aLocationprovid_1; jumptable 000000018000EBF1 case 1
0x18000ec2a  jmp     loc_18000E99E
0x18000ec2f  test    esi, esi
0x18000ec31  jns     loc_18000EB9E
0x18000ec37  mov     eax, esi
0x18000ec39  jmp     loc_18000EADE
0x18000ec3e  jle     short loc_18000EC2F
0x18000ec40  movzx   esi, ax
0x18000ec43  or      esi, 80070000h
0x18000ec49  jmp     short loc_18000EC2F
0x18000ec4b  lea     rbx, aLocationpermis; jumptable 000000018000EBF1 case 7
0x18000ec52  jmp     loc_18000E99E
0x18000ec57  lea     rbx, aLocationuserha_0; jumptable 000000018000EBF1 case 8
0x18000ec5e  jmp     loc_18000E99E
0x18000ec63  lea     rbx, aLocationprovid_3; jumptable 000000018000EBF1 case 16
0x18000ec6a  jmp     loc_18000E99E
0x18000ec6f  lea     rbx, aLocationacquir_3; jumptable 000000018000EBF1 case 17
0x18000ec76  jmp     loc_18000E99E
0x18000ec7b  lea     rbx, aLocationacquir_9; jumptable 000000018000EBF1 case 18
0x18000ec82  jmp     loc_18000E99E
0x18000ec87  lea     rbx, aLocationacquir_5; jumptable 000000018000EBF1 case 19
0x18000ec8e  jmp     loc_18000E99E
0x18000ec93  lea     rbx, aLocationmoveme; jumptable 000000018000EBF1 case 20
0x18000ec9a  jmp     loc_18000E99E
0x18000ec9f  lea     rbx, aLocationacquir_0; jumptable 000000018000EBF1 case 21
0x18000eca6  jmp     loc_18000E99E
0x18000ecab  lea     rbx, aLocationprovid; jumptable 000000018000EBF1 case 32
0x18000ecb2  jmp     loc_18000E99E
0x18000ecb7  lea     rbx, aLocationadapte_2; jumptable 000000018000EBF1 case 33
0x18000ecbe  jmp     loc_18000E99E
0x18000ecc3  lea     rbx, aLocationacquir_7; jumptable 000000018000EBF1 case 34
0x18000ecca  jmp     loc_18000E99E
0x18000eccf  lea     rbx, aLocationprovid_4; jumptable 000000018000EBF1 case 144
0x18000ecd6  jmp     loc_18000E99E
0x18000ecdb  lea     rbx, aLocationacquir_10; jumptable 000000018000EBF1 case 145
0x18000ece2  jmp     loc_18000E99E
0x18000ece7  lea     rbx, aLocationprovid_2; jumptable 000000018000EBF1 case 48
0x18000ecee  jmp     loc_18000E99E
0x18000ecf3  lea     rbx, aLocationadapte_0; jumptable 000000018000EBF1 case 49
0x18000ecfa  jmp     loc_18000E99E
0x18000ecff  lea     rbx, aLocationacquir_4; jumptable 000000018000EBF1 case 50
0x18000ed06  jmp     loc_18000E99E
0x18000ed0b  lea     rbx, aLocationprovid_0; jumptable 000000018000EBF1 case 64
0x18000ed12  jmp     loc_18000E99E
0x18000ed17  lea     rbx, aLocationacquir; jumptable 000000018000EBF1 case 65
0x18000ed1e  jmp     loc_18000E99E
0x18000ed23  lea     rbx, aLocationacquir_1; jumptable 000000018000EBF1 case 66
0x18000ed2a  jmp     loc_18000E99E
0x18000ed2f  lea     rbx, aLocationacquir_2; jumptable 000000018000EBF1 case 67
0x18000ed36  jmp     loc_18000E99E
0x18000ed3b  lea     rbx, aLocationgnssad; jumptable 000000018000EBF1 case 80
0x18000ed42  jmp     loc_18000E99E
0x18000ed47  lea     rbx, aLocationprovid_5; jumptable 000000018000EBF1 case 128
0x18000ed4e  jmp     loc_18000E99E
0x18000ed53  lea     rbx, aLocationacquir_8; jumptable 000000018000EBF1 case 129
0x18000ed5a  jmp     loc_18000E99E
0x18000ed5f  lea     rbx, aLocationacquir_6; jumptable 000000018000EBF1 case 130
0x18000ed66  jmp     loc_18000E99E
0x18000ed6b  lea     rbx, aLocationcrowds; jumptable 000000018000EBF1 case 96
0x18000ed72  jmp     loc_18000E99E
0x18000ed77  lea     rbx, aLocationdcpada; jumptable 000000018000EBF1 case 97
0x18000ed7e  jmp     loc_18000E99E
0x18000ed83  lea     rbx, aLocationpalmis; jumptable 000000018000EBF1 case 117
0x18000ed8a  jmp     loc_18000E99E
0x18000ed8f  lea     rbx, aLocationbackgr; jumptable 000000018000EBF1 case 114
0x18000ed96  jmp     loc_18000E99E
0x18000ed9b  lea     rbx, aLocationsystem_1; jumptable 000000018000EBF1 case 115
0x18000eda2  jmp     loc_18000E99E
0x18000eda7  lea     rbx, aGeofencetracke; "GeofenceTracker"
0x18000edae  jmp     loc_18000E99E
0x18000edb3  add     ebx, 0FFFFFEFFh; switch 32 cases
0x18000edb9  cmp     ebx, 1Fh
0x18000edbc  ja      def_18000EBF1; jumptable 000000018000EBF1 default case, cases 2,5,6,9-15,22-31,35-47,51-63,68-79,81-95,98-113,116,118-127,131-143
0x18000edc2  lea     rdx, __ImageBase
0x18000edc9  movsxd  rax, ebx
0x18000edcc  movzx   eax, ds:(byte_18000F010 - 180000000h)[rdx+rax]
0x18000edd4  mov     ecx, ds:(jpt_18000EDDE - 180000000h)[rdx+rax*4]
0x18000eddb  add     rcx, rdx
0x18000edde  jmp     rcx; switch jump
0x18000ede0  lea     rbx, aLocationadapte_3; jumptable 000000018000EDDE case 288
0x18000ede7  jmp     loc_18000E99E
0x18000edec  lea     rbx, aGeofencemanage; jumptable 000000018000EDDE case 257
0x18000edf3  jmp     loc_18000E99E
0x18000edf8  lea     rbx, aGeofencesettin; jumptable 000000018000EDDE case 258
0x18000edff  jmp     loc_18000E99E
0x18000ee04  lea     rbx, aGeofenceevents; jumptable 000000018000EDDE case 259
0x18000ee0b  jmp     loc_18000E99E
0x18000ee10  lea     rbx, aGeofenceappser; jumptable 000000018000EDDE case 260
0x18000ee17  jmp     loc_18000E99E
0x18000ee1c  lea     rbx, aGeofencestore; jumptable 000000018000EDDE case 261
0x18000ee23  jmp     loc_18000E99E
0x18000ee28  lea     rbx, aLocationcivica_3; jumptable 000000018000EDDE case 262
0x18000ee2f  jmp     loc_18000E99E
0x18000ee34  lea     rbx, aVisitclientbou; jumptable 000000018000EDDE case 272
0x18000ee3b  jmp     loc_18000E99E
0x18000ee40  lea     rbx, aVisitinformati; jumptable 000000018000EDDE case 273
0x18000ee47  jmp     loc_18000E99E
0x18000ee4c  mov     esi, 80070057h; jumptable 000000018000EBF1 default case, cases 2,5,6,9-15,22-31,35-47,51-63,68-79,81-95,98-113,116,118-127,131-143
0x18000ee51  jmp     loc_18000EC37
0x18000ee56  mov     r8, rdi
0x18000ee59  lea     rcx, [rsp+278h+var_228]
0x18000ee5e  mov     rdx, rbp
0x18000ee61  call    cs:__imp__o_wcscat_s
0x18000ee67  jmp     loc_18000EB89
0x18000ee6c  mov     rcx, [rsp+278h]; this
0x18000ee74  lea     rax, aPathIsTooLongB; "Path is too long. buff len: %zu. subPat"...
0x18000ee7b  mov     [rsp+278h+var_238], 0Bh
0x18000ee84  lea     r9, aClocationpersi; "CLocationPersistedRegPathHelper::GetPer"...
0x18000ee8b  mov     [rsp+278h+var_240], rdx; char *
0x18000ee90  lea     r8, aOnecoreuapDriv_0; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18000ee97  mov     [rsp+278h+var_248], rax; __int64
0x18000ee9c  mov     esi, 8000FFFFh
0x18000eea1  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x18000eea8  mov     dword ptr [rsp+278h+var_250], esi; wil::details *
0x18000eeac  mov     edx, 35h ; '5'; void *
0x18000eeb1  mov     [rsp+278h+var_258], rax; char *
0x18000eeb6  call    ?Return_HrMsg@in1diag5@details@wil@@YAXPEAXIPEBD11J1ZZ; wil::details::in1diag5::Return_HrMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x18000eebb  jmp     loc_18000EC37
0x18000eec0  mov     r11d, esi
0x18000eec3  jmp     loc_18000EADB
0x18000eec8  mov     eax, r9d
0x18000eecb  jmp     loc_18000EADE
```
