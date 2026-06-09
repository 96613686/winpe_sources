# CPolicyCheck::UpdateTrustedZonePolicyFromGP(void)

- ea: `0x1800046c4`
- end: `0x180004a93`
- name: `?UpdateTrustedZonePolicyFromGP@CPolicyCheck@@QEAAXXZ`
- size: `975`
- prototype: `void __fastcall(CPolicyCheck *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004364`

## callees

- `0x1800046c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a57`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a57`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800047c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000480a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004849`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000488d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800048d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004915`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004958`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000499b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800047c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000480a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004849`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000488d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800048d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004915`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004958`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000499b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000474d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000474d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004793`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004793`

## string_xrefs

- `0x1800047c0`: `InstallTrustedOCX`
- `0x1800049e1`: `InstallTrustedOCX`
- `0x18000483f`: `InstallSignedOCX`
- `0x180004a01`: `InstallSignedOCX`
- `0x180004883`: `InstallUnSignedOCX`
- `0x180004a21`: `InstallUnSignedOCX`
- `0x180004737`: `Software\policies\Microsoft\Windows\AxInstaller\AxISURLZonePolicies`

## pseudocode

```c
void __fastcall CPolicyCheck::UpdateTrustedZonePolicyFromGP(CPolicyCheck *this)
{
  BYTE *v1; // rsi
  BYTE *v2; // r14
  BYTE *v3; // r12
  BYTE *v4; // r15
  const BYTE *v5; // rbx
  HKEY v7; // rcx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  HKEY v9; // [rsp+58h] [rbp-10h] BYREF
  DWORD Type; // [rsp+B0h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int Data; // [rsp+C0h] [rbp+58h] BYREF
  DWORD dwDisposition; // [rsp+C8h] [rbp+60h] BYREF

  v1 = (BYTE *)this + 140;
  v2 = (BYTE *)this + 144;
  hKey = 0;
  v3 = (BYTE *)this + 152;
  v9 = 0;
  v4 = (BYTE *)this + 148;
  dwDisposition = 0;
  v5 = (const BYTE *)this + 156;
  Type = 0;
  Data = 0;
  cbData = 0;
  *((_DWORD *)this + 35) = 0;
  *((_DWORD *)this + 36) = 0;
  *((_DWORD *)this + 38) = 0;
  *((_DWORD *)this + 37) = 2;
  *((_DWORD *)this + 39) = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\policies\\Microsoft\\Windows\\AxInstaller\\AxISURLZonePolicies",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_35;
  }
  RegCreateKeyExW(*((HKEY *)this + 20), L"AxISURLZonePolicies", 0, 0, 0, 0x2001Fu, 0, &v9, &dwDisposition);
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"InstallTrustedOCX", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data <= 2 )
    *(_DWORD *)v1 = Data;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"URLZone", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    *(_DWORD *)v4 = Data;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"InstallSignedOCX", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data <= 2 )
    *(_DWORD *)v2 = Data;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"InstallUnSignedOCX", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data <= 1 )
    *(_DWORD *)v3 = Data;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"IgnoreUnknownCA", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
    *(_DWORD *)v5 |= 0x100u;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"IgnoreInvalidCN", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
    *(_DWORD *)v5 |= 0x1000u;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"IgnoreInvalidCertDate", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
    *(_DWORD *)v5 |= 0x2000u;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"IgnoreWrongCertUsage", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
    *(_DWORD *)v5 |= 0x200u;
  v7 = v9;
  if ( v9 )
  {
    RegSetValueExW(v9, L"URLZone", 0, 4u, v4, 4u);
    RegSetValueExW(v9, L"InstallTrustedOCX", 0, 4u, v1, 4u);
    RegSetValueExW(v9, L"InstallSignedOCX", 0, 4u, v2, 4u);
    RegSetValueExW(v9, L"InstallUnSignedOCX", 0, 4u, v3, 4u);
    RegSetValueExW(v9, L"VerifyServerCert", 0, 4u, v5, 4u);
LABEL_35:
    v7 = v9;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v7 = v9;
  }
  if ( v7 )
    RegCloseKey(v7);
}

