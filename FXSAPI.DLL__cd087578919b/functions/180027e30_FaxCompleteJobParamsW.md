# FaxCompleteJobParamsW

- ea: `0x180027e30`
- end: `0x1800289a0`
- name: `FaxCompleteJobParamsW`
- size: `2928`
- prototype: `BOOL __stdcall(PFAX_JOB_PARAMW *JobParams, PFAX_COVERPAGE_INFOW *CoverpageInfo)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027c20`

## callees

- `0x1800278e8`
- `0x180027e30`
- `0x18002bab8`
- `0x18002bb58`
- `0x18003d4ca`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002894d`
- `KERNEL32!SetLastError` at `0x180028980`
- `KERNEL32!SetLastError` at `0x18002894d`
- `KERNEL32!SetLastError` at `0x180028980`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180027ef9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180027ef9`
- `ADVAPI32!RegQueryValueExW` at `0x180027f48`
- `ADVAPI32!RegQueryValueExW` at `0x180027f93`
- `ADVAPI32!RegQueryValueExW` at `0x180027fd0`
- `ADVAPI32!RegQueryValueExW` at `0x18002800d`
- `ADVAPI32!RegQueryValueExW` at `0x18002804a`
- `ADVAPI32!RegQueryValueExW` at `0x180028084`
- `ADVAPI32!RegQueryValueExW` at `0x1800280be`
- `ADVAPI32!RegQueryValueExW` at `0x1800280f8`
- `ADVAPI32!RegQueryValueExW` at `0x180028132`
- `ADVAPI32!RegQueryValueExW` at `0x18002816c`
- `ADVAPI32!RegQueryValueExW` at `0x1800281a7`
- `ADVAPI32!RegQueryValueExW` at `0x18002826b`
- `ADVAPI32!RegQueryValueExW` at `0x1800282e8`
- `ADVAPI32!RegQueryValueExW` at `0x18002835f`
- `ADVAPI32!RegQueryValueExW` at `0x1800283d8`
- `ADVAPI32!RegQueryValueExW` at `0x18002844f`
- `ADVAPI32!RegQueryValueExW` at `0x1800284c8`
- `ADVAPI32!RegQueryValueExW` at `0x18002853f`
- `ADVAPI32!RegQueryValueExW` at `0x1800285b8`
- `ADVAPI32!RegQueryValueExW` at `0x18002862f`
- `ADVAPI32!RegQueryValueExW` at `0x1800286a8`
- `ADVAPI32!RegQueryValueExW` at `0x180028721`
- `ADVAPI32!RegQueryValueExW` at `0x18002879a`
- `ADVAPI32!RegQueryValueExW` at `0x180028813`
- `ADVAPI32!RegQueryValueExW` at `0x180028876`
- `ADVAPI32!RegQueryValueExW` at `0x1800288ed`
- `ADVAPI32!RegQueryValueExW` at `0x180027f48`
- `ADVAPI32!RegQueryValueExW` at `0x180027f93`
- `ADVAPI32!RegQueryValueExW` at `0x180027fd0`
- `ADVAPI32!RegQueryValueExW` at `0x18002800d`
- `ADVAPI32!RegQueryValueExW` at `0x18002804a`
- `ADVAPI32!RegQueryValueExW` at `0x180028084`
- `ADVAPI32!RegQueryValueExW` at `0x1800280be`
- `ADVAPI32!RegQueryValueExW` at `0x1800280f8`
- `ADVAPI32!RegQueryValueExW` at `0x180028132`
- `ADVAPI32!RegQueryValueExW` at `0x18002816c`
- `ADVAPI32!RegQueryValueExW` at `0x1800281a7`
- `ADVAPI32!RegQueryValueExW` at `0x18002826b`
- `ADVAPI32!RegQueryValueExW` at `0x1800282e8`
- `ADVAPI32!RegQueryValueExW` at `0x18002835f`
- `ADVAPI32!RegQueryValueExW` at `0x1800283d8`
- `ADVAPI32!RegQueryValueExW` at `0x18002844f`
- `ADVAPI32!RegQueryValueExW` at `0x1800284c8`
- `ADVAPI32!RegQueryValueExW` at `0x18002853f`
- `ADVAPI32!RegQueryValueExW` at `0x1800285b8`
- `ADVAPI32!RegQueryValueExW` at `0x18002862f`
- `ADVAPI32!RegQueryValueExW` at `0x1800286a8`
- `ADVAPI32!RegQueryValueExW` at `0x180028721`
- `ADVAPI32!RegQueryValueExW` at `0x18002879a`
- `ADVAPI32!RegQueryValueExW` at `0x180028813`
- `ADVAPI32!RegQueryValueExW` at `0x180028876`
- `ADVAPI32!RegQueryValueExW` at `0x1800288ed`
- `ADVAPI32!RegCloseKey` at `0x18002896a`
- `ADVAPI32!RegCloseKey` at `0x18002896a`
- `ADVAPI32!RegOpenKeyExW` at `0x180027e97`
- `ADVAPI32!RegOpenKeyExW` at `0x180027e97`

