# CRpcIOManagerClient::SetRpcSecuritySchannel(void *)

- ea: `0x18006e22c`
- end: `0x18006e730`
- name: `?SetRpcSecuritySchannel@CRpcIOManagerClient@@AEAAJPEAX@Z`
- size: `1284`
- prototype: `int(CRpcIOManagerClient *__hidden this, void *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e0cc`
- `0x18006e184`

## callees

- `0x180003cf0`
- `0x180006764`
- `0x18001d138`
- `0x18001d184`
- `0x180054968`
- `0x1800571f0`
- `0x180058be4`
- `0x18006e22c`
- `0x180070f24`
- `0x180081d9e`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e68d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e68d`
- `RPCRT4!RpcEpResolveBinding` at `0x18006e5c4`
- `RPCRT4!RpcEpResolveBinding` at `0x18006e5c4`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18006e560`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18006e560`
- `RPCRT4!RpcCertGeneratePrincipalNameW` at `0x18006e536`
- `RPCRT4!RpcCertGeneratePrincipalNameW` at `0x18006e536`
- `RPCRT4!RpcStringFreeW` at `0x18006e6ca`
- `RPCRT4!RpcStringFreeW` at `0x18006e6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e47b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e47b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e38c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e38c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e312`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e6ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e6ba`
- `CRYPT32!CertFreeCertificateContext` at `0x18006e69b`
- `CRYPT32!CertFreeCertificateContext` at `0x18006e69b`
- `CRYPT32!CertFindCertificateInStore` at `0x18006e46d`
- `CRYPT32!CertFindCertificateInStore` at `0x18006e46d`
- `CRYPT32!CertCloseStore` at `0x18006e6ab`
- `CRYPT32!CertCloseStore` at `0x18006e6ab`
- `CRYPT32!CertOpenStore` at `0x18006e41c`
- `CRYPT32!CertOpenStore` at `0x18006e41c`

## string_xrefs

