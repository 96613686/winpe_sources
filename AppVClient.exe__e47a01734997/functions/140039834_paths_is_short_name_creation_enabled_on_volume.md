# paths::is_short_name_creation_enabled_on_volume

- ea: `0x140039834`
- end: `0x140039df5`
- name: `paths::is_short_name_creation_enabled_on_volume`
- size: `1473`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140039668`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140018bec`
- `0x14003949c`
- `0x1400395a8`
- `0x140039834`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1400398b1`
- `ADVAPI32!RegGetValueW` at `0x1400398b1`
- `KERNEL32!DeviceIoControl` at `0x140039d09`
- `KERNEL32!DeviceIoControl` at `0x140039d09`
- `KERNEL32!CreateFileW` at `0x140039c57`
- `KERNEL32!CreateFileW` at `0x140039c57`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140039b55`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140039b55`
- `KERNEL32!CloseHandle` at `0x140039d69`
- `KERNEL32!CloseHandle` at `0x140039d9a`
- `KERNEL32!CloseHandle` at `0x140039d69`
- `KERNEL32!CloseHandle` at `0x140039d9a`
- `KERNEL32!GetLastError` at `0x1400399c9`
- `KERNEL32!GetLastError` at `0x140039a40`
- `KERNEL32!GetLastError` at `0x140039ac4`
- `KERNEL32!GetLastError` at `0x140039b92`
- `KERNEL32!GetLastError` at `0x140039c98`
- `KERNEL32!GetLastError` at `0x140039d45`
- `KERNEL32!GetLastError` at `0x1400399c9`
- `KERNEL32!GetLastError` at `0x140039a40`
- `KERNEL32!GetLastError` at `0x140039ac4`
- `KERNEL32!GetLastError` at `0x140039b92`
- `KERNEL32!GetLastError` at `0x140039c98`
- `KERNEL32!GetLastError` at `0x140039d45`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140039b0c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140039b0c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400398c8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039932`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400399a0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039a17`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039a9b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039b69`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039c6f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039d1c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400398c8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039932`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400399a0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039a17`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039a9b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039b69`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039c6f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039d1c`

## string_xrefs

