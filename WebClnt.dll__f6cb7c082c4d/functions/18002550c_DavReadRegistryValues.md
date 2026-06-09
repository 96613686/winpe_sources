# DavReadRegistryValues

- ea: `0x18002550c`
- end: `0x1800259fc`
- name: `DavReadRegistryValues`
- size: `1264`
- prototype: `unsigned int()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180025f10`

## callees

- `0x18000b7dc`
- `0x18002539c`
- `0x18002550c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025552`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025552`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800255d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025647`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800256a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025709`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002576e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800257d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025834`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025899`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800258fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800259a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800255d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025647`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800256a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025709`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002576e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800257d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025834`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025899`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800258fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800259a8`

## string_xrefs

- `0x180025544`: `System\CurrentControlSet\Services\WebClient\Parameters`
- `0x1800255ca`: `ServerNotFoundCacheLifeTimeInSec`

## pseudocode

```c
unsigned int DavReadRegistryValues()
{
  unsigned int result; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int RegistryBypassServerNames; // eax
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\WebClient\\Parameters",
             0,
             1u,
             &hKey);
  if ( !result )
  {
    cbData = 4;
    v3 = RegQueryValueExW(
           hKey,
           L"ServerNotFoundCacheLifeTimeInSec",
           0,
           &Type,
           &ServerNotFoundCacheLifeTimeInSec,
           &cbData);
    if ( v3 )
    {
      *(_DWORD *)&ServerNotFoundCacheLifeTimeInSec = 60;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v3);
    }
    cbData = 4;
    v4 = RegQueryValueExW(hKey, L"AcceptOfficeAndTahoeServers", 0, &Type, &AcceptOfficeAndTahoeServers, &cbData);
    if ( v4 )
    {
      *(_DWORD *)&AcceptOfficeAndTahoeServers = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v4);
    }
    cbData = 4;
    v5 = RegQueryValueExW(hKey, L"SupportLocking", 0, &Type, &DavSupportLockingOfFiles, &cbData);
    if ( v5 )
    {
      *(_DWORD *)&DavSupportLockingOfFiles = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v5);
    }
    cbData = 4;
    v6 = RegQueryValueExW(hKey, L"FileSizeLimitInBytes", 0, &Type, &DavFileSizeLimitInBytes, &cbData);
    if ( v6 )
    {
      *(_DWORD *)&DavFileSizeLimitInBytes = 50000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v6);
    }
    cbData = 4;
    v7 = RegQueryValueExW(hKey, L"FileAttributesLimitInBytes", 0, &Type, &DavFileAttributesLimitInBytes, &cbData);
    if ( v7 )
    {
      *(_DWORD *)&DavFileAttributesLimitInBytes = 1000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v7);
    }
    cbData = 4;
    v8 = RegQueryValueExW(hKey, L"BasicAuthLevel", 0, &Type, &BasicAuthLevel, &cbData);
    if ( v8 )
    {
      *(_DWORD *)&BasicAuthLevel = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v8);
    }
    cbData = 4;
    v9 = RegQueryValueExW(hKey, L"LocalServerTimeoutInSec", 0, &Type, &DavLocalServerTimeoutInSec, &cbData);
    if ( v9 )
    {
      *(_DWORD *)&DavLocalServerTimeoutInSec = 15;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v9);
    }
    cbData = 4;
    v10 = RegQueryValueExW(hKey, L"InternetServerTimeoutInSec", 0, &Type, &DavInternetServerTimeoutInSec, &cbData);
    if ( v10 )
    {
      *(_DWORD *)&DavInternetServerTimeoutInSec = 30;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v10);
    }
    cbData = 4;
    v11 = RegQueryValueExW(hKey, L"SendReceiveTimeoutInSec", 0, &Type, &DavSendReceiveTimeoutInSec, &cbData);
    if ( v11 )
    {
      *(_DWORD *)&DavSendReceiveTimeoutInSec = 30;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v11);
    }
    RegistryBypassServerNames = DavReadRegistryBypassServerNames(hKey);
    if ( RegistryBypassServerNames )
    {
      pBypassServerNames = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          WPP_3c901703a5983ce609c0997329a96280_Traceguids,
          RegistryBypassServerNames);
    }
    DavAllowSSL = 1;
    cbData = 4;
    result = RegQueryValueExW(hKey, L"AllowInvalidCertDate", 0, &Type, &DavAllowInvalidCertDate, &cbData);
    if ( !result )
      goto LABEL_50;
    *(_DWORD *)&DavAllowInvalidCertDate = 0;
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v2 = 54;
LABEL_49:
    result = WPP_SF_d(v1[2], v2, WPP_3c901703a5983ce609c0997329a96280_Traceguids, result);
LABEL_50:
    if ( hKey )
      return RegCloseKey(hKey);
    return result;
  }
  hKey = 0;
  *(_DWORD *)&ServerNotFoundCacheLifeTimeInSec = 60;
  *(_DWORD *)&AcceptOfficeAndTahoeServers = 1;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v2 = 43;
    goto LABEL_49;
  }
  return result;
}

```

