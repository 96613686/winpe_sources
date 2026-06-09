# FwAppCEncode(_tag_FW_APPCONTAINER *,ushort * *)

- ea: `0x18000d290`
- end: `0x18000dbc6`
- name: `?FwAppCEncode@@YAJPEAU_tag_FW_APPCONTAINER@@PEAPEAG@Z`
- size: `2358`
- prototype: `__int64 __fastcall(struct _INET_FIREWALL_AC_BINARIES *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800042c4`
- `0x18000cff0`
- `0x18000d250`
- `0x18000d290`
- `0x18000e0b0`
- `0x18000e150`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d53c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d5c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d53c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d5c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d4e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d56a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d4e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d56a`
- `fwbase!FwAlloc` at `0x18000d45f`
- `fwbase!FwAlloc` at `0x18000d45f`
- `fwbase!FwSizeTMultiply` at `0x18000d44b`
- `fwbase!FwSizeTMultiply` at `0x18000d44b`

## pseudocode

```c
__int64 __fastcall FwAppCEncode(struct _INET_FIREWALL_AC_BINARIES *a1, unsigned __int16 **a2)
{
  struct _INET_FIREWALL_AC_BINARIES *v2; // r15
  struct _INET_FIREWALL_AC_BINARIES *v3; // r13
  bool v4; // cf
  DWORD count; // r14d
  __int64 v6; // rdi
  __int64 v7; // rsi
  int v8; // eax
  unsigned int v9; // ebx
  size_t v10; // r11
  const wchar_t *binaries; // rcx
  unsigned int v12; // eax
  __int64 v13; // r10
  HRESULT v14; // eax
  const wchar_t *v15; // rcx
  __int64 v16; // r10
  unsigned int v17; // eax
  HRESULT v18; // eax
  const wchar_t *v19; // rcx
  __int64 v20; // r10
  unsigned int v21; // eax
  HRESULT v22; // eax
  const wchar_t *v23; // rcx
  __int64 v24; // r10
  unsigned int v25; // eax
  HRESULT v26; // eax
  const wchar_t *v27; // rcx
  __int64 v28; // r10
  unsigned int v29; // eax
  HRESULT v30; // eax
  __int64 v31; // rcx
  unsigned __int64 v32; // rdi
  wchar_t *v33; // rax
  unsigned int binaries_low; // ecx
  wchar_t *v35; // rdi
  unsigned __int64 v36; // rbx
  LPWSTR *v37; // rcx
  int v38; // ebx
  wchar_t *v39; // rdi
  unsigned __int64 v40; // rbx
  void *v41; // rcx
  int v42; // r14d
  wchar_t *v43; // rbx
  unsigned __int64 v44; // rdi
  wchar_t *v45; // rdi
  int v46; // r12d
  unsigned __int64 v47; // r14
  __int64 v48; // rbx
  LPWSTR *v49; // rax
  __int64 v50; // rax
  LPWSTR *v51; // rax
  __int64 v52; // rax
  LPWSTR *v53; // rax
  LPCOLESTR v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // r9
  unsigned __int16 *v58; // [rsp+20h] [rbp-49h]
  unsigned __int64 v59; // [rsp+50h] [rbp-19h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int64 v61; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 *v62; // [rsp+68h] [rbp-1h]
  unsigned __int16 **v63; // [rsp+70h] [rbp+7h]
  size_t pcchLength; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v65; // [rsp+80h] [rbp+17h] BYREF

  v2 = a1;
  v61 = (unsigned __int64)a1;
  v63 = a2;
  *a2 = 0;
  LODWORD(pszDest) = 0;
  v3 = a1 + 5;
  v4 = a1[1].binaries != 0;
  v65 = 0;
  count = a1[4].count;
  v6 = v4 ? 374LL : 24LL;
  v7 = *(_QWORD *)&a1[2].count != 0 ? 0x15B : 0;
  v8 = FwAppCGetBinariesSize(0, a1 + 5, (unsigned int *)&pszDest);
  v9 = v8;
  if ( v8 < 0 )
  {
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return v9;
    v56 = 40;
    goto LABEL_62;
  }
  v10 = 10000;
  binaries = (const wchar_t *)v2[2].binaries;
  v12 = 0;
  v13 = v6 + v7 + 343 * count + (unsigned int)pszDest;
  pcchLength = 0;
  if ( binaries )
  {
    v14 = StringLengthWorkerW(binaries, 0x2710u, &pcchLength);
    v9 = v14;
    if ( v14 < 0 )
    {
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
        return v9;
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
          (unsigned int)v14);
        v55 = WPP_GLOBAL_Control;
      }
      if ( v55 == (LPCOLESTR)&WPP_GLOBAL_Control || (v55[14] & 1) == 0 )
        return v9;
      v56 = 41;
LABEL_63:
      v57 = v9;
      goto LABEL_64;
    }
    v12 = pcchLength + 5;
  }
  v15 = *(const wchar_t **)&v2[3].count;
  v16 = v12 + v13;
  v17 = 0;
  pcchLength = 0;
  if ( !v15 )
    goto LABEL_8;
  v18 = StringLengthWorkerW(v15, v10, &pcchLength);
  v9 = v18;
  if ( v18 < 0 )
  {
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      return v9;
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
        (unsigned int)v18);
      v55 = WPP_GLOBAL_Control;
    }
    if ( v55 == (LPCOLESTR)&WPP_GLOBAL_Control || (v55[14] & 1) == 0 )
      return v9;
    v56 = 42;
    goto LABEL_63;
  }
  v17 = pcchLength + 8;
