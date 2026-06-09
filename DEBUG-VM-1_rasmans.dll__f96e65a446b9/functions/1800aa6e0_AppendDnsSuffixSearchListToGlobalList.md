# AppendDnsSuffixSearchListToGlobalList

- ea: `0x1800aa6e0`
- end: `0x1800ab026`
- name: `AppendDnsSuffixSearchListToGlobalList`
- size: `2374`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1800db0ac`
- `0x1800dde2c`
- `0x1800de2d8`

## callees

- `0x180003c5c`
- `0x180003cac`
- `0x180005e34`
- `0x1800a7b40`
- `0x1800a8fc4`
- `0x1800a92e0`
- `0x1800a93e8`
- `0x1800aa0e0`
- `0x1800aa6e0`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcstok_s` at `0x1800aab0f`
- `msvcrt!wcstok_s` at `0x1800aaba0`
- `msvcrt!wcstok_s` at `0x1800aad0e`
- `msvcrt!wcstok_s` at `0x1800aab0f`
- `msvcrt!wcstok_s` at `0x1800aaba0`
- `msvcrt!wcstok_s` at `0x1800aad0e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800aa7ed`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800aa7ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa8e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa987`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa8e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa987`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa821`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa821`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa9f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa9f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aafd9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aafd9`
- `IPHLPAPI!FreeDnsSettings` at `0x1800aa9d9`
- `IPHLPAPI!FreeDnsSettings` at `0x1800aa9d9`
- `IPHLPAPI!SetDnsSettings` at `0x1800aaf5b`
- `IPHLPAPI!SetDnsSettings` at `0x1800aaf5b`
- `IPHLPAPI!GetDnsSettings` at `0x1800aa884`
- `IPHLPAPI!GetDnsSettings` at `0x1800aa884`

## string_xrefs

- `0x1800aa7f3`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800aa7fa`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppendDnsSuffixSearchListToGlobalList(__int64 a1, unsigned int a2)
{
  struct _LIST_ENTRY *v2; // rcx
  BYTE *v3; // rdi
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int DnsSettings; // eax
  unsigned int v7; // r12d
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  BYTE *v10; // rbx
  PWSTR SearchList; // rbx
  unsigned int v12; // eax
  unsigned int v13; // eax
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // rdx
  __int64 result; // rax
  wchar_t *i; // rcx
  wchar_t *v18; // rax
  __int64 v19; // r8
  wchar_t *v20; // rax
  _QWORD *v21; // rdi
  _QWORD *v22; // rsi
  __int64 v23; // r8
  _QWORD *j; // rbx
  _WORD *v25; // rdx
  unsigned __int64 v26; // r10
  unsigned __int64 v27; // r8
  _QWORD *v28; // rcx
  _QWORD *k; // r15
  _QWORD *v30; // r13
  _QWORD *v31; // rbx
  __int64 v32; // rbx
  unsigned int m; // r15d
  __int64 v34; // rdx
  __int64 v35; // r8
  _QWORD *n; // rbx
  _WORD *v37; // rdx
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // r8
  _QWORD *v40; // rcx
  bool v41; // zf
  __int64 v42; // rdx
  __int64 v43; // r8
  _QWORD *v44; // rdx
  WCHAR *p_Block; // rax
  const BYTE *p_lpData; // rcx
  BYTE *v47; // [rsp+30h] [rbp-1A8h]
  DWORD cbData; // [rsp+38h] [rbp-1A0h] BYREF
  int v49; // [rsp+3Ch] [rbp-19Ch]
  HKEY hKey; // [rsp+40h] [rbp-198h] BYREF
  wchar_t *Context; // [rsp+48h] [rbp-190h] BYREF
  BYTE *v52; // [rsp+50h] [rbp-188h]
  unsigned int v53; // [rsp+58h] [rbp-180h]
  __int64 v54; // [rsp+60h] [rbp-178h]
  char v55[8]; // [rsp+68h] [rbp-170h] BYREF
  __int128 v56; // [rsp+70h] [rbp-168h]
  __int64 v57; // [rsp+80h] [rbp-158h]
  DNS_SETTINGS v58; // [rsp+88h] [rbp-150h] BYREF
  DNS_SETTINGS Settings; // [rsp+B0h] [rbp-128h] BYREF
  char v60[8]; // [rsp+D8h] [rbp-100h] BYREF
  BYTE *lpData; // [rsp+E0h] [rbp-F8h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-E8h]
  unsigned __int64 v63; // [rsp+F8h] [rbp-E0h]
  char v64[8]; // [rsp+100h] [rbp-D8h] BYREF
  void *v65; // [rsp+108h] [rbp-D0h]
  __int64 v66; // [rsp+118h] [rbp-C0h]
  unsigned __int64 v67; // [rsp+120h] [rbp-B8h]
  char v68[8]; // [rsp+128h] [rbp-B0h] BYREF
  void *Block; // [rsp+130h] [rbp-A8h] BYREF
  __int64 v70; // [rsp+140h] [rbp-98h]
  unsigned __int64 v71; // [rsp+148h] [rbp-90h]
  char v72[8]; // [rsp+150h] [rbp-88h] BYREF
  void *v73; // [rsp+158h] [rbp-80h] BYREF
  unsigned __int64 v74; // [rsp+168h] [rbp-70h]
  unsigned __int64 v75; // [rsp+170h] [rbp-68h]
  char v76[8]; // [rsp+178h] [rbp-60h] BYREF
  void *v77; // [rsp+180h] [rbp-58h] BYREF
  unsigned __int64 v78; // [rsp+190h] [rbp-48h]
  unsigned __int64 v79; // [rsp+198h] [rbp-40h]
  std::bad_alloc *v80; // [rsp+1A0h] [rbp-38h] BYREF

  v53 = a2;
  v54 = a1;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 10, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, a2);
  }
  v3 = 0;
  v47 = 0;
  v52 = 0;
  cbData = 0;
  memset(&Settings, 0, sizeof(Settings));
  memset(&v58, 0, sizeof(v58));
  hKey = 0;
  v56 = 0;
  v57 = 0;
  v63 = 7;
  v62 = 0;
  LOWORD(lpData) = 0;
  v71 = 7;
  v70 = 0;
  LOWORD(Block) = 0;
  Context = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v2);
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !IsStateSeparationEnabled )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  DnsSettings = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20007u, &hKey);
  v7 = DnsSettings;
  if ( DnsSettings )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v9 = 11;
