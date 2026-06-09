# FindUrlComponentsA(char const *,int,tagProxyResolveUrl * *)

- ea: `0x1800c0918`
- end: `0x1800c13b7`
- name: `?FindUrlComponentsA@@YAJPEBDHPEAPEAUtagProxyResolveUrl@@@Z`
- size: `2719`
- prototype: `__int64 __fastcall(const char *, int, struct tagProxyResolveUrl **)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180031150`
- `0x180101268`
- `0x180112e94`

## callees

- `0x18006e170`
- `0x1800701d0`
- `0x1800c005c`
- `0x1800c0918`
- `0x1800c14f4`
- `0x1800e96f0`
- `0x1800e98c0`
- `0x1800ef5a0`
- `0x180127990`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180190f24`
- `0x1801e0700`
- `0x1801e1790`
- `0x1801e875c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0bfa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0c62`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0d32`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0da6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0bfa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0c62`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0d32`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0da6`
- `ntdll!RtlIpv6StringToAddressExW` at `0x1800c1140`
- `ntdll!RtlIpv6StringToAddressExW` at `0x1800c1140`
- `ntdll!RtlIpv4StringToAddressExW` at `0x1800c1125`
- `ntdll!RtlIpv4StringToAddressExW` at `0x1800c1125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0f02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c108a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0f02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c108a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c09d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0d5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0eb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c09d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0d5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0eb3`

## pseudocode

```c
__int64 __fastcall FindUrlComponentsA(WCHAR *a1, int a2, struct tagProxyResolveUrl **a3)
{
  const CHAR *v3; // rsi
  CHAR *v4; // rbx
  CHAR *v5; // r15
  WCHAR *v6; // r14
  unsigned __int16 *v7; // r12
  WCHAR *v8; // r13
  __int64 v9; // rax
  CHAR *v10; // rax
  int v11; // edi
  unsigned __int64 v12; // r8
  CHAR *v13; // rdx
  LPWSTR v14; // rcx
  CHAR *v15; // rax
  __int64 v16; // r9
  CHAR *v17; // rcx
  signed int v18; // ecx
  __int64 v19; // rdx
  signed int v20; // eax
  bool v21; // sf
  void *v22; // rcx
  int v24; // eax
  unsigned __int64 v25; // rdi
  WCHAR *v26; // rax
  const CHAR *v27; // rax
  const CHAR *v28; // rdx
  int v29; // eax
  void *v30; // rsi
  int v31; // ecx
  int v32; // eax
  LPWSTR v33; // rdi
  unsigned int v34; // ecx
  size_t v35; // rax
  WCHAR *v36; // rax
  __int64 v37; // rdx
  int v38; // eax
  void *v39; // rax
  const CHAR *v40; // rcx
  int v41; // eax
  int v42; // ecx
  int v43; // r8d
  int v44; // esi
  int v45; // edi
  _WORD *v46; // rax
  USHORT v47; // cx
  struct tagProxyResolveUrl **v48; // rcx
  signed int LastError; // eax
  bool v50; // sf
  signed int v51; // eax
  bool v52; // sf
  signed int v53; // eax
  bool v54; // sf
  WCHAR v55; // cx
  WCHAR *v56; // rax
  int v57; // eax
  WCHAR *v58; // rdi
  unsigned int v59; // esi
  signed __int64 v60; // rdx
  int v61; // eax
  int v62; // eax
  __int64 v63; // rax
  int cbMultiByte[2]; // [rsp+90h] [rbp-80h] BYREF
  LPWSTR v65; // [rsp+98h] [rbp-78h] BYREF
  __int64 cchWideChar; // [rsp+A0h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-68h]
  int v68; // [rsp+B0h] [rbp-60h]
  _DWORD v69[3]; // [rsp+B4h] [rbp-5Ch] BYREF
  unsigned __int64 lpWideCharStr; // [rsp+C0h] [rbp-50h]
  void *v71; // [rsp+C8h] [rbp-48h] BYREF
  LPCCH v72; // [rsp+D0h] [rbp-40h] BYREF
  int v73; // [rsp+D8h] [rbp-38h]
  LPCCH lpMultiByteStr; // [rsp+E0h] [rbp-30h] BYREF
  void *v75; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v76; // [rsp+F0h] [rbp-20h] BYREF
  WCHAR *v77; // [rsp+F8h] [rbp-18h]
  unsigned __int16 *v78; // [rsp+100h] [rbp-10h]
  unsigned __int16 *v79; // [rsp+108h] [rbp-8h]
  LPCCH v80; // [rsp+110h] [rbp+0h] BYREF
  LPCCH v81; // [rsp+118h] [rbp+8h]
  struct tagProxyResolveUrl **v82; // [rsp+120h] [rbp+10h]
  USHORT Port[2]; // [rsp+128h] [rbp+18h] BYREF
  int cchUnicodeChar; // [rsp+12Ch] [rbp+1Ch] BYREF
  size_t Size[2]; // [rsp+130h] [rbp+20h] BYREF
  struct in6_addr Address[2]; // [rsp+140h] [rbp+30h] BYREF

  v82 = a3;
  v73 = a2;
  v3 = 0;
  v65 = a1;
  v4 = 0;
  cbMultiByte[1] = 0;
  v5 = 0;
  *(_QWORD *)&v69[1] = 0;
  v6 = 0;
  v78 = 0;
  v7 = 0;
  pv = 0;
  v8 = 0;
  v79 = 0;
  v77 = 0;
  v68 = 0;
  LOWORD(v69[0]) = 0;
  v72 = 0;
  v80 = 0;
  v81 = 0;
  LODWORD(cchWideChar) = 0;
  cchUnicodeChar = 0;
  v76 = 0;
  if ( !a3 )
  {
    cbMultiByte[1] = 285;
LABEL_148:
    v11 = -2147024809;
    goto LABEL_24;
  }
  *a3 = 0;
  if ( !a1 )
  {
    cbMultiByte[1] = 288;
    goto LABEL_148;
  }
  HIDWORD(lpWideCharStr) = 0;
  v9 = -1;
  do
    ++v9;
  while ( *((_BYTE *)a1 + v9) );
  HIDWORD(v75) = 0;
  lpWideCharStr = (unsigned int)(v9 + 1);
  v10 = (CHAR *)CoTaskMemAlloc(lpWideCharStr);
  lpMultiByteStr = v10;
  v11 = -2147024809;
  if ( v10 )
  {
    memset_0(v10, 0, lpWideCharStr);
    v12 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( lpWideCharStr > 0x7FFFFFFF )
      {
        v18 = -2147024809;
        *(_DWORD *)Port = -2147024809;
        v15 = (CHAR *)lpMultiByteStr;
        *lpMultiByteStr = 0;
      }
      else
      {
        v13 = (CHAR *)lpMultiByteStr;
        v14 = v65;
        v15 = (CHAR *)lpMultiByteStr;
        v16 = 2147483646;
        do
        {
          if ( !v16 )
            break;
          if ( !*(_BYTE *)v14 )
            break;
          *v13 = *(_BYTE *)v14;
          v14 = (LPWSTR)((char *)v14 + 1);
          ++v13;
          --v16;
          --v12;
        }
        while ( v12 );
        v17 = v13 - 1;
        if ( v12 )
          v17 = v13;
        *v17 = 0;
        v18 = v12 == 0 ? 0x8007007A : 0;
        *(_DWORD *)Port = v18;
      }
    }
    else
    {
      v18 = -2147024809;
      *(_DWORD *)Port = -2147024809;
      v15 = (CHAR *)lpMultiByteStr;
    }
    if ( v18 < 0 )
    {
      HIDWORD(lpWideCharStr) = 436;
      if ( v15 )
      {
        CoTaskMemFree(v15);
        v18 = *(_DWORD *)Port;
      }
    }
    else
    {
      v4 = v15;
    }
  }
  else
  {
    HIDWORD(v75) = 76;
    v18 = -2147024882;
    HIDWORD(lpWideCharStr) = 432;
  }
  if ( v18 < 0 )
  {
    cbMultiByte[1] = 290;
    v11 = v18;
    goto LABEL_24;
  }
  v19 = -1;
  do
    ++v19;
  while ( v4[v19] );
  v20 = CrackUrl(
          v4,
          (__int64)&v76 + 4,
          (__int64)&v72,
          (__int64)&cchWideChar,
          (__int64)v69,
          0,
          0,
          0,
          0,
          (__int64)&v80,
          (__int64)&v76,
          0,
          0,
          0,
          1);
  v21 = v20 < 0;
  if ( v20 > 0 )
  {
    v20 = (unsigned __int16)v20 | 0x80070000;
    v21 = v20 < 0;
  }
  if ( v21 )
  {
    cbMultiByte[1] = 314;
    v11 = v20;
LABEL_24:
    v22 = pv;
    goto LABEL_25;
  }
  if ( v68 == 5 )
  {
    cbMultiByte[1] = 321;
    v11 = -2147012891;
    goto LABEL_24;
  }
  HIDWORD(v65) = 0;
  *(_QWORD *)cbMultiByte = 0;
  lpMultiByteStr = 0;
  if ( !v4 )
  {
    HIDWORD(v65) = 105;
LABEL_119:
    cbMultiByte[1] = 329;
    goto LABEL_117;
  }
  if ( GlobalSafeToAssumeUTF8 )
  {
    HIDWORD(v71) = 0;
    v24 = MultiByteToWideChar(0xFDE9u, 0, v4, -1, 0, 0);
    v25 = 0;
    *(_DWORD *)Port = v24;
    if ( v24 )
    {
      v65 = 0;
      v75 = (void *)(unsigned int)(2 * v24);
      v26 = (WCHAR *)CoTaskMemAlloc((unsigned int)v75);
      lpWideCharStr = (unsigned __int64)v26;
      if ( v26 )
      {
        memset_0(v26, 0, (size_t)v75);
        v25 = lpWideCharStr;
        v65 = (LPWSTR)lpWideCharStr;
        if ( MultiByteToWideChar(0xFDE9u, 0, v4, -1, (LPWSTR)lpWideCharStr, *(int *)Port) )
        {
          v3 = (const CHAR *)v25;
          *(_QWORD *)cbMultiByte = v25;
          v25 = 0;
          v65 = 0;
          *(_DWORD *)Port = 0;
        }
        else
        {
          LastError = WxGetLastError();
          v50 = LastError < 0;
          if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
            v50 = LastError < 0;
          }
          if ( !v50 )
            LastError = -2147418113;
          *(_DWORD *)Port = LastError;
          HIDWORD(v71) = 209;
        }
      }
      else
      {
        HIDWORD(v75) = 76;
        *(_DWORD *)Port = -2147024882;
        HIDWORD(v71) = 197;
      }
      if ( v25 )
        WxCoTaskAllocator::Free((void **)&v65);
      v11 = *(_DWORD *)Port;
      if ( *(int *)Port >= 0 )
        goto LABEL_48;
    }
    else
    {
      v53 = WxGetLastError();
      v54 = v53 < 0;
      if ( v53 > 0 )
      {
        v53 = (unsigned __int16)v53 | 0x80070000;
        v54 = v53 < 0;
      }
      HIDWORD(v71) = 182;
      if ( !v54 )
        v53 = -2147418113;
      LODWORD(v65) = v53;
    }
  }
  v11 = WxNewStringAtoWCchCp<WxCoTaskAllocator>(v4, -1, 0);
  if ( v11 >= 0 )
  {
    v3 = *(const CHAR **)cbMultiByte;
LABEL_48:
    v27 = 0;
    lpMultiByteStr = v3;
    *(_QWORD *)cbMultiByte = 0;
    v5 = (CHAR *)v3;
    goto LABEL_49;
  }
  v27 = *(const CHAR **)cbMultiByte;
  HIDWORD(v65) = 131;
