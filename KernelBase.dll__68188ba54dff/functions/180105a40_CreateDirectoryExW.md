# CreateDirectoryExW

- ea: `0x180105a40`
- end: `0x180106984`
- name: `CreateDirectoryExW`
- size: `3908`
- prototype: `BOOL __stdcall(LPCWSTR lpTemplateDirectory, LPCWSTR lpNewDirectory, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x180022450`
- `0x180048f30`
- `0x1800cfa60`
- `0x1800d061c`
- `0x180105a40`
- `0x18012cd60`
- `0x18012daf0`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180105b15`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180105d5e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180105b15`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180105d5e`
- `ntdll!RtlReleaseRelativeName` at `0x180105bf7`
- `ntdll!RtlReleaseRelativeName` at `0x180105c58`
- `ntdll!RtlReleaseRelativeName` at `0x180105d6c`
- `ntdll!RtlReleaseRelativeName` at `0x180105dc8`
- `ntdll!RtlReleaseRelativeName` at `0x180105dd2`
- `ntdll!RtlReleaseRelativeName` at `0x180105e1c`
- `ntdll!RtlReleaseRelativeName` at `0x180105ec2`
- `ntdll!RtlReleaseRelativeName` at `0x180105f46`
- `ntdll!RtlReleaseRelativeName` at `0x18010601a`
- `ntdll!RtlReleaseRelativeName` at `0x180106109`
- `ntdll!RtlReleaseRelativeName` at `0x1801061b9`
- `ntdll!RtlReleaseRelativeName` at `0x18010623f`
- `ntdll!RtlReleaseRelativeName` at `0x180105bf7`
- `ntdll!RtlReleaseRelativeName` at `0x180105c58`
- `ntdll!RtlReleaseRelativeName` at `0x180105d6c`
- `ntdll!RtlReleaseRelativeName` at `0x180105dc8`
- `ntdll!RtlReleaseRelativeName` at `0x180105dd2`
- `ntdll!RtlReleaseRelativeName` at `0x180105e1c`
- `ntdll!RtlReleaseRelativeName` at `0x180105ec2`
- `ntdll!RtlReleaseRelativeName` at `0x180105f46`
- `ntdll!RtlReleaseRelativeName` at `0x18010601a`
- `ntdll!RtlReleaseRelativeName` at `0x180106109`
- `ntdll!RtlReleaseRelativeName` at `0x1801061b9`
- `ntdll!RtlReleaseRelativeName` at `0x18010623f`
- `ntdll!NtQueryInformationFile` at `0x180105c48`
- `ntdll!NtQueryInformationFile` at `0x180105cab`
- `ntdll!NtQueryInformationFile` at `0x180105d2d`
- `ntdll!NtQueryInformationFile` at `0x180105f36`
- `ntdll!NtQueryInformationFile` at `0x1801066f4`
- `ntdll!NtQueryInformationFile` at `0x180105c48`
- `ntdll!NtQueryInformationFile` at `0x180105cab`
- `ntdll!NtQueryInformationFile` at `0x180105d2d`
- `ntdll!NtQueryInformationFile` at `0x180105f36`
- `ntdll!NtQueryInformationFile` at `0x1801066f4`
- `ntdll!NtOpenFile` at `0x180105bb5`
- `ntdll!NtOpenFile` at `0x180105be3`
- `ntdll!NtOpenFile` at `0x180105cfe`
- `ntdll!NtOpenFile` at `0x180105bb5`
- `ntdll!NtOpenFile` at `0x180105be3`
- `ntdll!NtOpenFile` at `0x180105cfe`
- `ntdll!NtSetInformationFile` at `0x180106673`
- `ntdll!NtSetInformationFile` at `0x1801066a2`
- `ntdll!NtSetInformationFile` at `0x180106673`
- `ntdll!NtSetInformationFile` at `0x1801066a2`
- `ntdll!NtFsControlFile` at `0x18010631b`
- `ntdll!NtFsControlFile` at `0x180106405`
- `ntdll!NtFsControlFile` at `0x18010631b`
- `ntdll!NtFsControlFile` at `0x180106405`
- `ntdll!NtCreateFile` at `0x18010617a`
- `ntdll!NtCreateFile` at `0x18010622a`
- `ntdll!NtCreateFile` at `0x1801067e0`
- `ntdll!NtCreateFile` at `0x18010617a`
- `ntdll!NtCreateFile` at `0x18010622a`
- `ntdll!NtCreateFile` at `0x1801067e0`
- `ntdll!RtlSetLastWin32Error` at `0x180105b24`
- `ntdll!RtlSetLastWin32Error` at `0x180106631`
- `ntdll!RtlSetLastWin32Error` at `0x180105b24`
- `ntdll!RtlSetLastWin32Error` at `0x180106631`
- `ntdll!RtlEqualUnicodeString` at `0x180105dba`
- `ntdll!RtlEqualUnicodeString` at `0x180105dba`
- `ntdll!RtlReleasePrivilege` at `0x180106192`
- `ntdll!RtlReleasePrivilege` at `0x180106192`
- `ntdll!NtQueryEaFile` at `0x1801060b7`
- `ntdll!NtQueryEaFile` at `0x1801060b7`
- `ntdll!RtlAcquirePrivilege` at `0x180106005`
- `ntdll!RtlAcquirePrivilege` at `0x180106005`
- `ntdll!RtlIsDosDeviceName_U` at `0x18010628f`
- `ntdll!RtlIsDosDeviceName_U` at `0x18010628f`
- `ntdll!RtlInitUnicodeStringEx` at `0x180106539`
- `ntdll!RtlInitUnicodeStringEx` at `0x180106539`
- `ntdll!NtClose` at `0x180105d8e`
- `ntdll!NtClose` at `0x180105e0c`
- `ntdll!NtClose` at `0x180106282`
- `ntdll!NtClose` at `0x1801062da`
- `ntdll!NtClose` at `0x1801062e4`
- `ntdll!NtClose` at `0x180106343`
- `ntdll!NtClose` at `0x18010634d`
- `ntdll!NtClose` at `0x180106384`
- `ntdll!NtClose` at `0x18010638e`
- `ntdll!NtClose` at `0x18010642a`
- `ntdll!NtClose` at `0x180106434`
- `ntdll!NtClose` at `0x1801068f4`
- `ntdll!NtClose` at `0x180106904`
- `ntdll!NtClose` at `0x180106940`
- `ntdll!NtClose` at `0x18010694f`
- `ntdll!NtClose` at `0x180105d8e`
- `ntdll!NtClose` at `0x180105e0c`
- `ntdll!NtClose` at `0x180106282`
- `ntdll!NtClose` at `0x1801062da`
- `ntdll!NtClose` at `0x1801062e4`
- `ntdll!NtClose` at `0x180106343`
- `ntdll!NtClose` at `0x18010634d`
- `ntdll!NtClose` at `0x180106384`
- `ntdll!NtClose` at `0x18010638e`
- `ntdll!NtClose` at `0x18010642a`
- `ntdll!NtClose` at `0x180106434`
- `ntdll!NtClose` at `0x1801068f4`
- `ntdll!NtClose` at `0x180106904`
- `ntdll!NtClose` at `0x180106940`
- `ntdll!NtClose` at `0x18010694f`
- `ntdll!RtlFreeHeap` at `0x180105c0f`
- `ntdll!RtlFreeHeap` at `0x180105c70`
- `ntdll!RtlFreeHeap` at `0x180105d84`
- `ntdll!RtlFreeHeap` at `0x180105dea`
- `ntdll!RtlFreeHeap` at `0x180105e02`
- `ntdll!RtlFreeHeap` at `0x180105e34`
- `ntdll!RtlFreeHeap` at `0x180105eda`
- `ntdll!RtlFreeHeap` at `0x180105f5e`
- `ntdll!RtlFreeHeap` at `0x180106032`
- `ntdll!RtlFreeHeap` at `0x18010604f`
- `ntdll!RtlFreeHeap` at `0x1801060d5`
- `ntdll!RtlFreeHeap` at `0x180106121`
- `ntdll!RtlFreeHeap` at `0x1801061d1`
- `ntdll!RtlFreeHeap` at `0x180106257`
- `ntdll!RtlFreeHeap` at `0x180106274`
- `ntdll!RtlFreeHeap` at `0x180106339`
- `ntdll!RtlFreeHeap` at `0x18010637a`
- `ntdll!RtlFreeHeap` at `0x180106420`
- `ntdll!RtlFreeHeap` at `0x1801065fa`
- `ntdll!RtlFreeHeap` at `0x18010661c`
- `ntdll!RtlFreeHeap` at `0x180106712`
- `ntdll!RtlFreeHeap` at `0x180106936`
- `ntdll!RtlFreeHeap` at `0x180105c0f`
- `ntdll!RtlFreeHeap` at `0x180105c70`
- `ntdll!RtlFreeHeap` at `0x180105d84`
- `ntdll!RtlFreeHeap` at `0x180105dea`
- `ntdll!RtlFreeHeap` at `0x180105e02`
- `ntdll!RtlFreeHeap` at `0x180105e34`
- `ntdll!RtlFreeHeap` at `0x180105eda`
- `ntdll!RtlFreeHeap` at `0x180105f5e`
- `ntdll!RtlFreeHeap` at `0x180106032`
- `ntdll!RtlFreeHeap` at `0x18010604f`
- `ntdll!RtlFreeHeap` at `0x1801060d5`
- `ntdll!RtlFreeHeap` at `0x180106121`
- `ntdll!RtlFreeHeap` at `0x1801061d1`
- `ntdll!RtlFreeHeap` at `0x180106257`
- `ntdll!RtlFreeHeap` at `0x180106274`
- `ntdll!RtlFreeHeap` at `0x180106339`
- `ntdll!RtlFreeHeap` at `0x18010637a`
- `ntdll!RtlFreeHeap` at `0x180106420`
- `ntdll!RtlFreeHeap` at `0x1801065fa`
- `ntdll!RtlFreeHeap` at `0x18010661c`
- `ntdll!RtlFreeHeap` at `0x180106712`
- `ntdll!RtlFreeHeap` at `0x180106936`
- `ntdll!RtlGetFullPathName_UEx` at `0x180105e9c`
- `ntdll!RtlGetFullPathName_UEx` at `0x180105e9c`
- `ntdll!RtlAllocateHeap` at `0x180106082`
- `ntdll!RtlAllocateHeap` at `0x1801062c8`
- `ntdll!RtlAllocateHeap` at `0x18010655e`
- `ntdll!RtlAllocateHeap` at `0x1801066d0`
- `ntdll!RtlAllocateHeap` at `0x180106082`
- `ntdll!RtlAllocateHeap` at `0x1801062c8`
- `ntdll!RtlAllocateHeap` at `0x18010655e`
- `ntdll!RtlAllocateHeap` at `0x1801066d0`
- `ext-ms-win-kernel32-file-l1-1-0!SetVolumeMountPointWStub` at `0x1801065d0`
- `ext-ms-win-kernel32-file-l1-1-0!SetVolumeMountPointWStub` at `0x1801065d0`

## pseudocode

```c
BOOL __stdcall CreateDirectoryExW(
        LPCWSTR lpTemplateDirectory,
        LPCWSTR lpNewDirectory,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  ULONG EaLength; // r12d
  ULONG v5; // ecx
  PWSTR Buffer; // rbx
  char v8; // r13
  HANDLE ContainingDirectory; // rax
  NTSTATUS v10; // eax
  NTSTATUS v11; // edi
  __int64 v12; // rcx
  int v13; // eax
  NTSTATUS v14; // eax
  PWSTR v15; // rsi
  NTSTATUS FullPathName_UEx; // eax
  NTSTATUS v17; // ebx
  PWSTR v18; // r8
  ULONG v19; // r14d
  void *EaBuffer; // rdi
  ULONG v21; // eax
  unsigned int v22; // ebx
  ACCESS_MASK v23; // ebx
  NTSTATUS inited; // r14d
  PVOID Heap; // rax
  NTSTATUS v26; // ebx
  char v27; // r14
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // rdi
  _WORD *v30; // rbx
  int v31; // r15d
  _WORD *v32; // rax
  _WORD *v33; // rsi
  unsigned __int64 v34; // rcx
  ULONG v35; // esi
  unsigned int *v36; // rax
  unsigned int *v37; // rdi
  unsigned int *i; // rbx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rcx
  unsigned __int64 v43; // rcx
  char v44; // [rsp+B0h] [rbp-80h]
  HANDLE FileHandle; // [rsp+B8h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp-70h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+C8h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-60h] BYREF
  int v49; // [rsp+E0h] [rbp-50h] BYREF
  ULONG v50; // [rsp+E4h] [rbp-4Ch] BYREF
  __int64 v51; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+F8h] [rbp-38h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+108h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+118h] [rbp-18h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+128h] [rbp-8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp+18h] BYREF
  __int64 v58; // [rsp+178h] [rbp+48h] BYREF
  HANDLE v59; // [rsp+180h] [rbp+50h] BYREF
  HANDLE v60; // [rsp+188h] [rbp+58h] BYREF
  struct _RTL_RELATIVE_NAME_U v61; // [rsp+190h] [rbp+60h] BYREF
  __int128 v62; // [rsp+1B0h] [rbp+80h] BYREF
  PVOID ReturnedState; // [rsp+1C0h] [rbp+90h] BYREF
  PCWSTR Name; // [rsp+1C8h] [rbp+98h]
  PWSTR FilePart; // [rsp+1D0h] [rbp+A0h] BYREF
  LPSECURITY_ATTRIBUTES v66; // [rsp+1D8h] [rbp+A8h]
  __int64 v67; // [rsp+1E0h] [rbp+B0h] BYREF
  _OWORD FileInformation[2]; // [rsp+1E8h] [rbp+B8h] BYREF
  ULONG FileAttributes[2]; // [rsp+208h] [rbp+D8h]
  WCHAR v70[264]; // [rsp+210h] [rbp+E0h] BYREF

  EaLength = 0;
  v66 = lpSecurityAttributes;
  Name = lpNewDirectory;
  FileHandle = 0;
  Handle = 0;
  v59 = 0;
  v60 = 0;
  v52 = 0;
  v50 = 0;
  *(_QWORD *)FileAttributes = 0;
  memset(&ObjectAttributes, 0, 44);
  v49 = 0;
  NtName = 0;
  v51 = 0;
  String2 = 0;
  IoStatusBlock = 0;
  v67 = 0;
  DestinationString = 0;
  ReturnedState = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  LODWORD(v58) = 0;
  memset(&v61, 0, sizeof(v61));
  v62 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !RtlDosPathNameToRelativeNtPathName_U(lpTemplateDirectory, &NtName, 0, &RelativeName) )
  {
    v5 = 3;
LABEL_3:
    RtlSetLastWin32Error(v5);
    return 0;
  }
  Buffer = NtName.Buffer;
  v44 = 0;
  v8 = 0;
  if ( RelativeName.RelativeName.Length )
  {
    NtName = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &NtName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x100089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x204021u);
  v11 = v10;
  if ( v10 >= 0 )
  {
    FileAttributes[0] = 128;
    v11 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    if ( v11 >= 0 )
    {
      if ( (FileAttributes[0] & 0x400) != 0 )
      {
        v11 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v52, 8u, FileAttributeTagInformation);
        if ( v11 < 0 )
          goto LABEL_15;
        if ( (unsigned int)(HIDWORD(v52) + 2147483613) <= 3
          || (unsigned int)(HIDWORD(v52) + 1610612733) <= 0x1A
          && (v13 = 67109377, _bittest(&v13, HIDWORD(v52) + 1610612733)) )
        {
          v44 = 1;
        }
        else
        {
          CloseHandle(FileHandle);
          v11 = NtOpenFile(&FileHandle, 0x100089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
          if ( v11 < 0 )
          {
LABEL_11:
            RtlReleaseRelativeName(&RelativeName);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
LABEL_12:
            v12 = (unsigned int)v11;
LABEL_13:
            BaseSetLastNTError(v12);
            return 0;
          }
        }
      }
      v14 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v49, 4u, FileEaInformation|0x40);
      v11 = v14;
      if ( v14 >= 0 )
      {
        if ( (v49 & 1) != 0 )
          v8 = 1;
        goto LABEL_27;
      }
      if ( v14 == -1073741811 || v14 == -1073741637 )
        goto LABEL_27;
    }
