# RasInterfaceUpdateDefaultRouteSettings

- ea: `0x1800991c0`
- end: `0x180099548`
- name: `RasInterfaceUpdateDefaultRouteSettings`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180031a20`

## callees

- `0x180098c64`
- `0x1800991c0`
- `0x180099654`
- `0x180099770`
- `0x18009f484`
- `0x18009f6f8`
- `0x18009fba8`
- `0x1800a43b4`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099207`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099207`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009949a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009949a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180099375`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180099375`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180099341`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180099341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009939e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009939e`

## string_xrefs

- `0x1800994ea`: `RasUpdateDefaultRouteSettings: AdjustOtherInterfaceDefaultRoute failed. Error %d`
- `0x180099487`: `RasUpdateDefaultRouteSettings: AdjustVPNInterfaceDefaultRoute failed. Error %d`
- `0x18009932e`: `SYSTEM\CurrentControlSet\services\RemoteAccess\Parameters\IKEV2`
- `0x1800992b7`: `RasUpdateDefaultRouteSettings: AdjustOtherInterfaceMetrics failed. Error %d`
- `0x18009926e`: `RasUpdateDefaultRouteSettings(fIpv4:%u)(fSet:%u)(Luid:%I64X)(type:%s)(updateMetric: %s)`

## pseudocode

```c
__int64 __fastcall RasInterfaceUpdateDefaultRouteSettings(char a1, char a2, HKEY a3, char a4)
{
  HKEY *v8; // rax
  char v9; // dl
  const char *v10; // rcx
  const char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  LPVOID *v14; // r9
  unsigned int AllParameters; // ebx
  const CHAR *v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  LSTATUS v19; // edi
  HKEY v20; // rcx
  int v21; // ecx
  int v22; // r8d
  const NPI_MODULEID *v23; // rdi
  int v24; // ecx
  int v25; // r8d
  int v26; // ecx
  int v27; // r8d
  bool v28; // zf
  __int64 v29; // rcx
  int v30; // eax
  bool v31; // zf
  int v32; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY v43; // [rsp+78h] [rbp-88h] BYREF
  __int128 v44; // [rsp+80h] [rbp-80h]
  _BYTE v45[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  int v48; // [rsp+108h] [rbp+8h]
  bool v49; // [rsp+128h] [rbp+28h]
  int v50; // [rsp+168h] [rbp+68h]

  v44 = 0;
  EnterCriticalSection(&g_csInterfaceCache);
  v43 = a3;
  v8 = (HKEY *)g_RasVpnLuids;
  if ( g_RasVpnLuids )
  {
    while ( *v8 != a3 )
    {
      v8 = (HKEY *)v8[2];
      if ( !v8 )
        goto LABEL_4;
    }
    v9 = 1;
  }
  else
  {
LABEL_4:
    v9 = 0;
    *((_QWORD *)&v44 + 1) = g_RasVpnLuids;
  }
  v10 = "yes";
  if ( !a4 )
    v10 = "no";
  lpcbData = (LPDWORD)v10;
  v11 = "vpn";
  if ( !v9 )
    v11 = "internet";
  phkResult = (PHKEY)v11;
  TraceMsg("RasUpdateDefaultRouteSettings(fIpv4:%u)(fSet:%u)(Luid:%I64X)(type:%s)(updateMetric: %s)");
  if ( !a4 )
  {
    hKey = 0;
    Type = 4;
    cbData = 4;
    *(_DWORD *)Data = 0;
    v19 = RegOpenKeyExA(
            HKEY_LOCAL_MACHINE,
            "SYSTEM\\CurrentControlSet\\services\\RemoteAccess\\Parameters\\IKEV2",
            0,
            0x20019u,
            &hKey);
    if ( !v19 )
    {
      v19 = RegQueryValueExA(hKey, "DisableDefaultRouteHandling", 0, &Type, Data, &cbData);
      if ( v19 || Type != 4 )
      {
        *(_DWORD *)Data = 0;
        if ( v19 == 2 )
          v19 = 0;
      }
    }
    v20 = hKey;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v19 || *(_DWORD *)Data != 1 )
    {
      memset_0(v45, 0, 0xF0u);
      hKey = a3;
      v23 = &NPI_MS_IPV4_MODULEID;
      if ( !a2 )
        v23 = &NPI_MS_IPV6_MODULEID;
      AllParameters = GetAllParameters(v21, (_DWORD)v23, v22, (unsigned int)&hKey, phkResulta, (__int64)v45);
      if ( AllParameters )
        goto LABEL_42;
      memset_0(v45, 255, 0xF0u);
      v46 = 0;
      v47 = 0;
      v48 = 0;
      v50 = 0;
      v49 = a1 == 0;
      AllParameters = SetAllParameters(v24, (_DWORD)v23, v25, (unsigned int)&hKey, phkResultb, (__int64)v45);
      if ( AllParameters )
        goto LABEL_42;
      memset_0(v45, 0, 0xF0u);
      AllParameters = GetAllParameters(v26, (_DWORD)v23, v27, (unsigned int)&hKey, phkResultc, (__int64)v45);
      if ( AllParameters )
        goto LABEL_42;
      if ( a1 )
        v28 = !v49;
      else
        v28 = v49;
      if ( !v28 )
      {
        AllParameters = 1003;
LABEL_42:
        v16 = "RasUpdateDefaultRouteSettings: AdjustVPNInterfaceDefaultRoute failed. Error %d";
        goto LABEL_43;
      }
    }
    LOBYTE(v18) = a1;
    LOBYTE(v20) = a2;
    AllParameters = AdjustOtherInterfaceDefaultRoute(v20, v18, &v43);
    if ( AllParameters )
    {
      v16 = "RasUpdateDefaultRouteSettings: AdjustOtherInterfaceDefaultRoute failed. Error %d";
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  v14 = &g_IpV4InterfaceTable;
  LOBYTE(v12) = a1;
  if ( !a2 )
    v14 = &g_IpV6InterfaceTable;
  LOBYTE(v13) = a2;
  AllParameters = AdjustOtherInterfaceMetrics(v13, v12, &v43, v14, phkResult, lpcbData);
  if ( AllParameters )
  {
    v16 = "RasUpdateDefaultRouteSettings: AdjustOtherInterfaceMetrics failed. Error %d";
LABEL_43:
    TraceMsg(v16);
    goto LABEL_44;
  }
  if ( a2 )
  {
    if ( a1 )
      v17 = g_NumVpnIpv4RouteTableChanges + 1;
    else
      v17 = g_NumVpnIpv4RouteTableChanges - 1;
    g_NumVpnIpv4RouteTableChanges = v17;
  }
  else if ( a1 )
  {
    ++g_NumVpnIpv6RouteTableChanges;
  }
  else
  {
    --g_NumVpnIpv6RouteTableChanges;
  }
LABEL_44:
  LeaveCriticalSection(&g_csInterfaceCache);
  if ( a2 )
  {
    v30 = g_NumVpnIpv4RouteTableChanges;
    if ( !g_NumVpnIpv4RouteTableChanges )
      goto LABEL_49;
    if ( !g_hInterfaceChangeNotificationV4 )
    {
      LOBYTE(v29) = 1;
      RegisterInterfaceChangeNotifications(v29);
      v30 = g_NumVpnIpv4RouteTableChanges;
    }
    if ( !v30 )
    {
LABEL_49:
      v31 = g_hInterfaceChangeNotificationV4 == 0;
      goto LABEL_57;
    }
  }
  else
  {
    v32 = g_NumVpnIpv6RouteTableChanges;
    if ( !g_NumVpnIpv6RouteTableChanges )
      goto LABEL_56;
    if ( !g_hInterfaceChangeNotificationV6 )
    {
      RegisterInterfaceChangeNotifications(0);
      v32 = g_NumVpnIpv6RouteTableChanges;
    }
    if ( !v32 )
    {
LABEL_56:
      v31 = g_hInterfaceChangeNotificationV6 == 0;
LABEL_57:
      if ( !v31 )
        DeregisterInterfaceChangeNotifications();
    }
  }
  return AllParameters;
}

```

## disassembly

```asm
0x1800991c0  push    rbp
0x1800991c2  push    rbx
0x1800991c3  push    rsi
0x1800991c4  push    rdi
0x1800991c5  push    r12
0x1800991c7  push    r14
0x1800991c9  push    r15
0x1800991cb  lea     rbp, [rsp-90h]
0x1800991d3  sub     rsp, 190h
0x1800991da  mov     rax, cs:__security_cookie
0x1800991e1  xor     rax, rsp
0x1800991e4  mov     [rbp+0C0h+var_40], rax
0x1800991eb  movzx   esi, cl
0x1800991ee  xorps   xmm0, xmm0
0x1800991f1  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x1800991f8  movzx   r14d, dl
0x1800991fc  movdqu  [rbp+0C0h+var_140], xmm0
0x180099201  mov     dil, r9b
0x180099204  mov     rbx, r8
0x180099207  call    cs:__imp_EnterCriticalSection
0x18009920d  mov     rcx, cs:g_RasVpnLuids
0x180099214  xor     r15d, r15d
0x180099217  mov     [rsp+1C0h+var_148], rbx
0x18009921c  mov     rax, rcx
0x18009921f  test    rcx, rcx
0x180099222  jz      short loc_180099236
0x180099224  cmp     [rax], rbx
0x180099227  jz      loc_1800992C3
0x18009922d  mov     rax, [rax+10h]
0x180099231  test    rax, rax
0x180099234  jnz     short loc_180099224
0x180099236  mov     dl, r15b
0x180099239  mov     qword ptr [rbp+0C0h+var_140+8], rcx
0x18009923d  lea     r8, aInternet; "internet"
0x180099244  test    dil, dil
0x180099247  lea     rax, aNo; "no"
0x18009924e  mov     r9, rbx
0x180099251  lea     rcx, aYes; "yes"
0x180099258  cmovz   rcx, rax
0x18009925c  test    dl, dl
0x18009925e  mov     [rsp+1C0h+lpcbData], rcx
0x180099263  lea     rax, aVpn_1; "vpn"
0x18009926a  cmovz   rax, r8
0x18009926e  lea     rcx, aRasupdatedefau_1; "RasUpdateDefaultRouteSettings(fIpv4:%u)"...
0x180099275  mov     r8d, esi
0x180099278  mov     [rsp+1C0h+phkResult], rax
0x18009927d  mov     edx, r14d
0x180099280  call    TraceMsg
0x180099285  test    dil, dil
0x180099288  jz      short loc_180099306
0x18009928a  lea     rax, g_IpV6InterfaceTable
0x180099291  test    r14b, r14b
0x180099294  lea     r9, g_IpV4InterfaceTable
0x18009929b  mov     dl, sil
0x18009929e  cmovz   r9, rax
0x1800992a2  lea     r8, [rsp+1C0h+var_148]
0x1800992a7  mov     cl, r14b
0x1800992aa  call    AdjustOtherInterfaceMetrics
0x1800992af  mov     ebx, eax
0x1800992b1  test    eax, eax
0x1800992b3  jz      short loc_1800992CA
0x1800992b5  mov     edx, eax
0x1800992b7  lea     rcx, aRasupdatedefau; "RasUpdateDefaultRouteSettings: AdjustOt"...
0x1800992be  jmp     loc_18009948E
0x1800992c3  mov     dl, 1
0x1800992c5  jmp     loc_18009923D
0x1800992ca  test    r14b, r14b
0x1800992cd  jz      short loc_1800992EB
0x1800992cf  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x1800992d5  test    sil, sil
0x1800992d8  jz      short loc_1800992DE
0x1800992da  inc     eax
0x1800992dc  jmp     short loc_1800992E0
0x1800992de  dec     eax
0x1800992e0  mov     cs:g_NumVpnIpv4RouteTableChanges, eax
0x1800992e6  jmp     loc_180099493
0x1800992eb  test    sil, sil
0x1800992ee  jz      short loc_1800992FB
0x1800992f0  inc     cs:g_NumVpnIpv6RouteTableChanges
0x1800992f6  jmp     loc_180099493
0x1800992fb  dec     cs:g_NumVpnIpv6RouteTableChanges
0x180099301  jmp     loc_180099493
0x180099306  mov     r12d, 4
0x18009930c  mov     [rsp+1C0h+hKey], r15
0x180099311  lea     rax, [rsp+1C0h+hKey]
0x180099316  mov     [rsp+1C0h+Type], r12d
0x18009931b  mov     r9d, 20019h; samDesired
0x180099321  mov     [rsp+1C0h+cbData], r12d
0x180099326  xor     r8d, r8d; ulOptions
0x180099329  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18009932e  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\services\\Re"...
0x180099335  mov     dword ptr [rsp+1C0h+Data], r15d
0x18009933a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180099341  call    cs:__imp_RegOpenKeyExA
0x180099347  mov     edi, eax
0x180099349  test    eax, eax
0x18009934b  jnz     short loc_180099394
0x18009934d  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180099352  lea     rax, [rsp+1C0h+cbData]
0x180099357  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18009935c  lea     r9, [rsp+1C0h+Type]; lpType
0x180099361  lea     rax, [rsp+1C0h+Data]
0x180099366  xor     r8d, r8d; lpReserved
0x180099369  lea     rdx, aDisabledefault_0; "DisableDefaultRouteHandling"
0x180099370  mov     [rsp+1C0h+phkResult], rax; lpData
0x180099375  call    cs:__imp_RegQueryValueExA
0x18009937b  mov     edi, eax
0x18009937d  test    eax, eax
0x18009937f  jnz     short loc_180099388
0x180099381  cmp     [rsp+1C0h+Type], r12d
0x180099386  jz      short loc_180099394
0x180099388  cmp     edi, 2
0x18009938b  mov     dword ptr [rsp+1C0h+Data], r15d
0x180099390  cmovz   edi, r15d
0x180099394  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180099399  test    rcx, rcx
0x18009939c  jz      short loc_1800993A4
0x18009939e  call    cs:__imp_RegCloseKey
0x1800993a4  test    edi, edi
0x1800993a6  jnz     short loc_1800993B3
0x1800993a8  cmp     dword ptr [rsp+1C0h+Data], 1
0x1800993ad  jz      loc_1800994D2
0x1800993b3  mov     r12d, 0F0h
0x1800993b9  lea     rcx, [rbp+0C0h+var_130]; void *
0x1800993bd  mov     r8d, r12d; Size
0x1800993c0  xor     edx, edx; Val
0x1800993c2  call    memset_0
0x1800993c7  lea     rax, NPI_MS_IPV6_MODULEID
0x1800993ce  mov     [rsp+1C0h+hKey], rbx
0x1800993d3  test    r14b, r14b
0x1800993d6  lea     rdi, NPI_MS_IPV4_MODULEID
0x1800993dd  lea     r9, [rsp+1C0h+hKey]
0x1800993e2  cmovz   rdi, rax
0x1800993e6  lea     rax, [rbp+0C0h+var_130]
0x1800993ea  mov     rdx, rdi
0x1800993ed  mov     [rsp+1C0h+lpcbData], rax
0x1800993f2  call    GetAllParameters
0x1800993f7  mov     ebx, eax
0x1800993f9  test    eax, eax
0x1800993fb  jnz     loc_180099485
0x180099401  mov     r8d, r12d; Size
0x180099404  lea     edx, [r12+0Fh]; Val
0x180099409  lea     rcx, [rbp+0C0h+var_130]; void *
0x18009940d  call    memset_0
0x180099412  lea     rax, [rbp+0C0h+var_130]
0x180099416  mov     [rbp+0C0h+var_110], r15
0x18009941a  test    sil, sil
0x18009941d  mov     [rbp+0C0h+var_108], r15d
0x180099421  lea     r9, [rsp+1C0h+hKey]
0x180099426  mov     [rbp+0C0h+var_B8], r15d
0x18009942a  mov     rdx, rdi
0x18009942d  mov     [rbp+0C0h+var_58], r15d
0x180099431  setz    [rbp+0C0h+var_98]
0x180099435  mov     [rsp+1C0h+lpcbData], rax
0x18009943a  call    SetAllParameters
0x18009943f  mov     ebx, eax
0x180099441  test    eax, eax
0x180099443  jnz     short loc_180099485
0x180099445  mov     r8d, r12d; Size
0x180099448  lea     rcx, [rbp+0C0h+var_130]; void *
0x18009944c  xor     edx, edx; Val
0x18009944e  call    memset_0
0x180099453  lea     rax, [rbp+0C0h+var_130]
0x180099457  mov     rdx, rdi
0x18009945a  lea     r9, [rsp+1C0h+hKey]
0x18009945f  mov     [rsp+1C0h+lpcbData], rax
0x180099464  call    GetAllParameters
0x180099469  mov     ebx, eax
0x18009946b  test    eax, eax
0x18009946d  jnz     short loc_180099485
0x18009946f  test    sil, sil
0x180099472  jz      short loc_18009947A
0x180099474  cmp     [rbp+0C0h+var_98], r15b
0x180099478  jmp     short loc_18009947E
0x18009947a  cmp     [rbp+0C0h+var_98], 1
0x18009947e  jz      short loc_1800994D2
0x180099480  mov     ebx, 3EBh
0x180099485  mov     edx, ebx
0x180099487  lea     rcx, aRasupdatedefau_2; "RasUpdateDefaultRouteSettings: AdjustVP"...
0x18009948e  call    TraceMsg
0x180099493  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18009949a  call    cs:__imp_LeaveCriticalSection
0x1800994a0  test    r14b, r14b
0x1800994a3  jz      short loc_1800994F3
0x1800994a5  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x1800994ab  test    eax, eax
0x1800994ad  jz      short loc_1800994C9
0x1800994af  cmp     cs:g_hInterfaceChangeNotificationV4, r15
0x1800994b6  jnz     short loc_1800994C5
0x1800994b8  mov     cl, 1
0x1800994ba  call    RegisterInterfaceChangeNotifications
0x1800994bf  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x1800994c5  test    eax, eax
0x1800994c7  jnz     short loc_180099525
0x1800994c9  cmp     cs:g_hInterfaceChangeNotificationV4, r15
0x1800994d0  jmp     short loc_18009951E
0x1800994d2  lea     r8, [rsp+1C0h+var_148]
0x1800994d7  mov     dl, sil
0x1800994da  mov     cl, r14b
0x1800994dd  call    AdjustOtherInterfaceDefaultRoute
0x1800994e2  mov     ebx, eax
0x1800994e4  test    eax, eax
0x1800994e6  jz      short loc_180099493
0x1800994e8  mov     edx, eax
0x1800994ea  lea     rcx, aRasupdatedefau_0; "RasUpdateDefaultRouteSettings: AdjustOt"...
0x1800994f1  jmp     short loc_18009948E
0x1800994f3  mov     eax, cs:g_NumVpnIpv6RouteTableChanges
0x1800994f9  test    eax, eax
0x1800994fb  jz      short loc_180099517
0x1800994fd  cmp     cs:g_hInterfaceChangeNotificationV6, r15
0x180099504  jnz     short loc_180099513
0x180099506  xor     ecx, ecx
0x180099508  call    RegisterInterfaceChangeNotifications
0x18009950d  mov     eax, cs:g_NumVpnIpv6RouteTableChanges
0x180099513  test    eax, eax
0x180099515  jnz     short loc_180099525
0x180099517  cmp     cs:g_hInterfaceChangeNotificationV6, r15
0x18009951e  jz      short loc_180099525
0x180099520  call    DeregisterInterfaceChangeNotifications
0x180099525  mov     eax, ebx
0x180099527  mov     rcx, [rbp+0C0h+var_40]
0x18009952e  xor     rcx, rsp; StackCookie
0x180099531  call    __security_check_cookie
0x180099536  add     rsp, 190h
0x18009953d  pop     r15
0x18009953f  pop     r14
0x180099541  pop     r12
0x180099543  pop     rdi
0x180099544  pop     rsi
0x180099545  pop     rbx
0x180099546  pop     rbp
0x180099547  retn
```
