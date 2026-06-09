# Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18000b7b0`
- end: `0x18000bd99`
- name: `?OnAfterEvents@CBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1513`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001870`
- `0x180002420`
- `0x180002680`
- `0x18000b398`
- `0x18000b534`
- `0x18000b7b0`
- `0x18000bdb8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18000b8d0`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18000b8d0`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000bacb`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000bacb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000bb20`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000bb4f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000bb20`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000bb4f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b8c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b8e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b8c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b8e2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000bada`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000bada`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bc27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bc27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bc3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bc3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b8a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b9c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b8a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b9c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bcda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bcda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b850`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b850`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b946`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b946`

## string_xrefs

- `0x18000b88a`: `InstallDate`
- `0x18000bc1a`: `ntdll.dll`

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
0x18000b7b0  push    rbp
0x18000b7b2  push    rbx
0x18000b7b3  push    rsi
0x18000b7b4  push    rdi
0x18000b7b5  push    r12
0x18000b7b7  push    r13
0x18000b7b9  push    r14
0x18000b7bb  push    r15
0x18000b7bd  lea     rbp, [rsp-8C8h]
0x18000b7c5  sub     rsp, 9C8h
0x18000b7cc  mov     rax, cs:__security_cookie
0x18000b7d3  xor     rax, rsp
0x18000b7d6  mov     [rbp+900h+var_50], rax
0x18000b7dd  mov     r12d, r8d
0x18000b7e0  mov     [rsp+0A00h+var_9B0], r8d
0x18000b7e5  mov     rbx, rdx
0x18000b7e8  mov     [rsp+0A00h+var_9A8], rcx
0x18000b7ed  mov     r15, rcx
0x18000b7f0  mov     [rsp+0A00h+var_9B4], r9d
0x18000b7f5  xor     edx, edx; Val
0x18000b7f7  lea     rcx, [rbp+900h+var_880]; void *
0x18000b7fe  mov     r8d, 80Ch; Size
0x18000b804  mov     esi, r9d
0x18000b807  call    memset_0
0x18000b80c  xor     eax, eax
0x18000b80e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000b815  mov     r14d, eax
0x18000b818  mov     [rsp+0A00h+var_998], rax
0x18000b81d  mov     [rsp+0A00h+var_990], rax
0x18000b822  lea     rdi, [rbp+900h+var_878]
0x18000b829  mov     [rsp+0A00h+hKey], rax
0x18000b82e  xorps   xmm0, xmm0
0x18000b831  lea     rax, [rsp+0A00h+hKey]
0x18000b836  xor     r8d, r8d; ulOptions
0x18000b839  lea     r13d, [r14+1]
0x18000b83d  mov     [rsp+0A00h+phkResult], rax; phkResult
0x18000b842  mov     r9d, r13d; samDesired
0x18000b845  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b84c  movups  [rbp+900h+var_890], xmm0
0x18000b850  call    cs:__imp_RegOpenKeyExW
0x18000b856  test    eax, eax
0x18000b858  jnz     loc_18000BC6D
0x18000b85e  mov     r14, [rsp+0A00h+hKey]
0x18000b863  lea     rax, [rsp+0A00h+cbData]
0x18000b868  mov     [rsp+0A00h+lpcbData], rax; lpcbData
0x18000b86d  lea     r9, [rsp+0A00h+Type]; lpType
0x18000b872  lea     rax, [rsp+0A00h+Data]
0x18000b877  mov     [rsp+0A00h+var_9A0], r14
0x18000b87c  xor     esi, esi
0x18000b87e  mov     [rsp+0A00h+phkResult], rax; lpData
0x18000b883  xor     r8d, r8d; lpReserved
0x18000b886  mov     dword ptr [rsp+0A00h+Data], esi
0x18000b88a  lea     rdx, ValueName; "InstallDate"
0x18000b891  mov     [rsp+0A00h+Type], esi
0x18000b895  mov     rcx, r14; hKey
0x18000b898  mov     [rsp+0A00h+cbData], 4
0x18000b8a0  call    cs:__imp_RegQueryValueExW
0x18000b8a6  test    eax, eax
0x18000b8a8  jnz     loc_18000B962
0x18000b8ae  cmp     [rsp+0A00h+Type], 4
0x18000b8b3  jnz     loc_18000B962
0x18000b8b9  movsxd  rax, dword ptr [rsp+0A00h+Data]
0x18000b8be  mov     qword ptr [rsp+0A00h+cbData], rax
0x18000b8c3  call    cs:__imp__o__errno
0x18000b8c9  lea     rcx, [rsp+0A00h+cbData]
0x18000b8ce  mov     [rax], esi
0x18000b8d0  call    cs:__imp__o__gmtime64
0x18000b8d6  mov     rdi, rax
0x18000b8d9  test    rax, rax
0x18000b8dc  jz      loc_18000B962
0x18000b8e2  call    cs:__imp__o__errno
0x18000b8e8  cmp     [rax], esi
0x18000b8ea  jnz     short loc_18000B962
0x18000b8ec  movzx   edx, word ptr [rdi+18h]
0x18000b8f0  mov     ecx, 76Ch
0x18000b8f5  add     cx, [rdi+14h]
0x18000b8f9  movzx   eax, word ptr [rdi+10h]
0x18000b8fd  movzx   r11d, word ptr [rdi]
0x18000b901  add     ax, r13w
0x18000b905  movzx   r10d, word ptr [rdi+4]
0x18000b90a  movzx   r9d, word ptr [rdi+8]
0x18000b90f  movzx   r8d, word ptr [rdi+0Ch]
0x18000b914  mov     [rbp+900h+SystemTime.wYear], cx
0x18000b918  lea     rcx, [rbp+900h+SystemTime]; lpSystemTime
0x18000b91c  mov     [rbp+900h+SystemTime.wDayOfWeek], dx
0x18000b920  lea     rdx, [rsp+0A00h+hKey]; lpFileTime
0x18000b925  mov     [rbp+900h+SystemTime.wMonth], ax
0x18000b929  mov     [rbp+900h+SystemTime.wDay], r8w
0x18000b92e  mov     [rbp+900h+SystemTime.wHour], r9w
0x18000b933  mov     [rbp+900h+SystemTime.wMinute], r10w
0x18000b938  mov     [rbp+900h+SystemTime.wSecond], r11w
0x18000b93d  mov     [rbp+900h+SystemTime.wMilliseconds], si
0x18000b941  mov     [rsp+0A00h+hKey], rsi
0x18000b946  call    cs:__imp_SystemTimeToFileTime
0x18000b94c  mov     rcx, [rbp+900h+var_880]
0x18000b953  test    eax, eax
0x18000b955  cmovnz  rcx, [rsp+0A00h+hKey]
0x18000b95b  mov     [rbp+900h+var_880], rcx
0x18000b962  mov     edi, 401h
0x18000b967  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18000b96c  lea     r8, [rbp+900h+var_878]; unsigned __int16 *
0x18000b973  mov     [rsp+0A00h+Type], edi
0x18000b977  lea     rdx, aBuildlabex; "BuildLabEx"
0x18000b97e  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18000b983  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000b988  test    eax, eax
0x18000b98a  jnz     loc_18000BB92
0x18000b990  lea     rax, [rsp+0A00h+hKey]
0x18000b995  mov     [rsp+0A00h+cbData], esi
0x18000b999  mov     [rsp+0A00h+lpcbData], rax; lpcbData
0x18000b99e  lea     r9, [rbp+900h+SystemTime]; lpType
0x18000b9a2  lea     rax, [rsp+0A00h+cbData]
0x18000b9a7  mov     dword ptr [rbp+900h+SystemTime.wYear], esi
0x18000b9aa  xor     r8d, r8d; lpReserved
0x18000b9ad  mov     [rsp+0A00h+phkResult], rax; lpData
0x18000b9b2  lea     rdx, aUbr; "UBR"
0x18000b9b9  mov     dword ptr [rsp+0A00h+hKey], 4
0x18000b9c1  mov     rcx, r14; hKey
0x18000b9c4  call    cs:__imp_RegQueryValueExW
0x18000b9ca  test    eax, eax
0x18000b9cc  jnz     loc_18000BBB7
0x18000b9d2  cmp     dword ptr [rbp+900h+SystemTime.wYear], 4
0x18000b9d6  jnz     loc_18000BBB7
0x18000b9dc  mov     eax, esi
0x18000b9de  test    eax, eax
0x18000b9e0  jnz     loc_18000BBB7
0x18000b9e6  xorps   xmm0, xmm0
0x18000b9e9  mov     [rbp+900h+var_8A0], rsi
0x18000b9ed  movups  [rbp+900h+var_8B0], xmm0
0x18000b9f1  mov     [rbp+900h+var_898], rsi
0x18000b9f5  lea     rax, [rbp+900h+var_878]
0x18000b9fc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ba00  inc     r8
0x18000ba03  cmp     [rax+r8*2], si
0x18000ba08  jnz     short loc_18000BA00
0x18000ba0a  lea     rdx, [rbp+900h+var_878]
0x18000ba11  lea     rcx, [rbp+900h+var_8B0]
0x18000ba15  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ba1a  cmp     [rbp+900h+var_898], 7
0x18000ba1f  lea     rsi, [rbp+900h+var_8B0]
0x18000ba23  mov     rax, [rbp+900h+var_8A0]
0x18000ba27  cmova   rsi, qword ptr [rbp+900h+var_8B0]
0x18000ba2c  test    rax, rax
0x18000ba2f  jz      loc_18000BB71
0x18000ba35  lea     rdi, [rsi+rax*2]
0x18000ba39  mov     r15d, 2Eh ; '.'
0x18000ba3f  mov     r8d, r15d
0x18000ba42  mov     rdx, rdi
0x18000ba45  mov     rcx, rsi
0x18000ba48  call    __std_find_trivial_2
0x18000ba4d  cmp     rax, rdi
0x18000ba50  jz      loc_18000BB71
0x18000ba56  sub     rax, rsi
0x18000ba59  sar     rax, 1
0x18000ba5c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ba60  jz      loc_18000BB71
0x18000ba66  cmp     [rbp+900h+var_898], 7
0x18000ba6b  lea     r12, [rax+1]
0x18000ba6f  mov     rax, [rbp+900h+var_8A0]
0x18000ba73  lea     rsi, [rbp+900h+var_8B0]
0x18000ba77  cmova   rsi, qword ptr [rbp+900h+var_8B0]
0x18000ba7c  cmp     r12, rax
0x18000ba7f  jnb     loc_18000BB71
0x18000ba85  lea     rdi, [rsi+rax*2]
0x18000ba89  mov     r8d, r15d
0x18000ba8c  mov     rdx, rdi
0x18000ba8f  lea     rcx, [rsi+r12*2]
0x18000ba93  call    __std_find_trivial_2
0x18000ba98  mov     r15, rax
0x18000ba9b  cmp     rax, rdi
0x18000ba9e  jz      loc_18000BB71
0x18000baa4  sub     r15, rsi
0x18000baa7  sar     r15, 1
0x18000baaa  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000baae  jz      loc_18000BB71
0x18000bab4  mov     ecx, [rsp+0A00h+cbData]
0x18000bab8  lea     rdx, [rbp+900h+Source]
0x18000babf  mov     edi, 10h
0x18000bac4  mov     r8d, edi
0x18000bac7  lea     r9d, [rdi-6]
0x18000bacb  call    cs:__imp__o__ultow_s
0x18000bad1  mov     edx, edi; MaxCount
0x18000bad3  lea     rcx, [rbp+900h+Source]; Source
0x18000bada  call    cs:__imp_wcsnlen
0x18000bae0  mov     rcx, [rbp+900h+var_8A0]
0x18000bae4  mov     edx, 402h
0x18000bae9  sub     rcx, r15
0x18000baec  mov     [rsp+0A00h+hKey], rax
0x18000baf1  inc     rcx
0x18000baf4  mov     qword ptr [rbp+900h+SystemTime.wYear], rcx
0x18000baf8  add     rcx, r12
0x18000bafb  add     rcx, rax
0x18000bafe  cmp     rcx, rdx
0x18000bb01  ja      short loc_18000BB71
0x18000bb03  sub     edx, r12d
0x18000bb06  lea     rdi, [rbp+900h+var_878]
0x18000bb0d  lea     rdi, [rdi+r12*2]
0x18000bb11  mov     esi, edx
0x18000bb13  mov     rcx, rdi
0x18000bb16  lea     r8, [rbp+900h+Source]
0x18000bb1d  mov     r9, rax
0x18000bb20  call    cs:__imp__o_wcsncpy_s
0x18000bb26  mov     rax, [rsp+0A00h+hKey]
0x18000bb2b  sub     esi, eax
0x18000bb2d  cmp     [rbp+900h+var_898], 7
0x18000bb32  mov     edx, esi
0x18000bb34  lea     rdi, [rdi+rax*2]
0x18000bb38  lea     rax, [rbp+900h+var_8B0]
0x18000bb3c  mov     rcx, rdi
0x18000bb3f  cmova   rax, qword ptr [rbp+900h+var_8B0]
0x18000bb44  lea     r8, [rax+r15*2]
0x18000bb48  mov     r15, qword ptr [rbp+900h+SystemTime.wYear]
0x18000bb4c  mov     r9, r15
0x18000bb4f  call    cs:__imp__o_wcsncpy_s
0x18000bb55  lea     rcx, [rbp+900h+var_8B0]
0x18000bb59  sub     esi, r15d
0x18000bb5c  lea     rdi, [rdi+r15*2]
0x18000bb60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bb65  mov     r15, [rsp+0A00h+var_9A8]
0x18000bb6a  mov     r12d, [rsp+0A00h+var_9B0]
0x18000bb6f  jmp     short loc_18000BBE4
0x18000bb71  lea     rcx, [rbp+900h+var_8B0]
0x18000bb75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bb7a  test    r14, r14
0x18000bb7d  jz      short loc_18000BB88
0x18000bb7f  mov     rcx, r14; hKey
0x18000bb82  call    cs:__imp_RegCloseKey
0x18000bb88  mov     eax, 80004005h
0x18000bb8d  jmp     loc_18000BD76
0x18000bb92  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18000bb97  mov     [rsp+0A00h+Type], edi
0x18000bb9b  lea     r8, [rbp+900h+var_878]; unsigned __int16 *
0x18000bba2  lea     rdx, aBuildlab; "BuildLab"
0x18000bba9  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18000bbae  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000bbb3  test    eax, eax
0x18000bbb5  jnz     short loc_18000BBD1
0x18000bbb7  mov     eax, [rsp+0A00h+Type]
0x18000bbbb  lea     rdi, [rbp+900h+var_878]
0x18000bbc2  mov     esi, 402h
0x18000bbc7  sub     esi, [rsp+0A00h+Type]
0x18000bbcb  lea     rdi, [rdi+rax*2]
0x18000bbcf  jmp     short loc_18000BBE4
0x18000bbd1  mov     [rbp+900h+var_878], si
0x18000bbd8  lea     rdi, [rbp+900h+var_876]
0x18000bbdf  mov     esi, 401h
0x18000bbe4  lea     r9, [rsp+0A00h+Type]; unsigned int *
0x18000bbe9  mov     [rsp+0A00h+Type], esi
0x18000bbed  mov     r8, rdi; unsigned __int16 *
0x18000bbf0  lea     rdx, aProductname; "ProductName"
0x18000bbf7  lea     rcx, [rsp+0A00h+var_9A0]; this
0x18000bbfc  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000bc01  xor     esi, esi
0x18000bc03  test    eax, eax
0x18000bc05  jnz     short loc_18000BC11
0x18000bc07  mov     eax, [rsp+0A00h+Type]
0x18000bc0b  lea     rdi, [rdi+rax*2]
0x18000bc0f  jmp     short loc_18000BC18
0x18000bc11  mov     [rdi], si
0x18000bc14  add     rdi, 2
0x18000bc18  xor     edx, edx; hFile
0x18000bc1a  lea     rcx, LibFileName; "ntdll.dll"
0x18000bc21  mov     r8d, 800h; dwFlags
0x18000bc27  call    cs:__imp_LoadLibraryExW
0x18000bc2d  test    rax, rax
0x18000bc30  jz      short loc_18000BC58
0x18000bc32  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18000bc39  mov     rcx, rax; hModule
0x18000bc3c  call    cs:__imp_GetProcAddress
0x18000bc42  test    rax, rax
0x18000bc45  jz      short loc_18000BC58
0x18000bc47  lea     r8, [rbp+900h+var_890+0Ch]
0x18000bc4b  lea     rdx, [rbp+900h+var_890+8]
0x18000bc4f  lea     rcx, [rbp+900h+var_890]
0x18000bc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc58  test    r14, r14
0x18000bc5b  jz      short loc_18000BC69
0x18000bc5d  mov     rcx, r14; hKey
0x18000bc60  call    cs:__imp_RegCloseKey
0x18000bc66  mov     r14, rsi
0x18000bc69  mov     esi, [rsp+0A00h+var_9B4]
0x18000bc6d  xor     edx, edx; Val
0x18000bc6f  lea     rcx, [rbp+900h+var_980]; void *
0x18000bc73  lea     r8d, [rdx+58h]; Size
0x18000bc77  call    memset_0
0x18000bc7c  movups  xmm0, cs:SystemConfigExGuid
0x18000bc83  mov     rcx, [r15+10h]
0x18000bc87  lea     rax, [rbp+900h+var_880]
0x18000bc8e  mov     [rbp+900h+var_938], rax
0x18000bc92  lea     rdx, [rbp+900h+var_980]
0x18000bc96  lea     rax, [rbp+900h+var_880]
0x18000bc9d  mov     [rbp+900h+var_980], si
0x18000bca1  sub     edi, eax
0x18000bca3  mov     [rbp+900h+var_970], rbx
0x18000bca7  mov     [rbp+900h+var_930], edi
0x18000bcaa  xor     r9d, r9d
0x18000bcad  movdqu  [rbp+900h+var_968], xmm0
0x18000bcb2  mov     [rbp+900h+var_97C], 20h ; ' '
0x18000bcb6  xor     r8d, r8d
0x18000bcb9  mov     [rbp+900h+var_92C], r12d
  ... truncated ...
```
