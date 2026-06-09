# CRAGroupPolicy::GetSDFromRegistry(ushort *,ushort *,_SECURITY_DESCRIPTOR * *,void * *,void * *)

- ea: `0x14000f458`
- end: `0x14000f903`
- name: `?GetSDFromRegistry@CRAGroupPolicy@@AEAAKPEAG0PEAPEAU_SECURITY_DESCRIPTOR@@PEAPEAX2@Z`
- size: `1195`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *, unsigned __int16 *, PSECURITY_DESCRIPTOR *, PACL pSacl, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010594`
- `0x140010dc4`

## callees

- `0x14000f458`
- `0x140015240`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000f4db`
- `ADVAPI32!RegOpenKeyExW` at `0x14000f4db`
- `ADVAPI32!RegCloseKey` at `0x14000f8e7`
- `ADVAPI32!RegCloseKey` at `0x14000f8e7`
- `ADVAPI32!RegQueryValueExW` at `0x14000f52f`
- `ADVAPI32!RegQueryValueExW` at `0x14000f5b0`
- `ADVAPI32!RegQueryValueExW` at `0x14000f52f`
- `ADVAPI32!RegQueryValueExW` at `0x14000f5b0`
- `ADVAPI32!IsValidRelativeSecurityDescriptor` at `0x14000f5d3`
- `ADVAPI32!IsValidRelativeSecurityDescriptor` at `0x14000f5d3`
- `ADVAPI32!MakeAbsoluteSD` at `0x14000f650`
- `ADVAPI32!MakeAbsoluteSD` at `0x14000f7c0`
- `ADVAPI32!MakeAbsoluteSD` at `0x14000f650`
- `ADVAPI32!MakeAbsoluteSD` at `0x14000f7c0`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000f73a`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000f73a`
- `ADVAPI32!InitializeAcl` at `0x14000f761`
- `ADVAPI32!InitializeAcl` at `0x14000f761`
- `KERNEL32!GetLastError` at `0x14000f65a`
- `KERNEL32!GetLastError` at `0x14000f667`
- `KERNEL32!GetLastError` at `0x14000f744`
- `KERNEL32!GetLastError` at `0x14000f76b`
- `KERNEL32!GetLastError` at `0x14000f7ce`
- `KERNEL32!GetLastError` at `0x14000f65a`
- `KERNEL32!GetLastError` at `0x14000f667`
- `KERNEL32!GetLastError` at `0x14000f744`
- `KERNEL32!GetLastError` at `0x14000f76b`
- `KERNEL32!GetLastError` at `0x14000f7ce`
- `KERNEL32!HeapAlloc` at `0x14000f554`
- `KERNEL32!HeapAlloc` at `0x14000f68d`
- `KERNEL32!HeapAlloc` at `0x14000f6a7`
- `KERNEL32!HeapAlloc` at `0x14000f6c1`
- `KERNEL32!HeapAlloc` at `0x14000f6dc`
- `KERNEL32!HeapAlloc` at `0x14000f6f6`
- `KERNEL32!HeapAlloc` at `0x14000f554`
- `KERNEL32!HeapAlloc` at `0x14000f68d`
- `KERNEL32!HeapAlloc` at `0x14000f6a7`
- `KERNEL32!HeapAlloc` at `0x14000f6c1`
- `KERNEL32!HeapAlloc` at `0x14000f6dc`
- `KERNEL32!HeapAlloc` at `0x14000f6f6`
- `KERNEL32!GetProcessHeap` at `0x14000f546`
- `KERNEL32!GetProcessHeap` at `0x14000f67f`
- `KERNEL32!GetProcessHeap` at `0x14000f699`
- `KERNEL32!GetProcessHeap` at `0x14000f6b3`
- `KERNEL32!GetProcessHeap` at `0x14000f6ce`
- `KERNEL32!GetProcessHeap` at `0x14000f6e8`
- `KERNEL32!GetProcessHeap` at `0x14000f836`
- `KERNEL32!GetProcessHeap` at `0x14000f852`
- `KERNEL32!GetProcessHeap` at `0x14000f86e`
- `KERNEL32!GetProcessHeap` at `0x14000f88d`
- `KERNEL32!GetProcessHeap` at `0x14000f8ad`
- `KERNEL32!GetProcessHeap` at `0x14000f8ca`
- `KERNEL32!GetProcessHeap` at `0x14000f546`
- `KERNEL32!GetProcessHeap` at `0x14000f67f`
- `KERNEL32!GetProcessHeap` at `0x14000f699`
- `KERNEL32!GetProcessHeap` at `0x14000f6b3`
- `KERNEL32!GetProcessHeap` at `0x14000f6ce`
- `KERNEL32!GetProcessHeap` at `0x14000f6e8`
- `KERNEL32!GetProcessHeap` at `0x14000f836`
- `KERNEL32!GetProcessHeap` at `0x14000f852`
- `KERNEL32!GetProcessHeap` at `0x14000f86e`
- `KERNEL32!GetProcessHeap` at `0x14000f88d`
- `KERNEL32!GetProcessHeap` at `0x14000f8ad`
- `KERNEL32!GetProcessHeap` at `0x14000f8ca`
- `KERNEL32!HeapFree` at `0x14000f844`
- `KERNEL32!HeapFree` at `0x14000f860`
- `KERNEL32!HeapFree` at `0x14000f87c`
- `KERNEL32!HeapFree` at `0x14000f89b`
- `KERNEL32!HeapFree` at `0x14000f8bb`
- `KERNEL32!HeapFree` at `0x14000f8d8`
- `KERNEL32!HeapFree` at `0x14000f844`
- `KERNEL32!HeapFree` at `0x14000f860`
- `KERNEL32!HeapFree` at `0x14000f87c`
- `KERNEL32!HeapFree` at `0x14000f89b`
- `KERNEL32!HeapFree` at `0x14000f8bb`
- `KERNEL32!HeapFree` at `0x14000f8d8`

