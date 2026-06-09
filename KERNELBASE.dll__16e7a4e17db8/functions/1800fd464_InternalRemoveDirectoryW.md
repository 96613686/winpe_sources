# InternalRemoveDirectoryW

- ea: `0x1800fd464`
- end: `0x1800fda4b`
- name: `InternalRemoveDirectoryW`
- size: `1511`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800fd430`
- `0x18017fb30`
- `0x18017fb80`

## callees

- `0x1800134a0`
- `0x180013ec0`
- `0x180045ec0`
- `0x1800fd464`
- `0x180181c30`
- `0x180188eb9`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800fd4dc`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800fd4dc`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd5b1`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd62b`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd6ad`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd816`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd867`
- `ntdll!RtlReleaseRelativeName` at `0x1800fda11`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd5b1`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd62b`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd6ad`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd816`
- `ntdll!RtlReleaseRelativeName` at `0x1800fd867`
- `ntdll!RtlReleaseRelativeName` at `0x1800fda11`
- `ntdll!NtQueryInformationFile` at `0x1800fd60d`
- `ntdll!NtQueryInformationFile` at `0x1800fd60d`
- `ntdll!NtOpenFile` at `0x1800fd56d`
- `ntdll!NtOpenFile` at `0x1800fd59d`
- `ntdll!NtOpenFile` at `0x1800fd955`
- `ntdll!NtOpenFile` at `0x1800fd56d`
- `ntdll!NtOpenFile` at `0x1800fd59d`
- `ntdll!NtOpenFile` at `0x1800fd955`
- `ntdll!NtSetInformationFile` at `0x1800fd9cc`
- `ntdll!NtSetInformationFile` at `0x1800fda05`
- `ntdll!NtSetInformationFile` at `0x1800fd9cc`
- `ntdll!NtSetInformationFile` at `0x1800fda05`
- `ntdll!RtlSetLastWin32Error` at `0x1800fd4ea`
- `ntdll!RtlSetLastWin32Error` at `0x1800fd4ea`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800fd806`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800fd806`
- `ntdll!NtClose` at `0x1800fd64d`
- `ntdll!NtClose` at `0x1800fd6cf`
- `ntdll!NtClose` at `0x1800fd932`
- `ntdll!NtClose` at `0x1800fda33`
- `ntdll!NtClose` at `0x1800fd64d`
- `ntdll!NtClose` at `0x1800fd6cf`
- `ntdll!NtClose` at `0x1800fd932`
- `ntdll!NtClose` at `0x1800fda33`
- `ntdll!RtlFreeHeap` at `0x1800fd5c9`
- `ntdll!RtlFreeHeap` at `0x1800fd643`
- `ntdll!RtlFreeHeap` at `0x1800fd6c5`
- `ntdll!RtlFreeHeap` at `0x1800fd82e`
- `ntdll!RtlFreeHeap` at `0x1800fd87f`
- `ntdll!RtlFreeHeap` at `0x1800fd8e9`
- `ntdll!RtlFreeHeap` at `0x1800fd901`
- `ntdll!RtlFreeHeap` at `0x1800fda29`
- `ntdll!RtlFreeHeap` at `0x1800fd5c9`
- `ntdll!RtlFreeHeap` at `0x1800fd643`
- `ntdll!RtlFreeHeap` at `0x1800fd6c5`
- `ntdll!RtlFreeHeap` at `0x1800fd82e`
- `ntdll!RtlFreeHeap` at `0x1800fd87f`
- `ntdll!RtlFreeHeap` at `0x1800fd8e9`
- `ntdll!RtlFreeHeap` at `0x1800fd901`
- `ntdll!RtlFreeHeap` at `0x1800fda29`
- `ntdll!RtlAllocateHeap` at `0x1800fd69b`
- `ntdll!RtlAllocateHeap` at `0x1800fd855`
- `ntdll!RtlAllocateHeap` at `0x1800fd69b`
- `ntdll!RtlAllocateHeap` at `0x1800fd855`

## pseudocode

