# _GetVolumeGuidFileHandle(wchar_t const *,ulong,ulong,void * *)

- ea: `0x18020d95c`
- end: `0x18020db43`
- name: `?_GetVolumeGuidFileHandle@@YAJPEB_WKKPEAPEAX@Z`
- size: `487`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, DWORD dwDesiredAccess, DWORD dwCreationDisposition, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18020d5a0`

## callees

- `0x1800b827c`
- `0x18010839c`
- `0x18010b2b4`
- `0x1801244c0`
- `0x18012540e`
- `0x18020d95c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18020daeb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18020daeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020da0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020da0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18020daf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18020daf8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18020da04`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18020da04`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18020da5c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18020da5c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18020daa9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18020daa9`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x18020dac2`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x18020dac2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18020d9aa`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18020d9d2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18020d9aa`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18020d9d2`

## pseudocode

```c
__int64 __fastcall _GetVolumeGuidFileHandle(
        PCWSTR pszPathIn,
        DWORD dwDesiredAccess,
        DWORD dwCreationDisposition,
        void **a4)
{
  HRESULT v7; // esi
  __int64 v8; // rdi
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  unsigned int v11; // ebx
  HANDLE FileW; // rax
  HRESULT v13; // eax
  HANDLE v14; // rbx
  HANDLE hFile; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szFilePath[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszPathOut[264]; // [rsp+480h] [rbp+380h] BYREF

  v7 = PathCchCombine(pszPathOut, 0x104u, pszPathIn, L"System Volume Information");
  if ( v7 >= 0 )
  {
    v7 = PathCchCombine(FileName, 0x104u, pszPathOut, L"IndexerVolumeGuid");
    if ( v7 >= 0 )
    {
      v8 = -1;
      v17 = 0;
      hFile = (HANDLE)-1LL;
      v18 = -1;
      CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v17);
      FileAttributesW = GetFileAttributesW(FileName);
      if ( FileAttributesW == -1 )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError != 2 )
        {
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_15;
        }
      }
      else if ( (FileAttributesW & 0x400) != 0 )
      {
LABEL_14:
        v11 = -2147024735;
LABEL_15:
        CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v17);
        return v11;
      }
      FileW = CreateFileW(FileName, dwDesiredAccess, 0, 0, dwCreationDisposition, 0x80u, 0);
      v13 = ResultFromWin32Handle(FileW, &hFile);
      v14 = hFile;
      v7 = v13;
      if ( hFile != (HANDLE)-1LL )
      {
        memset_0(szFilePath, 0, 0x208u);
        if ( GetFinalPathNameByHandleW(v14, szFilePath, 0x104u, 0) - 1 > 0x102
          || PathCchStripPrefix(szFilePath, 0x104u) < 0 )
        {
          goto LABEL_13;
        }
        do
          ++v8;
        while ( FileName[v8] );
        if ( (unsigned int)_o__wcsnicmp(szFilePath, FileName, v8 + 1) )
        {
LABEL_13:
          CloseHandle(v14);
          goto LABEL_14;
        }
      }
      *a4 = v14;
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v17);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18020d95c  push    rbp
0x18020d95e  push    rbx
0x18020d95f  push    rsi
0x18020d960  push    rdi
0x18020d961  push    r12
0x18020d963  push    r13
0x18020d965  push    r14
0x18020d967  push    r15
0x18020d969  lea     rbp, [rsp-5A8h]
0x18020d971  sub     rsp, 6A8h
0x18020d978  mov     rax, cs:__security_cookie
0x18020d97f  xor     rax, rsp
0x18020d982  mov     [rbp+5E0h+var_50], rax
0x18020d989  mov     r12d, r8d
0x18020d98c  mov     r14, r9
0x18020d98f  mov     r8, rcx; pszPathIn
0x18020d992  lea     r9, pszMore; "System Volume Information"
0x18020d999  mov     r15d, edx
0x18020d99c  lea     rcx, [rbp+5E0h+pszPathOut]; pszPathOut
0x18020d9a3  mov     ebx, 104h
0x18020d9a8  mov     edx, ebx; cchPathOut
0x18020d9aa  call    cs:__imp_PathCchCombine
0x18020d9b0  xor     r13d, r13d
0x18020d9b3  mov     esi, eax
0x18020d9b5  test    eax, eax
0x18020d9b7  js      loc_18020DB1E
0x18020d9bd  lea     r9, aIndexervolumeg; "IndexerVolumeGuid"
0x18020d9c4  mov     edx, ebx; cchPathOut
0x18020d9c6  lea     r8, [rbp+5E0h+pszPathOut]; pszPathIn
0x18020d9cd  lea     rcx, [rsp+6E0h+FileName]; pszPathOut
0x18020d9d2  call    cs:__imp_PathCchCombine
0x18020d9d8  mov     esi, eax
0x18020d9da  test    eax, eax
0x18020d9dc  js      loc_18020DB1E
0x18020d9e2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18020d9e6  mov     [rsp+6E0h+var_698], r13d
0x18020d9eb  lea     rcx, [rsp+6E0h+var_698]; this
0x18020d9f0  mov     [rsp+6E0h+hFile], rdi
0x18020d9f5  mov     [rsp+6E0h+var_690], rdi
0x18020d9fa  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x18020d9ff  lea     rcx, [rsp+6E0h+FileName]; lpFileName
0x18020da04  call    cs:__imp_GetFileAttributesW
0x18020da0a  cmp     eax, 0FFFFFFFFh
0x18020da0d  jnz     short loc_18020DA32
0x18020da0f  call    cs:__imp_GetLastError
0x18020da15  mov     ebx, eax
0x18020da17  cmp     eax, 2
0x18020da1a  jz      short loc_18020DA3C
0x18020da1c  test    eax, eax
0x18020da1e  jle     loc_18020DB03
0x18020da24  movzx   ebx, ax
0x18020da27  or      ebx, 80070000h
0x18020da2d  jmp     loc_18020DB03
0x18020da32  bt      eax, 0Ah
0x18020da36  jb      loc_18020DAFE
0x18020da3c  mov     [rsp+6E0h+hTemplateFile], r13; hTemplateFile
0x18020da41  lea     rcx, [rsp+6E0h+FileName]; lpFileName
0x18020da46  mov     [rsp+6E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18020da4e  xor     r9d, r9d; lpSecurityAttributes
0x18020da51  xor     r8d, r8d; dwShareMode
0x18020da54  mov     [rsp+6E0h+dwCreationDisposition], r12d; dwCreationDisposition
0x18020da59  mov     edx, r15d; dwDesiredAccess
0x18020da5c  call    cs:__imp_CreateFileW
0x18020da62  mov     rcx, rax; void *
0x18020da65  lea     rdx, [rsp+6E0h+hFile]; void **
0x18020da6a  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x18020da6f  mov     rbx, [rsp+6E0h+hFile]
0x18020da74  mov     esi, eax
0x18020da76  cmp     rbx, rdi
0x18020da79  jz      loc_18020DB11
0x18020da7f  xor     edx, edx; Val
0x18020da81  lea     rcx, [rbp+5E0h+szFilePath]; void *
0x18020da88  mov     r8d, 208h; Size
0x18020da8e  call    memset_0
0x18020da93  mov     r15d, 104h
0x18020da99  lea     rdx, [rbp+5E0h+szFilePath]; lpszFilePath
0x18020daa0  mov     r8d, r15d; cchFilePath
0x18020daa3  xor     r9d, r9d; dwFlags
0x18020daa6  mov     rcx, rbx; hFile
0x18020daa9  call    cs:__imp_GetFinalPathNameByHandleW
0x18020daaf  dec     eax
0x18020dab1  cmp     eax, 102h
0x18020dab6  ja      short loc_18020DAF5
0x18020dab8  mov     edx, r15d; cchPath
0x18020dabb  lea     rcx, [rbp+5E0h+szFilePath]; pszPath
0x18020dac2  call    cs:__imp_PathCchStripPrefix
0x18020dac8  test    eax, eax
0x18020daca  js      short loc_18020DAF5
0x18020dacc  lea     rax, [rsp+6E0h+FileName]
0x18020dad1  inc     rdi
0x18020dad4  cmp     [rax+rdi*2], r13w
0x18020dad9  jnz     short loc_18020DAD1
0x18020dadb  lea     r8, [rdi+1]
0x18020dadf  lea     rdx, [rsp+6E0h+FileName]
0x18020dae4  lea     rcx, [rbp+5E0h+szFilePath]
0x18020daeb  call    cs:__imp__o__wcsnicmp
0x18020daf1  test    eax, eax
0x18020daf3  jz      short loc_18020DB11
0x18020daf5  mov     rcx, rbx; hObject
0x18020daf8  call    cs:__imp_CloseHandle
0x18020dafe  mov     ebx, 800700A1h
0x18020db03  lea     rcx, [rsp+6E0h+var_698]; this
0x18020db08  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x18020db0d  mov     eax, ebx
0x18020db0f  jmp     short loc_18020DB20
0x18020db11  lea     rcx, [rsp+6E0h+var_698]; this
0x18020db16  mov     [r14], rbx
0x18020db19  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x18020db1e  mov     eax, esi
0x18020db20  mov     rcx, [rbp+5E0h+var_50]
0x18020db27  xor     rcx, rsp; StackCookie
0x18020db2a  call    __security_check_cookie
0x18020db2f  add     rsp, 6A8h
0x18020db36  pop     r15
0x18020db38  pop     r14
0x18020db3a  pop     r13
0x18020db3c  pop     r12
0x18020db3e  pop     rdi
0x18020db3f  pop     rsi
0x18020db40  pop     rbx
0x18020db41  pop     rbp
0x18020db42  retn
```
