# WcSetReparsePointDataEx

- ea: `0x1800358c8`
- end: `0x180035bfa`
- name: `WcSetReparsePointDataEx`
- size: `818`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18018307c`
- `0x180183278`
- `0x180183578`

## callees

- `0x180004bd0`
- `0x180035128`
- `0x1800358c8`
- `0x180035d00`
- `0x1800364bc`
- `0x1800365c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180035bc4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180035bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ac6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180035a20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180035a20`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180035a58`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180035a58`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180035b7b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180035b7b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035987`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035a92`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035987`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035a92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035baf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035baf`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180035b4d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180035b4d`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800359f9`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800359f9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180035ab6`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180035ab6`

## pseudocode

```c
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
0x1800358c8  mov     [rsp-8+arg_18], rbx
0x1800358cd  push    rbp
0x1800358ce  push    rsi
0x1800358cf  push    rdi
0x1800358d0  push    r12
0x1800358d2  push    r13
0x1800358d4  push    r14
0x1800358d6  push    r15
0x1800358d8  lea     rbp, [rsp-1Fh]
0x1800358dd  sub     rsp, 0B0h
0x1800358e4  mov     rax, cs:__security_cookie
0x1800358eb  xor     rax, rsp
0x1800358ee  mov     [rbp+4Fh+var_40], rax
0x1800358f2  xor     eax, eax
0x1800358f4  mov     [rbp+4Fh+var_A0], r8w
0x1800358f9  mov     [rbp+4Fh+var_9C], 0
0x180035900  xorps   xmm0, xmm0
0x180035903  mov     [rbp+4Fh+var_48], rax
0x180035907  mov     r15d, r9d
0x18003590a  mov     [rbp+4Fh+lpFileName], rax
0x18003590e  mov     r13, rdx
0x180035911  mov     [rbp+4Fh+ppsidOwner], rax
0x180035915  mov     [rbp+4Fh+ppsidGroup], rax
0x180035919  mov     [rbp+4Fh+ppDacl], rax
0x18003591d  mov     [rbp+4Fh+hMem], rax
0x180035921  mov     [rbp+4Fh+Block], rax
0x180035925  movups  [rbp+4Fh+FileInformation], xmm0
0x180035929  movups  [rbp+4Fh+var_58], xmm0
0x18003592d  test    rdx, rdx
0x180035930  jnz     short loc_180035942
0x180035932  cmp     r9d, 2
0x180035936  jz      short loc_180035942
0x180035938  mov     ebx, 80070057h
0x18003593d  jmp     loc_180035BD0
0x180035942  lea     r8, [rbp+4Fh+lpFileName]
0x180035946  lea     rdx, [rbp+4Fh+Block]
0x18003594a  call    WcpConstructLongPath
0x18003594f  mov     ebx, eax
0x180035951  test    eax, eax
0x180035953  js      loc_180035BA6
0x180035959  mov     rsi, [rbp+4Fh+lpFileName]
0x18003595d  xor     r14d, r14d
0x180035960  xor     r12d, r12d
0x180035963  xor     r9d, r9d; lpSecurityAttributes
0x180035966  mov     [rsp+0E0h+hTemplateFile], r12; hTemplateFile
0x18003596b  mov     edx, 100h; dwDesiredAccess
0x180035970  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180035978  mov     rcx, rsi; lpFileName
0x18003597b  lea     r8d, [r14+1]; dwShareMode
0x18003597f  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180035987  call    cs:__imp_CreateFileW
0x18003598e  nop     dword ptr [rax+rax+00h]
0x180035993  mov     rdi, rax
0x180035996  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003599a  jnz     loc_180035AA7
0x1800359a0  call    cs:__imp_GetLastError
0x1800359a7  nop     dword ptr [rax+rax+00h]
0x1800359ac  mov     ebx, eax
0x1800359ae  cmp     eax, 5
0x1800359b1  jz      short loc_1800359C9
0x1800359b3  test    eax, eax
0x1800359b5  jle     loc_180035BA6
0x1800359bb  movzx   ebx, ax
0x1800359be  or      ebx, 80070000h
0x1800359c4  jmp     loc_180035BA6
0x1800359c9  lea     rax, [rbp+4Fh+hMem]
0x1800359cd  mov     edx, 1; ObjectType
0x1800359d2  mov     [rsp+0E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800359d7  lea     r9, [rbp+4Fh+ppsidOwner]; ppsidOwner
0x1800359db  lea     rax, [rbp+4Fh+ppDacl]
0x1800359df  mov     [rsp+0E0h+hTemplateFile], r12; ppSacl
0x1800359e4  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; ppDacl
0x1800359e9  mov     rcx, rsi; pObjectName
0x1800359ec  lea     rax, [rbp+4Fh+ppsidGroup]
0x1800359f0  lea     r8d, [rdx+6]; SecurityInfo
0x1800359f4  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; ppsidGroup
0x1800359f9  call    cs:__imp_GetNamedSecurityInfoW
0x180035a00  nop     dword ptr [rax+rax+00h]
0x180035a05  mov     ebx, eax
0x180035a07  test    eax, eax
0x180035a09  jnz     short loc_1800359B5
0x180035a0b  mov     rcx, rsi; pObjectName
0x180035a0e  call    WcpTakeOwnership
0x180035a13  mov     ebx, eax
0x180035a15  test    eax, eax
0x180035a17  js      loc_180035BA6
0x180035a1d  mov     rcx, rsi; lpFileName
0x180035a20  call    cs:__imp_GetFileAttributesW
0x180035a27  nop     dword ptr [rax+rax+00h]
0x180035a2c  cmp     eax, 0FFFFFFFFh
0x180035a2f  jnz     short loc_180035A44
0x180035a31  call    cs:__imp_GetLastError
0x180035a38  nop     dword ptr [rax+rax+00h]
0x180035a3d  mov     ebx, eax
0x180035a3f  jmp     loc_1800359B3
0x180035a44  mov     ebx, 1
0x180035a49  test    bl, al
0x180035a4b  jz      short loc_180035A68
0x180035a4d  and     eax, 0FFFFFFFEh
0x180035a50  mov     rcx, rsi; lpFileName
0x180035a53  mov     edx, eax; dwFileAttributes
0x180035a55  mov     r12d, ebx
0x180035a58  call    cs:__imp_SetFileAttributesW
0x180035a5f  nop     dword ptr [rax+rax+00h]
0x180035a64  test    eax, eax
0x180035a66  jz      short loc_180035A31
0x180035a68  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x180035a71  xor     r9d, r9d; lpSecurityAttributes
0x180035a74  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180035a7c  mov     r8d, ebx; dwShareMode
0x180035a7f  mov     edx, 100h; dwDesiredAccess
0x180035a84  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180035a8c  mov     rcx, rsi; lpFileName
0x180035a8f  mov     r14d, ebx
0x180035a92  call    cs:__imp_CreateFileW
0x180035a99  nop     dword ptr [rax+rax+00h]
0x180035a9e  mov     rdi, rax
0x180035aa1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035aa5  jz      short loc_180035A31
0x180035aa7  mov     r9d, 28h ; '('; dwBufferSize
0x180035aad  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x180035ab1  xor     edx, edx; FileInformationClass
0x180035ab3  mov     rcx, rdi; hFile
0x180035ab6  call    cs:__imp_GetFileInformationByHandleEx
0x180035abd  nop     dword ptr [rax+rax+00h]
0x180035ac2  test    eax, eax
0x180035ac4  jnz     short loc_180035AEA
0x180035ac6  call    cs:__imp_GetLastError
0x180035acd  nop     dword ptr [rax+rax+00h]
0x180035ad2  mov     ebx, eax
0x180035ad4  test    eax, eax
0x180035ad6  jle     loc_180035B91
0x180035adc  movzx   ebx, ax
0x180035adf  or      ebx, 80070000h
0x180035ae5  jmp     loc_180035B91
0x180035aea  mov     ecx, [rbp+4Fh+arg_20]
0x180035aed  lea     r8, [rbp+4Fh+var_9C]
0x180035af1  mov     edx, r15d
0x180035af4  call    WcGetFilterInstanceReparseTag
0x180035af9  mov     ebx, eax
0x180035afb  test    eax, eax
0x180035afd  js      loc_180035B91
0x180035b03  mov     r9d, [rbp+4Fh+var_9C]
0x180035b07  mov     rdx, r13; Src
0x180035b0a  movzx   r8d, [rbp+4Fh+var_A0]
0x180035b0f  mov     rcx, rdi; hDevice
0x180035b12  call    WcpWriteReparsePoint
0x180035b17  mov     ebx, eax
0x180035b19  test    eax, eax
0x180035b1b  js      short loc_180035B91
0x180035b1d  test    r14d, r14d
0x180035b20  jz      short loc_180035B63
0x180035b22  mov     rax, [rbp+4Fh+ppDacl]
0x180035b26  mov     edx, 1; ObjectType
0x180035b2b  mov     r9, [rbp+4Fh+ppsidOwner]; psidOwner
0x180035b2f  mov     rcx, rsi; pObjectName
0x180035b32  mov     [rsp+0E0h+hTemplateFile], 0; pSacl
0x180035b3b  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; pDacl
0x180035b40  mov     rax, [rbp+4Fh+ppsidGroup]
0x180035b44  lea     r8d, [rdx+6]; SecurityInfo
0x180035b48  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; psidGroup
0x180035b4d  call    cs:__imp_SetNamedSecurityInfoW
0x180035b54  nop     dword ptr [rax+rax+00h]
0x180035b59  mov     ebx, eax
0x180035b5b  test    eax, eax
0x180035b5d  jnz     loc_180035AD6
0x180035b63  test    r12d, r12d
0x180035b66  jz      short loc_180035B6C
0x180035b68  or      dword ptr [rbp+4Fh+var_48], 1
0x180035b6c  mov     r9d, 28h ; '('; dwBufferSize
0x180035b72  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x180035b76  xor     edx, edx; FileInformationClass
0x180035b78  mov     rcx, rdi; hFile
0x180035b7b  call    cs:__imp_SetFileInformationByHandle
0x180035b82  nop     dword ptr [rax+rax+00h]
0x180035b87  test    eax, eax
0x180035b89  jz      loc_180035AC6
0x180035b8f  xor     ebx, ebx
0x180035b91  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180035b95  jz      short loc_180035BA6
0x180035b97  mov     rcx, rdi; hObject
0x180035b9a  call    cs:__imp_CloseHandle
0x180035ba1  nop     dword ptr [rax+rax+00h]
0x180035ba6  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180035baa  test    rcx, rcx
0x180035bad  jz      short loc_180035BBB
0x180035baf  call    cs:__imp_LocalFree
0x180035bb6  nop     dword ptr [rax+rax+00h]
0x180035bbb  mov     rcx, [rbp+4Fh+Block]; Block
0x180035bbf  test    rcx, rcx
0x180035bc2  jz      short loc_180035BD0
0x180035bc4  call    cs:__imp_free
0x180035bcb  nop     dword ptr [rax+rax+00h]
0x180035bd0  mov     eax, ebx
0x180035bd2  mov     rcx, [rbp+4Fh+var_40]
0x180035bd6  xor     rcx, rsp; StackCookie
0x180035bd9  call    __security_check_cookie
0x180035bde  mov     rbx, [rsp+0E0h+arg_18]
0x180035be6  add     rsp, 0B0h
0x180035bed  pop     r15
0x180035bef  pop     r14
0x180035bf1  pop     r13
0x180035bf3  pop     r12
0x180035bf5  pop     rdi
0x180035bf6  pop     rsi
0x180035bf7  pop     rbp
0x180035bf8  retn
```
