# CTieredVolume::SetDesiredStorageClass(ushort *,ulong,_STORAGE_TIER_CLASS)

- ea: `0x140014fe4`
- end: `0x14001563f`
- name: `?SetDesiredStorageClass@CTieredVolume@@QEAAJPEAGKW4_STORAGE_TIER_CLASS@@@Z`
- size: `1627`
- prototype: `__int64 __fastcall(CTieredVolume *this, LPCWSTR lpFileName, char, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x14003c7e8`
- `0x14003e9d0`

## callees

- `0x140002323`
- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009c08`
- `0x14000c648`
- `0x140014fe4`
- `0x1400163c0`
- `0x140017cd4`
- `0x1400185a0`
- `0x14003fbb0`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x140015368`
- `ntdll!NtSetInformationFile` at `0x140015368`
- `ntdll!RtlNtStatusToDosError` at `0x1400154d9`
- `ntdll!RtlNtStatusToDosError` at `0x1400154d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400153d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001548c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400153d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001548c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400153b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001552e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400153b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001552e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001533a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001533a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140015080`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140015080`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400153ca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400153ca`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140015603`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140015603`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14001538e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14001538e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x14001517f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x14001517f`

## pseudocode

```c
__int64 __fastcall CTieredVolume::SetDesiredStorageClass(
        CTieredVolume *this,
        LPCWSTR lpFileName,
        char a3,
        unsigned int a4)
{
  signed int LastError; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  int v11; // edx
  WCHAR *v12; // r9
  WCHAR *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rax
  LPCWSTR v16; // rcx
  WCHAR *v17; // rcx
  unsigned __int64 v18; // rdx
  _QWORD *v19; // rcx
  int v20; // edx
  WCHAR *v21; // rax
  WCHAR *cFileName; // r9
  int v23; // r15d
  __int64 v24; // rax
  WCHAR *v25; // rcx
  unsigned __int64 v26; // rdx
  WCHAR *v27; // r8
  WCHAR *v28; // rcx
  HANDLE FileW; // rax
  void *v30; // rdi
  int v31; // eax
  char v32; // si
  signed int v33; // eax
  DWORD v34; // eax
  ULONG v35; // eax
  signed int v36; // eax
  _BYTE v38[8]; // [rsp+40h] [rbp-C0h] BYREF
  HRESULT v39; // [rsp+48h] [rbp-B8h]
  __int64 FileInformation; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFindFile; // [rsp+58h] [rbp-A8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR pszPath[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::SetDesiredStorageClass";
  CHResultImp::CHResultImp((CHResultImp *)v38);
  IoStatusBlock = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v43 = 0;
  v44 = 0;
  FileInformation = a4;
  hFindFile = FindFirstFileW(lpFileName, &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v39 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    v11 = 267;
LABEL_8:
    LODWORD(v12) = (_DWORD)lpFileName;
    goto LABEL_88;
  }
  v13 = pszPath;
  v14 = 260;
  v15 = 2147483646;
  v16 = lpFileName;
  do
  {
    if ( !v15 )
      break;
    if ( !*v16 )
      break;
    *v13++ = *v16++;
    --v15;
    --v14;
  }
  while ( v14 );
  v17 = v13 - 1;
  v9 = v14 == 0 ? 0x8007007A : 0;
  v39 = v9;
  if ( v14 )
    v17 = v13;
  *v17 = 0;
  if ( !v14 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    v11 = 268;
    goto LABEL_8;
  }
  v39 = PathCchRemoveFileSpec(pszPath, 0x104u);
  v9 = v39;
  if ( v39 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 269;
      goto LABEL_87;
    }
    goto LABEL_89;
  }
  v39 = StringCbCatW(pszPath, v18, L"\\");
  v9 = v39;
  if ( v39 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    v20 = 270;
    v21 = pszPath;
    cFileName = (WCHAR *)L"\\";
    goto LABEL_30;
  }
  v23 = a3 & 0x10;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_51;
    }
    memset_0(FileName, 0, 0x104u);
    v24 = 2147483646;
    v25 = pszPath;
    v26 = 260;
    v27 = FileName;
    do
    {
      if ( !v24 )
        break;
      if ( !*v25 )
        break;
      *v27++ = *v25++;
      --v24;
      --v26;
    }
    while ( v26 );
    v28 = v27 - 1;
    v9 = v26 == 0 ? 0x8007007A : 0;
    v39 = v9;
    if ( v26 )
      v28 = v27;
    *v28 = 0;
    if ( !v26 )
      break;
    v39 = StringCbCatW(FileName, v26, FindFileData.cFileName);
    v9 = v39;
    if ( v39 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v20 = 272;
      v21 = FileName;
      cFileName = FindFileData.cFileName;
LABEL_30:
      WPP_SF_SSd(
        v19[2],
        v20,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (_DWORD)cFileName,
        (__int64)v21,
        v9);
      goto LABEL_89;
    }
    FileW = CreateFileW(FileName, 0x180u, 7u, 0, 3u, v23 != 0 ? 0x2000000 : 35651584, 0);
    v30 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v36 = GetLastError();
      v9 = v36;
      if ( v36 > 0 )
        v9 = (unsigned __int16)v36 | 0x80070000;
      v39 = v9;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 273;
        v12 = FileName;
        goto LABEL_88;
      }
      goto LABEL_89;
    }
    v31 = NtSetInformationFile(FileW, &IoStatusBlock, &FileInformation, 8u, FileBothDirectoryInformation|0x40);
    v32 = v31;
    if ( v31 < 0 )
    {
      v35 = RtlNtStatusToDosError(v31);
      v9 = ATL::AtlHresultFromWin32(v35);
      v39 = v9;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          274,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (unsigned int)FileName,
          v32);
      }
      goto LABEL_72;
    }
    if ( !a4 )
    {
      if ( !GetFileInformationByHandleEx(v30, MaximumFileInfoByHandleClass, &v43, 0x18u) )
      {
        v34 = GetLastError();
        v9 = ATL::AtlHresultFromWin32(v34);
        v39 = v9;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            275,
            (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
            (_DWORD)lpFileName,
            v9);
        }
        goto LABEL_72;
      }
      v39 = CTieredVolume::ClearPinnedFlagFromHeatDb(this, (struct TE_FILE_ID_128 *)((char *)&v43 + 8));
      v9 = v39;
      if ( v39 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            276,
            (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
            0,
            0,
            (__int64)this + 672,
            v39);
        }
