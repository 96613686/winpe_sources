# archive_read_disk_entry_from_file

- ea: `0x1800bd620`
- end: `0x1800bda4f`
- name: `archive_read_disk_entry_from_file`
- size: `1071`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, reparse_path, installer_update`

## callees

- `0x180006c00`
- `0x180007c80`
- `0x18000e0e4`
- `0x1800149c0`
- `0x180014fc0`
- `0x180015810`
- `0x1800b1ce0`
- `0x1800b2730`
- `0x1800b2de0`
- `0x1800bd620`
- `0x1800bda60`
- `0x1800be020`
- `0x1800be1a4`
- `0x1800be410`
- `0x1800befa8`
- `0x1800ece24`
- `0x1800ef3f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd6f3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd74a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd7e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd813`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd9ab`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd6f3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd74a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd7e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd813`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bd9ab`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x1800bd6cb`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x1800bd935`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x1800bd6cb`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x1800bd935`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800bd731`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800bd731`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800bd75c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800bd75c`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bd6dc`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bd7fc`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bd994`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bd6dc`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bd7fc`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bd994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd6e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd73d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd7d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd6e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd73d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd7d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd99e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800bd7c6`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800bd979`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800bd7c6`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800bd979`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd82d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bda0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bda24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd82d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bda0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bda24`

## string_xrefs

- `0x1800bd693`: `Can't get a wide character version of the path`
- `0x1800bd7e8`: `Can't CreateFileW`

## pseudocode

