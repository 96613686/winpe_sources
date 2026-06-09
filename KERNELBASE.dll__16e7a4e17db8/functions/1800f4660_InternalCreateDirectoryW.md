# InternalCreateDirectoryW

- ea: `0x1800f4660`
- end: `0x1800f4940`
- name: `InternalCreateDirectoryW`
- size: `736`
- prototype: `__int64 __usercall@<rax>(PWSTR FileName@<rcx>, ACCESS_MASK DesiredAccess@<edx>, ULONG ShareAccess@<r8d>, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f4610`
- `0x18017faa0`
- `0x18017fb20`

## callees

- `0x1800134a0`
- `0x180022450`
- `0x1800f4660`
- `0x1801113e8`
- `0x180181c30`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800f46d2`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800f46d2`
- `ntdll!RtlReleaseRelativeName` at `0x1800f47aa`
- `ntdll!RtlReleaseRelativeName` at `0x1800f47aa`
- `ntdll!NtCreateFile` at `0x1800f4783`
- `ntdll!NtCreateFile` at `0x1800f4783`
- `ntdll!RtlSetLastWin32Error` at `0x1800f4847`
- `ntdll!RtlSetLastWin32Error` at `0x1800f4884`
- `ntdll!RtlSetLastWin32Error` at `0x1800f4847`
- `ntdll!RtlSetLastWin32Error` at `0x1800f4884`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800f47d4`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800f47d4`
- `ntdll!NtClose` at `0x1800f4927`
- `ntdll!NtClose` at `0x1800f4935`
- `ntdll!NtClose` at `0x1800f4927`
- `ntdll!NtClose` at `0x1800f4935`
- `ntdll!RtlFreeHeap` at `0x1800f47c7`
- `ntdll!RtlFreeHeap` at `0x1800f47c7`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800f482a`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800f482a`

## pseudocode

```c
__int64 __fastcall InternalCreateDirectoryW(
        PWSTR FileName,
        ACCESS_MASK DesiredAccess,
        ULONG ShareAccess,
        char a4,
        __int64 a5)
{
  NTSTATUS DirectoryRedirectionStatus; // ebx
  char v6; // r14
  __int64 v10; // rsi
  PWSTR Buffer; // r15
  HANDLE ContainingDirectory; // rax
  bool v14; // zf
  NTSTATUS FullPathName_UEx; // eax
  ULONG v16; // ecx
  int v17; // eax
  HANDLE FileHandle; // [rsp+60h] [rbp-81h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+68h] [rbp-79h] BYREF
  __int64 v20; // [rsp+78h] [rbp-69h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-61h] BYREF
  PWSTR FilePart; // [rsp+A0h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-9h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+158h] [rbp+77h] BYREF

  FileHandle = (HANDLE)-1LL;
  DirectoryRedirectionStatus = 0;
  v20 = -1;
  v6 = 1;
  v10 = -1;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( (a4 & 1) != 0 )
  {
    if ( (ShareAccess & 2) != 0 )
    {
      v16 = 87;
LABEL_30:
      RtlSetLastWin32Error(v16);
      return -1;
    }
  }
  else
  {
    v6 = 0;
  }
  if ( !RtlDosPathNameToRelativeNtPathName_U(FileName, &NtName, 0, &RelativeName) )
  {
    v16 = 3;
    goto LABEL_30;
  }
  Buffer = NtName.Buffer;
  if ( (unsigned __int8)RtlAreLongPathsEnabled() )
    goto LABEL_6;
  if ( NtName.Length <= 0x1F0u )
    goto LABEL_6;
  v14 = *FileName == 92;
  FilePart = 0;
  if ( v14 && FileName[1] == 92 && FileName[2] == 63 && FileName[3] == 92 )
    goto LABEL_6;
  InputPathType = RtlPathTypeUnknown;
  FullPathName_UEx = RtlGetFullPathName_UEx(FileName, 0, 0, &FilePart, &InputPathType);
  if ( FullPathName_UEx < 0 )
    BaseSetLastNTError((unsigned int)FullPathName_UEx);
  if ( (unsigned int)InputPathType >> 1 && ((unsigned int)InputPathType >> 1) + 12 <= 0x104 )
  {
LABEL_6:
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
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtName;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( a5 )
      ObjectAttributes.SecurityDescriptor = *(PVOID *)(a5 + 8);
    if ( v6 )
    {
      v17 = BasepOpenParentDirectoryNoRedirection(&NtName, &v20);
      v10 = v20;
      DirectoryRedirectionStatus = v17;
      if ( v17 < 0 )
        goto LABEL_13;
    }
    DirectoryRedirectionStatus = NtCreateFile(
                                   &FileHandle,
                                   DesiredAccess,
                                   &ObjectAttributes,
                                   &IoStatusBlock,
                                   0,
                                   0x80u,
                                   ShareAccess,
                                   2u,
                                   0x204021u,
                                   0,
                                   0);
    if ( DirectoryRedirectionStatus >= 0 )
    {
      if ( !v6
        || (DirectoryRedirectionStatus = BasepGetDirectoryRedirectionStatus(NtName.Buffer, FileHandle),
            DirectoryRedirectionStatus >= 0) )
      {
LABEL_13:
        if ( v10 != -1 )
          NtClose((HANDLE)v10);
        goto LABEL_15;
      }
      NtClose(FileHandle);
    }
    FileHandle = (HANDLE)-1LL;
    goto LABEL_13;
  }
  RtlSetLastWin32Error(0xCEu);
LABEL_15:
  RtlReleaseRelativeName(&RelativeName);
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( DirectoryRedirectionStatus < 0 )
  {
    if ( RtlIsDosDeviceName_U(FileName) )
      DirectoryRedirectionStatus = -1073741565;
    BaseSetLastNTError((unsigned int)DirectoryRedirectionStatus);
  }
  return (__int64)FileHandle;
}

```

