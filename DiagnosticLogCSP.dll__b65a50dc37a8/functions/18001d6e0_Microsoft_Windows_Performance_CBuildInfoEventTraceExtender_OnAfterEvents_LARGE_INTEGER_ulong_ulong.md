# Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001d6e0`
- end: `0x18001dd30`
- name: `?OnAfterEvents@CBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1616`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x180002ad0`
- `0x18000a924`
- `0x1800103a8`
- `0x180011a38`
- `0x18001d6e0`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18001d812`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18001d812`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18001da25`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18001da25`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001da86`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001dabb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001da86`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001dabb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d7ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d82a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d7ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d82a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001da3a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001da3a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001db9f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001db9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dbba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dbba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d7d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d918`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d7d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d918`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001daf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dbe4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dc64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dcdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001daf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dbe4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dc64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dcdc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d780`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d780`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001d894`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001d894`

## string_xrefs

- `0x18001db92`: `ntdll.dll`
- `0x18001d7c0`: `InstallDate`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r12d
  Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *v6; // r15
  unsigned int v7; // esi
  unsigned __int16 *v8; // rdi
  unsigned int v9; // r13d
  HKEY v10; // r14
  WORD *v11; // rdi
  WORD v12; // dx
  WORD v13; // r11
  WORD v14; // ax
  WORD v15; // r10
  WORD v16; // r9
  WORD v17; // r8
  BOOL v18; // eax
  HKEY v19; // rcx
  __int64 v20; // r8
  __int128 *v21; // rsi
  char *v22; // rdi
  __int64 trivial_2; // rax
  __int64 v24; // rax
  unsigned __int64 v25; // r12
  __int128 *v26; // rsi
  char *v27; // rdi
  __int64 v28; // rax
  __int64 v29; // r15
  HKEY v30; // rax
  unsigned int v31; // esi
  unsigned __int16 *v32; // rdi
  __int128 *v33; // rax
  char *v34; // r8
  __int64 v35; // r15
  DWORD v36; // esi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v40; // rcx
  int v41; // edi
  __int64 v42; // rcx
  __int64 v43; // rcx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v48; // [rsp+4Ch] [rbp-B4h]
  unsigned int v49; // [rsp+50h] [rbp-B0h]
  Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *v50; // [rsp+58h] [rbp-A8h]
  _QWORD v51[4]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v52[2]; // [rsp+80h] [rbp-80h] BYREF
  char v53; // [rsp+84h] [rbp-7Ch]
  union _LARGE_INTEGER v54; // [rsp+90h] [rbp-70h]
  __int128 v55; // [rsp+98h] [rbp-68h]
  HKEY *v56; // [rsp+C8h] [rbp-38h]
  unsigned int v57; // [rsp+D0h] [rbp-30h]
  unsigned int v58; // [rsp+D4h] [rbp-2Ch]
  _WORD v59[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v60; // [rsp+E4h] [rbp-1Ch]
  union _LARGE_INTEGER v61; // [rsp+F0h] [rbp-10h]
  __int128 v62; // [rsp+F8h] [rbp-8h] BYREF
  __int128 *v63; // [rsp+128h] [rbp+28h]
  int v64; // [rsp+130h] [rbp+30h]
  unsigned int v65; // [rsp+134h] [rbp+34h]
  SYSTEMTIME SystemTime; // [rsp+140h] [rbp+40h] BYREF
  __int128 v67; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v68; // [rsp+160h] [rbp+60h]
  unsigned __int64 v69; // [rsp+168h] [rbp+68h]
  __int128 v70; // [rsp+170h] [rbp+70h] BYREF
  HKEY v71; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v72; // [rsp+188h] [rbp+88h] BYREF
  char v73; // [rsp+18Ah] [rbp+8Ah] BYREF
  wchar_t Source[16]; // [rsp+990h] [rbp+890h] BYREF

  v4 = a3;
  v49 = a3;
  v50 = this;
  v6 = this;
  v48 = a4;
  v7 = a4;
  memset_0(&v71, 0, 0x80Cu);
  v51[1] = 0;
  v51[2] = 0;
  v8 = &v72;
  hKey = 0;
  v9 = 1;
  v70 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 1u, &hKey) )
  {
LABEL_43:
    memset_0(v52, 0, 0x58u);
    v40 = *((_QWORD *)v6 + 2);
    v56 = &v71;
    v52[0] = v7;
    v54 = a2;
    v57 = (_DWORD)v8 - ((unsigned int)&v62 + 8 + 128);
    v55 = SystemConfigExGuid;
    v53 = 32;
    v58 = v4;
    v41 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v40 + 192LL))(v40, v52, 0, 0);
    if ( v41 < 0 )
      return (unsigned int)v41;
    memset_0(v59, 0, 0x58u);
    v42 = *((_QWORD *)v6 + 2);
    v63 = &v70;
    v62 = SystemConfigExGuid;
    v59[0] = v7;
    v61 = a2;
    v60 = 37;
    v64 = 16;
    v65 = v4;
    v41 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v42 + 192LL))(v42, v59, 0, 0);
    if ( v41 < 0 )
      return (unsigned int)v41;
    v43 = *((_QWORD *)v6 + 1);
    if ( v43 )
      return (*(unsigned int (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v43 + 96LL))(
               v43,
               a2,
               v4,
               v7);
    return v9;
  }
  v10 = hKey;
  v51[0] = hKey;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(hKey, L"InstallDate", 0, &Type, Data, cbData) && Type == 4 )
  {
    *(_QWORD *)cbData = *(int *)Data;
    *(_DWORD *)_o__errno() = 0;
    v11 = (WORD *)_o__gmtime64(cbData);
    if ( v11 )
    {
      if ( !*(_DWORD *)_o__errno() )
      {
        v12 = v11[12];
        v13 = *v11;
        v14 = v11[8] + 1;
        v15 = v11[2];
        v16 = v11[4];
        v17 = v11[6];
        SystemTime.wYear = v11[10] + 1900;
        SystemTime.wDayOfWeek = v12;
        SystemTime.wMonth = v14;
        SystemTime.wDay = v17;
        SystemTime.wHour = v16;
        SystemTime.wMinute = v15;
        SystemTime.wSecond = v13;
        SystemTime.wMilliseconds = 0;
        hKey = 0;
        v18 = SystemTimeToFileTime(&SystemTime, (LPFILETIME)&hKey);
        v19 = v71;
        if ( v18 )
          v19 = hKey;
        v71 = v19;
      }
    }
  }
  Type = 1025;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v51, L"BuildLabEx", &v72, &Type) )
  {
    Type = 1025;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v51, L"BuildLab", &v72, &Type) )
    {
      v72 = 0;
      v8 = (unsigned __int16 *)&v73;
      v36 = 1025;
      goto LABEL_34;
    }
LABEL_32:
    v36 = 1026 - Type;
    v8 = &v72 + Type;
LABEL_34:
    Type = v36;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v51, L"ProductName", v8, &Type) )
    {
      *v8 = 0;
      LODWORD(v8) = (_DWORD)v8 + 2;
    }
    else
    {
      LODWORD(v8) = (_DWORD)v8 + 2 * Type;
    }
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetDeviceFamilyInfoEnum");
      if ( ProcAddress )
        ((void (__fastcall *)(__int128 *, char *, char *))ProcAddress)(&v70, (char *)&v70 + 8, (char *)&v70 + 12);
    }
    if ( v10 )
      RegCloseKey(v10);
    v7 = v48;
    goto LABEL_43;
  }
  cbData[0] = 0;
  *(_DWORD *)&SystemTime.wYear = 0;
  LODWORD(hKey) = 4;
  if ( RegQueryValueExW(v10, L"UBR", 0, (LPDWORD)&SystemTime.wYear, (LPBYTE)cbData, (LPDWORD)&hKey)
    || *(_DWORD *)&SystemTime.wYear != 4 )
  {
    goto LABEL_32;
  }
  v68 = 0;
  v67 = 0;
  v69 = 0;
  v20 = -1;
  do
    ++v20;
  while ( *(&v72 + v20) );
  std::wstring::_Construct<1,unsigned short const *>(&v67, &v72, v20);
  v21 = &v67;
  if ( v69 > 7 )
    v21 = (__int128 *)v67;
  if ( v68 )
  {
    v22 = (char *)v21 + 2 * v68;
    trivial_2 = _std_find_trivial_2(v21, v22, 46);
    if ( (char *)trivial_2 != v22 )
    {
      v24 = (trivial_2 - (__int64)v21) >> 1;
      if ( v24 != -1 )
      {
        v25 = v24 + 1;
        v26 = &v67;
        if ( v69 > 7 )
          v26 = (__int128 *)v67;
        if ( v25 < v68 )
        {
          v27 = (char *)v26 + 2 * v68;
          v28 = _std_find_trivial_2((char *)v26 + 2 * v25, v27, 46);
          if ( (char *)v28 != v27 )
          {
            v29 = (v28 - (__int64)v26) >> 1;
            if ( v29 != -1 )
            {
              _o__ultow_s(cbData[0], Source, 16, 10);
              v30 = (HKEY)wcsnlen(Source, 0x10u);
              hKey = v30;
              *(_QWORD *)&SystemTime.wYear = v68 - v29 + 1;
              if ( (unsigned __int64)v30 + v25 + *(_QWORD *)&SystemTime.wYear <= 0x402 )
              {
                _o_wcsncpy_s(&v72 + v25, (unsigned int)(1026 - v25), Source, v30);
                v31 = 1026 - v25 - (_DWORD)hKey;
                v32 = &v72 + v25 + (_QWORD)hKey;
                v33 = &v67;
                if ( v69 > 7 )
                  v33 = (__int128 *)v67;
                v34 = (char *)v33 + 2 * v29;
                v35 = *(_QWORD *)&SystemTime.wYear;
                _o_wcsncpy_s(&v72 + v25 + (_QWORD)hKey, v31, v34, *(_QWORD *)&SystemTime.wYear);
                v36 = v31 - v35;
                v8 = &v32[v35];
                std::wstring::~wstring(&v67);
                v6 = v50;
                v4 = v49;
                goto LABEL_34;
              }
            }
          }
        }
      }
    }
  }
  std::wstring::~wstring(&v67);
  if ( v10 )
    RegCloseKey(v10);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001d6e0  push    rbp
0x18001d6e2  push    rbx
0x18001d6e3  push    rsi
0x18001d6e4  push    rdi
0x18001d6e5  push    r12
0x18001d6e7  push    r13
0x18001d6e9  push    r14
0x18001d6eb  push    r15
0x18001d6ed  lea     rbp, [rsp-8C8h]
0x18001d6f5  sub     rsp, 9C8h
0x18001d6fc  mov     rax, cs:__security_cookie
0x18001d703  xor     rax, rsp
0x18001d706  mov     [rbp+900h+var_50], rax
0x18001d70d  mov     r12d, r8d
0x18001d710  mov     [rsp+0A00h+var_9B0], r8d
0x18001d715  mov     rbx, rdx
0x18001d718  mov     [rsp+0A00h+var_9A8], rcx
0x18001d71d  mov     r15, rcx
0x18001d720  mov     [rsp+0A00h+var_9B4], r9d
0x18001d725  xor     edx, edx; Val
0x18001d727  lea     rcx, [rbp+900h+var_880]; void *
0x18001d72e  mov     r8d, 80Ch; Size
0x18001d734  mov     esi, r9d
0x18001d737  call    memset_0
0x18001d73c  xor     eax, eax
0x18001d73e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001d745  mov     r14d, eax
0x18001d748  mov     [rsp+0A00h+var_998], rax
0x18001d74d  mov     [rsp+0A00h+var_990], rax
0x18001d752  lea     rdi, [rbp+900h+var_878]
0x18001d759  mov     [rsp+0A00h+hKey], rax
0x18001d75e  xorps   xmm0, xmm0
0x18001d761  lea     rax, [rsp+0A00h+hKey]
0x18001d766  xor     r8d, r8d; ulOptions
0x18001d769  lea     r13d, [r14+1]
0x18001d76d  mov     [rsp+0A00h+phkResult], rax; phkResult
0x18001d772  mov     r9d, r13d; samDesired
0x18001d775  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d77c  movups  [rbp+900h+var_890], xmm0
0x18001d780  call    cs:__imp_RegOpenKeyExW
0x18001d787  nop     dword ptr [rax+rax+00h]
0x18001d78c  test    eax, eax
0x18001d78e  jnz     loc_18001DBF7
0x18001d794  mov     r14, [rsp+0A00h+hKey]
0x18001d799  lea     rax, [rsp+0A00h+cbData]
0x18001d79e  mov     [rsp+0A00h+lpcbData], rax; lpcbData
0x18001d7a3  lea     r9, [rsp+0A00h+Type]; lpType
0x18001d7a8  lea     rax, [rsp+0A00h+Data]
0x18001d7ad  mov     [rsp+0A00h+var_9A0], r14
0x18001d7b2  xor     esi, esi
0x18001d7b4  mov     [rsp+0A00h+phkResult], rax; lpData
0x18001d7b9  xor     r8d, r8d; lpReserved
0x18001d7bc  mov     dword ptr [rsp+0A00h+Data], esi
0x18001d7c0  lea     rdx, aInstalldate; "InstallDate"
0x18001d7c7  mov     [rsp+0A00h+Type], esi
0x18001d7cb  mov     rcx, r14; hKey
0x18001d7ce  mov     [rsp+0A00h+cbData], 4
0x18001d7d6  call    cs:__imp_RegQueryValueExW
0x18001d7dd  nop     dword ptr [rax+rax+00h]
0x18001d7e2  test    eax, eax
0x18001d7e4  jnz     loc_18001D8B6
0x18001d7ea  cmp     [rsp+0A00h+Type], 4
0x18001d7ef  jnz     loc_18001D8B6
0x18001d7f5  movsxd  rax, dword ptr [rsp+0A00h+Data]
0x18001d7fa  mov     qword ptr [rsp+0A00h+cbData], rax
0x18001d7ff  call    cs:__imp__o__errno
0x18001d806  nop     dword ptr [rax+rax+00h]
0x18001d80b  lea     rcx, [rsp+0A00h+cbData]
0x18001d810  mov     [rax], esi
0x18001d812  call    cs:__imp__o__gmtime64
0x18001d819  nop     dword ptr [rax+rax+00h]
0x18001d81e  mov     rdi, rax
0x18001d821  test    rax, rax
0x18001d824  jz      loc_18001D8B6
0x18001d82a  call    cs:__imp__o__errno
0x18001d831  nop     dword ptr [rax+rax+00h]
0x18001d836  cmp     [rax], esi
0x18001d838  jnz     short loc_18001D8B6
0x18001d83a  movzx   edx, word ptr [rdi+18h]
0x18001d83e  mov     ecx, 76Ch
0x18001d843  add     cx, [rdi+14h]
0x18001d847  movzx   eax, word ptr [rdi+10h]
0x18001d84b  movzx   r11d, word ptr [rdi]
0x18001d84f  add     ax, r13w
0x18001d853  movzx   r10d, word ptr [rdi+4]
0x18001d858  movzx   r9d, word ptr [rdi+8]
0x18001d85d  movzx   r8d, word ptr [rdi+0Ch]
0x18001d862  mov     [rbp+900h+SystemTime.wYear], cx
0x18001d866  lea     rcx, [rbp+900h+SystemTime]; lpSystemTime
0x18001d86a  mov     [rbp+900h+SystemTime.wDayOfWeek], dx
0x18001d86e  lea     rdx, [rsp+0A00h+hKey]; lpFileTime
0x18001d873  mov     [rbp+900h+SystemTime.wMonth], ax
0x18001d877  mov     [rbp+900h+SystemTime.wDay], r8w
0x18001d87c  mov     [rbp+900h+SystemTime.wHour], r9w
0x18001d881  mov     [rbp+900h+SystemTime.wMinute], r10w
0x18001d886  mov     [rbp+900h+SystemTime.wSecond], r11w
0x18001d88b  mov     [rbp+900h+SystemTime.wMilliseconds], si
0x18001d88f  mov     [rsp+0A00h+hKey], rsi
0x18001d894  call    cs:__imp_SystemTimeToFileTime
0x18001d89b  nop     dword ptr [rax+rax+00h]
0x18001d8a0  mov     rcx, [rbp+900h+var_880]
0x18001d8a7  test    eax, eax
0x18001d8a9  cmovnz  rcx, [rsp+0A00h+hKey]
0x18001d8af  mov     [rbp+900h+var_880], rcx
0x18001d8b6  mov     edi, 401h
0x18001d8bb  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18001d8c0  lea     r8, [rbp+900h+var_878]; unsigned __int16 *
0x18001d8c7  mov     [rsp+0A00h+Type], edi
0x18001d8cb  lea     rdx, aBuildlabex; "BuildLabEx"
0x18001d8d2  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18001d8d7  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001d8dc  test    eax, eax
0x18001d8de  jnz     loc_18001DB0A
0x18001d8e4  lea     rax, [rsp+0A00h+hKey]
0x18001d8e9  mov     [rsp+0A00h+cbData], esi
0x18001d8ed  mov     [rsp+0A00h+lpcbData], rax; lpcbData
0x18001d8f2  lea     r9, [rbp+900h+SystemTime]; lpType
0x18001d8f6  lea     rax, [rsp+0A00h+cbData]
0x18001d8fb  mov     dword ptr [rbp+900h+SystemTime.wYear], esi
0x18001d8fe  xor     r8d, r8d; lpReserved
0x18001d901  mov     [rsp+0A00h+phkResult], rax; lpData
0x18001d906  lea     rdx, aUbr; "UBR"
0x18001d90d  mov     dword ptr [rsp+0A00h+hKey], 4
0x18001d915  mov     rcx, r14; hKey
0x18001d918  call    cs:__imp_RegQueryValueExW
0x18001d91f  nop     dword ptr [rax+rax+00h]
0x18001d924  test    eax, eax
0x18001d926  jnz     loc_18001DB2F
0x18001d92c  cmp     dword ptr [rbp+900h+SystemTime.wYear], 4
0x18001d930  jnz     loc_18001DB2F
0x18001d936  mov     eax, esi
0x18001d938  test    eax, eax
0x18001d93a  jnz     loc_18001DB2F
0x18001d940  xorps   xmm0, xmm0
0x18001d943  mov     [rbp+900h+var_8A0], rsi
0x18001d947  movups  [rbp+900h+var_8B0], xmm0
0x18001d94b  mov     [rbp+900h+var_898], rsi
0x18001d94f  lea     rax, [rbp+900h+var_878]
0x18001d956  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d95a  inc     r8
0x18001d95d  cmp     [rax+r8*2], si
0x18001d962  jnz     short loc_18001D95A
0x18001d964  lea     rdx, [rbp+900h+var_878]
0x18001d96b  lea     rcx, [rbp+900h+var_8B0]
0x18001d96f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d974  cmp     [rbp+900h+var_898], 7
0x18001d979  lea     rsi, [rbp+900h+var_8B0]
0x18001d97d  mov     rax, [rbp+900h+var_8A0]
0x18001d981  cmova   rsi, qword ptr [rbp+900h+var_8B0]
0x18001d986  test    rax, rax
0x18001d989  jz      loc_18001DAE3
0x18001d98f  lea     rdi, [rsi+rax*2]
0x18001d993  mov     r15d, 2Eh ; '.'
0x18001d999  mov     r8d, r15d
0x18001d99c  mov     rdx, rdi
0x18001d99f  mov     rcx, rsi
0x18001d9a2  call    __std_find_trivial_2
0x18001d9a7  cmp     rax, rdi
0x18001d9aa  jz      loc_18001DAE3
0x18001d9b0  sub     rax, rsi
0x18001d9b3  sar     rax, 1
0x18001d9b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d9ba  jz      loc_18001DAE3
0x18001d9c0  cmp     [rbp+900h+var_898], 7
0x18001d9c5  lea     r12, [rax+1]
0x18001d9c9  mov     rax, [rbp+900h+var_8A0]
0x18001d9cd  lea     rsi, [rbp+900h+var_8B0]
0x18001d9d1  cmova   rsi, qword ptr [rbp+900h+var_8B0]
0x18001d9d6  cmp     r12, rax
0x18001d9d9  jnb     loc_18001DAE3
0x18001d9df  lea     rdi, [rsi+rax*2]
0x18001d9e3  mov     r8d, r15d
0x18001d9e6  mov     rdx, rdi
0x18001d9e9  lea     rcx, [rsi+r12*2]
0x18001d9ed  call    __std_find_trivial_2
0x18001d9f2  mov     r15, rax
0x18001d9f5  cmp     rax, rdi
0x18001d9f8  jz      loc_18001DAE3
0x18001d9fe  sub     r15, rsi
0x18001da01  sar     r15, 1
0x18001da04  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18001da08  jz      loc_18001DAE3
0x18001da0e  mov     ecx, [rsp+0A00h+cbData]
0x18001da12  lea     rdx, [rbp+900h+Source]
0x18001da19  mov     edi, 10h
0x18001da1e  mov     r8d, edi
0x18001da21  lea     r9d, [rdi-6]
0x18001da25  call    cs:__imp__o__ultow_s
0x18001da2c  nop     dword ptr [rax+rax+00h]
0x18001da31  mov     edx, edi; MaxCount
0x18001da33  lea     rcx, [rbp+900h+Source]; Source
0x18001da3a  call    cs:__imp_wcsnlen
0x18001da41  nop     dword ptr [rax+rax+00h]
0x18001da46  mov     rcx, [rbp+900h+var_8A0]
0x18001da4a  mov     edx, 402h
0x18001da4f  sub     rcx, r15
0x18001da52  mov     [rsp+0A00h+hKey], rax
0x18001da57  inc     rcx
0x18001da5a  mov     qword ptr [rbp+900h+SystemTime.wYear], rcx
0x18001da5e  add     rcx, r12
0x18001da61  add     rcx, rax
0x18001da64  cmp     rcx, rdx
0x18001da67  ja      short loc_18001DAE3
0x18001da69  sub     edx, r12d
0x18001da6c  lea     rdi, [rbp+900h+var_878]
0x18001da73  lea     rdi, [rdi+r12*2]
0x18001da77  mov     esi, edx
0x18001da79  mov     rcx, rdi
0x18001da7c  lea     r8, [rbp+900h+Source]
0x18001da83  mov     r9, rax
0x18001da86  call    cs:__imp__o_wcsncpy_s
0x18001da8d  nop     dword ptr [rax+rax+00h]
0x18001da92  mov     rax, [rsp+0A00h+hKey]
0x18001da97  sub     esi, eax
0x18001da99  cmp     [rbp+900h+var_898], 7
0x18001da9e  mov     edx, esi
0x18001daa0  lea     rdi, [rdi+rax*2]
0x18001daa4  lea     rax, [rbp+900h+var_8B0]
0x18001daa8  mov     rcx, rdi
0x18001daab  cmova   rax, qword ptr [rbp+900h+var_8B0]
0x18001dab0  lea     r8, [rax+r15*2]
0x18001dab4  mov     r15, qword ptr [rbp+900h+SystemTime.wYear]
0x18001dab8  mov     r9, r15
0x18001dabb  call    cs:__imp__o_wcsncpy_s
0x18001dac2  nop     dword ptr [rax+rax+00h]
0x18001dac7  lea     rcx, [rbp+900h+var_8B0]
0x18001dacb  sub     esi, r15d
0x18001dace  lea     rdi, [rdi+r15*2]
0x18001dad2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dad7  mov     r15, [rsp+0A00h+var_9A8]
0x18001dadc  mov     r12d, [rsp+0A00h+var_9B0]
0x18001dae1  jmp     short loc_18001DB5C
0x18001dae3  lea     rcx, [rbp+900h+var_8B0]
0x18001dae7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001daec  test    r14, r14
0x18001daef  jz      short loc_18001DB00
0x18001daf1  mov     rcx, r14; hKey
0x18001daf4  call    cs:__imp_RegCloseKey
0x18001dafb  nop     dword ptr [rax+rax+00h]
0x18001db00  mov     eax, 80004005h
0x18001db05  jmp     loc_18001DD0C
0x18001db0a  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18001db0f  mov     [rsp+0A00h+Type], edi
0x18001db13  lea     r8, [rbp+900h+var_878]; unsigned __int16 *
0x18001db1a  lea     rdx, aBuildlab; "BuildLab"
0x18001db21  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18001db26  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001db2b  test    eax, eax
0x18001db2d  jnz     short loc_18001DB49
0x18001db2f  mov     eax, [rsp+0A00h+Type]
0x18001db33  lea     rdi, [rbp+900h+var_878]
0x18001db3a  mov     esi, 402h
0x18001db3f  sub     esi, [rsp+0A00h+Type]
0x18001db43  lea     rdi, [rdi+rax*2]
0x18001db47  jmp     short loc_18001DB5C
0x18001db49  mov     [rbp+900h+var_878], si
0x18001db50  lea     rdi, [rbp+900h+var_876]
0x18001db57  mov     esi, 401h
0x18001db5c  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18001db61  mov     [rsp+0A00h+Type], esi
0x18001db65  mov     r8, rdi; unsigned __int16 *
0x18001db68  lea     rdx, aProductname; "ProductName"
0x18001db6f  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18001db74  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001db79  xor     esi, esi
0x18001db7b  test    eax, eax
0x18001db7d  jnz     short loc_18001DB89
0x18001db7f  mov     eax, [rsp+0A00h+Type]
0x18001db83  lea     rdi, [rdi+rax*2]
0x18001db87  jmp     short loc_18001DB90
0x18001db89  mov     [rdi], si
0x18001db8c  add     rdi, 2
0x18001db90  xor     edx, edx; hFile
0x18001db92  lea     rcx, ModuleName; "ntdll.dll"
0x18001db99  mov     r8d, 800h; dwFlags
0x18001db9f  call    cs:__imp_LoadLibraryExW
0x18001dba6  nop     dword ptr [rax+rax+00h]
0x18001dbab  test    rax, rax
0x18001dbae  jz      short loc_18001DBDC
0x18001dbb0  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18001dbb7  mov     rcx, rax; hModule
0x18001dbba  call    cs:__imp_GetProcAddress
0x18001dbc1  nop     dword ptr [rax+rax+00h]
0x18001dbc6  test    rax, rax
0x18001dbc9  jz      short loc_18001DBDC
0x18001dbcb  lea     r8, [rbp+900h+var_890+0Ch]
0x18001dbcf  lea     rdx, [rbp+900h+var_890+8]
0x18001dbd3  lea     rcx, [rbp+900h+var_890]
0x18001dbd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbdc  test    r14, r14
0x18001dbdf  jz      short loc_18001DBF3
0x18001dbe1  mov     rcx, r14; hKey
0x18001dbe4  call    cs:__imp_RegCloseKey
0x18001dbeb  nop     dword ptr [rax+rax+00h]
0x18001dbf0  mov     r14, rsi
0x18001dbf3  mov     esi, [rsp+0A00h+var_9B4]
0x18001dbf7  xor     edx, edx; Val
0x18001dbf9  lea     rcx, [rbp+900h+var_980]; void *
0x18001dbfd  lea     r8d, [rdx+58h]; Size
0x18001dc01  call    memset_0
  ... truncated ...
```