```c
__int64 __fastcall InternalRemoveDirectoryW(PCWSTR SourceString, char a2)
{
  ULARGE_INTEGER AppCompatFlags; // r12
  ULONG v5; // ecx
  PWSTR Buffer; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v8; // eax
  NTSTATUS inited; // ebx
  NTSTATUS v10; // eax
  NTSTATUS v12; // eax
  __int16 v13; // ax
  char v14; // dl
  unsigned __int16 *Heap; // rsi
  USHORT v16; // dx
  WCHAR *v17; // rcx
  WCHAR *v18; // rax
  WCHAR *v19; // rbx
  unsigned __int64 v20; // rcx
  NTSTATUS v21; // eax
  HANDLE FileHandle; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-61h] BYREF
  __int64 FileInformation; // [rsp+58h] [rbp-51h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+60h] [rbp-49h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+70h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-9h] BYREF
  char v29; // [rsp+118h] [rbp+6Fh] BYREF
  int v30; // [rsp+120h] [rbp+77h] BYREF
  DWORD BytesReturned; // [rsp+128h] [rbp+7Fh] BYREF

  FileHandle = 0;
  v29 = 0;
  memset(&ObjectAttributes, 0, 44);
  v30 = 0;
  NtName = 0;
  IoStatusBlock = 0;
  AppCompatFlags = NtCurrentPeb()->AppCompatFlags;
  memset(&RelativeName, 0, sizeof(RelativeName));
  FileInformation = 0;
  DestinationString = 0;
  if ( !RtlDosPathNameToRelativeNtPathName_U(SourceString, &NtName, 0, &RelativeName) )
  {
    v5 = 3;
LABEL_3:
    RtlSetLastWin32Error(v5);
    return 0;
  }
  Buffer = NtName.Buffer;
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
  v8 = NtOpenFile(&FileHandle, 0x110080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204021u);
  inited = v8;
  if ( v8 >= 0 )
  {
    v12 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
    inited = v12;
    if ( v12 < 0 && v12 != -1073741822 && v12 != -1073741811 )
    {
      RtlReleaseRelativeName(&RelativeName);
LABEL_18:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      NtClose(FileHandle);
      goto LABEL_12;
    }
    if ( v12 < 0 )
      goto LABEL_63;
    v13 = FileInformation;
    v14 = 0;
    if ( (FileInformation & 0x400) == 0 )
      goto LABEL_63;
    if ( HIDWORD(FileInformation) == -1610612733 )
    {
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x4000u);
      if ( !Heap )
      {
        RtlReleaseRelativeName(&RelativeName);
LABEL_24:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
        NtClose(FileHandle);
        v5 = 8;
        goto LABEL_3;
      }
      if ( DeviceIoControl(FileHandle, 0x900A8u, 0, 0, Heap, 0x4000u, &BytesReturned, 0) )
      {
        v16 = Heap[5];
        DestinationString.MaximumLength = v16;
        DestinationString.Length = v16;
        v17 = (unsigned __int16 *)((char *)Heap + Heap[4] + 16);
        DestinationString.Buffer = v17;
        if ( (v16 == 96 || v16 == 98 && v17[48] == 92)
          && *v17 == 92
          && (v17[1] == 63 || v17[1] == 92)
          && v17[2] == 63
          && v17[3] == 92
          && v17[4] == 86
          && v17[5] == 111
          && v17[6] == 108
          && v17[7] == 117
          && v17[8] == 109
          && v17[9] == 101
          && v17[10] == 123
          && v17[19] == 45
          && v17[24] == 45
          && v17[29] == 45
          && v17[34] == 45
          && v17[47] == 125 )
        {
          inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
          if ( inited < 0 )
          {
            RtlReleaseRelativeName(&RelativeName);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            goto LABEL_18;
          }
          v18 = (WCHAR *)RtlAllocateHeap(
                           NtCurrentPeb()->ProcessHeap,
                           KernelBaseGlobalData,
                           DestinationString.Length + 4LL);
          v19 = v18;
          if ( !v18 )
          {
            RtlReleaseRelativeName(&RelativeName);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            goto LABEL_24;
          }
          memcpy_0(v18, DestinationString.Buffer, DestinationString.Length);
          v19[(unsigned __int64)DestinationString.Length >> 1] = 0;
          v20 = (unsigned __int64)DestinationString.Length >> 1;
          if ( DestinationString.Buffer[v20 - 1] != 92 )
          {
            v19[v20] = 92;
            v19[((unsigned __int64)DestinationString.Length >> 1) + 1] = 0;
          }
          DeleteVolumeMountPointW(v19);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v13 = FileInformation;
    }
    else if ( HIDWORD(FileInformation) != -1610612724 && HIDWORD(FileInformation) != -1610612711 )
    {
      goto LABEL_57;
    }
    v14 = 1;
LABEL_57:
    if ( (v13 & 0x400) == 0 )
      goto LABEL_63;
    if ( v14 )
      goto LABEL_63;
    NtClose(FileHandle);
    v21 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
    inited = v21;
    if ( v21 >= 0 )
      goto LABEL_63;
    if ( ((v21 + 1073741194) & 0xFFFFFFFC) != 0 || v21 == -1073741193 )
      goto LABEL_11;
    v10 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204021u);
    goto LABEL_10;
  }
  if ( v8 != -1073741811 )
  {
LABEL_11:
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
LABEL_12:
    BaseSetLastNTError((unsigned int)inited);
    return 0;
  }
  v10 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
LABEL_10:
  inited = v10;
  if ( v10 < 0 )
    goto LABEL_11;
LABEL_63:
  if ( (a2 & 1) == 0 || (inited = BasepGetDirectoryRedirectionStatus(NtName.Buffer, FileHandle), inited >= 0) )
  {
    if ( (AppCompatFlags.QuadPart & 0x100000000LL) != 0
      || (v30 = 3,
          inited = NtSetInformationFile(FileHandle, &IoStatusBlock, &v30, 4u, (FILE_INFORMATION_CLASS)64),
          (int)(inited + 0x80000000) >= 0)
      && inited != -1073741535 )
    {
      v29 = 1;
      inited = NtSetInformationFile(FileHandle, &IoStatusBlock, &v29, 1u, FileDispositionInformation);
    }
  }
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  NtClose(FileHandle);
  if ( inited < 0 )
    goto LABEL_12;
  return 1;
}

```

