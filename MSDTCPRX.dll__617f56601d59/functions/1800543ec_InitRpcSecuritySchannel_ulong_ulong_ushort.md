# InitRpcSecuritySchannel(ulong,ulong,ushort *)

- ea: `0x1800543ec`
- end: `0x1800547dd`
- name: `?InitRpcSecuritySchannel@@YAJKKPEAG@Z`
- size: `1009`
- prototype: `int(unsigned int, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054d28`

## callees

- `0x180003cf0`
- `0x18001d138`
- `0x18001d184`
- `0x1800543ec`
- `0x180054968`
- `0x1800572f8`
- `0x180081d9e`
- `0x180081dd0`

## import_xrefs

- `RPCRT4!RpcServerListen` at `0x1800546f2`
- `RPCRT4!RpcServerListen` at `0x1800546f2`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800546c9`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800546c9`
- `RPCRT4!RpcCertGeneratePrincipalNameW` at `0x180054675`
- `RPCRT4!RpcCertGeneratePrincipalNameW` at `0x180054675`
- `RPCRT4!RpcStringFreeW` at `0x180054785`
- `RPCRT4!RpcStringFreeW` at `0x180054785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005454a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005459e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005454a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005459e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800544f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800544f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800544a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800544a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054765`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054765`
- `CRYPT32!CertFreeCertificateContext` at `0x18005474f`
- `CRYPT32!CertFreeCertificateContext` at `0x18005474f`
- `CRYPT32!CertFindCertificateInStore` at `0x180054590`
- `CRYPT32!CertFindCertificateInStore` at `0x180054590`
- `CRYPT32!CertCloseStore` at `0x180054775`
- `CRYPT32!CertCloseStore` at `0x180054775`
- `CRYPT32!CertOpenStore` at `0x18005453c`
- `CRYPT32!CertOpenStore` at `0x18005453c`

## string_xrefs

- `0x180054427`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x18005464d`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x18005467f`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054717`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x18005479d`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x18005443e`: `InitRpcSecuritySchannel Started`
- `0x180054451`: `InitRpcSecuritySchannel`
- `0x180054642`: `InitRpcSecuritySchannel`
- `0x1800546a5`: `InitRpcSecuritySchannel`
- `0x180054720`: `InitRpcSecuritySchannel`
- `0x180054755`: `InitRpcSecuritySchannel`
- `0x1800544ba`: `InitRpcSecuritySchannel - Call to RegOpenKeyExW failed.`
- `0x18005450a`: `InitRpcSecuritySchannel - Call to RegQueryValueExW failed.`
- `0x180054562`: `InitRpcSecuritySchannel - Call to CertOpenStore failed.`
- `0x1800545b6`: `InitRpcSecuritySchannel - Call to CertFindCertificateInStore failed.`
- `0x180054630`: `InitRpcSecuritySchannel - Call to IsServerCertUseable failed.`
- `0x180054691`: `InitRpcSecuritySchannel - Calling RpcServerRegisterAuthInfo with %s as SPN`
- `0x1800546e0`: `InitRpcSecuritySchannel - Call to RpcServerRegisterAuthInfo failed.`
- `0x180054710`: `InitRpcSecuritySchannel - Call to RpcServerListen failed.`
- `0x18005478b`: `InitRpcSecuritySchannel Completed`

## pseudocode

