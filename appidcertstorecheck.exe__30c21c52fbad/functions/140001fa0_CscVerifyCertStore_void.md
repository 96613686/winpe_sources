# CscVerifyCertStore(void)

- ea: `0x140001fa0`
- end: `0x1400022fd`
- name: `?CscVerifyCertStore@@YAKXZ`
- size: `861`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400024e8`

## callees

- `0x140001920`
- `0x140001ab8`
- `0x140001bc4`
- `0x140001fa0`
- `0x140002d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002133`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002012`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002012`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400022d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400022d2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140002295`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140002295`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400020d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400020d5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1400020e5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1400021a3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1400021cf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1400020e5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1400021a3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1400021cf`
- `CRYPT32!CertOpenStore` at `0x140002032`
- `CRYPT32!CertOpenStore` at `0x140002032`
- `CRYPT32!CertFreeCertificateContext` at `0x140002250`
- `CRYPT32!CertFreeCertificateContext` at `0x1400022b7`
- `CRYPT32!CertFreeCertificateContext` at `0x140002250`
- `CRYPT32!CertFreeCertificateContext` at `0x1400022b7`
- `CRYPT32!CertCloseStore` at `0x1400022c2`
- `CRYPT32!CertCloseStore` at `0x1400022c2`
- `CRYPT32!CertGetCertificateChain` at `0x140002129`
- `CRYPT32!CertGetCertificateChain` at `0x140002129`
- `CRYPT32!CertFreeCertificateChain` at `0x140002211`
- `CRYPT32!CertFreeCertificateChain` at `0x140002211`

## pseudocode

