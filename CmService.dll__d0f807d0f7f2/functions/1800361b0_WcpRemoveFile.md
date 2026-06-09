# WcpRemoveFile

- ea: `0x1800361b0`
- end: `0x1800364b6`
- name: `WcpRemoveFile`
- size: `774`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ff9c`
- `0x18003551c`

## callees

- `0x180034b38`
- `0x180034b94`
- `0x180035d00`
- `0x180036030`
- `0x1800361b0`
- `0x1800364bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036473`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036473`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180036236`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180036236`
- `ntdll!RtlFreeUnicodeString` at `0x18003648a`
- `ntdll!RtlFreeUnicodeString` at `0x18003648a`
- `ntdll!NtOpenFile` at `0x1800362b2`
- `ntdll!NtOpenFile` at `0x1800362b2`
- `ntdll!NtSetInformationFile` at `0x18003630a`
- `ntdll!NtSetInformationFile` at `0x18003630a`
- `ntdll!NtClose` at `0x180036332`
- `ntdll!NtClose` at `0x180036458`
- `ntdll!NtClose` at `0x180036332`
- `ntdll!NtClose` at `0x180036458`
- `ntdll!RtlNtStatusToDosError` at `0x180036248`
- `ntdll!RtlNtStatusToDosError` at `0x180036320`
- `ntdll!RtlNtStatusToDosError` at `0x180036350`
- `ntdll!RtlNtStatusToDosError` at `0x180036248`
- `ntdll!RtlNtStatusToDosError` at `0x180036320`
- `ntdll!RtlNtStatusToDosError` at `0x180036350`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800363ee`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800363ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036415`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800363b2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800363b2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800363d0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800363d0`

## pseudocode

```c
__int64 __fastcall WcpRemoveFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v6; // rdi
  signed int v7; // ebx
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
      v7 = WcpPrivilegedRemoveFile(&ObjectAttributes);
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
0x1800361b0  mov     rax, rsp
0x1800361b3  mov     [rax+8], rbx
0x1800361b7  mov     [rax+18h], rdi
0x1800361bb  mov     [rax+20h], r9b
0x1800361bf  mov     [rax+10h], rdx
0x1800361c3  push    rbp
0x1800361c4  push    r12
0x1800361c6  push    r13
0x1800361c8  push    r14
0x1800361ca  push    r15
0x1800361cc  lea     rbp, [rax-57h]
0x1800361d0  sub     rsp, 0A0h
0x1800361d7  xorps   xmm0, xmm0
0x1800361da  mov     [rbp+4Fh+FileInformation], 0
0x1800361e1  xor     eax, eax
0x1800361e3  mov     [rbp+4Fh+lpFileName], 0
0x1800361eb  mov     r13, r8
0x1800361ee  mov     qword ptr [rbp+4Fh+UnicodeString.Length], rax
0x1800361f2  mov     rdi, rdx
0x1800361f5  mov     [rbp+4Fh+FileHandle], rax
0x1800361f9  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800361fd  lea     r8, [rbp+4Fh+lpFileName]
0x180036201  mov     [rbp+4Fh+Block], rax
0x180036205  lea     rdx, [rbp+4Fh+Block]
0x180036209  mov     [rbp+4Fh+UnicodeString.Buffer], rax
0x18003620d  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x180036211  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x180036215  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x180036219  call    WcpConstructLongPath
0x18003621e  mov     ebx, eax
0x180036220  test    eax, eax
0x180036222  js      loc_18003644F
0x180036228  mov     rcx, [rbp+4Fh+lpFileName]
0x18003622c  lea     rdx, [rbp+4Fh+UnicodeString]
0x180036230  xor     r9d, r9d
0x180036233  xor     r8d, r8d
0x180036236  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18003623d  nop     dword ptr [rax+rax+00h]
0x180036242  test    eax, eax
0x180036244  jns     short loc_180036266
0x180036246  mov     ecx, eax; Status
0x180036248  call    cs:__imp_RtlNtStatusToDosError
0x18003624f  nop     dword ptr [rax+rax+00h]
0x180036254  mov     ebx, eax
0x180036256  test    eax, eax
0x180036258  jle     loc_18003644F
0x18003625e  movzx   ebx, ax
0x180036261  jmp     loc_180036449
0x180036266  xor     r15d, r15d
0x180036269  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180036270  xor     r14b, r14b
0x180036273  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18003627a  xor     r12d, r12d
0x18003627d  lea     rax, [rbp+4Fh+UnicodeString]
0x180036281  xorps   xmm0, xmm0
0x180036284  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x180036288  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18003628c  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180036291  mov     [rsp+0C0h+OpenOptions], 204020h; OpenOptions
0x180036299  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18003629d  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800362a1  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x1800362a9  mov     edx, 110000h; DesiredAccess
0x1800362ae  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800362b2  call    cs:__imp_NtOpenFile
0x1800362b9  nop     dword ptr [rax+rax+00h]
0x1800362be  test    eax, eax
0x1800362c0  js      loc_18003634E
0x1800362c6  cmp     [rbp+4Fh+arg_20], 0
0x1800362ca  jnz     short loc_1800362E9
0x1800362cc  mov     rdx, [rbp+4Fh+lpFileName]
0x1800362d0  mov     r9, r13
0x1800362d3  mov     rcx, [rbp+4Fh+FileHandle]
0x1800362d7  mov     r8, rdi
0x1800362da  call    EnsurePathNotRedirected
0x1800362df  mov     ebx, eax
0x1800362e1  test    eax, eax
0x1800362e3  js      loc_18003644F
0x1800362e9  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800362ed  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x1800362f1  mov     r9d, 4; Length
0x1800362f7  mov     [rbp+4Fh+FileInformation], 1
0x1800362fe  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180036302  mov     [rsp+0C0h+ShareAccess], 40h ; '@'; FileInformationClass
0x18003630a  call    cs:__imp_NtSetInformationFile
0x180036311  nop     dword ptr [rax+rax+00h]
0x180036316  test    eax, eax
0x180036318  jns     loc_18003644F
0x18003631e  mov     ecx, eax; Status
0x180036320  call    cs:__imp_RtlNtStatusToDosError
0x180036327  nop     dword ptr [rax+rax+00h]
0x18003632c  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180036330  mov     edi, eax
0x180036332  call    cs:__imp_NtClose
0x180036339  nop     dword ptr [rax+rax+00h]
0x18003633e  test    eax, eax
0x180036340  jns     short loc_180036344
0x180036342  int     2Ch; Windows NT - assertion failure
0x180036344  mov     [rbp+4Fh+FileHandle], 0
0x18003634c  jmp     short loc_18003635E
0x18003634e  mov     ecx, eax; Status
0x180036350  call    cs:__imp_RtlNtStatusToDosError
0x180036357  nop     dword ptr [rax+rax+00h]
0x18003635c  mov     edi, eax
0x18003635e  test    edi, edi
0x180036360  jz      loc_18003644F
0x180036366  cmp     [rbp+4Fh+FileHandle], 0
0x18003636b  jz      short loc_18003636F
0x18003636d  int     2Ch; Windows NT - assertion failure
0x18003636f  cmp     edi, 20h ; ' '
0x180036372  jz      short loc_1800363E5
0x180036374  cmp     edi, 91h
0x18003637a  jz      short loc_1800363E5
0x18003637c  cmp     edi, 5
0x18003637f  jnz     loc_18003643E
0x180036385  test    r14b, r14b
0x180036388  jnz     loc_180036446
0x18003638e  call    Feature_WcRemoveFileOwnershipTOCTOU__private_IsEnabledDeviceUsageNoInline
0x180036393  test    eax, eax
0x180036395  jnz     loc_180036426
0x18003639b  mov     rcx, [rbp+4Fh+lpFileName]; pObjectName
0x18003639f  call    WcpTakeOwnership
0x1800363a4  mov     ebx, eax
0x1800363a6  test    eax, eax
0x1800363a8  js      loc_18003644F
0x1800363ae  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x1800363b2  call    cs:__imp_GetFileAttributesW
0x1800363b9  nop     dword ptr [rax+rax+00h]
0x1800363be  cmp     eax, 0FFFFFFFFh
0x1800363c1  jz      short loc_180036415
0x1800363c3  test    al, 1
0x1800363c5  jz      short loc_1800363E0
0x1800363c7  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x1800363cb  and     eax, 0FFFFFFFEh
0x1800363ce  mov     edx, eax; dwFileAttributes
0x1800363d0  call    cs:__imp_SetFileAttributesW
0x1800363d7  nop     dword ptr [rax+rax+00h]
0x1800363dc  test    eax, eax
0x1800363de  jz      short loc_180036415
0x1800363e0  mov     r14b, 1
0x1800363e3  jmp     short loc_18003640C
0x1800363e5  cmp     r12d, 19h
0x1800363e9  jz      short loc_18003643E
0x1800363eb  mov     ecx, r15d; dwMilliseconds
0x1800363ee  call    cs:__imp_Sleep
0x1800363f5  nop     dword ptr [rax+rax+00h]
0x1800363fa  lea     eax, [r15+5]
0x1800363fe  inc     r12d
0x180036401  cmp     r15d, 32h ; '2'
0x180036405  cmovnb  eax, r15d
0x180036409  mov     r15d, eax
0x18003640c  mov     rdi, [rbp+4Fh+arg_8]
0x180036410  jmp     loc_180036291
0x180036415  call    cs:__imp_GetLastError
0x18003641c  nop     dword ptr [rax+rax+00h]
0x180036421  jmp     loc_180036254
0x180036426  mov     r8, [rbp+4Fh+arg_8]
0x18003642a  lea     rcx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18003642e  mov     rdx, [rbp+4Fh+lpFileName]
0x180036432  mov     r9, r13
0x180036435  call    WcpPrivilegedRemoveFile
0x18003643a  mov     ebx, eax
0x18003643c  jmp     short loc_18003644F
0x18003643e  test    edi, edi
0x180036440  jg      short loc_180036446
0x180036442  mov     ebx, edi
0x180036444  jmp     short loc_18003644F
0x180036446  movzx   ebx, di
0x180036449  or      ebx, 80070000h
0x18003644f  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180036453  test    rcx, rcx
0x180036456  jz      short loc_18003646A
0x180036458  call    cs:__imp_NtClose
0x18003645f  nop     dword ptr [rax+rax+00h]
0x180036464  test    eax, eax
0x180036466  jns     short loc_18003646A
0x180036468  int     2Ch; Windows NT - assertion failure
0x18003646a  mov     rcx, [rbp+4Fh+Block]; Block
0x18003646e  test    rcx, rcx
0x180036471  jz      short loc_18003647F
0x180036473  call    cs:__imp_free
0x18003647a  nop     dword ptr [rax+rax+00h]
0x18003647f  cmp     [rbp+4Fh+UnicodeString.Buffer], 0
0x180036484  jz      short loc_180036496
0x180036486  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x18003648a  call    cs:__imp_RtlFreeUnicodeString
0x180036491  nop     dword ptr [rax+rax+00h]
0x180036496  lea     r11, [rsp+0C0h+var_20]
0x18003649e  mov     eax, ebx
0x1800364a0  mov     rbx, [r11+30h]
0x1800364a4  mov     rdi, [r11+40h]
0x1800364a8  mov     rsp, r11
0x1800364ab  pop     r15
0x1800364ad  pop     r14
0x1800364af  pop     r13
0x1800364b1  pop     r12
0x1800364b3  pop     rbp
0x1800364b4  retn
```