LABEL_49:
  if ( v27 )
    WxCoTaskAllocator::Free((void **)cbMultiByte);
  if ( v11 < 0 )
    goto LABEL_119;
  v28 = v72;
  lpWideCharStr = (unsigned __int64)v72;
  if ( v72 )
  {
    v29 = cchWideChar;
  }
  else
  {
    v28 = word_180222338;
    v29 = 0;
    lpWideCharStr = (unsigned __int64)word_180222338;
  }
  *(_DWORD *)Port = v29;
  v30 = 0;
  HIDWORD(v72) = 0;
  v6 = 0;
  v71 = 0;
  v75 = 0;
  if ( !v28 )
  {
    HIDWORD(v72) = 105;
    v11 = -2147024809;
LABEL_116:
    cbMultiByte[1] = 339;
    goto LABEL_117;
  }
  if ( GlobalSafeToAssumeUTF8 )
  {
    HIDWORD(v65) = 0;
    v31 = v29;
    if ( v29 == -1 )
      v31 = -1;
    cbMultiByte[0] = v31;
    v32 = MultiByteToWideChar(0xFDE9u, 0, v28, v31, 0, 0);
    v33 = 0;
    LODWORD(cchWideChar) = v32;
    if ( v32 )
    {
      v34 = 2 * v32;
      v35 = (unsigned int)(2 * v32 + 2);
      HIDWORD(v65) = 0;
      if ( *(_DWORD *)Port == -1 )
        v35 = v34;
      v72 = 0;
      Size[0] = v35;
      v36 = (WCHAR *)CoTaskMemAlloc((unsigned int)v35);
      v65 = v36;
      if ( v36 )
      {
        memset_0(v36, 0, Size[0]);
        v33 = v65;
        v72 = (LPCCH)v65;
        v38 = MultiByteToWideChar(0xFDE9u, 0, (LPCCH)lpWideCharStr, cbMultiByte[0], v65, cchWideChar);
        if ( v38 )
        {
          if ( *(_DWORD *)Port != -1 )
            v33[v38] = 0;
          v30 = v33;
          v71 = v33;
          v33 = 0;
          v72 = 0;
          LODWORD(cchWideChar) = 0;
        }
        else
        {
          v51 = WxGetLastError();
          v52 = v51 < 0;
          if ( v51 > 0 )
          {
            v51 = (unsigned __int16)v51 | 0x80070000;
            v52 = v51 < 0;
          }
          HIDWORD(v65) = 209;
          if ( !v52 )
            v51 = -2147418113;
          LODWORD(cchWideChar) = v51;
        }
      }
      else
      {
        v65 = (LPWSTR)0xC500000000LL;
        LODWORD(cchWideChar) = -2147024882;
      }
      if ( v33 )
        WxCoTaskAllocator::Free((void **)&v72);
      v11 = cchWideChar;
      if ( (int)cchWideChar >= 0 )
        goto LABEL_69;
    }
    else
    {
      WxGetLastError();
      HIDWORD(v65) = 182;
    }
  }
  v11 = WxNewStringAtoWCchCp<WxCoTaskAllocator>((LPCCH)lpWideCharStr, *(int *)Port, 0);
  if ( v11 >= 0 )
  {
    v30 = v71;
LABEL_69:
    v39 = 0;
    v75 = v30;
    v71 = 0;
    v6 = (WCHAR *)v30;
    goto LABEL_70;
  }
  v39 = v71;
  HIDWORD(v72) = 131;