- `0x1400398c1`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x1400398d8`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x14003992b`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039942`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039999`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x1400399b0`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039a10`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039a27`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039a94`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039aab`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039b62`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039b79`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039c68`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039c7f`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039d15`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`
- `0x140039d2c`: `admin\AppMan\AppV\shared\include\paths\short_paths.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall paths::is_short_name_creation_enabled_on_volume(LPCWSTR lpszFileName, bool *a2)
{
  unsigned int ValueW; // eax
  __int64 v5; // rsi
  char *v6; // rax
  const char *v7; // rax
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  char *v11; // rax
  const char *v12; // rax
  __m128i si128; // xmm6
  char *v14; // rax
  const char *v15; // rax
  unsigned __int64 FileId; // rbx
  __int64 LastError; // rdi
  __int64 v18; // rax
  char *v19; // rax
  const char *v20; // rax
  unsigned __int64 v21; // rbx
  __int64 v22; // rdi
  char **v23; // rcx
  char *v24; // rax
  const char *v25; // rax
  unsigned __int64 v26; // rbx
  __int128 *v27; // rdx
  _QWORD *v28; // rcx
  const WCHAR *v29; // rcx
  char *v30; // rax
  const char *v31; // rax
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // r8
  _QWORD *v34; // rax
  const WCHAR *v35; // r9
  __int64 v36; // rdx
  _QWORD *v37; // rcx
  const WCHAR *v38; // rcx
  HANDLE FileW; // rsi
  char *v40; // rax
  const char *v41; // rax
  unsigned __int64 v42; // rbx
  char *v43; // rax
  const char *v44; // rax
  unsigned __int64 v45; // rbx
  int pvData; // [rsp+48h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-BCh] BYREF
  _QWORD lpFileName[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+68h] [rbp-A0h]
  _QWORD lpszVolumeMountPoint[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i v51; // [rsp+88h] [rbp-80h]
  __int128 v52; // [rsp+98h] [rbp-70h] BYREF
  __m128i v53; // [rsp+A8h] [rbp-60h]
  __int128 InBuffer; // [rsp+B8h] [rbp-50h] BYREF
  WCHAR szFileName[8]; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v56; // [rsp+D8h] [rbp-30h]
  __int128 OutBuffer; // [rsp+E8h] [rbp-20h] BYREF
  WCHAR szVolumeName[264]; // [rsp+F8h] [rbp-10h] BYREF

  *a2 = 0;
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\FileSystem",
             L"NtfsDisable8dot3NameCreation",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v5 = ValueW;
  if ( ValueW )
  {
    v6 = strrchr("admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp", 92);
    if ( v6 )
      v7 = v6 + 1;
    else
      v7 = "admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp";
    v8 = v5 | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v7) << 52);
    v9 = 0x72500000000LL;
    return v9 | v8;
  }
  if ( pvData )
  {
    if ( pvData == 1 )
    {
      *a2 = 0;
    }
    else
    {
      if ( (unsigned int)(pvData - 2) >= 2 )
      {
        v11 = strrchr("admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp", 92);
        if ( v11 )
          v12 = v11 + 1;
        else
          v12 = "admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp";
        v8 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v12) << 52;
        v9 = 0xA250000000DLL;
        return v9 | v8;
      }
      *(_OWORD *)&lpszVolumeMountPoint[1] = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v51 = si128;
      LOWORD(lpszVolumeMountPoint[1]) = 0;
      if ( !(unsigned __int8)paths::get_volume_path_name(lpszFileName) )
      {
        v14 = strrchr("admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp", 92);
        if ( v14 )
          v15 = v14 + 1;
        else
          v15 = "admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp";
        FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v15);
        LastError = GetLastError();
        v18 = 0xB2500000000LL;
LABEL_43:
        v22 = v18 | (FileId << 52) | LastError;
LABEL_67:
        std::wstring::~wstring((char **)&lpszVolumeMountPoint[1]);
        return v22;
      }
      if ( pvData == 3 )
      {
        *(_OWORD *)szFileName = 0;
        v56 = si128;
        szFileName[0] = 0;
        if ( (unsigned __int8)paths::get_system_directory(szFileName) )
        {
          v52 = 0;
          v53 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v52) = 0;
          if ( (unsigned __int8)paths::get_volume_path_name(szFileName) )
          {
            v27 = &v52;
            if ( v53.m128i_i64[1] > 7uLL )
              v27 = (__int128 *)v52;
            v28 = &lpszVolumeMountPoint[1];
            if ( v51.m128i_i64[1] > 7uLL )
              v28 = (_QWORD *)lpszVolumeMountPoint[1];
            *a2 = (unsigned int)_o__wcsicmp(v28, v27) == 0;
            std::wstring::~wstring((char **)&v52);
            std::wstring::~wstring((char **)szFileName);
            v22 = 0x8000000000LL;
            goto LABEL_67;
          }
          v24 = strrchr("admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp", 92);
          if ( v24 )
            v25 = v24 + 1;
          else
            v25 = "admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp";
          v26 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v25);
          v22 = (v26 << 52) | GetLastError() | 0xC2500000000LL;
          std::wstring::~wstring((char **)&v52);
        }
        else
        {
          v19 = strrchr("admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp", 92);
          if ( v19 )
            v20 = v19 + 1;
          else
            v20 = "admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp";
          v21 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v20);
          v22 = (v21 << 52) | GetLastError() | 0xC2500000000LL;
        }
        v23 = (char **)szFileName;
        goto LABEL_66;
      }
      v29 = (const WCHAR *)&lpszVolumeMountPoint[1];
      if ( v51.m128i_i64[1] > 7uLL )
        v29 = (const WCHAR *)lpszVolumeMountPoint[1];
      if ( !GetVolumeNameForVolumeMountPointW(v29, szVolumeName, 0x104u) )
      {
        v30 = strrchr("admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp", 92);
        if ( v30 )
          v31 = v30 + 1;
        else
          v31 = "admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp";
        FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v31);
        LastError = GetLastError();
        v18 = 0xD2500000000LL;
        goto LABEL_43;
      }
      *(_OWORD *)&lpFileName[1] = 0;
      v49 = 0;
      lpszVolumeMountPoint[0] = 0;
      v32 = -1;
      do
        ++v32;
      while ( szVolumeName[v32] );
      std::wstring::_Construct<1,wchar_t const *>((char **)&lpFileName[1], szVolumeName, v32);
      v33 = lpszVolumeMountPoint[0];
      v34 = &lpFileName[1];
      v35 = (const WCHAR *)lpFileName[1];
      if ( lpszVolumeMountPoint[0] > 7u )
        v34 = (_QWORD *)lpFileName[1];
      if ( *((_WORD *)v34 + v49 - 1) == 92 )
      {
        v36 = --v49;
        v37 = &lpFileName[1];
        if ( lpszVolumeMountPoint[0] > 7u )
          v37 = (_QWORD *)lpFileName[1];
        *((_WORD *)v37 + v36) = 0;
        v33 = lpszVolumeMountPoint[0];
        v35 = (const WCHAR *)lpFileName[1];
      }
      v38 = (const WCHAR *)&lpFileName[1];
      if ( v33 > 7 )
        v38 = v35;
      FileW = CreateFileW(v38, 0x80000000, 3u, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        v40 = strrchr("admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp", 92);
        if ( v40 )
          v41 = v40 + 1;
        else
          v41 = "admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp";
        v42 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v41);
        v22 = (v42 << 52) | GetLastError() | 0xF2500000000LL;