## string_xrefs

- `0x14000f4f9`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000f57c`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000f5f4`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000f7e4`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000f820`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000f4ed`: `CRAGroupPolicy::GetSDFromRegistry`
- `0x14000f562`: `CRAGroupPolicy::GetSDFromRegistry`
- `0x14000f5dd`: `CRAGroupPolicy::GetSDFromRegistry`
- `0x14000f7eb`: `CRAGroupPolicy::GetSDFromRegistry`
- `0x14000f806`: `CRAGroupPolicy::GetSDFromRegistry`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::GetSDFromRegistry(
        CRAGroupPolicy *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        PSECURITY_DESCRIPTOR *a4,
        PACL pSacl,
        void **a6)
{
  PSID *v6; // r14
  void **v7; // r13
  ACL *v8; // r12
  BYTE *v10; // rsi
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  unsigned int v13; // edi
  unsigned int v14; // r9d
  DWORD v15; // ebx
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  ACL *v21; // rbx
  DWORD LastError; // eax
  const struct _EVENT_DESCRIPTOR *v23; // rdx
  CEventLogger *v24; // rcx
  unsigned int v25; // r9d
  DWORD v26; // ebx
  HANDLE v27; // rax
  struct _SECURITY_DESCRIPTOR *v28; // rax
  DWORD v29; // ebx
  HANDLE v30; // rax
  ACL *v31; // rax
  DWORD v32; // ebx
  HANDLE v33; // rax
  ACL *v34; // rax
  DWORD v35; // ebx
  HANDLE v36; // rax
  LPVOID v37; // rax
  DWORD v38; // ebx
  HANDLE v39; // rax
  LPVOID v40; // rax
  const struct _EVENT_DESCRIPTOR *v41; // rdx
  PSECURITY_DESCRIPTOR v42; // rcx
  HANDLE v43; // rax
  HANDLE v44; // rax
  PSECURITY_DESCRIPTOR v45; // rbx
  HANDLE v46; // rax
  PSID v47; // rbx
  HANDLE v48; // rax
  PSID v49; // rbx
  HANDLE v50; // rax
  HANDLE v51; // rax
  DWORD dwSaclSize; // [rsp+68h] [rbp-19h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp-15h] BYREF
  DWORD Type; // [rsp+70h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-9h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+D8h] [rbp+57h] BYREF
  int v58; // [rsp+DCh] [rbp+5Bh]
  DWORD dwDaclSize; // [rsp+E0h] [rbp+5Fh] BYREF
  int v60; // [rsp+E4h] [rbp+63h]
  DWORD cbData; // [rsp+E8h] [rbp+67h] BYREF
  int v62; // [rsp+ECh] [rbp+6Bh]
  DWORD dwOwnerSize; // [rsp+F0h] [rbp+6Fh] BYREF

  v62 = HIDWORD(a3);
  v60 = HIDWORD(a2);
  v58 = HIDWORD(this);
  v6 = (PSID *)pSacl;
  v7 = a6;
  v8 = 0;
  dwAbsoluteSecurityDescriptorSize = 40;
  *a4 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v10 = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  *v6 = 0;
  *v7 = 0;
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Ole", 0, 1u, &hKey);
  if ( v13 )
  {
    v14 = 136;
LABEL_3:
    CEventLogger::LogError(
      v12,
      v11,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v14,
      L"CRAGroupPolicy::GetSDFromRegistry",
      0);
    goto LABEL_33;
  }
  v13 = RegQueryValueExW(hKey, L"MachineLaunchRestriction", 0, &Type, 0, &cbData);
  if ( v13 )
  {
    v14 = 148;
    goto LABEL_3;
  }
  v15 = cbData;
  ProcessHeap = GetProcessHeap();
  v10 = (BYTE *)HeapAlloc(ProcessHeap, 0, v15);
  if ( !v10 )
  {
    CEventLogger::LogError(
      v18,
      v17,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0x9Au,
      L"CRAGroupPolicy::GetSDFromRegistry",
      0x8007000E);
    v13 = 8;
    goto LABEL_33;
  }
  v13 = RegQueryValueExW(hKey, L"MachineLaunchRestriction", 0, &Type, v10, &cbData);
  if ( v13 )
  {
    v14 = 170;
    goto LABEL_3;
  }
  if ( !(unsigned int)IsValidRelativeSecurityDescriptor(v10, cbData, 15) )
  {
    CEventLogger::LogError(
      v20,
      v19,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0xB4u,
      L"CRAGroupPolicy::GetSDFromRegistry",
      0);
    v13 = 11;
    goto LABEL_33;
  }
  if ( !MakeAbsoluteSD(
          v10,
          0,
          &dwAbsoluteSecurityDescriptorSize,
          0,
          &dwDaclSize,
          0,
          &dwSaclSize,
          *v6,
          &dwOwnerSize,
          *v7,
          &dwPrimaryGroupSize)
    && GetLastError() != 122 )
  {
    v21 = 0;
    LastError = GetLastError();
    v25 = 202;
    goto LABEL_26;
  }
  v26 = dwAbsoluteSecurityDescriptorSize;
  v27 = GetProcessHeap();
  v28 = (struct _SECURITY_DESCRIPTOR *)HeapAlloc(v27, 0, v26);
  v29 = dwDaclSize;
  *a4 = v28;
  v30 = GetProcessHeap();
  v31 = (ACL *)HeapAlloc(v30, 0, v29);
  v32 = dwSaclSize;
  v8 = v31;
  v33 = GetProcessHeap();
  v34 = (ACL *)HeapAlloc(v33, 0, v32);
  v35 = dwOwnerSize;
  pSacl = v34;
  v36 = GetProcessHeap();
  v37 = HeapAlloc(v36, 0, v35);
  v38 = dwPrimaryGroupSize;
  *v6 = v37;
  v39 = GetProcessHeap();
  v40 = HeapAlloc(v39, 0, v38);
  v21 = pSacl;
  *v7 = v40;
  if ( v8 )
  {
    if ( v21 )
    {
      if ( *v6 )
      {
        if ( v40 )
        {
          v42 = *a4;
          if ( *a4 )
          {
            if ( InitializeSecurityDescriptor(v42, 1u) )
            {
              if ( InitializeAcl(v8, dwDaclSize, 2u) )
              {
                if ( MakeAbsoluteSD(
                       v10,
                       *a4,
                       &dwAbsoluteSecurityDescriptorSize,
                       v8,
                       &dwDaclSize,
                       v21,
                       &dwSaclSize,
                       *v6,
                       &dwOwnerSize,
                       *v7,
                       &dwPrimaryGroupSize) )
                {
                  goto LABEL_40;
                }
                LastError = GetLastError();
                v25 = 256;
              }
              else
              {
                LastError = GetLastError();
                v25 = 234;
              }
            }
            else
            {
              LastError = GetLastError();
              v25 = 224;
            }
LABEL_26:
            v13 = LastError;
            CEventLogger::LogError(
              v24,
              v23,
              L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
              v25,
              L"CRAGroupPolicy::GetSDFromRegistry",
              0);
            if ( v13 )
              goto LABEL_29;
LABEL_40:
            v51 = GetProcessHeap();
            HeapFree(v51, 0, v10);
            goto LABEL_41;
          }
        }
      }
    }
  }
  v13 = 8;
  CEventLogger::LogError(
    (CEventLogger *)v42,
    v41,
    L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
    0xDAu,
    L"CRAGroupPolicy::GetSDFromRegistry",
    0x8007000E);
LABEL_29:
  if ( v8 )
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v8);
  }
  if ( v21 )
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v21);
  }
LABEL_33:
  v45 = *a4;
  if ( *a4 )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, v45);
    *a4 = 0;
  }
  v47 = *v6;
  if ( *v6 )
  {
    v48 = GetProcessHeap();
    HeapFree(v48, 0, v47);
    *v6 = 0;
  }
  v49 = *v7;
  if ( *v7 )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v49);
    *v7 = 0;
  }
  if ( v10 )
    goto LABEL_40;
LABEL_41:
  if ( hKey )
    RegCloseKey(hKey);
  return v13;
}

```