LABEL_70:
  if ( v39 )
    WxCoTaskAllocator::Free(&v71);
  if ( v11 < 0 )
    goto LABEL_116;
  if ( !v73 )
    goto LABEL_74;
  v11 = WxStringCchLengthDWordW(v6, v37, &cchUnicodeChar);
  if ( v11 < 0 )
  {
    cbMultiByte[1] = 343;
    goto LABEL_117;
  }
  v62 = WxHostWCharToPunycode<WxCoTaskAllocator>(v6, cchUnicodeChar);
  v8 = v77;
  v11 = v62;
  if ( v62 < 0 )
  {
    cbMultiByte[1] = 345;
LABEL_161:
    v3 = *(const CHAR **)&v69[1];
    goto LABEL_88;
  }
  Port[0] = 0;
  memset(Address, 0, 28);
  v58 = v77;
  *(_OWORD *)Size = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_Sd(1036, 10, (unsigned int)&WPP_e4a583e537b33e4222dcc118c6822267_Traceguids, (_DWORD)v77, 0);
  if ( !RtlIpv4StringToAddressExW(v8, 1u, (struct in_addr *)Size + 1, Port) )
    goto LABEL_137;
  v59 = 0;
  if ( RtlIpv6StringToAddressExW(
         v8,
         (struct in6_addr *)&Address[0].u.Word[4],
         (PULONG)&Address[1].u.Word[4],
         &Address[0].u.Word[1]) )
  {
    while ( *v58 )
    {
      if ( (unsigned __int16)(*v58 - 33) > 0x5Du || (byte_180226CB0[*v58 - 33] & 0x88) != 0 )
        goto LABEL_138;
      ++v58;
    }
    goto LABEL_137;
  }
  if ( *v8 == 91 )
  {
    v63 = -1;
    do
      ++v63;
    while ( v8[v63] );
    if ( v8[v63 - 1] == 93 )
LABEL_137:
      v59 = 1;
  }
