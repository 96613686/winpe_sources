# Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x1800083a0`
- end: `0x180008a15`
- name: `?OnAfterEvents@CBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1653`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000829c`
- `0x1800083a0`
- `0x180008bd4`
- `0x180026e30`
- `0x180026f6c`
- `0x180027910`
- `0x1800279e0`

## import_xrefs

- `msvcrt!_errno` at `0x1800084c0`
- `msvcrt!_errno` at `0x1800084e0`
- `msvcrt!_errno` at `0x1800084c0`
- `msvcrt!_errno` at `0x1800084e0`
- `msvcrt!_gmtime64` at `0x1800084ce`
- `msvcrt!_gmtime64` at `0x1800084ce`
- `KERNEL32!GetProcAddress` at `0x18000864d`
- `KERNEL32!GetProcAddress` at `0x18000864d`
- `KERNEL32!SystemTimeToFileTime` at `0x18000857e`
- `KERNEL32!SystemTimeToFileTime` at `0x18000857e`
- `KERNEL32!LoadLibraryW` at `0x180008638`
- `KERNEL32!LoadLibraryW` at `0x180008638`
- `ADVAPI32!RegOpenKeyExW` at `0x180008442`
- `ADVAPI32!RegOpenKeyExW` at `0x1800086b6`
- `ADVAPI32!RegOpenKeyExW` at `0x180008442`
- `ADVAPI32!RegOpenKeyExW` at `0x1800086b6`
- `ADVAPI32!RegCloseKey` at `0x1800086d0`
- `ADVAPI32!RegCloseKey` at `0x18000885d`
- `ADVAPI32!RegCloseKey` at `0x1800089b5`
- `ADVAPI32!RegCloseKey` at `0x1800089c7`
- `ADVAPI32!RegCloseKey` at `0x1800086d0`
- `ADVAPI32!RegCloseKey` at `0x18000885d`
- `ADVAPI32!RegCloseKey` at `0x1800089b5`
- `ADVAPI32!RegCloseKey` at `0x1800089c7`
- `ADVAPI32!RegQueryValueExW` at `0x180008492`
- `ADVAPI32!RegQueryValueExW` at `0x180008492`

## string_xrefs

- `0x180008480`: `InstallDate`
- `0x180008631`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  __int16 v7; // si
  HKEY v8; // rdi
  unsigned __int16 *v9; // r14
  unsigned int v10; // r15d
  struct tm *v11; // rsi
  __m128i v12; // xmm2
  __m128i v13; // xmm0
  DWORD v14; // esi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v17; // r9d
  LSTATUS v18; // eax
  unsigned int v19; // r9d
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  unsigned int v22; // r9d
  unsigned int v23; // r9d
  unsigned int v24; // r9d
  unsigned int v25; // r9d
  unsigned int v26; // r9d
  unsigned int v27; // r9d
  unsigned int v28; // r9d
  unsigned int v29; // r9d
  unsigned int v30; // r9d
  unsigned int v31; // r9d
  unsigned int v32; // r9d
  __int64 v33; // rcx
  int v34; // esi
  __int64 v35; // rcx
  unsigned int v36; // r14d
  __int64 v37; // rcx
  __int64 v39; // rcx
  unsigned __int16 *phkResult; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultd; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResulte; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultf; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultg; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResulth; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResulti; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultj; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultk; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultl; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultm; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *phkResultn; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v57; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v59[9]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v60[2]; // [rsp+90h] [rbp-70h] BYREF
  char v61; // [rsp+94h] [rbp-6Ch]
  union _LARGE_INTEGER v62; // [rsp+A0h] [rbp-60h]
  __int128 v63; // [rsp+A8h] [rbp-58h]
  _FILETIME *p_FileTime; // [rsp+D8h] [rbp-28h]
  unsigned int v65; // [rsp+E0h] [rbp-20h]
  unsigned int v66; // [rsp+E4h] [rbp-1Ch]
  _WORD v67[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v68; // [rsp+F4h] [rbp-Ch]
  union _LARGE_INTEGER v69; // [rsp+100h] [rbp+0h] BYREF
  __int128 v70; // [rsp+108h] [rbp+8h]
  __int64 *v71; // [rsp+138h] [rbp+38h]
  int v72; // [rsp+140h] [rbp+40h]
  unsigned int v73; // [rsp+144h] [rbp+44h]
  _WORD v74[2]; // [rsp+150h] [rbp+50h] BYREF
  char v75; // [rsp+154h] [rbp+54h]
  union _LARGE_INTEGER v76; // [rsp+160h] [rbp+60h]
  __int128 v77; // [rsp+168h] [rbp+68h]
  unsigned __int16 *v78; // [rsp+198h] [rbp+98h]
  int v79; // [rsp+1A0h] [rbp+A0h]
  unsigned int v80; // [rsp+1A4h] [rbp+A4h]
  SYSTEMTIME SystemTime; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v82; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v83; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int16 v84[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v85[64]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v86[64]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v87[64]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v88[64]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v89[64]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v90[64]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v91[64]; // [rsp+550h] [rbp+450h] BYREF
  unsigned __int16 v92[64]; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int16 v93[64]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v94[64]; // [rsp+6D0h] [rbp+5D0h] BYREF
  unsigned __int16 v95[64]; // [rsp+750h] [rbp+650h] BYREF
  unsigned __int16 v96[64]; // [rsp+7D0h] [rbp+6D0h] BYREF
  unsigned __int16 v97[64]; // [rsp+850h] [rbp+750h] BYREF
  unsigned __int16 v98[64]; // [rsp+8D0h] [rbp+7D0h] BYREF
  _FILETIME FileTime; // [rsp+950h] [rbp+850h] BYREF
  unsigned __int16 v100; // [rsp+958h] [rbp+858h] BYREF
  char v101; // [rsp+95Ah] [rbp+85Ah] BYREF

  v57 = a4;
  v7 = a4;
  memset_0(&FileTime, 0, 0x80Cu);
  v8 = 0;
  v82 = 0;
  v83 = 0;
  v9 = &v100;
  v59[1] = 0;
  v59[2] = 0;
  hKey = 0;
  v10 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 1u, &hKey) )
  {
    v8 = hKey;
    v59[0] = hKey;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"InstallDate", 0, (LPDWORD)&hKey, Data, &cbData) && (_DWORD)hKey == 4 )
    {
      hKey = (HKEY)*(int *)Data;
      *_errno() = 0;
      v11 = _gmtime64((const __time64_t *)&hKey);
      if ( v11 )
      {
        if ( !*_errno() )
        {
          v12 = *(__m128i *)&v11->tm_mon;
          v13 = *(__m128i *)&v11->tm_sec;
          SystemTime.wMilliseconds = 0;
          SystemTime.wYear = v12.m128i_i16[2] + 1900;
          SystemTime.wMonth = _mm_cvtsi128_si32(v12) + 1;
          SystemTime.wDayOfWeek = _mm_extract_epi16(v12, 4);
          SystemTime.wDay = _mm_srli_si128(v13, 8).m128i_u16[2];
          SystemTime.wHour = _mm_extract_epi16(v13, 4);
          SystemTime.wMinute = v13.m128i_u16[2];
          SystemTime.wSecond = _mm_cvtsi128_si32(v13);
          SystemTimeToFileTime(&SystemTime, &FileTime);
        }
      }
    }
    v14 = 1025;
    cbData = 1025;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v59, L"BuildLabEx", &v100, &cbData)
      && (cbData = 1025, (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v59, L"BuildLab", &v100, &cbData)) )
    {
      v100 = 0;
      v9 = (unsigned __int16 *)&v101;
    }
    else
    {
      v14 = 1026 - cbData;
      v9 = &v100 + cbData;
    }
    cbData = v14;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v59, L"ProductName", v9, &cbData) )
    {
      *v9 = 0;
      LODWORD(v9) = (_DWORD)v9 + 2;
    }
    else
    {
      LODWORD(v9) = (_DWORD)v9 + 2 * cbData;
    }
    LibraryW = LoadLibraryW(L"ntdll.dll");
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "RtlGetDeviceFamilyInfoEnum");
      if ( ProcAddress )
        ((void (__fastcall *)(__int64 *, __int64 *, char *))ProcAddress)(&v82, &v83, (char *)&v83 + 4);
    }
    v7 = v57;
  }
  *(_DWORD *)Data = 0;
  memset_0(v84, 0, 0x780u);
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\PLATFORM\\DeviceTargetingInfo", 0, 1u, &hKey) )
  {
    v18 = 0;
    if ( v8 )
      v18 = RegCloseKey(v8);
    v8 = hKey;
    v59[0] = hKey;
    if ( !v18 )
    {
      *(_DWORD *)Data = 1;
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneBootLoaderVersion",
        v84,
        v17,
        phkResult);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneFirmwareRevision",
        v85,
        v19,
        phkResulta);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneFriendlyName",
        v86,
        v20,
        phkResultb);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneHardwareRevision",
        v87,
        v21,
        phkResultc);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneManufacturer",
        v88,
        v22,
        phkResultd);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneManufacturerDisplayName",
        v89,
        v23,
        phkResulte);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneManufacturerModelName",
        v90,
        v24,
        phkResultf);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneMobileOperatorDisplayName",
        v91,
        v25,
        phkResultg);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneMobileOperatorName",
        v92,
        v26,
        phkResulth);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneModelName",
        v93,
        v27,
        phkResulti);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneRadioHardwareRevision",
        v94,
        v28,
        phkResultj);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneRadioHardwareRevision",
        v95,
        v29,
        phkResultk);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneROMVersion",
        v96,
        v30,
        phkResultl);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneSOCVersion",
        v97,
        v31,
        phkResultm);
      Microsoft::Windows::Performance::ReadRegkey(
        (Microsoft::Windows::Performance *)v59,
        (struct ATL::CRegKey *)L"PhoneHardwareVariant",
        v98,
        v32,
        phkResultn);
    }
  }
  if ( v8 )
    RegCloseKey(v8);
  memset_0(v60, 0, 0x58u);
  v33 = *((_QWORD *)this + 2);
  p_FileTime = &FileTime;
  v60[0] = v7;
  v62 = a2;
  v65 = (_DWORD)v9 - ((unsigned int)&v69 + 2128);
  v63 = SystemConfigExGuid;
  v61 = 32;
  v66 = a3;
  v34 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v33 + 192LL))(v33, v60, 0, 0);
  if ( v34 < 0 )
    return (unsigned int)v34;
  memset_0(v67, 0, 0x58u);
  v35 = *((_QWORD *)this + 2);
  v36 = v57;
  v71 = &v82;
  v70 = SystemConfigExGuid;
  v67[0] = v57;
  v69 = a2;
  v68 = 37;
  v72 = 16;
  v73 = a3;
  v34 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v35 + 192LL))(v35, v67, 0, 0);
  if ( v34 < 0 )
    return (unsigned int)v34;
  if ( *(_DWORD *)Data )
  {
    memset_0(v74, 0, 0x58u);
    v37 = *((_QWORD *)this + 2);
    v78 = v84;
    v77 = SystemConfigExGuid;
    v74[0] = v36;
    v76 = a2;
    v75 = 38;
    v79 = 1920;
    v80 = a3;
    v34 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v37 + 192LL))(v37, v74, 0, 0);
    if ( v34 < 0 )
      return (unsigned int)v34;
  }
  v39 = *((_QWORD *)this + 1);
  if ( v39 )
    return (*(unsigned int (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v39 + 96LL))(
             v39,
             a2,
             a3,
             v36);
  return v10;
}

```

