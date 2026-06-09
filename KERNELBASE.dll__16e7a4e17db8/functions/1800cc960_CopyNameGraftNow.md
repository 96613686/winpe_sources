# CopyNameGraftNow

- ea: `0x1800cc960`
- end: `0x1800cd098`
- name: `CopyNameGraftNow`
- size: `1848`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, int, int, int, __int64, HANDLE Event)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f0120`

## callees

- `0x1800134a0`
- `0x180048f30`
- `0x1800cc960`
- `0x1800cd0f0`
- `0x18012daf0`
- `0x180188f10`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800cccc1`
- `ntdll!NtQueryInformationFile` at `0x1800cccc1`
- `ntdll!NtSetInformationFile` at `0x1800ccd0d`
- `ntdll!NtSetInformationFile` at `0x1800ccdb1`
- `ntdll!NtSetInformationFile` at `0x1800ccd0d`
- `ntdll!NtSetInformationFile` at `0x1800ccdb1`
- `ntdll!NtFsControlFile` at `0x1800ccb21`
- `ntdll!NtFsControlFile` at `0x1800ccc8b`
- `ntdll!NtFsControlFile` at `0x1800ccb21`
- `ntdll!NtFsControlFile` at `0x1800ccc8b`
- `ntdll!NtCreateFile` at `0x1800ccc08`
- `ntdll!NtCreateFile` at `0x1800ccd84`
- `ntdll!NtCreateFile` at `0x1800ccc08`
- `ntdll!NtCreateFile` at `0x1800ccd84`
- `ntdll!RtlSetLastWin32Error` at `0x1800ccea9`
- `ntdll!RtlSetLastWin32Error` at `0x1800ccef4`
- `ntdll!RtlSetLastWin32Error` at `0x1800ccea9`
- `ntdll!RtlSetLastWin32Error` at `0x1800ccef4`
- `ntdll!NtWaitForSingleObject` at `0x1800ccf16`
- `ntdll!NtWaitForSingleObject` at `0x1800ccf16`
- `ntdll!RtlEqualUnicodeString` at `0x1800ccad4`
- `ntdll!RtlEqualUnicodeString` at `0x1800ccad4`
- `ntdll!RtlReleasePrivilege` at `0x1800ccffb`
- `ntdll!RtlReleasePrivilege` at `0x18018b6e5`
- `ntdll!RtlReleasePrivilege` at `0x1800ccffb`
- `ntdll!RtlReleasePrivilege` at `0x18018b6e5`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800cca6f`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800ccaa3`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800cca6f`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800ccaa3`
- `ntdll!RtlAcquirePrivilege` at `0x1800ccf73`
- `ntdll!RtlAcquirePrivilege` at `0x1800ccf73`
- `ntdll!RtlGetCurrentTransaction` at `0x1800cce80`
- `ntdll!RtlGetCurrentTransaction` at `0x1800cce80`
- `ntdll!RtlFreeHeap` at `0x1800cd02a`
- `ntdll!RtlFreeHeap` at `0x1800cd047`
- `ntdll!RtlFreeHeap` at `0x1800cd05f`
- `ntdll!RtlFreeHeap` at `0x18018b71b`
- `ntdll!RtlFreeHeap` at `0x18018b737`
- `ntdll!RtlFreeHeap` at `0x18018b753`
- `ntdll!RtlFreeHeap` at `0x1800cd02a`
- `ntdll!RtlFreeHeap` at `0x1800cd047`
- `ntdll!RtlFreeHeap` at `0x1800cd05f`
- `ntdll!RtlFreeHeap` at `0x18018b71b`
- `ntdll!RtlFreeHeap` at `0x18018b737`
- `ntdll!RtlFreeHeap` at `0x18018b753`
- `ntdll!RtlAllocateHeap` at `0x1800cca44`
- `ntdll!RtlAllocateHeap` at `0x1800cca44`
- `ext-ms-win-kernel32-file-l1-1-0!SetVolumeMountPointWStub` at `0x1800ccfbd`
- `ext-ms-win-kernel32-file-l1-1-0!SetVolumeMountPointWStub` at `0x1800ccfbd`

