# GetONBackupFolderFromRegistry(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>,std::allocator<std::pair<DirQueItem,ushort const *>>> &)

- ea: `0x180021b10`
- end: `0x180021f3b`
- name: `?GetONBackupFolderFromRegistry@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z`
- size: `1067`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x1800152d4`
- `0x180015bac`
- `0x18001c940`
- `0x18001f218`
- `0x18001faac`
- `0x18001fc6c`
- `0x180021b10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021d9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021d9a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021ce2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021ce2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021c35`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021c35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021bdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021d5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021bdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021d5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f02`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021e2d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021e2d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180021b86`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180021b86`

## string_xrefs

- `0x180021cfa`: `OneNote\Options\Paths`
- `0x180021d81`: `BackupFolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetONBackupFolderFromRegistry(__int64 *a1, _QWORD *a2)
{
  HRESULT v4; // eax
  signed int v5; // ebx
  char v6; // r14
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  DWORD v9; // eax
  DWORD i; // esi
  LSTATUS v11; // eax
  bool v12; // sf
  LSTATUS v13; // eax
  bool v14; // sf
  LSTATUS v15; // eax
  size_t v16; // rax
  const unsigned __int16 *v17; // r8
  unsigned __int64 v18; // rdx
  _OWORD *v19; // rdx
  unsigned __int16 *v20; // rax
  __int64 v21; // r8
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int64 v29; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v36; // [rsp+78h] [rbp-88h] BYREF
  PWSTR ppszPath; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v38[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+298h] [rbp+198h]
  unsigned __int16 v40[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t Data[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR Name[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR FileName[264]; // [rsp+8D0h] [rbp+7D0h] BYREF
  WCHAR SubKey[264]; // [rsp+AE0h] [rbp+9E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D48h] [rbp+C48h]

  ppszPath = 0;
  memset_0(v40, 0, 0x208u);
  memset_0(SubKey, 0, 0x208u);
  hKey = 0;
  v4 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  v5 = v4;
  if ( v4 >= 0 )
  {
    cSubKeys = 0;
    v6 = 0;
    v7 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Office", 0, 0x2000000u, &hKey);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 >= 0 )
    {
      v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 )
      {
        v9 = cSubKeys;
        if ( cSubKeys )
        {
          for ( i = 0; i < v9; ++i )
          {
            memset_0(Name, 0, 0x208u);
            cchName = 260;
            memset_0(Data, 0, 0x208u);
            v36 = 0;
            cbData = 520;
            memset_0(FileName, 0, 0x208u);
            v11 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
            v12 = v11 < 0;
            if ( v11 > 0 )
              v12 = 1;
            if ( !v12
              && StringCchPrintfW(
                   SubKey,
                   0x104u,
                   L"%s\\%s\\%s",
                   L"Software\\Microsoft\\Office",
                   Name,
                   L"OneNote\\Options\\Paths") >= 0 )
            {
              v13 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x2000000u, &v36);
              v14 = v13 < 0;
              if ( v13 > 0 )
                v14 = 1;
              if ( !v14 )
              {
                v15 = RegQueryValueExW(v36, L"BackupFolderPath", 0, 0, (LPBYTE)Data, &cbData);
                v5 = v15;
                if ( v15 > 0 )
                  v5 = (unsigned __int16)v15 | 0x80070000;
                if ( v5 < 0 )
                  break;
                v16 = wcsnlen_s(Data, 0x104u);
                if ( v16 - 1 > 0x102 )
                {
                  v5 = -2147418113;
                  break;
                }
                v17 = L"%s\\%s\\%s";
                if ( v40[v16 + 263] == 92 )
                  v17 = L"%s%s\\%s";
                v5 = StringCchPrintfW(FileName, 0x104u, v17, Data, Name, L"Backup");
                if ( v5 >= 0 && GetFileAttributesW(FileName) != -1 )
                {
                  v5 = StringCbCopyW(v40, v18, FileName);
                  if ( v5 >= 0 )
                  {
                    v19 = v38;
                    v20 = v40;
                    v21 = 4;
                    do
                    {
                      v22 = *((_OWORD *)v20 + 1);
                      *v19 = *(_OWORD *)v20;
                      v23 = *((_OWORD *)v20 + 2);
                      v19[1] = v22;
                      v24 = *((_OWORD *)v20 + 3);
                      v19[2] = v23;
                      v25 = *((_OWORD *)v20 + 4);
                      v19[3] = v24;
                      v26 = *((_OWORD *)v20 + 5);
                      v19[4] = v25;
                      v27 = *((_OWORD *)v20 + 6);
                      v19[5] = v26;
                      v28 = *((_OWORD *)v20 + 7);
                      v20 += 64;
                      v19[6] = v27;
                      v19[7] = v28;
                      v19 += 8;
                      --v21;
                    }
                    while ( v21 );
                    *(_QWORD *)v19 = *(_QWORD *)v20;
                    v29 = a2[1];
                    v39 = *a1;
                    if ( v29 == a2[2] )
                      std::vector<std::pair<DirQueItem,unsigned short const *>>::_Emplace_reallocate<std::pair<DirQueItem,unsigned short const *>>(
                        a2,
                        v29,
                        v38);
                    else
                      std::vector<std::pair<DirQueItem,unsigned short const *>>::_Emplace_back_with_unused_capacity<std::pair<DirQueItem,unsigned short const *>>(
                        (__int64)a2,
                        (__int64)v38,
                        0);
                  }
                  v6 = 1;
                  break;
                }
              }
            }
            v9 = cSubKeys;
          }
        }
        else
        {
          v5 = -2147012875;
        }
      }
    }
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    if ( v5 >= 0 && !v6 )
      return (unsigned int)-2147024893;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CF,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021b10  push    rbp
0x180021b12  push    rbx
0x180021b13  push    rsi
0x180021b14  push    rdi
0x180021b15  push    r12
0x180021b17  push    r13
0x180021b19  push    r14
0x180021b1b  push    r15
0x180021b1d  lea     rbp, [rsp-0C08h]
0x180021b25  sub     rsp, 0D08h
0x180021b2c  mov     rax, cs:__security_cookie
0x180021b33  xor     rax, rsp
0x180021b36  mov     [rbp+0C40h+var_50], rax
0x180021b3d  mov     rdi, rdx
0x180021b40  mov     r15, rcx
0x180021b43  mov     ebx, 208h
0x180021b48  lea     rcx, [rbp+0C40h+var_AA0]; void *
0x180021b4f  xor     r12d, r12d
0x180021b52  mov     r8d, ebx; Size
0x180021b55  xor     edx, edx; Val
0x180021b57  mov     [rbp+0C40h+ppszPath], r12
0x180021b5b  call    memset_0
0x180021b60  mov     r8d, ebx; Size
0x180021b63  lea     rcx, [rbp+0C40h+SubKey]; void *
0x180021b6a  xor     edx, edx; Val
0x180021b6c  call    memset_0
0x180021b71  lea     r9, [rbp+0C40h+ppszPath]; ppszPath
0x180021b75  mov     [rsp+0D40h+hKey], r12
0x180021b7a  xor     r8d, r8d; hToken
0x180021b7d  lea     rcx, FOLDERID_LocalAppData; rfid
0x180021b84  xor     edx, edx; dwFlags
0x180021b86  call    cs:__imp_SHGetKnownFolderPath
0x180021b8c  mov     ebx, eax
0x180021b8e  test    eax, eax
0x180021b90  jns     short loc_180021BB2
0x180021b92  mov     rcx, [rbp+0C48h]; this
0x180021b99  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180021ba0  mov     r9d, eax; char *
0x180021ba3  mov     edx, 4CFh; void *
0x180021ba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021bad  jmp     loc_180021F16
0x180021bb2  lea     rax, [rsp+0D40h+hKey]
0x180021bb7  mov     [rsp+0D40h+cSubKeys], r12d
0x180021bbc  mov     r9d, 2000000h; samDesired
0x180021bc2  mov     [rsp+0D40h+phkResult], rax; phkResult
0x180021bc7  xor     r8d, r8d; ulOptions
0x180021bca  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Office"
0x180021bd1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180021bd8  mov     r14b, r12b
0x180021bdb  call    cs:__imp_RegOpenKeyExW
0x180021be1  mov     ebx, eax
0x180021be3  mov     r13d, 80070000h
0x180021be9  test    eax, eax
0x180021beb  jle     short loc_180021BF3
0x180021bed  movzx   ebx, ax
0x180021bf0  or      ebx, r13d
0x180021bf3  test    ebx, ebx
0x180021bf5  js      loc_180021EF9
0x180021bfb  mov     rcx, [rsp+0D40h+hKey]; hKey
0x180021c00  lea     rax, [rsp+0D40h+cSubKeys]
0x180021c05  mov     [rsp+0D40h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180021c0a  xor     r9d, r9d; lpReserved
0x180021c0d  mov     [rsp+0D40h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180021c12  xor     r8d, r8d; lpcchClass
0x180021c15  mov     [rsp+0D40h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180021c1a  xor     edx, edx; lpClass
0x180021c1c  mov     [rsp+0D40h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180021c21  mov     [rsp+0D40h+lpcValues], r12; lpcValues
0x180021c26  mov     [rsp+0D40h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180021c2b  mov     [rsp+0D40h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180021c30  mov     [rsp+0D40h+phkResult], rax; lpcSubKeys
0x180021c35  call    cs:__imp_RegQueryInfoKeyW
0x180021c3b  mov     ebx, eax
0x180021c3d  test    eax, eax
0x180021c3f  jle     short loc_180021C47
0x180021c41  movzx   ebx, ax
0x180021c44  or      ebx, r13d
0x180021c47  test    ebx, ebx
0x180021c49  js      loc_180021EF9
0x180021c4f  mov     eax, [rsp+0D40h+cSubKeys]
0x180021c53  test    eax, eax
0x180021c55  jnz     short loc_180021C61
0x180021c57  mov     ebx, 80072EF5h
0x180021c5c  jmp     loc_180021EF9
0x180021c61  mov     esi, r12d
0x180021c64  cmp     esi, eax
0x180021c66  jnb     loc_180021EF9
0x180021c6c  xor     edx, edx; Val
0x180021c6e  lea     rcx, [rbp+0C40h+Name]; void *
0x180021c75  mov     r8d, 208h; Size
0x180021c7b  call    memset_0
0x180021c80  xor     edx, edx; Val
0x180021c82  mov     [rsp+0D40h+cchName], 104h
0x180021c8a  mov     r8d, 208h; Size
0x180021c90  lea     rcx, [rbp+0C40h+Data]; void *
0x180021c97  call    memset_0
0x180021c9c  mov     eax, 208h
0x180021ca1  mov     [rsp+0D40h+var_CC8], r12
0x180021ca6  mov     r8d, eax; Size
0x180021ca9  mov     [rsp+0D40h+cbData], eax
0x180021cad  xor     edx, edx; Val
0x180021caf  lea     rcx, [rbp+0C40h+FileName]; void *
0x180021cb6  call    memset_0
0x180021cbb  mov     rcx, [rsp+0D40h+hKey]; hKey
0x180021cc0  lea     r9, [rsp+0D40h+cchName]; lpcchName
0x180021cc5  mov     [rsp+0D40h+lpcValues], r12; lpftLastWriteTime
0x180021cca  lea     r8, [rbp+0C40h+Name]; lpName
0x180021cd1  mov     [rsp+0D40h+lpcbMaxClassLen], r12; lpcchClass
0x180021cd6  mov     edx, esi; dwIndex
0x180021cd8  mov     [rsp+0D40h+lpcbMaxSubKeyLen], r12; lpClass
0x180021cdd  mov     [rsp+0D40h+phkResult], r12; lpReserved
0x180021ce2  call    cs:__imp_RegEnumKeyExW
0x180021ce8  test    eax, eax
0x180021cea  jle     short loc_180021CF4
0x180021cec  movzx   eax, ax
0x180021cef  or      eax, r13d
0x180021cf2  test    eax, eax
0x180021cf4  js      loc_180021E38
0x180021cfa  lea     rax, aOnenoteOptions; "OneNote\\Options\\Paths"
0x180021d01  mov     edx, 104h; unsigned __int64
0x180021d06  mov     [rsp+0D40h+lpcbMaxSubKeyLen], rax
0x180021d0b  lea     r9, aSoftwareMicros_2; "Software\\Microsoft\\Office"
0x180021d12  lea     rax, [rbp+0C40h+Name]
0x180021d19  lea     r8, aSSS; "%s\\%s\\%s"
0x180021d20  mov     [rsp+0D40h+phkResult], rax
0x180021d25  lea     rcx, [rbp+0C40h+SubKey]; unsigned __int16 *
0x180021d2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021d31  test    eax, eax
0x180021d33  js      loc_180021E38
0x180021d39  lea     rax, [rsp+0D40h+var_CC8]
0x180021d3e  mov     r9d, 2000000h; samDesired
0x180021d44  xor     r8d, r8d; ulOptions
0x180021d47  mov     [rsp+0D40h+phkResult], rax; phkResult
0x180021d4c  lea     rdx, [rbp+0C40h+SubKey]; lpSubKey
0x180021d53  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180021d5a  call    cs:__imp_RegOpenKeyExW
0x180021d60  test    eax, eax
0x180021d62  jle     short loc_180021D6C
0x180021d64  movzx   eax, ax
0x180021d67  or      eax, r13d
0x180021d6a  test    eax, eax
0x180021d6c  js      loc_180021E38
0x180021d72  mov     rcx, [rsp+0D40h+var_CC8]; hKey
0x180021d77  lea     rax, [rsp+0D40h+cbData]
0x180021d7c  mov     [rsp+0D40h+lpcbMaxSubKeyLen], rax; lpcbData
0x180021d81  lea     rdx, aBackupfolderpa; "BackupFolderPath"
0x180021d88  lea     rax, [rbp+0C40h+Data]
0x180021d8f  xor     r9d, r9d; lpType
0x180021d92  xor     r8d, r8d; lpReserved
0x180021d95  mov     [rsp+0D40h+phkResult], rax; lpData
0x180021d9a  call    cs:__imp_RegQueryValueExW
0x180021da0  mov     ebx, eax
0x180021da2  test    eax, eax
0x180021da4  jle     short loc_180021DAC
0x180021da6  movzx   ebx, ax
0x180021da9  or      ebx, r13d
0x180021dac  test    ebx, ebx
0x180021dae  js      loc_180021EF9
0x180021db4  mov     ebx, 104h
0x180021db9  lea     rcx, [rbp+0C40h+Data]; Source
0x180021dc0  mov     edx, ebx; MaxCount
0x180021dc2  call    wcsnlen_s
0x180021dc7  lea     rcx, [rax-1]
0x180021dcb  cmp     rcx, 102h
0x180021dd2  ja      loc_180021EF4
0x180021dd8  cmp     [rbp+rax*2+0C40h+var_892], 5Ch ; '\'
0x180021de1  lea     rcx, aSSS_1; "%s%s\\%s"
0x180021de8  lea     rax, aBackup; "Backup"
0x180021def  mov     edx, ebx; unsigned __int64
0x180021df1  mov     [rsp+0D40h+lpcbMaxSubKeyLen], rax
0x180021df6  lea     r8, aSSS; "%s\\%s\\%s"
0x180021dfd  lea     rax, [rbp+0C40h+Name]
0x180021e04  cmovz   r8, rcx; unsigned __int16 *
0x180021e08  lea     r9, [rbp+0C40h+Data]
0x180021e0f  mov     [rsp+0D40h+phkResult], rax
0x180021e14  lea     rcx, [rbp+0C40h+FileName]; unsigned __int16 *
0x180021e1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021e20  mov     ebx, eax
0x180021e22  test    eax, eax
0x180021e24  js      short loc_180021E38
0x180021e26  lea     rcx, [rbp+0C40h+FileName]; lpFileName
0x180021e2d  call    cs:__imp_GetFileAttributesW
0x180021e33  cmp     eax, 0FFFFFFFFh
0x180021e36  jnz     short loc_180021E43
0x180021e38  mov     eax, [rsp+0D40h+cSubKeys]
0x180021e3c  inc     esi
0x180021e3e  jmp     loc_180021C64
0x180021e43  lea     r8, [rbp+0C40h+FileName]; unsigned __int16 *
0x180021e4a  lea     rcx, [rbp+0C40h+var_AA0]; unsigned __int16 *
0x180021e51  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180021e56  mov     ebx, eax
0x180021e58  test    eax, eax
0x180021e5a  js      loc_180021EEF
0x180021e60  mov     ecx, 80h
0x180021e65  lea     rdx, [rbp+0C40h+var_CB0]
0x180021e69  lea     rax, [rbp+0C40h+var_AA0]
0x180021e70  lea     r8d, [rcx-7Ch]
0x180021e74  movups  xmm0, xmmword ptr [rax]
0x180021e77  movups  xmm1, xmmword ptr [rax+10h]
0x180021e7b  movups  xmmword ptr [rdx], xmm0
0x180021e7e  movups  xmm0, xmmword ptr [rax+20h]
0x180021e82  movups  xmmword ptr [rdx+10h], xmm1
0x180021e86  movups  xmm1, xmmword ptr [rax+30h]
0x180021e8a  movups  xmmword ptr [rdx+20h], xmm0
0x180021e8e  movups  xmm0, xmmword ptr [rax+40h]
0x180021e92  movups  xmmword ptr [rdx+30h], xmm1
0x180021e96  movups  xmm1, xmmword ptr [rax+50h]
0x180021e9a  movups  xmmword ptr [rdx+40h], xmm0
0x180021e9e  movups  xmm0, xmmword ptr [rax+60h]
0x180021ea2  movups  xmmword ptr [rdx+50h], xmm1
0x180021ea6  movups  xmm1, xmmword ptr [rax+70h]
0x180021eaa  add     rax, rcx
0x180021ead  movups  xmmword ptr [rdx+60h], xmm0
0x180021eb1  movups  xmmword ptr [rdx+70h], xmm1
0x180021eb5  add     rdx, rcx
0x180021eb8  sub     r8, 1
0x180021ebc  jnz     short loc_180021E74
0x180021ebe  mov     rax, [rax]
0x180021ec1  mov     rcx, rdi
0x180021ec4  mov     [rdx], rax
0x180021ec7  mov     rdx, [rdi+8]
0x180021ecb  mov     rax, [r15]
0x180021ece  mov     [rbp+0C40h+var_AA8], rax
0x180021ed5  cmp     rdx, [rdi+10h]
0x180021ed9  jz      short loc_180021EE6
0x180021edb  lea     rdx, [rbp+0C40h+var_CB0]
0x180021edf  call    ??$_Emplace_back_with_unused_capacity@U?$pair@UDirQueItem@@PEBG@std@@@?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@AEAAAEAU?$pair@UDirQueItem@@PEBG@1@$$QEAU21@@Z; std::vector<std::pair<DirQueItem,ushort const *>>::_Emplace_back_with_unused_capacity<std::pair<DirQueItem,ushort const *>>(std::pair<DirQueItem,ushort const *> &&)
0x180021ee4  jmp     short loc_180021EEF
0x180021ee6  lea     r8, [rbp+0C40h+var_CB0]
0x180021eea  call    ??$_Emplace_reallocate@U?$pair@UDirQueItem@@PEBG@std@@@?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@AEAAPEAU?$pair@UDirQueItem@@PEBG@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<DirQueItem,ushort const *>>::_Emplace_reallocate<std::pair<DirQueItem,ushort const *>>(std::pair<DirQueItem,ushort const *> * const,std::pair<DirQueItem,ushort const *> &&)
0x180021eef  mov     r14b, 1
0x180021ef2  jmp     short loc_180021EF9
0x180021ef4  mov     ebx, 8000FFFFh
0x180021ef9  mov     rcx, [rbp+0C40h+ppszPath]; pv
0x180021efd  test    rcx, rcx
0x180021f00  jz      short loc_180021F08
0x180021f02  call    cs:__imp_CoTaskMemFree
0x180021f08  test    ebx, ebx
0x180021f0a  js      short loc_180021F16
0x180021f0c  test    r14b, r14b
0x180021f0f  jnz     short loc_180021F16
0x180021f11  mov     ebx, 80070003h
0x180021f16  mov     eax, ebx
0x180021f18  mov     rcx, [rbp+0C40h+var_50]
0x180021f1f  xor     rcx, rsp; StackCookie
0x180021f22  call    __security_check_cookie
0x180021f27  add     rsp, 0D08h
0x180021f2e  pop     r15
0x180021f30  pop     r14
0x180021f32  pop     r13
0x180021f34  pop     r12
0x180021f36  pop     rdi
0x180021f37  pop     rsi
0x180021f38  pop     rbx
0x180021f39  pop     rbp
0x180021f3a  retn
```