LABEL_12:
      WPP_SF_d(v8[1].Flink, v9, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, DnsSettings);
      v10 = 0;
      goto LABEL_33;
    }
    goto LABEL_32;
  }
  Settings.Version = 1;
  DnsSettings = GetDnsSettings(&Settings);
  if ( DnsSettings )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v9 = 12;
      goto LABEL_12;
    }
    goto LABEL_32;
  }
  SearchList = Settings.SearchList;
  v12 = RegQueryValueExW(hKey, L"AppendedDnsSuffixSearchList", 0, 0, 0, &cbData);
  v7 = v12;
  v49 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 13, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v12);
    }
    if ( v7 != 2 )
    {
LABEL_32:
      v10 = v47;
      goto LABEL_33;
    }
  }
  if ( cbData )
  {
    try
    {
      v3 = (BYTE *)operator new(saturated_mul(cbData + 1, 2u));
      v47 = v3;
      v52 = v3;
    }
    catch ( std::bad_alloc *v80 )
    {
      v49 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 14, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, 14);
      }
      v10 = 0;
      goto LABEL_47;
    }
    v13 = RegQueryValueExW(hKey, L"AppendedDnsSuffixSearchList", 0, 0, v3, &cbData);
    v7 = v13;
    v49 = v13;
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_32;
      }
      v15 = 15;
      goto LABEL_31;
    }
    *(_WORD *)&v3[2 * cbData] = 0;
  }
  try
  {
    if ( SearchList )
    {
      for ( i = SearchList; ; i = 0 )
      {
        v18 = wcstok_s(i, L",", &Context);
        if ( !v18 )
          break;
        v67 = 7;
        v66 = 0;
        LOWORD(v65) = 0;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        std::wstring::assign(v64);
        std::vector<std::wstring>::push_back(v55, v64);
        if ( v67 >= 8 )
          operator delete(v65);
      }
    }
    if ( v3 )
    {
      v20 = wcstok_s((wchar_t *)v3, L",", &Context);
      v21 = (_QWORD *)*((_QWORD *)&v56 + 1);
      v22 = (_QWORD *)v56;
      while ( v20 )
      {
        v75 = 7;
        v74 = 0;
        LOWORD(v73) = 0;
        v23 = -1;
        do
          ++v23;
        while ( v20[v23] );
        std::wstring::assign(v72);
        for ( j = v22; j != v21; j += 5 )
        {
          v25 = &v73;
          if ( v75 >= 8 )
            v25 = v73;
          v26 = j[3];
          v27 = v74;
          if ( v26 < v74 )
            v27 = j[3];
          v28 = j + 1;
          if ( j[4] >= 8u )
            v28 = (_QWORD *)*v28;
          if ( v27 )
          {
            while ( *(_WORD *)v28 == *v25 )
            {
              v28 = (_QWORD *)((char *)v28 + 2);
              ++v25;
              if ( !--v27 )
                goto LABEL_72;
            }
          }
          else
          {
LABEL_72:
            if ( v26 >= v74 && v26 == v74 )
              break;
          }
        }
        if ( v75 >= 8 )
          operator delete(v73);
        v75 = 7;
        v74 = 0;
        LOWORD(v73) = 0;
        if ( j != v21 )
        {
          for ( k = j + 5; k != v21; k += 5 )
          {
            std::wstring::assign(j, k, 0, -1);
            j += 5;
          }
          v30 = v21 - 5;
          v31 = v21 - 5;
          do
          {
            if ( v31[4] >= 8u )
              operator delete((void *)v31[1]);
            v31[4] = 7;
            v31[3] = 0;
            *((_WORD *)v31 + 4) = 0;
            v31 += 5;
          }
          while ( v31 != v21 );
          v21 -= 5;
          *((_QWORD *)&v56 + 1) = v30;
        }
        v20 = wcstok_s(0, L",", &Context);
      }
    }
    else
    {
      v21 = (_QWORD *)*((_QWORD *)&v56 + 1);
      v22 = (_QWORD *)v56;
    }
    v32 = v54;
    if ( v54 )
    {
      for ( m = 0; m < v53; ++m )
      {
        v34 = *(_QWORD *)(v32 + 8LL * m);
        v79 = 7;
        v78 = 0;
        LOWORD(v77) = 0;
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)(v34 + 2 * v35) );
        std::wstring::assign(v76);
        for ( n = v22; n != v21; n += 5 )
        {
          v37 = &v77;
          if ( v79 >= 8 )
            v37 = v77;
          v38 = n[3];
          v39 = v78;
          if ( v38 < v78 )
            v39 = n[3];
          v40 = n + 1;
          if ( n[4] >= 8u )
            v40 = (_QWORD *)*v40;
          if ( v39 )
          {
            while ( *(_WORD *)v40 == *v37 )
            {
              v40 = (_QWORD *)((char *)v40 + 2);
              ++v37;
              if ( !--v39 )
                goto LABEL_104;
            }
          }
          else
          {
LABEL_104:
            if ( v38 >= v78 && v38 == v78 )
              break;
          }
        }
        if ( v79 >= 8 )
          operator delete(v77);
        v41 = n == v21;
        v32 = v54;
        if ( v41 )
        {
          v42 = *(_QWORD *)(v54 + 8LL * m);
          v67 = 7;
          v66 = 0;
          LOWORD(v65) = 0;
          v43 = -1;
          do
            ++v43;
          while ( *(_WORD *)(v42 + 2 * v43) );
          std::wstring::assign(v64);
          std::vector<std::wstring>::push_back(v55, v64);
          if ( v67 >= 8 )
            operator delete(v65);
          LOWORD(v65) = 0;
          if ( v62 )
            std::wstring::append(v60, L",");
          std::wstring::append(v60, *(_QWORD *)(v32 + 8LL * m));
          v21 = (_QWORD *)*((_QWORD *)&v56 + 1);
          v22 = (_QWORD *)v56;
        }
      }
    }
    while ( v22 != v21 )
    {
      if ( v70 )
        std::wstring::append(v68, L",");
      v44 = v22 + 1;
      if ( v22[4] >= 8u )
        v44 = (_QWORD *)*v44;
      std::wstring::append(v68, v44);
      v22 += 5;
    }
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 16, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, 14);
    }
    v10 = v52;
