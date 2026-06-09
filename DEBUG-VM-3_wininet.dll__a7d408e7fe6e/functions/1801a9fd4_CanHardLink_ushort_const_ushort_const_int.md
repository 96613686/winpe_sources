# CanHardLink(ushort const *,ushort const *,int *)

- ea: `0x1801a9fd4`
- end: `0x1801aa405`
- name: `?CanHardLink@@YAJPEBG0PEAH@Z`
- size: `1073`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, LPCWSTR, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180024ed4`

## callees

- `0x1800701d0`
- `0x18014a7a0`
- `0x1801a9fd4`
- `0x1801db754`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e21a0`
- `0x1801e41b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801aa1ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801aa33c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801aa1ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801aa33c`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801aa175`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801aa175`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1801aa11f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1801aa12e`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1801aa11f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1801aa12e`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801aa09c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801aa0e1`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801aa09c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801aa0e1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801aa23c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801aa27d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801aa2c1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801aa302`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801aa23c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801aa27d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801aa2c1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801aa302`

## pseudocode

```c
__int64 __fastcall CanHardLink(LPCWSTR lpszFileName, LPCWSTR a2, int *a3)
{
  unsigned int v3; // r14d
  signed int v7; // ebx
  int v8; // eax
  int v9; // eax
  UINT DriveTypeW; // edi
  UINT v11; // eax
  int LastError; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  DWORD FileSystemFlags; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szVolumeName[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v20[56]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v21[56]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR RootPathName[264]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v3 = 0;
  FileSystemFlags = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_SSq(
      1036,
      10,
      (unsigned int)&WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids,
      (_DWORD)a2,
      (__int64)lpszFileName,
      (__int64)a3);
  if ( a3 )
    *a3 = 0;
  if ( lpszFileName )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
        {
          if ( GetVolumePathNameW(a2, RootPathName, 0x104u) )
          {
            v7 = 0;
            DriveTypeW = GetDriveTypeW(szVolumePathName);
            v11 = GetDriveTypeW(RootPathName);
            if ( DriveTypeW != v11 || DriveTypeW == 4 )
            {
              if ( (BYTE1(xmmword_180266B60) & 0x10) == 0 )
                return (unsigned int)v7;
              WPP_SF_dd(1036, 11, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, DriveTypeW, v11);
              goto LABEL_68;
            }
            if ( DriveTypeW != 3 )
              goto LABEL_74;
            if ( !GetVolumeInformationW(szVolumePathName, 0, 0, 0, 0, &FileSystemFlags, 0, 0) )
            {
              LastError = WxGetLastError();
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
              if ( v7 >= 0 )
                v7 = -2147418113;
              goto LABEL_68;
            }
            if ( (FileSystemFlags & 0x400000) != 0 )
            {
LABEL_74:
              if ( (unsigned int)_o__wcsicmp(szVolumePathName, RootPathName) )
              {
                if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x32u) )
                {
                  v13 = WxGetLastError();
                  v7 = v13;
                  if ( v13 > 0 )
                    v7 = (unsigned __int16)v13 | 0x80070000;
                  if ( v7 >= 0 )
                    v7 = -2147418113;
                  goto LABEL_68;
                }
                if ( !GetVolumeNameForVolumeMountPointW(szVolumeName, v21, 0x32u) )
                {
                  v14 = WxGetLastError();
                  v7 = v14;
                  if ( v14 > 0 )
                    v7 = (unsigned __int16)v14 | 0x80070000;
                  if ( v7 >= 0 )
                    v7 = -2147418113;
                  goto LABEL_68;
                }
                if ( !GetVolumeNameForVolumeMountPointW(RootPathName, szVolumeName, 0x32u) )
                {
                  v15 = WxGetLastError();
                  v7 = v15;
                  if ( v15 > 0 )
                    v7 = (unsigned __int16)v15 | 0x80070000;
                  if ( v7 >= 0 )
                    v7 = -2147418113;
                  goto LABEL_68;
                }
                if ( !GetVolumeNameForVolumeMountPointW(szVolumeName, v20, 0x32u) )
                {
                  v16 = WxGetLastError();
                  v7 = v16;
                  if ( v16 > 0 )
                    v7 = (unsigned __int16)v16 | 0x80070000;
                  if ( v7 >= 0 )
                    v7 = -2147418113;
                  goto LABEL_68;
                }
                if ( (unsigned int)_o__wcsicmp(v21, v20) )
                {
                  if ( (BYTE1(xmmword_180266B60) & 0x10) == 0 )
                    return (unsigned int)v7;
                  WPP_SF_SS(
                    1036,
                    14,
                    (unsigned int)&WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids,
                    (unsigned int)v21,
                    (__int64)v20);
                  goto LABEL_68;
                }
              }
              else if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              {
                WPP_SF_S(1036, 13, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, szVolumePathName);
              }
              v3 = 1;
              *a3 = 1;
            }
            else
            {
              if ( (BYTE1(xmmword_180266B60) & 0x10) == 0 )
                return (unsigned int)v7;
              WPP_SF_d(1036, 12, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, FileSystemFlags);
            }
          }
          else
          {
            v9 = WxGetLastError();
            v7 = v9;
            if ( v9 > 0 )
              v7 = (unsigned __int16)v9 | 0x80070000;
            if ( v7 >= 0 )
              v7 = -2147418113;
          }
        }
        else
        {
          v8 = WxGetLastError();
          v7 = v8;
          if ( v8 > 0 )
            v7 = (unsigned __int16)v8 | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147418113;
        }
      }
      else
      {
        v7 = -2147024809;
      }
    }
    else
    {
      v7 = -2147024809;
    }
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_68:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    WPP_SF_d(1036, 15, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, v3);
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_d(1036, 16, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801a9fd4  push    rbp
0x1801a9fd6  push    rbx
0x1801a9fd7  push    rsi
0x1801a9fd8  push    rdi
0x1801a9fd9  push    r14
0x1801a9fdb  lea     rbp, [rsp-4D0h]
0x1801a9fe3  sub     rsp, 5D0h
0x1801a9fea  mov     rax, cs:__security_cookie
0x1801a9ff1  xor     rax, rsp
0x1801a9ff4  mov     [rbp+4F0h+var_30], rax
0x1801a9ffb  xor     r14d, r14d
0x1801a9ffe  mov     [rsp+5F0h+var_5AC], 0
0x1801aa006  mov     [rsp+5F0h+FileSystemFlags], r14d
0x1801aa00b  mov     rsi, r8
0x1801aa00e  mov     rdi, rdx
0x1801aa011  mov     rbx, rcx
0x1801aa014  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa01b  jz      short loc_1801AA03F
0x1801aa01d  mov     [rsp+5F0h+lpFileSystemFlags], r8
0x1801aa022  lea     edx, [r14+0Ah]
0x1801aa026  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa02d  mov     [rsp+5F0h+lpMaximumComponentLength], rbx
0x1801aa032  mov     ecx, 40Ch
0x1801aa037  mov     r9, rdi
0x1801aa03a  call    WPP_SF_SSq
0x1801aa03f  test    rsi, rsi
0x1801aa042  jz      short loc_1801AA047
0x1801aa044  mov     [rsi], r14d
0x1801aa047  test    rbx, rbx
0x1801aa04a  jnz     short loc_1801AA05E
0x1801aa04c  mov     ebx, 80070057h
0x1801aa051  mov     [rsp+5F0h+var_5AC], 23h ; '#'
0x1801aa059  jmp     loc_1801AA3A2
0x1801aa05e  test    rdi, rdi
0x1801aa061  jnz     short loc_1801AA075
0x1801aa063  mov     ebx, 80070057h
0x1801aa068  mov     [rsp+5F0h+var_5AC], 24h ; '$'
0x1801aa070  jmp     loc_1801AA3A2
0x1801aa075  test    rsi, rsi
0x1801aa078  jnz     short loc_1801AA08C
0x1801aa07a  mov     ebx, 80070057h
0x1801aa07f  mov     [rsp+5F0h+var_5AC], 25h ; '%'
0x1801aa087  jmp     loc_1801AA3A2
0x1801aa08c  mov     r8d, 104h; cchBufferLength
0x1801aa092  lea     rdx, [rbp+4F0h+szVolumePathName]; lpszVolumePathName
0x1801aa099  mov     rcx, rbx; lpszFileName
0x1801aa09c  call    cs:__imp_GetVolumePathNameW
0x1801aa0a2  test    eax, eax
0x1801aa0a4  jnz     short loc_1801AA0D1
0x1801aa0a6  call    WxGetLastError
0x1801aa0ab  mov     ebx, eax
0x1801aa0ad  test    eax, eax
0x1801aa0af  jle     short loc_1801AA0BA
0x1801aa0b1  movzx   ebx, ax
0x1801aa0b4  or      ebx, 80070000h
0x1801aa0ba  test    ebx, ebx
0x1801aa0bc  mov     [rsp+5F0h+var_5AC], 29h ; ')'
0x1801aa0c4  mov     eax, 8000FFFFh
0x1801aa0c9  cmovns  ebx, eax
0x1801aa0cc  jmp     loc_1801AA3A2
0x1801aa0d1  mov     r8d, 104h; cchBufferLength
0x1801aa0d7  lea     rdx, [rbp+4F0h+RootPathName]; lpszVolumePathName
0x1801aa0de  mov     rcx, rdi; lpszFileName
0x1801aa0e1  call    cs:__imp_GetVolumePathNameW
0x1801aa0e7  test    eax, eax
0x1801aa0e9  jnz     short loc_1801AA116
0x1801aa0eb  call    WxGetLastError
0x1801aa0f0  mov     ebx, eax
0x1801aa0f2  test    eax, eax
0x1801aa0f4  jle     short loc_1801AA0FF
0x1801aa0f6  movzx   ebx, ax
0x1801aa0f9  or      ebx, 80070000h
0x1801aa0ff  test    ebx, ebx
0x1801aa101  mov     [rsp+5F0h+var_5AC], 2Dh ; '-'
0x1801aa109  mov     eax, 8000FFFFh
0x1801aa10e  cmovns  ebx, eax
0x1801aa111  jmp     loc_1801AA3A2
0x1801aa116  lea     rcx, [rbp+4F0h+szVolumePathName]; lpRootPathName
0x1801aa11d  xor     ebx, ebx
0x1801aa11f  call    cs:__imp_GetDriveTypeW
0x1801aa125  lea     rcx, [rbp+4F0h+RootPathName]; lpRootPathName
0x1801aa12c  mov     edi, eax
0x1801aa12e  call    cs:__imp_GetDriveTypeW
0x1801aa134  cmp     edi, eax
0x1801aa136  jnz     loc_1801AA37C
0x1801aa13c  cmp     edi, 4
0x1801aa13f  jz      loc_1801AA37C
0x1801aa145  cmp     edi, 3
0x1801aa148  jnz     loc_1801AA1DE
0x1801aa14e  mov     [rsp+5F0h+nFileSystemNameSize], ebx; nFileSystemNameSize
0x1801aa152  lea     rax, [rsp+5F0h+FileSystemFlags]
0x1801aa157  mov     [rsp+5F0h+lpFileSystemNameBuffer], rbx; lpFileSystemNameBuffer
0x1801aa15c  lea     rcx, [rbp+4F0h+szVolumePathName]; lpRootPathName
0x1801aa163  mov     [rsp+5F0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1801aa168  xor     r9d, r9d; lpVolumeSerialNumber
0x1801aa16b  xor     r8d, r8d; nVolumeNameSize
0x1801aa16e  mov     [rsp+5F0h+lpMaximumComponentLength], rbx; lpMaximumComponentLength
0x1801aa173  xor     edx, edx; lpVolumeNameBuffer
0x1801aa175  call    cs:__imp_GetVolumeInformationW
0x1801aa17b  test    eax, eax
0x1801aa17d  jnz     short loc_1801AA1AA
0x1801aa17f  call    WxGetLastError
0x1801aa184  mov     ebx, eax
0x1801aa186  test    eax, eax
0x1801aa188  jle     short loc_1801AA193
0x1801aa18a  movzx   ebx, ax
0x1801aa18d  or      ebx, 80070000h
0x1801aa193  test    ebx, ebx
0x1801aa195  mov     [rsp+5F0h+var_5AC], 47h ; 'G'
0x1801aa19d  mov     eax, 8000FFFFh
0x1801aa1a2  cmovns  ebx, eax
0x1801aa1a5  jmp     loc_1801AA3A2
0x1801aa1aa  mov     r9d, [rsp+5F0h+FileSystemFlags]
0x1801aa1af  bt      r9d, 16h
0x1801aa1b4  jb      short loc_1801AA1DE
0x1801aa1b6  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa1bd  jz      loc_1801AA3E6
0x1801aa1c3  mov     edx, 0Ch
0x1801aa1c8  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa1cf  mov     ecx, 40Ch
0x1801aa1d4  call    WPP_SF_d
0x1801aa1d9  jmp     loc_1801AA3A2
0x1801aa1de  lea     rdx, [rbp+4F0h+RootPathName]
0x1801aa1e5  lea     rcx, [rbp+4F0h+szVolumePathName]
0x1801aa1ec  call    cs:__imp__o__wcsicmp
0x1801aa1f2  test    eax, eax
0x1801aa1f4  jnz     short loc_1801AA228
0x1801aa1f6  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa1fd  jz      short loc_1801AA21A
0x1801aa1ff  lea     edx, [rax+0Dh]
0x1801aa202  mov     ecx, 40Ch
0x1801aa207  lea     r9, [rbp+4F0h+szVolumePathName]
0x1801aa20e  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa215  call    WPP_SF_S
0x1801aa21a  mov     r14d, 1
0x1801aa220  mov     [rsi], r14d
0x1801aa223  jmp     loc_1801AA3A2
0x1801aa228  mov     edi, 32h ; '2'
0x1801aa22d  lea     rdx, [rsp+5F0h+szVolumeName]; lpszVolumeName
0x1801aa232  mov     r8d, edi; cchBufferLength
0x1801aa235  lea     rcx, [rbp+4F0h+szVolumePathName]; lpszVolumeMountPoint
0x1801aa23c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801aa242  test    eax, eax
0x1801aa244  jnz     short loc_1801AA271
0x1801aa246  call    WxGetLastError
0x1801aa24b  mov     ebx, eax
0x1801aa24d  test    eax, eax
0x1801aa24f  jle     short loc_1801AA25A
0x1801aa251  movzx   ebx, ax
0x1801aa254  or      ebx, 80070000h
0x1801aa25a  test    ebx, ebx
0x1801aa25c  mov     [rsp+5F0h+var_5AC], 60h ; '`'
0x1801aa264  mov     eax, 8000FFFFh
0x1801aa269  cmovns  ebx, eax
0x1801aa26c  jmp     loc_1801AA3A2
0x1801aa271  mov     r8d, edi; cchBufferLength
0x1801aa274  lea     rdx, [rbp+4F0h+var_4C0]; lpszVolumeName
0x1801aa278  lea     rcx, [rsp+5F0h+szVolumeName]; lpszVolumeMountPoint
0x1801aa27d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801aa283  test    eax, eax
0x1801aa285  jnz     short loc_1801AA2B2
0x1801aa287  call    WxGetLastError
0x1801aa28c  mov     ebx, eax
0x1801aa28e  test    eax, eax
0x1801aa290  jle     short loc_1801AA29B
0x1801aa292  movzx   ebx, ax
0x1801aa295  or      ebx, 80070000h
0x1801aa29b  test    ebx, ebx
0x1801aa29d  mov     [rsp+5F0h+var_5AC], 64h ; 'd'
0x1801aa2a5  mov     eax, 8000FFFFh
0x1801aa2aa  cmovns  ebx, eax
0x1801aa2ad  jmp     loc_1801AA3A2
0x1801aa2b2  mov     r8d, edi; cchBufferLength
0x1801aa2b5  lea     rdx, [rsp+5F0h+szVolumeName]; lpszVolumeName
0x1801aa2ba  lea     rcx, [rbp+4F0h+RootPathName]; lpszVolumeMountPoint
0x1801aa2c1  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801aa2c7  test    eax, eax
0x1801aa2c9  jnz     short loc_1801AA2F6
0x1801aa2cb  call    WxGetLastError
0x1801aa2d0  mov     ebx, eax
0x1801aa2d2  test    eax, eax
0x1801aa2d4  jle     short loc_1801AA2DF
0x1801aa2d6  movzx   ebx, ax
0x1801aa2d9  or      ebx, 80070000h
0x1801aa2df  test    ebx, ebx
0x1801aa2e1  mov     [rsp+5F0h+var_5AC], 68h ; 'h'
0x1801aa2e9  mov     eax, 8000FFFFh
0x1801aa2ee  cmovns  ebx, eax
0x1801aa2f1  jmp     loc_1801AA3A2
0x1801aa2f6  mov     r8d, edi; cchBufferLength
0x1801aa2f9  lea     rdx, [rbp+4F0h+var_530]; lpszVolumeName
0x1801aa2fd  lea     rcx, [rsp+5F0h+szVolumeName]; lpszVolumeMountPoint
0x1801aa302  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801aa308  test    eax, eax
0x1801aa30a  jnz     short loc_1801AA334
0x1801aa30c  call    WxGetLastError
0x1801aa311  mov     ebx, eax
0x1801aa313  test    eax, eax
0x1801aa315  jle     short loc_1801AA320
0x1801aa317  movzx   ebx, ax
0x1801aa31a  or      ebx, 80070000h
0x1801aa320  test    ebx, ebx
0x1801aa322  mov     [rsp+5F0h+var_5AC], 6Ch ; 'l'
0x1801aa32a  mov     eax, 8000FFFFh
0x1801aa32f  cmovns  ebx, eax
0x1801aa332  jmp     short loc_1801AA3A2
0x1801aa334  lea     rdx, [rbp+4F0h+var_530]
0x1801aa338  lea     rcx, [rbp+4F0h+var_4C0]
0x1801aa33c  call    cs:__imp__o__wcsicmp
0x1801aa342  test    eax, eax
0x1801aa344  jz      loc_1801AA21A
0x1801aa34a  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa351  jz      loc_1801AA3E6
0x1801aa357  lea     rax, [rbp+4F0h+var_530]
0x1801aa35b  mov     edx, 0Eh
0x1801aa360  mov     ecx, 40Ch
0x1801aa365  mov     [rsp+5F0h+lpMaximumComponentLength], rax
0x1801aa36a  lea     r9, [rbp+4F0h+var_4C0]
0x1801aa36e  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa375  call    WPP_SF_SS
0x1801aa37a  jmp     short loc_1801AA3A2
0x1801aa37c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa383  jz      short loc_1801AA3E6
0x1801aa385  mov     edx, 0Bh
0x1801aa38a  mov     dword ptr [rsp+5F0h+lpMaximumComponentLength], eax
0x1801aa38e  mov     ecx, 40Ch
0x1801aa393  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa39a  mov     r9d, edi
0x1801aa39d  call    WPP_SF_dd
0x1801aa3a2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa3a9  jz      short loc_1801AA3E6
0x1801aa3ab  mov     edx, 0Fh
0x1801aa3b0  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa3b7  mov     ecx, 40Ch
0x1801aa3bc  mov     r9d, r14d
0x1801aa3bf  call    WPP_SF_d
0x1801aa3c4  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa3cb  jz      short loc_1801AA3E6
0x1801aa3cd  mov     edx, 10h
0x1801aa3d2  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa3d9  mov     ecx, 40Ch
0x1801aa3de  mov     r9d, ebx
0x1801aa3e1  call    WPP_SF_d
0x1801aa3e6  mov     eax, ebx
0x1801aa3e8  mov     rcx, [rbp+4F0h+var_30]
0x1801aa3ef  xor     rcx, rsp; StackCookie
0x1801aa3f2  call    __security_check_cookie
0x1801aa3f7  add     rsp, 5D0h
0x1801aa3fe  pop     r14
0x1801aa400  pop     rdi
0x1801aa401  pop     rsi
0x1801aa402  pop     rbx
0x1801aa403  pop     rbp
0x1801aa404  retn
```
