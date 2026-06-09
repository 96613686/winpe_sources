# Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001c7c0`
- end: `0x18001cda9`
- name: `?OnAfterEvents@CBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1513`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x180002aa0`
- `0x18000a600`
- `0x18000fb98`
- `0x180011170`
- `0x18001c7c0`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18001c8e0`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18001c8e0`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18001cadb`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18001cadb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001cb30`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001cb5f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001cb30`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001cb5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c8d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c8f2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c8d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c8f2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001caea`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001caea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001cc37`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001cc37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cc4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cc4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c8b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c9d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c8b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c9d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cc70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ccea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cd5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cc70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ccea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cd5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c860`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c860`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c956`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c956`

## string_xrefs

- `0x18001cc2a`: `ntdll.dll`
- `0x18001c89a`: `InstallDate`

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
  unsigned __int64 v20; // r8
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
  std::wstring::_Construct<1,unsigned short const *>((char **)&v67, &v72, v20);
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
                std::wstring::~wstring((char **)&v67);
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
  std::wstring::~wstring((char **)&v67);
  if ( v10 )
    RegCloseKey(v10);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001c7c0  push    rbp
0x18001c7c2  push    rbx
0x18001c7c3  push    rsi
0x18001c7c4  push    rdi
0x18001c7c5  push    r12
0x18001c7c7  push    r13
0x18001c7c9  push    r14
0x18001c7cb  push    r15
0x18001c7cd  lea     rbp, [rsp-8C8h]
0x18001c7d5  sub     rsp, 9C8h
0x18001c7dc  mov     rax, cs:__security_cookie
0x18001c7e3  xor     rax, rsp
0x18001c7e6  mov     [rbp+900h+var_50], rax
0x18001c7ed  mov     r12d, r8d
0x18001c7f0  mov     [rsp+0A00h+var_9B0], r8d
0x18001c7f5  mov     rbx, rdx
0x18001c7f8  mov     [rsp+0A00h+var_9A8], rcx
0x18001c7fd  mov     r15, rcx
0x18001c800  mov     [rsp+0A00h+var_9B4], r9d
0x18001c805  xor     edx, edx; Val
0x18001c807  lea     rcx, [rbp+900h+var_880]; void *
0x18001c80e  mov     r8d, 80Ch; Size
0x18001c814  mov     esi, r9d
0x18001c817  call    memset_0
0x18001c81c  xor     eax, eax
0x18001c81e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001c825  mov     r14d, eax
0x18001c828  mov     [rsp+0A00h+var_998], rax
0x18001c82d  mov     [rsp+0A00h+var_990], rax
0x18001c832  lea     rdi, [rbp+900h+var_878]
0x18001c839  mov     [rsp+0A00h+hKey], rax
0x18001c83e  xorps   xmm0, xmm0
0x18001c841  lea     rax, [rsp+0A00h+hKey]
0x18001c846  xor     r8d, r8d; ulOptions
0x18001c849  lea     r13d, [r14+1]
0x18001c84d  mov     [rsp+0A00h+phkResult], rax; phkResult
0x18001c852  mov     r9d, r13d; samDesired
0x18001c855  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c85c  movups  [rbp+900h+var_890], xmm0
0x18001c860  call    cs:__imp_RegOpenKeyExW
0x18001c866  test    eax, eax
0x18001c868  jnz     loc_18001CC7D
0x18001c86e  mov     r14, [rsp+0A00h+hKey]
0x18001c873  lea     rax, [rsp+0A00h+cbData]
0x18001c878  mov     [rsp+0A00h+lpcbData], rax; lpcbData
0x18001c87d  lea     r9, [rsp+0A00h+Type]; lpType
0x18001c882  lea     rax, [rsp+0A00h+Data]
0x18001c887  mov     [rsp+0A00h+var_9A0], r14
0x18001c88c  xor     esi, esi
0x18001c88e  mov     [rsp+0A00h+phkResult], rax; lpData
0x18001c893  xor     r8d, r8d; lpReserved
0x18001c896  mov     dword ptr [rsp+0A00h+Data], esi
0x18001c89a  lea     rdx, aInstalldate; "InstallDate"
0x18001c8a1  mov     [rsp+0A00h+Type], esi
0x18001c8a5  mov     rcx, r14; hKey
0x18001c8a8  mov     [rsp+0A00h+cbData], 4
0x18001c8b0  call    cs:__imp_RegQueryValueExW
0x18001c8b6  test    eax, eax
0x18001c8b8  jnz     loc_18001C972
0x18001c8be  cmp     [rsp+0A00h+Type], 4
0x18001c8c3  jnz     loc_18001C972
0x18001c8c9  movsxd  rax, dword ptr [rsp+0A00h+Data]
0x18001c8ce  mov     qword ptr [rsp+0A00h+cbData], rax
0x18001c8d3  call    cs:__imp__o__errno
0x18001c8d9  lea     rcx, [rsp+0A00h+cbData]
0x18001c8de  mov     [rax], esi
0x18001c8e0  call    cs:__imp__o__gmtime64
0x18001c8e6  mov     rdi, rax
0x18001c8e9  test    rax, rax
0x18001c8ec  jz      loc_18001C972
0x18001c8f2  call    cs:__imp__o__errno
0x18001c8f8  cmp     [rax], esi
0x18001c8fa  jnz     short loc_18001C972
0x18001c8fc  movzx   edx, word ptr [rdi+18h]
0x18001c900  mov     ecx, 76Ch
0x18001c905  add     cx, [rdi+14h]
0x18001c909  movzx   eax, word ptr [rdi+10h]
0x18001c90d  movzx   r11d, word ptr [rdi]
0x18001c911  add     ax, r13w
0x18001c915  movzx   r10d, word ptr [rdi+4]
0x18001c91a  movzx   r9d, word ptr [rdi+8]
0x18001c91f  movzx   r8d, word ptr [rdi+0Ch]
0x18001c924  mov     [rbp+900h+SystemTime.wYear], cx
0x18001c928  lea     rcx, [rbp+900h+SystemTime]; lpSystemTime
0x18001c92c  mov     [rbp+900h+SystemTime.wDayOfWeek], dx
0x18001c930  lea     rdx, [rsp+0A00h+hKey]; lpFileTime
0x18001c935  mov     [rbp+900h+SystemTime.wMonth], ax
0x18001c939  mov     [rbp+900h+SystemTime.wDay], r8w
0x18001c93e  mov     [rbp+900h+SystemTime.wHour], r9w
0x18001c943  mov     [rbp+900h+SystemTime.wMinute], r10w
0x18001c948  mov     [rbp+900h+SystemTime.wSecond], r11w
0x18001c94d  mov     [rbp+900h+SystemTime.wMilliseconds], si
0x18001c951  mov     [rsp+0A00h+hKey], rsi
0x18001c956  call    cs:__imp_SystemTimeToFileTime
0x18001c95c  mov     rcx, [rbp+900h+var_880]
0x18001c963  test    eax, eax
0x18001c965  cmovnz  rcx, [rsp+0A00h+hKey]
0x18001c96b  mov     [rbp+900h+var_880], rcx
0x18001c972  mov     edi, 401h
0x18001c977  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18001c97c  lea     r8, [rbp+900h+var_878]; unsigned __int16 *
0x18001c983  mov     [rsp+0A00h+Type], edi
0x18001c987  lea     rdx, aBuildlabex; "BuildLabEx"
0x18001c98e  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18001c993  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001c998  test    eax, eax
0x18001c99a  jnz     loc_18001CBA2
0x18001c9a0  lea     rax, [rsp+0A00h+hKey]
0x18001c9a5  mov     [rsp+0A00h+cbData], esi
0x18001c9a9  mov     [rsp+0A00h+lpcbData], rax; lpcbData
0x18001c9ae  lea     r9, [rbp+900h+SystemTime]; lpType
0x18001c9b2  lea     rax, [rsp+0A00h+cbData]
0x18001c9b7  mov     dword ptr [rbp+900h+SystemTime.wYear], esi
0x18001c9ba  xor     r8d, r8d; lpReserved
0x18001c9bd  mov     [rsp+0A00h+phkResult], rax; lpData
0x18001c9c2  lea     rdx, aUbr; "UBR"
0x18001c9c9  mov     dword ptr [rsp+0A00h+hKey], 4
0x18001c9d1  mov     rcx, r14; hKey
0x18001c9d4  call    cs:__imp_RegQueryValueExW
0x18001c9da  test    eax, eax
0x18001c9dc  jnz     loc_18001CBC7
0x18001c9e2  cmp     dword ptr [rbp+900h+SystemTime.wYear], 4
0x18001c9e6  jnz     loc_18001CBC7
0x18001c9ec  mov     eax, esi
0x18001c9ee  test    eax, eax
0x18001c9f0  jnz     loc_18001CBC7
0x18001c9f6  xorps   xmm0, xmm0
0x18001c9f9  mov     [rbp+900h+var_8A0], rsi
0x18001c9fd  movups  [rbp+900h+var_8B0], xmm0
0x18001ca01  mov     [rbp+900h+var_898], rsi
0x18001ca05  lea     rax, [rbp+900h+var_878]
0x18001ca0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001ca10  inc     r8
0x18001ca13  cmp     [rax+r8*2], si
0x18001ca18  jnz     short loc_18001CA10
0x18001ca1a  lea     rdx, [rbp+900h+var_878]
0x18001ca21  lea     rcx, [rbp+900h+var_8B0]
0x18001ca25  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001ca2a  cmp     [rbp+900h+var_898], 7
0x18001ca2f  lea     rsi, [rbp+900h+var_8B0]
0x18001ca33  mov     rax, [rbp+900h+var_8A0]
0x18001ca37  cmova   rsi, qword ptr [rbp+900h+var_8B0]
0x18001ca3c  test    rax, rax
0x18001ca3f  jz      loc_18001CB81
0x18001ca45  lea     rdi, [rsi+rax*2]
0x18001ca49  mov     r15d, 2Eh ; '.'
0x18001ca4f  mov     r8d, r15d
0x18001ca52  mov     rdx, rdi
0x18001ca55  mov     rcx, rsi
0x18001ca58  call    __std_find_trivial_2
0x18001ca5d  cmp     rax, rdi
0x18001ca60  jz      loc_18001CB81
0x18001ca66  sub     rax, rsi
0x18001ca69  sar     rax, 1
0x18001ca6c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ca70  jz      loc_18001CB81
0x18001ca76  cmp     [rbp+900h+var_898], 7
0x18001ca7b  lea     r12, [rax+1]
0x18001ca7f  mov     rax, [rbp+900h+var_8A0]
0x18001ca83  lea     rsi, [rbp+900h+var_8B0]
0x18001ca87  cmova   rsi, qword ptr [rbp+900h+var_8B0]
0x18001ca8c  cmp     r12, rax
0x18001ca8f  jnb     loc_18001CB81
0x18001ca95  lea     rdi, [rsi+rax*2]
0x18001ca99  mov     r8d, r15d
0x18001ca9c  mov     rdx, rdi
0x18001ca9f  lea     rcx, [rsi+r12*2]
0x18001caa3  call    __std_find_trivial_2
0x18001caa8  mov     r15, rax
0x18001caab  cmp     rax, rdi
0x18001caae  jz      loc_18001CB81
0x18001cab4  sub     r15, rsi
0x18001cab7  sar     r15, 1
0x18001caba  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18001cabe  jz      loc_18001CB81
0x18001cac4  mov     ecx, [rsp+0A00h+cbData]
0x18001cac8  lea     rdx, [rbp+900h+Source]
0x18001cacf  mov     edi, 10h
0x18001cad4  mov     r8d, edi
0x18001cad7  lea     r9d, [rdi-6]
0x18001cadb  call    cs:__imp__o__ultow_s
0x18001cae1  mov     edx, edi; MaxCount
0x18001cae3  lea     rcx, [rbp+900h+Source]; Source
0x18001caea  call    cs:__imp_wcsnlen
0x18001caf0  mov     rcx, [rbp+900h+var_8A0]
0x18001caf4  mov     edx, 402h
0x18001caf9  sub     rcx, r15
0x18001cafc  mov     [rsp+0A00h+hKey], rax
0x18001cb01  inc     rcx
0x18001cb04  mov     qword ptr [rbp+900h+SystemTime.wYear], rcx
0x18001cb08  add     rcx, r12
0x18001cb0b  add     rcx, rax
0x18001cb0e  cmp     rcx, rdx
0x18001cb11  ja      short loc_18001CB81
0x18001cb13  sub     edx, r12d
0x18001cb16  lea     rdi, [rbp+900h+var_878]
0x18001cb1d  lea     rdi, [rdi+r12*2]
0x18001cb21  mov     esi, edx
0x18001cb23  mov     rcx, rdi
0x18001cb26  lea     r8, [rbp+900h+Source]
0x18001cb2d  mov     r9, rax
0x18001cb30  call    cs:__imp__o_wcsncpy_s
0x18001cb36  mov     rax, [rsp+0A00h+hKey]
0x18001cb3b  sub     esi, eax
0x18001cb3d  cmp     [rbp+900h+var_898], 7
0x18001cb42  mov     edx, esi
0x18001cb44  lea     rdi, [rdi+rax*2]
0x18001cb48  lea     rax, [rbp+900h+var_8B0]
0x18001cb4c  mov     rcx, rdi
0x18001cb4f  cmova   rax, qword ptr [rbp+900h+var_8B0]
0x18001cb54  lea     r8, [rax+r15*2]
0x18001cb58  mov     r15, qword ptr [rbp+900h+SystemTime.wYear]
0x18001cb5c  mov     r9, r15
0x18001cb5f  call    cs:__imp__o_wcsncpy_s
0x18001cb65  lea     rcx, [rbp+900h+var_8B0]
0x18001cb69  sub     esi, r15d
0x18001cb6c  lea     rdi, [rdi+r15*2]
0x18001cb70  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cb75  mov     r15, [rsp+0A00h+var_9A8]
0x18001cb7a  mov     r12d, [rsp+0A00h+var_9B0]
0x18001cb7f  jmp     short loc_18001CBF4
0x18001cb81  lea     rcx, [rbp+900h+var_8B0]
0x18001cb85  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cb8a  test    r14, r14
0x18001cb8d  jz      short loc_18001CB98
0x18001cb8f  mov     rcx, r14; hKey
0x18001cb92  call    cs:__imp_RegCloseKey
0x18001cb98  mov     eax, 80004005h
0x18001cb9d  jmp     loc_18001CD86
0x18001cba2  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18001cba7  mov     [rsp+0A00h+Type], edi
0x18001cbab  lea     r8, [rbp+900h+var_878]; unsigned __int16 *
0x18001cbb2  lea     rdx, aBuildlab; "BuildLab"
0x18001cbb9  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18001cbbe  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001cbc3  test    eax, eax
0x18001cbc5  jnz     short loc_18001CBE1
0x18001cbc7  mov     eax, [rsp+0A00h+Type]
0x18001cbcb  lea     rdi, [rbp+900h+var_878]
0x18001cbd2  mov     esi, 402h
0x18001cbd7  sub     esi, [rsp+0A00h+Type]
0x18001cbdb  lea     rdi, [rdi+rax*2]
0x18001cbdf  jmp     short loc_18001CBF4
0x18001cbe1  mov     [rbp+900h+var_878], si
0x18001cbe8  lea     rdi, [rbp+900h+var_876]
0x18001cbef  mov     esi, 401h
0x18001cbf4  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18001cbf9  mov     [rsp+0A00h+Type], esi
0x18001cbfd  mov     r8, rdi; unsigned __int16 *
0x18001cc00  lea     rdx, aProductname; "ProductName"
0x18001cc07  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18001cc0c  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001cc11  xor     esi, esi
0x18001cc13  test    eax, eax
0x18001cc15  jnz     short loc_18001CC21
0x18001cc17  mov     eax, [rsp+0A00h+Type]
0x18001cc1b  lea     rdi, [rdi+rax*2]
0x18001cc1f  jmp     short loc_18001CC28
0x18001cc21  mov     [rdi], si
0x18001cc24  add     rdi, 2
0x18001cc28  xor     edx, edx; hFile
0x18001cc2a  lea     rcx, ModuleName; "ntdll.dll"
0x18001cc31  mov     r8d, 800h; dwFlags
0x18001cc37  call    cs:__imp_LoadLibraryExW
0x18001cc3d  test    rax, rax
0x18001cc40  jz      short loc_18001CC68
0x18001cc42  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18001cc49  mov     rcx, rax; hModule
0x18001cc4c  call    cs:__imp_GetProcAddress
0x18001cc52  test    rax, rax
0x18001cc55  jz      short loc_18001CC68
0x18001cc57  lea     r8, [rbp+900h+var_890+0Ch]
0x18001cc5b  lea     rdx, [rbp+900h+var_890+8]
0x18001cc5f  lea     rcx, [rbp+900h+var_890]
0x18001cc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc68  test    r14, r14
0x18001cc6b  jz      short loc_18001CC79
0x18001cc6d  mov     rcx, r14; hKey
0x18001cc70  call    cs:__imp_RegCloseKey
0x18001cc76  mov     r14, rsi
0x18001cc79  mov     esi, [rsp+0A00h+var_9B4]
0x18001cc7d  xor     edx, edx; Val
0x18001cc7f  lea     rcx, [rbp+900h+var_980]; void *
0x18001cc83  lea     r8d, [rdx+58h]; Size
0x18001cc87  call    memset_0
0x18001cc8c  movups  xmm0, cs:SystemConfigExGuid
0x18001cc93  mov     rcx, [r15+10h]
0x18001cc97  lea     rax, [rbp+900h+var_880]
0x18001cc9e  mov     [rbp+900h+var_938], rax
0x18001cca2  lea     rdx, [rbp+900h+var_980]
0x18001cca6  lea     rax, [rbp+900h+var_880]
0x18001ccad  mov     [rbp+900h+var_980], si
0x18001ccb1  sub     edi, eax
0x18001ccb3  mov     [rbp+900h+var_970], rbx
0x18001ccb7  mov     [rbp+900h+var_930], edi
0x18001ccba  xor     r9d, r9d
0x18001ccbd  movdqu  [rbp+900h+var_968], xmm0
0x18001ccc2  mov     [rbp+900h+var_97C], 20h ; ' '
0x18001ccc6  xor     r8d, r8d
0x18001ccc9  mov     [rbp+900h+var_92C], r12d
  ... truncated ...
```
