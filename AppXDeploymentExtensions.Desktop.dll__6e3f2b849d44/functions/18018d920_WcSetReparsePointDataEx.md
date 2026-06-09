# WcSetReparsePointDataEx

- ea: `0x18018d920`
- end: `0x18018dc52`
- name: `WcSetReparsePointDataEx`
- size: `818`
- prototype: `__int64 __fastcall(__int64, void *, __int64, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180189b68`
- `0x18018dd94`

## callees

- `0x1800aed10`
- `0x18018d648`
- `0x18018d920`
- `0x18018de74`
- `0x18018e0f4`
- `0x18018e25c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18018dc1c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18018dc1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018d9f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018da89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018db1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018d9f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018da89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018db1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018dbf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018dbf2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018da78`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018da78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18018d9df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18018daea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18018d9df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18018daea`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18018dab0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18018dab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018dc07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018dc07`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18018db0e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18018db0e`
- `KERNEL32!SetFileInformationByHandle` at `0x18018dbd3`
- `KERNEL32!SetFileInformationByHandle` at `0x18018dbd3`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18018dba5`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18018dba5`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18018da51`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18018da51`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WcSetReparsePointDataEx(__int64 a1, void *a2, __int64 a3, unsigned int a4, unsigned int a5)
{
  signed int FilterInstanceReparseTag; // ebx
  WCHAR *v8; // rsi
  int v9; // r14d
  int v10; // r12d
  HANDLE FileW; // rdi
  signed int LastError; // eax
  bool v13; // cc
  DWORD FileAttributesW; // eax
  signed int v15; // eax
  bool v16; // cc
  int v18; // [rsp+44h] [rbp-4Dh] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-49h] BYREF
  PACL ppDacl; // [rsp+50h] [rbp-41h] BYREF
  PSID ppsidGroup; // [rsp+58h] [rbp-39h] BYREF
  PSID ppsidOwner; // [rsp+60h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+68h] [rbp-29h] BYREF
  void *Block; // [rsp+70h] [rbp-21h] BYREF
  _OWORD FileInformation[2]; // [rsp+78h] [rbp-19h] BYREF
  __int64 v26; // [rsp+98h] [rbp+7h]

  v18 = 0;
  v26 = 0;
  lpFileName = 0;
  ppsidOwner = 0;
  ppsidGroup = 0;
  ppDacl = 0;
  hMem = 0;
  Block = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !a2 && a4 != 2 )
    return (unsigned int)-2147024809;
  FilterInstanceReparseTag = WcpConstructLongPath(a1, &Block, &lpFileName);
  if ( FilterInstanceReparseTag >= 0 )
  {
    v8 = (WCHAR *)lpFileName;
    v9 = 0;
    v10 = 0;
    FileW = CreateFileW(lpFileName, 0x100u, 1u, 0, 3u, 0x2200000u, 0);
    if ( FileW != (HANDLE)-1LL )
      goto LABEL_17;
    LastError = GetLastError();
    FilterInstanceReparseTag = LastError;
    if ( LastError != 5 )
    {
LABEL_7:
      v13 = LastError <= 0;
      goto LABEL_8;
    }
    LastError = GetNamedSecurityInfoW(v8, SE_FILE_OBJECT, 7u, &ppsidOwner, &ppsidGroup, &ppDacl, 0, &hMem);
    FilterInstanceReparseTag = LastError;
    v13 = LastError <= 0;
    if ( LastError )
    {
LABEL_8:
      if ( !v13 )
        FilterInstanceReparseTag = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_30;
    }
    FilterInstanceReparseTag = WcpTakeOwnership(v8);
    if ( FilterInstanceReparseTag >= 0 )
    {
      FileAttributesW = GetFileAttributesW(v8);
      if ( FileAttributesW == -1
        || (FileAttributesW & 1) != 0 && (v10 = 1, !SetFileAttributesW(v8, FileAttributesW & 0xFFFFFFFE))
        || (v9 = 1, FileW = CreateFileW(v8, 0x100u, 1u, 0, 3u, 0x2200000u, 0), FileW == (HANDLE)-1LL) )
      {
        LastError = GetLastError();
        FilterInstanceReparseTag = LastError;
        goto LABEL_7;
      }
LABEL_17:
      if ( !GetFileInformationByHandleEx(FileW, FileBasicInfo, FileInformation, 0x28u) )
        goto LABEL_18;
      FilterInstanceReparseTag = WcGetFilterInstanceReparseTag(a5, a4, &v18);
      if ( FilterInstanceReparseTag >= 0 )
      {
        FilterInstanceReparseTag = WcpWriteReparsePoint(FileW, a2);
        if ( FilterInstanceReparseTag >= 0 )
        {
          if ( v9 )
          {
            v15 = SetNamedSecurityInfoW(v8, SE_FILE_OBJECT, 7u, ppsidOwner, ppsidGroup, ppDacl, 0);
            FilterInstanceReparseTag = v15;
            v16 = v15 <= 0;
            if ( v15 )
            {
LABEL_19:
              if ( !v16 )
                FilterInstanceReparseTag = (unsigned __int16)v15 | 0x80070000;
              goto LABEL_29;
            }
          }
          if ( v10 )
            LODWORD(v26) = v26 | 1;
          if ( !SetFileInformationByHandle(FileW, FileBasicInfo, FileInformation, 0x28u) )
          {
LABEL_18:
            v15 = GetLastError();
            FilterInstanceReparseTag = v15;
            v16 = v15 <= 0;
            goto LABEL_19;
          }
          FilterInstanceReparseTag = 0;
        }
      }
LABEL_29:
      CloseHandle(FileW);
    }
  }
LABEL_30:
  if ( hMem )
    LocalFree(hMem);
  if ( Block )
    free(Block);
  return (unsigned int)FilterInstanceReparseTag;
}

```

