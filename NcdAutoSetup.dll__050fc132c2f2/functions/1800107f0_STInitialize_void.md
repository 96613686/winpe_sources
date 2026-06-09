# STInitialize(void)

- ea: `0x1800107f0`
- end: `0x180010a77`
- name: `?STInitialize@@YAXXZ`
- size: `647`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800110f0`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x18000e8cc`
- `0x1800107f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010898`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800108dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010925`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001096a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800109af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010898`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800108dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010925`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001096a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800109af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001085a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001085a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a67`

## pseudocode

```c
void STInitialize(void)
{
  HKEY v0; // rbx
  LSTATUS v1; // eax
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  DWORD Type; // [rsp+68h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  Data = 0;
  g_dwCurrentAutoSetupCount = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup",
          0,
          0x20019u,
          &hKey) )
  {
    v0 = hKey;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"WaitBeforeStart", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      g_dwWaitBeforeStart = Data;
    Type = 0;
    cbData = 4;
    v1 = RegQueryValueExW(v0, L"GlobalAutoSetup", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v1 && Type == 4 )
    {
      LOBYTE(v1) = Data != 0;
      g_fMachineQualified = v1;
    }
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(v0, L"NetworkSizeCalculationTimeout", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      g_dwNetworkSizeCalculationTimeout = Data;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(v0, L"MaxAutoSetupCountPerSizeCalculation", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      g_dwMaxAutoSetupCount = Data;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(v0, L"DefaulNetworkMask", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      if ( Data <= 0x20 )
      {
        g_dwDefaultNetworkMaskSize = Data;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
      }
    }
    InializeNetworkConfiguration(
      NLM_NETWORK_CATEGORY_PUBLIC,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup\\Public");
    InializeNetworkConfiguration(
      NLM_NETWORK_CATEGORY_PRIVATE,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup\\Private");
    InializeNetworkConfiguration(
      NLM_NETWORK_CATEGORY_DOMAIN_AUTHENTICATED,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup\\Domain");
    if ( v0 )
      RegCloseKey(v0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
}

```

## disassembly

