# FveRecordDeCheck(_GUID const *,unsigned __int64,int)

- ea: `0x18006d730`
- end: `0x18006e0ef`
- name: `?FveRecordDeCheck@@YAXPEBU_GUID@@_KH@Z`
- size: `2495`
- prototype: `void __fastcall(GUID *rguid, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006c39c`

## callees

- `0x18000dcc0`
- `0x18000dd60`
- `0x180034070`
- `0x1800345ec`
- `0x180034610`
- `0x180034cec`
- `0x180034d04`
- `0x180034d1c`
- `0x180034d28`
- `0x180034db8`
- `0x180034e24`
- `0x18006d730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d983`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006e01b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006e01b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006da55`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006de09`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006da55`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006de09`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006dbdd`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006dbdd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d9d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d9d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e05a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e05a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e09e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e09e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006dec8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006dec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e0b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e0b8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18006dc6b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18006dc6b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006d911`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006d911`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006d973`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006d973`

## pseudocode

```c
void __fastcall FveRecordDeCheck(GUID *rguid, __int64 a2, int a3)
{
  PSECURITY_DESCRIPTOR v4; // rcx
  unsigned int i; // ebx
  LSTATUS v6; // eax
  char *v7; // r12
  char *v8; // r14
  struct _FILETIME *v9; // r15
  unsigned int v10; // r13d
  int v11; // esi
  LSTATUS v12; // eax
  LSTATUS v13; // edi
  int v14; // eax
  DWORD v15; // ebx
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  DWORD j; // edi
  LSTATUS v20; // eax
  struct _FILETIME v21; // rbx
  unsigned int v22; // ecx
  struct _FILETIME v23; // r8
  struct _FILETIME v24; // rdx
  __int64 v25; // r14
  __int64 v26; // rsi
  __int64 v27; // rsi
  __int64 v28; // rdi
  __int64 v29; // rbx
  bool v30; // cf
  __int64 v31; // rax
  unsigned int v32; // r13d
  unsigned int v33; // ebx
  struct _FILETIME v34; // rcx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-D8h]
  REGSAM samDesireda[2]; // [rsp+28h] [rbp-D8h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  LPDWORD lpdwDisposition; // [rsp+40h] [rbp-C0h]
  LPDWORD lpcbMaxValueLen; // [rsp+48h] [rbp-B8h]
  LPDWORD lpcbSecurityDescriptor; // [rsp+50h] [rbp-B0h]
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v45; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME Buf2; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cchValueName; // [rsp+88h] [rbp-78h] BYREF
  DWORD Type; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v53; // [rsp+90h] [rbp-70h]
  DWORD v54; // [rsp+94h] [rbp-6Ch]
  int v55; // [rsp+98h] [rbp-68h]
  int v56; // [rsp+9Ch] [rbp-64h]
  char *v57; // [rsp+A0h] [rbp-60h]
  struct _FILETIME FileTime; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v61; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v62; // [rsp+D0h] [rbp-30h]
  REGSAM v63[2]; // [rsp+D8h] [rbp-28h]
  LPSECURITY_ATTRIBUTES v64; // [rsp+E0h] [rbp-20h]
  int v65; // [rsp+E8h] [rbp-18h]
  __int64 v66; // [rsp+F0h] [rbp-10h]
  int v67; // [rsp+F8h] [rbp-8h]
  __int64 v68; // [rsp+100h] [rbp+0h]
  SYSTEMTIME SystemTime; // [rsp+108h] [rbp+8h] BYREF
  struct _SYSTEMTIME v70; // [rsp+118h] [rbp+18h] BYREF
  wchar_t v71[20]; // [rsp+128h] [rbp+28h] BYREF
  wchar_t Format[40]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v73[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v74; // [rsp+1B0h] [rbp+B0h]
  __int128 v75; // [rsp+1C0h] [rbp+C0h]
  __int128 v76; // [rsp+1D0h] [rbp+D0h]
  __int128 v77; // [rsp+1E0h] [rbp+E0h]
  __int128 v78; // [rsp+1F0h] [rbp+F0h]
  __int128 v79; // [rsp+200h] [rbp+100h]
  __int128 v80; // [rsp+210h] [rbp+110h]
  int v81; // [rsp+220h] [rbp+120h]
  OLECHAR sz[40]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR SubKey[112]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR ValueName[264]; // [rsp+360h] [rbp+260h] BYREF
  wchar_t Data[259]; // [rsp+570h] [rbp+470h] BYREF
  __int16 v86; // [rsp+776h] [rbp+676h]

  wcscpy(Format, L"%04u-%02u-%02uT%02u:%02u:%02u.%03uZ");
  v56 = a3;
  v62 = a2;
  wcscpy(v71, L"%c;0016I64X");
  dwDisposition = 0;
  hKey = 0;
  v74 = *(_OWORD *)L"urrentControlSet\\Control\\BitLocker\\AutoDE\\ProvisionCheck\\";
  cValues = 0;
  *(_OWORD *)v73 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\BitLocker\\AutoDE\\ProvisionCheck\\";
  cchValueName = 0;
  v76 = *(_OWORD *)L"\\Control\\BitLocker\\AutoDE\\ProvisionCheck\\";
  cbData = 0;
  v75 = *(_OWORD *)L"ntrolSet\\Control\\BitLocker\\AutoDE\\ProvisionCheck\\";
  Buf2 = 0;
  v78 = *(_OWORD *)L"er\\AutoDE\\ProvisionCheck\\";
  ftLastWriteTime = 0;
  v77 = *(_OWORD *)L"\\BitLocker\\AutoDE\\ProvisionCheck\\";
  Type = 0;
  v80 = *(_OWORD *)L"ionCheck\\";
  v81 = *(_DWORD *)L"\\";
  v79 = *(_OWORD *)L"E\\ProvisionCheck\\";
  memset_0(sz, 0, 0x4Eu);
  memset_0(SubKey, 0, 0xD2u);
  FileTime = 0;
  v45 = 0;
  v61 = 0;
  v57 = 0;
  SystemTime = 0;
  v70 = 0;
  memset_0(ValueName, 0, 0x208u);
  memset_0(Data, 0, 0x208u);
  v59 = 24;
  v4 = 0;
  v63[0] = 983103;
  SecurityDescriptor[0] = 0;
  v64 = (LPSECURITY_ATTRIBUTES)&v59;
  v65 = 983103;
  SecurityDescriptor[1] = 0;
  v66 = 0;
  v67 = 131103;
  v68 = 0;
  if ( !rguid )
    goto LABEL_89;
  if ( StringFromGUID2(rguid, sz, 39)
    && (int)StringCchCopyW(SubKey, 0x69u, v73) >= 0
    && (int)StringCchCatW(SubKey, 0x69u, sz) >= 0 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;OICI;KR;;;WD)(A;OICI;KRKW;;;AU)(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)",
            1u,
            SecurityDescriptor,
            0) )
    {
      GetLastError();
      goto LABEL_86;
    }
    for ( i = 0; i < 3; ++i )
    {
      v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, v63[4 * i], *(&v64 + 2 * i), &hKey, &dwDisposition);
      if ( v6 != 5 )
        break;
    }
    if ( v6 )
      goto LABEL_86;
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    if ( dwDisposition == 2 )
    {
      v11 = 16;
      v55 = 16;
      v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, &ftLastWriteTime);
      while ( 1 )
      {
        v13 = v12;
        if ( v12 )
          break;
        v14 = memcmp_0(&ftLastWriteTime, &Buf2, 8u);
        v15 = cValues;
        if ( !v14 || !cValues || !v11 )
        {
          if ( !memcmp_0(&ftLastWriteTime, &Buf2, 8u) && v15 && v10 && v10 < v15 + 1 )
            goto LABEL_58;
          break;
        }
        if ( cValues + 1 < cValues || 260 * (cValues + 1) < 0x104 )
          goto LABEL_80;
        if ( v7 )
        {
          operator delete(v7);
          v15 = cValues;
        }
        if ( v8 )
        {
          operator delete(v8);
          v15 = cValues;
          v8 = 0;
        }
        if ( v9 )
        {
          operator delete(v9);
          v15 = cValues;
          v9 = 0;
        }
        v16 = 520LL * (v15 + 1);
        if ( !is_mul_ok(260 * (v15 + 1), 2u) )
          v16 = -1;
        v7 = (char *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v7 )
          goto LABEL_82;
        v17 = 520LL * (cValues + 1);
        if ( !is_mul_ok(260 * (cValues + 1), 2u) )
          v17 = -1;
        v57 = (char *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
        v8 = v57;
        if ( !v57 )
          goto LABEL_81;
        v18 = 8LL * (cValues + 1);
        if ( !is_mul_ok(cValues + 1, 8u) )
          v18 = -1;
        v9 = (struct _FILETIME *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v9 )
          goto LABEL_81;
        v10 = 0;
        for ( j = 0; ; ++j )
        {
          v54 = j;
          if ( j >= cValues )
            break;
          cchValueName = 260;
          cbData = 520;
          v20 = RegEnumValueW(hKey, j, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
          if ( v20 == 259 )
          {
            ftLastWriteTime = 0;
            break;
          }
          if ( v20 )
            goto LABEL_81;
          ValueName[259] = 0;
          v86 = 0;
          v9[v10] = (struct _FILETIME)1LL;
          if ( swscanf_s(
                 ValueName,
                 Format,
                 &SystemTime,
                 &SystemTime.wMonth,
                 &SystemTime.wDay,
                 &SystemTime.wHour,
                 &SystemTime.wMinute,
                 &SystemTime.wSecond,
                 &SystemTime.wMilliseconds) == 7
            && SystemTimeToFileTime(&SystemTime, &FileTime)
            && Type == 1
            && swscanf_s(Data, v71, &v45, 1, &v61) == 2
            && ((v45 - 43) & 0xFFFD) == 0 )
          {
            v21 = FileTime;
            v22 = 0;
            v53 = 0;
            if ( v10 )
            {
              do
              {
                if ( *(_QWORD *)&v9[v22] > *(unsigned __int64 *)&FileTime )
                  break;
                ++v22;
              }
              while ( v22 < v10 );
              v53 = v22;
            }
            v23 = (struct _FILETIME)(260 * v22);
            v24 = v23;
            Buf2 = v23;
            if ( v22 >= v10 )
            {
              v27 = v22;
              Buf2 = (struct _FILETIME)(260 * v22);
            }
            else
            {
              v25 = v10 - v22;
              v26 = v23.dwLowDateTime + 260;
              memmove_0(&v7[2 * v26], &v7[2 * *(_QWORD *)&v23], 2LL * (unsigned int)(260 * v25));
              memmove_0(&v57[2 * v26], &v57[2 * *(_QWORD *)&Buf2], 2LL * (unsigned int)(260 * v25));
              v27 = v53;
              memmove_0(&v9[v53 + 1], &v9[v53], 8 * v25);
              v24 = Buf2;
              v8 = v57;
              j = v54;
            }
            v9[v27] = v21;
            o_wcsncpy_s_0(&v7[2 * *(_QWORD *)&v24], 260, ValueName, -1);
            o_wcsncpy_s_0(&v8[2 * *(_QWORD *)&Buf2], 260, Data, -1);
            ++v10;
          }
        }
        Buf2 = ftLastWriteTime;
        v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, &ftLastWriteTime);
        v11 = --v55;
      }
      v15 = 0;
      v10 = 0;
      cValues = 0;
      if ( v7 )
      {
        operator delete(v7);
        v15 = cValues;
        v7 = 0;
      }
      if ( v8 )
      {
        operator delete(v8);
        v15 = cValues;
        v8 = 0;
      }
      if ( v9 )
      {
        operator delete(v9);
        v15 = cValues;
        v9 = 0;
      }
      if ( v13 )
        goto LABEL_80;
    }
    else
    {
      v15 = cValues;
    }