## disassembly

```asm
0x14000f458  mov     rax, rsp
0x14000f45b  mov     [rax+18h], r8
0x14000f45f  mov     [rax+10h], rdx
0x14000f463  mov     [rax+8], rcx
0x14000f467  push    rbp
0x14000f468  push    rbx
0x14000f469  push    rsi
0x14000f46a  push    rdi
0x14000f46b  push    r12
0x14000f46d  push    r13
0x14000f46f  push    r14
0x14000f471  push    r15
0x14000f473  lea     rbp, [rax-4Fh]
0x14000f477  sub     rsp, 88h
0x14000f47e  mov     r14, [rbp+47h+pSacl]
0x14000f482  lea     rax, [rbp+47h+hKey]
0x14000f486  mov     r13, [rbp+47h+arg_28]
0x14000f48a  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Ole"
0x14000f491  xor     r12d, r12d
0x14000f494  mov     [rbp+47h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x14000f49b  mov     r15, r9
0x14000f49e  mov     [r9], r12
0x14000f4a1  xor     r8d, r8d; ulOptions
0x14000f4a4  mov     [rbp+47h+hKey], r12
0x14000f4a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000f4af  mov     [rbp+47h+Type], r12d
0x14000f4b3  lea     r9d, [r12+1]; samDesired
0x14000f4b8  mov     [rbp+47h+cbData], r12d
0x14000f4bc  mov     esi, r12d
0x14000f4bf  mov     [rbp+47h+dwOwnerSize], r12d
0x14000f4c3  mov     [rbp+47h+dwPrimaryGroupSize], r12d
0x14000f4c7  mov     [rbp+47h+dwDaclSize], r12d
0x14000f4cb  mov     [rbp+47h+dwSaclSize], r12d
0x14000f4cf  mov     [r14], r12
0x14000f4d2  mov     [r13+0], r12
0x14000f4d6  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000f4db  call    cs:__imp_RegOpenKeyExW
0x14000f4e1  mov     edi, eax
0x14000f4e3  test    eax, eax
0x14000f4e5  jz      short loc_14000F50F
0x14000f4e7  mov     r9d, 88h; unsigned int
0x14000f4ed  lea     rax, aCragrouppolicy_4; "CRAGroupPolicy::GetSDFromRegistry"
0x14000f4f4  mov     dword ptr [rsp+0C0h+lpcbData], r12d; unsigned int
0x14000f4f9  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f500  mov     [rsp+0C0h+phkResult], rax; unsigned __int16 *
0x14000f505  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f50a  jmp     loc_14000F866
0x14000f50f  mov     rcx, [rbp+47h+hKey]; hKey
0x14000f513  lea     rax, [rbp+47h+cbData]
0x14000f517  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x14000f51c  lea     r9, [rbp+47h+Type]; lpType
0x14000f520  xor     r8d, r8d; lpReserved
0x14000f523  mov     [rsp+0C0h+phkResult], r12; lpData
0x14000f528  lea     rdx, ValueName; "MachineLaunchRestriction"
0x14000f52f  call    cs:__imp_RegQueryValueExW
0x14000f535  mov     edi, eax
0x14000f537  test    eax, eax
0x14000f539  jz      short loc_14000F543
0x14000f53b  mov     r9d, 94h
0x14000f541  jmp     short loc_14000F4ED
0x14000f543  mov     ebx, [rbp+47h+cbData]
0x14000f546  call    cs:__imp_GetProcessHeap
0x14000f54c  mov     r8d, ebx; dwBytes
0x14000f54f  xor     edx, edx; dwFlags
0x14000f551  mov     rcx, rax; hHeap
0x14000f554  call    cs:__imp_HeapAlloc
0x14000f55a  mov     rsi, rax
0x14000f55d  test    rax, rax
0x14000f560  jnz     short loc_14000F590
0x14000f562  lea     rax, aCragrouppolicy_4; "CRAGroupPolicy::GetSDFromRegistry"
0x14000f569  mov     dword ptr [rsp+0C0h+lpcbData], 8007000Eh; unsigned int
0x14000f571  mov     r9d, 9Ah; unsigned int
0x14000f577  mov     [rsp+0C0h+phkResult], rax; unsigned __int16 *
0x14000f57c  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f583  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f588  lea     edi, [rsi+8]
0x14000f58b  jmp     loc_14000F866
0x14000f590  mov     rcx, [rbp+47h+hKey]; hKey
0x14000f594  lea     rax, [rbp+47h+cbData]
0x14000f598  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x14000f59d  lea     r9, [rbp+47h+Type]; lpType
0x14000f5a1  xor     r8d, r8d; lpReserved
0x14000f5a4  mov     [rsp+0C0h+phkResult], rsi; lpData
0x14000f5a9  lea     rdx, ValueName; "MachineLaunchRestriction"
0x14000f5b0  call    cs:__imp_RegQueryValueExW
0x14000f5b6  mov     edi, eax
0x14000f5b8  test    eax, eax
0x14000f5ba  jz      short loc_14000F5C7
0x14000f5bc  mov     r9d, 0AAh
0x14000f5c2  jmp     loc_14000F4ED
0x14000f5c7  mov     edx, [rbp+47h+cbData]
0x14000f5ca  mov     r8d, 0Fh
0x14000f5d0  mov     rcx, rsi
0x14000f5d3  call    cs:__imp_IsValidRelativeSecurityDescriptor
0x14000f5d9  test    eax, eax
0x14000f5db  jnz     short loc_14000F60A
0x14000f5dd  lea     rax, aCragrouppolicy_4; "CRAGroupPolicy::GetSDFromRegistry"
0x14000f5e4  mov     dword ptr [rsp+0C0h+lpcbData], r12d; unsigned int
0x14000f5e9  mov     r9d, 0B4h; unsigned int
0x14000f5ef  mov     [rsp+0C0h+phkResult], rax; unsigned __int16 *
0x14000f5f4  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f5fb  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f600  mov     edi, 0Bh
0x14000f605  jmp     loc_14000F866
0x14000f60a  lea     rax, [rbp+47h+dwPrimaryGroupSize]
0x14000f60e  xor     r9d, r9d; pDacl
0x14000f611  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x14000f616  lea     r8, [rbp+47h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x14000f61a  mov     rax, [r13+0]
0x14000f61e  xor     edx, edx; pAbsoluteSecurityDescriptor
0x14000f620  mov     [rsp+0C0h+pPrimaryGroup], rax; pPrimaryGroup
0x14000f625  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x14000f628  lea     rax, [rbp+47h+dwOwnerSize]
0x14000f62c  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x14000f631  mov     rax, [r14]
0x14000f634  mov     [rsp+0C0h+pOwner], rax; pOwner
0x14000f639  lea     rax, [rbp+47h+dwSaclSize]
0x14000f63d  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x14000f642  lea     rax, [rbp+47h+dwDaclSize]
0x14000f646  mov     [rsp+0C0h+lpcbData], r12; pSacl
0x14000f64b  mov     [rsp+0C0h+phkResult], rax; lpdwDaclSize
0x14000f650  call    cs:__imp_MakeAbsoluteSD
0x14000f656  test    eax, eax
0x14000f658  jnz     short loc_14000F67C
0x14000f65a  call    cs:__imp_GetLastError
0x14000f660  cmp     eax, 7Ah ; 'z'
0x14000f663  jz      short loc_14000F67C
0x14000f665  xor     ebx, ebx
0x14000f667  call    cs:__imp_GetLastError
0x14000f66d  mov     r9d, 0CAh
0x14000f673  mov     dword ptr [rsp+0C0h+lpcbData], ebx
0x14000f677  jmp     loc_14000F7E2
0x14000f67c  mov     ebx, [rbp+47h+dwAbsoluteSecurityDescriptorSize]
0x14000f67f  call    cs:__imp_GetProcessHeap
0x14000f685  mov     r8d, ebx; dwBytes
0x14000f688  xor     edx, edx; dwFlags
0x14000f68a  mov     rcx, rax; hHeap
0x14000f68d  call    cs:__imp_HeapAlloc
0x14000f693  mov     ebx, [rbp+47h+dwDaclSize]
0x14000f696  mov     [r15], rax
0x14000f699  call    cs:__imp_GetProcessHeap
0x14000f69f  mov     r8d, ebx; dwBytes
0x14000f6a2  xor     edx, edx; dwFlags
0x14000f6a4  mov     rcx, rax; hHeap
0x14000f6a7  call    cs:__imp_HeapAlloc
0x14000f6ad  mov     ebx, [rbp+47h+dwSaclSize]
0x14000f6b0  mov     r12, rax
0x14000f6b3  call    cs:__imp_GetProcessHeap
0x14000f6b9  mov     r8d, ebx; dwBytes
0x14000f6bc  xor     edx, edx; dwFlags
0x14000f6be  mov     rcx, rax; hHeap
0x14000f6c1  call    cs:__imp_HeapAlloc
0x14000f6c7  mov     ebx, [rbp+47h+dwOwnerSize]
0x14000f6ca  mov     [rbp+47h+pSacl], rax
0x14000f6ce  call    cs:__imp_GetProcessHeap
0x14000f6d4  mov     r8d, ebx; dwBytes
0x14000f6d7  xor     edx, edx; dwFlags
0x14000f6d9  mov     rcx, rax; hHeap
0x14000f6dc  call    cs:__imp_HeapAlloc
0x14000f6e2  mov     ebx, [rbp+47h+dwPrimaryGroupSize]
0x14000f6e5  mov     [r14], rax
0x14000f6e8  call    cs:__imp_GetProcessHeap
0x14000f6ee  mov     r8d, ebx; dwBytes
0x14000f6f1  xor     edx, edx; dwFlags
0x14000f6f3  mov     rcx, rax; hHeap
0x14000f6f6  call    cs:__imp_HeapAlloc
0x14000f6fc  mov     rbx, [rbp+47h+pSacl]
0x14000f700  mov     [r13+0], rax
0x14000f704  test    r12, r12
0x14000f707  jz      loc_14000F806
0x14000f70d  test    rbx, rbx
0x14000f710  jz      loc_14000F806
0x14000f716  cmp     qword ptr [r14], 0
0x14000f71a  jz      loc_14000F806
0x14000f720  test    rax, rax
0x14000f723  jz      loc_14000F806
0x14000f729  mov     rcx, [r15]; pSecurityDescriptor
0x14000f72c  test    rcx, rcx
0x14000f72f  jz      loc_14000F806
0x14000f735  mov     edx, 1; dwRevision
0x14000f73a  call    cs:__imp_InitializeSecurityDescriptor
0x14000f740  test    eax, eax
0x14000f742  jnz     short loc_14000F755
0x14000f744  call    cs:__imp_GetLastError
0x14000f74a  mov     r9d, 0E0h
0x14000f750  jmp     loc_14000F7DA
0x14000f755  mov     edx, [rbp+47h+dwDaclSize]; nAclLength
0x14000f758  mov     r8d, 2; dwAclRevision
0x14000f75e  mov     rcx, r12; pAcl
0x14000f761  call    cs:__imp_InitializeAcl
0x14000f767  test    eax, eax
0x14000f769  jnz     short loc_14000F779
0x14000f76b  call    cs:__imp_GetLastError
0x14000f771  mov     r9d, 0EAh
0x14000f777  jmp     short loc_14000F7DA
0x14000f779  mov     rdx, [r15]; pAbsoluteSecurityDescriptor
0x14000f77c  lea     rax, [rbp+47h+dwPrimaryGroupSize]
0x14000f780  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x14000f785  lea     r8, [rbp+47h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x14000f789  mov     rax, [r13+0]
0x14000f78d  mov     r9, r12; pDacl
0x14000f790  mov     [rsp+0C0h+pPrimaryGroup], rax; pPrimaryGroup
0x14000f795  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x14000f798  lea     rax, [rbp+47h+dwOwnerSize]
0x14000f79c  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x14000f7a1  mov     rax, [r14]
0x14000f7a4  mov     [rsp+0C0h+pOwner], rax; pOwner
0x14000f7a9  lea     rax, [rbp+47h+dwSaclSize]
0x14000f7ad  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x14000f7b2  lea     rax, [rbp+47h+dwDaclSize]
0x14000f7b6  mov     [rsp+0C0h+lpcbData], rbx; pSacl
0x14000f7bb  mov     [rsp+0C0h+phkResult], rax; lpdwDaclSize
0x14000f7c0  call    cs:__imp_MakeAbsoluteSD
0x14000f7c6  test    eax, eax
0x14000f7c8  jnz     loc_14000F8CA
0x14000f7ce  call    cs:__imp_GetLastError
0x14000f7d4  mov     r9d, 100h; unsigned int
0x14000f7da  mov     dword ptr [rsp+0C0h+lpcbData], 0; unsigned int
0x14000f7e2  mov     edi, eax
0x14000f7e4  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f7eb  lea     rax, aCragrouppolicy_4; "CRAGroupPolicy::GetSDFromRegistry"
0x14000f7f2  mov     [rsp+0C0h+phkResult], rax; unsigned __int16 *
0x14000f7f7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f7fc  test    edi, edi
0x14000f7fe  jz      loc_14000F8CA
0x14000f804  jmp     short loc_14000F831
0x14000f806  lea     rax, aCragrouppolicy_4; "CRAGroupPolicy::GetSDFromRegistry"
0x14000f80d  mov     dword ptr [rsp+0C0h+lpcbData], 8007000Eh; unsigned int
0x14000f815  mov     r9d, 0DAh; unsigned int
0x14000f81b  mov     [rsp+0C0h+phkResult], rax; unsigned __int16 *
0x14000f820  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f827  mov     edi, 8
0x14000f82c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f831  test    r12, r12
0x14000f834  jz      short loc_14000F84A
0x14000f836  call    cs:__imp_GetProcessHeap
0x14000f83c  mov     r8, r12; lpMem
0x14000f83f  xor     edx, edx; dwFlags
0x14000f841  mov     rcx, rax; hHeap
0x14000f844  call    cs:__imp_HeapFree
0x14000f84a  xor     r12d, r12d
0x14000f84d  test    rbx, rbx
0x14000f850  jz      short loc_14000F866
0x14000f852  call    cs:__imp_GetProcessHeap
0x14000f858  mov     r8, rbx; lpMem
0x14000f85b  xor     edx, edx; dwFlags
0x14000f85d  mov     rcx, rax; hHeap
0x14000f860  call    cs:__imp_HeapFree
0x14000f866  mov     rbx, [r15]
0x14000f869  test    rbx, rbx
0x14000f86c  jz      short loc_14000F885
0x14000f86e  call    cs:__imp_GetProcessHeap
0x14000f874  mov     r8, rbx; lpMem
0x14000f877  xor     edx, edx; dwFlags
0x14000f879  mov     rcx, rax; hHeap
0x14000f87c  call    cs:__imp_HeapFree
0x14000f882  mov     [r15], r12
0x14000f885  mov     rbx, [r14]
0x14000f888  test    rbx, rbx
0x14000f88b  jz      short loc_14000F8A4
0x14000f88d  call    cs:__imp_GetProcessHeap
0x14000f893  mov     r8, rbx; lpMem
0x14000f896  xor     edx, edx; dwFlags
0x14000f898  mov     rcx, rax; hHeap
0x14000f89b  call    cs:__imp_HeapFree
0x14000f8a1  mov     [r14], r12
0x14000f8a4  mov     rbx, [r13+0]
0x14000f8a8  test    rbx, rbx
0x14000f8ab  jz      short loc_14000F8C5
0x14000f8ad  call    cs:__imp_GetProcessHeap
0x14000f8b3  mov     r8, rbx; lpMem
0x14000f8b6  xor     edx, edx; dwFlags
0x14000f8b8  mov     rcx, rax; hHeap
0x14000f8bb  call    cs:__imp_HeapFree
0x14000f8c1  mov     [r13+0], r12
0x14000f8c5  test    rsi, rsi
0x14000f8c8  jz      short loc_14000F8DE
0x14000f8ca  call    cs:__imp_GetProcessHeap
0x14000f8d0  mov     r8, rsi; lpMem
0x14000f8d3  xor     edx, edx; dwFlags
0x14000f8d5  mov     rcx, rax; hHeap
0x14000f8d8  call    cs:__imp_HeapFree
0x14000f8de  mov     rcx, [rbp+47h+hKey]; hKey
0x14000f8e2  test    rcx, rcx
0x14000f8e5  jz      short loc_14000F8ED
0x14000f8e7  call    cs:__imp_RegCloseKey
0x14000f8ed  mov     eax, edi
0x14000f8ef  add     rsp, 88h
0x14000f8f6  pop     r15
0x14000f8f8  pop     r14
0x14000f8fa  pop     r13
0x14000f8fc  pop     r12
0x14000f8fe  pop     rdi
0x14000f8ff  pop     rsi
0x14000f900  pop     rbx
0x14000f901  pop     rbp
0x14000f902  retn
```