```c
__int64 __fastcall InitRpcSecuritySchannel(__int64 a1, unsigned int a2, unsigned __int16 *a3)
{
  HCERTSTORE v4; // rsi
  const CERT_CONTEXT *CertificateInStore; // r14
  LSTATUS v6; // eax
  signed int v7; // ebx
  const wchar_t *v8; // r10
  __int64 v9; // r9
  LSTATUS v10; // eax
  signed int v11; // eax
  signed int LastError; // eax
  _DWORD *v13; // rdi
  _QWORD *v14; // rax
  PCCERT_CONTEXT *v15; // rcx
  unsigned int v16; // eax
  RPC_STATUS v17; // eax
  signed int v18; // eax
  RPC_STATUS v19; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-51h]
  RPC_WSTR pBuffer; // [rsp+40h] [rbp-39h] BYREF
  DWORD Type; // [rsp+48h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-21h] BYREF
  LPBYTE lpData; // [rsp+60h] [rbp-19h]
  __int128 v27; // [rsp+68h] [rbp-11h] BYREF
  int v28; // [rsp+78h] [rbp-1h]

  *(_QWORD *)cbData = 20;
  hKey = 0;
  v28 = 0;
  Type = 0;
  lpData = (LPBYTE)&v27;
  v4 = 0;
  v27 = 0;
  CertificateInStore = 0;
  TraceStringInline(
    1,
    3,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
    447,
    L"InitRpcSecuritySchannel",
    0,
    L"InitRpcSecuritySchannel Started");
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MSDTC", 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v8 = L"InitRpcSecuritySchannel - Call to RegOpenKeyExW failed.";
    v9 = 459;
  }
  else
  {
    v10 = RegQueryValueExW(hKey, L"ServerCertThumbprint", 0, &Type, lpData, cbData);
    v7 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      v8 = L"InitRpcSecuritySchannel - Call to RegQueryValueExW failed.";
      v9 = 475;
    }
    else
    {
      v4 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, L"My");
      if ( v4 )
      {
        CertificateInStore = CertFindCertificateInStore(v4, 0x10001u, 0, 0x10000u, cbData, 0);
        if ( CertificateInStore )
        {
          v7 = 0;
          v13 = operator new(0x50u);
          memset_0(v13, 0, 0x50u);
          v14 = operator new[](8u);
          *((_QWORD *)v13 + 1) = v14;
          *v13 = 4;
          v13[1] = 1;
          *v14 = CertificateInStore;
          v15 = (PCCERT_CONTEXT *)*((_QWORD *)v13 + 1);
          v13[18] = 2;
          *(_QWORD *)(v13 + 15) = 0;
          v13[14] = 0;
          *((_QWORD *)v13 + 2) = v4;
          v16 = IsServerCertUseable(*v15);
          if ( v16 )
          {
            LODWORD(lpcbData) = v16;
            TraceStringInline(
              1,
              1,
              L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
              525,
              L"InitRpcSecuritySchannel",
              lpcbData,
              L"InitRpcSecuritySchannel - Call to IsServerCertUseable failed.");
            goto LABEL_28;
          }
          pBuffer = 0;
          RpcCertGeneratePrincipalNameW(**((PCCERT_CONTEXT **)v13 + 1), 1u, &pBuffer);
          TraceStringInline(
            1,
            3,
            L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
            535,
            L"InitRpcSecuritySchannel",
            0,
            L"InitRpcSecuritySchannel - Calling RpcServerRegisterAuthInfo with %s as SPN",
            pBuffer);
          v17 = RpcServerRegisterAuthInfoW(pBuffer, 0xEu, 0, v13);
          if ( v17 )
          {
            v18 = RpcStatusToHresult(v17);
            v9 = 545;
            v8 = L"InitRpcSecuritySchannel - Call to RpcServerRegisterAuthInfo failed.";
          }
          else
          {
            v19 = RpcServerListen(1u, a2, 1u);
            if ( !v19 || v19 == 1713 )
              goto LABEL_28;
            v18 = RpcStatusToHresult(v19);
            v9 = 560;
            v8 = L"InitRpcSecuritySchannel - Call to RpcServerListen failed.";
          }
          v7 = v18;
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          v8 = L"InitRpcSecuritySchannel - Call to CertFindCertificateInStore failed.";
          v9 = 504;
        }
      }
      else
      {
        v11 = GetLastError();
        v7 = v11;
        if ( v11 > 0 )
          v7 = (unsigned __int16)v11 | 0x80070000;
        v8 = L"InitRpcSecuritySchannel - Call to CertOpenStore failed.";
        v9 = 489;
      }
    }
  }
  LODWORD(lpcbData) = v7;
  TraceStringInline(
    1,
    1,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
    v9,
    L"InitRpcSecuritySchannel",
    lpcbData,
    v8);
  if ( v7 < 0 && CertificateInStore )
    CertFreeCertificateContext(CertificateInStore);
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    CertCloseStore(v4, 0);
  if ( pBuffer )
    RpcStringFreeW(&pBuffer);
  TraceStringInline(
    1,
    3,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
    598,
    L"InitRpcSecuritySchannel",
    0,
    L"InitRpcSecuritySchannel Completed");
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800543ec  push    rbp
0x1800543ee  push    rbx
0x1800543ef  push    rsi
0x1800543f0  push    rdi
0x1800543f1  push    r12
0x1800543f3  push    r13
0x1800543f5  push    r14
0x1800543f7  push    r15
0x1800543f9  lea     rbp, [rsp-1Fh]
0x1800543fe  sub     rsp, 98h
0x180054405  mov     rax, cs:__security_cookie
0x18005440c  xor     rax, rsp
0x18005440f  mov     [rbp+57h+var_50], rax
0x180054413  xor     r13d, r13d
0x180054416  mov     qword ptr [rbp+57h+cbData], 14h
0x18005441e  xor     eax, eax
0x180054420  mov     [rbp+57h+hKey], r13
0x180054424  mov     [rbp+57h+var_58], eax
0x180054427  lea     rdi, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x18005442e  lea     rax, [rbp+57h+var_68]
0x180054432  mov     [rbp+57h+Type], r13d
0x180054436  mov     [rbp+57h+lpData], rax
0x18005443a  lea     r12d, [r13+1]
0x18005443e  lea     rax, aInitrpcsecurit_1; "InitRpcSecuritySchannel Started"
0x180054445  mov     r15d, edx
0x180054448  mov     [rsp+0D0h+var_A0], rax
0x18005444d  lea     edx, [r13+3]
0x180054451  lea     rax, aInitrpcsecurit_7; "InitRpcSecuritySchannel"
0x180054458  mov     [rsp+0D0h+lpcbData], r13
0x18005445d  xorps   xmm0, xmm0
0x180054460  mov     [rsp+0D0h+phkResult], rax
0x180054465  mov     r9d, 1BFh
0x18005446b  mov     r8, rdi
0x18005446e  mov     ecx, r12d
0x180054471  mov     esi, r13d
0x180054474  movups  [rbp+57h+var_68], xmm0
0x180054478  mov     r14d, r13d
0x18005447b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054480  lea     rax, [rbp+57h+hKey]
0x180054484  mov     r9d, 20019h; samDesired
0x18005448a  xor     r8d, r8d; ulOptions
0x18005448d  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180054492  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x180054499  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800544a0  call    cs:__imp_RegOpenKeyExW
0x1800544a6  mov     ebx, eax
0x1800544a8  test    eax, eax
0x1800544aa  jz      short loc_1800544CC
0x1800544ac  jle     short loc_1800544B7
0x1800544ae  movzx   ebx, ax
0x1800544b1  or      ebx, 80070000h
0x1800544b7  mov     r8, rdi
0x1800544ba  lea     r10, aInitrpcsecurit_5; "InitRpcSecuritySchannel - Call to RegOp"...
0x1800544c1  mov     r9d, 1CBh
0x1800544c7  jmp     loc_180054720
0x1800544cc  mov     rcx, [rbp+57h+hKey]; hKey
0x1800544d0  lea     rax, [rbp+57h+cbData]
0x1800544d4  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800544d9  lea     r9, [rbp+57h+Type]; lpType
0x1800544dd  mov     rax, [rbp+57h+lpData]
0x1800544e1  lea     rdx, aServercertthum; "ServerCertThumbprint"
0x1800544e8  xor     r8d, r8d; lpReserved
0x1800544eb  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800544f0  call    cs:__imp_RegQueryValueExW
0x1800544f6  mov     ebx, eax
0x1800544f8  test    eax, eax
0x1800544fa  jz      short loc_18005451C
0x1800544fc  jle     short loc_180054507
0x1800544fe  movzx   ebx, ax
0x180054501  or      ebx, 80070000h
0x180054507  mov     r8, rdi
0x18005450a  lea     r10, aInitrpcsecurit_0; "InitRpcSecuritySchannel - Call to RegQu"...
0x180054511  mov     r9d, 1DBh
0x180054517  jmp     loc_180054720
0x18005451c  xor     r8d, r8d; hCryptProv
0x18005451f  lea     rax, aMy; "My"
0x180054526  mov     ebx, 10001h
0x18005452b  mov     [rsp+0D0h+phkResult], rax; pvPara
0x180054530  mov     r9d, 28000h; dwFlags
0x180054536  mov     edx, ebx; dwEncodingType
0x180054538  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18005453c  call    cs:__imp_CertOpenStore
0x180054542  mov     rsi, rax
0x180054545  test    rax, rax
0x180054548  jnz     short loc_180054574
0x18005454a  call    cs:__imp_GetLastError
0x180054550  mov     ebx, eax
0x180054552  test    eax, eax
0x180054554  jle     short loc_18005455F
0x180054556  movzx   ebx, ax
0x180054559  or      ebx, 80070000h
0x18005455f  mov     r8, rdi
0x180054562  lea     r10, aInitrpcsecurit_2; "InitRpcSecuritySchannel - Call to CertO"...
0x180054569  mov     r9d, 1E9h
0x18005456f  jmp     loc_180054720
0x180054574  lea     rax, [rbp+57h+cbData]
0x180054578  mov     [rsp+0D0h+lpcbData], r13; pPrevCertContext
0x18005457d  mov     r9d, 10000h; dwFindType
0x180054583  mov     [rsp+0D0h+phkResult], rax; pvFindPara
0x180054588  xor     r8d, r8d; dwFindFlags
0x18005458b  mov     edx, ebx; dwCertEncodingType
0x18005458d  mov     rcx, rsi; hCertStore
0x180054590  call    cs:__imp_CertFindCertificateInStore
0x180054596  mov     r14, rax
0x180054599  test    rax, rax
0x18005459c  jnz     short loc_1800545C8
0x18005459e  call    cs:__imp_GetLastError
0x1800545a4  mov     ebx, eax
0x1800545a6  test    eax, eax
0x1800545a8  jle     short loc_1800545B3
0x1800545aa  movzx   ebx, ax
0x1800545ad  or      ebx, 80070000h
0x1800545b3  mov     r8, rdi
0x1800545b6  lea     r10, aInitrpcsecurit; "InitRpcSecuritySchannel - Call to CertF"...
0x1800545bd  mov     r9d, 1F8h
0x1800545c3  jmp     loc_180054720
0x1800545c8  mov     r12d, 50h ; 'P'
0x1800545ce  mov     ebx, r13d
0x1800545d1  mov     ecx, r12d; Size
0x1800545d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800545d9  mov     r8d, r12d; Size
0x1800545dc  xor     edx, edx; Val
0x1800545de  mov     rcx, rax; void *
0x1800545e1  mov     rdi, rax
0x1800545e4  call    memset_0
0x1800545e9  lea     ecx, [r12-48h]; unsigned __int64
0x1800545ee  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800545f3  mov     [rdi+8], rax
0x1800545f7  mov     r12d, 1
0x1800545fd  mov     dword ptr [rdi], 4
0x180054603  mov     [rdi+4], r12d
0x180054607  mov     [rax], r14
0x18005460a  mov     rcx, [rdi+8]
0x18005460e  mov     dword ptr [rdi+48h], 2
0x180054615  mov     [rdi+3Ch], r13
0x180054619  mov     [rdi+38h], r13d
0x18005461d  mov     [rdi+10h], rsi
0x180054621  mov     rcx, [rcx]; pCertContext
0x180054624  call    ?IsServerCertUseable@@YAKPEBU_CERT_CONTEXT@@@Z; IsServerCertUseable(_CERT_CONTEXT const *)
0x180054629  mov     edx, r12d; Flags
0x18005462c  test    eax, eax
0x18005462e  jz      short loc_180054666
0x180054630  lea     rcx, aInitrpcsecurit_8; "InitRpcSecuritySchannel - Call to IsSer"...
0x180054637  mov     r9d, 20Dh
0x18005463d  mov     [rsp+0D0h+var_A0], rcx
0x180054642  lea     rdi, aInitrpcsecurit_7; "InitRpcSecuritySchannel"
0x180054649  mov     dword ptr [rsp+0D0h+lpcbData], eax
0x18005464d  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054654  mov     ecx, r12d
0x180054657  mov     [rsp+0D0h+phkResult], rdi
0x18005465c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054661  jmp     loc_18005475C
0x180054666  mov     [rbp+57h+pBuffer], r13
0x18005466a  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x18005466e  mov     rcx, [rdi+8]
0x180054672  mov     rcx, [rcx]; Context
0x180054675  call    cs:__imp_RpcCertGeneratePrincipalNameW
0x18005467b  mov     rax, [rbp+57h+pBuffer]
0x18005467f  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054686  mov     [rsp+0D0h+var_98], rax
0x18005468b  mov     r9d, 217h
0x180054691  lea     rax, aInitrpcsecurit_10; "InitRpcSecuritySchannel - Calling RpcSe"...
0x180054698  mov     edx, 3
0x18005469d  mov     [rsp+0D0h+var_A0], rax
0x1800546a2  mov     ecx, r12d
0x1800546a5  lea     rax, aInitrpcsecurit_7; "InitRpcSecuritySchannel"
0x1800546ac  mov     [rsp+0D0h+lpcbData], r13
0x1800546b1  mov     [rsp+0D0h+phkResult], rax
0x1800546b6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800546bb  mov     rcx, [rbp+57h+pBuffer]; ServerPrincName
0x1800546bf  xor     r8d, r8d; GetKeyFn
0x1800546c2  mov     r9, rdi; Arg
0x1800546c5  lea     edx, [r8+0Eh]; AuthnSvc
0x1800546c9  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800546cf  test    eax, eax
0x1800546d1  jz      short loc_1800546E9
0x1800546d3  mov     ecx, eax; int
0x1800546d5  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x1800546da  mov     r9d, 221h
0x1800546e0  lea     r10, aInitrpcsecurit_9; "InitRpcSecuritySchannel - Call to RpcSe"...
0x1800546e7  jmp     short loc_180054717
0x1800546e9  mov     r8d, r12d; DontWait
0x1800546ec  mov     edx, r15d; MaxCalls
0x1800546ef  mov     ecx, r12d; MinimumCallThreads
0x1800546f2  call    cs:__imp_RpcServerListen
0x1800546f8  test    eax, eax
0x1800546fa  jz      short loc_180054755
0x1800546fc  cmp     eax, 6B1h
0x180054701  jz      short loc_180054755
0x180054703  mov     ecx, eax; int
0x180054705  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18005470a  mov     r9d, 230h
0x180054710  lea     r10, aInitrpcsecurit_11; "InitRpcSecuritySchannel - Call to RpcSe"...
0x180054717  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x18005471e  mov     ebx, eax
0x180054720  lea     rdx, aInitrpcsecurit_7; "InitRpcSecuritySchannel"
0x180054727  mov     al, r12b
0x18005472a  mov     ecx, r12d
0x18005472d  mov     [rsp+0D0h+var_A0], r10
0x180054732  mov     dword ptr [rsp+0D0h+lpcbData], ebx
0x180054736  mov     [rsp+0D0h+phkResult], rdx
0x18005473b  movzx   edx, al
0x18005473e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054743  test    ebx, ebx
0x180054745  jns     short loc_180054755
0x180054747  test    r14, r14
0x18005474a  jz      short loc_180054755
0x18005474c  mov     rcx, r14; pCertContext
0x18005474f  call    cs:__imp_CertFreeCertificateContext
0x180054755  lea     rdi, aInitrpcsecurit_7; "InitRpcSecuritySchannel"
0x18005475c  mov     rcx, [rbp+57h+hKey]; hKey
0x180054760  test    rcx, rcx
0x180054763  jz      short loc_18005476B
0x180054765  call    cs:__imp_RegCloseKey
0x18005476b  test    rsi, rsi
0x18005476e  jz      short loc_18005477B
0x180054770  xor     edx, edx; dwFlags
0x180054772  mov     rcx, rsi; hCertStore
0x180054775  call    cs:__imp_CertCloseStore
0x18005477b  cmp     [rbp+57h+pBuffer], r13
0x18005477f  jz      short loc_18005478B
0x180054781  lea     rcx, [rbp+57h+pBuffer]; String
0x180054785  call    cs:__imp_RpcStringFreeW
0x18005478b  lea     rax, aInitrpcsecurit_6; "InitRpcSecuritySchannel Completed"
0x180054792  mov     r9d, 256h
0x180054798  mov     [rsp+0D0h+var_A0], rax
0x18005479d  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x1800547a4  mov     [rsp+0D0h+lpcbData], r13
0x1800547a9  mov     edx, 3
0x1800547ae  mov     ecx, r12d
0x1800547b1  mov     [rsp+0D0h+phkResult], rdi
0x1800547b6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800547bb  mov     eax, ebx
0x1800547bd  mov     rcx, [rbp+57h+var_50]
0x1800547c1  xor     rcx, rsp; StackCookie
0x1800547c4  call    __security_check_cookie
0x1800547c9  add     rsp, 98h
0x1800547d0  pop     r15
0x1800547d2  pop     r14
0x1800547d4  pop     r13
0x1800547d6  pop     r12
0x1800547d8  pop     rdi
0x1800547d9  pop     rsi
0x1800547da  pop     rbx
0x1800547db  pop     rbp
0x1800547dc  retn
```
