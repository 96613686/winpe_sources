# CTieredVolume::EnumerateFilesByFileName(_TE_ENUM_INTERNAL_RESUME_KEY *,ulong,ushort *,ulong,_QUERY_FILE_LAYOUT_INPUT *)

- ea: `0x14000d804`
- end: `0x14000dd8c`
- name: `?EnumerateFilesByFileName@CTieredVolume@@QEAAJPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@KPEAGKPEAU_QUERY_FILE_LAYOUT_INPUT@@@Z`
- size: `1416`
- prototype: `__int64 __fastcall(CTieredVolume *this, struct _TE_ENUM_INTERNAL_RESUME_KEY *, char, unsigned __int16 *, unsigned int, struct _QUERY_FILE_LAYOUT_INPUT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x14003d2ec`

## callees

- `0x140002323`
- `0x140004ef0`
- `0x140005420`
- `0x140009c08`
- `0x14000acac`
- `0x14000d804`
- `0x1400163c0`
- `0x140017cd4`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d8ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d8ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc3e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000d910`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000d910`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000d89d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000dc21`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000d89d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000dc21`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000dd48`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000dd48`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x14000da33`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x14000da33`

## pseudocode

```c
__int64 __fastcall CTieredVolume::EnumerateFilesByFileName(
        CTieredVolume *this,
        struct _TE_ENUM_INTERNAL_RESUME_KEY *a2,
        char a3,
        unsigned __int16 *a4,
        unsigned int a5,
        struct _QUERY_FILE_LAYOUT_INPUT *a6)
{
  __int64 FirstFileW; // rsi
  signed int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  int v13; // edx
  WCHAR *v14; // r9
  signed int LastError; // eax
  __int64 v16; // rax
  WCHAR *v17; // r8
  unsigned __int16 *v18; // rcx
  __int64 v19; // rdx
  WCHAR *v20; // rcx
  unsigned __int64 v21; // rdx
  _QWORD *v22; // rcx
  int v23; // edx
  WCHAR *v24; // rax
  WCHAR *cFileName; // r9
  __int64 v26; // rax
  WCHAR *v27; // rcx
  unsigned __int64 v28; // rdx
  WCHAR *v29; // r8
  WCHAR *v30; // rcx
  __int64 v31; // rcx
  bool v32; // zf
  signed int v33; // eax
  _BYTE v35[8]; // [rsp+30h] [rbp-D0h] BYREF
  HRESULT FileIdByFilePath; // [rsp+38h] [rbp-C8h]
  _FILE_ID_128 v37; // [rsp+40h] [rbp-C0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::EnumerateFilesByFileName";
  CHResultImp::CHResultImp((CHResultImp *)v35);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = *((_QWORD *)a2 + 1);
  v37 = 0;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    FirstFileW = (__int64)FindFirstFileW(a4, &FindFileData);
    if ( FirstFileW == -1 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError == 2 )
      {
        v11 = 0;
LABEL_22:
        FileIdByFilePath = 0;
      }
      else
      {
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        FileIdByFilePath = v11;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            311,
            (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
            (_DWORD)a4,
            v11);
        }
      }
      goto LABEL_89;
    }
  }
  else if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 == 18 )
    {
      v11 = 0;
LABEL_12:
      FileIdByFilePath = 0;
      goto LABEL_88;
    }
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    FileIdByFilePath = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v13 = 312;
    goto LABEL_10;
  }
  v16 = 2147483646;
  v17 = pszPath;
  v18 = a4;
  v19 = 260;
  do
  {
    if ( !v16 )
      break;
    if ( !*v18 )
      break;
    *v17++ = *v18++;
    --v16;
    --v19;
  }
  while ( v19 );
  v20 = v17 - 1;
  v11 = v19 == 0 ? 0x8007007A : 0;
  FileIdByFilePath = v11;
  if ( v19 )
    v20 = v17;
  *v20 = 0;
  if ( !v19 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v13 = 313;
LABEL_10:
    LODWORD(v14) = (_DWORD)a4;
    goto LABEL_87;
  }
  FileIdByFilePath = PathCchRemoveFileSpec(pszPath, 0x104u);
  v11 = FileIdByFilePath;
  if ( FileIdByFilePath < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v13 = 314;
LABEL_86:
    v14 = pszPath;
LABEL_87:
    WPP_SF_Sd(v12[2], v13, (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (_DWORD)v14, v11);
    goto LABEL_88;
  }
  FileIdByFilePath = StringCbCatW(pszPath, v21, L"\\");
  v11 = FileIdByFilePath;
  if ( FileIdByFilePath < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = 315;
      v24 = pszPath;
      cFileName = (WCHAR *)L"\\";
LABEL_44:
      WPP_SF_SSd(
        v22[2],
        v23,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (_DWORD)cFileName,
        (__int64)v24,
        v11);
    }
    goto LABEL_88;
  }
  v11 = 0;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_61;
    }
    memset_0(FileName, 0, 0x104u);
    v26 = 2147483646;
    v27 = pszPath;
    v28 = 260;
    v29 = FileName;
    do
    {
      if ( !v26 )
        break;
      if ( !*v27 )
        break;
      *v29++ = *v27++;
      --v26;
      --v28;
    }
    while ( v28 );
    v30 = v29 - 1;
    v11 = v28 == 0 ? 0x8007007A : 0;
    FileIdByFilePath = v11;
    if ( v28 )
      v30 = v29;
    *v30 = 0;
    if ( !v28 )
      break;
    FileIdByFilePath = StringCbCatW(FileName, v28, FindFileData.cFileName);
    v11 = FileIdByFilePath;
    if ( FileIdByFilePath < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = 317;
        v24 = FileName;
        cFileName = FindFileData.cFileName;
        goto LABEL_44;
      }
      goto LABEL_88;
    }
    FileIdByFilePath = GetFileIdByFilePath(FileName, (a3 & 0x10) == 0, &v37);
    v11 = FileIdByFilePath;
    if ( FileIdByFilePath < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 318;
        v14 = FileName;
        goto LABEL_87;
      }
      goto LABEL_88;
    }
    v31 = *(_QWORD *)v37.Identifier;
    *((_QWORD *)a6 + 2 * *(unsigned int *)a6 + 2) = *(_QWORD *)v37.Identifier;
    *((_QWORD *)a6 + 2 * (unsigned int)(*(_DWORD *)a6)++ + 3) = v31;
    v11 = 0;
LABEL_61:
    v32 = *(_DWORD *)a6 == a5;
    if ( *(_DWORD *)a6 >= a5 )
      goto LABEL_64;
    if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
    {
      v32 = *(_DWORD *)a6 == a5;
LABEL_64:
      if ( v32 )
      {
        *(_DWORD *)a2 |= 1u;
        goto LABEL_22;
      }
      v33 = GetLastError();
      v11 = v33;
      if ( v33 == 18 )
      {
        v11 = 0;
        goto LABEL_12;
      }
      if ( v33 > 0 )
        v11 = (unsigned __int16)v33 | 0x80070000;
      FileIdByFilePath = v11;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 319;
        goto LABEL_10;
      }
      goto LABEL_88;
    }
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 316;
    goto LABEL_86;
  }
LABEL_88:
  FindClose((HANDLE)FirstFileW);
  FirstFileW = -1;
LABEL_89:
  *((_QWORD *)a2 + 1) = FirstFileW;
  CHResultImp::~CHResultImp((CHResultImp *)v35);
  return v11;
}

```

