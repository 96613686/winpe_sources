# GetVolumePathByFilePath(ushort *,int,ushort * *)

- ea: `0x14000b0d0`
- end: `0x14000b487`
- name: `?GetVolumePathByFilePath@@YAJPEAGHPEAPEAG@Z`
- size: `951`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x140038a50`
- `0x14003b070`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009c08`
- `0x14000b0d0`
- `0x14003fbb0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000b43c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000b43c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b1bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b23b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b37f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b1bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b23b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b37f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b44e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b44e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b1b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b1b0`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14000b30d`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14000b30d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b231`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b231`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14000b375`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14000b375`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x14000b3e8`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x14000b3e8`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x14000b2b5`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x14000b2b5`

## string_xrefs

- `0x14000b116`: `GetVolumePathByFilePath`

## pseudocode

```c
__int64 __fastcall GetVolumePathByFilePath(LPCWSTR lpszFileName, int a2, unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  __int64 v8; // r14
  DWORD v9; // eax
  _QWORD *v10; // rcx
  int v11; // edx
  WCHAR *v12; // r9
  DWORD v13; // eax
  _QWORD *v14; // rcx
  int v15; // edx
  WCHAR *v16; // r9
  __int64 v17; // rdx
  DWORD LastError; // eax
  DWORD v19; // eax
  __int64 v20; // rdx
  _BYTE v22[8]; // [rsp+40h] [rbp-C0h] BYREF
  HRESULT v23; // [rsp+48h] [rbp-B8h]
  OLECHAR szFilePath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+260h] [rbp+160h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "GetVolumePathByFilePath";
  CHResultImp::CHResultImp((CHResultImp *)v22);
  if ( !a3 )
  {
    v6 = -2147024809;
    v23 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_58242705c75132cdab80b446e38b4c82_Traceguids, 2147942487LL);
    }
    goto LABEL_47;
  }
  if ( a2 )
  {
    if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
    {
      LastError = GetLastError();
      v6 = ATL::AtlHresultFromWin32(LastError);
      v23 = v6;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v11 = 37;
      goto LABEL_12;
    }
    v8 = -1;
    if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szFilePath, 0x104u) )
    {
      v19 = GetLastError();
      v6 = ATL::AtlHresultFromWin32(v19);
      v23 = v6;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v11 = 38;
      v12 = szVolumePathName;
LABEL_13:
      WPP_SF_Sd(v10[2], v11, (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids, (_DWORD)v12, v6);
      goto LABEL_47;
    }
  }
  else
  {
    FileW = CreateFileW(lpszFileName, 0x80u, 7u, 0, 3u, 0x2000000u, 0);
    v8 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v9 = GetLastError();
      v6 = ATL::AtlHresultFromWin32(v9);
      v23 = v6;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v11 = 34;
LABEL_12:
      LODWORD(v12) = (_DWORD)lpszFileName;
      goto LABEL_13;
    }
    if ( !GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 1u) )
    {
      v13 = GetLastError();
      v6 = ATL::AtlHresultFromWin32(v13);
      v23 = v6;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v15 = 35;
      LODWORD(v16) = (_DWORD)lpszFileName;
LABEL_19:
      WPP_SF_Sd(v14[2], v15, (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids, (_DWORD)v16, v6);
LABEL_46:
      CloseHandle((HANDLE)v8);
      goto LABEL_47;
    }
    v17 = -1;
    do
      ++v17;
    while ( szFilePath[v17] );
    v23 = PathCchStripToRoot(szFilePath, v17 + 1);
    v6 = v23;
    if ( v23 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v15 = 36;
      v16 = szFilePath;
      goto LABEL_19;
    }
  }
  v20 = -1;
  do
    ++v20;
  while ( szFilePath[v20] );
  v23 = PathCchStripPrefix(szFilePath, v20 + 1);
  v6 = v23;
  if ( v23 >= 0 )
  {
    *a3 = SysAllocString(szFilePath);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids,
      (unsigned int)szFilePath,
      v23);
  }
  if ( v8 != -1 )
    goto LABEL_46;
