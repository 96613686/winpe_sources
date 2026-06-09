# WcpRemoveFile

- ea: `0x18000e014`
- end: `0x18000e31a`
- name: `WcpRemoveFile`
- size: `774`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000bc6c`
- `0x18000d8f4`

## callees

- `0x18000d268`
- `0x18000d2c4`
- `0x18000ddb8`
- `0x18000de94`
- `0x18000e014`
- `0x18000e320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e2d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e2d7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e252`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e279`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18000e09a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18000e09a`
- `ntdll!RtlFreeUnicodeString` at `0x18000e2ee`
- `ntdll!RtlFreeUnicodeString` at `0x18000e2ee`
- `ntdll!NtSetInformationFile` at `0x18000e16e`
- `ntdll!NtSetInformationFile` at `0x18000e16e`
- `ntdll!NtClose` at `0x18000e196`
- `ntdll!NtClose` at `0x18000e2bc`
- `ntdll!NtClose` at `0x18000e196`
- `ntdll!NtClose` at `0x18000e2bc`
- `ntdll!RtlNtStatusToDosError` at `0x18000e0ac`
- `ntdll!RtlNtStatusToDosError` at `0x18000e184`
- `ntdll!RtlNtStatusToDosError` at `0x18000e1b4`
- `ntdll!RtlNtStatusToDosError` at `0x18000e0ac`
- `ntdll!RtlNtStatusToDosError` at `0x18000e184`
- `ntdll!RtlNtStatusToDosError` at `0x18000e1b4`
- `ntdll!NtOpenFile` at `0x18000e116`
- `ntdll!NtOpenFile` at `0x18000e116`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e216`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e216`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000e234`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000e234`

## pseudocode

```c
__int64 __fastcall WcpRemoveFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v6; // rdi
  int v7; // ebx
  NTSTATUS v8; // eax
  signed int LastError; // eax
  int v10; // ebx
  DWORD v11; // r15d
  char v12; // r14
  int v13; // r12d
  int v14; // eax
  int v15; // eax
  signed int v16; // edi
  DWORD FileAttributesW; // eax
  DWORD v18; // eax
  LPCWSTR lpFileName; // [rsp+38h] [rbp-41h] BYREF
  void *FileHandle; // [rsp+40h] [rbp-39h] BYREF
  void *Block; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  int FileInformation; // [rsp+F0h] [rbp+77h] BYREF

  FileInformation = 0;
  lpFileName = 0;
  *(_QWORD *)&UnicodeString.Length = 0;
  v6 = a2;
  FileHandle = 0;
  Block = 0;
  UnicodeString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v7 = WcpConstructLongPath(a1, &Block, &lpFileName);
  if ( v7 < 0 )
    goto LABEL_39;
  v8 = RtlDosPathNameToNtPathName_U_WithStatus(lpFileName, &UnicodeString, 0, 0);
  if ( v8 < 0 )
  {
    LastError = RtlNtStatusToDosError(v8);
LABEL_4:
    v7 = LastError;
    if ( LastError > 0 )
    {
      v10 = (unsigned __int16)LastError;
      goto LABEL_38;
    }
    goto LABEL_39;
  }
  v11 = 0;
  ObjectAttributes.Length = 48;
  v12 = 0;
  ObjectAttributes.Attributes = 64;
  v13 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &UnicodeString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  while ( 1 )
  {
    v14 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
    if ( v14 < 0 )
    {
      v16 = RtlNtStatusToDosError(v14);
    }
    else
    {
      if ( !a5 )
      {
        v7 = EnsurePathNotRedirected(FileHandle, lpFileName, v6, a3);
        if ( v7 < 0 )
          goto LABEL_39;
      }
      FileInformation = 1;
      v15 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
      if ( v15 >= 0 )
        goto LABEL_39;
      v16 = RtlNtStatusToDosError(v15);
      if ( NtClose(FileHandle) < 0 )
        __int2c();
      FileHandle = 0;
    }
    if ( !v16 )
      goto LABEL_39;
    if ( FileHandle )
      __int2c();
    if ( v16 == 32 || v16 == 145 )
      break;
    if ( v16 != 5 )
      goto LABEL_35;
    if ( v12 )
      goto LABEL_37;
    if ( (unsigned int)Feature_WcRemoveFileOwnershipTOCTOU__private_IsEnabledDeviceUsageNoInline() )
    {
      v7 = WcpPrivilegedRemoveFile(&ObjectAttributes, (__int64)lpFileName, a2, a3);
      goto LABEL_39;
    }
    v7 = WcpTakeOwnership((LPWSTR)lpFileName);
    if ( v7 < 0 )
      goto LABEL_39;
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1
      || (FileAttributesW & 1) != 0 && !SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE) )
    {
      LastError = GetLastError();
      goto LABEL_4;
    }
    v12 = 1;