## disassembly

```asm
0x18002550c  push    rbp
0x18002550e  push    rbx
0x18002550f  push    rsi
0x180025510  push    rdi
0x180025511  push    r15
0x180025513  mov     rbp, rsp
0x180025516  sub     rsp, 30h
0x18002551a  lea     rax, [rbp+hKey]
0x18002551e  mov     [rbp+hKey], 0
0x180025526  mov     esi, 1
0x18002552b  mov     [rbp+Type], 0
0x180025532  mov     r9d, esi; samDesired
0x180025535  mov     [rbp+cbData], 0
0x18002553c  xor     r8d, r8d; ulOptions
0x18002553f  mov     [rsp+30h+phkResult], rax; phkResult
0x180025544  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\We"...
0x18002554b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025552  call    cs:__imp_RegOpenKeyExW
0x180025558  test    eax, eax
0x18002555a  jz      short loc_1800255A4
0x18002555c  mov     [rbp+hKey], 0
0x180025564  mov     cs:ServerNotFoundCacheLifeTimeInSec, 3Ch ; '<'
0x18002556e  mov     cs:AcceptOfficeAndTahoeServers, esi
0x180025574  mov     rcx, cs:WPP_GLOBAL_Control
0x18002557b  lea     rbx, WPP_GLOBAL_Control
0x180025582  cmp     rcx, rbx
0x180025585  jz      loc_1800259F1
0x18002558b  test    [rcx+1Ch], sil
0x18002558f  jz      loc_1800259F1
0x180025595  lea     edx, [rsi+2Ah]
0x180025598  lea     r8, WPP_3c901703a5983ce609c0997329a96280_Traceguids
0x18002559f  jmp     loc_1800259D6
0x1800255a4  mov     rcx, [rbp+hKey]; hKey
0x1800255a8  lea     rax, [rbp+cbData]
0x1800255ac  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800255b1  lea     r9, [rbp+Type]; lpType
0x1800255b5  lea     rax, ServerNotFoundCacheLifeTimeInSec
0x1800255bc  mov     r15d, 4
0x1800255c2  xor     r8d, r8d; lpReserved
0x1800255c5  mov     [rsp+30h+phkResult], rax; lpData
0x1800255ca  lea     rdx, ValueName; "ServerNotFoundCacheLifeTimeInSec"
0x1800255d1  mov     [rbp+cbData], r15d
0x1800255d5  call    cs:__imp_RegQueryValueExW
0x1800255db  lea     rdi, WPP_3c901703a5983ce609c0997329a96280_Traceguids
0x1800255e2  lea     rbx, WPP_GLOBAL_Control
0x1800255e9  test    eax, eax
0x1800255eb  jz      short loc_18002561C
0x1800255ed  mov     cs:ServerNotFoundCacheLifeTimeInSec, 3Ch ; '<'
0x1800255f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255fe  cmp     rcx, rbx
0x180025601  jz      short loc_18002561C
0x180025603  test    [rcx+1Ch], sil
0x180025607  jz      short loc_18002561C
0x180025609  mov     rcx, [rcx+10h]
0x18002560d  lea     edx, [r15+28h]
0x180025611  mov     r9d, eax
0x180025614  mov     r8, rdi
0x180025617  call    WPP_SF_d
0x18002561c  mov     rcx, [rbp+hKey]; hKey
0x180025620  lea     rax, [rbp+cbData]
0x180025624  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025629  lea     r9, [rbp+Type]; lpType
0x18002562d  lea     rax, AcceptOfficeAndTahoeServers
0x180025634  mov     [rbp+cbData], r15d
0x180025638  xor     r8d, r8d; lpReserved
0x18002563b  mov     [rsp+30h+phkResult], rax; lpData
0x180025640  lea     rdx, aAcceptofficean; "AcceptOfficeAndTahoeServers"
0x180025647  call    cs:__imp_RegQueryValueExW
0x18002564d  test    eax, eax
0x18002564f  jz      short loc_18002567D
0x180025651  mov     cs:AcceptOfficeAndTahoeServers, esi
0x180025657  mov     rcx, cs:WPP_GLOBAL_Control
0x18002565e  cmp     rcx, rbx
0x180025661  jz      short loc_18002567D
0x180025663  test    [rcx+1Ch], sil
0x180025667  jz      short loc_18002567D
0x180025669  mov     rcx, [rcx+10h]
0x18002566d  mov     edx, 2Dh ; '-'
0x180025672  mov     r9d, eax
0x180025675  mov     r8, rdi
0x180025678  call    WPP_SF_d
0x18002567d  mov     rcx, [rbp+hKey]; hKey
0x180025681  lea     rax, [rbp+cbData]
0x180025685  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002568a  lea     r9, [rbp+Type]; lpType
0x18002568e  lea     rax, DavSupportLockingOfFiles
0x180025695  mov     [rbp+cbData], r15d
0x180025699  xor     r8d, r8d; lpReserved
0x18002569c  mov     [rsp+30h+phkResult], rax; lpData
0x1800256a1  lea     rdx, aSupportlocking; "SupportLocking"
0x1800256a8  call    cs:__imp_RegQueryValueExW
0x1800256ae  test    eax, eax
0x1800256b0  jz      short loc_1800256DE
0x1800256b2  mov     cs:DavSupportLockingOfFiles, esi
0x1800256b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256bf  cmp     rcx, rbx
0x1800256c2  jz      short loc_1800256DE
0x1800256c4  test    [rcx+1Ch], sil
0x1800256c8  jz      short loc_1800256DE
0x1800256ca  mov     rcx, [rcx+10h]
0x1800256ce  mov     edx, 2Eh ; '.'
0x1800256d3  mov     r9d, eax
0x1800256d6  mov     r8, rdi
0x1800256d9  call    WPP_SF_d
0x1800256de  mov     rcx, [rbp+hKey]; hKey
0x1800256e2  lea     rax, [rbp+cbData]
0x1800256e6  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800256eb  lea     r9, [rbp+Type]; lpType
0x1800256ef  lea     rax, DavFileSizeLimitInBytes
0x1800256f6  mov     [rbp+cbData], r15d
0x1800256fa  xor     r8d, r8d; lpReserved
0x1800256fd  mov     [rsp+30h+phkResult], rax; lpData
0x180025702  lea     rdx, aFilesizelimiti; "FileSizeLimitInBytes"
0x180025709  call    cs:__imp_RegQueryValueExW
0x18002570f  test    eax, eax
0x180025711  jz      short loc_180025743
0x180025713  mov     cs:DavFileSizeLimitInBytes, 2FAF080h
0x18002571d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025724  cmp     rcx, rbx
0x180025727  jz      short loc_180025743
0x180025729  test    [rcx+1Ch], sil
0x18002572d  jz      short loc_180025743
0x18002572f  mov     rcx, [rcx+10h]
0x180025733  mov     edx, 2Fh ; '/'
0x180025738  mov     r9d, eax
0x18002573b  mov     r8, rdi
0x18002573e  call    WPP_SF_d
0x180025743  mov     rcx, [rbp+hKey]; hKey
0x180025747  lea     rax, [rbp+cbData]
0x18002574b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025750  lea     r9, [rbp+Type]; lpType
0x180025754  lea     rax, DavFileAttributesLimitInBytes
0x18002575b  mov     [rbp+cbData], r15d
0x18002575f  xor     r8d, r8d; lpReserved
0x180025762  mov     [rsp+30h+phkResult], rax; lpData
0x180025767  lea     rdx, aFileattributes; "FileAttributesLimitInBytes"
0x18002576e  call    cs:__imp_RegQueryValueExW
0x180025774  test    eax, eax
0x180025776  jz      short loc_1800257A8
0x180025778  mov     cs:DavFileAttributesLimitInBytes, 0F4240h
0x180025782  mov     rcx, cs:WPP_GLOBAL_Control
0x180025789  cmp     rcx, rbx
0x18002578c  jz      short loc_1800257A8
0x18002578e  test    [rcx+1Ch], sil
0x180025792  jz      short loc_1800257A8
0x180025794  mov     rcx, [rcx+10h]
0x180025798  mov     edx, 30h ; '0'
0x18002579d  mov     r9d, eax
0x1800257a0  mov     r8, rdi
0x1800257a3  call    WPP_SF_d
0x1800257a8  mov     rcx, [rbp+hKey]; hKey
0x1800257ac  lea     rax, [rbp+cbData]
0x1800257b0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800257b5  lea     r9, [rbp+Type]; lpType
0x1800257b9  lea     rax, BasicAuthLevel
0x1800257c0  mov     [rbp+cbData], r15d
0x1800257c4  xor     r8d, r8d; lpReserved
0x1800257c7  mov     [rsp+30h+phkResult], rax; lpData
0x1800257cc  lea     rdx, aBasicauthlevel; "BasicAuthLevel"
0x1800257d3  call    cs:__imp_RegQueryValueExW
0x1800257d9  test    eax, eax
0x1800257db  jz      short loc_180025809
0x1800257dd  mov     cs:BasicAuthLevel, esi
0x1800257e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257ea  cmp     rcx, rbx
0x1800257ed  jz      short loc_180025809
0x1800257ef  test    [rcx+1Ch], sil
0x1800257f3  jz      short loc_180025809
0x1800257f5  mov     rcx, [rcx+10h]
0x1800257f9  mov     edx, 31h ; '1'
0x1800257fe  mov     r9d, eax
0x180025801  mov     r8, rdi
0x180025804  call    WPP_SF_d
0x180025809  mov     rcx, [rbp+hKey]; hKey
0x18002580d  lea     rax, [rbp+cbData]
0x180025811  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025816  lea     r9, [rbp+Type]; lpType
0x18002581a  lea     rax, DavLocalServerTimeoutInSec
0x180025821  mov     [rbp+cbData], r15d
0x180025825  xor     r8d, r8d; lpReserved
0x180025828  mov     [rsp+30h+phkResult], rax; lpData
0x18002582d  lea     rdx, aLocalservertim; "LocalServerTimeoutInSec"
0x180025834  call    cs:__imp_RegQueryValueExW
0x18002583a  test    eax, eax
0x18002583c  jz      short loc_18002586E
0x18002583e  mov     cs:DavLocalServerTimeoutInSec, 0Fh
0x180025848  mov     rcx, cs:WPP_GLOBAL_Control
0x18002584f  cmp     rcx, rbx
0x180025852  jz      short loc_18002586E
0x180025854  test    [rcx+1Ch], sil
0x180025858  jz      short loc_18002586E
0x18002585a  mov     rcx, [rcx+10h]
0x18002585e  mov     edx, 32h ; '2'
0x180025863  mov     r9d, eax
0x180025866  mov     r8, rdi
0x180025869  call    WPP_SF_d
0x18002586e  mov     rcx, [rbp+hKey]; hKey
0x180025872  lea     rax, [rbp+cbData]
0x180025876  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002587b  lea     r9, [rbp+Type]; lpType
0x18002587f  lea     rax, DavInternetServerTimeoutInSec
0x180025886  mov     [rbp+cbData], r15d
0x18002588a  xor     r8d, r8d; lpReserved
0x18002588d  mov     [rsp+30h+phkResult], rax; lpData
0x180025892  lea     rdx, aInternetserver; "InternetServerTimeoutInSec"
0x180025899  call    cs:__imp_RegQueryValueExW
0x18002589f  test    eax, eax
0x1800258a1  jz      short loc_1800258D3
0x1800258a3  mov     cs:DavInternetServerTimeoutInSec, 1Eh
0x1800258ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258b4  cmp     rcx, rbx
0x1800258b7  jz      short loc_1800258D3
0x1800258b9  test    [rcx+1Ch], sil
0x1800258bd  jz      short loc_1800258D3
0x1800258bf  mov     rcx, [rcx+10h]
0x1800258c3  mov     edx, 33h ; '3'
0x1800258c8  mov     r9d, eax
0x1800258cb  mov     r8, rdi
0x1800258ce  call    WPP_SF_d
0x1800258d3  mov     rcx, [rbp+hKey]; hKey
0x1800258d7  lea     rax, [rbp+cbData]
0x1800258db  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800258e0  lea     r9, [rbp+Type]; lpType
0x1800258e4  lea     rax, DavSendReceiveTimeoutInSec
0x1800258eb  mov     [rbp+cbData], r15d
0x1800258ef  xor     r8d, r8d; lpReserved
0x1800258f2  mov     [rsp+30h+phkResult], rax; lpData
0x1800258f7  lea     rdx, aSendreceivetim; "SendReceiveTimeoutInSec"
0x1800258fe  call    cs:__imp_RegQueryValueExW
0x180025904  test    eax, eax
0x180025906  jz      short loc_180025938
0x180025908  mov     cs:DavSendReceiveTimeoutInSec, 1Eh
0x180025912  mov     rcx, cs:WPP_GLOBAL_Control
0x180025919  cmp     rcx, rbx
0x18002591c  jz      short loc_180025938
0x18002591e  test    [rcx+1Ch], sil
0x180025922  jz      short loc_180025938
0x180025924  mov     rcx, [rcx+10h]
0x180025928  mov     edx, 34h ; '4'
0x18002592d  mov     r9d, eax
0x180025930  mov     r8, rdi
0x180025933  call    WPP_SF_d
0x180025938  mov     rcx, [rbp+hKey]; hkey
0x18002593c  call    DavReadRegistryBypassServerNames
0x180025941  test    eax, eax
0x180025943  jz      short loc_180025976
0x180025945  mov     cs:pBypassServerNames, 0
0x180025950  mov     rcx, cs:WPP_GLOBAL_Control
0x180025957  cmp     rcx, rbx
0x18002595a  jz      short loc_180025976
0x18002595c  test    [rcx+1Ch], sil
0x180025960  jz      short loc_180025976
0x180025962  mov     rcx, [rcx+10h]
0x180025966  mov     edx, 35h ; '5'
0x18002596b  mov     r9d, eax
0x18002596e  mov     r8, rdi
0x180025971  call    WPP_SF_d
0x180025976  mov     rcx, [rbp+hKey]; hKey
0x18002597a  lea     rax, [rbp+cbData]
0x18002597e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025983  lea     r9, [rbp+Type]; lpType
0x180025987  lea     rax, DavAllowInvalidCertDate
0x18002598e  mov     cs:DavAllowSSL, sil
0x180025995  xor     r8d, r8d; lpReserved
0x180025998  mov     [rsp+30h+phkResult], rax; lpData
0x18002599d  lea     rdx, aAllowinvalidce; "AllowInvalidCertDate"
0x1800259a4  mov     [rbp+cbData], r15d
0x1800259a8  call    cs:__imp_RegQueryValueExW
0x1800259ae  test    eax, eax
0x1800259b0  jz      short loc_1800259E2
0x1800259b2  mov     cs:DavAllowInvalidCertDate, 0
0x1800259bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259c3  cmp     rcx, rbx
0x1800259c6  jz      short loc_1800259E2
0x1800259c8  test    [rcx+1Ch], sil
0x1800259cc  jz      short loc_1800259E2
0x1800259ce  mov     edx, 36h ; '6'
0x1800259d3  mov     r8, rdi
0x1800259d6  mov     rcx, [rcx+10h]
0x1800259da  mov     r9d, eax
0x1800259dd  call    WPP_SF_d
0x1800259e2  mov     rcx, [rbp+hKey]; hKey
0x1800259e6  test    rcx, rcx
0x1800259e9  jz      short loc_1800259F1
0x1800259eb  call    cs:__imp_RegCloseKey
0x1800259f1  add     rsp, 30h
0x1800259f5  pop     r15
0x1800259f7  pop     rdi
0x1800259f8  pop     rsi
0x1800259f9  pop     rbx
0x1800259fa  pop     rbp
0x1800259fb  retn
```
