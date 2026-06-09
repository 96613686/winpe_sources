# InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(CInputList &,CInputDllRegKey &,bool,bool,bool)

- ea: `0x1800080d0`
- end: `0x180008a57`
- name: `?EnumCtfRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@AEAVCInputDllRegKey@@_N22@Z`
- size: `2439`
- prototype: `void __fastcall(struct CInputList *, struct CInputDllRegKey *, char, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180005500`
- `0x180006d90`
- `0x180096a78`

## callees

- `0x1800080d0`
- `0x180008b40`
- `0x18006c000`
- `0x18006ca64`
- `0x18006ca88`
- `0x18006caa0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800087c0`
- `KERNEL32!LocalAlloc` at `0x1800087c0`
- `KERNEL32!LocalFree` at `0x1800087f7`
- `KERNEL32!LocalFree` at `0x180008a4c`
- `KERNEL32!LocalFree` at `0x1800087f7`
- `KERNEL32!LocalFree` at `0x180008a4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800082cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000839b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008479`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800082cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000839b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008479`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800086cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000870a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800086cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000870a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800082f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000834d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000849f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008634`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800088d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000891d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800082f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000834d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000849f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008634`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800088d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000891d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008689`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008861`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008973`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008a0b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008689`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008861`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008973`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008a0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180008753`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800088bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800089aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180008a28`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180008753`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800088bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800089aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180008a28`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800081b9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008331`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008417`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800081b9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008331`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008417`

## pseudocode

```c
void __fastcall InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
        struct CInputList *a1,
        struct CInputDllRegKey *a2,
        char a3,
        char a4)
{
  HKEY v4; // rbx
  char v5; // r13
  LSTATUS v7; // eax
  HKEY v8; // rsi
  DWORD v9; // ebx
  LSTATUS v10; // eax
  __int64 v11; // rdx
  WCHAR *v12; // rdx
  WCHAR *v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r9
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  WCHAR *v18; // rax
  __int64 v19; // rcx
  WCHAR *v20; // r9
  const unsigned __int16 *v21; // r8
  WCHAR *v22; // rcx
  HKEY v23; // rbx
  LSTATUS v24; // eax
  HKEY v25; // rdi
  DWORD v26; // r15d
  LSTATUS v27; // eax
  __int64 v28; // rdx
  HKEY v29; // rbx
  LSTATUS v30; // eax
  HKEY v31; // rsi
  __int16 v32; // r12
  DWORD v33; // ebx
  LSTATUS v34; // eax
  __int64 v35; // rdx
  HKEY v36; // rdi
  LSTATUS v37; // eax
  LSTATUS v38; // ebx
  HKEY v39; // rsi
  unsigned int v40; // ebx
  unsigned int v41; // r15d
  __int64 v42; // rdi
  unsigned int *v43; // r13
  unsigned int *v44; // rsi
  char v45; // di
  __int64 v46; // rcx
  __int64 v47; // rbx
  __int64 v48; // rcx
  WCHAR *v49; // rdx
  __int64 v50; // r8
  _WORD *v51; // r9
  _WORD *v52; // rdx
  __int64 v53; // rcx
  WCHAR *v54; // rdx
  __int64 v55; // r8
  _WORD *v56; // r9
  _WORD *v57; // rcx
  LSTATUS v58; // eax
  __int64 v59; // rdx
  HLOCAL v60; // rax
  void *v61; // rbx
  bool v62; // zf
  unsigned int v63; // eax
  DWORD lpdwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  char v68; // [rsp+70h] [rbp-90h]
  DWORD v69; // [rsp+74h] [rbp-8Ch]
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v71; // [rsp+80h] [rbp-80h]
  HKEY v72; // [rsp+88h] [rbp-78h]
  DWORD cbData; // [rsp+90h] [rbp-70h] BYREF
  DWORD Type; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD dwDisposition; // [rsp+98h] [rbp-68h] BYREF
  DWORD v76; // [rsp+9Ch] [rbp-64h]
  HKEY v77; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v78; // [rsp+A8h] [rbp-58h]
  HKEY v79; // [rsp+B0h] [rbp-50h]
  WCHAR String[12]; // [rsp+B8h] [rbp-48h] BYREF
  BYTE Data[2]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR String2[256]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[256]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR Name[256]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v4 = (HKEY)*((_QWORD *)a2 + 1);
  v68 = a4;
  v5 = a3;
  phkResult = 0;
  hKey = 0;
  if ( v4 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &hKey) )
    v4 = hKey;
  v7 = RegOpenKeyExW(v4, &sourceString, 0, 0x20019u, &phkResult);
  if ( !v7
    || (v79 = 0, v8 = 0, v7 == 5)
    && (cchName = 0, !RegCreateKeyExW(v4, &sourceString, 0, 0, 4u, 0x20019u, 0, &phkResult, &cchName)) )
  {
    v8 = phkResult;
    v79 = phkResult;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v9 = 0;
  if ( v8 )
  {
    while ( 1 )
    {
      cchName = 256;
      v10 = RegEnumKeyExW(v8, v9, Name, &cchName, 0, 0, 0, 0);
      v11 = 255;
      if ( v10 )
        v11 = 0;
      Name[v11] = 0;
      if ( v10 )
        break;
      v12 = Name;
      cchName = v9 + 1;
      v13 = SubKey;
      v14 = 2147483646;
      v15 = 256;
      do
      {
        if ( !v14 )
          break;
        if ( !*v12 )
          break;
        *v13++ = *v12++;
        --v14;
        --v15;
      }
      while ( v15 );
      v16 = v13 - 1;
      v17 = 256;
      v18 = SubKey;
      if ( v15 )
        v16 = v13;
      *v16 = 0;
      while ( *v18 )
      {
        ++v18;
        if ( !--v17 )
          goto LABEL_27;
      }
      v19 = 2147483646;
      v20 = &Name[-v17];
      v21 = L"\\LanguageProfile";
      do
      {
        if ( !v19 )
          break;
        if ( !*v21 )
          break;
        *v20++ = *v21++;
        --v19;
        --v17;
      }
      while ( v17 );
      v22 = v20 - 1;
      if ( v17 )
        v22 = v20;
      *v22 = 0;
LABEL_27:
      phkResult = 0;
      v23 = v8;
      hKey = 0;
      if ( v8 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &hKey) )
        v23 = hKey;
      v24 = RegOpenKeyExW(v23, SubKey, 0, 0x20019u, &phkResult);
      if ( !v24
        || (v78 = 0, v25 = 0, v24 == 5)
        && (lpdwDisposition = 0, !RegCreateKeyExW(v23, SubKey, 0, 0, 4u, 0x20019u, 0, &phkResult, &lpdwDisposition)) )
      {
        v25 = phkResult;
        v78 = phkResult;
      }
      if ( hKey )
        RegCloseKey(hKey);
      v9 = cchName;
      v26 = 0;
      if ( v25 )
      {
        while ( 1 )
        {
          lpdwDisposition = 11;
          v27 = RegEnumKeyExW(v25, v26, String, &lpdwDisposition, 0, 0, 0, 0);
          v28 = 10;
          if ( v27 )
            v28 = 0;
          String[v28] = 0;
          if ( v27 )
            break;
          ++v26;
          phkResult = 0;
          v76 = v26;
          v29 = v25;
          hKey = 0;
          if ( v25 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &hKey) )
            v29 = hKey;
          v30 = RegOpenKeyExW(v29, String, 0, 0x20019u, &phkResult);
          if ( !v30
            || (v72 = 0, v31 = 0, v30 == 5)
            && (lpdwDisposition = 0, !RegCreateKeyExW(v29, String, 0, 0, 4u, 0x20019u, 0, &phkResult, &lpdwDisposition)) )
          {
            v31 = phkResult;
            v72 = phkResult;
          }
          if ( hKey )
            RegCloseKey(hKey);
          v32 = o_wcstoul_0(String, 0, 16);
          if ( v32 )
          {
            v33 = 0;
            if ( v31 )
            {
              while ( 1 )
              {
                lpdwDisposition = 256;
                v34 = RegEnumKeyExW(v31, v33, String2, &lpdwDisposition, 0, 0, 0, 0);
                v35 = 255;
                if ( v34 )
                  v35 = 0;
                String2[v35] = 0;
                if ( v34 )
                  break;
                lpdwDisposition = 1;
                v69 = v33 + 1;
                v36 = v31;
                v71 = 0;
                hKey = 0;
                v77 = 0;
                if ( v31 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &v77) )
                  v36 = v77;
                v37 = RegOpenKeyExW(v36, String2, 0, 0x20019u, &hKey);
                v38 = v37;
                if ( !v37
                  || (phkResult = 0, v39 = 0, v37 == 5)
                  && (dwDisposition = 0,
                      (v38 = RegCreateKeyExW(v36, String2, 0, 0, 4u, 0x20019u, 0, &hKey, &dwDisposition)) == 0) )
                {
                  v39 = hKey;
                  v38 = 0;
                  phkResult = hKey;
                }
                if ( v77 )
                  RegCloseKey(v77);
                if ( !v38 )
                {
                  Type = 0;
                  cbData = 4;
                  RegQueryValueExW(v39, L"Enable", 0, &Type, (LPBYTE)&lpdwDisposition, &cbData);
                  if ( v5 )
                  {
                    Type = 22;
                    cbData = 0;
                    v58 = RegQueryValueExW(v39, L"SubstituteLayout", 0, &cbData, Data, &Type);
                    v59 = 20;
                    if ( v58 )
                      v59 = 0;
                    *(_WORD *)&Data[v59] = 0;
                    if ( !v58 )
                      v71 = o_wcstoul_0((const wchar_t *)Data, 0, 16);
                  }
                }
                v40 = 0;
                v41 = *(_DWORD *)a1;
                if ( *(_DWORD *)a1 )
                  v42 = *((_QWORD *)a1 + 1);
                else
                  v42 = 0;
                v43 = (unsigned int *)((char *)a1 + 4);
                v44 = (unsigned int *)((char *)a1 + 4);
                while ( v42 )
                {
                  v44 = (unsigned int *)((char *)a1 + 4);
                  if ( v40 >= *((_DWORD *)a1 + 1) )
                    break;
                  if ( *(_WORD *)v42 == v32
                    && !wcsicmp((const wchar_t *)(v42 + 20), Name)
                    && !wcsicmp((const wchar_t *)(v42 + 98), String2) )
                  {
                    if ( a3 )
                    {
                      v63 = v71;
                      *(_BYTE *)(v42 + 17) = 1;
                      if ( v63 )
                        *(_DWORD *)(v42 + 8) = v63;
                    }
                    goto LABEL_83;
                  }
                  v41 = *(_DWORD *)a1;
                  if ( ++v40 >= *(_DWORD *)a1 )
                    v42 = 0;
                  else
                    v42 = *((_QWORD *)a1 + 1) + 700LL * v40;
                }
                v45 = a3;
                if ( a3 )
                {
                  if ( !v68 )
                    goto LABEL_83;
                  if ( lpdwDisposition )
                  {
                    v43 = v44;
                  }
                  else if ( !v71 )
                  {
                    goto LABEL_83;
                  }
                }
                if ( *v43 >= v41 )
                {
                  if ( v41 )
                    v41 *= 2;
                  else
                    v41 = 10;
                  v60 = LocalAlloc(0x40u, 700LL * v41);
                  v61 = v60;
                  if ( !v60 )
                    goto LABEL_83;
                  if ( memcpy_s_0(v60, 700LL * v41, *((const void *const *)a1 + 1), 700LL * *(unsigned int *)a1) )
                  {
                    LocalFree(v61);
                    goto LABEL_83;
                  }
                  LocalFree(*((HLOCAL *)a1 + 1));
                  v45 = a3;
                  *((_QWORD *)a1 + 1) = v61;
                  *(_DWORD *)a1 = v41;
                }
                v46 = *v43;
                *v43 = v46 + 1;
                if ( (unsigned int)v46 < v41 )
                {
                  v47 = *((_QWORD *)a1 + 1) + 700 * v46;
                  if ( v47 )
                  {
                    v48 = 2147483646;
                    v49 = Name;
                    v50 = 39;
                    v51 = (_WORD *)(v47 + 20);
                    do
                    {
                      if ( !v48 )
                        break;
                      if ( !*v49 )
                        break;
                      *v51++ = *v49++;
                      --v48;
                      --v50;
                    }
                    while ( v50 );
                    v52 = v51 - 1;
                    if ( v50 )
                      v52 = v51;
                    *v52 = 0;
                    if ( v50 )
                    {
                      v53 = 2147483646;
                      v54 = String2;
                      v55 = 39;
                      v56 = (_WORD *)(v47 + 98);
                      do
                      {
                        if ( !v53 )
                          break;
                        if ( !*v54 )
                          break;
                        *v56++ = *v54++;
                        --v53;
                        --v55;
                      }
                      while ( v55 );
                      v57 = v56 - 1;
                      if ( v55 )
                        v57 = v56;
                      *v57 = 0;
                      if ( v55 )
                      {
                        *(_WORD *)(v47 + 176) = 0;
                        *(_DWORD *)(v47 + 12) = 2;
                        v62 = lpdwDisposition == 0;
                        *(_BYTE *)(v47 + 17) = v45;
                        *(_WORD *)v47 = v32;
                        *(_BYTE *)(v47 + 16) = !v62;
                        *(_BYTE *)(v47 + 19) = InstallLayoutOrTipPrivateHelpers::IsTfCatTip((unsigned __int16 *)(v47 + 20));
                        *(_DWORD *)(v47 + 8) = v71;
                      }
                      else
                      {
                        *(_WORD *)(v47 + 98) = 0;
                      }
                    }
                    else
                    {
                      *(_WORD *)(v47 + 20) = 0;
                    }
                  }
                }
LABEL_83:
                v31 = v72;
                v33 = v69;
                v5 = a3;
                if ( phkResult )
                  RegCloseKey(phkResult);
              }
              RegCloseKey(v31);
              v25 = v78;
              v26 = v76;
            }
          }
          else if ( v31 )
          {
            RegCloseKey(v31);
          }
        }
        RegCloseKey(v25);
        v8 = v79;
        v9 = cchName;
      }
    }
    RegCloseKey(v8);
  }
}