LABEL_32:
    v6 = a2;
  }
  if ( v13 != 25 )
  {
    Sleep(v11);
    v18 = v11 + 5;
    ++v13;
    if ( v11 >= 0x32 )
      v18 = v11;
    v11 = v18;
    goto LABEL_32;
  }
LABEL_35:
  if ( v16 <= 0 )
  {
    v7 = v16;
    goto LABEL_39;
  }
LABEL_37:
  v10 = (unsigned __int16)v16;
LABEL_38:
  v7 = v10 | 0x80070000;
LABEL_39:
  if ( FileHandle && NtClose(FileHandle) < 0 )
    __int2c();
  if ( Block )
    free(Block);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e014  mov     rax, rsp
0x18000e017  mov     [rax+8], rbx
0x18000e01b  mov     [rax+18h], rdi
0x18000e01f  mov     [rax+20h], r9b
0x18000e023  mov     [rax+10h], rdx
0x18000e027  push    rbp
0x18000e028  push    r12
0x18000e02a  push    r13
0x18000e02c  push    r14
0x18000e02e  push    r15
0x18000e030  lea     rbp, [rax-57h]
0x18000e034  sub     rsp, 0A0h
0x18000e03b  xorps   xmm0, xmm0
0x18000e03e  mov     [rbp+4Fh+FileInformation], 0
0x18000e045  xor     eax, eax
0x18000e047  mov     [rbp+4Fh+lpFileName], 0
0x18000e04f  mov     r13, r8
0x18000e052  mov     qword ptr [rbp+4Fh+UnicodeString.Length], rax
0x18000e056  mov     rdi, rdx
0x18000e059  mov     [rbp+4Fh+FileHandle], rax
0x18000e05d  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18000e061  lea     r8, [rbp+4Fh+lpFileName]
0x18000e065  mov     [rbp+4Fh+Block], rax
0x18000e069  lea     rdx, [rbp+4Fh+Block]
0x18000e06d  mov     [rbp+4Fh+UnicodeString.Buffer], rax
0x18000e071  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x18000e075  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18000e079  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18000e07d  call    WcpConstructLongPath
0x18000e082  mov     ebx, eax
0x18000e084  test    eax, eax
0x18000e086  js      loc_18000E2B3
0x18000e08c  mov     rcx, [rbp+4Fh+lpFileName]
0x18000e090  lea     rdx, [rbp+4Fh+UnicodeString]
0x18000e094  xor     r9d, r9d
0x18000e097  xor     r8d, r8d
0x18000e09a  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18000e0a1  nop     dword ptr [rax+rax+00h]
0x18000e0a6  test    eax, eax
0x18000e0a8  jns     short loc_18000E0CA
0x18000e0aa  mov     ecx, eax; Status
0x18000e0ac  call    cs:__imp_RtlNtStatusToDosError
0x18000e0b3  nop     dword ptr [rax+rax+00h]
0x18000e0b8  mov     ebx, eax
0x18000e0ba  test    eax, eax
0x18000e0bc  jle     loc_18000E2B3
0x18000e0c2  movzx   ebx, ax
0x18000e0c5  jmp     loc_18000E2AD
0x18000e0ca  xor     r15d, r15d
0x18000e0cd  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000e0d4  xor     r14b, r14b
0x18000e0d7  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18000e0de  xor     r12d, r12d
0x18000e0e1  lea     rax, [rbp+4Fh+UnicodeString]
0x18000e0e5  xorps   xmm0, xmm0
0x18000e0e8  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18000e0ec  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18000e0f0  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000e0f5  mov     [rsp+0C0h+OpenOptions], 204020h; OpenOptions
0x18000e0fd  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18000e101  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000e105  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x18000e10d  mov     edx, 110000h; DesiredAccess
0x18000e112  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18000e116  call    cs:__imp_NtOpenFile
0x18000e11d  nop     dword ptr [rax+rax+00h]
0x18000e122  test    eax, eax
0x18000e124  js      loc_18000E1B2
0x18000e12a  cmp     [rbp+4Fh+arg_20], 0
0x18000e12e  jnz     short loc_18000E14D
0x18000e130  mov     rdx, [rbp+4Fh+lpFileName]
0x18000e134  mov     r9, r13
0x18000e137  mov     rcx, [rbp+4Fh+FileHandle]
0x18000e13b  mov     r8, rdi
0x18000e13e  call    EnsurePathNotRedirected
0x18000e143  mov     ebx, eax
0x18000e145  test    eax, eax
0x18000e147  js      loc_18000E2B3
0x18000e14d  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18000e151  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x18000e155  mov     r9d, 4; Length
0x18000e15b  mov     [rbp+4Fh+FileInformation], 1
0x18000e162  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18000e166  mov     [rsp+0C0h+ShareAccess], 40h ; '@'; FileInformationClass
0x18000e16e  call    cs:__imp_NtSetInformationFile
0x18000e175  nop     dword ptr [rax+rax+00h]
0x18000e17a  test    eax, eax
0x18000e17c  jns     loc_18000E2B3
0x18000e182  mov     ecx, eax; Status
0x18000e184  call    cs:__imp_RtlNtStatusToDosError
0x18000e18b  nop     dword ptr [rax+rax+00h]
0x18000e190  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x18000e194  mov     edi, eax
0x18000e196  call    cs:__imp_NtClose
0x18000e19d  nop     dword ptr [rax+rax+00h]
0x18000e1a2  test    eax, eax
0x18000e1a4  jns     short loc_18000E1A8
0x18000e1a6  int     2Ch; Windows NT - assertion failure
0x18000e1a8  mov     [rbp+4Fh+FileHandle], 0
0x18000e1b0  jmp     short loc_18000E1C2
0x18000e1b2  mov     ecx, eax; Status
0x18000e1b4  call    cs:__imp_RtlNtStatusToDosError
0x18000e1bb  nop     dword ptr [rax+rax+00h]
0x18000e1c0  mov     edi, eax
0x18000e1c2  test    edi, edi
0x18000e1c4  jz      loc_18000E2B3
0x18000e1ca  cmp     [rbp+4Fh+FileHandle], 0
0x18000e1cf  jz      short loc_18000E1D3
0x18000e1d1  int     2Ch; Windows NT - assertion failure
0x18000e1d3  cmp     edi, 20h ; ' '
0x18000e1d6  jz      short loc_18000E249
0x18000e1d8  cmp     edi, 91h
0x18000e1de  jz      short loc_18000E249
0x18000e1e0  cmp     edi, 5
0x18000e1e3  jnz     loc_18000E2A2
0x18000e1e9  test    r14b, r14b
0x18000e1ec  jnz     loc_18000E2AA
0x18000e1f2  call    Feature_WcRemoveFileOwnershipTOCTOU__private_IsEnabledDeviceUsageNoInline
0x18000e1f7  test    eax, eax
0x18000e1f9  jnz     loc_18000E28A
0x18000e1ff  mov     rcx, [rbp+4Fh+lpFileName]; pObjectName
0x18000e203  call    WcpTakeOwnership
0x18000e208  mov     ebx, eax
0x18000e20a  test    eax, eax
0x18000e20c  js      loc_18000E2B3
0x18000e212  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x18000e216  call    cs:__imp_GetFileAttributesW
0x18000e21d  nop     dword ptr [rax+rax+00h]
0x18000e222  cmp     eax, 0FFFFFFFFh
0x18000e225  jz      short loc_18000E279
0x18000e227  test    al, 1
0x18000e229  jz      short loc_18000E244
0x18000e22b  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x18000e22f  and     eax, 0FFFFFFFEh
0x18000e232  mov     edx, eax; dwFileAttributes
0x18000e234  call    cs:__imp_SetFileAttributesW
0x18000e23b  nop     dword ptr [rax+rax+00h]
0x18000e240  test    eax, eax
0x18000e242  jz      short loc_18000E279
0x18000e244  mov     r14b, 1
0x18000e247  jmp     short loc_18000E270
0x18000e249  cmp     r12d, 19h
0x18000e24d  jz      short loc_18000E2A2
0x18000e24f  mov     ecx, r15d; dwMilliseconds
0x18000e252  call    cs:__imp_Sleep
0x18000e259  nop     dword ptr [rax+rax+00h]
0x18000e25e  lea     eax, [r15+5]
0x18000e262  inc     r12d
0x18000e265  cmp     r15d, 32h ; '2'
0x18000e269  cmovnb  eax, r15d
0x18000e26d  mov     r15d, eax
0x18000e270  mov     rdi, [rbp+4Fh+arg_8]
0x18000e274  jmp     loc_18000E0F5
0x18000e279  call    cs:__imp_GetLastError
0x18000e280  nop     dword ptr [rax+rax+00h]
0x18000e285  jmp     loc_18000E0B8
0x18000e28a  mov     r8, [rbp+4Fh+arg_8]
0x18000e28e  lea     rcx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000e292  mov     rdx, [rbp+4Fh+lpFileName]
0x18000e296  mov     r9, r13
0x18000e299  call    WcpPrivilegedRemoveFile
0x18000e29e  mov     ebx, eax
0x18000e2a0  jmp     short loc_18000E2B3
0x18000e2a2  test    edi, edi
0x18000e2a4  jg      short loc_18000E2AA
0x18000e2a6  mov     ebx, edi
0x18000e2a8  jmp     short loc_18000E2B3
0x18000e2aa  movzx   ebx, di
0x18000e2ad  or      ebx, 80070000h
0x18000e2b3  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x18000e2b7  test    rcx, rcx
0x18000e2ba  jz      short loc_18000E2CE
0x18000e2bc  call    cs:__imp_NtClose
0x18000e2c3  nop     dword ptr [rax+rax+00h]
0x18000e2c8  test    eax, eax
0x18000e2ca  jns     short loc_18000E2CE
0x18000e2cc  int     2Ch; Windows NT - assertion failure
0x18000e2ce  mov     rcx, [rbp+4Fh+Block]; Block
0x18000e2d2  test    rcx, rcx
0x18000e2d5  jz      short loc_18000E2E3
0x18000e2d7  call    cs:__imp_free
0x18000e2de  nop     dword ptr [rax+rax+00h]
0x18000e2e3  cmp     [rbp+4Fh+UnicodeString.Buffer], 0
0x18000e2e8  jz      short loc_18000E2FA
0x18000e2ea  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x18000e2ee  call    cs:__imp_RtlFreeUnicodeString
0x18000e2f5  nop     dword ptr [rax+rax+00h]
0x18000e2fa  lea     r11, [rsp+0C0h+var_20]
0x18000e302  mov     eax, ebx
0x18000e304  mov     rbx, [r11+30h]
0x18000e308  mov     rdi, [r11+40h]
0x18000e30c  mov     rsp, r11
0x18000e30f  pop     r15
0x18000e311  pop     r14
0x18000e313  pop     r13
0x18000e315  pop     r12
0x18000e317  pop     rbp
0x18000e318  retn
```