## disassembly

```asm
0x1800fd464  mov     [rsp-8+arg_0], rbx
0x1800fd469  push    rbp
0x1800fd46a  push    rsi
0x1800fd46b  push    rdi
0x1800fd46c  push    r12
0x1800fd46e  push    r13
0x1800fd470  push    r14
0x1800fd472  push    r15
0x1800fd474  lea     rbp, [rsp-27h]
0x1800fd479  sub     rsp, 0D0h
0x1800fd480  xorps   xmm0, xmm0
0x1800fd483  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800fd487  xor     r13d, r13d
0x1800fd48a  xorps   xmm1, xmm1
0x1800fd48d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800fd491  mov     [rbp+57h+FileHandle], r13
0x1800fd495  xor     eax, eax
0x1800fd497  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800fd49b  mov     [rbp+57h+arg_8], r13b
0x1800fd49f  mov     r15d, edx
0x1800fd4a2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800fd4a6  mov     [rbp+57h+arg_10], r13d
0x1800fd4aa  xor     r8d, r8d; PartName
0x1800fd4ad  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800fd4b1  lea     rdx, [rbp+57h+NtName]; NtName
0x1800fd4b5  mov     r14, rcx
0x1800fd4b8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800fd4bc  mov     rax, gs:60h
0x1800fd4c5  mov     r12, [rax+2C8h]
0x1800fd4cc  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800fd4d0  mov     [rbp+57h+FileInformation], r13
0x1800fd4d4  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800fd4d8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800fd4dc  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800fd4e2  test    al, al
0x1800fd4e4  jnz     short loc_1800FD4F5
0x1800fd4e6  lea     ecx, [r13+3]; LastError
0x1800fd4ea  call    cs:__imp_RtlSetLastWin32Error
0x1800fd4f0  jmp     loc_1800FD5D6
0x1800fd4f5  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800fd4f9  mov     rdi, [rbp+57h+NtName.Buffer]
0x1800fd4fd  test    ax, ax
0x1800fd500  jz      short loc_1800FD522
0x1800fd502  mov     [rbp+57h+NtName.Length], ax
0x1800fd506  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800fd509  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1800fd50c  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800fd510  mov     word ptr [rbp+57h+NtName+6], ax
0x1800fd514  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800fd518  mov     [rbp+57h+NtName.Buffer], rax
0x1800fd51c  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800fd520  jmp     short loc_1800FD529
0x1800fd522  mov     rax, r13
0x1800fd525  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800fd529  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800fd52d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800fd531  lea     rax, [rbp+57h+NtName]
0x1800fd535  mov     [rsp+100h+OpenOptions], 204021h; OpenOptions
0x1800fd53d  xorps   xmm0, xmm0
0x1800fd540  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800fd544  mov     esi, 7
0x1800fd549  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800fd550  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800fd554  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800fd55b  mov     edx, 110080h; DesiredAccess
0x1800fd560  mov     [rsp+100h+ShareAccess], esi; ShareAccess
0x1800fd564  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800fd568  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800fd56d  call    cs:__imp_NtOpenFile
0x1800fd573  mov     ebx, eax
0x1800fd575  test    eax, eax
0x1800fd577  jns     short loc_1800FD5F3
0x1800fd579  cmp     eax, 0C000000Dh
0x1800fd57e  jnz     short loc_1800FD5AD
0x1800fd580  mov     [rsp+100h+OpenOptions], 4021h; OpenOptions
0x1800fd588  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800fd58c  mov     [rsp+100h+ShareAccess], esi; ShareAccess
0x1800fd590  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800fd594  mov     edx, 110000h; DesiredAccess
0x1800fd599  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800fd59d  call    cs:__imp_NtOpenFile
0x1800fd5a3  mov     ebx, eax
0x1800fd5a5  test    eax, eax
0x1800fd5a7  jns     loc_1800FD98B
0x1800fd5ad  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800fd5b1  call    cs:__imp_RtlReleaseRelativeName
0x1800fd5b7  mov     rcx, gs:60h
0x1800fd5c0  mov     r8, rdi; P
0x1800fd5c3  xor     edx, edx; Flags
0x1800fd5c5  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd5c9  call    cs:__imp_RtlFreeHeap
0x1800fd5cf  mov     ecx, ebx
0x1800fd5d1  call    BaseSetLastNTError
0x1800fd5d6  xor     eax, eax
0x1800fd5d8  mov     rbx, [rsp+100h+arg_0]
0x1800fd5e0  add     rsp, 0D0h
0x1800fd5e7  pop     r15
0x1800fd5e9  pop     r14
0x1800fd5eb  pop     r13
0x1800fd5ed  pop     r12
0x1800fd5ef  pop     rdi
0x1800fd5f0  pop     rsi
0x1800fd5f1  pop     rbp
0x1800fd5f2  retn
0x1800fd5f3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800fd5f7  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800fd5fb  mov     r9d, 8; Length
0x1800fd601  mov     [rsp+100h+ShareAccess], 23h ; '#'; FileInformationClass
0x1800fd609  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800fd60d  call    cs:__imp_NtQueryInformationFile
0x1800fd613  mov     ebx, eax
0x1800fd615  test    eax, eax
0x1800fd617  jns     short loc_1800FD658
0x1800fd619  cmp     eax, 0C0000002h
0x1800fd61e  jz      short loc_1800FD658
0x1800fd620  cmp     eax, 0C000000Dh
0x1800fd625  jz      short loc_1800FD658
0x1800fd627  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800fd62b  call    cs:__imp_RtlReleaseRelativeName
0x1800fd631  mov     rcx, gs:60h
0x1800fd63a  mov     r8, rdi; P
0x1800fd63d  xor     edx, edx; Flags
0x1800fd63f  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd643  call    cs:__imp_RtlFreeHeap
0x1800fd649  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800fd64d  call    cs:__imp_NtClose
0x1800fd653  jmp     loc_1800FD5CF
0x1800fd658  test    ebx, ebx
0x1800fd65a  js      loc_1800FD98B
0x1800fd660  mov     rax, [rbp+57h+FileInformation]
0x1800fd664  mov     dl, r13b
0x1800fd667  bt      eax, 0Ah
0x1800fd66b  jnb     loc_1800FD98B
0x1800fd671  mov     ecx, dword ptr [rbp+57h+FileInformation+4]
0x1800fd674  cmp     ecx, 0A0000003h
0x1800fd67a  jnz     loc_1800FD912
0x1800fd680  mov     rcx, gs:60h
0x1800fd689  mov     ebx, 4000h
0x1800fd68e  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800fd694  mov     r8d, ebx; Size
0x1800fd697  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd69b  call    cs:__imp_RtlAllocateHeap
0x1800fd6a1  mov     rsi, rax
0x1800fd6a4  test    rax, rax
0x1800fd6a7  jnz     short loc_1800FD6DF
0x1800fd6a9  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800fd6ad  call    cs:__imp_RtlReleaseRelativeName
0x1800fd6b3  mov     rcx, gs:60h
0x1800fd6bc  mov     r8, rdi; P
0x1800fd6bf  xor     edx, edx; Flags
0x1800fd6c1  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd6c5  call    cs:__imp_RtlFreeHeap
0x1800fd6cb  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800fd6cf  call    cs:__imp_NtClose
0x1800fd6d5  mov     ecx, 8
0x1800fd6da  jmp     loc_1800FD4EA
0x1800fd6df  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x1800fd6e3  lea     rax, [rbp+57h+BytesReturned]
0x1800fd6e7  mov     [rsp+100h+lpOverlapped], r13; lpOverlapped
0x1800fd6ec  xor     r9d, r9d; nInBufferSize
0x1800fd6ef  mov     [rsp+100h+lpBytesReturned], rax; lpBytesReturned
0x1800fd6f4  xor     r8d, r8d; lpInBuffer
0x1800fd6f7  mov     [rsp+100h+OpenOptions], ebx; nOutBufferSize
0x1800fd6fb  mov     edx, 900A8h; dwIoControlCode
0x1800fd700  mov     qword ptr [rsp+100h+ShareAccess], rsi; lpOutBuffer
0x1800fd705  call    DeviceIoControl
0x1800fd70a  test    eax, eax
0x1800fd70c  jz      loc_1800FD8EF
0x1800fd712  movzx   edx, word ptr [rsi+0Ah]
0x1800fd716  mov     eax, 5Ch ; '\'
0x1800fd71b  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x1800fd71f  mov     [rbp+57h+DestinationString.Length], dx
0x1800fd723  movzx   ecx, word ptr [rsi+8]
0x1800fd727  add     rcx, 10h
0x1800fd72b  add     rcx, rsi
0x1800fd72e  mov     [rbp+57h+DestinationString.Buffer], rcx
0x1800fd732  cmp     dx, 60h ; '`'
0x1800fd736  jz      short loc_1800FD74C
0x1800fd738  cmp     dx, 62h ; 'b'
0x1800fd73c  jnz     loc_1800FD8EF
0x1800fd742  cmp     [rcx+60h], ax
0x1800fd746  jnz     loc_1800FD8EF
0x1800fd74c  cmp     [rcx], ax
0x1800fd74f  jnz     loc_1800FD8EF
0x1800fd755  cmp     word ptr [rcx+2], 3Fh ; '?'
0x1800fd75a  jz      short loc_1800FD766
0x1800fd75c  cmp     [rcx+2], ax
0x1800fd760  jnz     loc_1800FD8EF
0x1800fd766  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1800fd76b  jnz     loc_1800FD8EF
0x1800fd771  cmp     [rcx+6], ax
0x1800fd775  jnz     loc_1800FD8EF
0x1800fd77b  cmp     word ptr [rcx+8], 56h ; 'V'
0x1800fd780  jnz     loc_1800FD8EF
0x1800fd786  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x1800fd78b  jnz     loc_1800FD8EF
0x1800fd791  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1800fd796  jnz     loc_1800FD8EF
0x1800fd79c  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1800fd7a1  jnz     loc_1800FD8EF
0x1800fd7a7  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1800fd7ac  jnz     loc_1800FD8EF
0x1800fd7b2  cmp     word ptr [rcx+12h], 65h ; 'e'
0x1800fd7b7  jnz     loc_1800FD8EF
0x1800fd7bd  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x1800fd7c2  jnz     loc_1800FD8EF
0x1800fd7c8  mov     ax, 2Dh ; '-'
0x1800fd7cc  cmp     [rcx+26h], ax
0x1800fd7d0  jnz     loc_1800FD8EF
0x1800fd7d6  cmp     [rcx+30h], ax
0x1800fd7da  jnz     loc_1800FD8EF
0x1800fd7e0  cmp     [rcx+3Ah], ax
0x1800fd7e4  jnz     loc_1800FD8EF
0x1800fd7ea  cmp     [rcx+44h], ax
0x1800fd7ee  jnz     loc_1800FD8EF
0x1800fd7f4  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x1800fd7f9  jnz     loc_1800FD8EF
0x1800fd7ff  mov     rdx, r14; SourceString
0x1800fd802  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800fd806  call    cs:__imp_RtlInitUnicodeStringEx
0x1800fd80c  mov     ebx, eax
0x1800fd80e  test    eax, eax
0x1800fd810  jns     short loc_1800FD839
0x1800fd812  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800fd816  call    cs:__imp_RtlReleaseRelativeName
0x1800fd81c  mov     rcx, gs:60h
0x1800fd825  mov     r8, rsi; P
0x1800fd828  xor     edx, edx; Flags
0x1800fd82a  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd82e  call    cs:__imp_RtlFreeHeap
0x1800fd834  jmp     loc_1800FD631
0x1800fd839  mov     rcx, gs:60h
0x1800fd842  movzx   r8d, [rbp+57h+DestinationString.Length]
0x1800fd847  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800fd84d  add     r8, 4; Size
0x1800fd851  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd855  call    cs:__imp_RtlAllocateHeap
0x1800fd85b  mov     rbx, rax
0x1800fd85e  test    rax, rax
0x1800fd861  jnz     short loc_1800FD88A
0x1800fd863  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800fd867  call    cs:__imp_RtlReleaseRelativeName
0x1800fd86d  mov     rcx, gs:60h
0x1800fd876  mov     r8, rsi; P
0x1800fd879  xor     edx, edx; Flags
0x1800fd87b  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd87f  call    cs:__imp_RtlFreeHeap
0x1800fd885  jmp     loc_1800FD6B3
0x1800fd88a  movzx   r8d, [rbp+57h+DestinationString.Length]; Size
0x1800fd88f  mov     rcx, rbx; void *
0x1800fd892  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x1800fd896  call    memcpy_0
0x1800fd89b  movzx   ecx, [rbp+57h+DestinationString.Length]
0x1800fd89f  mov     edx, 5Ch ; '\'
0x1800fd8a4  shr     rcx, 1
0x1800fd8a7  mov     [rbx+rcx*2], r13w
0x1800fd8ac  movzx   ecx, [rbp+57h+DestinationString.Length]
0x1800fd8b0  mov     rax, [rbp+57h+DestinationString.Buffer]
0x1800fd8b4  shr     rcx, 1
0x1800fd8b7  cmp     [rax+rcx*2-2], dx
0x1800fd8bc  jz      short loc_1800FD8CF
0x1800fd8be  mov     [rbx+rcx*2], dx
0x1800fd8c2  movzx   ecx, [rbp+57h+DestinationString.Length]
0x1800fd8c6  shr     rcx, 1
0x1800fd8c9  mov     [rbx+rcx*2+2], r13w
0x1800fd8cf  mov     rcx, rbx; lpszVolumeMountPoint
0x1800fd8d2  call    DeleteVolumeMountPointW
0x1800fd8d7  mov     rcx, gs:60h
0x1800fd8e0  mov     r8, rbx; P
0x1800fd8e3  xor     edx, edx; Flags
0x1800fd8e5  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd8e9  call    cs:__imp_RtlFreeHeap
0x1800fd8ef  mov     rcx, gs:60h
0x1800fd8f8  mov     r8, rsi; P
0x1800fd8fb  xor     edx, edx; Flags
0x1800fd8fd  mov     rcx, [rcx+30h]; HeapHandle
0x1800fd901  call    cs:__imp_RtlFreeHeap
0x1800fd907  mov     rax, [rbp+57h+FileInformation]
0x1800fd90b  mov     esi, 7
0x1800fd910  jmp     short loc_1800FD922
0x1800fd912  cmp     ecx, 0A000000Ch
0x1800fd918  jz      short loc_1800FD922
0x1800fd91a  cmp     ecx, 0A0000019h
0x1800fd920  jnz     short loc_1800FD924
0x1800fd922  mov     dl, 1
0x1800fd924  bt      eax, 0Ah
0x1800fd928  jnb     short loc_1800FD98B
0x1800fd92a  test    dl, dl
0x1800fd92c  jnz     short loc_1800FD98B
0x1800fd92e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800fd932  call    cs:__imp_NtClose
0x1800fd938  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800fd93c  mov     [rsp+100h+OpenOptions], 4021h; OpenOptions
0x1800fd944  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800fd948  mov     [rsp+100h+ShareAccess], esi; ShareAccess
0x1800fd94c  mov     edx, 110000h; DesiredAccess
0x1800fd951  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800fd955  call    cs:__imp_NtOpenFile
0x1800fd95b  mov     ebx, eax
0x1800fd95d  test    eax, eax
  ... truncated ...
```