## disassembly

```asm
0x18018d920  mov     [rsp-8+arg_18], rbx
0x18018d925  push    rbp
0x18018d926  push    rsi
0x18018d927  push    rdi
0x18018d928  push    r12
0x18018d92a  push    r13
0x18018d92c  push    r14
0x18018d92e  push    r15
0x18018d930  lea     rbp, [rsp-1Fh]
0x18018d935  sub     rsp, 0B0h
0x18018d93c  mov     rax, cs:__security_cookie
0x18018d943  xor     rax, rsp
0x18018d946  mov     [rbp+4Fh+var_40], rax
0x18018d94a  xor     eax, eax
0x18018d94c  mov     [rbp+4Fh+var_A0], r8w
0x18018d951  mov     [rbp+4Fh+var_9C], 0
0x18018d958  xorps   xmm0, xmm0
0x18018d95b  mov     [rbp+4Fh+var_48], rax
0x18018d95f  mov     r15d, r9d
0x18018d962  mov     [rbp+4Fh+lpFileName], rax
0x18018d966  mov     r13, rdx
0x18018d969  mov     [rbp+4Fh+ppsidOwner], rax
0x18018d96d  mov     [rbp+4Fh+ppsidGroup], rax
0x18018d971  mov     [rbp+4Fh+ppDacl], rax
0x18018d975  mov     [rbp+4Fh+hMem], rax
0x18018d979  mov     [rbp+4Fh+Block], rax
0x18018d97d  movups  [rbp+4Fh+FileInformation], xmm0
0x18018d981  movups  [rbp+4Fh+var_58], xmm0
0x18018d985  test    rdx, rdx
0x18018d988  jnz     short loc_18018D99A
0x18018d98a  cmp     r9d, 2
0x18018d98e  jz      short loc_18018D99A
0x18018d990  mov     ebx, 80070057h
0x18018d995  jmp     loc_18018DC28
0x18018d99a  lea     r8, [rbp+4Fh+lpFileName]
0x18018d99e  lea     rdx, [rbp+4Fh+Block]
0x18018d9a2  call    WcpConstructLongPath
0x18018d9a7  mov     ebx, eax
0x18018d9a9  test    eax, eax
0x18018d9ab  js      loc_18018DBFE
0x18018d9b1  mov     rsi, [rbp+4Fh+lpFileName]
0x18018d9b5  xor     r14d, r14d
0x18018d9b8  xor     r12d, r12d
0x18018d9bb  xor     r9d, r9d; lpSecurityAttributes
0x18018d9be  mov     [rsp+0E0h+hTemplateFile], r12; hTemplateFile
0x18018d9c3  mov     edx, 100h; dwDesiredAccess
0x18018d9c8  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18018d9d0  mov     rcx, rsi; lpFileName
0x18018d9d3  lea     r8d, [r14+1]; dwShareMode
0x18018d9d7  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18018d9df  call    cs:__imp_CreateFileW
0x18018d9e6  nop     dword ptr [rax+rax+00h]
0x18018d9eb  mov     rdi, rax
0x18018d9ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018d9f2  jnz     loc_18018DAFF
0x18018d9f8  call    cs:__imp_GetLastError
0x18018d9ff  nop     dword ptr [rax+rax+00h]
0x18018da04  mov     ebx, eax
0x18018da06  cmp     eax, 5
0x18018da09  jz      short loc_18018DA21
0x18018da0b  test    eax, eax
0x18018da0d  jle     loc_18018DBFE
0x18018da13  movzx   ebx, ax
0x18018da16  or      ebx, 80070000h
0x18018da1c  jmp     loc_18018DBFE
0x18018da21  lea     rax, [rbp+4Fh+hMem]
0x18018da25  mov     edx, 1; ObjectType
0x18018da2a  mov     [rsp+0E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18018da2f  lea     r9, [rbp+4Fh+ppsidOwner]; ppsidOwner
0x18018da33  lea     rax, [rbp+4Fh+ppDacl]
0x18018da37  mov     [rsp+0E0h+hTemplateFile], r12; ppSacl
0x18018da3c  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; ppDacl
0x18018da41  mov     rcx, rsi; pObjectName
0x18018da44  lea     rax, [rbp+4Fh+ppsidGroup]
0x18018da48  lea     r8d, [rdx+6]; SecurityInfo
0x18018da4c  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; ppsidGroup
0x18018da51  call    cs:__imp_GetNamedSecurityInfoW
0x18018da58  nop     dword ptr [rax+rax+00h]
0x18018da5d  mov     ebx, eax
0x18018da5f  test    eax, eax
0x18018da61  jnz     short loc_18018DA0D
0x18018da63  mov     rcx, rsi; pObjectName
0x18018da66  call    WcpTakeOwnership
0x18018da6b  mov     ebx, eax
0x18018da6d  test    eax, eax
0x18018da6f  js      loc_18018DBFE
0x18018da75  mov     rcx, rsi; lpFileName
0x18018da78  call    cs:__imp_GetFileAttributesW
0x18018da7f  nop     dword ptr [rax+rax+00h]
0x18018da84  cmp     eax, 0FFFFFFFFh
0x18018da87  jnz     short loc_18018DA9C
0x18018da89  call    cs:__imp_GetLastError
0x18018da90  nop     dword ptr [rax+rax+00h]
0x18018da95  mov     ebx, eax
0x18018da97  jmp     loc_18018DA0B
0x18018da9c  mov     ebx, 1
0x18018daa1  test    bl, al
0x18018daa3  jz      short loc_18018DAC0
0x18018daa5  and     eax, 0FFFFFFFEh
0x18018daa8  mov     rcx, rsi; lpFileName
0x18018daab  mov     edx, eax; dwFileAttributes
0x18018daad  mov     r12d, ebx
0x18018dab0  call    cs:__imp_SetFileAttributesW
0x18018dab7  nop     dword ptr [rax+rax+00h]
0x18018dabc  test    eax, eax
0x18018dabe  jz      short loc_18018DA89
0x18018dac0  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18018dac9  xor     r9d, r9d; lpSecurityAttributes
0x18018dacc  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18018dad4  mov     r8d, ebx; dwShareMode
0x18018dad7  mov     edx, 100h; dwDesiredAccess
0x18018dadc  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18018dae4  mov     rcx, rsi; lpFileName
0x18018dae7  mov     r14d, ebx
0x18018daea  call    cs:__imp_CreateFileW
0x18018daf1  nop     dword ptr [rax+rax+00h]
0x18018daf6  mov     rdi, rax
0x18018daf9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018dafd  jz      short loc_18018DA89
0x18018daff  mov     r9d, 28h ; '('; dwBufferSize
0x18018db05  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x18018db09  xor     edx, edx; FileInformationClass
0x18018db0b  mov     rcx, rdi; hFile
0x18018db0e  call    cs:__imp_GetFileInformationByHandleEx
0x18018db15  nop     dword ptr [rax+rax+00h]
0x18018db1a  test    eax, eax
0x18018db1c  jnz     short loc_18018DB42
0x18018db1e  call    cs:__imp_GetLastError
0x18018db25  nop     dword ptr [rax+rax+00h]
0x18018db2a  mov     ebx, eax
0x18018db2c  test    eax, eax
0x18018db2e  jle     loc_18018DBE9
0x18018db34  movzx   ebx, ax
0x18018db37  or      ebx, 80070000h
0x18018db3d  jmp     loc_18018DBE9
0x18018db42  mov     ecx, [rbp+4Fh+arg_20]
0x18018db45  lea     r8, [rbp+4Fh+var_9C]
0x18018db49  mov     edx, r15d
0x18018db4c  call    WcGetFilterInstanceReparseTag
0x18018db51  mov     ebx, eax
0x18018db53  test    eax, eax
0x18018db55  js      loc_18018DBE9
0x18018db5b  mov     r9d, [rbp+4Fh+var_9C]
0x18018db5f  mov     rdx, r13; Src
0x18018db62  movzx   r8d, [rbp+4Fh+var_A0]
0x18018db67  mov     rcx, rdi; hDevice
0x18018db6a  call    WcpWriteReparsePoint
0x18018db6f  mov     ebx, eax
0x18018db71  test    eax, eax
0x18018db73  js      short loc_18018DBE9
0x18018db75  test    r14d, r14d
0x18018db78  jz      short loc_18018DBBB
0x18018db7a  mov     rax, [rbp+4Fh+ppDacl]
0x18018db7e  mov     edx, 1; ObjectType
0x18018db83  mov     r9, [rbp+4Fh+ppsidOwner]; psidOwner
0x18018db87  mov     rcx, rsi; pObjectName
0x18018db8a  mov     [rsp+0E0h+hTemplateFile], 0; pSacl
0x18018db93  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; pDacl
0x18018db98  mov     rax, [rbp+4Fh+ppsidGroup]
0x18018db9c  lea     r8d, [rdx+6]; SecurityInfo
0x18018dba0  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; psidGroup
0x18018dba5  call    cs:__imp_SetNamedSecurityInfoW
0x18018dbac  nop     dword ptr [rax+rax+00h]
0x18018dbb1  mov     ebx, eax
0x18018dbb3  test    eax, eax
0x18018dbb5  jnz     loc_18018DB2E
0x18018dbbb  test    r12d, r12d
0x18018dbbe  jz      short loc_18018DBC4
0x18018dbc0  or      dword ptr [rbp+4Fh+var_48], 1
0x18018dbc4  mov     r9d, 28h ; '('; dwBufferSize
0x18018dbca  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x18018dbce  xor     edx, edx; FileInformationClass
0x18018dbd0  mov     rcx, rdi; hFile
0x18018dbd3  call    cs:__imp_SetFileInformationByHandle
0x18018dbda  nop     dword ptr [rax+rax+00h]
0x18018dbdf  test    eax, eax
0x18018dbe1  jz      loc_18018DB1E
0x18018dbe7  xor     ebx, ebx
0x18018dbe9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18018dbed  jz      short loc_18018DBFE
0x18018dbef  mov     rcx, rdi; hObject
0x18018dbf2  call    cs:__imp_CloseHandle
0x18018dbf9  nop     dword ptr [rax+rax+00h]
0x18018dbfe  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18018dc02  test    rcx, rcx
0x18018dc05  jz      short loc_18018DC13
0x18018dc07  call    cs:__imp_LocalFree
0x18018dc0e  nop     dword ptr [rax+rax+00h]
0x18018dc13  mov     rcx, [rbp+4Fh+Block]; Block
0x18018dc17  test    rcx, rcx
0x18018dc1a  jz      short loc_18018DC28
0x18018dc1c  call    cs:__imp_free
0x18018dc23  nop     dword ptr [rax+rax+00h]
0x18018dc28  mov     eax, ebx
0x18018dc2a  mov     rcx, [rbp+4Fh+var_40]
0x18018dc2e  xor     rcx, rsp; StackCookie
0x18018dc31  call    __security_check_cookie
0x18018dc36  mov     rbx, [rsp+0E0h+arg_18]
0x18018dc3e  add     rsp, 0B0h
0x18018dc45  pop     r15
0x18018dc47  pop     r14
0x18018dc49  pop     r13
0x18018dc4b  pop     r12
0x18018dc4d  pop     rdi
0x18018dc4e  pop     rsi
0x18018dc4f  pop     rbp
0x18018dc50  retn
```