LABEL_138:
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_d(1038, 11, &WPP_e4a583e537b33e4222dcc118c6822267_Traceguids, v59);
  if ( !v59 )
  {
    cbMultiByte[1] = 349;
    v11 = -2147012891;
    goto LABEL_161;
  }
  v56 = v6;
  v60 = (char *)v8 - (char *)v6;
  while ( 1 )
  {
    v55 = *v56;
    if ( *v56 != *(WCHAR *)((char *)v56 + v60) )
      break;
    ++v56;
    if ( !v55 )
    {
      v57 = 0;
      goto LABEL_125;
    }
  }
  v57 = v55 < *(WCHAR *)((char *)v56 + v60) ? -1 : 1;
LABEL_125:
  v73 = v57 != 0 ? v73 : 0;
  if ( v6 )
    WxCoTaskAllocator::Free(&v75);
  v6 = v8;
  v8 = 0;
LABEL_74:
  v40 = v80;
  if ( v80 && *v80 )
  {
    v41 = v76;
  }
  else
  {
    v40 = "/";
    v41 = 1;
  }
  v11 = InetNewStringAtoW(v40, v41);
  if ( v11 < 0 )
  {
    v7 = v78;
    cbMultiByte[1] = 373;
    goto LABEL_117;
  }
  LOWORD(v44) = v69[0];
  *(_DWORD *)Port = LOWORD(v69[0]);
  if ( !LOWORD(v69[0]) )
  {
    v42 = v68 - 1;
    if ( v68 == 1 )
    {
      v44 = 21;
    }
    else
    {
      v42 = v68 - 3;
      if ( v68 == 4 )
        v44 = 443;
      else
        v44 = 80;
    }
    *(_DWORD *)Port = v44;
  }
  v7 = v78;
  if ( !v73 )
    goto LABEL_84;
  v11 = InetNewStringAtoW(v81, SHIDWORD(v76));
  if ( v11 >= 0 )
  {
    if ( v5 )
      WxCoTaskAllocator::Free((void **)&lpMultiByteStr);
    pv = v79;
    v61 = RecreateUrl(v6, v7, v79, v44, (unsigned __int16 **)&lpMultiByteStr);
    v5 = (CHAR *)lpMultiByteStr;
    v11 = v61;
    if ( v61 >= 0 )
    {
LABEL_84:
      v45 = v68;
      if ( (xmmword_180266B60 & 0x20) != 0 )
        WPP_SF_SSSdd(v42, 11, v43, (_DWORD)v5, (__int64)v6, (__int64)v7, v68, v44);
      HIDWORD(Size[0]) = 0;
      v3 = 0;
      *(_QWORD *)&v69[1] = 0;
      v46 = CoTaskMemAlloc(0x20u);
      if ( !v46 )
      {
        HIDWORD(Size[0]) = 76;
        v11 = -2147024882;
        cbMultiByte[1] = 418;
        goto LABEL_24;
      }
      v46[15] = 0;
      v47 = Port[0];
      *(_QWORD *)v46 = v5;
      v5 = 0;
      *((_QWORD *)v46 + 1) = v6;
      v6 = 0;
      *((_QWORD *)v46 + 2) = v7;
      v7 = 0;
      v46[14] = v47;
      v48 = v82;
      *((_DWORD *)v46 + 6) = v45;
      v11 = 0;
      *(_QWORD *)&v69[1] = 0;
      *v48 = (struct tagProxyResolveUrl *)v46;
LABEL_88:
      if ( v8 )
        CoTaskMemFree(v8);
      goto LABEL_24;
    }
    cbMultiByte[1] = 407;
LABEL_117:
    v3 = *(const CHAR **)&v69[1];
    goto LABEL_24;
  }
  v22 = v79;
  v3 = *(const CHAR **)&v69[1];
  cbMultiByte[1] = 401;
