# sub_18018ECEC

- ea: `0x18018ecec`
- end: `0x18018f180`
- name: `sub_18018ECEC`
- size: `1172`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801879a4`

## callees

- `0x180001f48`
- `0x18000222c`
- `0x180057e60`
- `0x18008f7e8`
- `0x1800acb00`
- `0x1800da304`
- `0x1800ea664`
- `0x180116084`
- `0x18018ecec`
- `0x180271a30`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18018efd2`
- `KERNEL32!WriteFile` at `0x18018efd2`
- `KERNEL32!SetFileTime` at `0x18018f040`
- `KERNEL32!SetFileTime` at `0x18018f040`
- `KERNEL32!GetFileTime` at `0x18018eec5`
- `KERNEL32!GetFileTime` at `0x18018eec5`
- `KERNEL32!GetLastError` at `0x18018ee20`
- `KERNEL32!GetLastError` at `0x18018ef3e`
- `KERNEL32!GetLastError` at `0x18018f0c6`
- `KERNEL32!GetLastError` at `0x18018ee20`
- `KERNEL32!GetLastError` at `0x18018ef3e`
- `KERNEL32!GetLastError` at `0x18018f0c6`
- `KERNEL32!CreateFileW` at `0x18018ede2`
- `KERNEL32!CreateFileW` at `0x18018ef2f`
- `KERNEL32!CreateFileW` at `0x18018ede2`
- `KERNEL32!CreateFileW` at `0x18018ef2f`
- `KERNEL32!CloseHandle` at `0x18018eef3`
- `KERNEL32!CloseHandle` at `0x18018f069`
- `KERNEL32!CloseHandle` at `0x18018f07d`
- `KERNEL32!CloseHandle` at `0x18018f09b`
- `KERNEL32!CloseHandle` at `0x18018f0af`
- `KERNEL32!CloseHandle` at `0x18018f137`
- `KERNEL32!CloseHandle` at `0x18018f14b`
- `KERNEL32!CloseHandle` at `0x18018eef3`
- `KERNEL32!CloseHandle` at `0x18018f069`
- `KERNEL32!CloseHandle` at `0x18018f07d`
- `KERNEL32!CloseHandle` at `0x18018f09b`
- `KERNEL32!CloseHandle` at `0x18018f0af`
- `KERNEL32!CloseHandle` at `0x18018f137`
- `KERNEL32!CloseHandle` at `0x18018f14b`
- `SHLWAPI!PathFileExistsW` at `0x18018ee16`
- `SHLWAPI!PathFileExistsW` at `0x18018ee16`

## string_xrefs