LABEL_8:
  v19 = (const wchar_t *)v2[3].binaries;
  v20 = v17 + v16;
  v21 = 0;
  pcchLength = 0;
  if ( !v19 )
    goto LABEL_11;
  v22 = StringLengthWorkerW(v19, v10, &pcchLength);
  v9 = v22;
  if ( v22 < 0 )
  {
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      return v9;
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
        (unsigned int)v22);
      v55 = WPP_GLOBAL_Control;
    }
    if ( v55 == (LPCOLESTR)&WPP_GLOBAL_Control || (v55[14] & 1) == 0 )
      return v9;
    v56 = 43;
    goto LABEL_63;
  }
  v21 = pcchLength + 8;
LABEL_11:
  v23 = *(const wchar_t **)&v2[6].count;
  v24 = v21 + v20;
  v25 = 0;
  pcchLength = 0;
  if ( !v23 )
    goto LABEL_14;
  v26 = StringLengthWorkerW(v23, v10, &pcchLength);
  v9 = v26;
  if ( v26 < 0 )
  {
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      return v9;
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
        (unsigned int)v26);
      v55 = WPP_GLOBAL_Control;
    }
    if ( v55 == (LPCOLESTR)&WPP_GLOBAL_Control || (v55[14] & 1) == 0 )
      return v9;
    v56 = 44;
    goto LABEL_63;
  }
  v25 = pcchLength + 5;