- `0x18006e2c5`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e33b`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e3ca`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e4f8`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e57c`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e5e4`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e6e1`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006e2b6`: `CRpcIOManagerClient::SetRpcSecuritySchannel started`
- `0x18006e2cc`: `CRpcIOManagerClient::SetRpcSecuritySchannel`
- `0x18006e34c`: `CRpcIOManagerClient::SetRpcSecuritySchannel`
- `0x18006e3d1`: `CRpcIOManagerClient::SetRpcSecuritySchannel`
- `0x18006e503`: `CRpcIOManagerClient::SetRpcSecuritySchannel`
- `0x18006e5a0`: `CRpcIOManagerClient::SetRpcSecuritySchannel`
- `0x18006e608`: `CRpcIOManagerClient::SetRpcSecuritySchannel`
- `0x18006e6e8`: `CRpcIOManagerClient::SetRpcSecuritySchannel`
- `0x18006e329`: `CRpcIOManagerClient::SetRpcSecuritySchannel - Call to RegOpenKeyExW failed.`
- `0x18006e3a3`: `CRpcIOManagerClient::SetRpcSecuritySchannel - Call to RegQueryValueExW failed.`
- `0x18006e3b8`: `CRpcIOManagerClient::SetRpcSecuritySchannel - certificate thumbprint registry is of not REG_BINARY type.`
- `0x18006e43f`: `CRpcIOManagerClient::SetRpcSecuritySchannel - Call to CertOpenStore failed.`
- `0x18006e490`: `CRpcIOManagerClient::SetRpcSecuritySchannel - Call to CertFindCertificateInStore method failed.`
- `0x18006e4e6`: `CRpcIOManagerClient::SetRpcSecuritySchannel - Call to IsCertUseable failed.`
- `0x18006e6d5`: `CRpcIOManagerClient::SetRpcSecuritySchannel completed`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerClient::SetRpcSecuritySchannel(LPVOID *this, void *a2)
{
  HCERTSTORE v4; // rsi
  const CERT_CONTEXT *CertificateInStore; // r14
  _DWORD *v6; // rdi
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // r9
  LSTATUS v11; // eax
  signed int LastError; // eax
  signed int v13; // eax
  _QWORD *v14; // rax
  PCCERT_CONTEXT *v15; // rcx
  unsigned int v16; // eax
  RPC_STATUS v17; // edi
  void *v18; // r9
  LPDWORD lpcbData; // [rsp+28h] [rbp-71h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-71h]
  LPDWORD lpcbDatab; // [rsp+28h] [rbp-71h]
  DWORD Type; // [rsp+50h] [rbp-49h] BYREF
  RPC_WSTR pBuffer; // [rsp+58h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-39h] BYREF
  LPBYTE lpData[2]; // [rsp+68h] [rbp-31h] BYREF
  LPVOID pv[2]; // [rsp+78h] [rbp-21h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+88h] [rbp-11h] BYREF
  __int128 v29; // [rsp+98h] [rbp-1h] BYREF
  int v30; // [rsp+A8h] [rbp+Fh]

  v30 = 0;
  hKey = 0;
  Type = 0;
  v4 = 0;
  CertificateInStore = 0;
  v29 = 0;
  HIDWORD(lpData[0]) = 0;
  v6 = operator new(0x50u);
  memset_0(v6, 0, 0x50u);
  SecurityQOS.Capabilities = 5;
  SecurityQOS.IdentityTracking = 1;
  lpData[1] = (LPBYTE)&v29;
  SecurityQOS.ImpersonationType = 3;
  SecurityQOS.Version = 1;
  LODWORD(lpData[0]) = 20;
  TraceStringInline(
    1,
    3,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
    862,
    L"CRpcIOManagerClient::SetRpcSecuritySchannel",
    0,
    L"CRpcIOManagerClient::SetRpcSecuritySchannel started");
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MSDTC", 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v9 = L"CRpcIOManagerClient::SetRpcSecuritySchannel - Call to RegOpenKeyExW failed.";
    v10 = 873;
LABEL_5:
    LODWORD(lpcbData) = v8;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      v10,
      L"CRpcIOManagerClient::SetRpcSecuritySchannel",
      lpcbData,
      v9);
    goto LABEL_27;
  }
  v11 = RegQueryValueExW(hKey, L"ClientCertThumbprint", 0, &Type, lpData[1], (LPDWORD)lpData);
  v8 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    v9 = L"CRpcIOManagerClient::SetRpcSecuritySchannel - Call to RegQueryValueExW failed.";
    v10 = 888;
    goto LABEL_5;
  }
  if ( Type != 3 )
  {
    v8 = -2147467259;
    LODWORD(lpcbData) = -2147467259;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      896,
      L"CRpcIOManagerClient::SetRpcSecuritySchannel",
      lpcbData,
      L"CRpcIOManagerClient::SetRpcSecuritySchannel - certificate thumbprint registry is of not REG_BINARY type.");
LABEL_28:
    *(_OWORD *)pv = 0;
    MakeStringW((unsigned __int16 **)pv, L"%X", v8);
    pv[1] = this[2];
    LODWORD(lpcbDataa) = 0;
    DtcWriteToEventLoggerExW(2u, 3u, 0x8000130F, v18, 2u, (size_t)lpcbDataa, (const unsigned __int16 **)pv, 0, 1);
    CoTaskMemFree(pv[0]);
    if ( CertificateInStore )
      CertFreeCertificateContext(CertificateInStore);
LABEL_30:
    if ( !v4 )
      goto LABEL_32;
    goto LABEL_31;
  }
  v4 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, L"My");
  if ( !v4 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = L"CRpcIOManagerClient::SetRpcSecuritySchannel - Call to CertOpenStore failed.";
    v10 = 910;
    goto LABEL_5;
  }
  CertificateInStore = CertFindCertificateInStore(v4, 0x10001u, 0, 0x10000u, lpData, 0);
  if ( !CertificateInStore )
  {
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    v9 = L"CRpcIOManagerClient::SetRpcSecuritySchannel - Call to CertFindCertificateInStore method failed.";
    v10 = 925;
    goto LABEL_5;
  }
  v8 = 0;
  v14 = operator new[](8u);
  *((_QWORD *)v6 + 1) = v14;
  *v6 = 4;
  v6[1] = 1;
  *v14 = CertificateInStore;
  v15 = (PCCERT_CONTEXT *)*((_QWORD *)v6 + 1);
  v6[18] = 28;
  *(_QWORD *)(v6 + 15) = 0;
  v6[14] = 0;
  *((_QWORD *)v6 + 2) = v4;
  v16 = IsCertUseable(*v15);
  if ( !v16 )
  {
    pBuffer = 0;
    RpcCertGeneratePrincipalNameW(**((PCCERT_CONTEXT **)v6 + 1), 1u, &pBuffer);
    v17 = RpcBindingSetAuthInfoExW(a2, pBuffer, 6u, 0xEu, v6, 0, &SecurityQOS);
    if ( v17 )
    {
      LODWORD(lpcbDatab) = v17;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
        964,
        L"CRpcIOManagerClient::SetRpcSecuritySchannel",
        lpcbDatab,
        L"[Remote:%s %.8s] Call to RpcBindingSetAuthInfoEx failed",
        this[2],
        this[3]);
    }
    else
    {
      v17 = RpcEpResolveBinding(a2, qword_18008BBE0);
      if ( !v17 )
        goto LABEL_31;
      LODWORD(lpcbDatab) = v17;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
        975,
        L"CRpcIOManagerClient::SetRpcSecuritySchannel",
        lpcbDatab,
        L"[Remote:%s %.8s] Call to RpcEpResolveBinding failed",
        this[2],
        this[3]);
      TraceRpcEEInfo();
    }
    v8 = RpcStatusToHresult(v17);
LABEL_27:
    if ( (v8 & 0x80000000) == 0 )
      goto LABEL_30;
    goto LABEL_28;
  }
  LODWORD(lpcbData) = v16;
  TraceStringInline(
    1,
    1,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
    943,
    L"CRpcIOManagerClient::SetRpcSecuritySchannel",
    lpcbData,
    L"CRpcIOManagerClient::SetRpcSecuritySchannel - Call to IsCertUseable failed.");
LABEL_31:
  CertCloseStore(v4, 0);
LABEL_32:
  if ( hKey )
    RegCloseKey(hKey);
  if ( pBuffer )
    RpcStringFreeW(&pBuffer);
  TraceStringInline(
    1,
    3,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
    1033,
    L"CRpcIOManagerClient::SetRpcSecuritySchannel",
    0,
    L"CRpcIOManagerClient::SetRpcSecuritySchannel completed");
  return v8;
}

```