LABEL_58:
    if ( v10 >= v15 + 1 )
      goto LABEL_80;
    if ( !v15 )
    {
      v7 = (char *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v7 )
        goto LABEL_82;
      v8 = (char *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v8 )
        goto LABEL_81;
      v9 = (struct _FILETIME *)operator new[](8u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v9 )
        goto LABEL_81;
    }
    GetSystemTime(&v70);
    LODWORD(lpcbSecurityDescriptor) = v70.wMilliseconds;
    LODWORD(lpcbMaxValueLen) = v70.wSecond;
    LODWORD(lpdwDisposition) = v70.wMinute;
    LODWORD(phkResult) = v70.wHour;
    LODWORD(lpSecurityAttributes) = v70.wDay;
    samDesired[0] = v70.wMonth;
    v28 = 260 * v10;
    dwOptions[0] = v70.wYear;
    snwprintf_s(
      (wchar_t *const)&v7[2 * v28],
      0x104u,
      0x103u,
      Format,
      *(_QWORD *)dwOptions,
      *(_QWORD *)samDesired,
      lpSecurityAttributes,
      phkResult,
      lpdwDisposition,
      lpcbMaxValueLen,
      lpcbSecurityDescriptor);
    v29 = (unsigned int)(v28 + 259);
    *(_QWORD *)samDesireda = v62;
    v30 = v56 != 0;
    v56 = -v56;
    *(_WORD *)&v7[2 * v29] = 0;
    dwOptionsa[0] = v30 ? 43 : 45;
    snwprintf_s((wchar_t *const)&v8[2 * v28], 0x104u, 0x103u, v71, *(_QWORD *)dwOptionsa, *(_QWORD *)samDesireda);
    v31 = v10;
    v32 = v10 + 1;
    *(_WORD *)&v8[2 * v29] = 0;
    v9[v31] = (struct _FILETIME)-1LL;
    if ( v32 <= 0x10 )
    {
      v33 = 0;
      if ( !v32 )
        goto LABEL_80;
    }
    else
    {
      memset_0(v9, 0, 8LL * (v32 - 16));
      v33 = 0;
    }
    do
    {
      v34 = v9[v33];
      if ( v34 )
      {
        if ( v34 == -1 )
          RegSetValueExW(hKey, (LPCWSTR)&v7[520 * v33], 0, 1u, (const BYTE *)&v8[520 * v33], 0x208u);
      }
      else
      {
        RegDeleteValueW(hKey, (LPCWSTR)&v7[520 * v33]);
      }
      ++v33;
    }
    while ( v33 < v32 );