## disassembly

```asm
0x1800f4660  push    rbp
0x1800f4662  push    rbx
0x1800f4663  push    rsi
0x1800f4664  push    rdi
0x1800f4665  push    r12
0x1800f4667  push    r13
0x1800f4669  push    r14
0x1800f466b  push    r15
0x1800f466d  lea     rbp, [rsp-17h]
0x1800f4672  sub     rsp, 0F8h
0x1800f4679  xorps   xmm0, xmm0
0x1800f467c  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800f4680  xor     eax, eax
0x1800f4682  mov     [rsp+130h+FileHandle], r15
0x1800f4687  xor     ebx, ebx
0x1800f4689  mov     [rbp+4Fh+var_B8], r15
0x1800f468d  mov     r14b, 1
0x1800f4690  xorps   xmm1, xmm1
0x1800f4693  mov     r12d, r8d
0x1800f4696  mov     r13d, edx
0x1800f4699  mov     rdi, rcx
0x1800f469c  mov     rsi, r15
0x1800f469f  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800f46a3  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800f46a7  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800f46ab  movups  xmmword ptr [rbp+4Fh+NtName.Length], xmm0
0x1800f46af  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm1
0x1800f46b3  movups  xmmword ptr [rbp+4Fh+RelativeName.RelativeName.Length], xmm0
0x1800f46b7  movups  xmmword ptr [rbp+4Fh+RelativeName.ContainingDirectory], xmm0
0x1800f46bb  test    r14b, r9b
0x1800f46be  jnz     loc_1800F4875
0x1800f46c4  mov     r14b, bl
0x1800f46c7  lea     r9, [rbp+4Fh+RelativeName]; RelativeName
0x1800f46cb  xor     r8d, r8d; PartName
0x1800f46ce  lea     rdx, [rbp+4Fh+NtName]; NtName
0x1800f46d2  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800f46d8  test    al, al
0x1800f46da  jz      loc_1800F4892
0x1800f46e0  mov     r15, [rbp+4Fh+NtName.Buffer]
0x1800f46e4  call    RtlAreLongPathsEnabled
0x1800f46e9  test    al, al
0x1800f46eb  jnz     short loc_1800F46FC
0x1800f46ed  mov     eax, 1F0h
0x1800f46f2  cmp     [rbp+4Fh+NtName.Length], ax
0x1800f46f6  ja      loc_1800F4804
0x1800f46fc  movzx   eax, [rbp+4Fh+RelativeName.RelativeName.Length]
0x1800f4700  test    ax, ax
0x1800f4703  jnz     loc_1800F4852
0x1800f4709  mov     rax, rbx
0x1800f470c  mov     [rbp+4Fh+RelativeName.ContainingDirectory], rbx
0x1800f4710  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x1800f4714  xorps   xmm0, xmm0
0x1800f4717  lea     rax, [rbp+4Fh+NtName]
0x1800f471b  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800f4722  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800f4726  mov     rax, [rbp+4Fh+arg_20]
0x1800f472a  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800f4731  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f4736  test    rax, rax
0x1800f4739  jnz     loc_1800F48D2
0x1800f473f  test    r14b, r14b
0x1800f4742  jnz     loc_1800F48DF
0x1800f4748  mov     [rsp+130h+EaLength], ebx; EaLength
0x1800f474c  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800f4750  mov     [rsp+130h+EaBuffer], rbx; EaBuffer
0x1800f4755  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800f4759  mov     [rsp+130h+CreateOptions], 204021h; CreateOptions
0x1800f4761  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x1800f4766  mov     [rsp+130h+CreateDisposition], 2; CreateDisposition
0x1800f476e  mov     edx, r13d; DesiredAccess
0x1800f4771  mov     [rsp+130h+ShareAccess], r12d; ShareAccess
0x1800f4776  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x1800f477e  mov     [rsp+130h+AllocationSize], rbx; AllocationSize
0x1800f4783  call    cs:__imp_NtCreateFile
0x1800f4789  mov     ebx, eax
0x1800f478b  test    eax, eax
0x1800f478d  jns     loc_1800F4901
0x1800f4793  mov     [rsp+130h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800f479c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800f47a0  jnz     loc_1800F4932
0x1800f47a6  lea     rcx, [rbp+4Fh+RelativeName]; RelativeName
0x1800f47aa  call    cs:__imp_RtlReleaseRelativeName
0x1800f47b0  test    r15, r15
0x1800f47b3  jz      short loc_1800F47CD
0x1800f47b5  mov     rcx, gs:60h
0x1800f47be  mov     r8, r15; P
0x1800f47c1  xor     edx, edx; Flags
0x1800f47c3  mov     rcx, [rcx+30h]; HeapHandle
0x1800f47c7  call    cs:__imp_RtlFreeHeap
0x1800f47cd  test    ebx, ebx
0x1800f47cf  jns     short loc_1800F47EB
0x1800f47d1  mov     rcx, rdi; Name
0x1800f47d4  call    cs:__imp_RtlIsDosDeviceName_U
0x1800f47da  mov     ecx, 0C0000103h
0x1800f47df  test    eax, eax
0x1800f47e1  cmovnz  ebx, ecx
0x1800f47e4  mov     ecx, ebx
0x1800f47e6  call    BaseSetLastNTError
0x1800f47eb  mov     rax, [rsp+130h+FileHandle]
0x1800f47f0  add     rsp, 0F8h
0x1800f47f7  pop     r15
0x1800f47f9  pop     r14
0x1800f47fb  pop     r13
0x1800f47fd  pop     r12
0x1800f47ff  pop     rdi
0x1800f4800  pop     rsi
0x1800f4801  pop     rbx
0x1800f4802  pop     rbp
0x1800f4803  retn
0x1800f4804  cmp     word ptr [rdi], 5Ch ; '\'
0x1800f4808  mov     [rbp+4Fh+FilePart], rbx
0x1800f480c  jz      loc_1800F4899
0x1800f4812  lea     rax, [rbp+4Fh+InputPathType]
0x1800f4816  mov     [rbp+4Fh+InputPathType], ebx
0x1800f4819  lea     r9, [rbp+4Fh+FilePart]; FilePart
0x1800f481d  mov     [rsp+130h+AllocationSize], rax; InputPathType
0x1800f4822  xor     r8d, r8d; Buffer
0x1800f4825  xor     edx, edx; BufferLength
0x1800f4827  mov     rcx, rdi; FileName
0x1800f482a  call    cs:__imp_RtlGetFullPathName_UEx
0x1800f4830  test    eax, eax
0x1800f4832  jns     short loc_1800F483B
0x1800f4834  mov     ecx, eax
0x1800f4836  call    BaseSetLastNTError
0x1800f483b  mov     eax, [rbp+4Fh+InputPathType]
0x1800f483e  shr     eax, 1
0x1800f4840  jnz     short loc_1800F48BF
0x1800f4842  mov     ecx, 0CEh; LastError
0x1800f4847  call    cs:__imp_RtlSetLastWin32Error
0x1800f484d  jmp     loc_1800F47A6
0x1800f4852  mov     [rbp+4Fh+NtName.Length], ax
0x1800f4856  mov     eax, dword ptr [rbp+4Fh+RelativeName.RelativeName.MaximumLength]
0x1800f4859  mov     dword ptr [rbp+4Fh+NtName.MaximumLength], eax
0x1800f485c  movzx   eax, word ptr [rbp+4Fh+RelativeName.RelativeName+6]
0x1800f4860  mov     word ptr [rbp+4Fh+NtName+6], ax
0x1800f4864  mov     rax, [rbp+4Fh+RelativeName.RelativeName.Buffer]
0x1800f4868  mov     [rbp+4Fh+NtName.Buffer], rax
0x1800f486c  mov     rax, [rbp+4Fh+RelativeName.ContainingDirectory]
0x1800f4870  jmp     loc_1800F4710
0x1800f4875  test    r12b, 2
0x1800f4879  jz      loc_1800F46C7
0x1800f487f  mov     ecx, 57h ; 'W'; LastError
0x1800f4884  call    cs:__imp_RtlSetLastWin32Error
0x1800f488a  mov     rax, r15
0x1800f488d  jmp     loc_1800F47F0
0x1800f4892  mov     ecx, 3
0x1800f4897  jmp     short loc_1800F4884
0x1800f4899  cmp     word ptr [rdi+2], 5Ch ; '\'
0x1800f489e  jnz     loc_1800F4812
0x1800f48a4  cmp     word ptr [rdi+4], 3Fh ; '?'
0x1800f48a9  jnz     loc_1800F4812
0x1800f48af  cmp     word ptr [rdi+6], 5Ch ; '\'
0x1800f48b4  jz      loc_1800F46FC
0x1800f48ba  jmp     loc_1800F4812
0x1800f48bf  add     eax, 0Ch
0x1800f48c2  cmp     eax, 104h
0x1800f48c7  jbe     loc_1800F46FC
0x1800f48cd  jmp     loc_1800F4842
0x1800f48d2  mov     rax, [rax+8]
0x1800f48d6  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x1800f48da  jmp     loc_1800F473F
0x1800f48df  lea     rdx, [rbp+4Fh+var_B8]
0x1800f48e3  lea     rcx, [rbp+4Fh+NtName]
0x1800f48e7  call    BasepOpenParentDirectoryNoRedirection
0x1800f48ec  mov     rsi, [rbp+4Fh+var_B8]
0x1800f48f0  mov     ebx, eax
0x1800f48f2  test    eax, eax
0x1800f48f4  js      loc_1800F479C
0x1800f48fa  xor     ebx, ebx
0x1800f48fc  jmp     loc_1800F4748
0x1800f4901  test    r14b, r14b
0x1800f4904  jz      loc_1800F479C
0x1800f490a  mov     rdx, [rsp+130h+FileHandle]
0x1800f490f  mov     rcx, [rbp+4Fh+NtName.Buffer]
0x1800f4913  call    BasepGetDirectoryRedirectionStatus
0x1800f4918  mov     ebx, eax
0x1800f491a  test    eax, eax
0x1800f491c  jns     loc_1800F479C
0x1800f4922  mov     rcx, [rsp+130h+FileHandle]; Handle
0x1800f4927  call    cs:__imp_NtClose
0x1800f492d  jmp     loc_1800F4793
0x1800f4932  mov     rcx, rsi; Handle
0x1800f4935  call    cs:__imp_NtClose
0x1800f493b  jmp     loc_1800F47A6
```
