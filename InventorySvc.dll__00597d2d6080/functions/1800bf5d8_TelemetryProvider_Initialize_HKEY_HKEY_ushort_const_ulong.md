# TelemetryProvider::Initialize(HKEY__ *,HKEY__ *,ushort const *,ulong)

- ea: `0x1800bf5d8`
- end: `0x1800bfe96`
- name: `?Initialize@TelemetryProvider@@QEAAJPEAUHKEY__@@0PEBGK@Z`
- size: `2238`
- prototype: `__int64 __fastcall(TelemetryProvider *__hidden this, HKEY hKey, HKEY, LPCWSTR lpValue, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800be9e8`

## callees

- `0x180002bf0`
- `0x1800152d0`
- `0x1800bf0c4`
- `0x1800bf40c`
- `0x1800bf5d8`
- `0x1800c0380`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf801`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf8c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf8e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf904`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf9dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf9f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf801`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf8c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf8e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf904`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf9dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf9f8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800bfadb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800bfc6e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800bfadb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800bfc6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf650`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf80f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf925`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf97c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bfa0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bfb87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bfbfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bfe37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf650`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf80f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf925`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf97c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bfa0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bfb87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bfbfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bfe37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bf65e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bf81d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bf933`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bfc08`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bf65e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bf81d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bf933`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bfc08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bfa1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bfb95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bfe45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bfa1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bfb95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bfe45`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800bf98d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800bf98d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf856`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf8a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf969`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf9c1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bfaa5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bfd0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf856`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf8a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf969`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf9c1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bfaa5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bfd0a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800bf7d4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800bfa60`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800bf7d4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800bfa60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bf779`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bf779`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bf70b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bf70b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bfd32`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bfd32`

## string_xrefs

- `0x1800bfe56`: `StringCchCopyW failed [%#x]`
- `0x1800bf785`: `RegCreateKeyExW failed [%d]`
- `0x1800bf719`: `RegOpenKeyExW failed [%d]`
- `0x1800bf9d1`: `Command`
- `0x1800bfe0d`: `Empty command [%#x]`

## pseudocode

```c
__int64 __fastcall TelemetryProvider::Initialize(
        TelemetryProvider *this,
        HKEY hKey,
        HKEY a3,
        LPCWSTR lpValue,
        unsigned int a5)
{
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v11; // rax
  _WORD *v12; // r8
  signed int Key; // ebx
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  LPCWSTR v16; // rcx
  _WORD *v17; // rcx
  HKEY *v18; // r12
  const char *v19; // r9
  __int64 v20; // r8
  HKEY *v21; // r14
  HKEY v22; // rcx
  unsigned int v23; // r15d
  DWORD v24; // ecx
  DWORD v25; // ebx
  HANDLE v26; // rax
  void *v27; // rax
  LSTATUS ValueW; // eax
  DWORD v29; // ebx
  HANDLE v30; // rax
  void *v31; // r14
  DWORD v32; // ebx
  HANDLE v33; // rax
  void *v34; // rax
  HANDLE v35; // rax
  HKEY v36; // rcx
  DWORD v37; // edx
  HKEY v38; // rcx
  const wchar_t *v39; // rcx
  wchar_t *v40; // rax
  wchar_t *v41; // r14
  const char *v42; // r9
  __int64 v43; // r8
  void *v44; // r14
  __int64 v45; // r8
  HANDLE v46; // rax
  int v47; // eax
  __int64 v48; // rcx
  SIZE_T v49; // rbx
  HANDLE v50; // rax
  LPVOID v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rdx
  wchar_t v54; // r8
  wchar_t *v55; // rax
  __int64 v56; // rcx
  __int64 v57; // r8
  wchar_t v58; // r9
  _WORD *v59; // rax
  HKEY v60; // rcx
  bool v61; // al
  bool v62; // cf
  bool v63; // zf
  HKEY v64; // r8
  const unsigned __int16 *v65; // r9
  HKEY v66; // rdx
  int HaveDependenciesRun; // eax
  HANDLE v68; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  bool v73; // [rsp+54h] [rbp-ACh]
  unsigned int pvData; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-A0h]
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwIndex[2]; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v79; // [rsp+80h] [rbp-80h] BYREF
  HKEY v80; // [rsp+88h] [rbp-78h]
  HKEY v81; // [rsp+90h] [rbp-70h]
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-60h] BYREF

  Type = 0;
  v5 = -1;
  pvData = 0;
  v80 = a3;
  v81 = hKey;
  cchValueName = 260;
  *((_DWORD *)this + 14) = a5;
  do
    ++v5;
  while ( lpValue[v5] );
  cbData = 2 * v5 + 2;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 0, cbData);
  *((_QWORD *)this + 2) = v11;
  v12 = v11;
  if ( !v11 )
  {
    Key = -2147024882;
    AslLogCallPrintf(1, "TelemetryProvider::Initialize", 111, "HeapAlloc failed [%#x]", -2147024882);
    return (unsigned int)Key;
  }
  v14 = (unsigned __int64)cbData >> 1;
  if ( !v14 )
  {
    Key = -2147024809;
LABEL_99:
    AslLogCallPrintf(1, "TelemetryProvider::Initialize", 118, "StringCchCopyW failed [%#x]", Key);
    return (unsigned int)Key;
  }
  v15 = 2147483646;
  v16 = lpValue;
  do
  {
    if ( !v15 )
      break;
    if ( !*v16 )
      break;
    *v12++ = *v16++;
    --v15;
    --v14;
  }
  while ( v14 );
  v17 = v12 - 1;
  Key = v14 == 0 ? 0x8007007A : 0;
  if ( v14 )
    v17 = v12;
  *v17 = 0;
  if ( !v14 )
    goto LABEL_99;
  v18 = (HKEY *)((char *)this + 32);
  Key = RegOpenKeyExW(hKey, lpValue, 0, 0x20019u, (PHKEY)this + 4);
  if ( Key )
  {
    v19 = "RegOpenKeyExW failed [%d]";
    v20 = 130;
    goto LABEL_15;
  }
  v21 = (HKEY *)((char *)this + 40);
  Key = RegCreateKeyExW(a3, lpValue, 0, 0, 0, 0xF003Fu, 0, (PHKEY)this + 5, 0);
  if ( Key )
  {
    v19 = "RegCreateKeyExW failed [%d]";
    v20 = 138;
LABEL_15:
    LODWORD(phkResult) = Key;
    AslLogCallPrintf(1, "TelemetryProvider::Initialize", v20, v19, phkResult);
    if ( Key > 0 )
      return (unsigned __int16)Key | 0x80070000;
    return (unsigned int)Key;
  }
  v22 = *v18;
  dwIndex[0] = 1;
  lpMem = 0;
  v23 = -1;
  v73 = 0;
  if ( RegEnumValueW(v22, 0, ValueName, &cchValueName, 0, &Type, 0, &cbData) )
  {
LABEL_47:
    v38 = *v21;
    cbData = 4;
    RegGetValueW(v38, 0, L"Pending", 0x20000010u, 0, &pvData, &cbData);
    v39 = *(const wchar_t **)this;
    *((_BYTE *)this + 51) = pvData == 1;
    if ( v39 && *v39 )
    {
      if ( !*((_QWORD *)this + 1) )
      {
        v40 = wcsstr(v39, L"-m:");
        v41 = v40;
        if ( !v40 )
        {
          v42 = "Empty binary [%#x]";
          v43 = 274;
LABEL_93:
          v47 = -2147467259;
          goto LABEL_94;
        }
        LODWORD(v48) = 0;
        if ( v40[3] != 32 )
        {
          do
          {
            if ( !v40[(unsigned int)v48 + 3] )
              break;
            v48 = (unsigned int)(v48 + 1);
          }
          while ( v40[v48 + 3] != 32 );
        }
        v49 = 2LL * (unsigned int)(v48 + 1);
        v50 = GetProcessHeap();
        v51 = HeapAlloc(v50, 0, v49);
        *((_QWORD *)this + 1) = v51;
        if ( !v51 )
        {
          v47 = -2147024882;
          v42 = "HeapAlloc failed [%#x]";
          v43 = 290;
LABEL_94:
          LODWORD(phkResulta) = v47;
          Key = v47;
          AslLogCallPrintf(1, "TelemetryProvider::Initialize", v43, v42, phkResulta);
          goto LABEL_95;
        }
        LODWORD(v52) = 0;
        if ( v41[3] != 32 )
        {
          do
          {
            v53 = (unsigned int)v52;
            v54 = v41[(unsigned int)v52 + 3];
            if ( !v54 )
              break;
            v52 = (unsigned int)(v52 + 1);
            *(_WORD *)(*((_QWORD *)this + 1) + 2 * v53) = v54;
          }
          while ( v41[v52 + 3] != 32 );
        }
        *(_WORD *)(*((_QWORD *)this + 1) + 2LL * (unsigned int)v52) = 0;
        v55 = wcsstr(*(const wchar_t **)this, L"-f:");
        if ( !v55 )
        {
          v43 = 307;
LABEL_92:
          v42 = "Empty command [%#x]";
          goto LABEL_93;
        }
        LODWORD(v56) = 0;
        if ( v55[3] != 32 )
        {
          do
          {
            v57 = (unsigned int)v56;
            v58 = v55[(unsigned int)v56 + 3];
            if ( !v58 )
              break;
            v56 = (unsigned int)(v56 + 1);
            *(_WORD *)(*(_QWORD *)this + 2 * v57) = v58;
          }
          while ( v55[v56 + 3] != 32 );
        }
        v21 = (HKEY *)((char *)this + 40);
        *(_WORD *)(*(_QWORD *)this + 2LL * (unsigned int)v56) = 0;
      }
      v59 = (_WORD *)*((_QWORD *)this + 1);
      if ( v59 && *v59 )
      {
        v60 = *v21;
        v79 = 0;
        cbData = 8;
        RegGetValueW(v60, 0, L"LastFullSync", 0x20000040u, 0, &v79, &cbData);
        v61 = v79 == 0;
        *((_BYTE *)this + 49) = v79 == 0;
        if ( !v61 )
        {
          *(_QWORD *)dwIndex = 0;
          if ( !v73
            || (GetSystemTimeAsFileTime((LPFILETIME)dwIndex),
                v62 = *(_QWORD *)dwIndex < v79 + 25920000000000LL,
                v63 = *(_QWORD *)dwIndex == v79 + 25920000000000LL,
                *(_QWORD *)dwIndex = 0,
                *((_BYTE *)this + 49) = !v62 && !v63,
                v62 || v63) )
          {
            if ( TelemetryProvider::FullSyncRequestedByOneSettings(lpValue, (unsigned __int64 *)dwIndex) )
            {
              if ( *(_QWORD *)dwIndex <= v79 )
              {
                *((_BYTE *)this + 49) = 0;
              }
              else
              {
                *((_BYTE *)this + 49) = 1;
                AslLogCallPrintf(
                  3,
                  "TelemetryProvider::Initialize",
                  361,
                  "Fullsync requested by OneSettings for %ls",
                  lpValue);
              }
            }
          }
        }
        if ( IsWindowsServer() )
          v23 >>= 1;
        v44 = lpMem;
        v64 = v80;
        v65 = (const unsigned __int16 *)lpMem;
        v66 = v81;
        *((_BYTE *)this + 48) = v23 & 1;
        HaveDependenciesRun = TelemetryProvider::HaveDependenciesRun(this, v66, v64, v65);
        Key = HaveDependenciesRun;
        if ( HaveDependenciesRun >= 0 )
          Key = 0;
        else
          AslLogCallPrintf(
            1,
            "TelemetryProvider::Initialize",
            369,
            "TelemetryProvider::HaveDependenciesRun failed [%#x]",
            HaveDependenciesRun);
        goto LABEL_96;
      }
      v42 = "Empty binary [%#x]";
      v43 = 326;
      goto LABEL_93;
    }
    v43 = 257;
    goto LABEL_92;
  }
  while ( 1 )
  {
    v24 = Type;
    if ( Type - 1 <= 1 )
      break;
    if ( Type == 7 )
    {
      if ( !(unsigned int)_o__wcsicmp(ValueName, L"Dependencies") )
      {
        v25 = cbData;
        v26 = GetProcessHeap();
        v27 = HeapAlloc(v26, 0, v25);
        lpMem = v27;
        if ( !v27 )
        {
          Key = -2147024882;
          LODWORD(phkResulta) = -2147024882;
          AslLogCallPrintf(1, "TelemetryProvider::Initialize", 209, "HeapAlloc failed [%#x]", phkResulta);
          return (unsigned int)Key;
        }
        ValueW = RegGetValueW(*v18, 0, ValueName, 0x20u, 0, v27, &cbData);
        Key = ValueW;
        if ( ValueW )
        {
          AslLogCallPrintf(1, "TelemetryProvider::Initialize", 216, "RegGetValueW failed [%d]", ValueW);
          if ( Key > 0 )
            Key = (unsigned __int16)Key | 0x80070000;
          v44 = lpMem;
          goto LABEL_97;
        }
        goto LABEL_45;
      }
      v24 = Type;
    }
    if ( v24 == 4 )
    {
      cbData = 4;
      Key = RegGetValueW(*v18, 0, ValueName, 0x10u, 0, &pvData, &cbData);
      if ( Key )
      {
        v45 = 227;
        goto LABEL_57;
      }
      if ( (unsigned int)_o__wcsicmp(ValueName, L"Sku") )
      {
        if ( (unsigned int)_o__wcsicmp(ValueName, L"SchedulingNeeded") )
        {
          if ( !(unsigned int)_o__wcsicmp(ValueName, L"Network") )
            *((_BYTE *)this + 50) = pvData == 1;
        }
        else
        {
          v73 = pvData == 1;
        }
      }
      else
      {
        v23 = pvData;
      }
    }
LABEL_45:
    v36 = *v18;
    v37 = dwIndex[0];
    cchValueName = 260;
    ++dwIndex[0];
    if ( RegEnumValueW(v36, v37, ValueName, &cchValueName, 0, &Type, 0, &cbData) )
    {
      v21 = (HKEY *)((char *)this + 40);
      goto LABEL_47;
    }
  }
  v29 = cbData;
  v30 = GetProcessHeap();
  v31 = HeapAlloc(v30, 0, v29);
  if ( !v31 )
  {
    v47 = -2147024882;
    v42 = "HeapAlloc failed [%#x]";
    v43 = 152;
    goto LABEL_94;
  }
  Key = RegGetValueW(*v18, 0, ValueName, 6u, 0, v31, &cbData);
  if ( Key == 234 )
  {
    v32 = cbData;
    v33 = GetProcessHeap();
    v34 = HeapReAlloc(v33, 0, v31, v32);
    if ( !v34 )
    {
      v46 = GetProcessHeap();
      HeapFree(v46, 0, v31);
      v47 = -2147024882;
      v42 = "HeapReAlloc failed [%#x]";
      v43 = 168;
      goto LABEL_94;
    }
    v31 = v34;
    Key = RegGetValueW(*v18, 0, ValueName, 6u, 0, v34, &cbData);
  }
  if ( !Key )
  {
    if ( (unsigned int)_o__wcsicmp(ValueName, L"Command") )
    {
      if ( (unsigned int)_o__wcsicmp(ValueName, L"Binary") )
      {
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v31);
      }
      else
      {
        *((_QWORD *)this + 1) = v31;
      }
    }
    else
    {
      *(_QWORD *)this = v31;
    }
    goto LABEL_45;
  }
  v45 = 180;
LABEL_57:
  AslLogCallPrintf(1, "TelemetryProvider::Initialize", v45, "RegGetValueW failed [%d]", Key);
  if ( Key > 0 )
    Key = (unsigned __int16)Key | 0x80070000;
LABEL_95:
  v44 = lpMem;
LABEL_96:
  if ( v44 )
  {
LABEL_97:
    v68 = GetProcessHeap();
    HeapFree(v68, 0, v44);
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x1800bf5d8  push    rbp
0x1800bf5da  push    rbx
0x1800bf5db  push    rsi
0x1800bf5dc  push    rdi
0x1800bf5dd  push    r12
0x1800bf5df  push    r13
0x1800bf5e1  push    r14
0x1800bf5e3  push    r15
0x1800bf5e5  lea     rbp, [rsp-1C8h]
0x1800bf5ed  sub     rsp, 2C8h
0x1800bf5f4  mov     rax, cs:__security_cookie
0x1800bf5fb  xor     rax, rsp
0x1800bf5fe  mov     [rbp+200h+var_50], rax
0x1800bf605  mov     eax, [rbp+200h+arg_20]
0x1800bf60b  xor     r12d, r12d
0x1800bf60e  mov     [rsp+300h+Type], r12d
0x1800bf613  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bf617  mov     [rsp+300h+pvData], r12d
0x1800bf61c  mov     r13, r9
0x1800bf61f  mov     r15, r8
0x1800bf622  mov     [rbp+200h+var_278], r8
0x1800bf626  mov     r14, rdx
0x1800bf629  mov     [rbp+200h+var_270], rdx
0x1800bf62d  mov     rsi, rcx
0x1800bf630  mov     [rsp+300h+cchValueName], 104h
0x1800bf638  mov     [rcx+38h], eax
0x1800bf63b  inc     rbx
0x1800bf63e  cmp     [r9+rbx*2], r12w
0x1800bf643  jnz     short loc_1800BF63B
0x1800bf645  lea     ebx, ds:2[rbx*2]
0x1800bf64c  mov     [rsp+300h+cbData], ebx
0x1800bf650  call    cs:__imp_GetProcessHeap
0x1800bf656  mov     r8d, ebx; dwBytes
0x1800bf659  xor     edx, edx; dwFlags
0x1800bf65b  mov     rcx, rax; hHeap
0x1800bf65e  call    cs:__imp_HeapAlloc
0x1800bf664  mov     [rsi+10h], rax
0x1800bf668  mov     r8, rax
0x1800bf66b  test    rax, rax
0x1800bf66e  jnz     short loc_1800BF691
0x1800bf670  mov     eax, 8007000Eh
0x1800bf675  lea     r9, aHeapallocFaile; "HeapAlloc failed [%#x]"
0x1800bf67c  mov     r8d, 6Fh ; 'o'
0x1800bf682  mov     dword ptr [rsp+300h+phkResult], eax
0x1800bf686  mov     ebx, eax
0x1800bf688  lea     ecx, [r8-6Eh]
0x1800bf68c  jmp     loc_1800BFE65
0x1800bf691  mov     edx, [rsp+300h+cbData]
0x1800bf695  mov     edi, 1
0x1800bf69a  shr     rdx, 1
0x1800bf69d  jz      loc_1800BFE4D
0x1800bf6a3  mov     eax, 7FFFFFFEh
0x1800bf6a8  mov     rcx, r13
0x1800bf6ab  test    rax, rax
0x1800bf6ae  jz      short loc_1800BF6CE
0x1800bf6b0  movzx   r9d, word ptr [rcx]
0x1800bf6b4  test    r9w, r9w
0x1800bf6b8  jz      short loc_1800BF6CE
0x1800bf6ba  mov     [r8], r9w
0x1800bf6be  add     rcx, 2
0x1800bf6c2  add     r8, 2
0x1800bf6c6  sub     rax, rdi
0x1800bf6c9  sub     rdx, rdi
0x1800bf6cc  jnz     short loc_1800BF6AB
0x1800bf6ce  mov     rax, rdx
0x1800bf6d1  lea     rcx, [r8-2]
0x1800bf6d5  neg     rax
0x1800bf6d8  sbb     ebx, ebx
0x1800bf6da  not     ebx
0x1800bf6dc  and     ebx, 8007007Ah
0x1800bf6e2  test    rdx, rdx
0x1800bf6e5  cmovnz  rcx, r8
0x1800bf6e9  mov     [rcx], r12w
0x1800bf6ed  jz      loc_1800BFE52
0x1800bf6f3  lea     r12, [rsi+20h]
0x1800bf6f7  mov     r9d, 20019h; samDesired
0x1800bf6fd  xor     r8d, r8d; ulOptions
0x1800bf700  mov     [rsp+300h+phkResult], r12; phkResult
0x1800bf705  mov     rdx, r13; lpSubKey
0x1800bf708  mov     rcx, r14; hKey
0x1800bf70b  call    cs:__imp_RegOpenKeyExW
0x1800bf711  mov     ebx, eax
0x1800bf713  xor     eax, eax
0x1800bf715  test    ebx, ebx
0x1800bf717  jz      short loc_1800BF74E
0x1800bf719  lea     r9, aRegopenkeyexwF; "RegOpenKeyExW failed [%d]"
0x1800bf720  mov     r8d, 82h
0x1800bf726  lea     rdx, aTelemetryprovi_2; "TelemetryProvider::Initialize"
0x1800bf72d  mov     dword ptr [rsp+300h+phkResult], ebx
0x1800bf731  mov     ecx, edi
0x1800bf733  call    AslLogCallPrintf
0x1800bf738  test    ebx, ebx
0x1800bf73a  jle     loc_1800BFE71
0x1800bf740  movzx   ebx, bx
0x1800bf743  or      ebx, 80070000h
0x1800bf749  jmp     loc_1800BFE71
0x1800bf74e  mov     [rsp+300h+lpdwDisposition], rax; lpdwDisposition
0x1800bf753  lea     r14, [rsi+28h]
0x1800bf757  mov     [rsp+300h+var_2C8], r14; phkResult
0x1800bf75c  xor     r9d, r9d; lpClass
0x1800bf75f  mov     [rsp+300h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800bf764  xor     r8d, r8d; Reserved
0x1800bf767  mov     [rsp+300h+samDesired], 0F003Fh; samDesired
0x1800bf76f  mov     rdx, r13; lpSubKey
0x1800bf772  mov     rcx, r15; hKey
0x1800bf775  mov     dword ptr [rsp+300h+phkResult], eax; dwOptions
0x1800bf779  call    cs:__imp_RegCreateKeyExW
0x1800bf77f  mov     ebx, eax
0x1800bf781  test    eax, eax
0x1800bf783  jz      short loc_1800BF794
0x1800bf785  lea     r9, aRegcreatekeyex; "RegCreateKeyExW failed [%d]"
0x1800bf78c  mov     r8d, 8Ah
0x1800bf792  jmp     short loc_1800BF726
0x1800bf794  mov     rcx, [r12]; hKey
0x1800bf798  lea     rax, [rsp+300h+cbData]
0x1800bf79d  mov     [rsp+300h+var_2C8], rax; lpcbData
0x1800bf7a2  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x1800bf7a7  xor     ebx, ebx
0x1800bf7a9  mov     [rsp+300h+dwIndex], edi
0x1800bf7ad  lea     rax, [rsp+300h+Type]
0x1800bf7b2  mov     [rsp+300h+lpSecurityAttributes], rbx; lpData
0x1800bf7b7  mov     qword ptr [rsp+300h+samDesired], rax; lpType
0x1800bf7bc  lea     r8, [rbp+200h+ValueName]; lpValueName
0x1800bf7c0  xor     edx, edx; dwIndex
0x1800bf7c2  mov     [rsp+300h+phkResult], rbx; lpReserved
0x1800bf7c7  mov     [rsp+300h+lpMem], rbx
0x1800bf7cc  or      r15d, 0FFFFFFFFh
0x1800bf7d0  mov     [rsp+300h+var_2AC], bl
0x1800bf7d4  call    cs:__imp_RegEnumValueW
0x1800bf7da  test    eax, eax
0x1800bf7dc  jnz     loc_1800BFA72
0x1800bf7e2  mov     ecx, [rsp+300h+Type]
0x1800bf7e6  lea     eax, [rcx-1]
0x1800bf7e9  cmp     eax, edi
0x1800bf7eb  jbe     loc_1800BF921
0x1800bf7f1  cmp     ecx, 7
0x1800bf7f4  jnz     short loc_1800BF871
0x1800bf7f6  lea     rdx, aDependencies; "Dependencies"
0x1800bf7fd  lea     rcx, [rbp+200h+ValueName]
0x1800bf801  call    cs:__imp__o__wcsicmp
0x1800bf807  test    eax, eax
0x1800bf809  jnz     short loc_1800BF86D
0x1800bf80b  mov     ebx, [rsp+300h+cbData]
0x1800bf80f  call    cs:__imp_GetProcessHeap
0x1800bf815  mov     r8d, ebx; dwBytes
0x1800bf818  xor     edx, edx; dwFlags
0x1800bf81a  mov     rcx, rax; hHeap
0x1800bf81d  call    cs:__imp_HeapAlloc
0x1800bf823  xor     r14d, r14d
0x1800bf826  mov     [rsp+300h+lpMem], rax
0x1800bf82b  test    rax, rax
0x1800bf82e  jz      loc_1800BFB35
0x1800bf834  lea     rcx, [rsp+300h+cbData]
0x1800bf839  xor     edx, edx; lpSubKey
0x1800bf83b  mov     [rsp+300h+lpSecurityAttributes], rcx; pcbData
0x1800bf840  lea     r9d, [r14+20h]; dwFlags
0x1800bf844  mov     rcx, [r12]; hkey
0x1800bf848  lea     r8, [rbp+200h+ValueName]; lpValue
0x1800bf84c  mov     qword ptr [rsp+300h+samDesired], rax; pvData
0x1800bf851  mov     [rsp+300h+phkResult], r14; pdwType
0x1800bf856  call    cs:__imp_RegGetValueW
0x1800bf85c  mov     ebx, eax
0x1800bf85e  test    eax, eax
0x1800bf860  jnz     loc_1800BFAFF
0x1800bf866  xor     ebx, ebx
0x1800bf868  jmp     loc_1800BFA21
0x1800bf86d  mov     ecx, [rsp+300h+Type]
0x1800bf871  cmp     ecx, 4
0x1800bf874  jnz     loc_1800BFA21
0x1800bf87a  lea     rax, [rsp+300h+cbData]
0x1800bf87f  mov     [rsp+300h+cbData], ecx
0x1800bf883  mov     [rsp+300h+lpSecurityAttributes], rax; pcbData
0x1800bf888  lea     r9d, [rcx+0Ch]; dwFlags
0x1800bf88c  mov     rcx, [r12]; hkey
0x1800bf890  lea     rax, [rsp+300h+pvData]
0x1800bf895  mov     qword ptr [rsp+300h+samDesired], rax; pvData
0x1800bf89a  lea     r8, [rbp+200h+ValueName]; lpValue
0x1800bf89e  xor     edx, edx; lpSubKey
0x1800bf8a0  mov     [rsp+300h+phkResult], rbx; pdwType
0x1800bf8a5  call    cs:__imp_RegGetValueW
0x1800bf8ab  mov     ebx, eax
0x1800bf8ad  test    eax, eax
0x1800bf8af  jnz     loc_1800BFB52
0x1800bf8b5  lea     rdx, aSku; "Sku"
0x1800bf8bc  lea     rcx, [rbp+200h+ValueName]
0x1800bf8c0  call    cs:__imp__o__wcsicmp
0x1800bf8c6  xor     ebx, ebx
0x1800bf8c8  test    eax, eax
0x1800bf8ca  jnz     short loc_1800BF8D6
0x1800bf8cc  mov     r15d, [rsp+300h+pvData]
0x1800bf8d1  jmp     loc_1800BFA21
0x1800bf8d6  lea     rdx, aSchedulingneed; "SchedulingNeeded"
0x1800bf8dd  lea     rcx, [rbp+200h+ValueName]
0x1800bf8e1  call    cs:__imp__o__wcsicmp
0x1800bf8e7  test    eax, eax
0x1800bf8e9  jnz     short loc_1800BF8F9
0x1800bf8eb  cmp     [rsp+300h+pvData], edi
0x1800bf8ef  setz    [rsp+300h+var_2AC]
0x1800bf8f4  jmp     loc_1800BFA21
0x1800bf8f9  lea     rdx, aNetwork; "Network"
0x1800bf900  lea     rcx, [rbp+200h+ValueName]
0x1800bf904  call    cs:__imp__o__wcsicmp
0x1800bf90a  test    eax, eax
0x1800bf90c  jnz     loc_1800BFA21
0x1800bf912  cmp     [rsp+300h+pvData], edi
0x1800bf916  setz    al
0x1800bf919  mov     [rsi+32h], al
0x1800bf91c  jmp     loc_1800BFA21
0x1800bf921  mov     ebx, [rsp+300h+cbData]
0x1800bf925  call    cs:__imp_GetProcessHeap
0x1800bf92b  mov     r8d, ebx; dwBytes
0x1800bf92e  xor     edx, edx; dwFlags
0x1800bf930  mov     rcx, rax; hHeap
0x1800bf933  call    cs:__imp_HeapAlloc
0x1800bf939  xor     ecx, ecx
0x1800bf93b  mov     r14, rax
0x1800bf93e  test    rax, rax
0x1800bf941  jz      loc_1800BFBBA
0x1800bf947  lea     rax, [rsp+300h+cbData]
0x1800bf94c  xor     edx, edx; lpSubKey
0x1800bf94e  mov     [rsp+300h+lpSecurityAttributes], rax; pcbData
0x1800bf953  lea     r9d, [rcx+6]; dwFlags
0x1800bf957  mov     qword ptr [rsp+300h+samDesired], r14; pvData
0x1800bf95c  lea     r8, [rbp+200h+ValueName]; lpValue
0x1800bf960  mov     [rsp+300h+phkResult], rcx; pdwType
0x1800bf965  mov     rcx, [r12]; hkey
0x1800bf969  call    cs:__imp_RegGetValueW
0x1800bf96f  mov     ebx, eax
0x1800bf971  cmp     eax, 0EAh
0x1800bf976  jnz     short loc_1800BF9C9
0x1800bf978  mov     ebx, [rsp+300h+cbData]
0x1800bf97c  call    cs:__imp_GetProcessHeap
0x1800bf982  mov     r9d, ebx; dwBytes
0x1800bf985  mov     r8, r14; lpMem
0x1800bf988  mov     rcx, rax; hHeap
0x1800bf98b  xor     edx, edx; dwFlags
0x1800bf98d  call    cs:__imp_HeapReAlloc
0x1800bf993  xor     edx, edx; lpSubKey
0x1800bf995  test    rax, rax
0x1800bf998  jz      loc_1800BFB87
0x1800bf99e  lea     rcx, [rsp+300h+cbData]
0x1800bf9a3  mov     r14, rax
0x1800bf9a6  mov     [rsp+300h+lpSecurityAttributes], rcx; pcbData
0x1800bf9ab  lea     r9d, [rdx+6]; dwFlags
0x1800bf9af  mov     rcx, [r12]; hkey
0x1800bf9b3  lea     r8, [rbp+200h+ValueName]; lpValue
0x1800bf9b7  mov     qword ptr [rsp+300h+samDesired], rax; pvData
0x1800bf9bc  mov     [rsp+300h+phkResult], rdx; pdwType
0x1800bf9c1  call    cs:__imp_RegGetValueW
0x1800bf9c7  mov     ebx, eax
0x1800bf9c9  test    ebx, ebx
0x1800bf9cb  jnz     loc_1800BFBB2
0x1800bf9d1  lea     rdx, aCommand; "Command"
0x1800bf9d8  lea     rcx, [rbp+200h+ValueName]
0x1800bf9dc  call    cs:__imp__o__wcsicmp
0x1800bf9e2  xor     ebx, ebx
0x1800bf9e4  test    eax, eax
0x1800bf9e6  jnz     short loc_1800BF9ED
0x1800bf9e8  mov     [rsi], r14
0x1800bf9eb  jmp     short loc_1800BFA21
0x1800bf9ed  lea     rdx, aBinary_0; "Binary"
0x1800bf9f4  lea     rcx, [rbp+200h+ValueName]
0x1800bf9f8  call    cs:__imp__o__wcsicmp
0x1800bf9fe  test    eax, eax
0x1800bfa00  jnz     short loc_1800BFA08
0x1800bfa02  mov     [rsi+8], r14
0x1800bfa06  jmp     short loc_1800BFA21
0x1800bfa08  test    r14, r14
0x1800bfa0b  jz      short loc_1800BFA21
0x1800bfa0d  call    cs:__imp_GetProcessHeap
0x1800bfa13  mov     r8, r14; lpMem
0x1800bfa16  xor     edx, edx; dwFlags
0x1800bfa18  mov     rcx, rax; hHeap
0x1800bfa1b  call    cs:__imp_HeapFree
0x1800bfa21  mov     eax, [rsp+300h+dwIndex]
0x1800bfa25  lea     rcx, [rsp+300h+cbData]
0x1800bfa2a  mov     [rsp+300h+var_2C8], rcx; lpcbData
0x1800bfa2f  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x1800bfa34  mov     rcx, [r12]; hKey
0x1800bfa38  lea     r8, [rbp+200h+ValueName]; lpValueName
0x1800bfa3c  mov     edx, eax; dwIndex
0x1800bfa3e  mov     [rsp+300h+lpSecurityAttributes], rbx; lpData
0x1800bfa43  add     eax, edi
0x1800bfa45  mov     [rsp+300h+cchValueName], 104h
0x1800bfa4d  mov     [rsp+300h+dwIndex], eax
0x1800bfa51  lea     rax, [rsp+300h+Type]
0x1800bfa56  mov     qword ptr [rsp+300h+samDesired], rax; lpType
0x1800bfa5b  mov     [rsp+300h+phkResult], rbx; lpReserved
0x1800bfa60  call    cs:__imp_RegEnumValueW
0x1800bfa66  test    eax, eax
0x1800bfa68  jz      loc_1800BF7E2
0x1800bfa6e  lea     r14, [rsi+28h]
0x1800bfa72  mov     rcx, [r14]; hkey
0x1800bfa75  lea     rax, [rsp+300h+cbData]
0x1800bfa7a  mov     [rsp+300h+lpSecurityAttributes], rax; pcbData
0x1800bfa7f  lea     r8, ValueName; "Pending"
0x1800bfa86  lea     rax, [rsp+300h+pvData]
0x1800bfa8b  mov     [rsp+300h+cbData], 4
0x1800bfa93  mov     qword ptr [rsp+300h+samDesired], rax; pvData
0x1800bfa98  mov     r9d, 20000010h; dwFlags
  ... truncated ...
```