LABEL_72:
        CloseHandle(v30);
        goto LABEL_89;
      }
    }
    CloseHandle(v30);
LABEL_51:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
    {
      v33 = GetLastError();
      v9 = v33;
      if ( v33 == 18 )
      {
        v9 = 0;
        v39 = 0;
      }
      else
      {
        if ( v33 > 0 )
          v9 = (unsigned __int16)v33 | 0x80070000;
        v39 = v9;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 277;
          goto LABEL_8;
        }
      }
      goto LABEL_89;
    }
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 271;
LABEL_87:
    v12 = pszPath;
LABEL_88:
    WPP_SF_Sd(v10[2], v11, (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (_DWORD)v12, v9);
  }
LABEL_89:
  FindClose(hFindFile);
  CHResultImp::~CHResultImp((CHResultImp *)v38);
  return v9;
}

```

## disassembly

```asm
0x140014fe4  mov     [rsp-8+arg_10], rbx
0x140014fe9  push    rbp
0x140014fea  push    rsi
0x140014feb  push    rdi
0x140014fec  push    r12
0x140014fee  push    r13
0x140014ff0  push    r14
0x140014ff2  push    r15
0x140014ff4  lea     rbp, [rsp-610h]
0x140014ffc  sub     rsp, 710h
0x140015003  mov     rax, cs:__security_cookie
0x14001500a  xor     rax, rsp
0x14001500d  mov     [rbp+640h+var_40], rax
0x140015014  mov     rax, gs:58h
0x14001501d  mov     r13, rcx
0x140015020  mov     r14, rdx
0x140015023  mov     ecx, 8
0x140015028  mov     r12d, r9d
0x14001502b  mov     r15d, r8d
0x14001502e  mov     rdx, [rax]
0x140015031  lea     rax, aCtieredvolumeS; "CTieredVolume::SetDesiredStorageClass"
0x140015038  mov     [rcx+rdx], rax
0x14001503c  lea     rcx, [rsp+740h+var_700]; this
0x140015041  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140015046  xorps   xmm0, xmm0
0x140015049  lea     rcx, [rbp+640h+FindFileData]; void *
0x14001504d  xor     edx, edx; Val
0x14001504f  mov     r8d, 250h; Size
0x140015055  movups  xmmword ptr [rsp+740h+IoStatusBlock], xmm0
0x14001505a  call    memset_0
0x14001505f  xorps   xmm0, xmm0
0x140015062  lea     rdx, [rbp+640h+FindFileData]; lpFindFileData
0x140015066  xor     eax, eax
0x140015068  xor     esi, esi
0x14001506a  mov     [rsp+740h+FileInformation], rsi
0x14001506f  mov     rcx, r14; lpFileName
0x140015072  movups  [rsp+740h+var_6D0], xmm0
0x140015077  mov     [rbp+640h+var_6C0], rax
0x14001507b  mov     dword ptr [rsp+740h+FileInformation], r12d
0x140015080  call    cs:__imp_FindFirstFileW
0x140015086  mov     [rsp+740h+hFindFile], rax
0x14001508b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001508f  jnz     short loc_1400150E2
0x140015091  call    cs:__imp_GetLastError
0x140015097  mov     ebx, eax
0x140015099  test    eax, eax
0x14001509b  jle     short loc_1400150A6
0x14001509d  movzx   ebx, ax
0x1400150a0  or      ebx, 80070000h
0x1400150a6  mov     [rsp+740h+var_6F8], ebx
0x1400150aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400150b1  lea     rax, WPP_GLOBAL_Control
0x1400150b8  cmp     rcx, rax
0x1400150bb  jz      loc_1400155FE
0x1400150c1  test    byte ptr [rcx+1Ch], 1
0x1400150c5  jz      loc_1400155FE
0x1400150cb  cmp     byte ptr [rcx+19h], 2
0x1400150cf  jb      loc_1400155FE
0x1400150d5  mov     edx, 10Bh
0x1400150da  mov     r9, r14
0x1400150dd  jmp     loc_1400155EA
0x1400150e2  mov     edi, 104h
0x1400150e7  lea     r8, [rbp+640h+pszPath]
0x1400150ee  mov     edx, edi
0x1400150f0  mov     eax, 7FFFFFFEh
0x1400150f5  mov     rcx, r14
0x1400150f8  test    rax, rax
0x1400150fb  jz      short loc_14001511C
0x1400150fd  movzx   r9d, word ptr [rcx]
0x140015101  test    r9w, r9w
0x140015105  jz      short loc_14001511C
0x140015107  mov     [r8], r9w
0x14001510b  add     rcx, 2
0x14001510f  add     r8, 2
0x140015113  dec     rax
0x140015116  sub     rdx, 1
0x14001511a  jnz     short loc_1400150F8
0x14001511c  mov     rax, rdx
0x14001511f  lea     rcx, [r8-2]
0x140015123  neg     rax
0x140015126  sbb     ebx, ebx
0x140015128  not     ebx
0x14001512a  and     ebx, 8007007Ah
0x140015130  test    rdx, rdx
0x140015133  mov     [rsp+740h+var_6F8], ebx
0x140015137  cmovnz  rcx, r8
0x14001513b  mov     [rcx], si
0x14001513e  jnz     short loc_140015175
0x140015140  mov     rcx, cs:WPP_GLOBAL_Control
0x140015147  lea     rax, WPP_GLOBAL_Control
0x14001514e  cmp     rcx, rax
0x140015151  jz      loc_1400155FE
0x140015157  test    byte ptr [rcx+1Ch], 1
0x14001515b  jz      loc_1400155FE
0x140015161  cmp     byte ptr [rcx+19h], 2
0x140015165  jb      loc_1400155FE
0x14001516b  mov     edx, 10Ch
0x140015170  jmp     loc_1400150DA
0x140015175  mov     rdx, rdi; cchPath
0x140015178  lea     rcx, [rbp+640h+pszPath]; pszPath
0x14001517f  call    cs:__imp_PathCchRemoveFileSpec
0x140015185  mov     [rsp+740h+var_6F8], eax
0x140015189  mov     ebx, eax
0x14001518b  test    eax, eax
0x14001518d  jns     short loc_1400151C4
0x14001518f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015196  lea     rax, WPP_GLOBAL_Control
0x14001519d  cmp     rcx, rax
0x1400151a0  jz      loc_1400155FE
0x1400151a6  test    byte ptr [rcx+1Ch], 1
0x1400151aa  jz      loc_1400155FE
0x1400151b0  cmp     byte ptr [rcx+19h], 2
0x1400151b4  jb      loc_1400155FE
0x1400151ba  mov     edx, 10Dh
0x1400151bf  jmp     loc_1400155E3
0x1400151c4  lea     r8, asc_1400435C0; "\\"
0x1400151cb  lea     rcx, [rbp+640h+pszPath]; unsigned __int16 *
0x1400151d2  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400151d7  mov     [rsp+740h+var_6F8], eax
0x1400151db  mov     ebx, eax
0x1400151dd  test    eax, eax
0x1400151df  jns     short loc_14001523D
0x1400151e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400151e8  lea     rax, WPP_GLOBAL_Control
0x1400151ef  cmp     rcx, rax
0x1400151f2  jz      loc_1400155FE
0x1400151f8  test    byte ptr [rcx+1Ch], 1
0x1400151fc  jz      loc_1400155FE
0x140015202  cmp     byte ptr [rcx+19h], 2
0x140015206  jb      loc_1400155FE
0x14001520c  mov     edx, 10Eh
0x140015211  lea     rax, [rbp+640h+pszPath]
0x140015218  lea     r9, asc_1400435C0; "\\"
0x14001521f  mov     rcx, [rcx+10h]
0x140015223  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14001522a  mov     [rsp+740h+dwFlagsAndAttributes], ebx
0x14001522e  mov     qword ptr [rsp+740h+dwCreationDisposition], rax
0x140015233  call    WPP_SF_SSd
0x140015238  jmp     loc_1400155FE
0x14001523d  and     r15d, 10h
0x140015241  test    byte ptr [rbp+640h+FindFileData.dwFileAttributes], 10h
0x140015245  jz      short loc_140015272
0x140015247  cmp     [rbp+640h+FindFileData.cFileName], 2Eh ; '.'
0x14001524c  movzx   eax, [rbp+640h+FindFileData.cFileName+2]
0x140015250  jnz     short loc_140015272
0x140015252  test    ax, ax
0x140015255  jz      loc_1400153C1
0x14001525b  cmp     [rbp+640h+FindFileData.cFileName], 2Eh ; '.'
0x140015260  jnz     short loc_140015272
0x140015262  cmp     ax, 2Eh ; '.'
0x140015266  jnz     short loc_140015272
0x140015268  cmp     [rbp+640h+FindFileData.cFileName+4], si
0x14001526c  jz      loc_1400153C1
0x140015272  mov     r8, rdi; Size
0x140015275  lea     rcx, [rbp+640h+FileName]; void *
0x14001527c  xor     edx, edx; Val
0x14001527e  call    memset_0
0x140015283  mov     eax, 7FFFFFFEh
0x140015288  lea     rcx, [rbp+640h+pszPath]
0x14001528f  mov     rdx, rdi
0x140015292  lea     r8, [rbp+640h+FileName]
0x140015299  test    rax, rax
0x14001529c  jz      short loc_1400152BD
0x14001529e  movzx   r9d, word ptr [rcx]
0x1400152a2  test    r9w, r9w
0x1400152a6  jz      short loc_1400152BD
0x1400152a8  mov     [r8], r9w
0x1400152ac  add     rcx, 2
0x1400152b0  add     r8, 2
0x1400152b4  dec     rax
0x1400152b7  sub     rdx, 1; unsigned __int64
0x1400152bb  jnz     short loc_140015299
0x1400152bd  mov     rax, rdx
0x1400152c0  lea     rcx, [r8-2]
0x1400152c4  neg     rax
0x1400152c7  sbb     ebx, ebx
0x1400152c9  not     ebx
0x1400152cb  and     ebx, 8007007Ah
0x1400152d1  test    rdx, rdx
0x1400152d4  mov     [rsp+740h+var_6F8], ebx
0x1400152d8  cmovnz  rcx, r8
0x1400152dc  mov     [rcx], si
0x1400152df  jz      loc_1400155BF
0x1400152e5  lea     r8, [rbp+640h+FindFileData.cFileName]; unsigned __int16 *
0x1400152e9  lea     rcx, [rbp+640h+FileName]; unsigned __int16 *
0x1400152f0  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400152f5  mov     [rsp+740h+var_6F8], eax
0x1400152f9  mov     ebx, eax
0x1400152fb  test    eax, eax
0x1400152fd  js      loc_14001558B
0x140015303  mov     eax, r15d
0x140015306  mov     [rsp+740h+hTemplateFile], rsi; hTemplateFile
0x14001530b  neg     eax
0x14001530d  mov     edx, 180h; dwDesiredAccess
0x140015312  sbb     ecx, ecx
0x140015314  xor     r9d, r9d; lpSecurityAttributes
0x140015317  and     ecx, 0FFE00000h
0x14001531d  add     ecx, 2200000h
0x140015323  mov     [rsp+740h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x140015327  lea     rcx, [rbp+640h+FileName]; lpFileName
0x14001532e  lea     r8d, [r9+7]; dwShareMode
0x140015332  mov     [rsp+740h+dwCreationDisposition], 3; dwCreationDisposition
0x14001533a  call    cs:__imp_CreateFileW
0x140015340  mov     rdi, rax
0x140015343  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140015347  jz      loc_140015539
0x14001534d  mov     r9d, 8; Length
0x140015353  mov     [rsp+740h+dwCreationDisposition], 43h ; 'C'; FileInformationClass
0x14001535b  lea     r8, [rsp+740h+FileInformation]; FileInformation
0x140015360  mov     rcx, rax; FileHandle
0x140015363  lea     rdx, [rsp+740h+IoStatusBlock]; IoStatusBlock
0x140015368  call    cs:__imp_NtSetInformationFile
0x14001536e  mov     esi, eax
0x140015370  test    eax, eax
0x140015372  js      loc_1400154D7
0x140015378  xor     esi, esi
0x14001537a  test    r12d, r12d
0x14001537d  jnz     short loc_1400153B3
0x14001537f  lea     r9d, [rsi+18h]; dwBufferSize
0x140015383  mov     rcx, rdi; hFile
0x140015386  lea     r8, [rsp+740h+var_6D0]; lpFileInformation
0x14001538b  lea     edx, [rsi+12h]; FileInformationClass
0x14001538e  call    cs:__imp_GetFileInformationByHandleEx
0x140015394  test    eax, eax
0x140015396  jz      loc_14001548C
0x14001539c  lea     rdx, [rsp+740h+var_6D0+8]; struct TE_FILE_ID_128 *
0x1400153a1  mov     rcx, r13; this
0x1400153a4  call    ?ClearPinnedFlagFromHeatDb@CTieredVolume@@QEAAJPEAUTE_FILE_ID_128@@@Z; CTieredVolume::ClearPinnedFlagFromHeatDb(TE_FILE_ID_128 *)
0x1400153a9  mov     [rsp+740h+var_6F8], eax
0x1400153ad  mov     ebx, eax
0x1400153af  test    eax, eax
0x1400153b1  js      short loc_14001542F
0x1400153b3  mov     rcx, rdi; hObject
0x1400153b6  call    cs:__imp_CloseHandle
0x1400153bc  mov     edi, 104h
0x1400153c1  mov     rcx, [rsp+740h+hFindFile]; hFindFile
0x1400153c6  lea     rdx, [rbp+640h+FindFileData]; lpFindFileData
0x1400153ca  call    cs:__imp_FindNextFileW
0x1400153d0  test    eax, eax
0x1400153d2  jnz     loc_140015241
0x1400153d8  call    cs:__imp_GetLastError
0x1400153de  mov     ebx, eax
0x1400153e0  cmp     eax, 12h
0x1400153e3  jz      loc_1400154CC
0x1400153e9  test    eax, eax
0x1400153eb  jle     short loc_1400153F6
0x1400153ed  movzx   ebx, ax
0x1400153f0  or      ebx, 80070000h
0x1400153f6  mov     [rsp+740h+var_6F8], ebx
0x1400153fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140015401  lea     rax, WPP_GLOBAL_Control
0x140015408  cmp     rcx, rax
0x14001540b  jz      loc_1400155FE
0x140015411  test    byte ptr [rcx+1Ch], 1
0x140015415  jz      loc_1400155FE
0x14001541b  cmp     byte ptr [rcx+19h], 2
0x14001541f  jb      loc_1400155FE
0x140015425  mov     edx, 115h
0x14001542a  jmp     loc_1400150DA
0x14001542f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015436  lea     rax, WPP_GLOBAL_Control
0x14001543d  cmp     rcx, rax
0x140015440  jz      loc_14001552B
0x140015446  test    byte ptr [rcx+1Ch], 1
0x14001544a  jz      loc_14001552B
0x140015450  cmp     byte ptr [rcx+19h], 2
0x140015454  jb      loc_14001552B
0x14001545a  mov     rcx, [rcx+10h]
0x14001545e  lea     rax, [r13+2A0h]
0x140015465  mov     dword ptr [rsp+740h+hTemplateFile], ebx
0x140015469  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140015470  mov     qword ptr [rsp+740h+dwFlagsAndAttributes], rax
0x140015475  mov     edx, 114h
0x14001547a  xor     r9d, r9d
0x14001547d  mov     qword ptr [rsp+740h+dwCreationDisposition], rsi
0x140015482  call    WPP_SF_iiZd
0x140015487  jmp     loc_14001552B
0x14001548c  call    cs:__imp_GetLastError
0x140015492  mov     ecx, eax; unsigned int
0x140015494  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140015499  mov     ebx, eax
0x14001549b  mov     [rsp+740h+var_6F8], eax
0x14001549f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154a6  lea     rax, WPP_GLOBAL_Control
0x1400154ad  cmp     rcx, rax
0x1400154b0  jz      short loc_14001552B
0x1400154b2  test    byte ptr [rcx+1Ch], 1
0x1400154b6  jz      short loc_14001552B
0x1400154b8  cmp     byte ptr [rcx+19h], 2
0x1400154bc  jb      short loc_14001552B
0x1400154be  mov     edx, 113h
0x1400154c3  mov     [rsp+740h+dwCreationDisposition], ebx
0x1400154c7  mov     r9, r14
0x1400154ca  jmp     short loc_14001551B
0x1400154cc  mov     ebx, esi
0x1400154ce  mov     [rsp+740h+var_6F8], ebx
0x1400154d2  jmp     loc_1400155FE
0x1400154d7  mov     ecx, esi; Status
0x1400154d9  call    cs:__imp_RtlNtStatusToDosError
0x1400154df  mov     ecx, eax; unsigned int
  ... truncated ...
```