```asm
0x1800107f0  push    rbp
0x1800107f2  push    rbx
0x1800107f3  push    rsi
0x1800107f4  push    r14
0x1800107f6  mov     rbp, rsp
0x1800107f9  sub     rsp, 38h
0x1800107fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180010804  lea     r14, WPP_GLOBAL_Control
0x18001080b  cmp     rcx, r14
0x18001080e  jz      short loc_18001082B
0x180010810  test    byte ptr [rcx+1Ch], 20h
0x180010814  jz      short loc_18001082B
0x180010816  mov     rcx, [rcx+10h]
0x18001081a  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010821  mov     edx, 0Ch
0x180010826  call    WPP_SF_
0x18001082b  xor     ebx, ebx
0x18001082d  lea     rax, [rbp+hKey]
0x180010831  mov     r9d, 20019h; samDesired
0x180010837  mov     [rbp+Data], ebx
0x18001083a  xor     r8d, r8d; ulOptions
0x18001083d  mov     cs:?g_dwCurrentAutoSetupCount@@3KA, ebx; ulong g_dwCurrentAutoSetupCount
0x180010843  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001084a  mov     [rbp+hKey], rbx
0x18001084e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010855  mov     [rsp+38h+phkResult], rax; phkResult
0x18001085a  call    cs:__imp_RegOpenKeyExW
0x180010860  test    eax, eax
0x180010862  jnz     loc_180010A38
0x180010868  mov     rbx, [rbp+hKey]
0x18001086c  lea     esi, [rax+4]
0x18001086f  mov     [rbp+Type], eax
0x180010872  lea     r9, [rbp+Type]; lpType
0x180010876  lea     rax, [rbp+cbData]
0x18001087a  mov     [rbp+cbData], esi
0x18001087d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180010882  lea     rdx, aWaitbeforestar; "WaitBeforeStart"
0x180010889  lea     rax, [rbp+Data]
0x18001088d  xor     r8d, r8d; lpReserved
0x180010890  mov     rcx, rbx; hKey
0x180010893  mov     [rsp+38h+phkResult], rax; lpData
0x180010898  call    cs:__imp_RegQueryValueExW
0x18001089e  test    eax, eax
0x1800108a0  jnz     short loc_1800108B0
0x1800108a2  cmp     [rbp+Type], esi
0x1800108a5  jnz     short loc_1800108B0
0x1800108a7  mov     eax, [rbp+Data]
0x1800108aa  mov     cs:?g_dwWaitBeforeStart@@3KA, eax; ulong g_dwWaitBeforeStart
0x1800108b0  lea     rax, [rbp+cbData]
0x1800108b4  mov     [rbp+Type], 0
0x1800108bb  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800108c0  lea     r9, [rbp+Type]; lpType
0x1800108c4  lea     rax, [rbp+Data]
0x1800108c8  mov     [rbp+cbData], esi
0x1800108cb  xor     r8d, r8d; lpReserved
0x1800108ce  mov     [rsp+38h+phkResult], rax; lpData
0x1800108d3  lea     rdx, aGlobalautosetu; "GlobalAutoSetup"
0x1800108da  mov     rcx, rbx; hKey
0x1800108dd  call    cs:__imp_RegQueryValueExW
0x1800108e3  test    eax, eax
0x1800108e5  jnz     short loc_1800108F8
0x1800108e7  cmp     [rbp+Type], esi
0x1800108ea  jnz     short loc_1800108F8
0x1800108ec  cmp     [rbp+Data], eax
0x1800108ef  setnz   al
0x1800108f2  mov     cs:?g_fMachineQualified@@3HA, eax; int g_fMachineQualified
0x1800108f8  lea     rax, [rbp+cbData]
0x1800108fc  mov     [rbp+Type], 0
0x180010903  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180010908  lea     r9, [rbp+Type]; lpType
0x18001090c  lea     rax, [rbp+Data]
0x180010910  mov     [rbp+cbData], esi
0x180010913  xor     r8d, r8d; lpReserved
0x180010916  mov     [rsp+38h+phkResult], rax; lpData
0x18001091b  lea     rdx, aNetworksizecal; "NetworkSizeCalculationTimeout"
0x180010922  mov     rcx, rbx; hKey
0x180010925  call    cs:__imp_RegQueryValueExW
0x18001092b  test    eax, eax
0x18001092d  jnz     short loc_18001093D
0x18001092f  cmp     [rbp+Type], esi
0x180010932  jnz     short loc_18001093D
0x180010934  mov     eax, [rbp+Data]
0x180010937  mov     cs:?g_dwNetworkSizeCalculationTimeout@@3KA, eax; ulong g_dwNetworkSizeCalculationTimeout
0x18001093d  lea     rax, [rbp+cbData]
0x180010941  mov     [rbp+Type], 0
0x180010948  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001094d  lea     r9, [rbp+Type]; lpType
0x180010951  lea     rax, [rbp+Data]
0x180010955  mov     [rbp+cbData], esi
0x180010958  xor     r8d, r8d; lpReserved
0x18001095b  mov     [rsp+38h+phkResult], rax; lpData
0x180010960  lea     rdx, aMaxautosetupco; "MaxAutoSetupCountPerSizeCalculation"
0x180010967  mov     rcx, rbx; hKey
0x18001096a  call    cs:__imp_RegQueryValueExW
0x180010970  test    eax, eax
0x180010972  jnz     short loc_180010982
0x180010974  cmp     [rbp+Type], esi
0x180010977  jnz     short loc_180010982
0x180010979  mov     eax, [rbp+Data]
0x18001097c  mov     cs:?g_dwMaxAutoSetupCount@@3KA, eax; ulong g_dwMaxAutoSetupCount
0x180010982  lea     rax, [rbp+cbData]
0x180010986  mov     [rbp+Type], 0
0x18001098d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180010992  lea     r9, [rbp+Type]; lpType
0x180010996  lea     rax, [rbp+Data]
0x18001099a  mov     [rbp+cbData], esi
0x18001099d  xor     r8d, r8d; lpReserved
0x1800109a0  mov     [rsp+38h+phkResult], rax; lpData
0x1800109a5  lea     rdx, aDefaulnetworkm; "DefaulNetworkMask"
0x1800109ac  mov     rcx, rbx; hKey
0x1800109af  call    cs:__imp_RegQueryValueExW
0x1800109b5  test    eax, eax
0x1800109b7  jnz     short loc_1800109F8
0x1800109b9  cmp     [rbp+Type], esi
0x1800109bc  jnz     short loc_1800109F8
0x1800109be  mov     eax, [rbp+Data]
0x1800109c1  cmp     eax, 20h ; ' '
0x1800109c4  jbe     short loc_1800109F2
0x1800109c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109cd  cmp     rcx, r14
0x1800109d0  jz      short loc_1800109F8
0x1800109d2  test    byte ptr [rcx+1Ch], 2
0x1800109d6  jz      short loc_1800109F8
0x1800109d8  mov     rcx, [rcx+10h]
0x1800109dc  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x1800109e3  mov     edx, 0Dh
0x1800109e8  mov     r9d, eax
0x1800109eb  call    WPP_SF_d
0x1800109f0  jmp     short loc_1800109F8
0x1800109f2  mov     cs:?g_dwDefaultNetworkMaskSize@@3KA, eax; ulong g_dwDefaultNetworkMaskSize
0x1800109f8  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800109ff  xor     ecx, ecx; enum NLM_NETWORK_CATEGORY
0x180010a01  call    ?InializeNetworkConfiguration@@YAXW4NLM_NETWORK_CATEGORY@@PEBG@Z; InializeNetworkConfiguration(NLM_NETWORK_CATEGORY,ushort const *)
0x180010a06  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010a0d  mov     ecx, 1; enum NLM_NETWORK_CATEGORY
0x180010a12  call    ?InializeNetworkConfiguration@@YAXW4NLM_NETWORK_CATEGORY@@PEBG@Z; InializeNetworkConfiguration(NLM_NETWORK_CATEGORY,ushort const *)
0x180010a17  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010a1e  mov     ecx, 2; enum NLM_NETWORK_CATEGORY
0x180010a23  call    ?InializeNetworkConfiguration@@YAXW4NLM_NETWORK_CATEGORY@@PEBG@Z; InializeNetworkConfiguration(NLM_NETWORK_CATEGORY,ushort const *)
0x180010a28  test    rbx, rbx
0x180010a2b  jz      short loc_180010A38
0x180010a2d  mov     rcx, rbx; hKey
0x180010a30  call    cs:__imp_RegCloseKey
0x180010a36  xor     ebx, ebx
0x180010a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a3f  cmp     rcx, r14
0x180010a42  jz      short loc_180010A5F
0x180010a44  test    byte ptr [rcx+1Ch], 20h
0x180010a48  jz      short loc_180010A5F
0x180010a4a  mov     rcx, [rcx+10h]
0x180010a4e  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010a55  mov     edx, 0Eh
0x180010a5a  call    WPP_SF_
0x180010a5f  test    rbx, rbx
0x180010a62  jz      short loc_180010A6D
0x180010a64  mov     rcx, rbx; hKey
0x180010a67  call    cs:__imp_RegCloseKey
0x180010a6d  add     rsp, 38h
0x180010a71  pop     r14
0x180010a73  pop     rsi
0x180010a74  pop     rbx
0x180010a75  pop     rbp
0x180010a76  retn
```