## disassembly

```asm
0x18006e22c  mov     [rsp-8+arg_10], rbx
0x18006e231  push    rbp
0x18006e232  push    rsi
0x18006e233  push    rdi
0x18006e234  push    r12
0x18006e236  push    r13
0x18006e238  push    r14
0x18006e23a  push    r15
0x18006e23c  lea     rbp, [rsp-27h]
0x18006e241  sub     rsp, 0C0h
0x18006e248  mov     rax, cs:__security_cookie
0x18006e24f  xor     rax, rsp
0x18006e252  mov     [rbp+57h+var_40], rax
0x18006e256  xor     r13d, r13d
0x18006e259  xor     eax, eax
0x18006e25b  xorps   xmm0, xmm0
0x18006e25e  mov     [rbp+57h+var_48], eax
0x18006e261  mov     r15, rcx
0x18006e264  mov     [rbp+57h+hKey], r13
0x18006e268  xorps   xmm1, xmm1
0x18006e26b  mov     [rbp+57h+Type], r13d
0x18006e26f  lea     ebx, [rax+50h]
0x18006e272  mov     r12, rdx
0x18006e275  mov     ecx, ebx; Size
0x18006e277  mov     esi, r13d
0x18006e27a  movups  xmmword ptr [rbp+57h+var_68.Version], xmm0
0x18006e27e  mov     r14d, r13d
0x18006e281  movups  [rbp+57h+var_58], xmm1
0x18006e285  movups  xmmword ptr [rbp+57h+lpData], xmm0
0x18006e289  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e28e  mov     r8d, ebx; Size
0x18006e291  xor     edx, edx; Val
0x18006e293  mov     rcx, rax; void *
0x18006e296  mov     rdi, rax
0x18006e299  call    memset_0
0x18006e29e  lea     ecx, [rbx-4Fh]
0x18006e2a1  mov     [rbp+57h+var_68.Capabilities], 5
0x18006e2a8  lea     rax, [rbp+57h+var_58]
0x18006e2ac  mov     [rbp+57h+var_68.IdentityTracking], ecx
0x18006e2af  mov     [rbp+57h+lpData+8], rax
0x18006e2b3  lea     edx, [rbx-4Dh]
0x18006e2b6  lea     rax, aCrpciomanagerc_3; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e2bd  mov     [rbp+57h+var_68.ImpersonationType], edx
0x18006e2c0  mov     [rsp+0F0h+SecurityQOS], rax
0x18006e2c5  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e2cc  lea     rax, aCrpciomanagerc_12; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e2d3  mov     [rsp+0F0h+lpcbData], r13
0x18006e2d8  mov     r9d, 35Eh
0x18006e2de  mov     [rsp+0F0h+phkResult], rax
0x18006e2e3  mov     [rbp+57h+var_68.Version], ecx
0x18006e2e6  mov     dword ptr [rbp+57h+lpData], 14h
0x18006e2ed  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e2f2  lea     rax, [rbp+57h+hKey]
0x18006e2f6  mov     r9d, 20019h; samDesired
0x18006e2fc  xor     r8d, r8d; ulOptions
0x18006e2ff  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18006e304  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x18006e30b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e312  call    cs:__imp_RegOpenKeyExW
0x18006e318  mov     ebx, eax
0x18006e31a  test    eax, eax
0x18006e31c  jz      short loc_18006E368
0x18006e31e  jle     short loc_18006E329
0x18006e320  movzx   ebx, ax
0x18006e323  or      ebx, 80070000h
0x18006e329  lea     rax, aCrpciomanagerc; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e330  mov     r9d, 369h
0x18006e336  mov     [rsp+0F0h+SecurityQOS], rax
0x18006e33b  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e342  mov     r12d, 1
0x18006e348  mov     dword ptr [rsp+0F0h+lpcbData], ebx
0x18006e34c  lea     rax, aCrpciomanagerc_12; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e353  mov     edx, r12d
0x18006e356  mov     ecx, r12d
0x18006e359  mov     [rsp+0F0h+phkResult], rax
0x18006e35e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e363  jmp     loc_18006E62E
0x18006e368  mov     rcx, [rbp+57h+hKey]; hKey
0x18006e36c  lea     rax, [rbp+57h+lpData]
0x18006e370  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18006e375  lea     r9, [rbp+57h+Type]; lpType
0x18006e379  mov     rax, [rbp+57h+lpData+8]
0x18006e37d  lea     rdx, aClientcertthum; "ClientCertThumbprint"
0x18006e384  xor     r8d, r8d; lpReserved
0x18006e387  mov     [rsp+0F0h+phkResult], rax; lpData
0x18006e38c  call    cs:__imp_RegQueryValueExW
0x18006e392  mov     ebx, eax
0x18006e394  test    eax, eax
0x18006e396  jz      short loc_18006E3B2
0x18006e398  jle     short loc_18006E3A3
0x18006e39a  movzx   ebx, ax
0x18006e39d  or      ebx, 80070000h
0x18006e3a3  lea     rax, aCrpciomanagerc_4; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e3aa  mov     r9d, 378h
0x18006e3b0  jmp     short loc_18006E336
0x18006e3b2  cmp     [rbp+57h+Type], 3
0x18006e3b6  jz      short loc_18006E3FC
0x18006e3b8  lea     rax, aCrpciomanagerc_15; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e3bf  mov     r12d, 1
0x18006e3c5  mov     [rsp+0F0h+SecurityQOS], rax
0x18006e3ca  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e3d1  lea     rax, aCrpciomanagerc_12; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e3d8  mov     ebx, 80004005h
0x18006e3dd  mov     dword ptr [rsp+0F0h+lpcbData], ebx
0x18006e3e1  mov     r9d, 380h
0x18006e3e7  mov     edx, r12d
0x18006e3ea  mov     [rsp+0F0h+phkResult], rax
0x18006e3ef  mov     ecx, r12d
0x18006e3f2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e3f7  jmp     loc_18006E632
0x18006e3fc  xor     r8d, r8d; hCryptProv
0x18006e3ff  lea     rax, aMy; "My"
0x18006e406  mov     ebx, 10001h
0x18006e40b  mov     [rsp+0F0h+phkResult], rax; pvPara
0x18006e410  mov     r9d, 28000h; dwFlags
0x18006e416  mov     edx, ebx; dwEncodingType
0x18006e418  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18006e41c  call    cs:__imp_CertOpenStore
0x18006e422  mov     rsi, rax
0x18006e425  test    rax, rax
0x18006e428  jnz     short loc_18006E451
0x18006e42a  call    cs:__imp_GetLastError
0x18006e430  mov     ebx, eax
0x18006e432  test    eax, eax
0x18006e434  jle     short loc_18006E43F
0x18006e436  movzx   ebx, ax
0x18006e439  or      ebx, 80070000h
0x18006e43f  lea     rax, aCrpciomanagerc_13; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e446  mov     r9d, 38Eh
0x18006e44c  jmp     loc_18006E336
0x18006e451  lea     rax, [rbp+57h+lpData]
0x18006e455  mov     [rsp+0F0h+lpcbData], r13; pPrevCertContext
0x18006e45a  mov     r9d, 10000h; dwFindType
0x18006e460  mov     [rsp+0F0h+phkResult], rax; pvFindPara
0x18006e465  xor     r8d, r8d; dwFindFlags
0x18006e468  mov     edx, ebx; dwCertEncodingType
0x18006e46a  mov     rcx, rsi; hCertStore
0x18006e46d  call    cs:__imp_CertFindCertificateInStore
0x18006e473  mov     r14, rax
0x18006e476  test    rax, rax
0x18006e479  jnz     short loc_18006E4A2
0x18006e47b  call    cs:__imp_GetLastError
0x18006e481  mov     ebx, eax
0x18006e483  test    eax, eax
0x18006e485  jle     short loc_18006E490
0x18006e487  movzx   ebx, ax
0x18006e48a  or      ebx, 80070000h
0x18006e490  lea     rax, aCrpciomanagerc_7; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e497  mov     r9d, 39Dh
0x18006e49d  jmp     loc_18006E336
0x18006e4a2  mov     ecx, 8; unsigned __int64
0x18006e4a7  mov     ebx, r13d
0x18006e4aa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006e4af  mov     [rdi+8], rax
0x18006e4b3  mov     dword ptr [rdi], 4
0x18006e4b9  mov     dword ptr [rdi+4], 1
0x18006e4c0  mov     [rax], r14
0x18006e4c3  mov     rcx, [rdi+8]
0x18006e4c7  mov     dword ptr [rdi+48h], 1Ch
0x18006e4ce  mov     [rdi+3Ch], r13
0x18006e4d2  mov     [rdi+38h], r13d
0x18006e4d6  mov     [rdi+10h], rsi
0x18006e4da  mov     rcx, [rcx]; pCertContext
0x18006e4dd  call    ?IsCertUseable@@YAKPEBU_CERT_CONTEXT@@@Z; IsCertUseable(_CERT_CONTEXT const *)
0x18006e4e2  test    eax, eax
0x18006e4e4  jz      short loc_18006E522
0x18006e4e6  lea     rcx, aCrpciomanagerc_5; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e4ed  mov     r9d, 3AFh
0x18006e4f3  mov     [rsp+0F0h+SecurityQOS], rcx
0x18006e4f8  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e4ff  mov     dword ptr [rsp+0F0h+lpcbData], eax
0x18006e503  lea     rax, aCrpciomanagerc_12; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e50a  mov     [rsp+0F0h+phkResult], rax
0x18006e50f  mov     eax, 1
0x18006e514  mov     edx, eax
0x18006e516  mov     ecx, eax
0x18006e518  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e51d  jmp     loc_18006E6A6
0x18006e522  mov     [rbp+57h+pBuffer], r13
0x18006e526  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x18006e52a  mov     rcx, [rdi+8]
0x18006e52e  mov     edx, 1; Flags
0x18006e533  mov     rcx, [rcx]; Context
0x18006e536  call    cs:__imp_RpcCertGeneratePrincipalNameW
0x18006e53c  mov     rdx, [rbp+57h+pBuffer]; ServerPrincName
0x18006e540  lea     rax, [rbp+57h+var_68]
0x18006e544  mov     [rsp+0F0h+SecurityQOS], rax; SecurityQOS
0x18006e549  mov     r9d, 0Eh; AuthnSvc
0x18006e54f  mov     dword ptr [rsp+0F0h+lpcbData], r13d; AuthzSvc
0x18006e554  mov     rcx, r12; Binding
0x18006e557  mov     [rsp+0F0h+phkResult], rdi; AuthIdentity
0x18006e55c  lea     r8d, [r9-8]; AuthnLevel
0x18006e560  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18006e566  mov     edi, eax
0x18006e568  test    eax, eax
0x18006e56a  jz      short loc_18006E5BA
0x18006e56c  mov     rcx, [r15+18h]
0x18006e570  lea     rax, aRemoteS8sCallT_0; "[Remote:%s %.8s] Call to RpcBindingSetA"...
0x18006e577  mov     qword ptr [rsp+0F0h+var_B0], rcx
0x18006e57c  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e583  mov     rcx, [r15+10h]
0x18006e587  mov     r12d, 1
0x18006e58d  mov     [rsp+0F0h+Src], rcx
0x18006e592  mov     r9d, 3C4h
0x18006e598  mov     [rsp+0F0h+SecurityQOS], rax
0x18006e59d  mov     edx, r12d
0x18006e5a0  lea     rax, aCrpciomanagerc_12; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e5a7  mov     dword ptr [rsp+0F0h+lpcbData], edi
0x18006e5ab  mov     ecx, r12d
0x18006e5ae  mov     [rsp+0F0h+phkResult], rax
0x18006e5b3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e5b8  jmp     short loc_18006E625
0x18006e5ba  lea     rdx, qword_18008BBE0; IfSpec
0x18006e5c1  mov     rcx, r12; Binding
0x18006e5c4  call    cs:__imp_RpcEpResolveBinding
0x18006e5ca  mov     edi, eax
0x18006e5cc  test    eax, eax
0x18006e5ce  jz      loc_18006E6A6
0x18006e5d4  mov     rcx, [r15+18h]
0x18006e5d8  lea     rax, aRemoteS8sCallT_3; "[Remote:%s %.8s] Call to RpcEpResolveBi"...
0x18006e5df  mov     qword ptr [rsp+0F0h+var_B0], rcx
0x18006e5e4  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e5eb  mov     rcx, [r15+10h]
0x18006e5ef  mov     r12d, 1
0x18006e5f5  mov     [rsp+0F0h+Src], rcx
0x18006e5fa  mov     r9d, 3CFh
0x18006e600  mov     [rsp+0F0h+SecurityQOS], rax
0x18006e605  mov     edx, r12d
0x18006e608  lea     rax, aCrpciomanagerc_12; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e60f  mov     dword ptr [rsp+0F0h+lpcbData], edi
0x18006e613  mov     ecx, r12d
0x18006e616  mov     [rsp+0F0h+phkResult], rax
0x18006e61b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e620  call    ?TraceRpcEEInfo@@YAXXZ; TraceRpcEEInfo(void)
0x18006e625  mov     ecx, edi; int
0x18006e627  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18006e62c  mov     ebx, eax
0x18006e62e  test    ebx, ebx
0x18006e630  jns     short loc_18006E6A1
0x18006e632  xorps   xmm0, xmm0
0x18006e635  lea     rdx, asc_1800B060C; "%X"
0x18006e63c  mov     r8d, ebx
0x18006e63f  lea     rcx, [rbp+57h+pv]; unsigned __int16 **
0x18006e643  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18006e647  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18006e64c  mov     rax, [r15+10h]
0x18006e650  mov     edx, 3; unsigned __int16
0x18006e655  mov     [rsp+0F0h+var_B0], r12d; int
0x18006e65a  mov     [rsp+0F0h+Src], r13; Src
0x18006e65f  mov     [rbp+57h+pv+8], rax
0x18006e663  lea     rax, [rbp+57h+pv]
0x18006e667  lea     r8d, [rdx-1]
0x18006e66b  mov     [rsp+0F0h+SecurityQOS], rax; unsigned __int16 **
0x18006e670  mov     ecx, r8d; unsigned __int16
0x18006e673  mov     dword ptr [rsp+0F0h+lpcbData], r13d; Size
0x18006e678  mov     word ptr [rsp+0F0h+phkResult], r8w; unsigned __int16
0x18006e67e  mov     r8d, 8000130Fh; unsigned int
0x18006e684  call    ?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x18006e689  mov     rcx, [rbp+57h+pv]; pv
0x18006e68d  call    cs:__imp_CoTaskMemFree
0x18006e693  test    r14, r14
0x18006e696  jz      short loc_18006E6A1
0x18006e698  mov     rcx, r14; pCertContext
0x18006e69b  call    cs:__imp_CertFreeCertificateContext
0x18006e6a1  test    rsi, rsi
0x18006e6a4  jz      short loc_18006E6B1
0x18006e6a6  xor     edx, edx; dwFlags
0x18006e6a8  mov     rcx, rsi; hCertStore
0x18006e6ab  call    cs:__imp_CertCloseStore
0x18006e6b1  mov     rcx, [rbp+57h+hKey]; hKey
0x18006e6b5  test    rcx, rcx
0x18006e6b8  jz      short loc_18006E6C0
0x18006e6ba  call    cs:__imp_RegCloseKey
0x18006e6c0  cmp     [rbp+57h+pBuffer], r13
0x18006e6c4  jz      short loc_18006E6D0
0x18006e6c6  lea     rcx, [rbp+57h+pBuffer]; String
0x18006e6ca  call    cs:__imp_RpcStringFreeW
0x18006e6d0  mov     edx, 3
0x18006e6d5  lea     rax, aCrpciomanagerc_1; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e6dc  mov     [rsp+0F0h+SecurityQOS], rax
0x18006e6e1  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006e6e8  lea     rax, aCrpciomanagerc_12; "CRpcIOManagerClient::SetRpcSecurityScha"...
0x18006e6ef  mov     [rsp+0F0h+lpcbData], r13
0x18006e6f4  mov     r9d, 409h
0x18006e6fa  mov     [rsp+0F0h+phkResult], rax
0x18006e6ff  lea     ecx, [rdx-2]
0x18006e702  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006e707  mov     eax, ebx
0x18006e709  mov     rcx, [rbp+57h+var_40]
0x18006e70d  xor     rcx, rsp; StackCookie
0x18006e710  call    __security_check_cookie
0x18006e715  mov     rbx, [rsp+0F0h+arg_10]
0x18006e71d  add     rsp, 0C0h
0x18006e724  pop     r15
0x18006e726  pop     r14
0x18006e728  pop     r13
0x18006e72a  pop     r12
0x18006e72c  pop     rdi
0x18006e72d  pop     rsi
0x18006e72e  pop     rbp
  ... truncated ...
```