## pseudocode

```c
__int64 __fastcall CopyNameGraftNow(
        HANDLE FileHandle,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        _BYTE *a8,
        HANDLE Event)
{
  NTSTATUS Status; // ebx
  int Information; // r12d
  unsigned __int16 *OutputBuffer; // r14
  int v15; // eax
  const WCHAR *v16; // rsi
  int v17; // eax
  ULONG v18; // eax
  NTSTATUS v19; // eax
  unsigned int v20; // edi
  PWSTR v21; // rax
  __int64 v22; // rcx
  NTSTATUS v23; // eax
  int v24; // eax
  HANDLE FileHandlea; // [rsp+68h] [rbp-120h] BYREF
  int v27; // [rsp+70h] [rbp-118h]
  ULONG Privilege[2]; // [rsp+78h] [rbp-110h] BYREF
  PVOID ReturnedState; // [rsp+80h] [rbp-108h] BYREF
  PVOID P; // [rsp+88h] [rbp-100h]
  PVOID Buffer; // [rsp+90h] [rbp-F8h]
  UNICODE_STRING String1; // [rsp+98h] [rbp-F0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-E0h] BYREF
  UNICODE_STRING String2; // [rsp+B8h] [rbp-D0h] BYREF
  struct _IO_STATUS_BLOCK v35; // [rsp+C8h] [rbp-C0h] BYREF
  int v36; // [rsp+D8h] [rbp-B0h]
  __int64 v37; // [rsp+E0h] [rbp-A8h]
  unsigned __int16 *v38; // [rsp+E8h] [rbp-A0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-98h] BYREF
  _OWORD FileInformation[2]; // [rsp+120h] [rbp-68h] BYREF
  __int64 v41; // [rsp+140h] [rbp-48h]

  *(_QWORD *)Privilege = a3;
  v37 = a3;
  Status = 0;
  FileHandlea = (HANDLE)-1LL;
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v41 = 0;
  v36 = 0;
  String1 = 0;
  String2 = 0;
  P = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  v35 = 0;
  Information = 0;
  v27 = 0;
  ReturnedState = 0;
  OutputBuffer = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x4000u);
  v38 = OutputBuffer;
  if ( !OutputBuffer )
  {
    BaseSetLastNTError(3221225495LL);
    return 0;
  }
  v15 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &String1, 0, 0);
  if ( v15 < 0 )
  {
    if ( v15 == -1073741801 || v15 == -1073741670 )
      BaseSetLastNTError((unsigned int)v15);
    else
      RtlSetLastWin32Error(3u);
    FileHandlea = (HANDLE)-1LL;
    v16 = *(const WCHAR **)Privilege;
    goto LABEL_48;
  }
  P = String1.Buffer;
  v16 = *(const WCHAR **)Privilege;
  v17 = RtlDosPathNameToNtPathName_U_WithStatus(*(_QWORD *)Privilege, &String2, 0, 0);
  if ( v17 < 0 )
  {
    if ( v17 == -1073741801 || v17 == -1073741670 )
      BaseSetLastNTError((unsigned int)v17);
    else
      RtlSetLastWin32Error(3u);
    goto LABEL_53;
  }
  Buffer = String2.Buffer;
  if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
  {
LABEL_53:
    FileHandlea = (HANDLE)-1LL;
    goto LABEL_48;
  }
  Status = NtFsControlFile(FileHandle, Event, 0, 0, &IoStatusBlock, 0x900A8u, 0, 0, OutputBuffer, 0x4000u);
  if ( Status == 259 )
  {
    do
    {
      v23 = NtWaitForSingleObject(Event, 1u, 0);
      Status = v23;
      if ( v23 >= 0 && v23 != 257 )
        Status = IoStatusBlock.Status;
    }
    while ( Status == 257 );
  }
  if ( Status < 0 )
    goto LABEL_46;
  if ( *(_DWORD *)OutputBuffer == -1610612733 )
  {
    if ( *(_DWORD *)OutputBuffer != -1610612724 )
      goto LABEL_9;
  }
  else if ( *(_DWORD *)OutputBuffer != -1610612724 )
  {
    v22 = 3221225523LL;
    goto LABEL_47;
  }
  Privilege[0] = 35;
  v19 = RtlAcquirePrivilege(Privilege, 1u, 0, &ReturnedState);
  Status = v19;
  if ( v19 < 0 )
    goto LABEL_62;
LABEL_9:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &String2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (a4 & 1) != 0 )
    v18 = !(*a8 & 1) + 2;
  else
    v18 = 2 * (*(_DWORD *)a8 & 1);
  Status = NtCreateFile(&FileHandlea, 0xC0000000, &ObjectAttributes, &v35, 0, 0, 3u, v18, a4 | 0x200000, 0, 0);
  if ( Status < 0 )
  {
    FileHandlea = (HANDLE)-1LL;
LABEL_46:
    v22 = (unsigned int)Status;
    goto LABEL_47;
  }
  Information = v35.Information;
  v27 = v35.Information;
  if ( String1.Length == 96 )
  {
    v21 = String1.Buffer;
  }
  else
  {
    if ( String1.Length != 98 )
      goto LABEL_14;
    v21 = String1.Buffer;
    if ( String1.Buffer[48] != 92 )
      goto LABEL_14;
  }
  if ( *v21 != 92
    || v21[1] != 63 && v21[1] != 92
    || v21[2] != 63
    || v21[3] != 92
    || v21[4] != 86
    || v21[5] != 111
    || v21[6] != 108
    || v21[7] != 117
    || v21[8] != 109
    || v21[9] != 101
    || v21[10] != 123
    || v21[19] != 45
    || v21[24] != 45
    || v21[29] != 45
    || v21[34] != 45
    || v21[47] != 125 )
  {
LABEL_14:
    v19 = NtFsControlFile(FileHandlea, 0, 0, 0, &IoStatusBlock, 0x900A4u, OutputBuffer, OutputBuffer[2] + 8, 0, 0);
    Status = v19;
    if ( v19 >= 0 )
    {
LABEL_15:
      v19 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      Status = v19;
      if ( v19 >= 0 )
      {
        FileInformation[0] = 0;
        LODWORD(v41) = 0;
        Status = NtSetInformationFile(FileHandlea, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
        if ( Status == -1073741757 )
        {
          CloseHandle(FileHandlea);
          Status = NtCreateFile(&FileHandlea, 0x100u, &ObjectAttributes, &v35, 0, 0, 0, 1u, a4 | 0x200000, 0, 0);
          if ( Status >= 0 )
            Status = NtSetInformationFile(FileHandlea, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
        }
        v20 = 1;
        goto LABEL_71;
      }
    }
LABEL_62:
    v22 = (unsigned int)v19;
    goto LABEL_47;
  }
  if ( !RtlGetCurrentTransaction() )
  {
    if ( (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() )
    {
      v24 = SetVolumeMountPointWStub(v16, OutputBuffer + 8);
    }
    else
    {
      BaseSetLastNTError(3221225659LL);
      v24 = 0;
    }
    if ( !v24 )
      goto LABEL_48;
    goto LABEL_15;
  }
  v22 = 3221225659LL;
LABEL_47:
  BaseSetLastNTError(v22);
LABEL_48:
  v20 = 0;
LABEL_71:
  if ( FileHandlea != (HANDLE)-1LL )
    CloseHandle(FileHandlea);
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  if ( Status < 0 && Information == 2 )
    DeleteFileW(v16);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBuffer);
  return v20;
}

```