```c
__int64 CscVerifyCertStore(void)
{
  PCCERT_CONTEXT v0; // rdi
  unsigned int updated; // ebx
  HCERTSTORE v2; // rax
  void *v3; // r12
  DWORD v4; // esi
  DWORD v5; // edx
  unsigned int v6; // eax
  PCERT_INFO pCertInfo; // rax
  unsigned int v8; // r15d
  unsigned int v9; // r14d
  FILETIME *v10; // rax
  DWORD LastError; // eax
  const CERT_CHAIN_CONTEXT *v12; // rcx
  unsigned int v13; // r15d
  __int64 v14; // r13
  __int64 v15; // rsi
  LSTATUS v16; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h]
  DWORD v21; // [rsp+54h] [rbp-ACh]
  FILETIME FileTime2; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  FILETIME NotBefore; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+78h] [rbp-88h] BYREF
  HCERTSTORE v27; // [rsp+80h] [rbp-80h]
  _CERT_CHAIN_PARA pChainPara; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+B0h] [rbp-50h] BYREF

  hKey = 0;
  cchName = 0;
  ftLastWriteTime = 0;
  pCertContext = 0;
  v0 = 0;
  NotBefore = 0;
  FileTime2 = 0;
  updated = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Control\\AppID\\CertStore\\",
              0,
              0x20019u,
              &hKey);
  if ( !updated )
  {
    v2 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
    v27 = v2;
    v3 = v2;
    if ( v2 )
    {
      updated = CscInitializeCertChainStore(v2);
      if ( !updated )
      {
        v4 = 0;
        v5 = 0;
        while ( 1 )
        {
          v21 = v4;
          cchName = 260;
          v16 = RegEnumKeyExW(hKey, v5, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
          updated = v16;
          if ( v16 )
            break;
          v6 = CscReadCertFromStore(hKey, Name, &pCertContext);
          v0 = pCertContext;
          updated = v6;
          if ( v6 )
            goto LABEL_33;
          pCertInfo = pCertContext->pCertInfo;
          memset(&pChainPara, 0, sizeof(pChainPara));
          pCertContext = 0;
          v8 = 0;
          SystemTimeAsFileTime = 0;
          v9 = 0;
          NotBefore = pCertInfo->NotBefore;
          v10 = (FILETIME *)v0->pCertInfo;
          v20 = 0;
          FileTime2 = v10[9];
          pChainPara.cbSize = 32;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) > 0 )
            SystemTimeAsFileTime = FileTime2;
          if ( CertGetCertificateChain(
                 (HCERTCHAINENGINE)1,
                 v0,
                 &SystemTimeAsFileTime,
                 v3,
                 &pChainPara,
                 0x40000000u,
                 0,
                 (PCCERT_CHAIN_CONTEXT *)&pCertContext) )
          {
            v12 = (const CERT_CHAIN_CONTEXT *)pCertContext;
            updated = 0;
            if ( (*(_BYTE *)(&pCertContext->dwCertEncodingType + 1) & 4) != 0 )
            {
              v9 = 1;
            }
            else if ( (*(&pCertContext->dwCertEncodingType + 1) & 0xFEFFFFBF) != 0 )
            {
              v20 = 1;
            }
            else if ( HIDWORD(pCertContext->pbCertEncoded) != 1 )
            {
              v9 = 1;
            }
            v13 = 0;
            v14 = **(_QWORD **)&pCertContext->cbCertEncoded;
            v15 = **(_QWORD **)(v14 + 16);
            if ( *(_DWORD *)(v14 + 12) )
            {
              do
              {
                if ( CompareFileTime((const FILETIME *)(*(_QWORD *)(*(_QWORD *)(v15 + 8) + 24LL) + 64LL), &NotBefore) > 0 )
                  NotBefore = *(FILETIME *)(*(_QWORD *)(*(_QWORD *)(v15 + 8) + 24LL) + 64LL);
                if ( CompareFileTime((const FILETIME *)(*(_QWORD *)(*(_QWORD *)(v15 + 8) + 24LL) + 72LL), &FileTime2) < 0 )
                  FileTime2 = *(FILETIME *)(*(_QWORD *)(*(_QWORD *)(v15 + 8) + 24LL) + 72LL);
                ++v13;
                v15 += 56;
              }
              while ( v13 < *(_DWORD *)(v14 + 12) );
              v3 = v27;
              v12 = (const CERT_CHAIN_CONTEXT *)pCertContext;
            }
            v8 = v20;
            v4 = v21;
          }
          else
          {
            LastError = GetLastError();
            v12 = (const CERT_CHAIN_CONTEXT *)pCertContext;
            updated = LastError;
          }
          if ( v12 )
            CertFreeCertificateChain(v12);
          if ( updated )
            goto LABEL_33;
          updated = CscUpdateCertificateStatus(hKey, Name, v9, v8, &NotBefore, &FileTime2);
          if ( updated )
            goto LABEL_33;
          CertFreeCertificateContext(v0);
          ++v4;
          pCertContext = 0;
          v5 = v4;
          v0 = 0;
        }
        if ( v16 != 259 )
          goto LABEL_35;
        updated = 0;
LABEL_33:
        if ( v0 )
          CertFreeCertificateContext(v0);
      }
LABEL_35:
      CertCloseStore(v3, 0);
    }
    else
    {
      updated = GetLastError();
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return updated;
}

```

## disassembly