```

## disassembly

```asm
0x1800046c4  push    rbp
0x1800046c6  push    rbx
0x1800046c7  push    rsi
0x1800046c8  push    rdi
0x1800046c9  push    r12
0x1800046cb  push    r13
0x1800046cd  push    r14
0x1800046cf  push    r15
0x1800046d1  mov     rbp, rsp
0x1800046d4  sub     rsp, 68h
0x1800046d8  xor     r13d, r13d
0x1800046db  lea     rsi, [rcx+8Ch]
0x1800046e2  lea     r14, [rcx+90h]
0x1800046e9  mov     [rbp+hKey], r13
0x1800046ed  lea     r12, [rcx+98h]
0x1800046f4  mov     [rbp+var_10], r13
0x1800046f8  lea     r15, [rcx+94h]
0x1800046ff  mov     [rbp+dwDisposition], r13d
0x180004703  lea     rbx, [rcx+9Ch]
0x18000470a  mov     [rbp+Type], r13d
0x18000470e  mov     rdi, rcx
0x180004711  mov     [rbp+Data], r13d
0x180004715  lea     rax, [rbp+hKey]
0x180004719  mov     [rbp+cbData], r13d
0x18000471d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004724  mov     [rsi], r13d
0x180004727  mov     r9d, 20019h; samDesired
0x18000472d  mov     [r14], r13d
0x180004730  xor     r8d, r8d; ulOptions
0x180004733  mov     [r12], r13d
0x180004737  lea     rdx, aSoftwarePolici_1; "Software\\policies\\Microsoft\\Windows"...
0x18000473e  mov     dword ptr [r15], 2
0x180004745  mov     [rbx], r13d
0x180004748  mov     [rsp+68h+phkResult], rax; phkResult
0x18000474d  call    cs:__imp_RegOpenKeyExW
0x180004753  test    eax, eax
0x180004755  jnz     loc_180004A5D
0x18000475b  mov     rcx, [rdi+0A0h]; hKey
0x180004762  lea     rax, [rbp+dwDisposition]
0x180004766  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18000476b  lea     rdx, aAxisurlzonepol; "AxISURLZonePolicies"
0x180004772  lea     rax, [rbp+var_10]
0x180004776  xor     r9d, r9d; lpClass
0x180004779  mov     [rsp+68h+var_30], rax; phkResult
0x18000477e  xor     r8d, r8d; Reserved
0x180004781  mov     [rsp+68h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180004786  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18000478e  mov     dword ptr [rsp+68h+phkResult], r13d; dwOptions
0x180004793  call    cs:__imp_RegCreateKeyExW
0x180004799  mov     rcx, [rbp+hKey]; hKey
0x18000479d  lea     rax, [rbp+cbData]
0x1800047a1  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x1800047a6  lea     edi, [r13+4]
0x1800047aa  lea     rax, [rbp+Data]
0x1800047ae  mov     [rbp+Type], edi
0x1800047b1  lea     r9, [rbp+Type]; lpType
0x1800047b5  mov     [rsp+68h+phkResult], rax; lpData
0x1800047ba  xor     r8d, r8d; lpReserved
0x1800047bd  mov     [rbp+cbData], edi
0x1800047c0  lea     rdx, ValueName; "InstallTrustedOCX"
0x1800047c7  call    cs:__imp_RegQueryValueExW
0x1800047cd  test    eax, eax
0x1800047cf  jnz     short loc_1800047E0
0x1800047d1  cmp     [rbp+Type], edi
0x1800047d4  jnz     short loc_1800047E0
0x1800047d6  mov     eax, [rbp+Data]
0x1800047d9  cmp     eax, 2
0x1800047dc  ja      short loc_1800047E0
0x1800047de  mov     [rsi], eax
0x1800047e0  mov     rcx, [rbp+hKey]; hKey
0x1800047e4  lea     rax, [rbp+cbData]
0x1800047e8  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x1800047ed  lea     r9, [rbp+Type]; lpType
0x1800047f1  lea     rax, [rbp+Data]
0x1800047f5  mov     [rbp+Type], edi
0x1800047f8  xor     r8d, r8d; lpReserved
0x1800047fb  mov     [rsp+68h+phkResult], rax; lpData
0x180004800  lea     rdx, aUrlzone; "URLZone"
0x180004807  mov     [rbp+cbData], edi
0x18000480a  call    cs:__imp_RegQueryValueExW
0x180004810  test    eax, eax
0x180004812  jnz     short loc_18000481F
0x180004814  cmp     [rbp+Type], edi
0x180004817  jnz     short loc_18000481F
0x180004819  mov     eax, [rbp+Data]
0x18000481c  mov     [r15], eax
0x18000481f  mov     rcx, [rbp+hKey]; hKey
0x180004823  lea     rax, [rbp+cbData]
0x180004827  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x18000482c  lea     r9, [rbp+Type]; lpType
0x180004830  lea     rax, [rbp+Data]
0x180004834  mov     [rbp+Type], edi
0x180004837  xor     r8d, r8d; lpReserved
0x18000483a  mov     [rsp+68h+phkResult], rax; lpData
0x18000483f  lea     rdx, aInstallsignedo; "InstallSignedOCX"
0x180004846  mov     [rbp+cbData], edi
0x180004849  call    cs:__imp_RegQueryValueExW
0x18000484f  test    eax, eax
0x180004851  jnz     short loc_180004863
0x180004853  cmp     [rbp+Type], edi
0x180004856  jnz     short loc_180004863
0x180004858  mov     eax, [rbp+Data]
0x18000485b  cmp     eax, 2
0x18000485e  ja      short loc_180004863
0x180004860  mov     [r14], eax
0x180004863  mov     rcx, [rbp+hKey]; hKey
0x180004867  lea     rax, [rbp+cbData]
0x18000486b  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180004870  lea     r9, [rbp+Type]; lpType
0x180004874  lea     rax, [rbp+Data]
0x180004878  mov     [rbp+Type], edi
0x18000487b  xor     r8d, r8d; lpReserved
0x18000487e  mov     [rsp+68h+phkResult], rax; lpData
0x180004883  lea     rdx, aInstallunsigne; "InstallUnSignedOCX"
0x18000488a  mov     [rbp+cbData], edi
0x18000488d  call    cs:__imp_RegQueryValueExW
0x180004893  test    eax, eax
0x180004895  jnz     short loc_1800048A8
0x180004897  cmp     [rbp+Type], edi
0x18000489a  jnz     short loc_1800048A8
0x18000489c  mov     eax, [rbp+Data]
0x18000489f  cmp     eax, 1
0x1800048a2  ja      short loc_1800048A8
0x1800048a4  mov     [r12], eax
0x1800048a8  mov     rcx, [rbp+hKey]; hKey
0x1800048ac  lea     rax, [rbp+cbData]
0x1800048b0  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x1800048b5  lea     r9, [rbp+Type]; lpType
0x1800048b9  lea     rax, [rbp+Data]
0x1800048bd  mov     [rbp+Type], edi
0x1800048c0  xor     r8d, r8d; lpReserved
0x1800048c3  mov     [rsp+68h+phkResult], rax; lpData
0x1800048c8  lea     rdx, aIgnoreunknownc; "IgnoreUnknownCA"
0x1800048cf  mov     [rbp+cbData], edi
0x1800048d2  call    cs:__imp_RegQueryValueExW
0x1800048d8  test    eax, eax
0x1800048da  jnz     short loc_1800048EB
0x1800048dc  cmp     [rbp+Type], edi
0x1800048df  jnz     short loc_1800048EB
0x1800048e1  cmp     [rbp+Data], 1
0x1800048e5  jnz     short loc_1800048EB
0x1800048e7  bts     dword ptr [rbx], 8
0x1800048eb  mov     rcx, [rbp+hKey]; hKey
0x1800048ef  lea     rax, [rbp+cbData]
0x1800048f3  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x1800048f8  lea     r9, [rbp+Type]; lpType
0x1800048fc  lea     rax, [rbp+Data]
0x180004900  mov     [rbp+Type], edi
0x180004903  xor     r8d, r8d; lpReserved
0x180004906  mov     [rsp+68h+phkResult], rax; lpData
0x18000490b  lea     rdx, aIgnoreinvalidc; "IgnoreInvalidCN"
0x180004912  mov     [rbp+cbData], edi
0x180004915  call    cs:__imp_RegQueryValueExW
0x18000491b  test    eax, eax
0x18000491d  jnz     short loc_18000492E
0x18000491f  cmp     [rbp+Type], edi
0x180004922  jnz     short loc_18000492E
0x180004924  cmp     [rbp+Data], 1
0x180004928  jnz     short loc_18000492E
0x18000492a  bts     dword ptr [rbx], 0Ch
0x18000492e  mov     rcx, [rbp+hKey]; hKey
0x180004932  lea     rax, [rbp+cbData]
0x180004936  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x18000493b  lea     r9, [rbp+Type]; lpType
0x18000493f  lea     rax, [rbp+Data]
0x180004943  mov     [rbp+Type], edi
0x180004946  xor     r8d, r8d; lpReserved
0x180004949  mov     [rsp+68h+phkResult], rax; lpData
0x18000494e  lea     rdx, aIgnoreinvalidc_0; "IgnoreInvalidCertDate"
0x180004955  mov     [rbp+cbData], edi
0x180004958  call    cs:__imp_RegQueryValueExW
0x18000495e  test    eax, eax
0x180004960  jnz     short loc_180004971
0x180004962  cmp     [rbp+Type], edi
0x180004965  jnz     short loc_180004971
0x180004967  cmp     [rbp+Data], 1
0x18000496b  jnz     short loc_180004971
0x18000496d  bts     dword ptr [rbx], 0Dh
0x180004971  mov     rcx, [rbp+hKey]; hKey
0x180004975  lea     rax, [rbp+cbData]
0x180004979  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x18000497e  lea     r9, [rbp+Type]; lpType
0x180004982  lea     rax, [rbp+Data]
0x180004986  mov     [rbp+Type], edi
0x180004989  xor     r8d, r8d; lpReserved
0x18000498c  mov     [rsp+68h+phkResult], rax; lpData
0x180004991  lea     rdx, aIgnorewrongcer; "IgnoreWrongCertUsage"
0x180004998  mov     [rbp+cbData], edi
0x18000499b  call    cs:__imp_RegQueryValueExW
0x1800049a1  test    eax, eax
0x1800049a3  jnz     short loc_1800049B4
0x1800049a5  cmp     [rbp+Type], edi
0x1800049a8  jnz     short loc_1800049B4
0x1800049aa  cmp     [rbp+Data], 1
0x1800049ae  jnz     short loc_1800049B4
0x1800049b0  bts     dword ptr [rbx], 9
0x1800049b4  mov     rcx, [rbp+var_10]; hKey
0x1800049b8  test    rcx, rcx
0x1800049bb  jz      loc_180004A61
0x1800049c1  mov     [rsp+68h+samDesired], edi; cbData
0x1800049c5  lea     rdx, aUrlzone; "URLZone"
0x1800049cc  mov     r9d, edi; dwType
0x1800049cf  mov     [rsp+68h+phkResult], r15; lpData
0x1800049d4  xor     r8d, r8d; Reserved
0x1800049d7  call    cs:__imp_RegSetValueExW
0x1800049dd  mov     rcx, [rbp+var_10]; hKey
0x1800049e1  lea     rdx, ValueName; "InstallTrustedOCX"
0x1800049e8  mov     r9d, edi; dwType
0x1800049eb  mov     [rsp+68h+samDesired], edi; cbData
0x1800049ef  xor     r8d, r8d; Reserved
0x1800049f2  mov     [rsp+68h+phkResult], rsi; lpData
0x1800049f7  call    cs:__imp_RegSetValueExW
0x1800049fd  mov     rcx, [rbp+var_10]; hKey
0x180004a01  lea     rdx, aInstallsignedo; "InstallSignedOCX"
0x180004a08  mov     r9d, edi; dwType
0x180004a0b  mov     [rsp+68h+samDesired], edi; cbData
0x180004a0f  xor     r8d, r8d; Reserved
0x180004a12  mov     [rsp+68h+phkResult], r14; lpData
0x180004a17  call    cs:__imp_RegSetValueExW
0x180004a1d  mov     rcx, [rbp+var_10]; hKey
0x180004a21  lea     rdx, aInstallunsigne; "InstallUnSignedOCX"
0x180004a28  mov     r9d, edi; dwType
0x180004a2b  mov     [rsp+68h+samDesired], edi; cbData
0x180004a2f  xor     r8d, r8d; Reserved
0x180004a32  mov     [rsp+68h+phkResult], r12; lpData
0x180004a37  call    cs:__imp_RegSetValueExW
0x180004a3d  mov     rcx, [rbp+var_10]; hKey
0x180004a41  lea     rdx, aVerifyserverce; "VerifyServerCert"
0x180004a48  mov     r9d, edi; dwType
0x180004a4b  mov     [rsp+68h+samDesired], edi; cbData
0x180004a4f  xor     r8d, r8d; Reserved
0x180004a52  mov     [rsp+68h+phkResult], rbx; lpData
0x180004a57  call    cs:__imp_RegSetValueExW
0x180004a5d  mov     rcx, [rbp+var_10]
0x180004a61  mov     rax, [rbp+hKey]
0x180004a65  test    rax, rax
0x180004a68  jz      short loc_180004A77
0x180004a6a  mov     rcx, rax; hKey
0x180004a6d  call    cs:__imp_RegCloseKey
0x180004a73  mov     rcx, [rbp+var_10]; hKey
0x180004a77  test    rcx, rcx
0x180004a7a  jz      short loc_180004A82
0x180004a7c  call    cs:__imp_RegCloseKey
0x180004a82  add     rsp, 68h
0x180004a86  pop     r15
0x180004a88  pop     r14
0x180004a8a  pop     r13
0x180004a8c  pop     r12
0x180004a8e  pop     rdi
0x180004a8f  pop     rsi
0x180004a90  pop     rbx
0x180004a91  pop     rbp
0x180004a92  retn
```