## disassembly

```asm
0x1800cc960  mov     r11, rsp
0x1800cc963  push    rbx
0x1800cc964  push    rsi
0x1800cc965  push    rdi
0x1800cc966  push    r12
0x1800cc968  push    r13
0x1800cc96a  push    r14
0x1800cc96c  push    r15
0x1800cc96e  sub     rsp, 150h
0x1800cc975  mov     rax, cs:__security_cookie
0x1800cc97c  xor     rax, rsp
0x1800cc97f  mov     [rsp+188h+var_40], rax
0x1800cc987  mov     r15d, r9d
0x1800cc98a  mov     rax, r8
0x1800cc98d  mov     qword ptr [rsp+188h+Privilege], rax
0x1800cc992  mov     rsi, rdx
0x1800cc995  mov     r13, rcx
0x1800cc998  mov     [rsp+188h+var_A8], rax
0x1800cc9a0  mov     rdi, [rsp+188h+Event]
0x1800cc9a8  xor     ecx, ecx
0x1800cc9aa  mov     ebx, ecx
0x1800cc9ac  mov     [rsp+188h+var_128], ecx
0x1800cc9b0  mov     [rsp+188h+var_124], ecx
0x1800cc9b4  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800cc9bd  xorps   xmm0, xmm0
0x1800cc9c0  movups  xmmword ptr [rsp+188h+var_E0], xmm0
0x1800cc9c8  xorps   xmm1, xmm1
0x1800cc9cb  xor     eax, eax
0x1800cc9cd  movups  xmmword ptr [r11-68h], xmm1
0x1800cc9d2  movups  xmmword ptr [r11-58h], xmm1
0x1800cc9d7  mov     [r11-48h], rax
0x1800cc9db  mov     [rsp+188h+var_B0], ecx
0x1800cc9e2  movups  xmmword ptr [rsp+188h+String1.Length], xmm0
0x1800cc9ea  movups  xmmword ptr [rsp+188h+String2.Length], xmm1
0x1800cc9f2  mov     [r11-100h], rcx
0x1800cc9f9  mov     [r11-0F8h], rcx
0x1800cca00  movups  xmmword ptr [rsp+188h+ObjectAttributes.Length], xmm0
0x1800cca08  movups  xmmword ptr [rsp+188h+ObjectAttributes.ObjectName], xmm0
0x1800cca10  movups  xmmword ptr [r11-7Ch], xmm0
0x1800cca15  movups  xmmword ptr [rsp+188h+var_C0], xmm0
0x1800cca1d  mov     r12d, ecx
0x1800cca20  mov     [rsp+188h+var_118], ecx
0x1800cca24  mov     [r11-108h], rcx
0x1800cca2b  mov     rcx, gs:60h
0x1800cca34  mov     r8d, 4000h; Size
0x1800cca3a  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800cca40  mov     rcx, [rcx+30h]; HeapHandle
0x1800cca44  call    cs:__imp_RtlAllocateHeap
0x1800cca4a  mov     r14, rax
0x1800cca4d  mov     [rsp+188h+var_A0], rax
0x1800cca55  test    rax, rax
0x1800cca58  jz      loc_1800CD08A
0x1800cca5e  xor     r9d, r9d
0x1800cca61  xor     r8d, r8d
0x1800cca64  lea     rdx, [rsp+188h+String1]
0x1800cca6c  mov     rcx, rsi
0x1800cca6f  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800cca75  test    eax, eax
0x1800cca77  js      loc_1800CCE96
0x1800cca7d  mov     rax, [rsp+188h+String1.Buffer]
0x1800cca85  mov     [rsp+188h+P], rax
0x1800cca8d  xor     r9d, r9d
0x1800cca90  xor     r8d, r8d
0x1800cca93  lea     rdx, [rsp+188h+String2]
0x1800cca9b  mov     rsi, qword ptr [rsp+188h+Privilege]
0x1800ccaa0  mov     rcx, rsi
0x1800ccaa3  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800ccaa9  test    eax, eax
0x1800ccaab  js      loc_1800CCEE1
0x1800ccab1  mov     rax, [rsp+188h+String2.Buffer]
0x1800ccab9  mov     [rsp+188h+var_F8], rax
0x1800ccac1  mov     r8b, 1; CaseInsensitive
0x1800ccac4  lea     rdx, [rsp+188h+String2]; String2
0x1800ccacc  lea     rcx, [rsp+188h+String1]; String1
0x1800ccad4  call    cs:__imp_RtlEqualUnicodeString
0x1800ccada  test    al, al
0x1800ccadc  jnz     loc_1800CCF03
0x1800ccae2  mov     [rsp+188h+OutputBufferLength], 4000h; OutputBufferLength
0x1800ccaea  mov     [rsp+188h+OutputBuffer], r14; OutputBuffer
0x1800ccaef  mov     [rsp+188h+InputBufferLength], 0; InputBufferLength
0x1800ccaf7  mov     [rsp+188h+InputBuffer], 0; InputBuffer
0x1800ccb00  mov     [rsp+188h+FsControlCode], 900A8h; FsControlCode
0x1800ccb08  lea     rax, [rsp+188h+var_E0]
0x1800ccb10  mov     [rsp+188h+IoStatusBlock], rax; IoStatusBlock
0x1800ccb15  xor     r9d, r9d; ApcContext
0x1800ccb18  xor     r8d, r8d; ApcRoutine
0x1800ccb1b  mov     rdx, rdi; Event
0x1800ccb1e  mov     rcx, r13; FileHandle
0x1800ccb21  call    cs:__imp_NtFsControlFile
0x1800ccb27  mov     ebx, eax
0x1800ccb29  mov     [rsp+188h+var_128], eax
0x1800ccb2d  cmp     eax, 103h
0x1800ccb32  jz      loc_1800CCF0E
0x1800ccb38  test    ebx, ebx
0x1800ccb3a  js      loc_1800CCED1
0x1800ccb40  cmp     dword ptr [r14], 0A0000003h
0x1800ccb47  jnz     loc_1800CCF44
0x1800ccb4d  cmp     dword ptr [r14], 0A000000Ch
0x1800ccb54  jz      loc_1800CCF57
0x1800ccb5a  mov     [rsp+188h+ObjectAttributes.Length], 30h ; '0'
0x1800ccb65  mov     [rsp+188h+ObjectAttributes.RootDirectory], 0
0x1800ccb71  mov     [rsp+188h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ccb7c  lea     rax, [rsp+188h+String2]
0x1800ccb84  mov     [rsp+188h+ObjectAttributes.ObjectName], rax
0x1800ccb8c  xorps   xmm0, xmm0
0x1800ccb8f  movdqu  xmmword ptr [rsp+188h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ccb98  mov     rax, [rsp+188h+arg_38]
0x1800ccba0  mov     eax, [rax]
0x1800ccba2  and     eax, 1
0x1800ccba5  mov     edi, r15d
0x1800ccba8  bts     edi, 15h
0x1800ccbac  mov     [rsp+188h+EaLength], 0; EaLength
0x1800ccbb4  lea     r9, [rsp+188h+var_C0]; IoStatusBlock
0x1800ccbbc  lea     r8, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x1800ccbc4  mov     edx, 0C0000000h; DesiredAccess
0x1800ccbc9  lea     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800ccbce  mov     qword ptr [rsp+188h+OutputBufferLength], 0; EaBuffer
0x1800ccbd7  mov     dword ptr [rsp+188h+OutputBuffer], edi; CreateOptions
0x1800ccbdb  test    r15b, 1
0x1800ccbdf  jz      loc_1800CCF8E
0x1800ccbe5  xor     eax, 1
0x1800ccbe8  add     eax, 2
0x1800ccbeb  mov     [rsp+188h+InputBufferLength], eax; CreateDisposition
0x1800ccbef  mov     dword ptr [rsp+188h+InputBuffer], 3; ShareAccess
0x1800ccbf7  mov     [rsp+188h+FsControlCode], 0; FileAttributes
0x1800ccbff  mov     [rsp+188h+IoStatusBlock], 0; AllocationSize
0x1800ccc08  call    cs:__imp_NtCreateFile
0x1800ccc0e  mov     [rsp+188h+var_128], eax
0x1800ccc12  mov     ebx, eax
0x1800ccc14  test    eax, eax
0x1800ccc16  js      loc_1800CCEC8
0x1800ccc1c  mov     r12, [rsp+188h+var_C0.Information]
0x1800ccc24  mov     [rsp+188h+var_118], r12d
0x1800ccc29  cmp     [rsp+188h+String1.Length], 60h ; '`'
0x1800ccc32  jz      loc_1800CCDC2
0x1800ccc38  cmp     [rsp+188h+String1.Length], 62h ; 'b'
0x1800ccc41  jz      loc_1800CCF95
0x1800ccc47  movzx   eax, word ptr [r14+4]
0x1800ccc4c  add     eax, 8
0x1800ccc4f  mov     [rsp+188h+OutputBufferLength], 0; OutputBufferLength
0x1800ccc57  mov     [rsp+188h+OutputBuffer], 0; OutputBuffer
0x1800ccc60  mov     [rsp+188h+InputBufferLength], eax; InputBufferLength
0x1800ccc64  mov     [rsp+188h+InputBuffer], r14; InputBuffer
0x1800ccc69  mov     [rsp+188h+FsControlCode], 900A4h; FsControlCode
0x1800ccc71  lea     rax, [rsp+188h+var_E0]
0x1800ccc79  mov     [rsp+188h+IoStatusBlock], rax; IoStatusBlock
0x1800ccc7e  xor     r9d, r9d; ApcContext
0x1800ccc81  xor     r8d, r8d; ApcRoutine
0x1800ccc84  xor     edx, edx; Event
0x1800ccc86  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800ccc8b  call    cs:__imp_NtFsControlFile
0x1800ccc91  mov     ebx, eax
0x1800ccc93  mov     [rsp+188h+var_128], eax
0x1800ccc97  test    eax, eax
0x1800ccc99  js      loc_1800CCF87
0x1800ccc9f  mov     r15d, 4
0x1800ccca5  mov     dword ptr [rsp+188h+IoStatusBlock], r15d; FileInformationClass
0x1800cccaa  lea     r9d, [r15+24h]; Length
0x1800cccae  lea     r8, [rsp+188h+FileInformation]; FileInformation
0x1800cccb6  lea     rdx, [rsp+188h+var_E0]; IoStatusBlock
0x1800cccbe  mov     rcx, r13; FileHandle
0x1800cccc1  call    cs:__imp_NtQueryInformationFile
0x1800cccc7  mov     ebx, eax
0x1800cccc9  mov     [rsp+188h+var_128], eax
0x1800ccccd  test    eax, eax
0x1800ccccf  js      loc_1800CCF87
0x1800cccd5  xorps   xmm0, xmm0
0x1800cccd8  movdqu  [rsp+188h+FileInformation], xmm0
0x1800ccce1  mov     dword ptr [rsp+188h+var_48], 0
0x1800cccec  mov     dword ptr [rsp+188h+IoStatusBlock], r15d; FileInformationClass
0x1800cccf1  lea     r13d, [r15+24h]
0x1800cccf5  mov     r9d, r13d; Length
0x1800cccf8  lea     r8, [rsp+188h+FileInformation]; FileInformation
0x1800ccd00  lea     rdx, [rsp+188h+var_E0]; IoStatusBlock
0x1800ccd08  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800ccd0d  call    cs:__imp_NtSetInformationFile
0x1800ccd13  mov     ebx, eax
0x1800ccd15  mov     [rsp+188h+var_128], eax
0x1800ccd19  cmp     eax, 0C0000043h
0x1800ccd1e  jz      short loc_1800CCD2A
0x1800ccd20  mov     edi, 1
0x1800ccd25  jmp     loc_1800CCFDE
0x1800ccd2a  mov     rcx, [rsp+188h+FileHandle]; hObject
0x1800ccd2f  call    CloseHandle
0x1800ccd34  mov     [rsp+188h+EaLength], 0; EaLength
0x1800ccd3c  mov     qword ptr [rsp+188h+OutputBufferLength], 0; EaBuffer
0x1800ccd45  mov     dword ptr [rsp+188h+OutputBuffer], edi; CreateOptions
0x1800ccd49  mov     [rsp+188h+InputBufferLength], 1; CreateDisposition
0x1800ccd51  mov     dword ptr [rsp+188h+InputBuffer], 0; ShareAccess
0x1800ccd59  mov     [rsp+188h+FsControlCode], 0; FileAttributes
0x1800ccd61  mov     [rsp+188h+IoStatusBlock], 0; AllocationSize
0x1800ccd6a  lea     r9, [rsp+188h+var_C0]; IoStatusBlock
0x1800ccd72  lea     r8, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x1800ccd7a  mov     edx, 100h; DesiredAccess
0x1800ccd7f  lea     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800ccd84  call    cs:__imp_NtCreateFile
0x1800ccd8a  mov     ebx, eax
0x1800ccd8c  mov     [rsp+188h+var_128], eax
0x1800ccd90  test    eax, eax
0x1800ccd92  js      short loc_1800CCD20
0x1800ccd94  mov     dword ptr [rsp+188h+IoStatusBlock], r15d; FileInformationClass
0x1800ccd99  mov     r9d, r13d; Length
0x1800ccd9c  lea     r8, [rsp+188h+FileInformation]; FileInformation
0x1800ccda4  lea     rdx, [rsp+188h+var_E0]; IoStatusBlock
0x1800ccdac  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800ccdb1  call    cs:__imp_NtSetInformationFile
0x1800ccdb7  mov     ebx, eax
0x1800ccdb9  mov     [rsp+188h+var_128], eax
0x1800ccdbd  jmp     loc_1800CCD20
0x1800ccdc2  mov     rax, [rsp+188h+String1.Buffer]
0x1800ccdca  cmp     word ptr [rax], 5Ch ; '\'
0x1800ccdce  jnz     loc_1800CCC47
0x1800ccdd4  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800ccdd9  jz      short loc_1800CCDE6
0x1800ccddb  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800ccde0  jnz     loc_1800CCC47
0x1800ccde6  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800ccdeb  jnz     loc_1800CCC47
0x1800ccdf1  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800ccdf6  jnz     loc_1800CCC47
0x1800ccdfc  cmp     word ptr [rax+8], 56h ; 'V'
0x1800cce01  jnz     loc_1800CCC47
0x1800cce07  cmp     word ptr [rax+0Ah], 6Fh ; 'o'
0x1800cce0c  jnz     loc_1800CCC47
0x1800cce12  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x1800cce17  jnz     loc_1800CCC47
0x1800cce1d  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x1800cce22  jnz     loc_1800CCC47
0x1800cce28  cmp     word ptr [rax+10h], 6Dh ; 'm'
0x1800cce2d  jnz     loc_1800CCC47
0x1800cce33  cmp     word ptr [rax+12h], 65h ; 'e'
0x1800cce38  jnz     loc_1800CCC47
0x1800cce3e  cmp     word ptr [rax+14h], 7Bh ; '{'
0x1800cce43  jnz     loc_1800CCC47
0x1800cce49  mov     cx, 2Dh ; '-'
0x1800cce4d  cmp     [rax+26h], cx
0x1800cce51  jnz     loc_1800CCC47
0x1800cce57  cmp     [rax+30h], cx
0x1800cce5b  jnz     loc_1800CCC47
0x1800cce61  cmp     [rax+3Ah], cx
0x1800cce65  jnz     loc_1800CCC47
0x1800cce6b  cmp     [rax+44h], cx
0x1800cce6f  jnz     loc_1800CCC47
0x1800cce75  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x1800cce7a  jnz     loc_1800CCC47
0x1800cce80  call    cs:__imp_RtlGetCurrentTransaction
0x1800cce86  test    rax, rax
0x1800cce89  jz      loc_1800CCFAD
0x1800cce8f  mov     ecx, 0C00000BBh
0x1800cce94  jmp     short loc_1800CCED3
0x1800cce96  cmp     eax, 0C0000017h
0x1800cce9b  jz      short loc_1800CCEB1
0x1800cce9d  cmp     eax, 0C000009Ah
0x1800ccea2  jz      short loc_1800CCEB1
0x1800ccea4  mov     ecx, 3; LastError
0x1800ccea9  call    cs:__imp_RtlSetLastWin32Error
0x1800cceaf  jmp     short loc_1800CCEB8
0x1800cceb1  mov     ecx, eax
0x1800cceb3  call    BaseSetLastNTError
0x1800cceb8  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800ccec1  mov     rsi, qword ptr [rsp+188h+Privilege]
0x1800ccec6  jmp     short loc_1800CCED8
0x1800ccec8  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800cced1  mov     ecx, ebx
0x1800cced3  call    BaseSetLastNTError
0x1800cced8  mov     edi, [rsp+188h+var_124]
0x1800ccedc  jmp     loc_1800CCFDE
0x1800ccee1  cmp     eax, 0C0000017h
0x1800ccee6  jz      short loc_1800CCEFC
0x1800ccee8  cmp     eax, 0C000009Ah
0x1800cceed  jz      short loc_1800CCEFC
0x1800cceef  mov     ecx, 3; LastError
0x1800ccef4  call    cs:__imp_RtlSetLastWin32Error
0x1800ccefa  jmp     short loc_1800CCF03
0x1800ccefc  mov     ecx, eax
0x1800ccefe  call    BaseSetLastNTError
0x1800ccf03  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800ccf0c  jmp     short loc_1800CCED8
0x1800ccf0e  xor     r8d, r8d; Timeout
0x1800ccf11  mov     dl, 1; Alertable
0x1800ccf13  mov     rcx, rdi; Handle
0x1800ccf16  call    cs:__imp_NtWaitForSingleObject
0x1800ccf1c  mov     ebx, eax
0x1800ccf1e  mov     [rsp+188h+var_128], eax
0x1800ccf22  test    eax, eax
0x1800ccf24  js      short loc_1800CCF37
0x1800ccf26  cmp     eax, 101h
0x1800ccf2b  cmovnz  ebx, dword ptr [rsp+188h+var_E0]
0x1800ccf33  mov     [rsp+188h+var_128], ebx
0x1800ccf37  cmp     ebx, 101h
0x1800ccf3d  jz      short loc_1800CCF0E
0x1800ccf3f  jmp     loc_1800CCB38
0x1800ccf44  cmp     dword ptr [r14], 0A000000Ch
0x1800ccf4b  jz      short loc_1800CCF57
0x1800ccf4d  mov     ecx, 0C0000033h
0x1800ccf52  jmp     loc_1800CCED3
0x1800ccf57  mov     [rsp+188h+Privilege], 23h ; '#'
0x1800ccf5f  lea     r9, [rsp+188h+ReturnedState]; ReturnedState
0x1800ccf67  xor     r8d, r8d; Flags
0x1800ccf6a  lea     edx, [r8+1]; NumPriv
  ... truncated ...
```