- `0x18018ed3c`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\rw_ads.cpp`
- `0x18018eed3`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\rw_ads.cpp`
- `0x18018f04e`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\rw_ads.cpp`
- `0x18018f0fa`: `Failed to write Dlp Info metadata to ADS file`
- `0x18018ef72`: `Failed to create ADS file`

## pseudocode

```c
__int64 __fastcall sub_18018ECEC(_QWORD *a1, __int64 a2, const void *a3, DWORD a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v10; // rax
  __int64 v11; // rax
  char *FileW; // rbx
  __int64 v13; // rax
  signed int LastError; // eax
  _DWORD *v15; // rdi
  _QWORD *v16; // rax
  unsigned int v17; // edi
  bool v18; // cc
  const WCHAR *v19; // rcx
  HANDLE v20; // rax
  void *v21; // rdi
  signed int v22; // eax
  _DWORD *v23; // rax
  LPCWSTR *v24; // rcx
  _DWORD *v25; // rax
  LPCWSTR *v26; // rcx
  unsigned int v27; // esi
  signed int v28; // eax
  unsigned int v29; // esi
  _DWORD *v30; // rax
  LPCWSTR *v31; // rcx
  __int64 v32; // [rsp+40h] [rbp-29h] BYREF
  __int64 v33; // [rsp+48h] [rbp-21h] BYREF
  __int64 v34; // [rsp+50h] [rbp-19h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v37; // [rsp+78h] [rbp+Fh]
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+17h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+88h] [rbp+1Fh] BYREF
  struct _FILETIME CreationTime; // [rsp+90h] [rbp+27h] BYREF
  void *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( !*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1) + 16) )
  {
    v7 = 99;
LABEL_3:
    v8 = -2147024809;
    sub_1800DA304(retaddr, v7, "src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\rw_ads.cpp", 2147942487LL);
    return v8;
  }
  if ( !qword_18034BC88 )
  {
    v7 = 100;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v7 = 101;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v7 = 102;
    goto LABEL_3;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  sub_1800ACB00(lpFileName, v10, qword_18034BC78);
  v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  if ( *(_QWORD *)(v11 + 24) > 7u )
    v11 = *(_QWORD *)v11;
  FileW = (char *)CreateFileW((LPCWSTR)v11, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v33 = (__int64)FileW;
  if ( FileW == (char *)-1LL )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    if ( *(_QWORD *)(v13 + 24) > 7u )
      v13 = *(_QWORD *)v13;
    if ( !PathFileExistsW((LPCWSTR)v13) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v15 = (_DWORD *)sub_180116084();
      if ( *v15 > 3u )
      {
        LODWORD(v32) = v8;
        v16 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
        if ( v16[3] > 7u )
          v16 = (_QWORD *)*v16;
        v34 = (__int64)v16;
        v33 = (__int64)L"Not writing ADS since file doesn't exist";
        sub_18000222C((int)v15, (int)&byte_1803010B1, (__int64)&v33, (__int64)&v34, (__int64)&v32);
      }
LABEL_51:
      sub_18008F7E8(lpFileName);
      return v8;
    }
  }
  CreationTime = 0;
  LastAccessTime = 0;
  LastWriteTime = 0;
  if ( !GetFileTime(FileW, &CreationTime, &LastAccessTime, &LastWriteTime) )
  {
    v17 = sub_1800EA664(retaddr, 136, "src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\rw_ads.cpp");
    v18 = (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_26:
    if ( v18 )
      CloseHandle(FileW);
    v8 = v17;
    goto LABEL_51;
  }
  v19 = (const WCHAR *)lpFileName;
  if ( v37 > 7 )
    v19 = lpFileName[0];
  v20 = CreateFileW(v19, 0x40000000u, 7u, 0, 2u, 0x80u, 0);
  v21 = v20;
  if ( v20 == (HANDLE)-1LL )
  {
    v22 = GetLastError();
    v17 = v22;
    if ( v22 > 0 )
      v17 = (unsigned __int16)v22 | 0x80070000;
    v23 = (_DWORD *)sub_180116084();
    if ( *v23 > 3u )
    {
      LODWORD(v32) = v17;
      v24 = lpFileName;
      if ( v37 > 7 )
        v24 = (LPCWSTR *)lpFileName[0];
      v33 = (__int64)v24;
      v34 = (__int64)L"Failed to create ADS file";
      sub_18000222C((int)v23, (int)&byte_180301135, (__int64)&v34, (__int64)&v33, (__int64)&v32);
    }
    v18 = (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
    goto LABEL_26;
  }
  NumberOfBytesWritten = 0;
  if ( WriteFile(v20, a3, a4, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == a4 )
  {
    v25 = (_DWORD *)sub_180116084();
    if ( *v25 > 5u )
    {
      v26 = lpFileName;
      if ( v37 > 7 )
        v26 = (LPCWSTR *)lpFileName[0];
      v33 = (__int64)v26;
      v34 = (__int64)L"Successfully wrote DlpInfo data to ADS file";
      sub_180001F48((int)v25, (int)&word_1803011F6, (__int64)&v34, (__int64)&v33);
    }
    if ( !SetFileTime(v21, &CreationTime, &LastAccessTime, &LastWriteTime) )
    {
      v27 = sub_1800EA664(retaddr, 177, "src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\rw_ads.cpp");
      if ( v21 )
        CloseHandle(v21);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      v8 = v27;
      goto LABEL_51;
    }
    if ( v21 )
      CloseHandle(v21);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    sub_18008F7E8(lpFileName);
    return 0;
  }
  else
  {
    v28 = GetLastError();
    v29 = v28;
    if ( v28 > 0 )
      v29 = (unsigned __int16)v28 | 0x80070000;
    v30 = (_DWORD *)sub_180116084();
    if ( *v30 > 3u )
    {
      LODWORD(v32) = v29;
      v31 = lpFileName;
      if ( v37 > 7 )
        v31 = (LPCWSTR *)lpFileName[0];
      v33 = (__int64)v31;
      v34 = (__int64)L"Failed to write Dlp Info metadata to ADS file";
      sub_18000222C((int)v30, (int)&byte_18030122F, (__int64)&v34, (__int64)&v33, (__int64)&v32);
    }
    if ( v21 )
      CloseHandle(v21);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    sub_18008F7E8(lpFileName);
    return v29;
  }
}

```

## disassembly

```asm
0x18018ecec  mov     [rsp-8+arg_8], rbx
0x18018ecf1  push    rbp
0x18018ecf2  push    rsi
0x18018ecf3  push    rdi
0x18018ecf4  push    r14
0x18018ecf6  push    r15
0x18018ecf8  lea     rbp, [rsp-37h]
0x18018ecfd  sub     rsp, 0A0h
0x18018ed04  mov     rax, cs:__security_cookie
0x18018ed0b  xor     rax, rsp
0x18018ed0e  mov     [rbp+57h+var_28], rax
0x18018ed12  mov     esi, r9d
0x18018ed15  mov     r15, r8
0x18018ed18  mov     r14, rcx
0x18018ed1b  mov     rcx, [rcx]
0x18018ed1e  mov     rax, [rcx]
0x18018ed21  mov     rax, [rax+10h]
0x18018ed25  call    cs:__guard_dispatch_icall_fptr
0x18018ed2b  cmp     qword ptr [rax+10h], 0
0x18018ed30  jnz     short loc_18018ED56
0x18018ed32  mov     edx, 63h ; 'c'
0x18018ed37  mov     ebx, 80070057h
0x18018ed3c  lea     r8, aSrcEppDlpFilem_5; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x18018ed43  mov     r9d, ebx
0x18018ed46  mov     rcx, [rbp+5Fh]
0x18018ed4a  call    sub_1800DA304
0x18018ed4f  mov     eax, ebx
0x18018ed51  jmp     loc_18018F15D
0x18018ed56  cmp     cs:qword_18034BC88, 0
0x18018ed5e  jnz     short loc_18018ED67
0x18018ed60  mov     edx, 64h ; 'd'
0x18018ed65  jmp     short loc_18018ED37
0x18018ed67  test    r15, r15
0x18018ed6a  jnz     short loc_18018ED72
0x18018ed6c  lea     edx, [r15+65h]
0x18018ed70  jmp     short loc_18018ED37
0x18018ed72  test    esi, esi
0x18018ed74  jnz     short loc_18018ED7B
0x18018ed76  lea     edx, [rsi+66h]
0x18018ed79  jmp     short loc_18018ED37
0x18018ed7b  mov     rcx, [r14]
0x18018ed7e  mov     rax, [rcx]
0x18018ed81  mov     rax, [rax+10h]
0x18018ed85  call    cs:__guard_dispatch_icall_fptr
0x18018ed8b  lea     r8, qword_18034BC78
0x18018ed92  mov     rdx, rax
0x18018ed95  lea     rcx, [rbp+57h+lpFileName]
0x18018ed99  call    sub_1800ACB00
0x18018ed9e  nop
0x18018ed9f  mov     rcx, [r14]
0x18018eda2  mov     rax, [rcx]
0x18018eda5  mov     rax, [rax+10h]
0x18018eda9  call    cs:__guard_dispatch_icall_fptr
0x18018edaf  cmp     qword ptr [rax+18h], 7
0x18018edb4  jbe     short loc_18018EDB9
0x18018edb6  mov     rax, [rax]
0x18018edb9  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18018edc2  mov     edi, 80h
0x18018edc7  mov     [rsp+0C0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18018edcb  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18018edd3  xor     r9d, r9d; lpSecurityAttributes
0x18018edd6  mov     edx, 80000000h; dwDesiredAccess
0x18018eddb  lea     r8d, [rdi-7Dh]; dwShareMode
0x18018eddf  mov     rcx, rax; lpFileName
0x18018ede2  call    cs:CreateFileW
0x18018ede8  mov     rbx, rax
0x18018edeb  mov     [rbp+57h+var_78], rax
0x18018edef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018edf3  jnz     loc_18018EE9E
0x18018edf9  mov     rcx, [r14]
0x18018edfc  mov     rax, [rcx]
0x18018edff  mov     rax, [rax+10h]
0x18018ee03  call    cs:__guard_dispatch_icall_fptr
0x18018ee09  cmp     qword ptr [rax+18h], 7
0x18018ee0e  jbe     short loc_18018EE13
0x18018ee10  mov     rax, [rax]
0x18018ee13  mov     rcx, rax; pszPath
0x18018ee16  call    cs:PathFileExistsW
0x18018ee1c  test    eax, eax
0x18018ee1e  jnz     short loc_18018EE9E
0x18018ee20  call    cs:GetLastError
0x18018ee26  mov     ebx, eax
0x18018ee28  test    eax, eax
0x18018ee2a  jle     short loc_18018EE35
0x18018ee2c  movzx   ebx, ax
0x18018ee2f  or      ebx, 80070000h
0x18018ee35  call    sub_180116084
0x18018ee3a  mov     rdi, rax
0x18018ee3d  cmp     dword ptr [rax], 3
0x18018ee40  jbe     short loc_18018EE99
0x18018ee42  mov     dword ptr [rbp+57h+var_80], ebx
0x18018ee45  mov     rcx, [r14]
0x18018ee48  mov     rdx, [rcx]
0x18018ee4b  mov     rax, [rdx+10h]
0x18018ee4f  call    cs:__guard_dispatch_icall_fptr
0x18018ee55  cmp     qword ptr [rax+18h], 7
0x18018ee5a  jbe     short loc_18018EE5F
0x18018ee5c  mov     rax, [rax]
0x18018ee5f  mov     [rbp+57h+var_70], rax
0x18018ee63  lea     rax, aNotWritingAdsS; "Not writing ADS since file doesn't exis"...
0x18018ee6a  mov     [rbp+57h+var_78], rax
0x18018ee6e  lea     rax, [rbp+57h+var_80]
0x18018ee72  mov     [rsp+0C0h+hTemplateFile], rax; __int64
0x18018ee77  lea     rax, [rbp+57h+var_70]
0x18018ee7b  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax; __int64
0x18018ee80  lea     rax, [rbp+57h+var_78]
0x18018ee84  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; __int64
0x18018ee89  lea     rdx, byte_1803010B1; int
0x18018ee90  mov     rcx, rdi; int
0x18018ee93  call    sub_18000222C
0x18018ee98  nop
0x18018ee99  jmp     loc_18018F085
0x18018ee9e  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], 0
0x18018eea6  mov     qword ptr [rbp+57h+LastAccessTime.dwLowDateTime], 0
0x18018eeae  mov     qword ptr [rbp+57h+LastWriteTime.dwLowDateTime], 0
0x18018eeb6  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x18018eeba  lea     r8, [rbp+57h+LastAccessTime]; lpLastAccessTime
0x18018eebe  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x18018eec2  mov     rcx, rbx; hFile
0x18018eec5  call    cs:GetFileTime
0x18018eecb  test    eax, eax
0x18018eecd  jnz     short loc_18018EF00
0x18018eecf  mov     rcx, [rbp+5Fh]
0x18018eed3  lea     r8, aSrcEppDlpFilem_5; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x18018eeda  mov     edx, 88h
0x18018eedf  call    sub_1800EA664
0x18018eee4  mov     edi, eax
0x18018eee6  lea     rcx, [rbx-1]
0x18018eeea  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18018eeee  ja      short loc_18018EEF9
0x18018eef0  mov     rcx, rbx; hObject
0x18018eef3  call    cs:CloseHandle
0x18018eef9  mov     ebx, edi
0x18018eefb  jmp     loc_18018F085
0x18018ef00  lea     rcx, [rbp+57h+lpFileName]
0x18018ef04  cmp     [rbp+57h+var_48], 7
0x18018ef09  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18018ef0e  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18018ef17  mov     [rsp+0C0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18018ef1b  mov     [rsp+0C0h+dwCreationDisposition], 2; dwCreationDisposition
0x18018ef23  xor     r9d, r9d; lpSecurityAttributes
0x18018ef26  mov     edx, 40000000h; dwDesiredAccess
0x18018ef2b  lea     r8d, [r9+7]; dwShareMode
0x18018ef2f  call    cs:CreateFileW
0x18018ef35  mov     rdi, rax
0x18018ef38  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018ef3c  jnz     short loc_18018EFB5
0x18018ef3e  call    cs:GetLastError
0x18018ef44  mov     edi, eax
0x18018ef46  test    eax, eax
0x18018ef48  jle     short loc_18018EF53
0x18018ef4a  movzx   edi, ax
0x18018ef4d  or      edi, 80070000h
0x18018ef53  call    sub_180116084
0x18018ef58  cmp     dword ptr [rax], 3
0x18018ef5b  jbe     short loc_18018EFA8
0x18018ef5d  mov     dword ptr [rbp+57h+var_80], edi
0x18018ef60  lea     rcx, [rbp+57h+lpFileName]
0x18018ef64  cmp     [rbp+57h+var_48], 7
0x18018ef69  cmova   rcx, [rbp+57h+lpFileName]
0x18018ef6e  mov     [rbp+57h+var_78], rcx
0x18018ef72  lea     rcx, aFailedToCreate_0; "Failed to create ADS file"
0x18018ef79  mov     [rbp+57h+var_70], rcx
0x18018ef7d  lea     rcx, [rbp+57h+var_80]
0x18018ef81  mov     [rsp+0C0h+hTemplateFile], rcx; __int64
0x18018ef86  lea     rcx, [rbp+57h+var_78]
0x18018ef8a  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rcx; __int64
0x18018ef8f  lea     rcx, [rbp+57h+var_70]
0x18018ef93  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx; __int64
0x18018ef98  lea     rdx, byte_180301135; int
0x18018ef9f  mov     rcx, rax; int
0x18018efa2  call    sub_18000222C
0x18018efa7  nop
0x18018efa8  lea     rax, [rbx-1]
0x18018efac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18018efb0  jmp     loc_18018EEEE
0x18018efb5  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18018efbc  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOverlapped
0x18018efc5  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18018efc9  mov     r8d, esi; nNumberOfBytesToWrite
0x18018efcc  mov     rdx, r15; lpBuffer
0x18018efcf  mov     rcx, rdi; hFile
0x18018efd2  call    cs:WriteFile
0x18018efd8  test    eax, eax
0x18018efda  jz      loc_18018F0C6
0x18018efe0  cmp     [rbp+57h+NumberOfBytesWritten], esi
0x18018efe3  jnz     loc_18018F0C6
0x18018efe9  call    sub_180116084
0x18018efee  cmp     dword ptr [rax], 5
0x18018eff1  jbe     short loc_18018F031
0x18018eff3  lea     rcx, [rbp+57h+lpFileName]
0x18018eff7  cmp     [rbp+57h+var_48], 7
0x18018effc  cmova   rcx, [rbp+57h+lpFileName]
0x18018f001  mov     [rbp+57h+var_78], rcx
0x18018f005  lea     rcx, aSuccessfullyWr; "Successfully wrote DlpInfo data to ADS "...
0x18018f00c  mov     [rbp+57h+var_70], rcx
0x18018f010  lea     rcx, [rbp+57h+var_78]
0x18018f014  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rcx; __int64
0x18018f019  lea     rcx, [rbp+57h+var_70]
0x18018f01d  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx; __int64
0x18018f022  lea     rdx, word_1803011F6; int
0x18018f029  mov     rcx, rax; int
0x18018f02c  call    sub_180001F48
0x18018f031  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x18018f035  lea     r8, [rbp+57h+LastAccessTime]; lpLastAccessTime
0x18018f039  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x18018f03d  mov     rcx, rdi; hFile
0x18018f040  call    cs:SetFileTime
0x18018f046  test    eax, eax
0x18018f048  jnz     short loc_18018F093
0x18018f04a  mov     rcx, [rbp+5Fh]
0x18018f04e  lea     r8, aSrcEppDlpFilem_5; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x18018f055  mov     edx, 0B1h
0x18018f05a  call    sub_1800EA664
0x18018f05f  mov     esi, eax
0x18018f061  test    rdi, rdi
0x18018f064  jz      short loc_18018F070
0x18018f066  mov     rcx, rdi; hObject
0x18018f069  call    cs:CloseHandle
0x18018f06f  nop
0x18018f070  lea     rcx, [rbx-1]
0x18018f074  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18018f078  ja      short loc_18018F083
0x18018f07a  mov     rcx, rbx; hObject
0x18018f07d  call    cs:CloseHandle
0x18018f083  mov     ebx, esi
0x18018f085  lea     rcx, [rbp+57h+lpFileName]
0x18018f089  call    sub_18008F7E8
0x18018f08e  jmp     loc_18018ED4F
0x18018f093  test    rdi, rdi
0x18018f096  jz      short loc_18018F0A2
0x18018f098  mov     rcx, rdi; hObject
0x18018f09b  call    cs:CloseHandle
0x18018f0a1  nop
0x18018f0a2  lea     rax, [rbx-1]
0x18018f0a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18018f0aa  ja      short loc_18018F0B6
0x18018f0ac  mov     rcx, rbx; hObject
0x18018f0af  call    cs:CloseHandle
0x18018f0b5  nop
0x18018f0b6  lea     rcx, [rbp+57h+lpFileName]
0x18018f0ba  call    sub_18008F7E8
0x18018f0bf  xor     eax, eax
0x18018f0c1  jmp     loc_18018F15D
0x18018f0c6  call    cs:GetLastError
0x18018f0cc  mov     esi, eax
0x18018f0ce  test    eax, eax
0x18018f0d0  jle     short loc_18018F0DB
0x18018f0d2  movzx   esi, ax
0x18018f0d5  or      esi, 80070000h
0x18018f0db  call    sub_180116084
0x18018f0e0  cmp     dword ptr [rax], 3
0x18018f0e3  jbe     short loc_18018F12F
0x18018f0e5  mov     dword ptr [rbp+57h+var_80], esi
0x18018f0e8  lea     rcx, [rbp+57h+lpFileName]
0x18018f0ec  cmp     [rbp+57h+var_48], 7
0x18018f0f1  cmova   rcx, [rbp+57h+lpFileName]
0x18018f0f6  mov     [rbp+57h+var_78], rcx
0x18018f0fa  lea     rcx, aFailedToWriteD; "Failed to write Dlp Info metadata to AD"...
0x18018f101  mov     [rbp+57h+var_70], rcx
0x18018f105  lea     rcx, [rbp+57h+var_80]
0x18018f109  mov     [rsp+0C0h+hTemplateFile], rcx; __int64
0x18018f10e  lea     rcx, [rbp+57h+var_78]
0x18018f112  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rcx; __int64
0x18018f117  lea     rcx, [rbp+57h+var_70]
0x18018f11b  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx; __int64
0x18018f120  lea     rdx, byte_18030122F; int
0x18018f127  mov     rcx, rax; int
0x18018f12a  call    sub_18000222C
0x18018f12f  test    rdi, rdi
0x18018f132  jz      short loc_18018F13E
0x18018f134  mov     rcx, rdi; hObject
0x18018f137  call    cs:CloseHandle
0x18018f13d  nop
0x18018f13e  lea     rcx, [rbx-1]
0x18018f142  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18018f146  ja      short loc_18018F152
0x18018f148  mov     rcx, rbx; hObject
0x18018f14b  call    cs:CloseHandle
0x18018f151  nop
0x18018f152  lea     rcx, [rbp+57h+lpFileName]
0x18018f156  call    sub_18008F7E8
0x18018f15b  mov     eax, esi
0x18018f15d  mov     rcx, [rbp+57h+var_28]
0x18018f161  xor     rcx, rsp; StackCookie
0x18018f164  call    __security_check_cookie
0x18018f169  mov     rbx, [rsp+0C0h+arg_8]
0x18018f171  add     rsp, 0A0h
0x18018f178  pop     r15
0x18018f17a  pop     r14
0x18018f17c  pop     rdi
0x18018f17d  pop     rsi
0x18018f17e  pop     rbp
0x18018f17f  retn
```