```c
__int64 __fastcall archive_read_disk_entry_from_file(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  const WCHAR *v8; // rax
  const char *v9; // r8
  __int64 v10; // rdx
  const WCHAR *v12; // r13
  intptr_t osfhandle; // rbx
  DWORD v14; // eax
  unsigned int *v15; // rax
  struct _WIN32_FIND_DATAW *p_FindFileData; // r8
  HANDLE FirstFileW; // rax
  DWORD LastError; // eax
  int v19; // ecx
  __int64 v20; // rdx
  void *v21; // rax
  DWORD v22; // eax
  DWORD v23; // eax
  unsigned int *v24; // rax
  __int16 dwFileAttributes; // r15
  __int64 disk_uname; // rax
  __int64 disk_gname; // rax
  DWORD v28; // eax
  unsigned int *v29; // rax
  unsigned int v30; // r15d
  __int128 v31; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v32; // [rsp+40h] [rbp-C0h]
  _OWORD v33[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF

  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v8 = (const WCHAR *)archive_entry_sourcepath_w(a2);
  if ( !v8 )
  {
    v8 = (const WCHAR *)archive_entry_pathname_w(a2);
    if ( !v8 )
    {
      v9 = "Can't get a wide character version of the path";
      v10 = 22;
LABEL_4:
      archive_set_error(a1, v10, v9);
      return 4294967271LL;
    }
  }
  v12 = (const WCHAR *)_la_win_permissive_name_w(v8);
  if ( a4 )
  {
    dwFileAttributes = 0;
    archive_entry_copy_stat(a2, a4);
    if ( (*(_WORD *)(a4 + 6) & 0xA000) != 0 )
      entry_symlink_from_pathw(a2, v12);
    osfhandle = -1;
  }
  else
  {
    if ( a3 < 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      v31 = 0;
      v32 = 0;
      FirstFileW = FindFirstFileW(v12, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        _la_dosmaperr(LastError);
        v15 = (unsigned int *)_o__errno();
        v9 = "Can't FindFirstFileW";
        goto LABEL_10;
      }
      FindClose(FirstFileW);
      if ( !*(_BYTE *)(a1 + 153)
        && (FindFileData.dwFileAttributes & 0x400) != 0
        && FindFileData.dwReserved0 == -1610612724 )
      {
        v19 = 35651584;
        v20 = 0;
      }
      else
      {
        v19 = 0x2000000;
        v20 = (unsigned __int8)(~LOBYTE(FindFileData.dwFileAttributes) & 0xF0) << 27;
      }
      v31 = 0;
      DWORD2(v31) = v19;
      LODWORD(v31) = 32;
      v32 = 0;
      v21 = (void *)CreateFile2(v12, v20, 7, 3, &v31);
      osfhandle = (intptr_t)v21;
      if ( v21 == (void *)-1LL )
        goto LABEL_20;
      if ( !GetFileInformationByHandle(v21, &FileInformation) )
      {
        v23 = GetLastError();
        _la_dosmaperr(v23);
        v24 = (unsigned int *)_o__errno();
        archive_set_error(a1, *v24, "Can't GetFileInformationByHandle");
LABEL_23:
        CloseHandle((HANDLE)osfhandle);
        return 4294967271LL;
      }
      p_FindFileData = &FindFileData;
    }
    else
    {
      osfhandle = _get_osfhandle(a3);
      if ( !GetFileInformationByHandle((HANDLE)osfhandle, &FileInformation) )
      {
        v14 = GetLastError();
        _la_dosmaperr(v14);
        v15 = (unsigned int *)_o__errno();
        v9 = "Can't GetFileInformationByHandle";
LABEL_10:
        v10 = *v15;
        goto LABEL_4;
      }
      p_FindFileData = 0;
    }
    entry_copy_bhfi(a2, v12, p_FindFileData, &FileInformation);
    dwFileAttributes = FileInformation.dwFileAttributes;
  }
  disk_uname = archive_read_disk_uname(a1, *(_QWORD *)(a2 + 120));
  if ( disk_uname )
    archive_mstring_copy_mbs(a2 + 592, disk_uname);
  disk_gname = archive_read_disk_gname(a1, *(_QWORD *)(a2 + 88));
  if ( disk_gname )
    archive_mstring_copy_mbs(a2 + 280, disk_gname);
  if ( (*(_BYTE *)(a1 + 192) & 0x40) == 0 && (dwFileAttributes & 7) != 0 )
  {
    archive_mstring_clean(a2 + 168);
    *(_DWORD *)(a2 + 272) = dwFileAttributes & 7;
    *(_DWORD *)(a2 + 276) = 0;
  }
  if ( (*(_WORD *)(a2 + 1032) & 0xF000) != 0x8000 || *(__int64 *)(a2 + 112) <= 0 || archive_entry_hardlink(a2) )
  {
    if ( osfhandle == -1 )
      return 0;
LABEL_54:
    if ( a3 < 0 )
      CloseHandle((HANDLE)osfhandle);
    return 0;
  }
  if ( osfhandle == -1 )
  {
    if ( a3 >= 0 )
    {
      osfhandle = _get_osfhandle(a3);
LABEL_43:
      if ( !GetFileInformationByHandle((HANDLE)osfhandle, &FileInformation) )
      {
        v28 = GetLastError();
        _la_dosmaperr(v28);
        v29 = (unsigned int *)_o__errno();
        archive_set_error(a1, *v29, "Can't GetFileInformationByHandle");
        if ( osfhandle == -1 || a3 >= 0 )
          return 4294967271LL;
        goto LABEL_23;
      }
      dwFileAttributes = FileInformation.dwFileAttributes;
      goto LABEL_48;
    }
    memset(v33, 0, sizeof(v33));
    LODWORD(v33[0]) = 32;
    DWORD2(v33[0]) = 0x2000000;
    osfhandle = CreateFile2(v12, 0x80000000LL, 7, 3, v33);
    if ( osfhandle != -1 )
      goto LABEL_43;
LABEL_20:
    v22 = GetLastError();
    _la_dosmaperr(v22);
    v15 = (unsigned int *)_o__errno();
    v9 = "Can't CreateFileW";
    goto LABEL_10;
  }
LABEL_48:
  if ( (dwFileAttributes & 0x200) == 0 )
    goto LABEL_54;
  v30 = 0;
  if ( *(char *)(a1 + 192) >= 0 )
  {
    v30 = setup_sparse_from_disk(a1, a2, osfhandle);
    if ( a3 < 0 )
      CloseHandle((HANDLE)osfhandle);
  }
  return v30;
}

```