LABEL_47:
    v7 = v49;
LABEL_33:
    FreeDnsSettings(&Settings);
    if ( v10 )
      operator delete(v10);
    if ( hKey )
      RegCloseKey(hKey);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 19, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v7);
    }
    if ( v71 >= 8 )
      operator delete(Block);
    v71 = 7;
    v70 = 0;
    LOWORD(Block) = 0;
    if ( v63 >= 8 )
      operator delete(lpData);
    v63 = 7;
    v62 = 0;
    LOWORD(lpData) = 0;
    std::vector<std::wstring>::~vector<std::wstring>(v55);
    result = v7;
  }
  v58.Version = 1;
  v58.Flags = 4;
  p_Block = (WCHAR *)&Block;
  if ( v71 >= 8 )
    p_Block = (WCHAR *)Block;
  v58.SearchList = p_Block;
  v13 = SetDnsSettings(&v58);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_32;
    }
    v15 = 17;
  }
  else
  {
    p_lpData = (const BYTE *)&lpData;
    if ( v63 >= 8 )
      p_lpData = lpData;
    v13 = RegSetValueExW(hKey, L"AppendedDnsSuffixSearchList", 0, 1u, p_lpData, 2 * v62 + 2);
    v7 = v13;
    if ( !v13 )
      goto LABEL_32;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_32;
    }
    v15 = 18;
  }