## string_xrefs

- `0x180027f87`: `Company`
- `0x18002833d`: `Company`
- `0x1800283b6`: `Company`

## pseudocode

```c
BOOL __stdcall FaxCompleteJobParamsW(PFAX_JOB_PARAMW *JobParams, PFAX_COVERPAGE_INFOW *CoverpageInfo)
{
  LSTATUS v2; // eax
  LSTATUS v3; // esi
  DWORD v4; // ecx
  BOOL v5; // r12d
  unsigned __int16 *v6; // rdi
  LSTATUS v7; // eax
  DWORD v8; // ecx
  DWORD v9; // eax
  DWORD v10; // ebx
  DWORD v11; // r14d
  DWORD v12; // eax
  DWORD v13; // ebx
  DWORD v14; // r14d
  DWORD v15; // eax
  DWORD v16; // ebx
  DWORD v17; // r14d
  DWORD v18; // eax
  DWORD v19; // ebx
  DWORD v20; // r14d
  DWORD v21; // eax
  DWORD v22; // ebx
  DWORD v23; // eax
  DWORD v24; // ebx
  DWORD v25; // eax
  DWORD v26; // ebx
  DWORD v27; // eax
  DWORD v28; // ebx
  DWORD v29; // eax
  unsigned int v30; // ebx
  DWORD v31; // eax
  DWORD v32; // r14d
  DWORD v33; // eax
  SIZE_T v34; // rcx
  _DWORD *v35; // r15
  __int64 v36; // r13
  __int64 v37; // rax
  _DWORD *v38; // r14
  void *v39; // rcx
  unsigned __int16 *v40; // rbx
  unsigned __int16 *v41; // rsi
  __int64 v42; // r12
  __int16 v43; // r11
  __int64 v44; // rax
  size_t v45; // rdx
  __int16 v46; // r11
  __int64 v47; // rax
  __int16 v48; // r11
  __int64 v49; // rax
  size_t v50; // rdx
  __int16 v51; // r11
  __int64 v52; // rax
  __int16 v53; // r11
  __int64 v54; // rax
  size_t v55; // rdx
  __int16 v56; // r11
  __int64 v57; // rax
  __int16 v58; // r11
  __int64 v59; // rax
  size_t v60; // rdx
  __int16 v61; // r11
  __int64 v62; // rax
  __int16 v63; // r11
  __int64 v64; // rax
  __int16 v65; // r11
  __int64 v66; // rax
  __int16 v67; // r11
  __int64 v68; // rax
  __int16 v69; // r11
  __int64 v70; // rax
  LSTATUS v71; // eax
  size_t v72; // rbx
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  size_t Size; // [rsp+68h] [rbp-10h]
  DWORD cbData; // [rsp+D0h] [rbp+58h] BYREF
  DWORD cbMaxValueLen; // [rsp+D8h] [rbp+60h] BYREF

  hKey = 0;
  cbData = 0;
  cbMaxValueLen = 0;
  if ( !JobParams || !CoverpageInfo )
  {
    v4 = 87;
    goto LABEL_117;
  }
  *JobParams = 0;
  *CoverpageInfo = 0;
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Fax\\UserInfo", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( (v2 & 0xFFFFFFFD) != 0 )
  {
    v4 = v2;
LABEL_117:
    SetLastError(v4);
    return 0;
  }
  v5 = 0;
  v6 = 0;
  if ( v2 )
  {
    v34 = 136;
    v30 = 240;
    goto LABEL_33;
  }
  v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
  v3 = v7;
  if ( !v7 )
  {
    v6 = (unsigned __int16 *)pMemAlloc(cbMaxValueLen + 2);
    if ( !v6 )
      goto LABEL_111;
    RegQueryValueExW(hKey, L"FullName", 0, 0, 0, &cbData);
    v9 = cbData;
    if ( cbData )
    {
      v9 = cbData + 2;
      cbData += 2;
    }
    v10 = v9 + 240;
    v11 = v9 + 136;
    RegQueryValueExW(hKey, L"Company", 0, 0, 0, &cbData);
    v12 = cbData;
    if ( cbData )
    {
      v12 = cbData + 2;
      cbData += 2;
    }
    v13 = v12 + v10;
    v14 = v12 + v11;
    RegQueryValueExW(hKey, L"Department", 0, 0, 0, &cbData);
    v15 = cbData;
    if ( cbData )
    {
      v15 = cbData + 2;
      cbData += 2;
    }
    v16 = v15 + v13;
    v17 = v15 + v14;
    RegQueryValueExW(hKey, L"FaxNumber", 0, 0, 0, &cbData);
    v18 = cbData;
    if ( cbData )
    {
      v18 = cbData + 2;
      cbData += 2;
    }
    v19 = v18 + v16;
    v20 = v18 + v17;
    RegQueryValueExW(hKey, L"Address", 0, 0, 0, &cbData);
    v21 = cbData;
    if ( cbData )
    {
      v21 = cbData + 2;
      cbData += 2;
    }
    v22 = v21 + v19;
    RegQueryValueExW(hKey, L"Title", 0, 0, 0, &cbData);
    v23 = cbData;
    if ( cbData )
    {
      v23 = cbData + 2;
      cbData += 2;
    }
    v24 = v23 + v22;
    RegQueryValueExW(hKey, L"Office", 0, 0, 0, &cbData);
    v25 = cbData;
    if ( cbData )
    {
      v25 = cbData + 2;
      cbData += 2;
    }
    v26 = v25 + v24;
    RegQueryValueExW(hKey, L"HomePhone", 0, 0, 0, &cbData);
    v27 = cbData;
    if ( cbData )
    {
      v27 = cbData + 2;
      cbData += 2;
    }
    v28 = v27 + v26;
    RegQueryValueExW(hKey, L"OfficePhone", 0, 0, 0, &cbData);
    v29 = cbData;
    if ( cbData )
    {
      v29 = cbData + 2;
      cbData += 2;
    }
    v30 = v29 + v28;
    RegQueryValueExW(hKey, L"BillingCode", 0, 0, 0, &cbData);
    v31 = cbData;
    if ( cbData )
    {
      v31 = cbData + 2;
      cbData += 2;
    }
    v32 = v31 + v20;
    RegQueryValueExW(hKey, L"Mailbox", 0, 0, 0, &cbData);
    v33 = cbData;
    if ( cbData )
    {
      v33 = cbData + 2;
      cbData += 2;
    }
    v34 = v32 + 2 * v33;
LABEL_33:
    Size = (unsigned int)v34;
    v35 = (_DWORD *)pMemAlloc(v34);
    v36 = v30;
    v37 = pMemAlloc(v30);
    v38 = (_DWORD *)v37;
    if ( v35 )
    {
      v39 = v35;
      if ( v37 )
      {
        memset_0(v35, 0, Size);
        *v35 = 136;
        v35[16] = 0;
        v35[21] = 0;
        memset_0(v38, 0, v30);
        *v38 = 240;
        if ( !v3 )
        {
          v40 = (unsigned __int16 *)(v38 + 60);
          cbData = cbMaxValueLen;
          v41 = (unsigned __int16 *)(v35 + 34);
          v42 = -1;
          if ( !RegQueryValueExW(hKey, L"FullName", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 16) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW((unsigned __int16 *)v38 + 120, (unsigned int)v36 - 240LL, v6);
            v44 = -1;
            do
              ++v44;
            while ( v40[v44] != v43 );
            v40 += v44 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"FullName", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            v45 = Size;
            *((_QWORD *)v35 + 4) = v41;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW((unsigned __int16 *)v35 + 68, v45 - 136, v6);
            v47 = -1;
            do
              ++v47;
            while ( v41[v47] != v46 );
            v41 += v47 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"Company", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 18) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v40, (unsigned __int64)v38 + v36 - (_QWORD)v40, v6);
            v49 = -1;
            do
              ++v49;
            while ( v40[v49] != v48 );
            v40 += v49 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"Company", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            v50 = Size;
            *((_QWORD *)v35 + 5) = v41;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v41, (unsigned __int64)v35 + v50 - (_QWORD)v41, v6);
            v52 = -1;
            do
              ++v52;
            while ( v41[v52] != v51 );
            v41 += v52 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"Department", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 21) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v40, (unsigned __int64)v38 + v36 - (_QWORD)v40, v6);
            v54 = -1;
            do
              ++v54;
            while ( v40[v54] != v53 );
            v40 += v54 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"Department", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            v55 = Size;
            *((_QWORD *)v35 + 6) = v41;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v41, (unsigned __int64)v35 + v55 - (_QWORD)v41, v6);
            v57 = -1;
            do
              ++v57;
            while ( v41[v57] != v56 );
            v41 += v57 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"FaxNumber", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 17) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v40, (unsigned __int64)v38 + v36 - (_QWORD)v40, v6);
            v59 = -1;
            do
              ++v59;
            while ( v40[v59] != v58 );
            v40 += v59 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"FaxNumber", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            v60 = Size;
            *((_QWORD *)v35 + 3) = v41;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v41, (unsigned __int64)v35 + v60 - (_QWORD)v41, v6);
            v62 = -1;
            do
              ++v62;
            while ( v41[v62] != v61 );
            v41 += v62 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"Address", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 19) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v40, (unsigned __int64)v38 + v36 - (_QWORD)v40, v6);
            v64 = -1;
            do
              ++v64;
            while ( v40[v64] != v63 );
            v40 += v64 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"Title", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 20) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v40, (unsigned __int64)v38 + v36 - (_QWORD)v40, v6);
            v66 = -1;
            do
              ++v66;
            while ( v40[v66] != v65 );
            v40 += v66 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"Office", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 22) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v40, (unsigned __int64)v38 + v36 - (_QWORD)v40, v6);
            v68 = -1;
            do
              ++v68;
            while ( v40[v68] != v67 );
            v40 += v68 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"HomePhone", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 23) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v40, (unsigned __int64)v38 + v36 - (_QWORD)v40, v6);
            v70 = -1;
            do
              ++v70;
            while ( v40[v70] != v69 );
            v40 += v70 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"OfficePhone", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v38 + 24) = v40;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v40, (unsigned __int64)v38 + v36 - (_QWORD)v40, v6);
          }
          cbData = cbMaxValueLen;
          v71 = RegQueryValueExW(hKey, L"BillingCode", 0, 0, (LPBYTE)v6, &cbData);
          v72 = Size;
          if ( !v71 && cbData )
          {
            *((_QWORD *)v35 + 7) = v41;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v41, (unsigned __int64)v35 + v72 - (_QWORD)v41, v6);
            do
              ++v42;
            while ( v41[v42] );
            v41 += v42 + 1;
          }
          cbData = cbMaxValueLen;
          if ( !RegQueryValueExW(hKey, L"Mailbox", 0, 0, (LPBYTE)v6, &cbData) && cbData )
          {
            *((_QWORD *)v35 + 11) = v41;
            v6[(unsigned __int64)cbData >> 1] = 0;
            StringCbCopyW(v41, (unsigned __int64)v35 + v72 - (_QWORD)v41, v6);
          }
        }
        v5 = 1;
        *JobParams = (PFAX_JOB_PARAMW)v35;
        *CoverpageInfo = (PFAX_COVERPAGE_INFOW)v38;
        goto LABEL_113;
      }
      goto LABEL_110;
    }
    if ( v37 )
    {
      v39 = (void *)v37;
LABEL_110:
      pMemFree(v39);
    }
LABEL_111:
    v8 = 8;
    goto LABEL_112;
  }
  v8 = v7;
LABEL_112:
  SetLastError(v8);
LABEL_113:
  pMemFree(v6);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180027e30  mov     [rsp-40h+arg_8], rdx
0x180027e35  mov     [rsp-40h+arg_0], rcx
0x180027e3a  push    rbp
0x180027e3b  push    rbx
0x180027e3c  push    rsi
0x180027e3d  push    rdi
0x180027e3e  push    r12
0x180027e40  push    r13
0x180027e42  push    r14
0x180027e44  push    r15
0x180027e46  mov     rbp, rsp
0x180027e49  sub     rsp, 78h
0x180027e4d  xor     r13d, r13d
0x180027e50  mov     rax, rdx
0x180027e53  mov     [rbp+hKey], r13
0x180027e57  mov     [rbp+cbData], r13d
0x180027e5b  mov     [rbp+cbMaxValueLen], r13d
0x180027e5f  test    rcx, rcx
0x180027e62  jz      loc_18002897B
0x180027e68  test    rax, rax
0x180027e6b  jz      loc_18002897B
0x180027e71  mov     [rcx], r13
0x180027e74  lea     rax, [rbp+hKey]
0x180027e78  mov     [rdx], r13
0x180027e7b  mov     r9d, 20019h; samDesired
0x180027e81  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Fax\\UserInfo"
0x180027e88  mov     [rsp+78h+phkResult], rax; phkResult
0x180027e8d  xor     r8d, r8d; ulOptions
0x180027e90  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180027e97  call    cs:__imp_RegOpenKeyExW
0x180027e9e  nop     dword ptr [rax+rax+00h]
0x180027ea3  mov     esi, eax
0x180027ea5  test    eax, 0FFFFFFFDh
0x180027eaa  jz      short loc_180027EB3
0x180027eac  mov     ecx, eax
0x180027eae  jmp     loc_180028980
0x180027eb3  mov     r12d, r13d
0x180027eb6  mov     rdi, r13
0x180027eb9  test    eax, eax
0x180027ebb  jnz     loc_1800281C6
0x180027ec1  mov     rcx, [rbp+hKey]; hKey
0x180027ec5  lea     rax, [rbp+cbMaxValueLen]
0x180027ec9  mov     [rsp+78h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180027ece  xor     r9d, r9d; lpReserved
0x180027ed1  mov     [rsp+78h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180027ed6  xor     r8d, r8d; lpcchClass
0x180027ed9  mov     [rsp+78h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180027ede  xor     edx, edx; lpClass
0x180027ee0  mov     [rsp+78h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180027ee5  mov     [rsp+78h+lpcValues], r13; lpcValues
0x180027eea  mov     [rsp+78h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180027eef  mov     [rsp+78h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180027ef4  mov     [rsp+78h+phkResult], r13; lpcSubKeys
0x180027ef9  call    cs:__imp_RegQueryInfoKeyW
0x180027f00  nop     dword ptr [rax+rax+00h]
0x180027f05  mov     esi, eax
0x180027f07  test    eax, eax
0x180027f09  jz      short loc_180027F12
0x180027f0b  mov     ecx, eax
0x180027f0d  jmp     loc_18002894D
0x180027f12  mov     ecx, [rbp+cbMaxValueLen]
0x180027f15  add     ecx, 2; dwBytes
0x180027f18  call    pMemAlloc
0x180027f1d  mov     rdi, rax
0x180027f20  test    rax, rax
0x180027f23  jz      loc_180028948
0x180027f29  mov     rcx, [rbp+hKey]; hKey
0x180027f2d  lea     rax, [rbp+cbData]
0x180027f31  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180027f36  lea     rdx, ValueName; "FullName"
0x180027f3d  xor     r9d, r9d; lpType
0x180027f40  mov     [rsp+78h+phkResult], r13; lpData
0x180027f45  xor     r8d, r8d; lpReserved
0x180027f48  call    cs:__imp_RegQueryValueExW
0x180027f4f  nop     dword ptr [rax+rax+00h]
0x180027f54  mov     eax, [rbp+cbData]
0x180027f57  mov     r15d, 2
0x180027f5d  test    eax, eax
0x180027f5f  jz      short loc_180027F67
0x180027f61  add     eax, r15d
0x180027f64  mov     [rbp+cbData], eax
0x180027f67  mov     rcx, [rbp+hKey]; hKey
0x180027f6b  lea     ebx, [rax+0F0h]
0x180027f71  lea     r14d, [rax+88h]
0x180027f78  xor     r9d, r9d; lpType
0x180027f7b  lea     rax, [rbp+cbData]
0x180027f7f  xor     r8d, r8d; lpReserved
0x180027f82  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180027f87  lea     rdx, aCompany; "Company"
0x180027f8e  mov     [rsp+78h+phkResult], r13; lpData
0x180027f93  call    cs:__imp_RegQueryValueExW
0x180027f9a  nop     dword ptr [rax+rax+00h]
0x180027f9f  mov     eax, [rbp+cbData]
0x180027fa2  test    eax, eax
0x180027fa4  jz      short loc_180027FAC
0x180027fa6  add     eax, r15d
0x180027fa9  mov     [rbp+cbData], eax
0x180027fac  mov     rcx, [rbp+hKey]; hKey
0x180027fb0  lea     rdx, aDepartment; "Department"
0x180027fb7  add     ebx, eax
0x180027fb9  add     r14d, eax
0x180027fbc  lea     rax, [rbp+cbData]
0x180027fc0  xor     r9d, r9d; lpType
0x180027fc3  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180027fc8  xor     r8d, r8d; lpReserved
0x180027fcb  mov     [rsp+78h+phkResult], r13; lpData
0x180027fd0  call    cs:__imp_RegQueryValueExW
0x180027fd7  nop     dword ptr [rax+rax+00h]
0x180027fdc  mov     eax, [rbp+cbData]
0x180027fdf  test    eax, eax
0x180027fe1  jz      short loc_180027FE9
0x180027fe3  add     eax, r15d
0x180027fe6  mov     [rbp+cbData], eax
0x180027fe9  mov     rcx, [rbp+hKey]; hKey
0x180027fed  lea     rdx, aFaxnumber; "FaxNumber"
0x180027ff4  add     ebx, eax
0x180027ff6  add     r14d, eax
0x180027ff9  lea     rax, [rbp+cbData]
0x180027ffd  xor     r9d, r9d; lpType
0x180028000  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180028005  xor     r8d, r8d; lpReserved
0x180028008  mov     [rsp+78h+phkResult], r13; lpData
0x18002800d  call    cs:__imp_RegQueryValueExW
0x180028014  nop     dword ptr [rax+rax+00h]
0x180028019  mov     eax, [rbp+cbData]
0x18002801c  test    eax, eax
0x18002801e  jz      short loc_180028026
0x180028020  add     eax, r15d
0x180028023  mov     [rbp+cbData], eax
0x180028026  mov     rcx, [rbp+hKey]; hKey
0x18002802a  lea     rdx, aAddress; "Address"
0x180028031  add     ebx, eax
0x180028033  add     r14d, eax
0x180028036  lea     rax, [rbp+cbData]
0x18002803a  xor     r9d, r9d; lpType
0x18002803d  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180028042  xor     r8d, r8d; lpReserved
0x180028045  mov     [rsp+78h+phkResult], r13; lpData
0x18002804a  call    cs:__imp_RegQueryValueExW
0x180028051  nop     dword ptr [rax+rax+00h]
0x180028056  mov     eax, [rbp+cbData]
0x180028059  test    eax, eax
0x18002805b  jz      short loc_180028063
0x18002805d  add     eax, r15d
0x180028060  mov     [rbp+cbData], eax
0x180028063  mov     rcx, [rbp+hKey]; hKey
0x180028067  lea     rdx, aTitle; "Title"
0x18002806e  add     ebx, eax
0x180028070  xor     r9d, r9d; lpType
0x180028073  lea     rax, [rbp+cbData]
0x180028077  xor     r8d, r8d; lpReserved
0x18002807a  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x18002807f  mov     [rsp+78h+phkResult], r13; lpData
0x180028084  call    cs:__imp_RegQueryValueExW
0x18002808b  nop     dword ptr [rax+rax+00h]
0x180028090  mov     eax, [rbp+cbData]
0x180028093  test    eax, eax
0x180028095  jz      short loc_18002809D
0x180028097  add     eax, r15d
0x18002809a  mov     [rbp+cbData], eax
0x18002809d  mov     rcx, [rbp+hKey]; hKey
0x1800280a1  lea     rdx, aOffice; "Office"
0x1800280a8  add     ebx, eax
0x1800280aa  xor     r9d, r9d; lpType
0x1800280ad  lea     rax, [rbp+cbData]
0x1800280b1  xor     r8d, r8d; lpReserved
0x1800280b4  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800280b9  mov     [rsp+78h+phkResult], r13; lpData
0x1800280be  call    cs:__imp_RegQueryValueExW
0x1800280c5  nop     dword ptr [rax+rax+00h]
0x1800280ca  mov     eax, [rbp+cbData]
0x1800280cd  test    eax, eax
0x1800280cf  jz      short loc_1800280D7
0x1800280d1  add     eax, r15d
0x1800280d4  mov     [rbp+cbData], eax
0x1800280d7  mov     rcx, [rbp+hKey]; hKey
0x1800280db  lea     rdx, aHomephone; "HomePhone"
0x1800280e2  add     ebx, eax
0x1800280e4  xor     r9d, r9d; lpType
0x1800280e7  lea     rax, [rbp+cbData]
0x1800280eb  xor     r8d, r8d; lpReserved
0x1800280ee  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800280f3  mov     [rsp+78h+phkResult], r13; lpData
0x1800280f8  call    cs:__imp_RegQueryValueExW
0x1800280ff  nop     dword ptr [rax+rax+00h]
0x180028104  mov     eax, [rbp+cbData]
0x180028107  test    eax, eax
0x180028109  jz      short loc_180028111
0x18002810b  add     eax, r15d
0x18002810e  mov     [rbp+cbData], eax
0x180028111  mov     rcx, [rbp+hKey]; hKey
0x180028115  lea     rdx, aOfficephone; "OfficePhone"
0x18002811c  add     ebx, eax
0x18002811e  xor     r9d, r9d; lpType
0x180028121  lea     rax, [rbp+cbData]
0x180028125  xor     r8d, r8d; lpReserved
0x180028128  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x18002812d  mov     [rsp+78h+phkResult], r13; lpData
0x180028132  call    cs:__imp_RegQueryValueExW
0x180028139  nop     dword ptr [rax+rax+00h]
0x18002813e  mov     eax, [rbp+cbData]
0x180028141  test    eax, eax
0x180028143  jz      short loc_18002814B
0x180028145  add     eax, r15d
0x180028148  mov     [rbp+cbData], eax
0x18002814b  mov     rcx, [rbp+hKey]; hKey
0x18002814f  lea     rdx, aBillingcode; "BillingCode"
0x180028156  add     ebx, eax
0x180028158  xor     r9d, r9d; lpType
0x18002815b  lea     rax, [rbp+cbData]
0x18002815f  xor     r8d, r8d; lpReserved
0x180028162  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180028167  mov     [rsp+78h+phkResult], r13; lpData
0x18002816c  call    cs:__imp_RegQueryValueExW
0x180028173  nop     dword ptr [rax+rax+00h]
0x180028178  mov     eax, [rbp+cbData]
0x18002817b  test    eax, eax
0x18002817d  jz      short loc_180028185
0x18002817f  add     eax, r15d
0x180028182  mov     [rbp+cbData], eax
0x180028185  mov     rcx, [rbp+hKey]; hKey
0x180028189  lea     rdx, aMailbox; "Mailbox"
0x180028190  add     r14d, eax
0x180028193  xor     r9d, r9d; lpType
0x180028196  lea     rax, [rbp+cbData]
0x18002819a  xor     r8d, r8d; lpReserved
0x18002819d  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800281a2  mov     [rsp+78h+phkResult], r13; lpData
0x1800281a7  call    cs:__imp_RegQueryValueExW
0x1800281ae  nop     dword ptr [rax+rax+00h]
0x1800281b3  mov     eax, [rbp+cbData]
0x1800281b6  test    eax, eax
0x1800281b8  jz      short loc_1800281C0
0x1800281ba  add     eax, r15d
0x1800281bd  mov     [rbp+cbData], eax
0x1800281c0  lea     ecx, [r14+rax*2]
0x1800281c4  jmp     short loc_1800281D0
0x1800281c6  mov     ecx, 88h; dwBytes
0x1800281cb  mov     ebx, 0F0h
0x1800281d0  mov     eax, ecx
0x1800281d2  mov     [rbp+Size], rax
0x1800281d6  call    pMemAlloc
0x1800281db  mov     ecx, ebx; dwBytes
0x1800281dd  mov     r15, rax
0x1800281e0  mov     r13d, ebx
0x1800281e3  call    pMemAlloc
0x1800281e8  xor     ebx, ebx
0x1800281ea  mov     r14, rax
0x1800281ed  test    r15, r15
0x1800281f0  jz      loc_18002893B
0x1800281f6  mov     rcx, r15; void *
0x1800281f9  test    rax, rax
0x1800281fc  jz      loc_180028943
0x180028202  mov     r8, [rbp+Size]; Size
0x180028206  xor     edx, edx; Val
0x180028208  call    memset_0
0x18002820d  mov     r8d, r13d; Size
0x180028210  mov     dword ptr [r15], 88h
0x180028217  xor     edx, edx; Val
0x180028219  mov     [r15+40h], ebx
0x18002821d  mov     rcx, r14; void *
0x180028220  mov     [r15+54h], ebx
0x180028224  call    memset_0
0x180028229  mov     dword ptr [r14], 0F0h
0x180028230  test    esi, esi
0x180028232  jnz     loc_180028925
0x180028238  mov     eax, [rbp+cbMaxValueLen]
0x18002823b  lea     rdx, ValueName; "FullName"
0x180028242  mov     rcx, [rbp+hKey]; hKey
0x180028246  lea     rbx, [r14+0F0h]
0x18002824d  mov     [rbp+cbData], eax
0x180028250  lea     rsi, [r15+88h]
0x180028257  lea     rax, [rbp+cbData]
0x18002825b  xor     r9d, r9d; lpType
0x18002825e  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180028263  xor     r8d, r8d; lpReserved
0x180028266  mov     [rsp+78h+phkResult], rdi; lpData
0x18002826b  call    cs:__imp_RegQueryValueExW
0x180028272  nop     dword ptr [rax+rax+00h]
0x180028277  xor     r11d, r11d
0x18002827a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002827e  test    eax, eax
0x180028280  jnz     short loc_1800282C3
0x180028282  cmp     [rbp+cbData], r11d
0x180028286  jz      short loc_1800282C3
0x180028288  mov     [r14+80h], rbx
0x18002828f  mov     edx, r13d
0x180028292  mov     ecx, [rbp+cbData]
0x180028295  sub     rdx, rbx
0x180028298  shr     rcx, 1
0x18002829b  add     rdx, r14; unsigned __int64
0x18002829e  mov     r8, rdi; unsigned __int16 *
0x1800282a1  mov     [rdi+rcx*2], r11w
0x1800282a6  mov     rcx, rbx; unsigned __int16 *
0x1800282a9  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800282ae  mov     rax, r12
0x1800282b1  inc     rax
0x1800282b4  cmp     [rbx+rax*2], r11w
0x1800282b9  jnz     short loc_1800282B1
0x1800282bb  lea     rbx, [rbx+rax*2]
  ... truncated ...
```
