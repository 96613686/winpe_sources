# ProofOfPossessionTokenProvider::GetAadLoginUrl(ushort * *)

- ea: `0x1800045fc`
- end: `0x180004c7e`
- name: `?GetAadLoginUrl@ProofOfPossessionTokenProvider@@YAJPEAPEAG@Z`
- size: `1666`
- prototype: `__int64 __fastcall(ProofOfPossessionTokenProvider *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800030b8`
- `0x1800040ec`

## callees

- `0x1800045fc`
- `0x180004c84`
- `0x180004dd0`
- `0x180073844`
- `0x18007bdfc`
- `0x18009a6a0`
- `0x18011a7c4`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000476a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004831`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004939`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000476a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004831`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004939`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004719`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800047dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004719`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800047dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000474a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004811`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004910`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000474a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004811`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004910`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800046a5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800046a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800046dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800047a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000489e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800046dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800047a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000489e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000483f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000483f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a1e`

## string_xrefs

- `0x180004738`: `LoginUri`
- `0x1800048fe`: `LoginUri`
- `0x180004ba3`: `LoginUri`
- `0x1800047ff`: `EnterpriseAuthorityUri`
- `0x180004bf0`: `EnterpriseAuthorityUri`
- `0x180004aca`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`

## pseudocode

```c
__int64 __fastcall ProofOfPossessionTokenProvider::GetAadLoginUrl(
        ProofOfPossessionTokenProvider *this,
        unsigned __int16 **a2)
{
  HKEY v2; // rbx
  HKEY v3; // r14
  unsigned __int16 *v4; // r15
  int PersistedRegistryLocationW; // eax
  int v6; // edi
  signed int v7; // ebx
  bool v8; // sf
  bool v9; // sf
  BYTE *v10; // rax
  HKEY v11; // rsi
  BYTE *v12; // rbx
  LSTATUS v13; // eax
  unsigned int v14; // edi
  LSTATUS Value; // eax
  BYTE *v16; // rax
  unsigned __int16 *v17; // rsi
  BYTE *v18; // rbx
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  unsigned __int64 *v21; // rax
  int v22; // r12d
  unsigned __int64 *v23; // rdi
  BYTE *v24; // rbx
  BYTE *v25; // r13
  BYTE *v26; // rsi
  LSTATUS v27; // eax
  rsize_t v28; // r13
  unsigned __int64 v30; // rcx
  char *v31; // rdx
  unsigned __int64 v32; // rcx
  BYTE *v33; // rdx
  unsigned __int64 v34; // rcx
  unsigned __int16 *v35; // rdx
  int MergedAadLoginUrl; // eax
  unsigned int TokenProviderLoginUrls; // eax
  unsigned int v38; // eax
  DWORD cbData[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v42; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v43; // [rsp+50h] [rbp-B0h] BYREF
  SIZE_T cb; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v45; // [rsp+60h] [rbp-A0h]
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v45 = (unsigned __int64)this;
  if ( !this )
    return (unsigned int)-2147024809;
  hKey = 0;
  v2 = 0;
  cb = 0;
  *(_QWORD *)cbData = 0;
  v3 = 0;
  phkResult = 0;
  v4 = 0;
  v42 = 0;
  v43 = 0;
  if ( (unsigned int)IsInternetExplorerApp() )
  {
    TokenProviderLoginUrls = GetTokenProviderLoginUrls(
                               HKEY_LOCAL_MACHINE,
                               L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
                               L"LoginUri",
                               (unsigned __int16 **)&hKey,
                               (unsigned __int64 *)cbData);
    v14 = TokenProviderLoginUrls;
    if ( (int)(TokenProviderLoginUrls + 0x80000000) < 0 || TokenProviderLoginUrls == -2147024894 )
    {
      v38 = GetTokenProviderLoginUrls(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
              L"EnterpriseAuthorityUri",
              &v43,
              (unsigned __int64 *)&v42);
      v3 = hKey;
      v14 = v38;
      v21 = *(unsigned __int64 **)cbData;
      v4 = v43;
      v2 = (HKEY)v42;
    }
    else
    {
      v3 = hKey;
      v21 = *(unsigned __int64 **)cbData;
    }
    goto LABEL_29;
  }
  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"IDStoreLoadParametersAad",
                                 L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
                                 SubKey,
                                 520);
  v6 = (unsigned __int16)PersistedRegistryLocationW;
  v7 = PersistedRegistryLocationW;
  v8 = PersistedRegistryLocationW < 0;
  if ( PersistedRegistryLocationW > 0 )
    v8 = 1;
  if ( v8 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v9 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = v6 | 0x80070000;
    v9 = 1;
  }
  if ( !v9 )
  {
    cbData[0] = 4168;
    v10 = (BYTE *)CoTaskMemAlloc(0x104Cu);
    v11 = (HKEY)v10;
    if ( !v10 )
    {
      v22 = -2147024882;
LABEL_46:
      if ( v4 )
        CoTaskMemFree(v4);
      if ( v3 )
        CoTaskMemFree(v3);
      return (unsigned int)v22;
    }
    v12 = v10;
    hKey = 0;
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x101u, &hKey);
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      Value = RegQueryValueExW(hKey, L"LoginUri", 0, 0, v12, cbData);
      v14 = Value;
      if ( Value )
      {
        if ( Value > 0 )
          v14 = (unsigned __int16)Value | 0x80070000;
      }
      else
      {
        v30 = (unsigned __int64)cbData[0] >> 1;
        *((_WORD *)v11 + v30) = 0;
        v31 = (char *)v11 + 2 * v30 + 2;
        *(_WORD *)v31 = 0;
        while ( v31 >= (char *)v11 && !*(_WORD *)v31 )
          v31 -= 2;
        v12 = 0;
        v3 = v11;
        v14 = 0;
        cb = 2 * ((v31 - (char *)v11) >> 1) + 6;
      }
      RegCloseKey(hKey);
    }
    if ( v12 )
      CoTaskMemFree(v12);
    if ( (int)(v14 + 0x80000000) < 0 || v14 == -2147024894 )
    {
      cbData[0] = 4168;
      v16 = (BYTE *)CoTaskMemAlloc(0x104Cu);
      v17 = (unsigned __int16 *)v16;
      if ( v16 )
      {
        v18 = v16;
        hKey = 0;
        v19 = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
                0,
                0x101u,
                &hKey);
        v14 = v19;
        if ( v19 )
        {
          if ( v19 > 0 )
            v14 = (unsigned __int16)v19 | 0x80070000;
        }
        else
        {
          v20 = RegQueryValueExW(hKey, L"EnterpriseAuthorityUri", 0, 0, v18, cbData);
          v14 = v20;
          if ( v20 )
          {
            if ( v20 > 0 )
              v14 = (unsigned __int16)v20 | 0x80070000;
          }
          else
          {
            v34 = (unsigned __int64)cbData[0] >> 1;
            v17[v34] = 0;
            v35 = &v17[v34 + 1];
            *v35 = 0;
            while ( v35 >= v17 && !*v35 )
              --v35;
            v18 = 0;
            v4 = v17;
            v14 = 0;
            phkResult = (HKEY)(2 * (v35 - v17) + 6);
          }
          RegCloseKey(hKey);
        }
        if ( v18 )
          CoTaskMemFree(v18);
      }
      else
      {
        v14 = -2147024882;
      }
    }
    v2 = phkResult;
    v21 = (unsigned __int64 *)cb;
LABEL_29:
    v22 = 0;
    if ( v14 != -2147024894 )
      v22 = v14;
    if ( v22 < 0 )
      goto LABEL_46;
    *(_QWORD *)cbData = 0;
    v23 = 0;
    hKey = 0;
    v42 = 0;
    if ( v3 )
    {
      if ( v4 )
      {
        MergedAadLoginUrl = ProofOfPossessionTokenProvider::GetMergedAadLoginUrl(
                              (ProofOfPossessionTokenProvider *)v3,
                              (SIZE_T)v21,
                              v4,
                              (rsize_t)v2,
                              (unsigned __int64)cbData,
                              &v42,
                              *(unsigned __int64 **)cbData);
        v23 = *(unsigned __int64 **)cbData;
        v22 = MergedAadLoginUrl;
        if ( MergedAadLoginUrl < 0 )
        {
LABEL_60:
          if ( v23 )
            CoTaskMemFree(v23);
          goto LABEL_46;
        }
        hKey = (HKEY)v42;
      }
      else
      {
        v23 = (unsigned __int64 *)v3;
        hKey = (HKEY)v21;
        v3 = 0;
      }
    }
    else if ( v4 )
    {
      v23 = (unsigned __int64 *)v4;
      v4 = 0;
      Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>>::Clear(cbData);
      hKey = v2;
    }
    v43 = 0;
    v24 = 0;
    cbData[0] = 4168;
    v25 = (BYTE *)CoTaskMemAlloc(0x104Cu);
    if ( v25 )
    {
      phkResult = 0;
      v26 = v25;
      v22 = RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\AAD\\Package",
              0,
              0x101u,
              &phkResult);
      if ( v22 )
      {
        if ( v22 > 0 )
          v22 = (unsigned __int16)v22 | 0x80070000;
        v28 = 0;
      }
      else
      {
        v27 = RegQueryValueExW(phkResult, L"LoginUri", 0, 0, v25, cbData);
        v22 = v27;
        if ( v27 )
        {
          if ( v27 > 0 )
            v22 = (unsigned __int16)v27 | 0x80070000;
          v28 = 0;
        }
        else
        {
          v32 = (unsigned __int64)cbData[0] >> 1;
          *(_WORD *)&v25[2 * v32] = 0;
          v33 = &v25[2 * v32 + 2];
          *(_WORD *)v33 = 0;
          while ( v33 >= v25 && !*(_WORD *)v33 )
            v33 -= 2;
          v24 = v25;
          v26 = 0;
          v22 = 0;
          v28 = 2 * ((v33 - v25) >> 1) + 6;
        }
        RegCloseKey(phkResult);
      }
      if ( v26 )
        CoTaskMemFree(v26);
    }
    else
    {
      v22 = -2147024882;
      v28 = 0;
    }
    if ( !v23 && !v24 )
      goto LABEL_46;
    v22 = ProofOfPossessionTokenProvider::GetMergedAadLoginUrl(
            (ProofOfPossessionTokenProvider *)v23,
            (SIZE_T)hKey,
            v24,
            v28,
            v45,
            &v43,
            *(unsigned __int64 **)cbData);
    if ( v24 )
      CoTaskMemFree(v24);
    goto LABEL_60;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18A,
    (unsigned int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
    (const char *)(unsigned int)v7,
    0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800045fc  push    rbp
0x1800045fe  push    rbx
0x1800045ff  push    rsi
0x180004600  push    rdi
0x180004601  push    r12
0x180004603  push    r13
0x180004605  push    r14
0x180004607  push    r15
0x180004609  lea     rbp, [rsp-198h]
0x180004611  sub     rsp, 298h
0x180004618  mov     rax, cs:__security_cookie
0x18000461f  xor     rax, rsp
0x180004622  mov     [rbp+1D0h+var_50], rax
0x180004629  xor     r13d, r13d
0x18000462c  mov     [rsp+2D0h+var_270], rcx
0x180004631  test    rcx, rcx
0x180004634  jz      loc_180004A29
0x18000463a  mov     edx, r13d
0x18000463d  mov     [rsp+2D0h+hKey], r13
0x180004642  mov     ebx, r13d
0x180004645  mov     [rsp+2D0h+cb], rdx
0x18000464a  mov     qword ptr [rsp+2D0h+cbData], rdx
0x18000464f  mov     r14d, r13d
0x180004652  mov     [rsp+2D0h+var_290], rbx
0x180004657  mov     r15d, r13d
0x18000465a  mov     [rsp+2D0h+var_288], rbx
0x18000465f  mov     [rsp+2D0h+var_280], r13
0x180004664  call    ?IsInternetExplorerApp@@YAHXZ; IsInternetExplorerApp(void)
0x180004669  mov     esi, 80070000h
0x18000466e  test    eax, eax
0x180004670  jnz     loc_180004B8A
0x180004676  mov     ebx, 208h
0x18000467b  lea     rcx, [rsp+2D0h+SubKey]; void *
0x180004680  mov     r8d, ebx; Size
0x180004683  xor     edx, edx; Val
0x180004685  call    memset_0
0x18000468a  mov     r9d, ebx
0x18000468d  mov     [rsp+2D0h+phkResult], r13; int
0x180004692  lea     r8, [rsp+2D0h+SubKey]
0x180004697  lea     rdx, aSoftwareMicros_72; "Software\\Microsoft\\IdentityStore\\Loa"...
0x18000469e  lea     rcx, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x1800046a5  call    cs:__imp_GetPersistedRegistryLocationW
0x1800046ab  movzx   edi, ax
0x1800046ae  mov     ebx, eax
0x1800046b0  test    eax, eax
0x1800046b2  jle     short loc_1800046BA
0x1800046b4  mov     eax, edi
0x1800046b6  or      eax, esi
0x1800046b8  test    eax, eax
0x1800046ba  js      loc_180004C1E
0x1800046c0  test    ebx, ebx
0x1800046c2  jle     short loc_1800046CA
0x1800046c4  mov     ebx, edi
0x1800046c6  or      ebx, esi
0x1800046c8  test    ebx, ebx
0x1800046ca  js      loc_180004AC3
0x1800046d0  mov     ecx, 104Ch; cb
0x1800046d5  mov     [rsp+2D0h+cbData], 1048h
0x1800046dd  call    cs:__imp_CoTaskMemAlloc
0x1800046e3  mov     rsi, rax
0x1800046e6  test    rax, rax
0x1800046e9  jz      loc_180004C73
0x1800046ef  mov     rbx, rax
0x1800046f2  mov     [rsp+2D0h+hKey], r13
0x1800046f7  lea     rax, [rsp+2D0h+hKey]
0x1800046fc  mov     r12, 0FFFFFFFF80000002h
0x180004703  mov     rcx, r12; hKey
0x180004706  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18000470b  mov     r9d, 101h; samDesired
0x180004711  lea     rdx, [rsp+2D0h+SubKey]; lpSubKey
0x180004716  xor     r8d, r8d; ulOptions
0x180004719  call    cs:__imp_RegOpenKeyExW
0x18000471f  mov     edi, eax
0x180004721  test    eax, eax
0x180004723  jnz     loc_18000499D
0x180004729  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18000472e  lea     rax, [rsp+2D0h+cbData]
0x180004733  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180004738  lea     rdx, aLoginuri; "LoginUri"
0x18000473f  xor     r9d, r9d; lpType
0x180004742  mov     [rsp+2D0h+phkResult], rbx; lpData
0x180004747  xor     r8d, r8d; lpReserved
0x18000474a  call    cs:__imp_RegQueryValueExW
0x180004750  mov     edi, eax
0x180004752  test    eax, eax
0x180004754  jz      loc_180004A34
0x18000475a  jle     short loc_180004765
0x18000475c  movzx   edi, ax
0x18000475f  or      edi, 80070000h
0x180004765  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18000476a  call    cs:__imp_RegCloseKey
0x180004770  test    rbx, rbx
0x180004773  jz      short loc_18000477E
0x180004775  mov     rcx, rbx; pv
0x180004778  call    cs:__imp_CoTaskMemFree
0x18000477e  mov     edx, 80000000h
0x180004783  mov     r13d, 80070002h
0x180004789  lea     eax, [rdi+rdx]
0x18000478c  test    edx, eax
0x18000478e  jnz     short loc_180004799
0x180004790  cmp     edi, r13d
0x180004793  jnz     loc_180004845
0x180004799  mov     ecx, 104Ch; cb
0x18000479e  mov     [rsp+2D0h+cbData], 1048h
0x1800047a6  call    cs:__imp_CoTaskMemAlloc
0x1800047ac  mov     rsi, rax
0x1800047af  test    rax, rax
0x1800047b2  jz      loc_180004C28
0x1800047b8  mov     rbx, rax
0x1800047bb  mov     [rsp+2D0h+hKey], r15
0x1800047c0  lea     rax, [rsp+2D0h+hKey]
0x1800047c5  mov     r9d, 101h; samDesired
0x1800047cb  xor     r8d, r8d; ulOptions
0x1800047ce  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800047d3  lea     rdx, aSoftwareMicros_72; "Software\\Microsoft\\IdentityStore\\Loa"...
0x1800047da  mov     rcx, r12; hKey
0x1800047dd  call    cs:__imp_RegOpenKeyExW
0x1800047e3  xor     r12d, r12d
0x1800047e6  mov     edi, eax
0x1800047e8  test    eax, eax
0x1800047ea  jnz     loc_1800049C6
0x1800047f0  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800047f5  lea     rax, [rsp+2D0h+cbData]
0x1800047fa  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x1800047ff  lea     rdx, aEnterpriseauth; "EnterpriseAuthorityUri"
0x180004806  xor     r9d, r9d; lpType
0x180004809  mov     [rsp+2D0h+phkResult], rbx; lpData
0x18000480e  xor     r8d, r8d; lpReserved
0x180004811  call    cs:__imp_RegQueryValueExW
0x180004817  mov     edi, eax
0x180004819  test    eax, eax
0x18000481b  jz      loc_180004A9A
0x180004821  jle     short loc_18000482C
0x180004823  movzx   edi, ax
0x180004826  or      edi, 80070000h
0x18000482c  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180004831  call    cs:__imp_RegCloseKey
0x180004837  test    rbx, rbx
0x18000483a  jz      short loc_180004845
0x18000483c  mov     rcx, rbx; pv
0x18000483f  call    cs:__imp_CoTaskMemFree
0x180004845  mov     rbx, [rsp+2D0h+var_290]
0x18000484a  mov     rax, [rsp+2D0h+cb]
0x18000484f  xor     r12d, r12d
0x180004852  cmp     edi, r13d
0x180004855  cmovnz  r12d, edi
0x180004859  xor     r13d, r13d
0x18000485c  test    r12d, r12d
0x18000485f  js      loc_18000495B
0x180004865  mov     qword ptr [rsp+2D0h+cbData], r13; unsigned __int64 *
0x18000486a  mov     edi, r13d
0x18000486d  mov     [rsp+2D0h+hKey], r13
0x180004872  mov     [rsp+2D0h+var_288], r13
0x180004877  test    r14, r14
0x18000487a  jnz     loc_180004C32
0x180004880  test    r15, r15
0x180004883  jnz     loc_180004C4B
0x180004889  mov     ecx, 104Ch; cb
0x18000488e  mov     [rsp+2D0h+var_280], r13
0x180004893  mov     rbx, r13
0x180004896  mov     [rsp+2D0h+cbData], 1048h; unsigned __int64 *
0x18000489e  call    cs:__imp_CoTaskMemAlloc
0x1800048a4  mov     r13, rax
0x1800048a7  xor     eax, eax
0x1800048a9  test    r13, r13
0x1800048ac  jz      loc_180004C65
0x1800048b2  mov     [rsp+2D0h+var_290], rax
0x1800048b7  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800048be  lea     rax, [rsp+2D0h+var_290]
0x1800048c3  mov     r9d, 101h; samDesired
0x1800048c9  xor     r8d, r8d; ulOptions
0x1800048cc  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800048d1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800048d8  mov     rsi, r13
0x1800048db  call    cs:__imp_RegOpenKeyExW
0x1800048e1  mov     r12d, eax
0x1800048e4  xor     eax, eax
0x1800048e6  test    r12d, r12d
0x1800048e9  jnz     loc_1800049B1
0x1800048ef  mov     rcx, [rsp+2D0h+var_290]; hKey
0x1800048f4  lea     rax, [rsp+2D0h+cbData]
0x1800048f9  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x1800048fe  lea     rdx, aLoginuri; "LoginUri"
0x180004905  xor     r9d, r9d; lpType
0x180004908  mov     [rsp+2D0h+phkResult], r13; lpData
0x18000490d  xor     r8d, r8d; lpReserved
0x180004910  call    cs:__imp_RegQueryValueExW
0x180004916  xor     r8d, r8d
0x180004919  mov     r12d, eax
0x18000491c  test    eax, eax
0x18000491e  jz      loc_180004A65
0x180004924  jle     short loc_180004931
0x180004926  movzx   r12d, ax
0x18000492a  or      r12d, 80070000h
0x180004931  mov     r13, r8
0x180004934  mov     rcx, [rsp+2D0h+var_290]; hKey
0x180004939  call    cs:__imp_RegCloseKey
0x18000493f  test    rsi, rsi
0x180004942  jz      short loc_18000494D
0x180004944  mov     rcx, rsi; pv
0x180004947  call    cs:__imp_CoTaskMemFree
0x18000494d  test    rdi, rdi
0x180004950  jnz     loc_1800049DA
0x180004956  test    rbx, rbx
0x180004959  jnz     short loc_1800049DA
0x18000495b  test    r15, r15
0x18000495e  jz      short loc_180004969
0x180004960  mov     rcx, r15; pv
0x180004963  call    cs:__imp_CoTaskMemFree
0x180004969  test    r14, r14
0x18000496c  jz      short loc_180004977
0x18000496e  mov     rcx, r14; pv
0x180004971  call    cs:__imp_CoTaskMemFree
0x180004977  mov     eax, r12d
0x18000497a  mov     rcx, [rbp+1D0h+var_50]
0x180004981  xor     rcx, rsp; StackCookie
0x180004984  call    __security_check_cookie
0x180004989  add     rsp, 298h
0x180004990  pop     r15
0x180004992  pop     r14
0x180004994  pop     r13
0x180004996  pop     r12
0x180004998  pop     rdi
0x180004999  pop     rsi
0x18000499a  pop     rbx
0x18000499b  pop     rbp
0x18000499c  retn
0x18000499d  jle     loc_180004770
0x1800049a3  movzx   edi, ax
0x1800049a6  or      edi, 80070000h
0x1800049ac  jmp     loc_180004770
0x1800049b1  jle     short loc_1800049BE
0x1800049b3  movzx   r12d, r12w
0x1800049b7  or      r12d, 80070000h
0x1800049be  mov     r13, rax
0x1800049c1  jmp     loc_18000493F
0x1800049c6  jle     loc_180004837
0x1800049cc  movzx   edi, ax
0x1800049cf  or      edi, 80070000h
0x1800049d5  jmp     loc_180004837
0x1800049da  mov     rdx, [rsp+2D0h+hKey]; cb
0x1800049df  lea     rax, [rsp+2D0h+var_280]
0x1800049e4  mov     [rsp+2D0h+lpcbData], rax; unsigned __int16 **
0x1800049e9  mov     r9, r13; SourceSize
0x1800049ec  mov     rax, [rsp+2D0h+var_270]
0x1800049f1  mov     r8, rbx; void *
0x1800049f4  mov     rcx, rdi; this
0x1800049f7  mov     [rsp+2D0h+phkResult], rax; unsigned __int64
0x1800049fc  call    ?GetMergedAadLoginUrl@ProofOfPossessionTokenProvider@@YAJPEBG_K01PEAPEAGPEA_K@Z; ProofOfPossessionTokenProvider::GetMergedAadLoginUrl(ushort const *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *)
0x180004a01  mov     r12d, eax
0x180004a04  test    rbx, rbx
0x180004a07  jz      short loc_180004A12
0x180004a09  mov     rcx, rbx; pv
0x180004a0c  call    cs:__imp_CoTaskMemFree
0x180004a12  test    rdi, rdi
0x180004a15  jz      loc_18000495B
0x180004a1b  mov     rcx, rdi; pv
0x180004a1e  call    cs:__imp_CoTaskMemFree
0x180004a24  jmp     loc_18000495B
0x180004a29  mov     r12d, 80070057h
0x180004a2f  jmp     loc_180004977
0x180004a34  mov     ecx, [rsp+2D0h+cbData]
0x180004a38  shr     rcx, 1
0x180004a3b  lea     rdx, [rcx+1]
0x180004a3f  mov     [rsi+rcx*2], r13w
0x180004a44  lea     rdx, [rsi+rdx*2]
0x180004a48  mov     [rdx], r13w
0x180004a4c  cmp     rdx, rsi
0x180004a4f  jb      loc_180004AE5
0x180004a55  cmp     [rdx], r13w
0x180004a59  jnz     loc_180004AE5
0x180004a5f  sub     rdx, 2
0x180004a63  jmp     short loc_180004A4C
0x180004a65  mov     ecx, [rsp+2D0h+cbData]
0x180004a69  shr     rcx, 1
0x180004a6c  lea     rdx, ds:2[rcx*2]
0x180004a74  mov     [r13+rcx*2+0], r8w
0x180004a7a  add     rdx, r13
0x180004a7d  mov     [rdx], r8w
0x180004a81  cmp     rdx, r13
0x180004a84  jb      loc_180004B27
0x180004a8a  cmp     [rdx], r8w
0x180004a8e  jnz     loc_180004B27
0x180004a94  sub     rdx, 2
0x180004a98  jmp     short loc_180004A81
0x180004a9a  mov     ecx, [rsp+2D0h+cbData]
0x180004a9e  shr     rcx, 1
0x180004aa1  lea     rdx, [rcx+1]
0x180004aa5  mov     [rsi+rcx*2], r12w
0x180004aaa  lea     rdx, [rsi+rdx*2]
0x180004aae  mov     [rdx], r12w
0x180004ab2  cmp     rdx, rsi
0x180004ab5  jb      short loc_180004B06
0x180004ab7  cmp     [rdx], r12w
0x180004abb  jnz     short loc_180004B06
0x180004abd  sub     rdx, 2
0x180004ac1  jmp     short loc_180004AB2
0x180004ac3  mov     rcx, [rbp+1D8h]; this
0x180004aca  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180004ad1  mov     r9d, ebx; char *
  ... truncated ...
```