LABEL_14:
  v27 = (const wchar_t *)v2[6].binaries;
  v28 = v25 + v24;
  v29 = 0;
  pcchLength = 0;
  if ( !v27 )
  {
LABEL_17:
    v31 = 12;
    if ( v2[7].count != 1 )
      v31 = 1;
    v32 = v31 + v28 + v29;
    v59 = v32;
    v8 = FwSizeTMultiply(v32, 2, &v65);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v33 = (wchar_t *)FwAlloc(v65);
      v62 = v33;
      if ( v33 )
      {
        binaries_low = LOWORD(v2->binaries);
        pszDest = v33;
        if ( (int)StringCchPrintfExW(
                    v33,
                    v32,
                    &pszDest,
                    &v59,
                    0x800u,
                    L"v%d.%d%s",
                    binaries_low >> 8,
                    (unsigned __int8)binaries_low,
                    L"|") < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v35 = pszDest;
        v36 = v59;
        v37 = v2[1].binaries;
        pcchLength = 0;
        ConvertSidToStringSidW(v37, (LPWSTR *)&pcchLength);
        v38 = StringCchPrintfExW(v35, v36, &pszDest, &v59, 0x800u, L"%s%s%s", L"AppPkgId=", pcchLength, L"|");
        if ( v38 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        LocalFree((HLOCAL)pcchLength);
        if ( v38 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v39 = pszDest;
        v40 = v59;
        v41 = *(void **)&v2[2].count;
        pcchLength = 0;
        ConvertSidToStringSidW(v41, (LPWSTR *)&pcchLength);
        v42 = StringCchPrintfExW(v39, v40, &pszDest, &v59, 0x800u, L"%s%s%s");
        if ( v42 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        LocalFree((HLOCAL)pcchLength);
        v43 = pszDest;
        v44 = v59;
        if ( v42 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeCapabilities(
                    v43,
                    v44,
                    &pszDest,
                    &v59,
                    v58,
                    (struct _INET_FIREWALL_AC_CAPABILITIES *)&v2[4]) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v45 = pszDest;
        v46 = 0;
        v47 = v59;
        v48 = 0;
        pcchLength = (size_t)pszDest;
        if ( v3->count )
        {
          do
          {
            v46 = StringCchPrintfExW(
                    v45,
                    v47,
                    (unsigned __int16 **)&pcchLength,
                    &v59,
                    0x800u,
                    L"%s%s%s",
                    L"B=",
                    v3->binaries[v48],
                    L"|");
            if ( v46 < 0 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v45 = (wchar_t *)pcchLength;
            v48 = (unsigned int)(v48 + 1);
            v47 = v59;
          }
          while ( (unsigned int)v48 < v3->count );
          v2 = (struct _INET_FIREWALL_AC_BINARIES *)v61;
        }
        if ( v46 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v49 = v2[2].binaries;
        if ( v49 )
        {
          pcchLength = (size_t)v45;
          v59 = v47;
          if ( (int)StringCchPrintfExW(
                      v45,
                      v47,
                      (unsigned __int16 **)&pcchLength,
                      &v59,
                      0x800u,
                      L"%s%s%s",
                      L"M=",
                      v49,
                      L"|") < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v45 = (wchar_t *)pcchLength;
          v47 = v59;
        }
        v50 = *(_QWORD *)&v2[3].count;
        if ( v50 )
        {
          pcchLength = (size_t)v45;
          v59 = v47;
          if ( (int)StringCchPrintfExW(
                      v45,
                      v47,
                      (unsigned __int16 **)&pcchLength,
                      &v59,
                      0x800u,
                      L"%s%s%s",
                      L"Name=",
                      v50,
                      L"|") < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v45 = (wchar_t *)pcchLength;
          v47 = v59;
        }
        v51 = v2[3].binaries;
        if ( v51 )
        {
          pcchLength = (size_t)v45;
          v59 = v47;
          if ( (int)StringCchPrintfExW(
                      v45,
                      v47,
                      (unsigned __int16 **)&pcchLength,
                      &v59,
                      0x800u,
                      L"%s%s%s",
                      L"Desc=",
                      v51,
                      L"|") < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v45 = (wchar_t *)pcchLength;
          v47 = v59;
        }
        v52 = *(_QWORD *)&v2[6].count;
        if ( v52 )
        {
          pcchLength = (size_t)v45;
          v59 = v47;
          if ( (int)StringCchPrintfExW(
                      v45,
                      v47,
                      (unsigned __int16 **)&pcchLength,
                      &v59,
                      0x800u,
                      L"%s%s%s",
                      L"D=",
                      v52,
                      L"|") < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v45 = (wchar_t *)pcchLength;
          v47 = v59;
        }
        v53 = v2[6].binaries;
        if ( v53 )
        {
          pcchLength = (size_t)v45;
          v59 = v47;
          if ( (int)StringCchPrintfExW(
                      v45,
                      v47,
                      (unsigned __int16 **)&pcchLength,
                      &v59,
                      0x800u,
                      L"%s%s%s",
                      L"PFN=",
                      v53,
                      L"|") < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v45 = (wchar_t *)pcchLength;
          v47 = v59;
        }
        v9 = 0;
        pcchLength = (size_t)v45;
        v61 = v47;
        if ( v2[7].count == 1 )
        {
          v9 = StringCchPrintfExW(
                 v45,
                 v47,
                 (unsigned __int16 **)&pcchLength,
                 &v61,
                 0x800u,
                 L"%s%s%s",
                 L"BF=",
                 L"TRUE",
                 L"|");
          if ( (v9 & 0x80000000) != 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        *v63 = v62;
        return v9;
      }
      v9 = -2147024882;
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return v9;
      v56 = 47;
      goto LABEL_63;
    }
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return v9;
    v56 = 46;
LABEL_62:
    v57 = (unsigned int)v8;
LABEL_64:
    WPP_SF_d(*((_QWORD *)v55 + 2), v56, WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids, v57);
    return v9;
  }
  v30 = StringLengthWorkerW(v27, v10, &pcchLength);
  v9 = v30;
  if ( v30 >= 0 )
  {
    v29 = pcchLength + 7;
    goto LABEL_17;
  }
  v55 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
        (unsigned int)v30);
      v55 = WPP_GLOBAL_Control;
    }
    if ( v55 != (LPCOLESTR)&WPP_GLOBAL_Control && (v55[14] & 1) != 0 )
    {
      v56 = 45;
      goto LABEL_63;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000d290  mov     [rsp-8+arg_10], rbx
0x18000d295  push    rbp
0x18000d296  push    rsi
0x18000d297  push    rdi
0x18000d298  push    r12
0x18000d29a  push    r13
0x18000d29c  push    r14
0x18000d29e  push    r15
0x18000d2a0  lea     rbp, [rsp-27h]
0x18000d2a5  sub     rsp, 90h
0x18000d2ac  mov     rax, cs:__security_cookie
0x18000d2b3  xor     rax, rsp
0x18000d2b6  mov     [rbp+57h+var_38], rax
0x18000d2ba  mov     r15, rcx
0x18000d2bd  mov     [rbp+57h+var_60], rcx
0x18000d2c1  xor     ecx, ecx; unsigned int
0x18000d2c3  mov     [rbp+57h+var_50], rdx
0x18000d2c7  mov     [rdx], rcx
0x18000d2ca  lea     r8, [rbp+57h+pszDest]; unsigned int *
0x18000d2ce  mov     dword ptr [rbp+57h+pszDest], ecx
0x18000d2d1  mov     rax, [r15+18h]
0x18000d2d5  lea     r13, [r15+50h]
0x18000d2d9  neg     rax
0x18000d2dc  mov     [rbp+57h+var_40], rcx
0x18000d2e0  mov     rax, [r15+20h]
0x18000d2e4  lea     r12, [r15+40h]
0x18000d2e8  mov     r14d, [r12]
0x18000d2ec  sbb     rdi, rdi
0x18000d2ef  and     edi, 15Eh
0x18000d2f5  mov     rdx, r13; struct _INET_FIREWALL_AC_BINARIES *
0x18000d2f8  add     rdi, 18h
0x18000d2fc  neg     rax
0x18000d2ff  sbb     rsi, rsi
0x18000d302  and     esi, 15Bh
0x18000d308  call    ?FwAppCGetBinariesSize@@YAJKPEAU_INET_FIREWALL_AC_BINARIES@@PEAK@Z; FwAppCGetBinariesSize(ulong,_INET_FIREWALL_AC_BINARIES *,ulong *)
0x18000d30d  mov     ebx, eax
0x18000d30f  test    eax, eax
0x18000d311  js      loc_18000D827
0x18000d317  mov     r10d, dword ptr [rbp+57h+pszDest]
0x18000d31b  mov     r11d, 2710h
0x18000d321  mov     rcx, [r15+28h]; psz
0x18000d325  imul    eax, r14d, 157h
0x18000d32c  add     rax, rsi
0x18000d32f  add     r10, rax
0x18000d332  xor     eax, eax
0x18000d334  add     r10, rdi
0x18000d337  mov     [rbp+57h+pcchLength], rax
0x18000d33b  test    rcx, rcx
0x18000d33e  jz      short loc_18000D35E
0x18000d340  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x18000d344  mov     edx, r11d; cchMax
0x18000d347  call    StringLengthWorkerW
0x18000d34c  mov     ebx, eax
0x18000d34e  test    eax, eax
0x18000d350  js      loc_18000D86E
0x18000d356  mov     rax, [rbp+57h+pcchLength]
0x18000d35a  add     rax, 5
0x18000d35e  mov     rcx, [r15+30h]; psz
0x18000d362  mov     eax, eax
0x18000d364  add     r10, rax
0x18000d367  xor     eax, eax
0x18000d369  mov     [rbp+57h+pcchLength], rax
0x18000d36d  test    rcx, rcx
0x18000d370  jz      short loc_18000D390
0x18000d372  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x18000d376  mov     rdx, r11; cchMax
0x18000d379  call    StringLengthWorkerW
0x18000d37e  mov     ebx, eax
0x18000d380  test    eax, eax
0x18000d382  js      loc_18000D8C2
0x18000d388  mov     rax, [rbp+57h+pcchLength]
0x18000d38c  add     rax, 8
0x18000d390  mov     rcx, [r15+38h]; psz
0x18000d394  mov     eax, eax
0x18000d396  add     r10, rax
0x18000d399  xor     eax, eax
0x18000d39b  mov     [rbp+57h+pcchLength], rax
0x18000d39f  test    rcx, rcx
0x18000d3a2  jz      short loc_18000D3C2
0x18000d3a4  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x18000d3a8  mov     rdx, r11; cchMax
0x18000d3ab  call    StringLengthWorkerW
0x18000d3b0  mov     ebx, eax
0x18000d3b2  test    eax, eax
0x18000d3b4  js      loc_18000D91E
0x18000d3ba  mov     rax, [rbp+57h+pcchLength]
0x18000d3be  add     rax, 8
0x18000d3c2  mov     rcx, [r15+60h]; psz
0x18000d3c6  mov     eax, eax
0x18000d3c8  add     r10, rax
0x18000d3cb  xor     eax, eax
0x18000d3cd  mov     [rbp+57h+pcchLength], rax
0x18000d3d1  test    rcx, rcx
0x18000d3d4  jz      short loc_18000D3F4
0x18000d3d6  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x18000d3da  mov     rdx, r11; cchMax
0x18000d3dd  call    StringLengthWorkerW
0x18000d3e2  mov     ebx, eax
0x18000d3e4  test    eax, eax
0x18000d3e6  js      loc_18000D97A
0x18000d3ec  mov     rax, [rbp+57h+pcchLength]
0x18000d3f0  add     rax, 5
0x18000d3f4  mov     rcx, [r15+68h]; psz
0x18000d3f8  mov     eax, eax
0x18000d3fa  add     r10, rax
0x18000d3fd  xor     eax, eax
0x18000d3ff  mov     [rbp+57h+pcchLength], rax
0x18000d403  test    rcx, rcx
0x18000d406  jz      short loc_18000D426
0x18000d408  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x18000d40c  mov     rdx, r11; cchMax
0x18000d40f  call    StringLengthWorkerW
0x18000d414  mov     ebx, eax
0x18000d416  test    eax, eax
0x18000d418  js      loc_18000D9D6
0x18000d41e  mov     rax, [rbp+57h+pcchLength]
0x18000d422  add     rax, 7
0x18000d426  mov     ecx, 0Ch
0x18000d42b  mov     edi, eax
0x18000d42d  lea     r8, [rbp+57h+var_40]
0x18000d431  lea     esi, [rcx-0Bh]
0x18000d434  cmp     [r15+70h], esi
0x18000d438  lea     edx, [rsi+1]
0x18000d43b  cmovnz  ecx, esi
0x18000d43e  add     rdi, r10
0x18000d441  add     rdi, rcx
0x18000d444  mov     rcx, rdi
0x18000d447  mov     [rbp+57h+var_70], rdi
0x18000d44b  call    cs:__imp_FwSizeTMultiply
0x18000d451  mov     ebx, eax
0x18000d453  test    eax, eax
0x18000d455  js      loc_18000DA32
0x18000d45b  mov     rcx, [rbp+57h+var_40]
0x18000d45f  call    cs:__imp_FwAlloc
0x18000d465  mov     [rbp+57h+var_58], rax
0x18000d469  mov     r10, rax
0x18000d46c  test    rax, rax
0x18000d46f  jz      loc_18000DA58
0x18000d475  movzx   ecx, word ptr [r15+8]
0x18000d47a  lea     r14, asc_18003D4F8; "|"
0x18000d481  mov     [rsp+0C0h+var_80], r14
0x18000d486  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18000d48a  mov     [rbp+57h+pszDest], rax
0x18000d48e  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x18000d492  movzx   eax, cl
0x18000d495  mov     rdx, rdi; unsigned __int64
0x18000d498  mov     dword ptr [rsp+0C0h+var_88], eax
0x18000d49c  lea     rax, aVDDS; "v%d.%d%s"
0x18000d4a3  shr     ecx, 8
0x18000d4a6  mov     dword ptr [rsp+0C0h+var_90], ecx
0x18000d4aa  mov     rcx, r10; pszDest
0x18000d4ad  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x18000d4b2  mov     dword ptr [rsp+0C0h+var_A0], 800h; unsigned int
0x18000d4ba  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000d4bf  test    eax, eax
0x18000d4c1  js      loc_18000DA88
0x18000d4c7  mov     rdi, [rbp+57h+pszDest]
0x18000d4cb  lea     rdx, [rbp+57h+pcchLength]; StringSid
0x18000d4cf  mov     rbx, [rbp+57h+var_70]
0x18000d4d3  mov     rcx, [r15+18h]; Sid
0x18000d4d7  mov     [rbp+57h+pszDest], rdi
0x18000d4db  mov     [rbp+57h+var_70], rbx
0x18000d4df  mov     [rbp+57h+pcchLength], 0
0x18000d4e7  call    cs:__imp_ConvertSidToStringSidW
0x18000d4ed  mov     rax, [rbp+57h+pcchLength]
0x18000d4f1  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18000d4f5  mov     [rsp+0C0h+var_80], r14
0x18000d4fa  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x18000d4fe  mov     [rsp+0C0h+var_88], rax
0x18000d503  lea     r14, aSSS_2; "%s%s%s"
0x18000d50a  lea     rax, aApppkgid; "AppPkgId="
0x18000d511  mov     rdx, rbx; unsigned __int64
0x18000d514  mov     [rsp+0C0h+var_90], rax
0x18000d519  mov     rcx, rdi; pszDest
0x18000d51c  mov     [rsp+0C0h+var_98], r14; unsigned __int16 *
0x18000d521  mov     dword ptr [rsp+0C0h+var_A0], 800h; unsigned int
0x18000d529  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000d52e  mov     ebx, eax
0x18000d530  test    eax, eax
0x18000d532  js      loc_18000DA92
0x18000d538  mov     rcx, [rbp+57h+pcchLength]; hMem
0x18000d53c  call    cs:__imp_LocalFree
0x18000d542  test    ebx, ebx
0x18000d544  js      loc_18000DA9C
0x18000d54a  mov     rdi, [rbp+57h+pszDest]
0x18000d54e  lea     rdx, [rbp+57h+pcchLength]; StringSid
0x18000d552  mov     rbx, [rbp+57h+var_70]
0x18000d556  mov     rcx, [r15+20h]; Sid
0x18000d55a  mov     [rbp+57h+pszDest], rdi
0x18000d55e  mov     [rbp+57h+var_70], rbx
0x18000d562  mov     [rbp+57h+pcchLength], 0
0x18000d56a  call    cs:__imp_ConvertSidToStringSidW
0x18000d570  lea     rax, asc_18003D4F8; "|"
0x18000d577  mov     rdx, rbx; unsigned __int64
0x18000d57a  mov     [rsp+0C0h+var_80], rax
0x18000d57f  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18000d583  mov     rax, [rbp+57h+pcchLength]
0x18000d587  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x18000d58b  mov     [rsp+0C0h+var_88], rax
0x18000d590  mov     rcx, rdi; pszDest
0x18000d593  lea     rax, aLuown; "LUOwn="
0x18000d59a  mov     [rsp+0C0h+var_90], rax
0x18000d59f  mov     [rsp+0C0h+var_98], r14; unsigned __int16 *
0x18000d5a4  mov     dword ptr [rsp+0C0h+var_A0], 800h; unsigned __int16 *
0x18000d5ac  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000d5b1  mov     r14d, eax
0x18000d5b4  test    eax, eax
0x18000d5b6  js      loc_18000DAA6
0x18000d5bc  mov     rcx, [rbp+57h+pcchLength]; hMem
0x18000d5c0  call    cs:__imp_LocalFree
0x18000d5c6  mov     rbx, [rbp+57h+pszDest]
0x18000d5ca  mov     rdi, [rbp+57h+var_70]
0x18000d5ce  mov     [rbp+57h+pszDest], rbx
0x18000d5d2  mov     [rbp+57h+var_70], rdi
0x18000d5d6  test    r14d, r14d
0x18000d5d9  js      loc_18000DAB0
0x18000d5df  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18000d5e3  mov     [rsp+0C0h+var_98], r12; struct _INET_FIREWALL_AC_CAPABILITIES *
0x18000d5e8  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x18000d5ec  mov     rdx, rdi; unsigned __int64
0x18000d5ef  mov     rcx, rbx; pszDest
0x18000d5f2  call    ?FwRuleSerializeCapabilities@@YAJPEAG_KPEAPEAGPEA_KPEBGPEAU_INET_FIREWALL_AC_CAPABILITIES@@@Z; FwRuleSerializeCapabilities(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ushort const *,_INET_FIREWALL_AC_CAPABILITIES *)
0x18000d5f7  test    eax, eax
0x18000d5f9  js      loc_18000DABA
0x18000d5ff  mov     rdi, [rbp+57h+pszDest]
0x18000d603  xor     r12d, r12d
0x18000d606  mov     r14, [rbp+57h+var_70]
0x18000d60a  xor     ebx, ebx
0x18000d60c  mov     [rbp+57h+pcchLength], rdi
0x18000d610  mov     [rbp+57h+var_70], r14
0x18000d614  cmp     [r13+0], ebx
0x18000d618  ja      loc_18000DAC4
0x18000d61e  test    r12d, r12d
0x18000d621  js      loc_18000DB35
0x18000d627  mov     rax, [r15+28h]
0x18000d62b  lea     rbx, asc_18003D4F8; "|"
0x18000d632  lea     r12, aSSS_2; "%s%s%s"
0x18000d639  mov     r13d, 800h
0x18000d63f  test    rax, rax
0x18000d642  jz      short loc_18000D68F
0x18000d644  mov     [rsp+0C0h+var_80], rbx
0x18000d649  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18000d64d  mov     [rsp+0C0h+var_88], rax
0x18000d652  lea     r8, [rbp+57h+pcchLength]; unsigned __int16 **
0x18000d656  lea     rax, aM; "M="
0x18000d65d  mov     [rbp+57h+pcchLength], rdi
0x18000d661  mov     [rsp+0C0h+var_90], rax
0x18000d666  mov     rdx, r14; unsigned __int64
0x18000d669  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x18000d66e  mov     rcx, rdi; pszDest
0x18000d671  mov     dword ptr [rsp+0C0h+var_A0], r13d; unsigned int
0x18000d676  mov     [rbp+57h+var_70], r14
0x18000d67a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000d67f  test    eax, eax
0x18000d681  js      loc_18000DB3F
0x18000d687  mov     rdi, [rbp+57h+pcchLength]
0x18000d68b  mov     r14, [rbp+57h+var_70]
0x18000d68f  mov     rax, [r15+30h]
0x18000d693  test    rax, rax
0x18000d696  jz      short loc_18000D6E3
0x18000d698  mov     [rsp+0C0h+var_80], rbx
0x18000d69d  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18000d6a1  mov     [rsp+0C0h+var_88], rax
0x18000d6a6  lea     r8, [rbp+57h+pcchLength]; unsigned __int16 **
0x18000d6aa  lea     rax, aName_0; "Name="
0x18000d6b1  mov     [rbp+57h+pcchLength], rdi
0x18000d6b5  mov     [rsp+0C0h+var_90], rax
0x18000d6ba  mov     rdx, r14; unsigned __int64
0x18000d6bd  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x18000d6c2  mov     rcx, rdi; pszDest
0x18000d6c5  mov     dword ptr [rsp+0C0h+var_A0], r13d; unsigned int
0x18000d6ca  mov     [rbp+57h+var_70], r14
0x18000d6ce  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000d6d3  test    eax, eax
0x18000d6d5  js      loc_18000DB49
0x18000d6db  mov     rdi, [rbp+57h+pcchLength]
0x18000d6df  mov     r14, [rbp+57h+var_70]
0x18000d6e3  mov     rax, [r15+38h]
0x18000d6e7  test    rax, rax
0x18000d6ea  jz      short loc_18000D737
0x18000d6ec  mov     [rsp+0C0h+var_80], rbx
0x18000d6f1  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18000d6f5  mov     [rsp+0C0h+var_88], rax
0x18000d6fa  lea     r8, [rbp+57h+pcchLength]; unsigned __int16 **
0x18000d6fe  lea     rax, aDesc; "Desc="
0x18000d705  mov     [rbp+57h+pcchLength], rdi
0x18000d709  mov     [rsp+0C0h+var_90], rax
0x18000d70e  mov     rdx, r14; unsigned __int64
0x18000d711  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x18000d716  mov     rcx, rdi; pszDest
0x18000d719  mov     dword ptr [rsp+0C0h+var_A0], r13d; unsigned int
0x18000d71e  mov     [rbp+57h+var_70], r14
0x18000d722  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000d727  test    eax, eax
0x18000d729  js      loc_18000DB53
0x18000d72f  mov     rdi, [rbp+57h+pcchLength]
0x18000d733  mov     r14, [rbp+57h+var_70]
0x18000d737  mov     rax, [r15+60h]
0x18000d73b  test    rax, rax
0x18000d73e  jz      short loc_18000D78B
  ... truncated ...
```