## disassembly

```asm
0x1800bd620  push    rbp
0x1800bd622  push    rbx
0x1800bd623  push    rsi
0x1800bd624  push    rdi
0x1800bd625  push    r12
0x1800bd627  push    r13
0x1800bd629  push    r14
0x1800bd62b  push    r15
0x1800bd62d  lea     rbp, [rsp-218h]
0x1800bd635  sub     rsp, 318h
0x1800bd63c  mov     rax, cs:__security_cookie
0x1800bd643  xor     rax, rsp
0x1800bd646  mov     [rbp+250h+var_50], rax
0x1800bd64d  xor     eax, eax
0x1800bd64f  xorps   xmm0, xmm0
0x1800bd652  mov     [rcx+38h], rax
0x1800bd656  mov     rdi, rcx
0x1800bd659  mov     [rcx+28h], rax
0x1800bd65d  mov     rbx, r9
0x1800bd660  mov     [rcx+24h], eax
0x1800bd663  mov     r14d, r8d
0x1800bd666  mov     rcx, rdx
0x1800bd669  mov     [rbp+250h+FileInformation.nFileIndexLow], eax
0x1800bd66c  mov     rsi, rdx
0x1800bd66f  movups  xmmword ptr [rsp+350h+FileInformation.dwFileAttributes], xmm0
0x1800bd674  movups  xmmword ptr [rbp+250h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800bd678  movups  xmmword ptr [rbp+250h+FileInformation.nFileSizeHigh], xmm0
0x1800bd67c  call    archive_entry_sourcepath_w
0x1800bd681  test    rax, rax
0x1800bd684  jnz     short loc_1800BD6AF
0x1800bd686  mov     rcx, rsi
0x1800bd689  call    archive_entry_pathname_w
0x1800bd68e  test    rax, rax
0x1800bd691  jnz     short loc_1800BD6AF
0x1800bd693  lea     r8, aCanTGetAWideCh; "Can't get a wide character version of t"...
0x1800bd69a  lea     edx, [rax+16h]
0x1800bd69d  mov     rcx, rdi
0x1800bd6a0  call    archive_set_error
0x1800bd6a5  mov     eax, 0FFFFFFE7h
0x1800bd6aa  jmp     loc_1800BDA2C
0x1800bd6af  mov     rcx, rax; lpFileName
0x1800bd6b2  call    __la_win_permissive_name_w
0x1800bd6b7  mov     r13, rax
0x1800bd6ba  test    rbx, rbx
0x1800bd6bd  jnz     loc_1800BD853
0x1800bd6c3  test    r14d, r14d
0x1800bd6c6  js      short loc_1800BD70C
0x1800bd6c8  mov     ecx, r14d; FileHandle
0x1800bd6cb  call    cs:__imp__get_osfhandle
0x1800bd6d1  mov     rcx, rax; hFile
0x1800bd6d4  lea     rdx, [rsp+350h+FileInformation]; lpFileInformation
0x1800bd6d9  mov     rbx, rax
0x1800bd6dc  call    cs:__imp_GetFileInformationByHandle
0x1800bd6e2  test    eax, eax
0x1800bd6e4  jnz     short loc_1800BD704
0x1800bd6e6  call    cs:__imp_GetLastError
0x1800bd6ec  mov     ecx, eax
0x1800bd6ee  call    __la_dosmaperr
0x1800bd6f3  call    cs:__imp__o__errno
0x1800bd6f9  lea     r8, aCanTGetfileinf; "Can't GetFileInformationByHandle"
0x1800bd700  mov     edx, [rax]
0x1800bd702  jmp     short loc_1800BD69D
0x1800bd704  xor     r8d, r8d
0x1800bd707  jmp     loc_1800BD83C
0x1800bd70c  xor     edx, edx; Val
0x1800bd70e  lea     rcx, [rbp+250h+FindFileData]; void *
0x1800bd712  mov     r8d, 250h; Size
0x1800bd718  call    memset_0
0x1800bd71d  xorps   xmm0, xmm0
0x1800bd720  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x1800bd724  mov     rcx, r13; lpFileName
0x1800bd727  movups  [rsp+350h+var_320], xmm0
0x1800bd72c  movups  [rsp+350h+var_310], xmm0
0x1800bd731  call    cs:__imp_FindFirstFileW
0x1800bd737  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bd73b  jnz     short loc_1800BD759
0x1800bd73d  call    cs:__imp_GetLastError
0x1800bd743  mov     ecx, eax
0x1800bd745  call    __la_dosmaperr
0x1800bd74a  call    cs:__imp__o__errno
0x1800bd750  lea     r8, aCanTFindfirstf; "Can't FindFirstFileW"
0x1800bd757  jmp     short loc_1800BD700
0x1800bd759  mov     rcx, rax; hFindFile
0x1800bd75c  call    cs:__imp_FindClose
0x1800bd762  cmp     byte ptr [rdi+99h], 0
0x1800bd769  mov     eax, [rbp+250h+FindFileData.dwFileAttributes]
0x1800bd76c  jnz     short loc_1800BD786
0x1800bd76e  bt      eax, 0Ah
0x1800bd772  jnb     short loc_1800BD786
0x1800bd774  cmp     [rbp+250h+FindFileData.dwReserved0], 0A000000Ch
0x1800bd77b  jnz     short loc_1800BD786
0x1800bd77d  mov     ecx, 2200000h
0x1800bd782  xor     edx, edx
0x1800bd784  jmp     short loc_1800BD796
0x1800bd786  not     al
0x1800bd788  mov     ecx, 2000000h
0x1800bd78d  movzx   edx, al
0x1800bd790  and     edx, 0FFFFFFF0h
0x1800bd793  shl     edx, 1Bh
0x1800bd796  xorps   xmm0, xmm0
0x1800bd799  lea     rax, [rsp+350h+var_320]
0x1800bd79e  movups  [rsp+350h+var_320], xmm0
0x1800bd7a3  mov     r9d, 3
0x1800bd7a9  mov     dword ptr [rsp+350h+var_320+8], ecx
0x1800bd7ad  mov     rcx, r13
0x1800bd7b0  mov     dword ptr [rsp+350h+var_320], 20h ; ' '
0x1800bd7b8  movups  [rsp+350h+var_310], xmm0
0x1800bd7bd  mov     [rsp+350h+var_330], rax
0x1800bd7c2  lea     r8d, [r9+4]
0x1800bd7c6  call    cs:__imp_CreateFile2
0x1800bd7cc  mov     rbx, rax
0x1800bd7cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bd7d3  jnz     short loc_1800BD7F4
0x1800bd7d5  call    cs:__imp_GetLastError
0x1800bd7db  mov     ecx, eax
0x1800bd7dd  call    __la_dosmaperr
0x1800bd7e2  call    cs:__imp__o__errno
0x1800bd7e8  lea     r8, aCanTCreatefile; "Can't CreateFileW"
0x1800bd7ef  jmp     loc_1800BD700
0x1800bd7f4  lea     rdx, [rsp+350h+FileInformation]; lpFileInformation
0x1800bd7f9  mov     rcx, rbx; hFile
0x1800bd7fc  call    cs:__imp_GetFileInformationByHandle
0x1800bd802  test    eax, eax
0x1800bd804  jnz     short loc_1800BD838
0x1800bd806  call    cs:__imp_GetLastError
0x1800bd80c  mov     ecx, eax
0x1800bd80e  call    __la_dosmaperr
0x1800bd813  call    cs:__imp__o__errno
0x1800bd819  lea     r8, aCanTGetfileinf; "Can't GetFileInformationByHandle"
0x1800bd820  mov     rcx, rdi
0x1800bd823  mov     edx, [rax]
0x1800bd825  call    archive_set_error
0x1800bd82a  mov     rcx, rbx; hObject
0x1800bd82d  call    cs:__imp_CloseHandle
0x1800bd833  jmp     loc_1800BD6A5
0x1800bd838  lea     r8, [rbp+250h+FindFileData]
0x1800bd83c  lea     r9, [rsp+350h+FileInformation]
0x1800bd841  mov     rdx, r13
0x1800bd844  mov     rcx, rsi
0x1800bd847  call    entry_copy_bhfi
0x1800bd84c  mov     r15d, [rsp+350h+FileInformation.dwFileAttributes]
0x1800bd851  jmp     short loc_1800BD87B
0x1800bd853  mov     rdx, rbx
0x1800bd856  mov     rcx, rsi
0x1800bd859  xor     r15d, r15d
0x1800bd85c  call    archive_entry_copy_stat
0x1800bd861  mov     eax, 0A000h
0x1800bd866  test    [rbx+6], ax
0x1800bd86a  jz      short loc_1800BD877
0x1800bd86c  mov     rdx, r13
0x1800bd86f  mov     rcx, rsi
0x1800bd872  call    entry_symlink_from_pathw
0x1800bd877  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bd87b  mov     rdx, [rsi+78h]
0x1800bd87f  mov     rcx, rdi
0x1800bd882  call    archive_read_disk_uname
0x1800bd887  test    rax, rax
0x1800bd88a  jz      short loc_1800BD89B
0x1800bd88c  lea     rcx, [rsi+250h]
0x1800bd893  mov     rdx, rax
0x1800bd896  call    archive_mstring_copy_mbs
0x1800bd89b  mov     rdx, [rsi+58h]
0x1800bd89f  mov     rcx, rdi
0x1800bd8a2  call    archive_read_disk_gname
0x1800bd8a7  test    rax, rax
0x1800bd8aa  jz      short loc_1800BD8BB
0x1800bd8ac  lea     rcx, [rsi+118h]
0x1800bd8b3  mov     rdx, rax
0x1800bd8b6  call    archive_mstring_copy_mbs
0x1800bd8bb  test    byte ptr [rdi+0C0h], 40h
0x1800bd8c2  jnz     short loc_1800BD8EA
0x1800bd8c4  mov     r12d, r15d
0x1800bd8c7  and     r12d, 7
0x1800bd8cb  jz      short loc_1800BD8EA
0x1800bd8cd  lea     rcx, [rsi+0A8h]
0x1800bd8d4  call    archive_mstring_clean
0x1800bd8d9  mov     [rsi+110h], r12d
0x1800bd8e0  mov     dword ptr [rsi+114h], 0
0x1800bd8ea  movzx   eax, word ptr [rsi+408h]
0x1800bd8f1  mov     ecx, 0F000h
0x1800bd8f6  and     ax, cx
0x1800bd8f9  mov     ecx, 8000h
0x1800bd8fe  cmp     ax, cx
0x1800bd901  jnz     loc_1800BDA16
0x1800bd907  cmp     qword ptr [rsi+70h], 0
0x1800bd90c  jle     loc_1800BDA16
0x1800bd912  mov     rcx, rsi
0x1800bd915  call    archive_entry_hardlink
0x1800bd91a  test    rax, rax
0x1800bd91d  jnz     loc_1800BDA16
0x1800bd923  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800bd927  jnz     loc_1800BD9DF
0x1800bd92d  test    r14d, r14d
0x1800bd930  js      short loc_1800BD940
0x1800bd932  mov     ecx, r14d; FileHandle
0x1800bd935  call    cs:__imp__get_osfhandle
0x1800bd93b  mov     rbx, rax
0x1800bd93e  jmp     short loc_1800BD98C
0x1800bd940  xorps   xmm0, xmm0
0x1800bd943  lea     rax, [rsp+350h+var_300]
0x1800bd948  movups  [rsp+350h+var_300], xmm0
0x1800bd94d  mov     r9d, 3
0x1800bd953  mov     dword ptr [rsp+350h+var_300], 20h ; ' '
0x1800bd95b  mov     edx, 80000000h
0x1800bd960  mov     dword ptr [rsp+350h+var_300+8], 2000000h
0x1800bd968  mov     rcx, r13
0x1800bd96b  mov     [rsp+350h+var_330], rax
0x1800bd970  movups  [rsp+350h+var_2F0], xmm0
0x1800bd975  lea     r8d, [r9+4]
0x1800bd979  call    cs:__imp_CreateFile2
0x1800bd97f  mov     rbx, rax
0x1800bd982  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bd986  jz      loc_1800BD7D5
0x1800bd98c  lea     rdx, [rsp+350h+FileInformation]; lpFileInformation
0x1800bd991  mov     rcx, rbx; hFile
0x1800bd994  call    cs:__imp_GetFileInformationByHandle
0x1800bd99a  test    eax, eax
0x1800bd99c  jnz     short loc_1800BD9DA
0x1800bd99e  call    cs:__imp_GetLastError
0x1800bd9a4  mov     ecx, eax
0x1800bd9a6  call    __la_dosmaperr
0x1800bd9ab  call    cs:__imp__o__errno
0x1800bd9b1  lea     r8, aCanTGetfileinf; "Can't GetFileInformationByHandle"
0x1800bd9b8  mov     rcx, rdi
0x1800bd9bb  mov     edx, [rax]
0x1800bd9bd  call    archive_set_error
0x1800bd9c2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800bd9c6  jz      loc_1800BD6A5
0x1800bd9cc  test    r14d, r14d
0x1800bd9cf  jns     loc_1800BD6A5
0x1800bd9d5  jmp     loc_1800BD82A
0x1800bd9da  mov     r15d, [rsp+350h+FileInformation.dwFileAttributes]
0x1800bd9df  bt      r15d, 9
0x1800bd9e4  jnb     short loc_1800BDA1C
0x1800bd9e6  xor     r15d, r15d
0x1800bd9e9  test    byte ptr [rdi+0C0h], 80h
0x1800bd9f0  jnz     short loc_1800BDA11
0x1800bd9f2  mov     r8, rbx
0x1800bd9f5  mov     rdx, rsi
0x1800bd9f8  mov     rcx, rdi
0x1800bd9fb  call    setup_sparse_from_disk
0x1800bda00  mov     r15d, eax
0x1800bda03  test    r14d, r14d
0x1800bda06  jns     short loc_1800BDA11
0x1800bda08  mov     rcx, rbx; hObject
0x1800bda0b  call    cs:__imp_CloseHandle
0x1800bda11  mov     eax, r15d
0x1800bda14  jmp     short loc_1800BDA2C
0x1800bda16  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800bda1a  jz      short loc_1800BDA2A
0x1800bda1c  test    r14d, r14d
0x1800bda1f  jns     short loc_1800BDA2A
0x1800bda21  mov     rcx, rbx; hObject
0x1800bda24  call    cs:__imp_CloseHandle
0x1800bda2a  xor     eax, eax
0x1800bda2c  mov     rcx, [rbp+250h+var_50]
0x1800bda33  xor     rcx, rsp; StackCookie
0x1800bda36  call    __security_check_cookie
0x1800bda3b  add     rsp, 318h
0x1800bda42  pop     r15
0x1800bda44  pop     r14
0x1800bda46  pop     r13
0x1800bda48  pop     r12
0x1800bda4a  pop     rdi
0x1800bda4b  pop     rsi
0x1800bda4c  pop     rbx
0x1800bda4d  pop     rbp
0x1800bda4e  retn
```