LABEL_25:
  if ( v22 )
    CoTaskMemFree(v22);
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v3 )
    FreeProxyResolveUrl((struct tagProxyResolveUrl **)&v69[1]);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800c0918  mov     [rsp-8+arg_8], rbx
0x1800c091d  push    rbp
0x1800c091e  push    rsi
0x1800c091f  push    rdi
0x1800c0920  push    r12
0x1800c0922  push    r13
0x1800c0924  push    r14
0x1800c0926  push    r15
0x1800c0928  lea     rbp, [rsp-60h]
0x1800c092d  sub     rsp, 170h
0x1800c0934  mov     rax, cs:__security_cookie
0x1800c093b  xor     rax, rsp
0x1800c093e  mov     [rbp+90h+var_40], rax
0x1800c0942  xor     r10d, r10d
0x1800c0945  mov     [rbp+90h+var_80], r8
0x1800c0949  mov     [rbp+90h+var_C8], edx
0x1800c094c  mov     esi, r10d
0x1800c094f  mov     [rbp+90h+var_108], rcx
0x1800c0953  mov     ebx, r10d
0x1800c0956  mov     [rbp+90h+cbMultiByte+4], r10d
0x1800c095a  mov     r15d, r10d
0x1800c095d  mov     qword ptr [rbp+90h+var_EC+4], r10
0x1800c0961  mov     r14d, r10d
0x1800c0964  mov     [rbp+90h+var_A0], r10
0x1800c0968  mov     r12d, r10d
0x1800c096b  mov     [rbp+90h+pv], r10
0x1800c096f  mov     r13d, r10d
0x1800c0972  mov     [rbp+90h+var_98], r10
0x1800c0976  mov     [rbp+90h+var_A8], r10
0x1800c097a  mov     [rbp+90h+var_F0], r10d
0x1800c097e  mov     word ptr [rbp+90h+var_EC], r10w
0x1800c0983  mov     [rbp+90h+var_D0], r10
0x1800c0987  mov     [rbp+90h+var_90], r10
0x1800c098b  mov     [rbp+90h+var_88], r10
0x1800c098f  mov     dword ptr [rbp+90h+var_100], r10d
0x1800c0993  mov     [rbp+90h+cchUnicodeChar], r10d
0x1800c0997  mov     dword ptr [rbp+90h+var_B0], r10d
0x1800c099b  mov     dword ptr [rbp+90h+var_B0+4], r10d
0x1800c099f  test    r8, r8
0x1800c09a2  jz      loc_1800C1206
0x1800c09a8  mov     [r8], r10
0x1800c09ab  test    rcx, rcx
0x1800c09ae  jz      loc_1800C120F
0x1800c09b4  mov     [rbp+90h+var_DC], r10d
0x1800c09b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c09bc  inc     rax
0x1800c09bf  cmp     [rcx+rax], r10b
0x1800c09c3  jnz     short loc_1800C09BC
0x1800c09c5  inc     eax
0x1800c09c7  mov     dword ptr [rbp+90h+var_B8+4], r10d
0x1800c09cb  mov     ecx, eax; cb
0x1800c09cd  mov     [rbp-50h], rax
0x1800c09d1  call    cs:__imp_CoTaskMemAlloc
0x1800c09d7  mov     [rbp+90h+lpMultiByteStr], rax
0x1800c09db  xor     r10d, r10d
0x1800c09de  mov     edi, 80070057h
0x1800c09e3  mov     r8d, 1
0x1800c09e9  test    rax, rax
0x1800c09ec  jz      loc_1800C0F0D
0x1800c09f2  mov     r8, [rbp-50h]; Size
0x1800c09f6  xor     edx, edx; Val
0x1800c09f8  mov     rcx, rax; void *
0x1800c09fb  call    memset_0
0x1800c0a00  mov     r8, [rbp-50h]
0x1800c0a04  xor     r10d, r10d
0x1800c0a07  test    r8, r8
0x1800c0a0a  jz      loc_1800C1231
0x1800c0a10  cmp     r8, 7FFFFFFFh
0x1800c0a17  ja      loc_1800C1220
0x1800c0a1d  mov     rdx, [rbp+90h+lpMultiByteStr]
0x1800c0a21  lea     r11d, [r10+1]
0x1800c0a25  mov     rcx, [rbp+90h+var_108]
0x1800c0a29  mov     rax, rdx
0x1800c0a2c  mov     r9d, 7FFFFFFEh
0x1800c0a32  test    r9, r9
0x1800c0a35  jz      short loc_1800C0A57
0x1800c0a37  mov     r10b, [rcx]
0x1800c0a3a  test    r10b, r10b
0x1800c0a3d  jz      loc_1800C0F25
0x1800c0a43  mov     [rdx], r10b
0x1800c0a46  add     rcx, r11
0x1800c0a49  add     rdx, r11
0x1800c0a4c  xor     r10d, r10d
0x1800c0a4f  sub     r9, r11
0x1800c0a52  sub     r8, r11
0x1800c0a55  jnz     short loc_1800C0A32
0x1800c0a57  test    r8, r8
0x1800c0a5a  lea     rcx, [rdx-1]
0x1800c0a5e  cmovnz  rcx, rdx
0x1800c0a62  neg     r8
0x1800c0a65  mov     [rcx], r10b
0x1800c0a68  sbb     ecx, ecx
0x1800c0a6a  not     ecx
0x1800c0a6c  and     ecx, 8007007Ah
0x1800c0a72  mov     dword ptr [rbp+90h+Port], ecx
0x1800c0a75  test    ecx, ecx
0x1800c0a77  js      loc_1800C1077
0x1800c0a7d  mov     rbx, rax
0x1800c0a80  mov     r8d, 1
0x1800c0a86  test    ecx, ecx
0x1800c0a88  js      loc_1800C1244
0x1800c0a8e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800c0a92  inc     rdx
0x1800c0a95  cmp     [rbx+rdx], r10b
0x1800c0a99  jnz     short loc_1800C0A92
0x1800c0a9b  mov     [rsp+1A0h+var_118], r8d; int
0x1800c0aa3  lea     rax, [rbp+90h+var_B0]
0x1800c0aa7  mov     [rsp+1A0h+var_120], r10; __int64
0x1800c0aaf  lea     r9, [rbp+90h+var_88]
0x1800c0ab3  mov     [rsp+1A0h+var_128], r10; __int64
0x1800c0ab8  lea     r8, [rbp+90h+var_F0]
0x1800c0abc  mov     [rsp+1A0h+var_130], r10; __int64
0x1800c0ac1  mov     rcx, rbx; pszStr2
0x1800c0ac4  mov     [rsp+1A0h+var_138], rax; __int64
0x1800c0ac9  lea     rax, [rbp+90h+var_90]
0x1800c0acd  mov     [rsp+1A0h+var_140], rax; __int64
0x1800c0ad2  lea     rax, [rbp+90h+var_EC]
0x1800c0ad6  mov     [rsp+1A0h+var_148], r10; __int64
0x1800c0adb  mov     [rsp+1A0h+var_150], r10; __int64
0x1800c0ae0  mov     [rsp+1A0h+var_158], r10; __int64
0x1800c0ae5  mov     [rsp+1A0h+var_160], r10; __int64
0x1800c0aea  mov     [rsp+1A0h+var_168], rax; __int64
0x1800c0aef  lea     rax, [rbp+90h+var_100]
0x1800c0af3  mov     [rsp+1A0h+var_170], rax; __int64
0x1800c0af8  lea     rax, [rbp+90h+var_D0]
0x1800c0afc  mov     qword ptr [rsp+1A0h+cchWideChar], rax; __int64
0x1800c0b01  lea     rax, [rbp+90h+var_B0+4]
0x1800c0b05  mov     [rsp+1A0h+lpWideCharStr], rax; __int64
0x1800c0b0a  call    CrackUrl
0x1800c0b0f  xor     r10d, r10d
0x1800c0b12  test    eax, eax
0x1800c0b14  jle     short loc_1800C0B20
0x1800c0b16  movzx   eax, ax
0x1800c0b19  or      eax, 80070000h
0x1800c0b1e  test    eax, eax
0x1800c0b20  jns     loc_1800C0BAD
0x1800c0b26  mov     [rbp+90h+cbMultiByte+4], 13Ah
0x1800c0b2d  mov     edi, eax
0x1800c0b2f  mov     rcx, [rbp+90h+pv]; pv
0x1800c0b33  test    rcx, rcx
0x1800c0b36  jz      short loc_1800C0B3E
0x1800c0b38  call    cs:__imp_CoTaskMemFree
0x1800c0b3e  test    r12, r12
0x1800c0b41  jz      short loc_1800C0B4C
0x1800c0b43  mov     rcx, r12; pv
0x1800c0b46  call    cs:__imp_CoTaskMemFree
0x1800c0b4c  test    r14, r14
0x1800c0b4f  jz      short loc_1800C0B5A
0x1800c0b51  mov     rcx, r14; pv
0x1800c0b54  call    cs:__imp_CoTaskMemFree
0x1800c0b5a  test    r15, r15
0x1800c0b5d  jz      short loc_1800C0B68
0x1800c0b5f  mov     rcx, r15; pv
0x1800c0b62  call    cs:__imp_CoTaskMemFree
0x1800c0b68  test    rbx, rbx
0x1800c0b6b  jz      short loc_1800C0B76
0x1800c0b6d  mov     rcx, rbx; pv
0x1800c0b70  call    cs:__imp_CoTaskMemFree
0x1800c0b76  test    rsi, rsi
0x1800c0b79  jz      short loc_1800C0B84
0x1800c0b7b  lea     rcx, [rbp+90h+var_EC+4]; struct tagProxyResolveUrl **
0x1800c0b7f  call    ?FreeProxyResolveUrl@@YAXPEAPEAUtagProxyResolveUrl@@@Z; FreeProxyResolveUrl(tagProxyResolveUrl * *)
0x1800c0b84  mov     eax, edi
0x1800c0b86  mov     rcx, [rbp+90h+var_40]
0x1800c0b8a  xor     rcx, rsp; StackCookie
0x1800c0b8d  call    __security_check_cookie
0x1800c0b92  mov     rbx, [rsp+1A0h+arg_8]
0x1800c0b9a  add     rsp, 170h
0x1800c0ba1  pop     r15
0x1800c0ba3  pop     r14
0x1800c0ba5  pop     r13
0x1800c0ba7  pop     r12
0x1800c0ba9  pop     rdi
0x1800c0baa  pop     rsi
0x1800c0bab  pop     rbp
0x1800c0bac  retn
0x1800c0bad  mov     eax, [rbp+90h+var_F0]
0x1800c0bb0  mov     [rbp+90h+var_F0], eax
0x1800c0bb3  cmp     eax, 5
0x1800c0bb6  jz      loc_1800C1252
0x1800c0bbc  mov     dword ptr [rbp+90h+var_108+4], r10d
0x1800c0bc0  mov     [rbp-80h], r10
0x1800c0bc4  mov     [rbp+90h+lpMultiByteStr], r10
0x1800c0bc8  test    rbx, rbx
0x1800c0bcb  jz      loc_1800C1067
0x1800c0bd1  cmp     cs:GlobalSafeToAssumeUTF8, r10d
0x1800c0bd8  jz      loc_1800C0FFC
0x1800c0bde  mov     [rsp+1A0h+cchWideChar], r10d; cchWideChar
0x1800c0be3  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800c0be7  mov     r8, rbx; lpMultiByteStr
0x1800c0bea  mov     [rsp+1A0h+lpWideCharStr], r10; lpWideCharStr
0x1800c0bef  xor     edx, edx; dwFlags
0x1800c0bf1  mov     dword ptr [rbp+90h+var_D8+4], r10d
0x1800c0bf5  mov     ecx, 0FDE9h; CodePage
0x1800c0bfa  call    cs:__imp_MultiByteToWideChar
0x1800c0c00  xor     edi, edi
0x1800c0c02  mov     dword ptr [rbp+90h+Port], eax
0x1800c0c05  test    eax, eax
0x1800c0c07  jz      loc_1800C1024
0x1800c0c0d  add     eax, eax
0x1800c0c0f  mov     dword ptr [rbp+90h+var_B8+4], edi
0x1800c0c12  mov     ecx, eax; cb
0x1800c0c14  mov     [rbp+90h+var_108], rdi
0x1800c0c18  mov     [rbp-28h], rax
0x1800c0c1c  call    cs:__imp_CoTaskMemAlloc
0x1800c0c22  xor     r10d, r10d
0x1800c0c25  mov     [rbp-50h], rax
0x1800c0c29  test    rax, rax
0x1800c0c2c  jz      loc_1800C0F2D
0x1800c0c32  mov     r8, [rbp-28h]; Size
0x1800c0c36  xor     edx, edx; Val
0x1800c0c38  mov     rcx, rax; void *
0x1800c0c3b  call    memset_0
0x1800c0c40  mov     rdi, [rbp-50h]
0x1800c0c44  mov     [rbp+90h+var_108], rdi
0x1800c0c48  mov     eax, dword ptr [rbp+90h+Port]
0x1800c0c4b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800c0c4f  mov     [rsp+1A0h+cchWideChar], eax; cchWideChar
0x1800c0c53  mov     r8, rbx; lpMultiByteStr
0x1800c0c56  xor     edx, edx; dwFlags
0x1800c0c58  mov     [rsp+1A0h+lpWideCharStr], rdi; lpWideCharStr
0x1800c0c5d  mov     ecx, 0FDE9h; CodePage
0x1800c0c62  call    cs:__imp_MultiByteToWideChar
0x1800c0c68  xor     r10d, r10d
0x1800c0c6b  test    eax, eax
0x1800c0c6d  jz      loc_1800C0F63
0x1800c0c73  mov     rsi, rdi
0x1800c0c76  mov     [rbp-80h], rdi
0x1800c0c7a  mov     edi, r10d
0x1800c0c7d  mov     [rbp+90h+var_108], r10
0x1800c0c81  mov     dword ptr [rbp+90h+Port], r10d
0x1800c0c85  test    rdi, rdi
0x1800c0c88  jz      short loc_1800C0C96
0x1800c0c8a  lea     rcx, [rbp+90h+var_108]; void **
0x1800c0c8e  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x1800c0c93  xor     r10d, r10d
0x1800c0c96  mov     edi, dword ptr [rbp+90h+Port]
0x1800c0c99  test    edi, edi
0x1800c0c9b  js      loc_1800C0FFC
0x1800c0ca1  mov     rax, r10
0x1800c0ca4  mov     [rbp+90h+lpMultiByteStr], rsi
0x1800c0ca8  mov     [rbp-80h], rax
0x1800c0cac  mov     r15, rsi
0x1800c0caf  test    rax, rax
0x1800c0cb2  jz      short loc_1800C0CC0
0x1800c0cb4  lea     rcx, [rbp+90h+cbMultiByte]; void **
0x1800c0cb8  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x1800c0cbd  xor     r10d, r10d
0x1800c0cc0  test    edi, edi
0x1800c0cc2  js      loc_1800C106E
0x1800c0cc8  mov     rdx, [rbp+90h+var_D0]
0x1800c0ccc  mov     [rbp-50h], rdx
0x1800c0cd0  test    rdx, rdx
0x1800c0cd3  jz      loc_1800C1273
0x1800c0cd9  mov     eax, dword ptr [rbp+90h+var_100]
0x1800c0cdc  mov     dword ptr [rbp+90h+Port], eax
0x1800c0cdf  mov     rsi, r10
0x1800c0ce2  mov     dword ptr [rbp+90h+var_D0+4], r10d
0x1800c0ce6  mov     r14, r10
0x1800c0ce9  mov     [rbp-48h], r10
0x1800c0ced  mov     [rbp-28h], r10
0x1800c0cf1  test    rdx, rdx
0x1800c0cf4  jz      loc_1800C104B
0x1800c0cfa  cmp     cs:GlobalSafeToAssumeUTF8, r10d
0x1800c0d01  jz      loc_1800C0FD3
0x1800c0d07  or      r8d, 0FFFFFFFFh
0x1800c0d0b  mov     [rsp+1A0h+cchWideChar], r10d; cchWideChar
0x1800c0d10  cmp     eax, r8d
0x1800c0d13  mov     dword ptr [rbp+90h+var_108+4], r10d
0x1800c0d17  mov     ecx, eax
0x1800c0d19  mov     [rsp+1A0h+lpWideCharStr], r10; lpWideCharStr
0x1800c0d1e  cmovz   ecx, r8d
0x1800c0d22  mov     r8, rdx; lpMultiByteStr
0x1800c0d25  mov     [rbp+90h+cbMultiByte], ecx
0x1800c0d28  mov     r9d, ecx; cbMultiByte
0x1800c0d2b  mov     ecx, 0FDE9h; CodePage
0x1800c0d30  xor     edx, edx; dwFlags
0x1800c0d32  call    cs:__imp_MultiByteToWideChar
0x1800c0d38  xor     edi, edi
0x1800c0d3a  mov     dword ptr [rbp+90h+var_100], eax
0x1800c0d3d  test    eax, eax
0x1800c0d3f  jz      loc_1800C0FC7
0x1800c0d45  cmp     dword ptr [rbp+90h+Port], 0FFFFFFFFh
0x1800c0d49  lea     ecx, [rax+rax]
0x1800c0d4c  lea     eax, [rcx+2]
0x1800c0d4f  mov     dword ptr [rbp+90h+var_108+4], edi
0x1800c0d52  cmovz   eax, ecx
0x1800c0d55  mov     [rbp+90h+var_D0], rdi
0x1800c0d59  mov     ecx, eax; cb
0x1800c0d5b  mov     [rbp+90h+Size], rax
0x1800c0d5f  call    cs:__imp_CoTaskMemAlloc
0x1800c0d65  xor     r10d, r10d
0x1800c0d68  mov     [rbp+90h+var_108], rax
0x1800c0d6c  test    rax, rax
0x1800c0d6f  jz      loc_1800C0F48
0x1800c0d75  mov     r8, [rbp+90h+Size]; Size
0x1800c0d79  xor     edx, edx; Val
0x1800c0d7b  mov     rcx, rax; void *
0x1800c0d7e  call    memset_0
0x1800c0d83  mov     rdi, [rbp+90h+var_108]
  ... truncated ...
```