## disassembly

```asm
0x1800083a0  push    rbp
0x1800083a2  push    rbx
0x1800083a3  push    rsi
0x1800083a4  push    rdi
0x1800083a5  push    r12
0x1800083a7  push    r13
0x1800083a9  push    r14
0x1800083ab  push    r15
0x1800083ad  lea     rbp, [rsp-1078h]
0x1800083b5  mov     eax, 1178h
0x1800083ba  call    _alloca_probe
0x1800083bf  sub     rsp, rax
0x1800083c2  mov     rax, cs:__security_cookie
0x1800083c9  xor     rax, rsp
0x1800083cc  mov     [rbp+10B0h+var_50], rax
0x1800083d3  mov     r12d, r8d
0x1800083d6  mov     [rsp+11B0h+var_1178], r9d
0x1800083db  mov     rbx, rdx
0x1800083de  mov     r13, rcx
0x1800083e1  xor     edx, edx; Val
0x1800083e3  lea     rcx, [rbp+10B0h+FileTime]; void *
0x1800083ea  mov     r8d, 80Ch; Size
0x1800083f0  mov     esi, r9d
0x1800083f3  call    memset_0
0x1800083f8  xor     eax, eax
0x1800083fa  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180008401  mov     edi, eax
0x180008403  mov     [rbp+10B0h+var_FF0], rax
0x18000840a  mov     [rbp+10B0h+var_FE8], rax
0x180008411  lea     r14, [rbp+10B0h+var_858]
0x180008418  mov     [rsp+11B0h+var_1160], rax
0x18000841d  xor     r8d, r8d; ulOptions
0x180008420  mov     [rsp+11B0h+var_1158], rax
0x180008425  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000842c  mov     [rsp+11B0h+hKey], rax
0x180008431  lea     r15d, [rdi+1]
0x180008435  lea     rax, [rsp+11B0h+hKey]
0x18000843a  mov     r9d, r15d; samDesired
0x18000843d  mov     [rsp+11B0h+phkResult], rax; phkResult
0x180008442  call    cs:__imp_RegOpenKeyExW
0x180008448  xor     ecx, ecx
0x18000844a  test    eax, eax
0x18000844c  jnz     loc_180008679
0x180008452  mov     rdi, [rsp+11B0h+hKey]
0x180008457  lea     rax, [rsp+11B0h+cbData]
0x18000845c  mov     [rsp+11B0h+lpcbData], rax; lpcbData
0x180008461  lea     r9, [rsp+11B0h+hKey]; lpType
0x180008466  lea     rax, [rsp+11B0h+Data]
0x18000846b  mov     [rsp+11B0h+var_1168], rdi
0x180008470  xor     r14d, r14d
0x180008473  mov     [rsp+11B0h+phkResult], rax; lpData
0x180008478  xor     r8d, r8d; lpReserved
0x18000847b  mov     dword ptr [rsp+11B0h+Data], r14d
0x180008480  lea     rdx, ValueName; "InstallDate"
0x180008487  mov     [rsp+11B0h+cbData], 4
0x18000848f  mov     rcx, rdi; hKey
0x180008492  call    cs:__imp_RegQueryValueExW
0x180008498  test    eax, eax
0x18000849a  jnz     loc_180008584
0x1800084a0  cmp     dword ptr [rsp+11B0h+hKey], 4
0x1800084a5  jnz     loc_180008584
0x1800084ab  mov     eax, r14d
0x1800084ae  test    eax, eax
0x1800084b0  jnz     loc_180008584
0x1800084b6  movsxd  rax, dword ptr [rsp+11B0h+Data]
0x1800084bb  mov     [rsp+11B0h+hKey], rax
0x1800084c0  call    cs:__imp__errno
0x1800084c6  lea     rcx, [rsp+11B0h+hKey]; Time
0x1800084cb  mov     [rax], r14d
0x1800084ce  call    cs:__imp__gmtime64
0x1800084d4  mov     rsi, rax
0x1800084d7  test    rax, rax
0x1800084da  jz      loc_180008584
0x1800084e0  call    cs:__imp__errno
0x1800084e6  cmp     [rax], r14d
0x1800084e9  jnz     loc_180008584
0x1800084ef  movups  xmm2, xmmword ptr [rsi+10h]
0x1800084f3  mov     ecx, 76Ch
0x1800084f8  lea     rdx, [rbp+10B0h+FileTime]; lpFileTime
0x1800084ff  movups  xmm0, xmmword ptr [rsi]
0x180008502  mov     [rbp+10B0h+SystemTime.wMilliseconds], r14w
0x18000850a  movq    rax, xmm2
0x18000850f  shr     rax, 20h
0x180008513  movups  xmm3, xmm0
0x180008516  add     ax, cx
0x180008519  psrldq  xmm0, 8
0x18000851e  mov     [rbp+10B0h+SystemTime.wYear], ax
0x180008525  lea     rcx, [rbp+10B0h+SystemTime]; lpSystemTime
0x18000852c  movd    eax, xmm2
0x180008530  add     ax, r15w
0x180008534  mov     [rbp+10B0h+SystemTime.wMonth], ax
0x18000853b  pextrw  eax, xmm2, 4
0x180008540  mov     [rbp+10B0h+SystemTime.wDayOfWeek], ax
0x180008547  movq    rax, xmm0
0x18000854c  shr     rax, 20h
0x180008550  mov     [rbp+10B0h+SystemTime.wDay], ax
0x180008557  pextrw  eax, xmm3, 4
0x18000855c  mov     [rbp+10B0h+SystemTime.wHour], ax
0x180008563  movq    rax, xmm3
0x180008568  shr     rax, 20h
0x18000856c  mov     [rbp+10B0h+SystemTime.wMinute], ax
0x180008573  movd    eax, xmm3
0x180008577  mov     [rbp+10B0h+SystemTime.wSecond], ax
0x18000857e  call    cs:__imp_SystemTimeToFileTime
0x180008584  mov     esi, 401h
0x180008589  lea     r9, [rsp+11B0h+cbData]; unsigned int *
0x18000858e  lea     r8, [rbp+10B0h+var_858]; unsigned __int16 *
0x180008595  mov     [rsp+11B0h+cbData], esi
0x180008599  lea     rdx, aBuildlabex; "BuildLabEx"
0x1800085a0  lea     rcx, [rsp+11B0h+var_1168]; this
0x1800085a5  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800085aa  test    eax, eax
0x1800085ac  jz      short loc_1800085D3
0x1800085ae  lea     r9, [rsp+11B0h+cbData]; unsigned int *
0x1800085b3  mov     [rsp+11B0h+cbData], esi
0x1800085b7  lea     r8, [rbp+10B0h+var_858]; unsigned __int16 *
0x1800085be  lea     rdx, aBuildlab; "BuildLab"
0x1800085c5  lea     rcx, [rsp+11B0h+var_1168]; this
0x1800085ca  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800085cf  test    eax, eax
0x1800085d1  jnz     short loc_1800085ED
0x1800085d3  mov     eax, [rsp+11B0h+cbData]
0x1800085d7  lea     r14, [rbp+10B0h+var_858]
0x1800085de  mov     esi, 402h
0x1800085e3  sub     esi, [rsp+11B0h+cbData]
0x1800085e7  lea     r14, [r14+rax*2]
0x1800085eb  jmp     short loc_1800085FC
0x1800085ed  mov     [rbp+10B0h+var_858], r14w
0x1800085f5  lea     r14, [rbp+10B0h+var_856]
0x1800085fc  lea     r9, [rsp+11B0h+cbData]; unsigned int *
0x180008601  mov     [rsp+11B0h+cbData], esi
0x180008605  mov     r8, r14; unsigned __int16 *
0x180008608  lea     rdx, aProductname; "ProductName"
0x18000860f  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008614  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180008619  xor     esi, esi
0x18000861b  test    eax, eax
0x18000861d  jnz     short loc_180008629
0x18000861f  mov     eax, [rsp+11B0h+cbData]
0x180008623  lea     r14, [r14+rax*2]
0x180008627  jmp     short loc_180008631
0x180008629  mov     [r14], si
0x18000862d  add     r14, 2
0x180008631  lea     rcx, LibFileName; "ntdll.dll"
0x180008638  call    cs:__imp_LoadLibraryW
0x18000863e  test    rax, rax
0x180008641  jz      short loc_180008673
0x180008643  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18000864a  mov     rcx, rax; hModule
0x18000864d  call    cs:__imp_GetProcAddress
0x180008653  test    rax, rax
0x180008656  jz      short loc_180008673
0x180008658  lea     r8, [rbp+10B0h+var_FE8+4]
0x18000865f  lea     rdx, [rbp+10B0h+var_FE8]
0x180008666  lea     rcx, [rbp+10B0h+var_FF0]
0x18000866d  call    cs:__guard_dispatch_icall_fptr
0x180008673  mov     esi, [rsp+11B0h+var_1178]
0x180008677  xor     ecx, ecx
0x180008679  mov     dword ptr [rsp+11B0h+Data], ecx
0x18000867d  xor     edx, edx; Val
0x18000867f  lea     rcx, [rbp+10B0h+var_FE0]; void *
0x180008686  mov     r8d, 780h; Size
0x18000868c  call    memset_0
0x180008691  xor     eax, eax
0x180008693  lea     rdx, aSystemPlatform; "SYSTEM\\PLATFORM\\DeviceTargetingInfo"
0x18000869a  mov     [rsp+11B0h+hKey], rax
0x18000869f  mov     r9d, r15d; samDesired
0x1800086a2  lea     rax, [rsp+11B0h+hKey]
0x1800086a7  xor     r8d, r8d; ulOptions
0x1800086aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800086b1  mov     [rsp+11B0h+phkResult], rax; unsigned __int16 *
0x1800086b6  call    cs:__imp_RegOpenKeyExW
0x1800086bc  xor     ecx, ecx
0x1800086be  test    eax, eax
0x1800086c0  jnz     loc_180008855
0x1800086c6  mov     eax, ecx
0x1800086c8  test    rdi, rdi
0x1800086cb  jz      short loc_1800086D6
0x1800086cd  mov     rcx, rdi; hKey
0x1800086d0  call    cs:__imp_RegCloseKey
0x1800086d6  mov     rdi, [rsp+11B0h+hKey]
0x1800086db  mov     [rsp+11B0h+var_1168], rdi
0x1800086e0  test    eax, eax
0x1800086e2  jnz     loc_180008855
0x1800086e8  lea     r8, [rbp+10B0h+var_FE0]; unsigned __int16 *
0x1800086ef  mov     dword ptr [rsp+11B0h+Data], r15d
0x1800086f4  lea     rdx, aPhonebootloade; "PhoneBootLoaderVersion"
0x1800086fb  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008700  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x180008705  lea     r8, [rbp+10B0h+var_F60]; unsigned __int16 *
0x18000870c  lea     rdx, aPhonefirmwarer; "PhoneFirmwareRevision"
0x180008713  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008718  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x18000871d  lea     r8, [rbp+10B0h+var_EE0]; unsigned __int16 *
0x180008724  lea     rdx, aPhonefriendlyn; "PhoneFriendlyName"
0x18000872b  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008730  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x180008735  lea     r8, [rbp+10B0h+var_E60]; unsigned __int16 *
0x18000873c  lea     rdx, aPhonehardwarer; "PhoneHardwareRevision"
0x180008743  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008748  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x18000874d  lea     r8, [rbp+10B0h+var_DE0]; unsigned __int16 *
0x180008754  lea     rdx, aPhonemanufactu_0; "PhoneManufacturer"
0x18000875b  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008760  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x180008765  lea     r8, [rbp+10B0h+var_D60]; unsigned __int16 *
0x18000876c  lea     rdx, aPhonemanufactu_1; "PhoneManufacturerDisplayName"
0x180008773  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008778  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x18000877d  lea     r8, [rbp+10B0h+var_CE0]; unsigned __int16 *
0x180008784  lea     rdx, aPhonemanufactu; "PhoneManufacturerModelName"
0x18000878b  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008790  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x180008795  lea     r8, [rbp+10B0h+var_C60]; unsigned __int16 *
0x18000879c  lea     rdx, aPhonemobileope_0; "PhoneMobileOperatorDisplayName"
0x1800087a3  lea     rcx, [rsp+11B0h+var_1168]; this
0x1800087a8  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x1800087ad  lea     r8, [rbp+10B0h+var_BE0]; unsigned __int16 *
0x1800087b4  lea     rdx, aPhonemobileope; "PhoneMobileOperatorName"
0x1800087bb  lea     rcx, [rsp+11B0h+var_1168]; this
0x1800087c0  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x1800087c5  lea     r8, [rbp+10B0h+var_B60]; unsigned __int16 *
0x1800087cc  lea     rdx, aPhonemodelname; "PhoneModelName"
0x1800087d3  lea     rcx, [rsp+11B0h+var_1168]; this
0x1800087d8  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x1800087dd  lea     r8, [rbp+10B0h+var_AE0]; unsigned __int16 *
0x1800087e4  lea     rdx, aPhoneradiohard; "PhoneRadioHardwareRevision"
0x1800087eb  lea     rcx, [rsp+11B0h+var_1168]; this
0x1800087f0  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x1800087f5  lea     r8, [rbp+10B0h+var_A60]; unsigned __int16 *
0x1800087fc  lea     rdx, aPhoneradiohard; "PhoneRadioHardwareRevision"
0x180008803  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008808  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x18000880d  lea     r8, [rbp+10B0h+var_9E0]; unsigned __int16 *
0x180008814  lea     rdx, aPhoneromversio; "PhoneROMVersion"
0x18000881b  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008820  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x180008825  lea     r8, [rbp+10B0h+var_960]; unsigned __int16 *
0x18000882c  lea     rdx, aPhonesocversio; "PhoneSOCVersion"
0x180008833  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008838  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x18000883d  lea     r8, [rbp+10B0h+var_8E0]; unsigned __int16 *
0x180008844  lea     rdx, aPhonehardwarev; "PhoneHardwareVariant"
0x18000884b  lea     rcx, [rsp+11B0h+var_1168]; this
0x180008850  call    ?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z; Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)
0x180008855  test    rdi, rdi
0x180008858  jz      short loc_180008867
0x18000885a  mov     rcx, rdi; hKey
0x18000885d  call    cs:__imp_RegCloseKey
0x180008863  xor     eax, eax
0x180008865  mov     edi, eax
0x180008867  xor     edx, edx; Val
0x180008869  lea     rcx, [rbp+10B0h+var_1120]; void *
0x18000886d  lea     r8d, [rdx+58h]; Size
0x180008871  call    memset_0
0x180008876  movups  xmm0, cs:SystemConfigExGuid
0x18000887d  mov     rcx, [r13+10h]
0x180008881  lea     rax, [rbp+10B0h+FileTime]
0x180008888  mov     [rbp+10B0h+var_10D8], rax
0x18000888c  lea     rdx, [rbp+10B0h+var_1120]
0x180008890  lea     rax, [rbp+10B0h+FileTime]
0x180008897  mov     [rbp+10B0h+var_1120], si
0x18000889b  sub     r14d, eax
0x18000889e  mov     [rbp+10B0h+var_1110], rbx
0x1800088a2  mov     [rbp+10B0h+var_10D0], r14d
0x1800088a6  xor     r9d, r9d
0x1800088a9  movdqu  [rbp+10B0h+var_1108], xmm0
0x1800088ae  mov     [rbp+10B0h+var_111C], 20h ; ' '
0x1800088b2  xor     r8d, r8d
0x1800088b5  mov     [rbp+10B0h+var_10CC], r12d
0x1800088b9  mov     rax, [rcx]
0x1800088bc  mov     rax, [rax+0C0h]
0x1800088c3  call    cs:__guard_dispatch_icall_fptr
0x1800088c9  mov     esi, eax
0x1800088cb  test    eax, eax
0x1800088cd  js      loc_1800089AD
0x1800088d3  xor     edx, edx; Val
0x1800088d5  lea     rcx, [rbp+10B0h+var_10C0]; void *
0x1800088d9  lea     r8d, [rdx+58h]; Size
0x1800088dd  call    memset_0
0x1800088e2  movups  xmm0, cs:SystemConfigExGuid
0x1800088e9  mov     rcx, [r13+10h]
0x1800088ed  lea     rax, [rbp+10B0h+var_FF0]
0x1800088f4  mov     r14d, [rsp+11B0h+var_1178]
0x1800088f9  lea     rdx, [rbp+10B0h+var_10C0]
0x1800088fd  mov     [rbp+10B0h+var_1078], rax
0x180008901  xor     r9d, r9d
0x180008904  movdqu  [rbp+10B0h+var_10A8], xmm0
0x180008909  mov     [rbp+10B0h+var_10C0], r14w
0x18000890e  xor     r8d, r8d
0x180008911  mov     [rbp+10B0h+var_10B0], rbx
0x180008915  mov     [rbp+10B0h+var_10BC], 25h ; '%'
0x180008919  mov     [rbp+10B0h+var_1070], 10h
0x180008920  mov     [rbp+10B0h+var_106C], r12d
0x180008924  mov     rax, [rcx]
0x180008927  mov     rax, [rax+0C0h]
0x18000892e  call    cs:__guard_dispatch_icall_fptr
0x180008934  mov     esi, eax
0x180008936  xor     eax, eax
0x180008938  test    esi, esi
  ... truncated ...
```