LABEL_47:
  CHResultImp::~CHResultImp((CHResultImp *)v22);
  return v6;
}

```

## disassembly

```asm
0x14000b0d0  mov     [rsp-8+arg_8], rbx
0x14000b0d5  push    rbp
0x14000b0d6  push    rsi
0x14000b0d7  push    r12
0x14000b0d9  push    r14
0x14000b0db  push    r15
0x14000b0dd  lea     rbp, [rsp-380h]
0x14000b0e5  sub     rsp, 480h
0x14000b0ec  mov     rax, cs:__security_cookie
0x14000b0f3  xor     rax, rsp
0x14000b0f6  mov     [rbp+3A0h+var_30], rax
0x14000b0fd  mov     rax, gs:58h
0x14000b106  mov     rsi, rcx
0x14000b109  mov     ebx, edx
0x14000b10b  mov     r15, r8
0x14000b10e  mov     edx, 8
0x14000b113  mov     rcx, [rax]
0x14000b116  lea     rax, aGetvolumepathb; "GetVolumePathByFilePath"
0x14000b11d  mov     [rdx+rcx], rax
0x14000b121  lea     rcx, [rsp+4A0h+var_460]; this
0x14000b126  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000b12b  xor     r12d, r12d
0x14000b12e  test    r15, r15
0x14000b131  jnz     short loc_14000B184
0x14000b133  mov     ebx, 80070057h
0x14000b138  mov     [rsp+4A0h+var_458], ebx
0x14000b13c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b143  lea     rax, WPP_GLOBAL_Control
0x14000b14a  cmp     rcx, rax
0x14000b14d  jz      loc_14000B454
0x14000b153  test    byte ptr [rcx+1Ch], 1
0x14000b157  jz      loc_14000B454
0x14000b15d  cmp     byte ptr [rcx+19h], 2
0x14000b161  jb      loc_14000B454
0x14000b167  mov     rcx, [rcx+10h]
0x14000b16b  lea     edx, [r12+21h]
0x14000b170  mov     r9d, ebx
0x14000b173  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000b17a  call    WPP_SF_d
0x14000b17f  jmp     loc_14000B454
0x14000b184  mov     rcx, rsi; lpszFileName
0x14000b187  test    ebx, ebx
0x14000b189  jnz     loc_14000B300
0x14000b18f  mov     [rsp+4A0h+hTemplateFile], r12; hTemplateFile
0x14000b194  lea     r8d, [rbx+7]; dwShareMode
0x14000b198  mov     [rsp+4A0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x14000b1a0  xor     r9d, r9d; lpSecurityAttributes
0x14000b1a3  mov     edx, 80h; dwDesiredAccess
0x14000b1a8  mov     [rsp+4A0h+dwCreationDisposition], 3; dwCreationDisposition
0x14000b1b0  call    cs:__imp_CreateFileW
0x14000b1b6  mov     r14, rax
0x14000b1b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b1bd  jnz     short loc_14000B21D
0x14000b1bf  call    cs:__imp_GetLastError
0x14000b1c5  mov     ecx, eax; unsigned int
0x14000b1c7  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000b1cc  mov     ebx, eax
0x14000b1ce  mov     [rsp+4A0h+var_458], eax
0x14000b1d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b1d9  lea     rax, WPP_GLOBAL_Control
0x14000b1e0  cmp     rcx, rax
0x14000b1e3  jz      loc_14000B454
0x14000b1e9  test    byte ptr [rcx+1Ch], 1
0x14000b1ed  jz      loc_14000B454
0x14000b1f3  cmp     byte ptr [rcx+19h], 2
0x14000b1f7  jb      loc_14000B454
0x14000b1fd  lea     edx, [r14+23h]
0x14000b201  mov     r9, rsi
0x14000b204  mov     rcx, [rcx+10h]
0x14000b208  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000b20f  mov     [rsp+4A0h+dwCreationDisposition], ebx
0x14000b213  call    WPP_SF_Sd
0x14000b218  jmp     loc_14000B454
0x14000b21d  mov     r9d, 1; dwFlags
0x14000b223  lea     rdx, [rsp+4A0h+szFilePath]; lpszFilePath
0x14000b228  mov     r8d, 104h; cchFilePath
0x14000b22e  mov     rcx, rax; hFile
0x14000b231  call    cs:__imp_GetFinalPathNameByHandleW
0x14000b237  test    eax, eax
0x14000b239  jnz     short loc_14000B29A
0x14000b23b  call    cs:__imp_GetLastError
0x14000b241  mov     ecx, eax; unsigned int
0x14000b243  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000b248  mov     ebx, eax
0x14000b24a  mov     [rsp+4A0h+var_458], eax
0x14000b24e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b255  lea     rax, WPP_GLOBAL_Control
0x14000b25c  cmp     rcx, rax
0x14000b25f  jz      loc_14000B44B
0x14000b265  test    byte ptr [rcx+1Ch], 1
0x14000b269  jz      loc_14000B44B
0x14000b26f  cmp     byte ptr [rcx+19h], 2
0x14000b273  jb      loc_14000B44B
0x14000b279  mov     edx, 23h ; '#'
0x14000b27e  mov     r9, rsi
0x14000b281  mov     rcx, [rcx+10h]
0x14000b285  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000b28c  mov     [rsp+4A0h+dwCreationDisposition], ebx
0x14000b290  call    WPP_SF_Sd
0x14000b295  jmp     loc_14000B44B
0x14000b29a  lea     rax, [rsp+4A0h+szFilePath]
0x14000b29f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000b2a3  inc     rdx
0x14000b2a6  cmp     [rax+rdx*2], r12w
0x14000b2ab  jnz     short loc_14000B2A3
0x14000b2ad  inc     rdx; cchPath
0x14000b2b0  lea     rcx, [rsp+4A0h+szFilePath]; pszPath
0x14000b2b5  call    cs:__imp_PathCchStripToRoot
0x14000b2bb  mov     [rsp+4A0h+var_458], eax
0x14000b2bf  mov     ebx, eax
0x14000b2c1  test    eax, eax
0x14000b2c3  jns     loc_14000B3CD
0x14000b2c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b2d0  lea     rax, WPP_GLOBAL_Control
0x14000b2d7  cmp     rcx, rax
0x14000b2da  jz      loc_14000B44B
0x14000b2e0  test    byte ptr [rcx+1Ch], 1
0x14000b2e4  jz      loc_14000B44B
0x14000b2ea  cmp     byte ptr [rcx+19h], 2
0x14000b2ee  jb      loc_14000B44B
0x14000b2f4  mov     edx, 24h ; '$'
0x14000b2f9  lea     r9, [rsp+4A0h+szFilePath]
0x14000b2fe  jmp     short loc_14000B281
0x14000b300  mov     r8d, 104h; cchBufferLength
0x14000b306  lea     rdx, [rbp+3A0h+szVolumePathName]; lpszVolumePathName
0x14000b30d  call    cs:__imp_GetVolumePathNameW
0x14000b313  test    eax, eax
0x14000b315  jnz     short loc_14000B35F
0x14000b317  call    cs:__imp_GetLastError
0x14000b31d  mov     ecx, eax; unsigned int
0x14000b31f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000b324  mov     ebx, eax
0x14000b326  mov     [rsp+4A0h+var_458], eax
0x14000b32a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b331  lea     rax, WPP_GLOBAL_Control
0x14000b338  cmp     rcx, rax
0x14000b33b  jz      loc_14000B454
0x14000b341  test    byte ptr [rcx+1Ch], 1
0x14000b345  jz      loc_14000B454
0x14000b34b  cmp     byte ptr [rcx+19h], 2
0x14000b34f  jb      loc_14000B454
0x14000b355  mov     edx, 25h ; '%'
0x14000b35a  jmp     loc_14000B201
0x14000b35f  mov     r8d, 104h; cchBufferLength
0x14000b365  lea     rdx, [rsp+4A0h+szFilePath]; lpszVolumeName
0x14000b36a  lea     rcx, [rbp+3A0h+szVolumePathName]; lpszVolumeMountPoint
0x14000b371  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000b375  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14000b37b  test    eax, eax
0x14000b37d  jnz     short loc_14000B3CD
0x14000b37f  call    cs:__imp_GetLastError
0x14000b385  mov     ecx, eax; unsigned int
0x14000b387  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000b38c  mov     ebx, eax
0x14000b38e  mov     [rsp+4A0h+var_458], eax
0x14000b392  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b399  lea     rax, WPP_GLOBAL_Control
0x14000b3a0  cmp     rcx, rax
0x14000b3a3  jz      loc_14000B454
0x14000b3a9  test    byte ptr [rcx+1Ch], 1
0x14000b3ad  jz      loc_14000B454
0x14000b3b3  cmp     byte ptr [rcx+19h], 2
0x14000b3b7  jb      loc_14000B454
0x14000b3bd  lea     edx, [r14+27h]
0x14000b3c1  lea     r9, [rbp+3A0h+szVolumePathName]
0x14000b3c8  jmp     loc_14000B204
0x14000b3cd  lea     rax, [rsp+4A0h+szFilePath]
0x14000b3d2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000b3d6  inc     rdx
0x14000b3d9  cmp     [rax+rdx*2], r12w
0x14000b3de  jnz     short loc_14000B3D6
0x14000b3e0  inc     rdx; cchPath
0x14000b3e3  lea     rcx, [rsp+4A0h+szFilePath]; pszPath
0x14000b3e8  call    cs:__imp_PathCchStripPrefix
0x14000b3ee  mov     [rsp+4A0h+var_458], eax
0x14000b3f2  mov     ebx, eax
0x14000b3f4  test    eax, eax
0x14000b3f6  jns     short loc_14000B437
0x14000b3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b3ff  lea     rax, WPP_GLOBAL_Control
0x14000b406  cmp     rcx, rax
0x14000b409  jz      short loc_14000B445
0x14000b40b  test    byte ptr [rcx+1Ch], 1
0x14000b40f  jz      short loc_14000B445
0x14000b411  cmp     byte ptr [rcx+19h], 2
0x14000b415  jb      short loc_14000B445
0x14000b417  mov     rcx, [rcx+10h]
0x14000b41b  lea     r9, [rsp+4A0h+szFilePath]
0x14000b420  mov     edx, 27h ; '''
0x14000b425  mov     [rsp+4A0h+dwCreationDisposition], ebx
0x14000b429  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000b430  call    WPP_SF_Sd
0x14000b435  jmp     short loc_14000B445
0x14000b437  lea     rcx, [rsp+4A0h+szFilePath]; psz
0x14000b43c  call    cs:__imp_SysAllocString
0x14000b442  mov     [r15], rax
0x14000b445  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14000b449  jz      short loc_14000B454
0x14000b44b  mov     rcx, r14; hObject
0x14000b44e  call    cs:__imp_CloseHandle
0x14000b454  lea     rcx, [rsp+4A0h+var_460]; this
0x14000b459  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14000b45e  mov     eax, ebx
0x14000b460  mov     rcx, [rbp+3A0h+var_30]
0x14000b467  xor     rcx, rsp; StackCookie
0x14000b46a  call    __security_check_cookie
0x14000b46f  mov     rbx, [rsp+4A0h+arg_8]
0x14000b477  add     rsp, 480h
0x14000b47e  pop     r15
0x14000b480  pop     r14
0x14000b482  pop     r12
0x14000b484  pop     rsi
0x14000b485  pop     rbp
0x14000b486  retn
```