LABEL_15:
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    CloseHandle(FileHandle);
    goto LABEL_12;
  }
  if ( v10 != -1073741811 )
    goto LABEL_11;
  v11 = NtOpenFile(&FileHandle, 0x100089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
  if ( v11 < 0 )
    goto LABEL_11;
LABEL_27:
  if ( !RtlDosPathNameToRelativeNtPathName_U(lpNewDirectory, &String2, 0, &v61) )
  {
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    NtClose(FileHandle);
    v5 = 3;
    goto LABEL_3;
  }
  v15 = String2.Buffer;
  if ( RtlEqualUnicodeString(&NtName, &String2, 1u) )
  {
    RtlReleaseRelativeName(&RelativeName);
    RtlReleaseRelativeName(&v61);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    NtClose(FileHandle);
    v5 = 123;
    goto LABEL_3;
  }
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( !(unsigned __int8)RtlAreLongPathsEnabled() && String2.Length > 0x1F0u )
  {
    FilePart = 0;
    if ( *lpNewDirectory != 92 || lpNewDirectory[1] != 92 || lpNewDirectory[2] != 63 || lpNewDirectory[3] != 92 )
    {
      InputPathType = RtlPathTypeUnknown;
      FullPathName_UEx = RtlGetFullPathName_UEx((PWSTR)lpNewDirectory, 0, 0, &FilePart, &InputPathType);
      if ( FullPathName_UEx < 0 )
        BaseSetLastNTError((unsigned int)FullPathName_UEx);
      if ( !((unsigned int)InputPathType >> 1) || ((unsigned int)InputPathType >> 1) + 12 > 0x104 )
      {
        RtlReleaseRelativeName(&v61);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        CloseHandle(FileHandle);
        v5 = 206;
        goto LABEL_3;
      }
    }
  }
  if ( v61.RelativeName.Length )
    String2 = v61.RelativeName;
  else
    v61.ContainingDirectory = 0;
  v17 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v50, 4u, FileEaInformation);
  if ( v17 < 0 )
  {
    RtlReleaseRelativeName(&v61);
    v18 = v15;
    goto LABEL_50;
  }
  v19 = v50;
  if ( v50 )
  {
    while ( 1 )
    {
      v19 *= 2;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v19);
      EaBuffer = Heap;
      if ( !Heap )
        break;
      v26 = NtQueryEaFile(FileHandle, &IoStatusBlock, Heap, v19, 0, 0, 0, 0, 1u);
      if ( v26 >= 0 )
      {
        EaLength = IoStatusBlock.Information;
      }
      else
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
        EaBuffer = 0;
        IoStatusBlock.Information = 0;
      }
      if ( v26 != -2147483643 && v26 != -1073741789 )
        goto LABEL_55;
      EaLength = 0;
    }
    RtlReleaseRelativeName(&v61);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    CloseHandle(FileHandle);
    goto LABEL_72;
  }
  EaBuffer = 0;