## disassembly

```asm
0x14000d804  mov     [rsp-8+arg_0], rbx
0x14000d809  push    rbp
0x14000d80a  push    rsi
0x14000d80b  push    rdi
0x14000d80c  push    r12
0x14000d80e  push    r13
0x14000d810  push    r14
0x14000d812  push    r15
0x14000d814  lea     rbp, [rsp-5D0h]
0x14000d81c  sub     rsp, 6D0h
0x14000d823  mov     rax, cs:__security_cookie
0x14000d82a  xor     rax, rsp
0x14000d82d  mov     [rbp+600h+var_40], rax
0x14000d834  mov     rax, gs:58h
0x14000d83d  mov     r13, rdx
0x14000d840  mov     rdi, [rbp+600h+arg_28]
0x14000d847  mov     r14, r9
0x14000d84a  mov     edx, 8
0x14000d84f  mov     r12d, r8d
0x14000d852  mov     rcx, [rax]
0x14000d855  lea     rax, aCtieredvolumeE; "CTieredVolume::EnumerateFilesByFileName"
0x14000d85c  mov     [rdx+rcx], rax
0x14000d860  lea     rcx, [rsp+700h+var_6D0]; this
0x14000d865  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000d86a  xor     edx, edx; Val
0x14000d86c  lea     rcx, [rsp+700h+FindFileData]; void *
0x14000d871  mov     r8d, 250h; Size
0x14000d877  call    memset_0
0x14000d87c  mov     rsi, [r13+8]
0x14000d880  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x14000d885  xor     r15d, r15d
0x14000d888  xorps   xmm0, xmm0
0x14000d88b  movups  xmmword ptr [rsp+700h+var_6C0.Identifier], xmm0
0x14000d890  lea     rax, [rsi-1]
0x14000d894  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d898  ja      short loc_14000D90D
0x14000d89a  mov     rcx, rsi; hFindFile
0x14000d89d  call    cs:__imp_FindNextFileW
0x14000d8a3  test    eax, eax
0x14000d8a5  jnz     loc_14000D995
0x14000d8ab  call    cs:__imp_GetLastError
0x14000d8b1  mov     ebx, eax
0x14000d8b3  cmp     eax, 12h
0x14000d8b6  jz      short loc_14000D901
0x14000d8b8  test    eax, eax
0x14000d8ba  jle     short loc_14000D8C5
0x14000d8bc  movzx   ebx, ax
0x14000d8bf  or      ebx, 80070000h
0x14000d8c5  mov     [rsp+700h+var_6C8], ebx
0x14000d8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8d0  lea     rax, WPP_GLOBAL_Control
0x14000d8d7  cmp     rcx, rax
0x14000d8da  jz      loc_14000DD45
0x14000d8e0  test    byte ptr [rcx+1Ch], 1
0x14000d8e4  jz      loc_14000DD45
0x14000d8ea  cmp     byte ptr [rcx+19h], 2
0x14000d8ee  jb      loc_14000DD45
0x14000d8f4  mov     edx, 138h
0x14000d8f9  mov     r9, r14
0x14000d8fc  jmp     loc_14000DD31
0x14000d901  mov     ebx, r15d
0x14000d904  mov     [rsp+700h+var_6C8], ebx
0x14000d908  jmp     loc_14000DD45
0x14000d90d  mov     rcx, r14; lpFileName
0x14000d910  call    cs:__imp_FindFirstFileW
0x14000d916  mov     rsi, rax
0x14000d919  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d91d  jnz     short loc_14000D995
0x14000d91f  call    cs:__imp_GetLastError
0x14000d925  mov     ebx, eax
0x14000d927  cmp     eax, 2
0x14000d92a  jz      short loc_14000D989
0x14000d92c  test    eax, eax
0x14000d92e  jle     short loc_14000D939
0x14000d930  movzx   ebx, ax
0x14000d933  or      ebx, 80070000h
0x14000d939  mov     [rsp+700h+var_6C8], ebx
0x14000d93d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d944  lea     rax, WPP_GLOBAL_Control
0x14000d94b  cmp     rcx, rax
0x14000d94e  jz      loc_14000DD52
0x14000d954  test    byte ptr [rcx+1Ch], 1
0x14000d958  jz      loc_14000DD52
0x14000d95e  cmp     byte ptr [rcx+19h], 2
0x14000d962  jb      loc_14000DD52
0x14000d968  mov     rcx, [rcx+10h]
0x14000d96c  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000d973  mov     edx, 137h
0x14000d978  mov     dword ptr [rsp+700h+var_6E0], ebx
0x14000d97c  mov     r9, r14
0x14000d97f  call    WPP_SF_Sd
0x14000d984  jmp     loc_14000DD52
0x14000d989  mov     ebx, r15d
0x14000d98c  mov     [rsp+700h+var_6C8], ebx
0x14000d990  jmp     loc_14000DD52
0x14000d995  mov     eax, 7FFFFFFEh
0x14000d99a  lea     r8, [rbp+600h+pszPath]
0x14000d9a1  mov     rcx, r14
0x14000d9a4  mov     edx, 104h
0x14000d9a9  test    rax, rax
0x14000d9ac  jz      short loc_14000D9CD
0x14000d9ae  movzx   r9d, word ptr [rcx]
0x14000d9b2  test    r9w, r9w
0x14000d9b6  jz      short loc_14000D9CD
0x14000d9b8  mov     [r8], r9w
0x14000d9bc  add     rcx, 2
0x14000d9c0  add     r8, 2
0x14000d9c4  dec     rax
0x14000d9c7  sub     rdx, 1
0x14000d9cb  jnz     short loc_14000D9A9
0x14000d9cd  mov     rax, rdx
0x14000d9d0  lea     rcx, [r8-2]
0x14000d9d4  neg     rax
0x14000d9d7  sbb     ebx, ebx
0x14000d9d9  not     ebx
0x14000d9db  and     ebx, 8007007Ah
0x14000d9e1  test    rdx, rdx
0x14000d9e4  mov     [rsp+700h+var_6C8], ebx
0x14000d9e8  cmovnz  rcx, r8
0x14000d9ec  mov     [rcx], r15w
0x14000d9f0  jnz     short loc_14000DA27
0x14000d9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9f9  lea     rax, WPP_GLOBAL_Control
0x14000da00  cmp     rcx, rax
0x14000da03  jz      loc_14000DD45
0x14000da09  test    byte ptr [rcx+1Ch], 1
0x14000da0d  jz      loc_14000DD45
0x14000da13  cmp     byte ptr [rcx+19h], 2
0x14000da17  jb      loc_14000DD45
0x14000da1d  mov     edx, 139h
0x14000da22  jmp     loc_14000D8F9
0x14000da27  mov     edx, 104h; cchPath
0x14000da2c  lea     rcx, [rbp+600h+pszPath]; pszPath
0x14000da33  call    cs:__imp_PathCchRemoveFileSpec
0x14000da39  mov     [rsp+700h+var_6C8], eax
0x14000da3d  mov     ebx, eax
0x14000da3f  test    eax, eax
0x14000da41  jns     short loc_14000DA78
0x14000da43  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da4a  lea     rax, WPP_GLOBAL_Control
0x14000da51  cmp     rcx, rax
0x14000da54  jz      loc_14000DD45
0x14000da5a  test    byte ptr [rcx+1Ch], 1
0x14000da5e  jz      loc_14000DD45
0x14000da64  cmp     byte ptr [rcx+19h], 2
0x14000da68  jb      loc_14000DD45
0x14000da6e  mov     edx, 13Ah
0x14000da73  jmp     loc_14000DD2A
0x14000da78  lea     r8, asc_1400435C0; "\\"
0x14000da7f  lea     rcx, [rbp+600h+pszPath]; unsigned __int16 *
0x14000da86  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000da8b  mov     [rsp+700h+var_6C8], eax
0x14000da8f  mov     ebx, eax
0x14000da91  test    eax, eax
0x14000da93  jns     short loc_14000DAF1
0x14000da95  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da9c  lea     rax, WPP_GLOBAL_Control
0x14000daa3  cmp     rcx, rax
0x14000daa6  jz      loc_14000DD45
0x14000daac  test    byte ptr [rcx+1Ch], 1
0x14000dab0  jz      loc_14000DD45
0x14000dab6  cmp     byte ptr [rcx+19h], 2
0x14000daba  jb      loc_14000DD45
0x14000dac0  mov     edx, 13Bh
0x14000dac5  lea     rax, [rbp+600h+pszPath]
0x14000dacc  lea     r9, asc_1400435C0; "\\"
0x14000dad3  mov     rcx, [rcx+10h]
0x14000dad7  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000dade  mov     [rsp+700h+var_6D8], ebx
0x14000dae2  mov     [rsp+700h+var_6E0], rax
0x14000dae7  call    WPP_SF_SSd
0x14000daec  jmp     loc_14000DD45
0x14000daf1  mov     r15d, [rbp+600h+arg_20]
0x14000daf8  xor     ebx, ebx
0x14000dafa  test    byte ptr [rsp+700h+FindFileData.dwFileAttributes], 10h
0x14000daff  jz      short loc_14000DB2F
0x14000db01  cmp     [rsp+700h+FindFileData.cFileName], 2Eh ; '.'
0x14000db07  movzx   eax, [rsp+700h+FindFileData.cFileName+2]
0x14000db0c  jnz     short loc_14000DB2F
0x14000db0e  test    ax, ax
0x14000db11  jz      loc_14000DC14
0x14000db17  cmp     [rsp+700h+FindFileData.cFileName], 2Eh ; '.'
0x14000db1d  jnz     short loc_14000DB2F
0x14000db1f  cmp     ax, 2Eh ; '.'
0x14000db23  jnz     short loc_14000DB2F
0x14000db25  cmp     [rbp+600h+FindFileData.cFileName+4], bx
0x14000db29  jz      loc_14000DC14
0x14000db2f  xor     edx, edx; Val
0x14000db31  lea     rcx, [rbp+600h+FileName]; void *
0x14000db38  mov     r8d, 104h; Size
0x14000db3e  call    memset_0
0x14000db43  mov     eax, 7FFFFFFEh
0x14000db48  lea     rcx, [rbp+600h+pszPath]
0x14000db4f  mov     edx, 104h
0x14000db54  lea     r8, [rbp+600h+FileName]
0x14000db5b  test    rax, rax
0x14000db5e  jz      short loc_14000DB7F
0x14000db60  movzx   r9d, word ptr [rcx]
0x14000db64  test    r9w, r9w
0x14000db68  jz      short loc_14000DB7F
0x14000db6a  mov     [r8], r9w
0x14000db6e  add     rcx, 2
0x14000db72  add     r8, 2
0x14000db76  dec     rax
0x14000db79  sub     rdx, 1; unsigned __int64
0x14000db7d  jnz     short loc_14000DB5B
0x14000db7f  mov     rax, rdx
0x14000db82  lea     rcx, [r8-2]
0x14000db86  neg     rax
0x14000db89  sbb     ebx, ebx
0x14000db8b  not     ebx
0x14000db8d  and     ebx, 8007007Ah
0x14000db93  test    rdx, rdx
0x14000db96  mov     [rsp+700h+var_6C8], ebx
0x14000db9a  cmovnz  rcx, r8
0x14000db9e  xor     eax, eax
0x14000dba0  mov     [rcx], ax
0x14000dba3  test    rdx, rdx
0x14000dba6  jz      loc_14000DD06
0x14000dbac  lea     r8, [rsp+700h+FindFileData.cFileName]; unsigned __int16 *
0x14000dbb1  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x14000dbb8  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000dbbd  mov     [rsp+700h+var_6C8], eax
0x14000dbc1  mov     ebx, eax
0x14000dbc3  test    eax, eax
0x14000dbc5  js      loc_14000DCD1
0x14000dbcb  mov     edx, r12d
0x14000dbce  lea     r8, [rsp+700h+var_6C0]; struct _FILE_ID_128 *
0x14000dbd3  shr     edx, 4
0x14000dbd6  lea     rcx, [rbp+600h+FileName]; lpFileName
0x14000dbdd  not     edx
0x14000dbdf  and     edx, 1; int
0x14000dbe2  call    ?GetFileIdByFilePath@@YAJPEAGHPEAU_FILE_ID_128@@@Z; GetFileIdByFilePath(ushort *,int,_FILE_ID_128 *)
0x14000dbe7  mov     [rsp+700h+var_6C8], eax
0x14000dbeb  mov     ebx, eax
0x14000dbed  test    eax, eax
0x14000dbef  js      loc_14000DC98
0x14000dbf5  mov     eax, [rdi]
0x14000dbf7  mov     rcx, qword ptr [rsp+700h+var_6C0.Identifier]
0x14000dbfc  inc     rax
0x14000dbff  add     rax, rax
0x14000dc02  mov     [rdi+rax*8], rcx
0x14000dc06  mov     eax, [rdi]
0x14000dc08  add     rax, rax
0x14000dc0b  mov     [rdi+rax*8+18h], rcx
0x14000dc10  inc     dword ptr [rdi]
0x14000dc12  xor     ebx, ebx
0x14000dc14  cmp     [rdi], r15d
0x14000dc17  jnb     short loc_14000DC32
0x14000dc19  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x14000dc1e  mov     rcx, rsi; hFindFile
0x14000dc21  call    cs:__imp_FindNextFileW
0x14000dc27  test    eax, eax
0x14000dc29  jnz     loc_14000DAFA
0x14000dc2f  cmp     [rdi], r15d
0x14000dc32  jnz     short loc_14000DC3E
0x14000dc34  or      dword ptr [r13+0], 1
0x14000dc39  jmp     loc_14000D98C
0x14000dc3e  call    cs:__imp_GetLastError
0x14000dc44  mov     ebx, eax
0x14000dc46  cmp     eax, 12h
0x14000dc49  jz      short loc_14000DC91
0x14000dc4b  test    eax, eax
0x14000dc4d  jle     short loc_14000DC58
0x14000dc4f  movzx   ebx, ax
0x14000dc52  or      ebx, 80070000h
0x14000dc58  mov     [rsp+700h+var_6C8], ebx
0x14000dc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc63  lea     rax, WPP_GLOBAL_Control
0x14000dc6a  cmp     rcx, rax
0x14000dc6d  jz      loc_14000DD45
0x14000dc73  test    byte ptr [rcx+1Ch], 1
0x14000dc77  jz      loc_14000DD45
0x14000dc7d  cmp     byte ptr [rcx+19h], 2
0x14000dc81  jb      loc_14000DD45
0x14000dc87  mov     edx, 13Fh
0x14000dc8c  jmp     loc_14000D8F9
0x14000dc91  xor     ebx, ebx
0x14000dc93  jmp     loc_14000D904
0x14000dc98  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc9f  lea     rax, WPP_GLOBAL_Control
0x14000dca6  cmp     rcx, rax
0x14000dca9  jz      loc_14000DD45
0x14000dcaf  test    byte ptr [rcx+1Ch], 1
0x14000dcb3  jz      loc_14000DD45
0x14000dcb9  cmp     byte ptr [rcx+19h], 2
0x14000dcbd  jb      loc_14000DD45
0x14000dcc3  mov     edx, 13Eh
0x14000dcc8  lea     r9, [rbp+600h+FileName]
0x14000dccf  jmp     short loc_14000DD31
0x14000dcd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dcd8  lea     rax, WPP_GLOBAL_Control
0x14000dcdf  cmp     rcx, rax
0x14000dce2  jz      short loc_14000DD45
0x14000dce4  test    byte ptr [rcx+1Ch], 1
0x14000dce8  jz      short loc_14000DD45
0x14000dcea  cmp     byte ptr [rcx+19h], 2
0x14000dcee  jb      short loc_14000DD45
0x14000dcf0  mov     edx, 13Dh
0x14000dcf5  lea     rax, [rbp+600h+FileName]
  ... truncated ...
```