```asm
0x140001fa0  push    rbp
0x140001fa2  push    rbx
0x140001fa3  push    rsi
0x140001fa4  push    rdi
0x140001fa5  push    r12
0x140001fa7  push    r13
0x140001fa9  push    r14
0x140001fab  push    r15
0x140001fad  lea     rbp, [rsp-1D8h]
0x140001fb5  sub     rsp, 2D8h
0x140001fbc  mov     rax, cs:__security_cookie
0x140001fc3  xor     rax, rsp
0x140001fc6  mov     [rbp+210h+var_50], rax
0x140001fcd  xor     r13d, r13d
0x140001fd0  lea     rax, [rsp+310h+hKey]
0x140001fd5  mov     r9d, 20019h; samDesired
0x140001fdb  mov     [rsp+310h+hKey], r13
0x140001fe0  xor     r8d, r8d; ulOptions
0x140001fe3  mov     [rsp+310h+cchName], r13d
0x140001fe8  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\App"...
0x140001fef  mov     qword ptr [rsp+310h+ftLastWriteTime.dwLowDateTime], r13
0x140001ff4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140001ffb  mov     [rsp+310h+pCertContext], r13
0x140002000  mov     edi, r13d
0x140002003  mov     qword ptr [rsp+310h+var_2A0.dwLowDateTime], r13
0x140002008  mov     qword ptr [rsp+310h+FileTime2.dwLowDateTime], r13
0x14000200d  mov     [rsp+310h+phkResult], rax; phkResult
0x140002012  call    cs:__imp_RegOpenKeyExW
0x140002018  mov     ebx, eax
0x14000201a  test    eax, eax
0x14000201c  jnz     loc_1400022C8
0x140002022  xor     r9d, r9d; dwFlags
0x140002025  mov     [rsp+310h+phkResult], r13; pvPara
0x14000202a  xor     r8d, r8d; hCryptProv
0x14000202d  lea     ecx, [rax+2]; lpszStoreProvider
0x140002030  xor     edx, edx; dwEncodingType
0x140002032  call    cs:__imp_CertOpenStore
0x140002038  mov     [rbp+210h+var_290], rax
0x14000203c  mov     r12, rax
0x14000203f  test    rax, rax
0x140002042  jnz     short loc_140002051
0x140002044  call    cs:__imp_GetLastError
0x14000204a  mov     ebx, eax
0x14000204c  jmp     loc_1400022C8
0x140002051  mov     rcx, rax; hCertStore
0x140002054  call    ?CscInitializeCertChainStore@@YAKPEAX@Z; CscInitializeCertChainStore(void *)
0x140002059  mov     ebx, eax
0x14000205b  test    eax, eax
0x14000205d  jnz     loc_1400022BD
0x140002063  mov     esi, r13d
0x140002066  xor     edx, edx
0x140002068  jmp     loc_140002262
0x14000206d  mov     rcx, [rsp+310h+hKey]; HKEY
0x140002072  lea     r8, [rsp+310h+pCertContext]; struct _CERT_CONTEXT **
0x140002077  lea     rdx, [rbp+210h+Name]; unsigned __int16 *
0x14000207b  call    ?CscReadCertFromStore@@YAKPEAUHKEY__@@PEBGPEAPEBU_CERT_CONTEXT@@@Z; CscReadCertFromStore(HKEY__ *,ushort const *,_CERT_CONTEXT const * *)
0x140002080  mov     rdi, [rsp+310h+pCertContext]
0x140002085  mov     ebx, eax
0x140002087  test    eax, eax
0x140002089  jnz     loc_1400022AF
0x14000208f  mov     rax, [rdi+18h]
0x140002093  xorps   xmm0, xmm0
0x140002096  movups  xmmword ptr [rbp+210h+pChainPara.cbSize], xmm0
0x14000209a  mov     [rsp+310h+pCertContext], r13
0x14000209f  mov     r15d, r13d
0x1400020a2  movups  xmmword ptr [rbp+210h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1400020a6  mov     qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1400020ab  mov     r14d, r13d
0x1400020ae  mov     rcx, [rax+40h]
0x1400020b2  mov     qword ptr [rsp+310h+var_2A0.dwLowDateTime], rcx
0x1400020b7  mov     rax, [rdi+18h]
0x1400020bb  mov     [rsp+310h+var_2C0], r13d
0x1400020c0  mov     rcx, [rax+48h]
0x1400020c4  mov     qword ptr [rsp+310h+FileTime2.dwLowDateTime], rcx
0x1400020c9  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400020ce  mov     [rbp+210h+pChainPara.cbSize], 20h ; ' '
0x1400020d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400020db  lea     rdx, [rsp+310h+FileTime2]; lpFileTime2
0x1400020e0  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpFileTime1
0x1400020e5  call    cs:__imp_CompareFileTime
0x1400020eb  test    eax, eax
0x1400020ed  jle     short loc_1400020F9
0x1400020ef  mov     rax, qword ptr [rsp+310h+FileTime2.dwLowDateTime]
0x1400020f4  mov     qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400020f9  lea     rax, [rsp+310h+pCertContext]
0x1400020fe  mov     r9, r12; hAdditionalStore
0x140002101  mov     [rsp+310h+ppChainContext], rax; ppChainContext
0x140002106  lea     r8, [rsp+310h+SystemTimeAsFileTime]; pTime
0x14000210b  mov     [rsp+310h+pvReserved], r13; pvReserved
0x140002110  lea     rax, [rbp+210h+pChainPara]
0x140002114  mov     [rsp+310h+dwFlags], 40000000h; dwFlags
0x14000211c  mov     rdx, rdi; pCertContext
0x14000211f  mov     ecx, 1; hChainEngine
0x140002124  mov     [rsp+310h+phkResult], rax; pChainPara
0x140002129  call    cs:__imp_CertGetCertificateChain
0x14000212f  test    eax, eax
0x140002131  jnz     short loc_140002145
0x140002133  call    cs:__imp_GetLastError
0x140002139  mov     rcx, [rsp+310h+pCertContext]
0x14000213e  mov     ebx, eax
0x140002140  jmp     loc_14000220C
0x140002145  mov     rcx, [rsp+310h+pCertContext]
0x14000214a  mov     ebx, r13d
0x14000214d  mov     eax, [rcx+4]
0x140002150  and     eax, 0FEFFFFBFh
0x140002155  test    al, 4
0x140002157  jz      short loc_140002161
0x140002159  mov     r14d, 1
0x14000215f  jmp     short loc_14000217B
0x140002161  test    eax, eax
0x140002163  jz      short loc_14000216F
0x140002165  mov     [rsp+310h+var_2C0], 1
0x14000216d  jmp     short loc_14000217B
0x14000216f  mov     eax, 1
0x140002174  cmp     [rcx+0Ch], eax
0x140002177  cmovnz  r14d, eax
0x14000217b  mov     rax, [rcx+10h]
0x14000217f  xor     r15d, r15d
0x140002182  mov     r13, [rax]
0x140002185  mov     rax, [r13+10h]
0x140002189  mov     rsi, [rax]
0x14000218c  cmp     [r13+0Ch], r15d
0x140002190  jbe     short loc_140002200
0x140002192  mov     rax, [rsi+8]
0x140002196  lea     rdx, [rsp+310h+var_2A0]; lpFileTime2
0x14000219b  mov     rcx, [rax+18h]
0x14000219f  add     rcx, 40h ; '@'; lpFileTime1
0x1400021a3  call    cs:__imp_CompareFileTime
0x1400021a9  test    eax, eax
0x1400021ab  jle     short loc_1400021BE
0x1400021ad  mov     rax, [rsi+8]
0x1400021b1  mov     rcx, [rax+18h]
0x1400021b5  mov     rax, [rcx+40h]
0x1400021b9  mov     qword ptr [rsp+310h+var_2A0.dwLowDateTime], rax
0x1400021be  mov     rax, [rsi+8]
0x1400021c2  lea     rdx, [rsp+310h+FileTime2]; lpFileTime2
0x1400021c7  mov     rcx, [rax+18h]
0x1400021cb  add     rcx, 48h ; 'H'; lpFileTime1
0x1400021cf  call    cs:__imp_CompareFileTime
0x1400021d5  test    eax, eax
0x1400021d7  jns     short loc_1400021EA
0x1400021d9  mov     rax, [rsi+8]
0x1400021dd  mov     rcx, [rax+18h]
0x1400021e1  mov     rax, [rcx+48h]
0x1400021e5  mov     qword ptr [rsp+310h+FileTime2.dwLowDateTime], rax
0x1400021ea  inc     r15d
0x1400021ed  add     rsi, 38h ; '8'
0x1400021f1  cmp     r15d, [r13+0Ch]
0x1400021f5  jb      short loc_140002192
0x1400021f7  mov     r12, [rbp+210h+var_290]
0x1400021fb  mov     rcx, [rsp+310h+pCertContext]; pChainContext
0x140002200  mov     r15d, [rsp+310h+var_2C0]
0x140002205  xor     r13d, r13d
0x140002208  mov     esi, [rsp+310h+var_2BC]
0x14000220c  test    rcx, rcx
0x14000220f  jz      short loc_140002217
0x140002211  call    cs:__imp_CertFreeCertificateChain
0x140002217  test    ebx, ebx
0x140002219  jnz     loc_1400022AF
0x14000221f  mov     rcx, [rsp+310h+hKey]; HKEY
0x140002224  lea     rax, [rsp+310h+FileTime2]
0x140002229  mov     qword ptr [rsp+310h+dwFlags], rax; FILETIME *
0x14000222e  lea     rdx, [rbp+210h+Name]; unsigned __int16 *
0x140002232  lea     rax, [rsp+310h+var_2A0]
0x140002237  mov     r9d, r15d; unsigned int
0x14000223a  mov     r8d, r14d; unsigned int
0x14000223d  mov     [rsp+310h+phkResult], rax; lpFileTime2
0x140002242  call    ?CscUpdateCertificateStatus@@YAKPEAUHKEY__@@PEBGKKPEAU_FILETIME@@2@Z; CscUpdateCertificateStatus(HKEY__ *,ushort const *,ulong,ulong,_FILETIME *,_FILETIME *)
0x140002247  mov     ebx, eax
0x140002249  test    eax, eax
0x14000224b  jnz     short loc_1400022AF
0x14000224d  mov     rcx, rdi; pCertContext
0x140002250  call    cs:__imp_CertFreeCertificateContext
0x140002256  inc     esi
0x140002258  mov     [rsp+310h+pCertContext], r13
0x14000225d  mov     edx, esi; dwIndex
0x14000225f  mov     rdi, r13
0x140002262  mov     rcx, [rsp+310h+hKey]; hKey
0x140002267  lea     rax, [rsp+310h+ftLastWriteTime]
0x14000226c  mov     [rsp+310h+ppChainContext], rax; lpftLastWriteTime
0x140002271  lea     r9, [rsp+310h+cchName]; lpcchName
0x140002276  mov     [rsp+310h+pvReserved], r13; lpcchClass
0x14000227b  lea     r8, [rbp+210h+Name]; lpName
0x14000227f  mov     qword ptr [rsp+310h+dwFlags], r13; lpClass
0x140002284  mov     [rsp+310h+phkResult], r13; lpReserved
0x140002289  mov     [rsp+310h+var_2BC], esi
0x14000228d  mov     [rsp+310h+cchName], 104h
0x140002295  call    cs:__imp_RegEnumKeyExW
0x14000229b  mov     ebx, eax
0x14000229d  test    eax, eax
0x14000229f  jz      loc_14000206D
0x1400022a5  cmp     eax, 103h
0x1400022aa  jnz     short loc_1400022BD
0x1400022ac  mov     ebx, r13d
0x1400022af  test    rdi, rdi
0x1400022b2  jz      short loc_1400022BD
0x1400022b4  mov     rcx, rdi; pCertContext
0x1400022b7  call    cs:__imp_CertFreeCertificateContext
0x1400022bd  xor     edx, edx; dwFlags
0x1400022bf  mov     rcx, r12; hCertStore
0x1400022c2  call    cs:__imp_CertCloseStore
0x1400022c8  mov     rcx, [rsp+310h+hKey]; hKey
0x1400022cd  test    rcx, rcx
0x1400022d0  jz      short loc_1400022D8
0x1400022d2  call    cs:__imp_RegCloseKey
0x1400022d8  mov     eax, ebx
0x1400022da  mov     rcx, [rbp+210h+var_50]
0x1400022e1  xor     rcx, rsp; StackCookie
0x1400022e4  call    __security_check_cookie
0x1400022e9  add     rsp, 2D8h
0x1400022f0  pop     r15
0x1400022f2  pop     r14
0x1400022f4  pop     r13
0x1400022f6  pop     r12
0x1400022f8  pop     rdi
0x1400022f9  pop     rsi
0x1400022fa  pop     rbx
0x1400022fb  pop     rbp
0x1400022fc  retn
```
