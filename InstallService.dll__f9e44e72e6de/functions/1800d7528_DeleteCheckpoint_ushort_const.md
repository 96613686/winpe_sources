# DeleteCheckpoint(ushort const *)

- ea: `0x1800d7528`
- end: `0x1800d7801`
- name: `?DeleteCheckpoint@@YAJPEBG@Z`
- size: `729`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180052e60`
- `0x180053028`
- `0x18005920c`
- `0x18005ffd0`
- `0x180061994`
- `0x1800d8424`
- `0x1801fcead`

## callees

- `0x180009ea0`
- `0x180010b54`
- `0x18001c414`
- `0x180072420`
- `0x180084010`
- `0x1800d70b8`
- `0x1800d7528`
- `0x1800d8804`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d76e1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d76e1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800d7764`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800d7764`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d7675`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d7690`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d7675`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d7690`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d75a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d762e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d75a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d762e`

## string_xrefs

- `0x1800d75f9`: `onecoreuap\enduser\winstore\installservice\lib\checkpoint.cpp`
- `0x1800d7649`: `onecoreuap\enduser\winstore\installservice\lib\checkpoint.cpp`
- `0x1800d771e`: `onecoreuap\enduser\winstore\installservice\lib\checkpoint.cpp`
- `0x1800d77b7`: `onecoreuap\enduser\winstore\installservice\lib\checkpoint.cpp`
- `0x1800d75db`: `Symbolic link detected. Checkpoint file delete failed: Id = '%s'`
- `0x1800d75ec`: `DeleteCheckpoint`
- `0x1800d7717`: `DeleteCheckpoint`
- `0x1800d77aa`: `DeleteCheckpoint`
- `0x1800d7799`: `Checkpoint file delete failed: Id = '%s'`
- `0x1800d76a4`: `Path length does not match. Checkpoint file delete failed: Id = '%s'`
- `0x1800d76f6`: `File path from handle do not match. Checkpoint file delete failed: Id = '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeleteCheckpoint(const unsigned __int16 *a1, unsigned __int64 a2)
{
  int Error; // r15d
  unsigned int LastError; // r14d
  HANDLE FileW; // rdi
  HANDLE v6; // rax
  const char *v7; // r9
  void *v8; // rbx
  DWORD FinalPathNameByHandleW; // esi
  __int64 v10; // rdx
  char FileInformation[8]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v13; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String2[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR szFilePath[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+5D8h]

  Error = CheckpointFilename(FileName, a2, a1);
  if ( Error >= 0 )
  {
    LastError = 5;
    FileW = CreateFileW(FileName, 0x80000000, 5u, 0, 3u, 0x80u, 0);
    v14[0] = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      Error = ResultFromKnownLastError();
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
        0xD4u,
        "DeleteCheckpoint",
        Error,
        L"Checkpoint file delete failed: Id = '%s'",
        0,
        0,
        a1);
    }
    else
    {
      if ( _IsFilePathSymlink(FileName) )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
          0xA2u,
          "DeleteCheckpoint",
          5,
          L"Symbolic link detected. Checkpoint file delete failed: Id = '%s'",
          0,
          0,
          FileName);
LABEL_14:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v14);
        return LastError;
      }
      v6 = CreateFileW(FileName, 0x10000u, 5u, 0, 3u, 0x200080u, 0);
      v8 = v6;
      v13 = v6;
      if ( v6 == (HANDLE)-1LL )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xAF,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
                      v7);
LABEL_13:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
        goto LABEL_14;
      }
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(v6, szFilePath, 0x104u, 0);
      if ( FinalPathNameByHandleW != GetFinalPathNameByHandleW(FileW, String2, 0x104u, 0) )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
          0xB8u,
          "DeleteCheckpoint",
          5,
          L"Path length does not match. Checkpoint file delete failed: Id = '%s'",
          0,
          0,
          FileName);
        goto LABEL_13;
      }
      v10 = -1;
      do
        ++v10;
      while ( String2[v10] );
      if ( CompareStringOrdinal(szFilePath, v10, String2, -1, 1) != 2 )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
          0xBFu,
          "DeleteCheckpoint",
          5,
          L"File path from handle do not match. Checkpoint file delete failed: Id = '%s'",
          0,
          0,
          FileName);
        goto LABEL_13;
      }
      FileInformation[0] = 1;
      if ( !SetFileInformationByHandle(v8, FileDispositionInfo, FileInformation, 1u) )
        Error = ResultFromKnownLastError();
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v14);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d7528  mov     [rsp-8+arg_8], rbx
0x1800d752d  mov     [rsp-8+arg_10], rsi
0x1800d7532  push    rbp
0x1800d7533  push    rdi
0x1800d7534  push    r13
0x1800d7536  push    r14
0x1800d7538  push    r15
0x1800d753a  lea     rbp, [rsp-5B0h]
0x1800d7542  sub     rsp, 6B0h
0x1800d7549  mov     rax, cs:__security_cookie
0x1800d7550  xor     rax, rsp
0x1800d7553  mov     [rbp+5D0h+var_30], rax
0x1800d755a  mov     rbx, rcx
0x1800d755d  mov     r8, rcx; unsigned __int16 *
0x1800d7560  lea     rcx, [rsp+6D0h+FileName]; unsigned __int16 *
0x1800d7565  call    ?CheckpointFilename@@YAJPEAG_KPEBG@Z; CheckpointFilename(ushort *,unsigned __int64,ushort const *)
0x1800d756a  mov     r15d, eax
0x1800d756d  xor     r13d, r13d
0x1800d7570  test    eax, eax
0x1800d7572  js      loc_1800D77D3
0x1800d7578  mov     [rsp+6D0h+hTemplateFile], r13; hTemplateFile
0x1800d757d  mov     [rsp+6D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d7585  lea     esi, [r13+3]
0x1800d7589  mov     [rsp+6D0h+dwCreationDisposition], esi; dwCreationDisposition
0x1800d758d  xor     r9d, r9d; lpSecurityAttributes
0x1800d7590  lea     r14d, [r13+5]
0x1800d7594  mov     r8d, r14d; dwShareMode
0x1800d7597  mov     edx, 80000000h; dwDesiredAccess
0x1800d759c  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x1800d75a1  call    cs:__imp_CreateFileW
0x1800d75a7  mov     rdi, rax
0x1800d75aa  mov     [rsp+6D0h+var_670], rax
0x1800d75af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d75b3  jz      loc_1800D7782
0x1800d75b9  lea     rcx, [rsp+6D0h+FileName]; unsigned __int16 *
0x1800d75be  call    ?_IsFilePathSymlink@@YA_NPEBG@Z; _IsFilePathSymlink(ushort const *)
0x1800d75c3  test    al, al
0x1800d75c5  jz      short loc_1800D760D
0x1800d75c7  lea     rax, [rsp+6D0h+FileName]
0x1800d75cc  mov     [rsp+6D0h+var_690], rax
0x1800d75d1  mov     [rsp+6D0h+var_698], r13; unsigned __int16 *
0x1800d75d6  mov     [rsp+6D0h+hTemplateFile], r13; char *
0x1800d75db  lea     rax, aSymbolicLinkDe_0; "Symbolic link detected. Checkpoint file"...
0x1800d75e2  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800d75e7  mov     [rsp+6D0h+dwCreationDisposition], r14d; int
0x1800d75ec  lea     r9, aDeletecheckpoi_0; "DeleteCheckpoint"
0x1800d75f3  mov     r8d, 0A2h; unsigned int
0x1800d75f9  lea     rdx, aOnecoreuapEndu_45; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d7600  lea     ecx, [rsi-2]; unsigned int
0x1800d7603  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d7608  jmp     loc_1800D773B
0x1800d760d  mov     [rsp+6D0h+hTemplateFile], r13; hTemplateFile
0x1800d7612  mov     [rsp+6D0h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x1800d761a  mov     [rsp+6D0h+dwCreationDisposition], esi; dwCreationDisposition
0x1800d761e  xor     r9d, r9d; lpSecurityAttributes
0x1800d7621  mov     r8d, r14d; dwShareMode
0x1800d7624  mov     edx, 10000h; dwDesiredAccess
0x1800d7629  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x1800d762e  call    cs:__imp_CreateFileW
0x1800d7634  mov     rbx, rax
0x1800d7637  mov     [rsp+6D0h+var_678], rax
0x1800d763c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d7640  jnz     short loc_1800D7662
0x1800d7642  mov     rcx, [rbp+5D8h]; this
0x1800d7649  lea     r8, aOnecoreuapEndu_45; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d7650  mov     edx, 0AFh; void *
0x1800d7655  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d765a  mov     r14d, eax
0x1800d765d  jmp     loc_1800D7730
0x1800d7662  xor     r9d, r9d; dwFlags
0x1800d7665  mov     r8d, 104h; cchFilePath
0x1800d766b  lea     rdx, [rbp+5D0h+szFilePath]; lpszFilePath
0x1800d7672  mov     rcx, rbx; hFile
0x1800d7675  call    cs:__imp_GetFinalPathNameByHandleW
0x1800d767b  mov     esi, eax
0x1800d767d  xor     r9d, r9d; dwFlags
0x1800d7680  mov     r8d, 104h; cchFilePath
0x1800d7686  lea     rdx, [rbp+5D0h+String2]; lpszFilePath
0x1800d768d  mov     rcx, rdi; hFile
0x1800d7690  call    cs:__imp_GetFinalPathNameByHandleW
0x1800d7696  cmp     esi, eax
0x1800d7698  jz      short loc_1800D76B3
0x1800d769a  lea     rax, [rsp+6D0h+FileName]
0x1800d769f  mov     [rsp+6D0h+var_690], rax
0x1800d76a4  lea     rax, aPathLengthDoes; "Path length does not match. Checkpoint "...
0x1800d76ab  mov     r8d, 0B8h
0x1800d76b1  jmp     short loc_1800D7703
0x1800d76b3  lea     rax, [rbp+5D0h+String2]
0x1800d76ba  or      r9, 0FFFFFFFFFFFFFFFFh; cchCount2
0x1800d76be  mov     rdx, r9
0x1800d76c1  inc     rdx; cchCount1
0x1800d76c4  cmp     [rax+rdx*2], r13w
0x1800d76c9  jnz     short loc_1800D76C1
0x1800d76cb  mov     [rsp+6D0h+dwCreationDisposition], 1; bIgnoreCase
0x1800d76d3  lea     r8, [rbp+5D0h+String2]; lpString2
0x1800d76da  lea     rcx, [rbp+5D0h+szFilePath]; lpString1
0x1800d76e1  call    cs:__imp_CompareStringOrdinal
0x1800d76e7  cmp     eax, 2
0x1800d76ea  jz      short loc_1800D774D
0x1800d76ec  lea     rax, [rsp+6D0h+FileName]
0x1800d76f1  mov     [rsp+6D0h+var_690], rax
0x1800d76f6  lea     rax, aFilePathFromHa; "File path from handle do not match. Che"...
0x1800d76fd  mov     r8d, 0BFh; unsigned int
0x1800d7703  mov     [rsp+6D0h+var_698], r13; unsigned __int16 *
0x1800d7708  mov     [rsp+6D0h+hTemplateFile], r13; char *
0x1800d770d  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800d7712  mov     [rsp+6D0h+dwCreationDisposition], r14d; int
0x1800d7717  lea     r9, aDeletecheckpoi_0; "DeleteCheckpoint"
0x1800d771e  lea     rdx, aOnecoreuapEndu_45; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d7725  mov     ecx, 1; unsigned int
0x1800d772a  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d772f  nop
0x1800d7730  lea     rcx, [rsp+6D0h+var_678]
0x1800d7735  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d773a  nop
0x1800d773b  lea     rcx, [rsp+6D0h+var_670]
0x1800d7740  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d7745  mov     eax, r14d
0x1800d7748  jmp     loc_1800D77D6
0x1800d774d  mov     [rsp+6D0h+FileInformation], 1
0x1800d7752  mov     r9d, 1; dwBufferSize
0x1800d7758  lea     r8, [rsp+6D0h+FileInformation]; lpFileInformation
0x1800d775d  lea     edx, [r9+3]; FileInformationClass
0x1800d7761  mov     rcx, rbx; hFile
0x1800d7764  call    cs:__imp_SetFileInformationByHandle
0x1800d776a  test    eax, eax
0x1800d776c  jnz     short loc_1800D7776
0x1800d776e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d7773  mov     r15d, eax
0x1800d7776  lea     rcx, [rsp+6D0h+var_678]
0x1800d777b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d7780  jmp     short loc_1800D77C9
0x1800d7782  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d7787  mov     r15d, eax
0x1800d778a  mov     [rsp+6D0h+var_690], rbx
0x1800d778f  mov     [rsp+6D0h+var_698], r13; unsigned __int16 *
0x1800d7794  mov     [rsp+6D0h+hTemplateFile], r13; char *
0x1800d7799  lea     rax, aCheckpointFile_3; "Checkpoint file delete failed: Id = '%s"...
0x1800d77a0  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800d77a5  mov     [rsp+6D0h+dwCreationDisposition], r15d; int
0x1800d77aa  lea     r9, aDeletecheckpoi_0; "DeleteCheckpoint"
0x1800d77b1  mov     r8d, 0D4h; unsigned int
0x1800d77b7  lea     rdx, aOnecoreuapEndu_45; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d77be  mov     ecx, 1; unsigned int
0x1800d77c3  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d77c8  nop
0x1800d77c9  lea     rcx, [rsp+6D0h+var_670]
0x1800d77ce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d77d3  mov     eax, r15d
0x1800d77d6  mov     rcx, [rbp+5D0h+var_30]
0x1800d77dd  xor     rcx, rsp; StackCookie
0x1800d77e0  call    __security_check_cookie
0x1800d77e5  lea     r11, [rsp+6D0h+var_20]
0x1800d77ed  mov     rbx, [r11+38h]
0x1800d77f1  mov     rsi, [r11+40h]
0x1800d77f5  mov     rsp, r11
0x1800d77f8  pop     r15
0x1800d77fa  pop     r14
0x1800d77fc  pop     r13
0x1800d77fe  pop     rdi
0x1800d77ff  pop     rbp
0x1800d7800  retn
```