```

## disassembly

```asm
0x1800080d0  push    rbp
0x1800080d2  push    rbx
0x1800080d3  push    rsi
0x1800080d4  push    r12
0x1800080d6  push    r13
0x1800080d8  push    r14
0x1800080da  lea     rbp, [rsp-608h]
0x1800080e2  sub     rsp, 708h
0x1800080e9  mov     rax, cs:__security_cookie
0x1800080f0  xor     rax, rsp
0x1800080f3  mov     [rbp+630h+var_40], rax
0x1800080fa  mov     rbx, [rdx+8]
0x1800080fe  xor     r12d, r12d
0x180008101  mov     [rsp+730h+var_6C0], r9b
0x180008106  movzx   r13d, r8b
0x18000810a  mov     [rsp+730h+var_6E0], r8b
0x18000810f  mov     r14, rcx
0x180008112  mov     [rsp+730h+var_6D0], r12
0x180008117  mov     [rsp+730h+hKey], r12
0x18000811c  cmp     rbx, 0FFFFFFFF80000001h
0x180008123  jz      loc_180008A1E
0x180008129  lea     rax, [rsp+730h+var_6D0]
0x18000812e  mov     r9d, 20019h; samDesired
0x180008134  xor     r8d, r8d; ulOptions
0x180008137  mov     [rsp+730h+phkResult], rax; phkResult
0x18000813c  lea     rdx, sourceString; lpSubKey
0x180008143  mov     rcx, rbx; hKey
0x180008146  call    cs:__imp_RegOpenKeyExW
0x18000814c  test    eax, eax
0x18000814e  jnz     loc_1800089BD
0x180008154  mov     rsi, [rsp+730h+var_6D0]
0x180008159  mov     [rbp+630h+var_680], rsi
0x18000815d  mov     rcx, [rsp+730h+hKey]; hKey
0x180008162  test    rcx, rcx
0x180008165  jz      short loc_180008170
0x180008167  call    cs:__imp_RegCloseKey
0x18000816d  nop     dword ptr [rax]
0x180008170  mov     ebx, r12d
0x180008173  test    rsi, rsi
0x180008176  jz      loc_1800088EB
0x18000817c  mov     [rsp+730h+arg_10], rdi
0x180008184  mov     [rsp+730h+var_30], r15
0x18000818c  mov     [rsp+730h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180008191  lea     r9, [rsp+730h+cchName]; lpcchName
0x180008196  mov     [rsp+730h+lpcchClass], r12; lpcchClass
0x18000819b  lea     r8, [rbp+630h+Name]; lpName
0x1800081a2  mov     [rsp+730h+lpClass], r12; lpClass
0x1800081a7  mov     edx, ebx; dwIndex
0x1800081a9  mov     rcx, rsi; hKey
0x1800081ac  mov     [rsp+730h+phkResult], r12; lpReserved
0x1800081b1  mov     [rsp+730h+cchName], 100h
0x1800081b9  call    cs:__imp_RegEnumKeyExW
0x1800081bf  test    eax, eax
0x1800081c1  mov     edx, 1FEh
0x1800081c6  cmovnz  rdx, r12
0x1800081ca  mov     [rbp+rdx+630h+Name], r12w
0x1800081d3  jnz     loc_1800088D2
0x1800081d9  inc     ebx
0x1800081db  lea     rdx, [rbp+630h+Name]
0x1800081e2  mov     [rsp+730h+cchName], ebx
0x1800081e6  lea     r8, [rbp+630h+SubKey]
0x1800081ed  mov     ecx, 7FFFFFFEh
0x1800081f2  mov     r9d, 100h
0x1800081f8  test    rcx, rcx
0x1800081fb  jz      short loc_18000821A
0x1800081fd  movzx   eax, word ptr [rdx]
0x180008200  test    ax, ax
0x180008203  jz      short loc_18000821A
0x180008205  mov     [r8], ax
0x180008209  add     rdx, 2
0x18000820d  add     r8, 2
0x180008211  dec     rcx
0x180008214  sub     r9, 1
0x180008218  jnz     short loc_1800081F8
0x18000821a  test    r9, r9
0x18000821d  lea     rcx, [r8-2]
0x180008221  mov     edx, 100h
0x180008226  lea     rax, [rbp+630h+SubKey]
0x18000822d  cmovnz  rcx, r8
0x180008231  mov     [rcx], r12w
0x180008235  cmp     word ptr [rax], 0
0x180008239  jz      short loc_180008247
0x18000823b  add     rax, 2
0x18000823f  sub     rdx, 1
0x180008243  jnz     short loc_180008235
0x180008245  jmp     short loc_180008298
0x180008247  lea     rax, [rdx+rdx]
0x18000824b  mov     ecx, 7FFFFFFEh
0x180008250  lea     r9, [rbp+630h+Name]
0x180008257  sub     r9, rax
0x18000825a  lea     r8, ?c_szLanguageProfile@@3QBGB; "\\LanguageProfile"
0x180008261  test    rdx, rdx
0x180008264  jz      short loc_180008289
0x180008266  test    rcx, rcx
0x180008269  jz      short loc_180008289
0x18000826b  movzx   eax, word ptr [r8]
0x18000826f  test    ax, ax
0x180008272  jz      short loc_180008289
0x180008274  mov     [r9], ax
0x180008278  add     r8, 2
0x18000827c  add     r9, 2
0x180008280  dec     rcx
0x180008283  sub     rdx, 1
0x180008287  jnz     short loc_180008266
0x180008289  test    rdx, rdx
0x18000828c  lea     rcx, [r9-2]
0x180008290  cmovnz  rcx, r9
0x180008294  mov     [rcx], r12w
0x180008298  mov     [rsp+730h+var_6D0], r12
0x18000829d  mov     rbx, rsi
0x1800082a0  mov     [rsp+730h+hKey], r12
0x1800082a5  cmp     rsi, 0FFFFFFFF80000001h
0x1800082ac  jz      loc_1800088B5
0x1800082b2  lea     rax, [rsp+730h+var_6D0]
0x1800082b7  mov     r9d, 20019h; samDesired
0x1800082bd  xor     r8d, r8d; ulOptions
0x1800082c0  mov     [rsp+730h+phkResult], rax; phkResult
0x1800082c5  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x1800082cc  mov     rcx, rbx; hKey
0x1800082cf  call    cs:__imp_RegOpenKeyExW
0x1800082d5  test    eax, eax
0x1800082d7  jnz     loc_180008813
0x1800082dd  mov     rdi, [rsp+730h+var_6D0]
0x1800082e2  mov     [rbp+630h+var_688], rdi
0x1800082e6  mov     rcx, [rsp+730h+hKey]; hKey
0x1800082eb  test    rcx, rcx
0x1800082ee  jz      short loc_1800082F6
0x1800082f0  call    cs:__imp_RegCloseKey
0x1800082f6  mov     ebx, [rsp+730h+cchName]
0x1800082fa  mov     r15d, r12d
0x1800082fd  test    rdi, rdi
0x180008300  jz      loc_18000818C
0x180008306  mov     [rsp+730h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000830b  lea     r9, [rsp+730h+var_6D8]; lpcchName
0x180008310  mov     [rsp+730h+lpcchClass], r12; lpcchClass
0x180008315  lea     r8, [rbp+630h+String]; lpName
0x180008319  mov     [rsp+730h+lpClass], r12; lpClass
0x18000831e  mov     edx, r15d; dwIndex
0x180008321  mov     rcx, rdi; hKey
0x180008324  mov     [rsp+730h+phkResult], r12; lpReserved
0x180008329  mov     [rsp+730h+var_6D8], 0Bh
0x180008331  call    cs:__imp_RegEnumKeyExW
0x180008337  test    eax, eax
0x180008339  mov     edx, 14h
0x18000833e  cmovnz  rdx, r12
0x180008342  mov     [rbp+rdx+630h+String], r12w
0x180008348  jz      short loc_180008360
0x18000834a  mov     rcx, rdi; hKey
0x18000834d  call    cs:__imp_RegCloseKey
0x180008353  mov     rsi, [rbp+630h+var_680]
0x180008357  mov     ebx, [rsp+730h+cchName]
0x18000835b  jmp     loc_18000818C
0x180008360  inc     r15d
0x180008363  mov     [rsp+730h+var_6D0], r12
0x180008368  mov     [rbp+630h+var_694], r15d
0x18000836c  mov     rbx, rdi
0x18000836f  mov     [rsp+730h+hKey], r12
0x180008374  cmp     rdi, 0FFFFFFFF80000001h
0x18000837b  jz      loc_1800089A0
0x180008381  lea     rax, [rsp+730h+var_6D0]
0x180008386  mov     r9d, 20019h; samDesired
0x18000838c  xor     r8d, r8d; ulOptions
0x18000838f  mov     [rsp+730h+phkResult], rax; phkResult
0x180008394  lea     rdx, [rbp+630h+String]; lpSubKey
0x180008398  mov     rcx, rbx; hKey
0x18000839b  call    cs:__imp_RegOpenKeyExW
0x1800083a1  test    eax, eax
0x1800083a3  jnz     loc_180008928
0x1800083a9  mov     rsi, [rsp+730h+var_6D0]
0x1800083ae  mov     [rbp+630h+var_6A8], rsi
0x1800083b2  mov     rcx, [rsp+730h+hKey]; hKey
0x1800083b7  test    rcx, rcx
0x1800083ba  jz      short loc_1800083C2
0x1800083bc  call    cs:__imp_RegCloseKey
0x1800083c2  xor     edx, edx; EndPtr
0x1800083c4  lea     rcx, [rbp+630h+String]; String
0x1800083c8  mov     r8d, 10h; Radix
0x1800083ce  call    _o_wcstoul_0
0x1800083d3  mov     r12d, eax
0x1800083d6  test    ax, ax
0x1800083d9  jz      loc_18000890B
0x1800083df  xor     ebx, ebx
0x1800083e1  test    rsi, rsi
0x1800083e4  jz      loc_180008776
0x1800083ea  xor     r15d, r15d
0x1800083ed  mov     [rsp+730h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800083f2  lea     r9, [rsp+730h+var_6D8]; lpcchName
0x1800083f7  mov     [rsp+730h+lpcchClass], r15; lpcchClass
0x1800083fc  lea     r8, [rbp+630h+String2]; lpName
0x180008400  mov     [rsp+730h+lpClass], r15; lpClass
0x180008405  mov     edx, ebx; dwIndex
0x180008407  mov     rcx, rsi; hKey
0x18000840a  mov     [rsp+730h+phkResult], r15; lpReserved
0x18000840f  mov     [rsp+730h+var_6D8], 100h
0x180008417  call    cs:__imp_RegEnumKeyExW
0x18000841d  test    eax, eax
0x18000841f  mov     edx, 1FEh
0x180008424  cmovnz  rdx, r15
0x180008428  mov     [rbp+rdx+630h+String2], r15w
0x18000842e  jnz     loc_180008765
0x180008434  inc     ebx
0x180008436  mov     [rsp+730h+var_6D8], 1
0x18000843e  mov     [rsp+730h+var_6BC], ebx
0x180008442  mov     rdi, rsi
0x180008445  mov     [rbp+630h+var_6B0], r15d
0x180008449  mov     [rsp+730h+hKey], r15
0x18000844e  mov     [rbp+630h+var_690], r15
0x180008452  cmp     rsi, 0FFFFFFFF80000001h
0x180008459  jz      loc_18000874A
0x18000845f  lea     rax, [rsp+730h+hKey]
0x180008464  mov     r9d, 20019h; samDesired
0x18000846a  xor     r8d, r8d; ulOptions
0x18000846d  mov     [rsp+730h+phkResult], rax; phkResult
0x180008472  lea     rdx, [rbp+630h+String2]; lpSubKey
0x180008476  mov     rcx, rdi; hKey
0x180008479  call    cs:__imp_RegOpenKeyExW
0x18000847f  mov     ebx, eax
0x180008481  test    eax, eax
0x180008483  jnz     loc_18000863F
0x180008489  mov     rsi, [rsp+730h+hKey]
0x18000848e  mov     ebx, r15d
0x180008491  mov     [rsp+730h+var_6D0], rsi
0x180008496  mov     rcx, [rbp+630h+var_690]; hKey
0x18000849a  test    rcx, rcx
0x18000849d  jz      short loc_1800084A5
0x18000849f  call    cs:__imp_RegCloseKey
0x1800084a5  test    ebx, ebx
0x1800084a7  jz      loc_18000869E
0x1800084ad  mov     ebx, r15d
0x1800084b0  mov     r15d, [r14]
0x1800084b3  test    r15d, r15d
0x1800084b6  jz      loc_180008A3B
0x1800084bc  mov     rdi, [r14+8]
0x1800084c0  lea     r13, [r14+4]
0x1800084c4  mov     rsi, r13
0x1800084c7  test    rdi, rdi
0x1800084ca  jz      short loc_1800084FD
0x1800084cc  cmp     ebx, [r14+4]
0x1800084d0  lea     rsi, [r14+4]
0x1800084d4  jnb     short loc_1800084FD
0x1800084d6  cmp     [rdi], r12w
0x1800084da  jz      loc_1800085DE
0x1800084e0  mov     r15d, [r14]
0x1800084e3  inc     ebx
0x1800084e5  cmp     ebx, r15d
0x1800084e8  jnb     loc_180008A42
0x1800084ee  mov     eax, ebx
0x1800084f0  imul    rdi, rax, 2BCh
0x1800084f7  add     rdi, [r14+8]
0x1800084fb  jmp     short loc_1800084C7
0x1800084fd  movzx   edi, [rsp+730h+var_6E0]
0x180008502  test    dil, dil
0x180008505  jnz     loc_18000877E
0x18000850b  cmp     [r13+0], r15d
0x18000850f  jnb     loc_1800087A3
0x180008515  mov     ecx, [r13+0]
0x180008519  lea     eax, [rcx+1]
0x18000851c  mov     [r13+0], eax
0x180008520  cmp     ecx, r15d
0x180008523  jnb     loc_180008615
0x180008529  imul    rbx, rcx, 2BCh
0x180008530  add     rbx, [r14+8]
0x180008534  jz      loc_180008615
0x18000853a  mov     ecx, 7FFFFFFEh
0x18000853f  lea     rdx, [rbp+630h+Name]
0x180008546  mov     r8d, 27h ; '''
0x18000854c  lea     r9, [rbx+14h]
0x180008550  test    rcx, rcx
0x180008553  jz      short loc_180008572
0x180008555  movzx   eax, word ptr [rdx]
0x180008558  test    ax, ax
0x18000855b  jz      short loc_180008572
0x18000855d  mov     [r9], ax
0x180008561  add     rdx, 2
0x180008565  add     r9, 2
0x180008569  dec     rcx
0x18000856c  sub     r8, 1
0x180008570  jnz     short loc_180008550
0x180008572  test    r8, r8
0x180008575  lea     rdx, [r9-2]
0x180008579  cmovnz  rdx, r9
0x18000857d  xor     r15d, r15d
0x180008580  mov     [rdx], r15w
0x180008584  test    r8, r8
0x180008587  jz      loc_180008740
0x18000858d  mov     ecx, 7FFFFFFEh
0x180008592  lea     rdx, [rbp+630h+String2]
0x180008596  mov     r8d, 27h ; '''
0x18000859c  lea     r9, [rbx+62h]
0x1800085a0  test    rcx, rcx
0x1800085a3  jz      short loc_1800085C2
0x1800085a5  movzx   eax, word ptr [rdx]
0x1800085a8  test    ax, ax
0x1800085ab  jz      short loc_1800085C2
0x1800085ad  mov     [r9], ax
0x1800085b1  add     rdx, 2
0x1800085b5  add     r9, 2
0x1800085b9  dec     rcx
0x1800085bc  sub     r8, 1
0x1800085c0  jnz     short loc_1800085A0
  ... truncated ...
```