LABEL_65:
        v23 = (char **)&lpFileName[1];
LABEL_66:
        std::wstring::~wstring(v23);
        goto LABEL_67;
      }
      InBuffer = 0;
      *(_QWORD *)((char *)&InBuffer + 4) = 0x100000001LL;
      OutBuffer = 0;
      LODWORD(lpFileName[0]) = 0;
      if ( !DeviceIoControl(FileW, 0x9023Cu, &InBuffer, 0x10u, &OutBuffer, 0x10u, (LPDWORD)lpFileName, 0) )
      {
        v43 = strrchr("admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp", 92);
        if ( v43 )
          v44 = v43 + 1;
        else
          v44 = "admin\\AppMan\\AppV\\shared\\include\\paths\\short_paths.hpp";
        v45 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v44);
        v22 = (v45 << 52) | GetLastError() | 0x112500000000LL;
        if ( FileW )
          CloseHandle(FileW);
        goto LABEL_65;
      }
      *a2 = (OutBuffer & 1) == 0;
      if ( FileW )
        CloseHandle(FileW);
      std::wstring::~wstring((char **)&lpFileName[1]);
      std::wstring::~wstring((char **)&lpszVolumeMountPoint[1]);
    }
  }
  else
  {
    *a2 = 1;
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x140039834  mov     rax, rsp
0x140039837  mov     [rax+18h], rbx
0x14003983b  mov     [rax+20h], rsi
0x14003983f  push    rbp
0x140039840  push    rdi
0x140039841  push    r14
0x140039843  lea     rbp, [rax-238h]
0x14003984a  sub     rsp, 320h
0x140039851  movaps  xmmword ptr [rax-28h], xmm6
0x140039855  mov     rax, cs:__security_cookie
0x14003985c  xor     rax, rsp
0x14003985f  mov     [rbp+230h+var_30], rax
0x140039866  mov     rdi, rdx
0x140039869  mov     rbx, rcx
0x14003986c  xor     r14d, r14d
0x14003986f  mov     [rdx], r14b
0x140039872  mov     [rsp+330h+var_2F0], r14d
0x140039877  mov     [rsp+330h+var_2EC], 4
0x14003987f  lea     rax, [rsp+330h+var_2EC]
0x140039884  mov     [rsp+330h+pcbData], rax; pcbData
0x140039889  lea     rax, [rsp+330h+var_2F0]
0x14003988e  mov     [rsp+330h+pvData], rax; pvData
0x140039893  mov     [rsp+330h+pdwType], r14; pdwType
0x140039898  lea     r9d, [r14+10h]; dwFlags
0x14003989c  lea     r8, Value; "NtfsDisable8dot3NameCreation"
0x1400398a3  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Fil"...
0x1400398aa  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400398b1  call    cs:__imp_RegGetValueW
0x1400398b7  mov     esi, eax
0x1400398b9  test    eax, eax
0x1400398bb  jz      short loc_140039907
0x1400398bd  lea     edx, [r14+5Ch]; Ch
0x1400398c1  lea     rcx, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x1400398c8  call    cs:__imp_strrchr
0x1400398ce  test    rax, rax
0x1400398d1  jz      short loc_1400398D8
0x1400398d3  inc     rax
0x1400398d6  jmp     short loc_1400398DF
0x1400398d8  lea     rax, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x1400398df  mov     rdx, rax; char *
0x1400398e2  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400398e9  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400398ee  shl     rax, 34h
0x1400398f2  or      rax, rsi
0x1400398f5  mov     rcx, 72500000000h
0x1400398ff  or      rax, rcx
0x140039902  jmp     loc_140039DC9
0x140039907  mov     eax, [rsp+330h+var_2F0]
0x14003990b  test    eax, eax
0x14003990d  jz      loc_140039DBC
0x140039913  sub     eax, 1
0x140039916  jz      loc_140039DB7
0x14003991c  sub     eax, 1
0x14003991f  jz      short loc_140039968
0x140039921  cmp     eax, 1
0x140039924  jz      short loc_140039968
0x140039926  mov     edx, 5Ch ; '\'; Ch
0x14003992b  lea     rcx, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039932  call    cs:__imp_strrchr
0x140039938  test    rax, rax
0x14003993b  jz      short loc_140039942
0x14003993d  inc     rax
0x140039940  jmp     short loc_140039949
0x140039942  lea     rax, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039949  mov     rdx, rax; char *
0x14003994c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039953  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140039958  shl     rax, 34h
0x14003995c  mov     rcx, 0A250000000Dh
0x140039966  jmp     short loc_1400398FF
0x140039968  xorps   xmm0, xmm0
0x14003996b  movups  xmmword ptr [rsp+330h+lpszVolumeMountPoint+8], xmm0
0x140039970  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140039978  movdqu  [rbp+230h+var_2B0], xmm6
0x14003997d  mov     word ptr [rsp+330h+lpszVolumeMountPoint+8], r14w
0x140039983  lea     rdx, [rsp+330h+lpszVolumeMountPoint+8]
0x140039988  mov     rcx, rbx; lpszFileName
0x14003998b  call    paths__get_volume_path_name
0x140039990  test    al, al
0x140039992  jnz     short loc_1400399E0
0x140039994  mov     edx, 5Ch ; '\'; Ch
0x140039999  lea     rcx, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x1400399a0  call    cs:__imp_strrchr
0x1400399a6  test    rax, rax
0x1400399a9  jz      short loc_1400399B0
0x1400399ab  inc     rax
0x1400399ae  jmp     short loc_1400399B7
0x1400399b0  lea     rax, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x1400399b7  mov     rdx, rax; char *
0x1400399ba  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400399c1  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400399c6  mov     rbx, rax
0x1400399c9  call    cs:__imp_GetLastError
0x1400399cf  mov     edi, eax
0x1400399d1  mov     rax, 0B2500000000h
0x1400399db  jmp     loc_140039BA4
0x1400399e0  mov     esi, 3
0x1400399e5  cmp     [rsp+330h+var_2F0], esi
0x1400399e9  jnz     loc_140039B3B
0x1400399ef  xorps   xmm0, xmm0
0x1400399f2  movups  xmmword ptr [rbp+230h+szFileName], xmm0
0x1400399f6  movdqu  [rbp+230h+var_260], xmm6
0x1400399fb  mov     [rbp+230h+szFileName], r14w
0x140039a00  lea     rcx, [rbp+230h+szFileName]
0x140039a04  call    paths__get_system_directory
0x140039a09  test    al, al
0x140039a0b  jnz     short loc_140039A65
0x140039a0d  lea     edx, [rsi+59h]; Ch
0x140039a10  lea     rcx, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039a17  call    cs:__imp_strrchr
0x140039a1d  test    rax, rax
0x140039a20  jz      short loc_140039A27
0x140039a22  inc     rax
0x140039a25  jmp     short loc_140039A2E
0x140039a27  lea     rax, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039a2e  mov     rdx, rax; char *
0x140039a31  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039a38  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140039a3d  mov     rbx, rax
0x140039a40  call    cs:__imp_GetLastError
0x140039a46  mov     edi, eax
0x140039a48  shl     rbx, 34h
0x140039a4c  or      rdi, rbx
0x140039a4f  mov     rax, 0C2500000000h
0x140039a59  or      rdi, rax
0x140039a5c  lea     rcx, [rbp+230h+szFileName]
0x140039a60  jmp     loc_140039D74
0x140039a65  xorps   xmm0, xmm0
0x140039a68  movups  [rbp+230h+var_2A0], xmm0
0x140039a6c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140039a74  movdqu  [rbp+230h+var_290], xmm1
0x140039a79  mov     word ptr [rbp+230h+var_2A0], r14w
0x140039a7e  lea     rdx, [rbp+230h+var_2A0]
0x140039a82  lea     rcx, [rbp+230h+szFileName]; lpszFileName
0x140039a86  call    paths__get_volume_path_name
0x140039a8b  test    al, al
0x140039a8d  jnz     short loc_140039AEE
0x140039a8f  mov     edx, 5Ch ; '\'; Ch
0x140039a94  lea     rcx, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039a9b  call    cs:__imp_strrchr
0x140039aa1  test    rax, rax
0x140039aa4  jz      short loc_140039AAB
0x140039aa6  inc     rax
0x140039aa9  jmp     short loc_140039AB2
0x140039aab  lea     rax, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039ab2  mov     rdx, rax; char *
0x140039ab5  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039abc  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140039ac1  mov     rbx, rax
0x140039ac4  call    cs:__imp_GetLastError
0x140039aca  mov     edi, eax
0x140039acc  shl     rbx, 34h
0x140039ad0  or      rdi, rbx
0x140039ad3  mov     rax, 0C2500000000h
0x140039add  or      rdi, rax
0x140039ae0  lea     rcx, [rbp+230h+var_2A0]
0x140039ae4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140039ae9  jmp     loc_140039A5C
0x140039aee  lea     rdx, [rbp+230h+var_2A0]
0x140039af2  cmp     qword ptr [rbp+230h+var_290+8], 7
0x140039af7  cmova   rdx, qword ptr [rbp+230h+var_2A0]
0x140039afc  lea     rcx, [rsp+330h+lpszVolumeMountPoint+8]
0x140039b01  cmp     qword ptr [rbp+230h+var_2B0+8], 7
0x140039b06  cmova   rcx, qword ptr [rsp+330h+lpszVolumeMountPoint+8]
0x140039b0c  call    cs:__imp__o__wcsicmp
0x140039b12  test    eax, eax
0x140039b14  setz    al
0x140039b17  mov     [rdi], al
0x140039b19  lea     rcx, [rbp+230h+var_2A0]
0x140039b1d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140039b22  nop
0x140039b23  lea     rcx, [rbp+230h+szFileName]
0x140039b27  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140039b2c  mov     rdi, 8000000000h
0x140039b36  jmp     loc_140039D7A
0x140039b3b  lea     rcx, [rsp+330h+lpszVolumeMountPoint+8]
0x140039b40  cmp     qword ptr [rbp+230h+var_2B0+8], 7
0x140039b45  cmova   rcx, qword ptr [rsp+330h+lpszVolumeMountPoint+8]; lpszVolumeMountPoint
0x140039b4b  mov     r8d, 104h; cchBufferLength
0x140039b51  lea     rdx, [rbp+230h+szVolumeName]; lpszVolumeName
0x140039b55  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140039b5b  test    eax, eax
0x140039b5d  jnz     short loc_140039BB3
0x140039b5f  lea     edx, [rax+5Ch]; Ch
0x140039b62  lea     rcx, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039b69  call    cs:__imp_strrchr
0x140039b6f  test    rax, rax
0x140039b72  jz      short loc_140039B79
0x140039b74  inc     rax
0x140039b77  jmp     short loc_140039B80
0x140039b79  lea     rax, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039b80  mov     rdx, rax; char *
0x140039b83  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039b8a  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140039b8f  mov     rbx, rax
0x140039b92  call    cs:__imp_GetLastError
0x140039b98  mov     edi, eax
0x140039b9a  mov     rax, 0D2500000000h
0x140039ba4  shl     rbx, 34h
0x140039ba8  or      rdi, rbx
0x140039bab  or      rdi, rax
0x140039bae  jmp     loc_140039D7A
0x140039bb3  xorps   xmm0, xmm0
0x140039bb6  movups  xmmword ptr [rsp+330h+lpFileName+8], xmm0
0x140039bbb  mov     [rsp+330h+var_2D0], r14
0x140039bc0  mov     qword ptr [rsp+330h+lpszVolumeMountPoint], r14
0x140039bc5  lea     rax, [rbp+230h+szVolumeName]
0x140039bc9  or      r8, 0FFFFFFFFFFFFFFFFh
0x140039bcd  inc     r8
0x140039bd0  cmp     [rax+r8*2], r14w
0x140039bd5  jnz     short loc_140039BCD
0x140039bd7  lea     rdx, [rbp+230h+szVolumeName]
0x140039bdb  lea     rcx, [rsp+330h+lpFileName+8]
0x140039be0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140039be5  mov     r8, qword ptr [rsp+330h+lpszVolumeMountPoint]
0x140039bea  lea     rax, [rsp+330h+lpFileName+8]
0x140039bef  mov     r9, qword ptr [rsp+330h+lpFileName+8]
0x140039bf4  cmp     r8, 7
0x140039bf8  cmova   rax, r9
0x140039bfc  mov     ebx, 5Ch ; '\'
0x140039c01  mov     rdx, [rsp+330h+var_2D0]
0x140039c06  cmp     bx, [rax+rdx*2-2]
0x140039c0b  jnz     short loc_140039C31
0x140039c0d  dec     rdx
0x140039c10  mov     [rsp+330h+var_2D0], rdx
0x140039c15  lea     rcx, [rsp+330h+lpFileName+8]
0x140039c1a  cmp     r8, 7
0x140039c1e  cmova   rcx, r9
0x140039c22  mov     [rcx+rdx*2], r14w
0x140039c27  mov     r8, qword ptr [rsp+330h+lpszVolumeMountPoint]
0x140039c2c  mov     r9, qword ptr [rsp+330h+lpFileName+8]
0x140039c31  lea     rcx, [rsp+330h+lpFileName+8]
0x140039c36  cmp     r8, 7
0x140039c3a  cmova   rcx, r9; lpFileName
0x140039c3e  mov     [rsp+330h+pcbData], r14; hTemplateFile
0x140039c43  mov     dword ptr [rsp+330h+pvData], r14d; dwFlagsAndAttributes
0x140039c48  mov     dword ptr [rsp+330h+pdwType], esi; dwCreationDisposition
0x140039c4c  xor     r9d, r9d; lpSecurityAttributes
0x140039c4f  mov     r8d, esi; dwShareMode
0x140039c52  mov     edx, 80000000h; dwDesiredAccess
0x140039c57  call    cs:__imp_CreateFileW
0x140039c5d  mov     rsi, rax
0x140039c60  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140039c64  jnz     short loc_140039CB9
0x140039c66  mov     edx, ebx; Ch
0x140039c68  lea     rcx, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039c6f  call    cs:__imp_strrchr
0x140039c75  test    rax, rax
0x140039c78  jz      short loc_140039C7F
0x140039c7a  inc     rax
0x140039c7d  jmp     short loc_140039C86
0x140039c7f  lea     rax, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039c86  mov     rdx, rax; char *
0x140039c89  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039c90  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140039c95  mov     rbx, rax
0x140039c98  call    cs:__imp_GetLastError
0x140039c9e  mov     edi, eax
0x140039ca0  shl     rbx, 34h
0x140039ca4  or      rdi, rbx
0x140039ca7  mov     rax, 0F2500000000h
0x140039cb1  or      rdi, rax
0x140039cb4  jmp     loc_140039D6F
0x140039cb9  xorps   xmm0, xmm0
0x140039cbc  movups  [rbp+230h+InBuffer], xmm0
0x140039cc0  mov     dword ptr [rbp+230h+InBuffer+4], 1
0x140039cc7  mov     dword ptr [rbp+230h+InBuffer+8], 1
0x140039cce  movups  [rbp+230h+OutBuffer], xmm0
0x140039cd2  mov     dword ptr [rsp+330h+lpFileName], r14d
0x140039cd7  mov     [rsp+330h+lpOverlapped], r14; lpOverlapped
0x140039cdc  lea     rax, [rsp+330h+lpFileName]
0x140039ce1  mov     [rsp+330h+pcbData], rax; lpBytesReturned
0x140039ce6  mov     dword ptr [rsp+330h+pvData], 10h; nOutBufferSize
0x140039cee  lea     rax, [rbp+230h+OutBuffer]
0x140039cf2  mov     [rsp+330h+pdwType], rax; lpOutBuffer
0x140039cf7  mov     r9d, 10h; nInBufferSize
0x140039cfd  lea     r8, [rbp+230h+InBuffer]; lpInBuffer
0x140039d01  mov     edx, 9023Ch; dwIoControlCode
0x140039d06  mov     rcx, rsi; hDevice
0x140039d09  call    cs:__imp_DeviceIoControl
0x140039d0f  test    eax, eax
0x140039d11  jnz     short loc_140039D89
0x140039d13  mov     edx, ebx; Ch
0x140039d15  lea     rcx, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039d1c  call    cs:__imp_strrchr
0x140039d22  test    rax, rax
0x140039d25  jz      short loc_140039D2C
0x140039d27  inc     rax
0x140039d2a  jmp     short loc_140039D33
0x140039d2c  lea     rax, aAdminAppmanApp_19; "admin\\AppMan\\AppV\\shared\\include\\p"...
0x140039d33  mov     rdx, rax; char *
0x140039d36  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039d3d  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140039d42  mov     rbx, rax
0x140039d45  call    cs:__imp_GetLastError
0x140039d4b  mov     edi, eax
0x140039d4d  shl     rbx, 34h
0x140039d51  or      rdi, rbx
0x140039d54  mov     rax, 112500000000h
0x140039d5e  or      rdi, rax
  ... truncated ...
```