LABEL_55:
  ObjectAttributes.RootDirectory = v61.ContainingDirectory;
  ObjectAttributes.ObjectName = &String2;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( v66 )
    ObjectAttributes.SecurityDescriptor = v66->lpSecurityDescriptor;
  v21 = FileAttributes[0] & 0xFFFFFBFF;
  v22 = FileAttributes[0] & 0x400 | 0x20030200;
  FileAttributes[0] &= ~0x400u;
  v23 = v22 >> 9;
  if ( HIDWORD(v52) == -1610612724 )
  {
    InputPathType = RtlPathTypeDriveRelative|0x20;
    inited = RtlAcquirePrivilege((PULONG)&InputPathType, 1u, 0, &ReturnedState);
    if ( inited < 0 )
    {
      RtlReleaseRelativeName(&v61);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      if ( EaBuffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
      CloseHandle(FileHandle);
LABEL_62:
      v12 = (unsigned int)inited;
      goto LABEL_13;
    }
    v21 = FileAttributes[0];
  }
  v17 = NtCreateFile(&Handle, v23, &ObjectAttributes, &IoStatusBlock, 0, v21, 3u, 2u, 0x204021u, EaBuffer, EaLength);
  if ( HIDWORD(v52) == -1610612724 )
    RtlReleasePrivilege(ReturnedState);
  if ( v17 == -1073741811 || v17 == -1073741790 )
  {
    v27 = v44;
    if ( v44 )
    {
      RtlReleaseRelativeName(&v61);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      if ( !EaBuffer )
        goto LABEL_51;
      v18 = (PWSTR)EaBuffer;
LABEL_50:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
LABEL_51:
      CloseHandle(FileHandle);
LABEL_52:
      v12 = (unsigned int)v17;
      goto LABEL_13;
    }
    v17 = NtCreateFile(
            &Handle,
            0x100181u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes[0],
            3u,
            2u,
            0x4021u,
            EaBuffer,
            EaLength);
  }
  else
  {
    v27 = v44;
  }
  RtlReleaseRelativeName(&v61);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  if ( EaBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
  if ( v17 < 0 )
  {
    NtClose(FileHandle);
    if ( RtlIsDosDeviceName_U(Name) )
      v17 = -1073741565;
    goto LABEL_52;
  }
  if ( v27 )
  {
    v28 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x4000u);
    v29 = v28;
    if ( !v28 )
    {
      NtClose(FileHandle);
      NtClose(Handle);
LABEL_72:
      v12 = 3221225495LL;
      goto LABEL_13;
    }
    v17 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900A8u, 0, 0, v28, 0x4000u);
    if ( v17 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
LABEL_94:
      NtClose(FileHandle);
      NtClose(Handle);
      goto LABEL_52;
    }
    if ( *(_DWORD *)v29 != -1610612733 )
    {
      if ( *(_DWORD *)v29 != -1610612724 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
        NtClose(FileHandle);
        NtClose(Handle);
        v12 = 3221225523LL;
        goto LABEL_13;
      }
      goto LABEL_101;
    }
    v30 = (unsigned __int16 *)((char *)v29 + v29[4]);
    if ( v29[5] != 96 && (v29[5] != 98 || v30[56] != 92)
      || v30[8] != 92
      || v30[9] != 63 && v30[9] != 92
      || v30[10] != 63
      || v30[11] != 92
      || v30[12] != 86
      || v30[13] != 111
      || v30[14] != 108
      || v30[15] != 117
      || v30[16] != 109
      || v30[17] != 101
      || v30[18] != 123
      || v30[27] != 45
      || v30[32] != 45
      || v30[37] != 45
      || v30[42] != 45
      || v30[55] != 125
      || v29[5] != 98
      || v30[9] != 63 )
    {
LABEL_101:
      v31 = 1;
      inited = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x900A4u, v29, v29[2] + 8, 0, 0);
      goto LABEL_102;
    }
    inited = RtlInitUnicodeStringEx(&DestinationString, Name);
    v32 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, DestinationString.Length + 4LL);
    v33 = v32;
    if ( v32 )
    {
      if ( inited >= 0 )
      {
        memcpy_0(v32, DestinationString.Buffer, DestinationString.Length);
        v33[(unsigned __int64)DestinationString.Length >> 1] = 0;
        v34 = (unsigned __int64)DestinationString.Length >> 1;
        if ( DestinationString.Buffer[v34 - 1] != 92 )
        {
          v33[v34] = 92;
          v33[((unsigned __int64)DestinationString.Length >> 1) + 1] = 0;
        }
        v30[9] = 92;
        if ( (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() )
        {
          v31 = SetVolumeMountPointWStub(v33, v30 + 8);
        }
        else
        {
          v31 = 0;
          BaseSetLastNTError(3221225659LL);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
        v30[9] = 63;
LABEL_102:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
        NtClose(FileHandle);
        NtClose(Handle);
        if ( !v31 )
          return 0;
        if ( inited < 0 )
          goto LABEL_62;
        return 1;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
      BaseSetLastNTError((unsigned int)inited);
    }
    else
    {
      RtlSetLastWin32Error(8u);
    }
    v31 = 0;
    goto LABEL_102;
  }
  if ( (FileAttributes[0] & 0x180000) != 0 )
  {
    FileAttributes[0] &= 0x180000u;
    v17 = NtSetInformationFile(Handle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    if ( v17 < 0 )
      goto LABEL_94;
  }
  if ( v8 )
  {
    v17 = NtSetInformationFile(Handle, &IoStatusBlock, &v49, 4u, FileEaInformation|0x40);
    if ( v17 < 0 )
      goto LABEL_94;
  }
  v35 = 4096;
  LODWORD(v51) = 4096;
  while ( 1 )
  {
    v36 = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v35);
    v37 = v36;
    if ( !v36 )
      break;
    v17 = NtQueryInformationFile(FileHandle, &IoStatusBlock, v36, v35, FileStreamInformation);
    if ( v17 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
      v35 *= 2;
      v37 = 0;
    }
    if ( v17 != -2147483643 && v17 != -1073741789 )
      goto LABEL_147;
  }
  BaseMarkFileForDelete(Handle);
  BaseSetLastNTError(3221225495LL);
LABEL_147:
  if ( v17 >= 0 && IoStatusBlock.Information )
  {
    for ( i = v37; ; i = (unsigned int *)((char *)i + *i) )
    {
      *((_QWORD *)&v62 + 1) = i + 6;
      InputPathType = RtlPathTypeUnknown;
      LOWORD(v62) = *((_WORD *)i + 2);
      WORD1(v62) = v62;
      ObjectAttributes.RootDirectory = FileHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v62;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtCreateFile(&v59, 0x80100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 1u, 1u, 0x20u, 0, 0) >= 0 )
      {
        v39 = 0;
        v40 = (unsigned __int16)v62 >> 1;
        if ( (unsigned __int16)v62 >> 1 )
        {
          v41 = *((_QWORD *)&v62 + 1);
          do
          {
            if ( (unsigned int)v39 >= 0x100 )
              break;
            v42 = (unsigned int)v39;
            v39 = (unsigned int)(v39 + 1);
            v70[v42] = *(_WORD *)(v41 + 2 * v42);
          }
          while ( (unsigned int)v39 < (unsigned int)v40 );
        }
        v43 = 2LL * (unsigned int)v39;
        if ( v43 >= 0x202 )
          _report_rangecheckfailure(v43, v39, v40);
        v70[(unsigned int)v39] = 0;
        v60 = (HANDLE)-1LL;
        HIDWORD(v51) = 0;
        BaseCopyStream(
          0,
          &v59,
          0x80100000,
          v70,
          Handle,
          0,
          (__int64 *)i + 1,
          (int *)&v51 + 1,
          &v60,
          0,
          &v51,
          &v67,
          0,
          0,
          0,
          0,
          (__int64)&InputPathType,
          0,
          0,
          0,
          0,
          &v58);
        NtClose(v59);
        if ( v60 != (HANDLE)-1LL )
          NtClose(v60);
      }
      if ( !*i )
        break;
    }
  }
  if ( v37 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
  NtClose(FileHandle);
  if ( Handle )
    NtClose(Handle);
  return 1;
}

```

## disassembly

```asm
0x180105a40  mov     [rsp-8+arg_18], rbx
0x180105a45  push    rbp
0x180105a46  push    rsi
0x180105a47  push    rdi
0x180105a48  push    r12
0x180105a4a  push    r13
0x180105a4c  push    r14
0x180105a4e  push    r15
0x180105a50  lea     rbp, [rsp-300h]
0x180105a58  sub     rsp, 430h
0x180105a5f  mov     rax, cs:__security_cookie
0x180105a66  xor     rax, rsp
0x180105a69  mov     [rbp+330h+var_40], rax
0x180105a70  xor     r12d, r12d
0x180105a73  mov     [rbp+330h+var_288], r8
0x180105a7a  xorps   xmm0, xmm0
0x180105a7d  mov     [rbp+330h+Name], rdx
0x180105a84  xorps   xmm1, xmm1
0x180105a87  mov     [rbp+330h+FileHandle], r12
0x180105a8b  mov     r14, rdx
0x180105a8e  mov     [rbp+330h+Handle], r12
0x180105a92  xor     eax, eax
0x180105a94  mov     [rbp+330h+var_2E0], r12
0x180105a98  movups  xmmword ptr [rbp+330h+ObjectAttributes.ObjectName], xmm0
0x180105a9c  lea     r9, [rbp+330h+RelativeName]; RelativeName
0x180105aa0  mov     [rbp+330h+var_2D8], r12
0x180105aa4  xor     r8d, r8d; PartName
0x180105aa7  mov     [rbp+330h+var_370], r12
0x180105aab  lea     rdx, [rbp+330h+NtName]; NtName
0x180105aaf  mov     [rbp+330h+var_37C], r12d
0x180105ab3  movups  xmmword ptr [rbp+330h+ObjectAttributes+1Ch], xmm0
0x180105ab7  mov     qword ptr [rbp+330h+FileAttributes], rax
0x180105abe  movups  xmmword ptr [rbp+330h+ObjectAttributes.Length], xmm0
0x180105ac2  mov     [rbp+330h+var_380], r12d
0x180105ac6  movups  xmmword ptr [rbp+330h+NtName.Length], xmm0
0x180105aca  mov     dword ptr [rbp+330h+var_378], r12d
0x180105ace  movups  xmmword ptr [rbp+330h+String2.Length], xmm1
0x180105ad2  mov     dword ptr [rbp+330h+var_378+4], r12d
0x180105ad6  movups  xmmword ptr [rbp+330h+IoStatusBlock], xmm0
0x180105ada  mov     [rbp+330h+var_280], r12
0x180105ae1  movups  xmmword ptr [rbp+330h+DestinationString.Length], xmm1
0x180105ae5  mov     [rbp+330h+ReturnedState], r12
0x180105aec  movups  xmmword ptr [rbp+330h+RelativeName.RelativeName.Length], xmm0
0x180105af0  mov     dword ptr [rbp+330h+var_2E8], r12d
0x180105af4  movups  xmmword ptr [rbp+330h+RelativeName.ContainingDirectory], xmm0
0x180105af8  movups  xmmword ptr [rbp+330h+var_2D0.RelativeName.Length], xmm1
0x180105afc  movups  xmmword ptr [rbp+330h+var_2D0.ContainingDirectory], xmm1
0x180105b00  movups  [rbp+330h+var_2B0], xmm0
0x180105b07  movups  [rbp+330h+FileInformation], xmm0
0x180105b0e  movups  [rbp+330h+var_268], xmm0
0x180105b15  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180105b1b  test    al, al
0x180105b1d  jnz     short loc_180105B31
0x180105b1f  lea     ecx, [r12+3]; LastError
0x180105b24  call    cs:__imp_RtlSetLastWin32Error
0x180105b2a  xor     eax, eax
0x180105b2c  jmp     loc_18010695A
0x180105b31  movzx   eax, [rbp+330h+RelativeName.RelativeName.Length]
0x180105b35  mov     rbx, [rbp+330h+NtName.Buffer]
0x180105b39  mov     [rbp+330h+var_3B0], r12b
0x180105b3d  movzx   r13d, r12b
0x180105b41  test    ax, ax
0x180105b44  jz      short loc_180105B66
0x180105b46  mov     [rbp+330h+NtName.Length], ax
0x180105b4a  mov     eax, dword ptr [rbp+330h+RelativeName.RelativeName.MaximumLength]
0x180105b4d  mov     dword ptr [rbp+330h+NtName.MaximumLength], eax
0x180105b50  movzx   eax, word ptr [rbp+330h+RelativeName.RelativeName+6]
0x180105b54  mov     word ptr [rbp+330h+NtName+6], ax
0x180105b58  mov     rax, [rbp+330h+RelativeName.RelativeName.Buffer]
0x180105b5c  mov     [rbp+330h+NtName.Buffer], rax
0x180105b60  mov     rax, [rbp+330h+RelativeName.ContainingDirectory]
0x180105b64  jmp     short loc_180105B6D
0x180105b66  mov     rax, r12
0x180105b69  mov     [rbp+330h+RelativeName.ContainingDirectory], rax
0x180105b6d  mov     [rbp+330h+ObjectAttributes.RootDirectory], rax
0x180105b71  lea     r9, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x180105b75  lea     rax, [rbp+330h+NtName]
0x180105b79  mov     [rsp+460h+OpenOptions], 204021h; OpenOptions
0x180105b81  xorps   xmm0, xmm0
0x180105b84  mov     [rbp+330h+ObjectAttributes.ObjectName], rax
0x180105b88  mov     esi, 100089h
0x180105b8d  mov     [rbp+330h+ObjectAttributes.Length], 30h ; '0'
0x180105b94  mov     r15d, 3
0x180105b9a  mov     [rbp+330h+ObjectAttributes.Attributes], 40h ; '@'
0x180105ba1  mov     edx, esi; DesiredAccess
0x180105ba3  mov     [rsp+460h+ShareAccess], r15d; ShareAccess
0x180105ba8  lea     r8, [rbp+330h+ObjectAttributes]; ObjectAttributes
0x180105bac  lea     rcx, [rbp+330h+FileHandle]; FileHandle
0x180105bb0  movdqu  xmmword ptr [rbp+330h+ObjectAttributes.SecurityDescriptor], xmm0
0x180105bb5  call    cs:__imp_NtOpenFile
0x180105bbb  mov     edi, eax
0x180105bbd  test    eax, eax
0x180105bbf  jns     short loc_180105C21
0x180105bc1  cmp     eax, 0C000000Dh
0x180105bc6  jnz     short loc_180105BF3
0x180105bc8  mov     [rsp+460h+OpenOptions], 4021h; OpenOptions
0x180105bd0  lea     r9, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x180105bd4  lea     r8, [rbp+330h+ObjectAttributes]; ObjectAttributes
0x180105bd8  mov     [rsp+460h+ShareAccess], r15d; ShareAccess
0x180105bdd  mov     edx, esi; DesiredAccess
0x180105bdf  lea     rcx, [rbp+330h+FileHandle]; FileHandle
0x180105be3  call    cs:__imp_NtOpenFile
0x180105be9  mov     edi, eax
0x180105beb  test    eax, eax
0x180105bed  jns     loc_180105D4B
0x180105bf3  lea     rcx, [rbp+330h+RelativeName]; RelativeName
0x180105bf7  call    cs:__imp_RtlReleaseRelativeName
0x180105bfd  mov     rcx, gs:60h
0x180105c06  mov     r8, rbx; P
0x180105c09  xor     edx, edx; Flags
0x180105c0b  mov     rcx, [rcx+30h]; HeapHandle
0x180105c0f  call    cs:__imp_RtlFreeHeap
0x180105c15  mov     ecx, edi
0x180105c17  call    BaseSetLastNTError
0x180105c1c  jmp     loc_180105B2A
0x180105c21  mov     rcx, [rbp+330h+FileHandle]; FileHandle
0x180105c25  lea     r8, [rbp+330h+FileInformation]; FileInformation
0x180105c2c  mov     r9d, 28h ; '('; Length
0x180105c32  mov     [rbp+330h+FileAttributes], 80h
0x180105c3c  lea     rdx, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x180105c40  mov     [rsp+460h+ShareAccess], 4; FileInformationClass
0x180105c48  call    cs:__imp_NtQueryInformationFile
0x180105c4e  mov     edi, eax
0x180105c50  test    eax, eax
0x180105c52  jns     short loc_180105C81
0x180105c54  lea     rcx, [rbp+330h+RelativeName]; RelativeName
0x180105c58  call    cs:__imp_RtlReleaseRelativeName
0x180105c5e  mov     rcx, gs:60h
0x180105c67  mov     r8, rbx; P
0x180105c6a  xor     edx, edx; Flags
0x180105c6c  mov     rcx, [rcx+30h]; HeapHandle
0x180105c70  call    cs:__imp_RtlFreeHeap
0x180105c76  mov     rcx, [rbp+330h+FileHandle]; hObject
0x180105c7a  call    CloseHandle
0x180105c7f  jmp     short loc_180105C15
0x180105c81  test    [rbp+330h+FileAttributes], 400h
0x180105c8b  jz      loc_180105D13
0x180105c91  mov     rcx, [rbp+330h+FileHandle]; FileHandle
0x180105c95  lea     r8, [rbp+330h+var_370]; FileInformation
0x180105c99  mov     r9d, 8; Length
0x180105c9f  mov     [rsp+460h+ShareAccess], 23h ; '#'; FileInformationClass
0x180105ca7  lea     rdx, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x180105cab  call    cs:__imp_NtQueryInformationFile
0x180105cb1  mov     edi, eax
0x180105cb3  test    eax, eax
0x180105cb5  js      short loc_180105C54
0x180105cb7  mov     ecx, dword ptr [rbp+330h+var_370+4]
0x180105cba  lea     eax, [rcx+7FFFFFDDh]
0x180105cc0  cmp     eax, r15d
0x180105cc3  jbe     short loc_180105D0F
0x180105cc5  add     ecx, 5FFFFFFDh
0x180105ccb  cmp     ecx, 1Ah
0x180105cce  ja      short loc_180105CDA
0x180105cd0  mov     eax, 4000201h
0x180105cd5  bt      eax, ecx
0x180105cd8  jb      short loc_180105D0F
0x180105cda  mov     rcx, [rbp+330h+FileHandle]; hObject
0x180105cde  call    CloseHandle
0x180105ce3  lea     r9, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x180105ce7  mov     [rsp+460h+OpenOptions], 4021h; OpenOptions
0x180105cef  lea     r8, [rbp+330h+ObjectAttributes]; ObjectAttributes
0x180105cf3  mov     [rsp+460h+ShareAccess], r15d; ShareAccess
0x180105cf8  mov     edx, esi; DesiredAccess
0x180105cfa  lea     rcx, [rbp+330h+FileHandle]; FileHandle
0x180105cfe  call    cs:__imp_NtOpenFile
0x180105d04  mov     edi, eax
0x180105d06  test    eax, eax
0x180105d08  jns     short loc_180105D13
0x180105d0a  jmp     loc_180105BF3
0x180105d0f  mov     [rbp+330h+var_3B0], 1
0x180105d13  mov     rcx, [rbp+330h+FileHandle]; FileHandle
0x180105d17  lea     r8, [rbp+330h+var_380]; FileInformation
0x180105d1b  mov     r9d, 4; Length
0x180105d21  mov     [rsp+460h+ShareAccess], 47h ; 'G'; FileInformationClass
0x180105d29  lea     rdx, [rbp+330h+IoStatusBlock]; IoStatusBlock
0x180105d2d  call    cs:__imp_NtQueryInformationFile
0x180105d33  mov     edi, eax
0x180105d35  test    eax, eax
0x180105d37  jns     short loc_180105D9C
0x180105d39  cmp     eax, 0C000000Dh
0x180105d3e  jz      short loc_180105D4B
0x180105d40  cmp     eax, 0C00000BBh
0x180105d45  jnz     loc_180105C54
0x180105d4b  mov     edi, 1
0x180105d50  lea     r9, [rbp+330h+var_2D0]; RelativeName
0x180105d54  xor     r8d, r8d; PartName
0x180105d57  lea     rdx, [rbp+330h+String2]; NtName
0x180105d5b  mov     rcx, r14; DosName
0x180105d5e  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180105d64  test    al, al
0x180105d66  jnz     short loc_180105DAB
0x180105d68  lea     rcx, [rbp+330h+RelativeName]; RelativeName
0x180105d6c  call    cs:__imp_RtlReleaseRelativeName
0x180105d72  mov     rcx, gs:60h
0x180105d7b  mov     r8, rbx; P
0x180105d7e  xor     edx, edx; Flags
0x180105d80  mov     rcx, [rcx+30h]; HeapHandle
0x180105d84  call    cs:__imp_RtlFreeHeap
0x180105d8a  mov     rcx, [rbp+330h+FileHandle]; Handle
0x180105d8e  call    cs:__imp_NtClose
0x180105d94  mov     ecx, r15d
0x180105d97  jmp     loc_180105B24
0x180105d9c  mov     edi, 1
0x180105da1  test    byte ptr [rbp+330h+var_380], dil
0x180105da5  cmovnz  r13d, edi
0x180105da9  jmp     short loc_180105D50
0x180105dab  mov     rsi, [rbp+330h+String2.Buffer]
0x180105daf  lea     rdx, [rbp+330h+String2]; String2
0x180105db3  mov     r8b, dil; CaseInsensitive
0x180105db6  lea     rcx, [rbp+330h+NtName]; String1
0x180105dba  call    cs:__imp_RtlEqualUnicodeString
0x180105dc0  lea     rcx, [rbp+330h+RelativeName]; RelativeName
0x180105dc4  test    al, al
0x180105dc6  jz      short loc_180105E1C
0x180105dc8  call    cs:__imp_RtlReleaseRelativeName
0x180105dce  lea     rcx, [rbp+330h+var_2D0]; RelativeName
0x180105dd2  call    cs:__imp_RtlReleaseRelativeName
0x180105dd8  mov     rcx, gs:60h
0x180105de1  mov     r8, rbx; P
0x180105de4  xor     edx, edx; Flags
0x180105de6  mov     rcx, [rcx+30h]; HeapHandle
0x180105dea  call    cs:__imp_RtlFreeHeap
0x180105df0  mov     rcx, gs:60h
0x180105df9  mov     r8, rsi; P
0x180105dfc  xor     edx, edx; Flags
0x180105dfe  mov     rcx, [rcx+30h]; HeapHandle
0x180105e02  call    cs:__imp_RtlFreeHeap
0x180105e08  mov     rcx, [rbp+330h+FileHandle]; Handle
0x180105e0c  call    cs:__imp_NtClose
0x180105e12  mov     ecx, 7Bh ; '{'
0x180105e17  jmp     loc_180105B24
0x180105e1c  call    cs:__imp_RtlReleaseRelativeName
0x180105e22  mov     rcx, gs:60h
0x180105e2b  mov     r8, rbx; P
0x180105e2e  xor     edx, edx; Flags
0x180105e30  mov     rcx, [rcx+30h]; HeapHandle
0x180105e34  call    cs:__imp_RtlFreeHeap
0x180105e3a  call    RtlAreLongPathsEnabled
0x180105e3f  mov     ecx, 5Ch ; '\'
0x180105e44  lea     edx, [rcx-1Dh]
0x180105e47  test    al, al
0x180105e49  jnz     loc_180105EF3
0x180105e4f  mov     eax, 1F0h
0x180105e54  cmp     [rbp+330h+String2.Length], ax
0x180105e58  jbe     loc_180105EF3
0x180105e5e  mov     [rbp+330h+FilePart], r12
0x180105e65  cmp     [r14], cx
0x180105e69  jnz     short loc_180105E80
0x180105e6b  cmp     [r14+2], cx
0x180105e70  jnz     short loc_180105E80
0x180105e72  cmp     [r14+4], dx
0x180105e77  jnz     short loc_180105E80
0x180105e79  cmp     [r14+6], cx
0x180105e7e  jz      short loc_180105EF3
0x180105e80  lea     rax, [rbp+330h+InputPathType]
0x180105e84  mov     [rbp+330h+InputPathType], r12d
0x180105e88  lea     r9, [rbp+330h+FilePart]; FilePart
0x180105e8f  mov     qword ptr [rsp+460h+ShareAccess], rax; InputPathType
0x180105e94  xor     r8d, r8d; Buffer
0x180105e97  xor     edx, edx; BufferLength
0x180105e99  mov     rcx, r14; FileName
0x180105e9c  call    cs:__imp_RtlGetFullPathName_UEx
0x180105ea2  test    eax, eax
0x180105ea4  jns     short loc_180105EAD
0x180105ea6  mov     ecx, eax
0x180105ea8  call    BaseSetLastNTError
0x180105ead  mov     eax, [rbp+330h+InputPathType]
0x180105eb0  shr     eax, 1
0x180105eb2  jz      short loc_180105EBE
0x180105eb4  add     eax, 0Ch
0x180105eb7  cmp     eax, 104h
0x180105ebc  jbe     short loc_180105EF3
0x180105ebe  lea     rcx, [rbp+330h+var_2D0]; RelativeName
0x180105ec2  call    cs:__imp_RtlReleaseRelativeName
0x180105ec8  mov     rcx, gs:60h
0x180105ed1  mov     r8, rsi; P
0x180105ed4  xor     edx, edx; Flags
0x180105ed6  mov     rcx, [rcx+30h]; HeapHandle
0x180105eda  call    cs:__imp_RtlFreeHeap
0x180105ee0  mov     rcx, [rbp+330h+FileHandle]; hObject
0x180105ee4  call    CloseHandle
0x180105ee9  mov     ecx, 0CEh
0x180105eee  jmp     loc_180105B24
0x180105ef3  movzx   eax, [rbp+330h+var_2D0.RelativeName.Length]
0x180105ef7  test    ax, ax
0x180105efa  jz      short loc_180105F18
0x180105efc  mov     [rbp+330h+String2.Length], ax
0x180105f00  mov     eax, dword ptr [rbp+330h+var_2D0.RelativeName.MaximumLength]
0x180105f03  mov     dword ptr [rbp+330h+String2.MaximumLength], eax
0x180105f06  movzx   eax, word ptr [rbp+330h+var_2D0.RelativeName+6]
0x180105f0a  mov     word ptr [rbp+330h+String2+6], ax
0x180105f0e  mov     rax, [rbp+330h+var_2D0.RelativeName.Buffer]
0x180105f12  mov     [rbp+330h+String2.Buffer], rax
0x180105f16  jmp     short loc_180105F1C
0x180105f18  mov     [rbp+330h+var_2D0.ContainingDirectory], r12
0x180105f1c  mov     rcx, [rbp+330h+FileHandle]; FileHandle
0x180105f20  lea     r8, [rbp+330h+var_37C]; FileInformation
0x180105f24  mov     r9d, 4; Length
0x180105f2a  mov     [rsp+460h+ShareAccess], 7; FileInformationClass
0x180105f32  lea     rdx, [rbp+330h+IoStatusBlock]; IoStatusBlock
  ... truncated ...
```