LABEL_80:
    if ( v7 )
LABEL_81:
      operator delete(v7);
LABEL_82:
    if ( v8 )
      operator delete(v8);
    if ( v9 )
      operator delete(v9);
  }
LABEL_86:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v4 = SecurityDescriptor[0];
LABEL_89:
  if ( v4 )
    LocalFree(v4);
}

```

## disassembly

```asm
0x18006d730  mov     [rsp-8+arg_10], rbx
0x18006d735  push    rbp
0x18006d736  push    rsi
0x18006d737  push    rdi
0x18006d738  push    r12
0x18006d73a  push    r13
0x18006d73c  push    r14
0x18006d73e  push    r15
0x18006d740  lea     rbp, [rsp-690h]
0x18006d748  sub     rsp, 790h
0x18006d74f  mov     rax, cs:__security_cookie
0x18006d756  xor     rax, rsp
0x18006d759  mov     [rbp+6C0h+var_40], rax
0x18006d760  movaps  xmm0, xmmword ptr cs:a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02u.%03uZ"
0x18006d767  xor     esi, esi
0x18006d769  movaps  xmm1, xmmword ptr cs:a04u02u02ut02u0+10h; "u-%02uT%02u:%02u:%02u.%03uZ"
0x18006d770  mov     rbx, rcx
0x18006d773  mov     eax, dword ptr cs:aSystemCurrentc_1+80h; "\\"
0x18006d779  lea     rcx, [rbp+6C0h+sz]; void *
0x18006d780  movaps  xmmword ptr [rbp+6C0h+Format], xmm0
0x18006d784  movaps  xmm0, xmmword ptr cs:a04u02u02ut02u0+20h; "02u:%02u:%02u.%03uZ"
0x18006d78b  movaps  [rbp+6C0h+var_660], xmm1
0x18006d78f  movaps  xmm1, xmmword ptr cs:a04u02u02ut02u0+30h; ":%02u.%03uZ"
0x18006d796  movaps  [rbp+6C0h+var_650], xmm0
0x18006d79a  movsd   xmm0, qword ptr cs:a04u02u02ut02u0+40h; "3uZ"
0x18006d7a2  movaps  [rbp+6C0h+var_640], xmm1
0x18006d7a9  movups  xmm1, xmmword ptr cs:aC0x016i64x; "%c;0x%016I64X"
0x18006d7b0  mov     [rbp+6C0h+var_724], r8d
0x18006d7b4  lea     r8d, [rsi+4Eh]; Size
0x18006d7b8  movsd   [rbp+6C0h+var_630], xmm0
0x18006d7c0  movups  xmm0, xmmword ptr cs:aC0x016i64x+0Ch; "016I64X"
0x18006d7c7  mov     [rbp+6C0h+var_6F0], rdx
0x18006d7cb  xor     edx, edx; Val
0x18006d7cd  movups  xmmword ptr [rbp+6C0h+var_698], xmm1
0x18006d7d1  mov     [rbp+6C0h+dwDisposition], esi
0x18006d7d4  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Bit"...
0x18006d7db  movups  xmmword ptr [rbp+6C0h+var_698+0Ch], xmm0
0x18006d7df  mov     [rsp+7C0h+hKey], rsi
0x18006d7e4  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+10h; "urrentControlSet\\Control\\BitLocker\\A"...
0x18006d7eb  movups  [rbp+6C0h+var_610], xmm0
0x18006d7f2  mov     [rsp+7C0h+cValues], esi
0x18006d7f6  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+30h; "\\Control\\BitLocker\\AutoDE\\Provision"...
0x18006d7fd  movups  xmmword ptr [rbp+6C0h+var_620], xmm1
0x18006d804  mov     [rbp+6C0h+cchValueName], esi
0x18006d807  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+20h; "ntrolSet\\Control\\BitLocker\\AutoDE\\P"...
0x18006d80e  movups  [rbp+6C0h+var_5F0], xmm0
0x18006d815  mov     [rbp+6C0h+cbData], esi
0x18006d818  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+50h; "er\\AutoDE\\ProvisionCheck\\"
0x18006d81f  movups  [rbp+6C0h+var_600], xmm1
0x18006d826  mov     [rsp+7C0h+Buf2], rsi
0x18006d82b  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+40h; "\\BitLocker\\AutoDE\\ProvisionCheck\\"
0x18006d832  movups  [rbp+6C0h+var_5D0], xmm0
0x18006d839  mov     qword ptr [rsp+7C0h+ftLastWriteTime.dwLowDateTime], rsi
0x18006d83e  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+70h; "ionCheck\\"
0x18006d845  movups  [rbp+6C0h+var_5E0], xmm1
0x18006d84c  mov     [rbp+6C0h+Type], esi
0x18006d84f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+60h; "E\\ProvisionCheck\\"
0x18006d856  movups  [rbp+6C0h+var_5B0], xmm0
0x18006d85d  mov     [rbp+6C0h+var_5A0], eax
0x18006d863  movups  [rbp+6C0h+var_5C0], xmm1
0x18006d86a  call    memset_0
0x18006d86f  xor     edx, edx; Val
0x18006d871  lea     rcx, [rbp+6C0h+SubKey]; void *
0x18006d878  mov     r8d, 0D2h; Size
0x18006d87e  call    memset_0
0x18006d883  xorps   xmm0, xmm0
0x18006d886  mov     qword ptr [rbp+6C0h+FileTime.dwLowDateTime], rsi
0x18006d88a  mov     edi, 208h
0x18006d88f  mov     [rsp+7C0h+var_75C], si
0x18006d894  mov     r8d, edi; Size
0x18006d897  mov     [rbp+6C0h+var_6F8], rsi
0x18006d89b  xor     edx, edx; Val
0x18006d89d  mov     [rbp+6C0h+var_720], rsi
0x18006d8a1  lea     rcx, [rbp+6C0h+ValueName]; void *
0x18006d8a8  movups  xmmword ptr [rbp+6C0h+SystemTime.wYear], xmm0
0x18006d8ac  movups  xmmword ptr [rbp+6C0h+var_6A8.wYear], xmm0
0x18006d8b0  call    memset_0
0x18006d8b5  mov     r8d, edi; Size
0x18006d8b8  lea     rcx, [rbp+6C0h+Data]; void *
0x18006d8bf  xor     edx, edx; Val
0x18006d8c1  call    memset_0
0x18006d8c6  mov     edx, 0F003Fh
0x18006d8cb  mov     [rbp+6C0h+var_710], 18h
0x18006d8d3  mov     ecx, esi
0x18006d8d5  mov     [rbp+6C0h+var_6E8], edx
0x18006d8d8  lea     rax, [rbp+6C0h+var_710]
0x18006d8dc  mov     [rbp+6C0h+SecurityDescriptor], rcx
0x18006d8e0  mov     [rbp+6C0h+var_6E0], rax
0x18006d8e4  test    rbx, rbx
0x18006d8e7  mov     [rbp+6C0h+var_6D8], edx
0x18006d8ea  mov     [rbp+6C0h+var_700], rsi
0x18006d8ee  mov     [rbp+6C0h+var_6D0], rsi
0x18006d8f2  mov     [rbp+6C0h+var_6C8], 2001Fh
0x18006d8f9  mov     [rbp+6C0h+var_6C0], rsi
0x18006d8fd  jz      loc_18006E0B3
0x18006d903  lea     r8d, [rsi+27h]; cchMax
0x18006d907  mov     rcx, rbx; rguid
0x18006d90a  lea     rdx, [rbp+6C0h+sz]; lpsz
0x18006d911  call    cs:__imp_StringFromGUID2
0x18006d918  nop     dword ptr [rax+rax+00h]
0x18006d91d  test    eax, eax
0x18006d91f  jz      loc_18006E094
0x18006d925  lea     ebx, [rsi+69h]
0x18006d928  mov     edx, ebx; unsigned __int64
0x18006d92a  lea     r8, [rbp+6C0h+var_620]; unsigned __int16 *
0x18006d931  lea     rcx, [rbp+6C0h+SubKey]; unsigned __int16 *
0x18006d938  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006d93d  test    eax, eax
0x18006d93f  js      loc_18006E094
0x18006d945  lea     r8, [rbp+6C0h+sz]; unsigned __int16 *
0x18006d94c  mov     edx, ebx; unsigned __int64
0x18006d94e  lea     rcx, [rbp+6C0h+SubKey]; unsigned __int16 *
0x18006d955  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006d95a  test    eax, eax
0x18006d95c  js      loc_18006E094
0x18006d962  xor     r9d, r9d; SecurityDescriptorSize
0x18006d965  lea     r8, [rbp+6C0h+SecurityDescriptor]; SecurityDescriptor
0x18006d969  lea     edx, [rsi+1]; StringSDRevision
0x18006d96c  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;KR;;;WD)(A;OICI;KRKW;;;AU)(A;"...
0x18006d973  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006d97a  nop     dword ptr [rax+rax+00h]
0x18006d97f  test    eax, eax
0x18006d981  jnz     short loc_18006D994
0x18006d983  call    cs:__imp_GetLastError
0x18006d98a  nop     dword ptr [rax+rax+00h]
0x18006d98f  jmp     loc_18006E094
0x18006d994  mov     ebx, esi
0x18006d996  lea     rax, [rbp+6C0h+dwDisposition]
0x18006d99a  mov     ecx, ebx
0x18006d99c  mov     [rsp+7C0h+lpdwDisposition], rax; lpdwDisposition
0x18006d9a1  lea     rdx, [rbp+6C0h+SubKey]; lpSubKey
0x18006d9a8  add     rcx, rcx
0x18006d9ab  lea     rax, [rsp+7C0h+hKey]
0x18006d9b0  mov     [rsp+7C0h+phkResult], rax; phkResult
0x18006d9b5  xor     r9d, r9d; lpClass
0x18006d9b8  xor     r8d, r8d; Reserved
0x18006d9bb  mov     rax, [rbp+rcx*8+6C0h+var_6E0]
0x18006d9c0  mov     [rsp+7C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18006d9c5  mov     eax, [rbp+rcx*8+6C0h+var_6E8]
0x18006d9c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d9d0  mov     [rsp+7C0h+samDesired], eax; samDesired
0x18006d9d4  mov     [rsp+7C0h+dwOptions], esi; dwOptions
0x18006d9d8  call    cs:__imp_RegCreateKeyExW
0x18006d9df  nop     dword ptr [rax+rax+00h]
0x18006d9e4  cmp     eax, 5
0x18006d9e7  jnz     short loc_18006D9F0
0x18006d9e9  inc     ebx
0x18006d9eb  cmp     ebx, 3
0x18006d9ee  jb      short loc_18006D996
0x18006d9f0  test    eax, eax
0x18006d9f2  jnz     loc_18006E094
0x18006d9f8  cmp     [rbp+6C0h+dwDisposition], 2
0x18006d9fc  mov     r12, rsi
0x18006d9ff  mov     r14, rsi
0x18006da02  mov     r15, rsi
0x18006da05  mov     r13d, esi
0x18006da08  jnz     loc_18006DFF1
0x18006da0e  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18006da13  lea     esi, [rax+10h]
0x18006da16  xor     ebx, ebx
0x18006da18  mov     [rbp+6C0h+var_728], esi
0x18006da1b  lea     rax, [rsp+7C0h+ftLastWriteTime]
0x18006da20  xor     r9d, r9d; lpReserved
0x18006da23  mov     [rsp+7C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18006da28  xor     r8d, r8d; lpcchClass
0x18006da2b  mov     [rsp+7C0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18006da30  lea     rax, [rsp+7C0h+cValues]
0x18006da35  mov     [rsp+7C0h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18006da3a  xor     edx, edx; lpClass
0x18006da3c  mov     [rsp+7C0h+lpdwDisposition], rbx; lpcbMaxValueNameLen
0x18006da41  mov     [rsp+7C0h+phkResult], rax; lpcValues
0x18006da46  mov     [rsp+7C0h+lpSecurityAttributes], rbx; lpcbMaxClassLen
0x18006da4b  mov     qword ptr [rsp+7C0h+samDesired], rbx; lpcbMaxSubKeyLen
0x18006da50  mov     qword ptr [rsp+7C0h+dwOptions], rbx; lpcSubKeys
0x18006da55  call    cs:__imp_RegQueryInfoKeyW
0x18006da5c  nop     dword ptr [rax+rax+00h]
0x18006da61  mov     edi, eax
0x18006da63  test    eax, eax
0x18006da65  jnz     loc_18006DF9D
0x18006da6b  lea     r8d, [rax+8]; Size
0x18006da6f  lea     rdx, [rsp+7C0h+Buf2]; Buf2
0x18006da74  lea     rcx, [rsp+7C0h+ftLastWriteTime]; Buf1
0x18006da79  call    memcmp_0
0x18006da7e  mov     ebx, [rsp+7C0h+cValues]
0x18006da82  test    eax, eax
0x18006da84  jz      loc_18006DE22
0x18006da8a  test    ebx, ebx
0x18006da8c  jz      loc_18006DE22
0x18006da92  test    esi, esi
0x18006da94  jz      loc_18006DE22
0x18006da9a  lea     eax, [rbx+1]
0x18006da9d  xor     esi, esi
0x18006da9f  cmp     eax, ebx
0x18006daa1  jb      loc_18006E06D
0x18006daa7  lea     eax, [rbx+1]
0x18006daaa  imul    edx, eax, 104h
0x18006dab0  cmp     edx, 104h
0x18006dab6  jb      loc_18006E06D
0x18006dabc  test    r12, r12
0x18006dabf  jz      short loc_18006DACD
0x18006dac1  mov     rcx, r12; Block
0x18006dac4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006dac9  mov     ebx, [rsp+7C0h+cValues]
0x18006dacd  test    r14, r14
0x18006dad0  jz      short loc_18006DAE1
0x18006dad2  mov     rcx, r14; Block
0x18006dad5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006dada  mov     ebx, [rsp+7C0h+cValues]
0x18006dade  mov     r14, rsi
0x18006dae1  test    r15, r15
0x18006dae4  jz      short loc_18006DAF5
0x18006dae6  mov     rcx, r15; Block
0x18006dae9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006daee  mov     ebx, [rsp+7C0h+cValues]
0x18006daf2  mov     r15, rsi
0x18006daf5  lea     eax, [rbx+1]
0x18006daf8  mov     r13d, 2
0x18006dafe  imul    edx, eax, 104h
0x18006db04  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006db0b  mov     eax, r13d
0x18006db0e  lea     rdi, [r13-3]
0x18006db12  mul     rdx
0x18006db15  mov     rdx, rbx; struct std::nothrow_t *
0x18006db18  cmovb   rax, rdi
0x18006db1c  mov     rcx, rax; unsigned __int64
0x18006db1f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006db24  mov     r12, rax
0x18006db27  test    rax, rax
0x18006db2a  jz      loc_18006E07A
0x18006db30  mov     eax, [rsp+7C0h+cValues]
0x18006db34  inc     eax
0x18006db36  imul    edx, eax, 104h
0x18006db3c  mov     eax, r13d
0x18006db3f  mul     rdx
0x18006db42  mov     rdx, rbx; struct std::nothrow_t *
0x18006db45  cmovb   rax, rdi
0x18006db49  mov     rcx, rax; unsigned __int64
0x18006db4c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006db51  mov     [rbp+6C0h+var_720], rax
0x18006db55  mov     r14, rax
0x18006db58  test    rax, rax
0x18006db5b  jz      loc_18006E072
0x18006db61  mov     ecx, [rsp+7C0h+cValues]
0x18006db65  lea     eax, [rdi+9]
0x18006db68  inc     ecx
0x18006db6a  mul     rcx
0x18006db6d  mov     rdx, rbx; struct std::nothrow_t *
0x18006db70  cmovb   rax, rdi
0x18006db74  mov     rcx, rax; unsigned __int64
0x18006db77  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006db7c  mov     r15, rax
0x18006db7f  test    rax, rax
0x18006db82  jz      loc_18006E072
0x18006db88  mov     r13d, esi
0x18006db8b  mov     edi, esi
0x18006db8d  mov     [rbp+6C0h+var_72C], edi
0x18006db90  cmp     edi, [rsp+7C0h+cValues]
0x18006db94  jnb     loc_18006DDC0
0x18006db9a  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18006db9f  lea     rax, [rbp+6C0h+cbData]
0x18006dba3  mov     [rsp+7C0h+phkResult], rax; lpcbData
0x18006dba8  lea     r9, [rbp+6C0h+cchValueName]; lpcchValueName
0x18006dbac  lea     rax, [rbp+6C0h+Data]
0x18006dbb3  mov     [rbp+6C0h+cchValueName], 104h
0x18006dbba  mov     [rsp+7C0h+lpSecurityAttributes], rax; lpData
0x18006dbbf  lea     r8, [rbp+6C0h+ValueName]; lpValueName
0x18006dbc6  lea     rax, [rbp+6C0h+Type]
0x18006dbca  mov     [rbp+6C0h+cbData], 208h
0x18006dbd1  mov     qword ptr [rsp+7C0h+samDesired], rax; lpType
0x18006dbd6  mov     edx, edi; dwIndex
0x18006dbd8  mov     qword ptr [rsp+7C0h+dwOptions], rsi; lpReserved
0x18006dbdd  call    cs:__imp_RegEnumValueW
0x18006dbe4  nop     dword ptr [rax+rax+00h]
0x18006dbe9  cmp     eax, 103h
0x18006dbee  jz      loc_18006DDB7
0x18006dbf4  test    eax, eax
0x18006dbf6  jnz     loc_18006E072
0x18006dbfc  mov     eax, r13d
0x18006dbff  lea     r9, [rbp+6C0h+SystemTime.wMonth]
0x18006dc03  mov     [rbp+6C0h+var_25A], si
0x18006dc0a  lea     r8, [rbp+6C0h+SystemTime]
0x18006dc0e  mov     [rbp+6C0h+var_4A], si
0x18006dc15  lea     rdx, [rbp+6C0h+Format]; Format
0x18006dc19  lea     rcx, [rbp+6C0h+ValueName]; Buffer
0x18006dc20  mov     qword ptr [r15+rax*8], 1
0x18006dc28  lea     rax, [rbp+6C0h+SystemTime.wMilliseconds]
0x18006dc2c  mov     [rsp+7C0h+lpdwDisposition], rax
0x18006dc31  lea     rax, [rbp+6C0h+SystemTime.wSecond]
0x18006dc35  mov     [rsp+7C0h+phkResult], rax
0x18006dc3a  lea     rax, [rbp+6C0h+SystemTime.wMinute]
0x18006dc3e  mov     [rsp+7C0h+lpSecurityAttributes], rax
0x18006dc43  lea     rax, [rbp+6C0h+SystemTime.wHour]
0x18006dc47  mov     qword ptr [rsp+7C0h+samDesired], rax
0x18006dc4c  lea     rax, [rbp+6C0h+SystemTime.wDay]
0x18006dc50  mov     qword ptr [rsp+7C0h+dwOptions], rax
0x18006dc55  call    swscanf_s
0x18006dc5a  cmp     eax, 7
0x18006dc5d  jnz     loc_18006DDB0
0x18006dc63  lea     rdx, [rbp+6C0h+FileTime]; lpFileTime
0x18006dc67  lea     rcx, [rbp+6C0h+SystemTime]; lpSystemTime
  ... truncated ...
```