LABEL_31:
  WPP_SF_d(v14[1].Flink, v15, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v13);
  goto LABEL_32;
}

```

## disassembly

```asm
0x1800aa6e0  mov     [rsp+arg_10], rbx
0x1800aa6e5  mov     [rsp+arg_18], rsi
0x1800aa6ea  push    rdi
0x1800aa6eb  push    r12
0x1800aa6ed  push    r13
0x1800aa6ef  push    r14
0x1800aa6f1  push    r15
0x1800aa6f3  sub     rsp, 1B0h
0x1800aa6fa  mov     rax, cs:__security_cookie
0x1800aa701  xor     rax, rsp
0x1800aa704  mov     [rsp+1D8h+var_30], rax
0x1800aa70c  mov     eax, edx
0x1800aa70e  mov     [rsp+1D8h+var_180], edx
0x1800aa712  mov     [rsp+1D8h+var_178], rcx
0x1800aa717  lea     r13, WPP_GLOBAL_Control
0x1800aa71e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa725  cmp     rcx, r13
0x1800aa728  jz      short loc_1800AA74E
0x1800aa72a  test    byte ptr [rcx+1Ch], 1
0x1800aa72e  jz      short loc_1800AA74E
0x1800aa730  cmp     byte ptr [rcx+19h], 6
0x1800aa734  jb      short loc_1800AA74E
0x1800aa736  mov     edx, 0Ah
0x1800aa73b  mov     r9d, eax
0x1800aa73e  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800aa745  mov     rcx, [rcx+10h]
0x1800aa749  call    WPP_SF_d
0x1800aa74e  xor     r14d, r14d
0x1800aa751  mov     edi, r14d
0x1800aa754  mov     [rsp+1D8h+var_1A8], r14
0x1800aa759  mov     [rsp+1D8h+var_188], r14
0x1800aa75e  mov     [rsp+1D8h+cbData], r14d
0x1800aa763  xorps   xmm0, xmm0
0x1800aa766  xor     eax, eax
0x1800aa768  movups  xmmword ptr [rsp+1D8h+Settings.Version], xmm0
0x1800aa770  movups  xmmword ptr [rsp+1D8h+Settings.Hostname], xmm0
0x1800aa778  mov     [rsp+1D8h+Settings.SearchList], rax
0x1800aa780  xorps   xmm1, xmm1
0x1800aa783  movups  xmmword ptr [rsp+1D8h+var_150.Version], xmm1
0x1800aa78b  movups  xmmword ptr [rsp+1D8h+var_150.Hostname], xmm1
0x1800aa793  mov     [rsp+1D8h+var_150.SearchList], rax
0x1800aa79b  mov     [rsp+1D8h+hKey], r14
0x1800aa7a0  movdqu  [rsp+1D8h+var_168], xmm0
0x1800aa7a6  mov     [rsp+1D8h+var_158], r14
0x1800aa7ae  mov     [rsp+1D8h+var_E0], 7
0x1800aa7ba  mov     [rsp+1D8h+var_E8], r14
0x1800aa7c2  mov     word ptr [rsp+1D8h+lpData], r14w
0x1800aa7cb  mov     [rsp+1D8h+var_90], 7
0x1800aa7d7  mov     [rsp+1D8h+var_98], r14
0x1800aa7df  mov     word ptr [rsp+1D8h+Block], r14w
0x1800aa7e8  mov     [rsp+1D8h+Context], r14
0x1800aa7ed  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800aa7f3  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800aa7fa  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800aa801  test    al, al
0x1800aa803  cmovz   rdx, rcx; lpSubKey
0x1800aa807  lea     rax, [rsp+1D8h+hKey]
0x1800aa80c  mov     [rsp+1D8h+phkResult], rax; phkResult
0x1800aa811  mov     r9d, 20007h; samDesired
0x1800aa817  xor     r8d, r8d; ulOptions
0x1800aa81a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aa821  call    cs:__imp_RegOpenKeyExW
0x1800aa827  mov     r12d, eax
0x1800aa82a  test    eax, eax
0x1800aa82c  jz      short loc_1800AA871
0x1800aa82e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa835  cmp     rcx, r13
0x1800aa838  jz      loc_1800AA9CC
0x1800aa83e  test    byte ptr [rcx+1Ch], 1
0x1800aa842  jz      loc_1800AA9CC
0x1800aa848  cmp     byte ptr [rcx+19h], 2
0x1800aa84c  jb      loc_1800AA9CC
0x1800aa852  lea     edx, [r14+0Bh]
0x1800aa856  mov     r9d, eax
0x1800aa859  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800aa860  mov     rcx, [rcx+10h]
0x1800aa864  call    WPP_SF_d
0x1800aa869  mov     rbx, r14
0x1800aa86c  jmp     loc_1800AA9D1
0x1800aa871  mov     [rsp+1D8h+Settings.Version], 1
0x1800aa87c  lea     rcx, [rsp+1D8h+Settings]; Settings
0x1800aa884  call    cs:__imp_GetDnsSettings
0x1800aa88a  test    eax, eax
0x1800aa88c  jz      short loc_1800AA8B9
0x1800aa88e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa895  cmp     rcx, r13
0x1800aa898  jz      loc_1800AA9CC
0x1800aa89e  test    byte ptr [rcx+1Ch], 1
0x1800aa8a2  jz      loc_1800AA9CC
0x1800aa8a8  cmp     byte ptr [rcx+19h], 2
0x1800aa8ac  jb      loc_1800AA9CC
0x1800aa8b2  mov     edx, 0Ch
0x1800aa8b7  jmp     short loc_1800AA856
0x1800aa8b9  mov     rbx, [rsp+1D8h+Settings.SearchList]
0x1800aa8c1  lea     rax, [rsp+1D8h+cbData]
0x1800aa8c6  mov     [rsp+1D8h+lpcbData], rax; lpcbData
0x1800aa8cb  mov     [rsp+1D8h+phkResult], r14; lpData
0x1800aa8d0  xor     r9d, r9d; lpType
0x1800aa8d3  xor     r8d, r8d; lpReserved
0x1800aa8d6  lea     rdx, aAppendeddnssuf; "AppendedDnsSuffixSearchList"
0x1800aa8dd  mov     rcx, [rsp+1D8h+hKey]; hKey
0x1800aa8e2  call    cs:__imp_RegQueryValueExW
0x1800aa8e8  mov     r12d, eax
0x1800aa8eb  mov     [rsp+1D8h+var_19C], eax
0x1800aa8ef  test    eax, eax
0x1800aa8f1  jz      short loc_1800AA92D
0x1800aa8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa8fa  cmp     rcx, r13
0x1800aa8fd  jz      short loc_1800AA923
0x1800aa8ff  test    byte ptr [rcx+1Ch], 1
0x1800aa903  jz      short loc_1800AA923
0x1800aa905  cmp     byte ptr [rcx+19h], 2
0x1800aa909  jb      short loc_1800AA923
0x1800aa90b  mov     edx, 0Dh
0x1800aa910  mov     r9d, eax
0x1800aa913  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800aa91a  mov     rcx, [rcx+10h]
0x1800aa91e  call    WPP_SF_d
0x1800aa923  cmp     r12d, 2
0x1800aa927  jnz     loc_1800AA9CC
0x1800aa92d  cmp     [rsp+1D8h+cbData], r14d
0x1800aa932  jbe     loc_1800AAAF3
0x1800aa938  mov     ecx, [rsp+1D8h+cbData]
0x1800aa93c  inc     ecx
0x1800aa93e  mov     eax, 2
0x1800aa943  mul     rcx
0x1800aa946  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800aa94d  cmovb   rax, rsi
0x1800aa951  mov     rcx, rax; Size
0x1800aa954  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800aa959  mov     rdi, rax
0x1800aa95c  mov     [rsp+1D8h+var_1A8], rax
0x1800aa961  mov     [rsp+1D8h+var_188], rax
0x1800aa966  lea     rax, [rsp+1D8h+cbData]
0x1800aa96b  mov     [rsp+1D8h+lpcbData], rax; lpcbData
0x1800aa970  mov     [rsp+1D8h+phkResult], rdi; lpData
0x1800aa975  xor     r9d, r9d; lpType
0x1800aa978  xor     r8d, r8d; lpReserved
0x1800aa97b  lea     rdx, aAppendeddnssuf; "AppendedDnsSuffixSearchList"
0x1800aa982  mov     rcx, [rsp+1D8h+hKey]; hKey
0x1800aa987  call    cs:__imp_RegQueryValueExW
0x1800aa98d  mov     r12d, eax
0x1800aa990  mov     [rsp+1D8h+var_19C], eax
0x1800aa994  test    eax, eax
0x1800aa996  jz      loc_1800AAAD1
0x1800aa99c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa9a3  cmp     rcx, r13
0x1800aa9a6  jz      short loc_1800AA9CC
0x1800aa9a8  test    byte ptr [rcx+1Ch], 1
0x1800aa9ac  jz      short loc_1800AA9CC
0x1800aa9ae  cmp     byte ptr [rcx+19h], 2
0x1800aa9b2  jb      short loc_1800AA9CC
0x1800aa9b4  mov     edx, 0Fh
0x1800aa9b9  mov     r9d, eax
0x1800aa9bc  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800aa9c3  mov     rcx, [rcx+10h]
0x1800aa9c7  call    WPP_SF_d
0x1800aa9cc  mov     rbx, [rsp+1D8h+var_1A8]
0x1800aa9d1  lea     rcx, [rsp+1D8h+Settings]; Settings
0x1800aa9d9  call    cs:__imp_FreeDnsSettings
0x1800aa9df  test    rbx, rbx
0x1800aa9e2  jz      short loc_1800AA9EC
0x1800aa9e4  mov     rcx, rbx; Block
0x1800aa9e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aa9ec  mov     rcx, [rsp+1D8h+hKey]; hKey
0x1800aa9f1  test    rcx, rcx
0x1800aa9f4  jz      short loc_1800AA9FC
0x1800aa9f6  call    cs:__imp_RegCloseKey
0x1800aa9fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaa03  cmp     rcx, r13
0x1800aaa06  jz      short loc_1800AAA2D
0x1800aaa08  test    byte ptr [rcx+1Ch], 1
0x1800aaa0c  jz      short loc_1800AAA2D
0x1800aaa0e  cmp     byte ptr [rcx+19h], 6
0x1800aaa12  jb      short loc_1800AAA2D
0x1800aaa14  mov     edx, 13h
0x1800aaa19  mov     r9d, r12d
0x1800aaa1c  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800aaa23  mov     rcx, [rcx+10h]
0x1800aaa27  call    WPP_SF_d
0x1800aaa2c  nop
0x1800aaa2d  cmp     [rsp+1D8h+var_90], 8
0x1800aaa36  jb      short loc_1800AAA45
0x1800aaa38  mov     rcx, [rsp+1D8h+Block]; Block
0x1800aaa40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aaa45  mov     [rsp+1D8h+var_90], 7
0x1800aaa51  mov     [rsp+1D8h+var_98], r14
0x1800aaa59  mov     word ptr [rsp+1D8h+Block], r14w
0x1800aaa62  cmp     [rsp+1D8h+var_E0], 8
0x1800aaa6b  jb      short loc_1800AAA7A
0x1800aaa6d  mov     rcx, [rsp+1D8h+lpData]; Block
0x1800aaa75  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aaa7a  mov     [rsp+1D8h+var_E0], 7
0x1800aaa86  mov     [rsp+1D8h+var_E8], r14
0x1800aaa8e  mov     word ptr [rsp+1D8h+lpData], r14w
0x1800aaa97  lea     rcx, [rsp+1D8h+var_170]
0x1800aaa9c  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800aaaa1  mov     eax, r12d
0x1800aaaa4  mov     rcx, [rsp+1D8h+var_30]
0x1800aaaac  xor     rcx, rsp; StackCookie
0x1800aaaaf  call    __security_check_cookie
0x1800aaab4  lea     r11, [rsp+1D8h+var_28]
0x1800aaabc  mov     rbx, [r11+40h]
0x1800aaac0  mov     rsi, [r11+48h]
0x1800aaac4  mov     rsp, r11
0x1800aaac7  pop     r15
0x1800aaac9  pop     r14
0x1800aaacb  pop     r13
0x1800aaacd  pop     r12
0x1800aaacf  pop     rdi
0x1800aaad0  retn
0x1800aaad1  mov     eax, [rsp+1D8h+cbData]
0x1800aaad5  mov     [rdi+rax*2], r14w
0x1800aaada  jmp     short loc_1800AAAF7
0x1800aaadc  xor     r14d, r14d
0x1800aaadf  mov     ebx, r14d
0x1800aaae2  lea     r13, WPP_GLOBAL_Control
0x1800aaae9  mov     r12d, [rsp+1D8h+var_19C]
0x1800aaaee  jmp     loc_1800AA9D1
0x1800aaaf3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800aaaf7  test    rbx, rbx
0x1800aaafa  jz      loc_1800AAB88
0x1800aab00  mov     rcx, rbx; String
0x1800aab03  lea     r8, [rsp+1D8h+Context]; Context
0x1800aab08  lea     rdx, Delimiter; ","
0x1800aab0f  call    cs:__imp_wcstok_s
0x1800aab15  test    rax, rax
0x1800aab18  jz      short loc_1800AAB88
0x1800aab1a  mov     [rsp+1D8h+var_B8], 7
0x1800aab26  mov     [rsp+1D8h+var_C0], r14
0x1800aab2e  mov     word ptr [rsp+1D8h+var_D0], r14w
0x1800aab37  mov     r8, rsi
0x1800aab3a  inc     r8
0x1800aab3d  cmp     [rax+r8*2], r14w
0x1800aab42  jnz     short loc_1800AAB3A
0x1800aab44  mov     rdx, rax
0x1800aab47  lea     rcx, [rsp+1D8h+var_D8]
0x1800aab4f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800aab54  nop
0x1800aab55  lea     rdx, [rsp+1D8h+var_D8]
0x1800aab5d  lea     rcx, [rsp+1D8h+var_170]
0x1800aab62  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800aab67  nop
0x1800aab68  cmp     [rsp+1D8h+var_B8], 8
0x1800aab71  jb      short loc_1800AAB81
0x1800aab73  mov     rcx, [rsp+1D8h+var_D0]; Block
0x1800aab7b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aab80  nop
0x1800aab81  xor     ecx, ecx
0x1800aab83  jmp     loc_1800AAB03
0x1800aab88  test    rdi, rdi
0x1800aab8b  jz      loc_1800AAD19
0x1800aab91  lea     r8, [rsp+1D8h+Context]; Context
0x1800aab96  lea     rdx, Delimiter; ","
0x1800aab9d  mov     rcx, rdi; String
0x1800aaba0  call    cs:__imp_wcstok_s
0x1800aaba6  mov     rdi, qword ptr [rsp+1D8h+var_168+8]
0x1800aabab  mov     rsi, qword ptr [rsp+1D8h+var_168]
0x1800aabb0  test    rax, rax
0x1800aabb3  jz      loc_1800AAD25
0x1800aabb9  mov     r15d, 7
0x1800aabbf  mov     [rsp+1D8h+var_68], r15
0x1800aabc7  mov     [rsp+1D8h+var_70], r14
0x1800aabcf  mov     word ptr [rsp+1D8h+var_80], r14w
0x1800aabd8  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800aabdc  mov     r8, r13
0x1800aabdf  inc     r8
0x1800aabe2  cmp     [rax+r8*2], r14w
0x1800aabe7  jnz     short loc_1800AABDF
0x1800aabe9  mov     rdx, rax
0x1800aabec  lea     rcx, [rsp+1D8h+var_88]
0x1800aabf4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800aabf9  nop
0x1800aabfa  mov     rbx, rsi
0x1800aabfd  mov     r9, [rsp+1D8h+var_70]
0x1800aac05  cmp     rbx, rdi
0x1800aac08  jz      short loc_1800AAC68
0x1800aac0a  lea     rdx, [rsp+1D8h+var_80]
0x1800aac12  cmp     [rsp+1D8h+var_68], 8
0x1800aac1b  cmovnb  rdx, [rsp+1D8h+var_80]
0x1800aac24  mov     r10, [rbx+18h]
0x1800aac28  mov     r8, r9
0x1800aac2b  cmp     r10, r9
0x1800aac2e  cmovb   r8, r10
0x1800aac32  lea     rcx, [rbx+8]
0x1800aac36  cmp     qword ptr [rbx+20h], 8
0x1800aac3b  jb      short loc_1800AAC40
0x1800aac3d  mov     rcx, [rcx]
0x1800aac40  test    r8, r8
0x1800aac43  jz      short loc_1800AAC5B
0x1800aac45  movzx   eax, word ptr [rdx]
0x1800aac48  cmp     [rcx], ax
0x1800aac4b  jnz     short loc_1800AAC62
0x1800aac4d  add     rcx, 2
0x1800aac51  add     rdx, 2
0x1800aac55  sub     r8, 1
0x1800aac59  jnz     short loc_1800AAC45
0x1800aac5b  cmp     r10, r9
0x1800aac5e  jb      short loc_1800AAC62
0x1800aac60  jz      short loc_1800AAC68
  ... truncated ...
```
