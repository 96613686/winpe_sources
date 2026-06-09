# InternalDeleteFileW

- ea: `0x1800cd124`
- end: `0x1800cd3dd`
- name: `InternalDeleteFileW`
- size: `697`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cd0f0`
- `0x1800cd450`
- `0x1801813f0`
- `0x180181440`

## callees

- `0x1800134a0`
- `0x1800cd124`
- `0x180181d44`

## import_xrefs

- `ntdll!RtlReleaseRelativeName` at `0x1800cd283`
- `ntdll!RtlReleaseRelativeName` at `0x180193c16`
- `ntdll!RtlReleaseRelativeName` at `0x180193c3a`
- `ntdll!RtlReleaseRelativeName` at `0x1800cd283`
- `ntdll!RtlReleaseRelativeName` at `0x180193c16`
- `ntdll!RtlReleaseRelativeName` at `0x180193c3a`
- `ntdll!NtQueryInformationFile` at `0x1800cd259`
- `ntdll!NtQueryInformationFile` at `0x1800cd259`
- `ntdll!NtOpenFile` at `0x1800cd22b`
- `ntdll!NtOpenFile` at `0x180193c02`
- `ntdll!NtOpenFile` at `0x180193c9c`
- `ntdll!NtOpenFile` at `0x1800cd22b`
- `ntdll!NtOpenFile` at `0x180193c02`
- `ntdll!NtOpenFile` at `0x180193c9c`
- `ntdll!NtSetInformationFile` at `0x1800cd2cc`
- `ntdll!NtSetInformationFile` at `0x1800cd31f`
- `ntdll!NtSetInformationFile` at `0x1800cd2cc`
- `ntdll!NtSetInformationFile` at `0x1800cd31f`
- `ntdll!RtlSetLastWin32Error` at `0x1800cd339`
- `ntdll!RtlSetLastWin32Error` at `0x1800cd339`
- `ntdll!NtClose` at `0x1800cd2e4`
- `ntdll!NtClose` at `0x180193c5c`
- `ntdll!NtClose` at `0x180193c7a`
- `ntdll!NtClose` at `0x1800cd2e4`
- `ntdll!NtClose` at `0x180193c5c`
- `ntdll!NtClose` at `0x180193c7a`
- `ntdll!RtlFreeHeap` at `0x1800cd29b`
- `ntdll!RtlFreeHeap` at `0x180193c2e`
- `ntdll!RtlFreeHeap` at `0x180193c52`
- `ntdll!RtlFreeHeap` at `0x1800cd29b`
- `ntdll!RtlFreeHeap` at `0x180193c2e`
- `ntdll!RtlFreeHeap` at `0x180193c52`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800cd194`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800cd194`

## pseudocode

```c
__int64 __fastcall InternalDeleteFileW(__int64 a1, int a2)
{
  ULARGE_INTEGER AppCompatFlags; // r14
  int v4; // eax
  __int64 v5; // rcx
  PVOID v7; // rbx
  HANDLE ContainingDirectory; // rax
  NTSTATUS FileRedirectionStatus; // edi
  NTSTATUS v10; // ebx
  NTSTATUS v11; // eax
  int v12; // ecx
  NTSTATUS v13; // eax
  __int64 FileInformation; // [rsp+30h] [rbp-59h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-41h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+58h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  char v19; // [rsp+F8h] [rbp+6Fh] BYREF
  int v20; // [rsp+100h] [rbp+77h] BYREF
  HANDLE FileHandle; // [rsp+108h] [rbp+7Fh] BYREF

  FileHandle = 0;
  v19 = 0;
  memset(&ObjectAttributes, 0, 44);
  v20 = 0;
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  AppCompatFlags = NtCurrentPeb()->AppCompatFlags;
  FileInformation = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  v4 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( v4 < 0 )
  {
    if ( v4 != -1073741801 && v4 != -1073741670 )
    {
      RtlSetLastWin32Error(3u);
      return 0;
    }
    v5 = (unsigned int)v4;
LABEL_4:
    BaseSetLastNTError(v5);
    return 0;
  }
  v7 = P[1];
  if ( RelativeName.RelativeName.Length )
  {
    LOWORD(P[0]) = RelativeName.RelativeName.Length;
    *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
    HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
    P[1] = RelativeName.RelativeName.Buffer;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileRedirectionStatus = NtOpenFile(&FileHandle, 0x10080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204040u);
  if ( FileRedirectionStatus < 0 )
  {
    if ( FileRedirectionStatus == -1073741811 )
    {
      v11 = NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4040u);
      goto LABEL_33;
    }
    if ( FileRedirectionStatus != -1073741790 )
      goto LABEL_34;
LABEL_32:
    v11 = NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204040u);
LABEL_33:
    FileRedirectionStatus = v11;
    if ( v11 < 0 )
    {
LABEL_34:
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
LABEL_36:
      v5 = (unsigned int)FileRedirectionStatus;
      goto LABEL_4;
    }
    goto LABEL_11;
  }
  FileRedirectionStatus = NtQueryInformationFile(
                            FileHandle,
                            &IoStatusBlock,
                            &FileInformation,
                            8u,
                            FileAttributeTagInformation);
  if ( FileRedirectionStatus >= 0 )
  {
    if ( (FileInformation & 0x400) == 0 )
      goto LABEL_11;
    if ( (unsigned int)(HIDWORD(FileInformation) + 1610612733) <= 0x16 )
    {
      v12 = 4194817;
      if ( _bittest(&v12, HIDWORD(FileInformation) + 1610612733) )
        goto LABEL_11;
    }
    NtClose(FileHandle);
    v13 = NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4040u);
    FileRedirectionStatus = v13;
    if ( v13 >= 0 )
      goto LABEL_11;
    if ( ((v13 + 1073741194) & 0xFFFFFFFC) != 0 || v13 == -1073741193 )
      goto LABEL_34;
    goto LABEL_32;
  }
  if ( FileRedirectionStatus != -1073741822 && FileRedirectionStatus != -1073741811 )
    goto LABEL_35;
LABEL_11:
  if ( (a2 & 0x10000) != 0 )
  {
    FileRedirectionStatus = BasepGetFileRedirectionStatus(P[1], FileHandle);
    if ( FileRedirectionStatus < 0 )
    {
LABEL_35:
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      NtClose(FileHandle);
      goto LABEL_36;
    }
  }
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( (AppCompatFlags.QuadPart & 0x100000000LL) != 0
    || (v20 = 3,
        v10 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v20, 4u, (FILE_INFORMATION_CLASS)64),
        (int)(v10 + 0x80000000) >= 0)
    && v10 != -1073741535 )
  {
    v19 = 1;
    v10 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v19, 1u, FileDispositionInformation);
  }
  NtClose(FileHandle);
  if ( v10 < 0 )
  {
    v5 = (unsigned int)v10;
    goto LABEL_4;
  }
  return 1;
}

```

## disassembly

```asm
0x1800cd124  mov     [rsp-8+arg_0], rbx
0x1800cd129  push    rbp
0x1800cd12a  push    rsi
0x1800cd12b  push    rdi
0x1800cd12c  push    r12
0x1800cd12e  push    r13
0x1800cd130  push    r14
0x1800cd132  push    r15
0x1800cd134  lea     rbp, [rsp-27h]
0x1800cd139  sub     rsp, 0B0h
0x1800cd140  xorps   xmm0, xmm0
0x1800cd143  lea     r9, [rbp+57h+RelativeName]
0x1800cd147  xor     r15d, r15d
0x1800cd14a  xorps   xmm1, xmm1
0x1800cd14d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800cd151  mov     [rbp+57h+FileHandle], r15
0x1800cd155  xor     eax, eax
0x1800cd157  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800cd15b  mov     [rbp+57h+arg_8], r15b
0x1800cd15f  mov     esi, edx
0x1800cd161  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800cd165  mov     [rbp+57h+arg_10], r15d
0x1800cd169  xor     r8d, r8d
0x1800cd16c  movups  xmmword ptr [rbp+57h+P], xmm0
0x1800cd170  lea     rdx, [rbp+57h+P]
0x1800cd174  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800cd178  mov     rax, gs:60h
0x1800cd181  mov     r14, [rax+2C8h]
0x1800cd188  mov     [rbp+57h+FileInformation], r15
0x1800cd18c  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800cd190  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800cd194  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800cd19a  test    eax, eax
0x1800cd19c  jns     short loc_1800CD1CD
0x1800cd19e  cmp     eax, 0C0000017h
0x1800cd1a3  jnz     loc_1800CD329
0x1800cd1a9  mov     ecx, eax
0x1800cd1ab  call    BaseSetLastNTError
0x1800cd1b0  xor     eax, eax
0x1800cd1b2  mov     rbx, [rsp+0E0h+arg_0]
0x1800cd1ba  add     rsp, 0B0h
0x1800cd1c1  pop     r15
0x1800cd1c3  pop     r14
0x1800cd1c5  pop     r13
0x1800cd1c7  pop     r12
0x1800cd1c9  pop     rdi
0x1800cd1ca  pop     rsi
0x1800cd1cb  pop     rbp
0x1800cd1cc  retn
0x1800cd1cd  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800cd1d1  mov     rbx, [rbp+57h+P+8]
0x1800cd1d5  test    ax, ax
0x1800cd1d8  jnz     loc_1800CD344
0x1800cd1de  mov     rax, r15
0x1800cd1e1  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800cd1e5  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800cd1e9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800cd1ed  lea     rax, [rbp+57h+P]
0x1800cd1f1  mov     [rsp+0E0h+OpenOptions], 204040h; OpenOptions
0x1800cd1f9  xorps   xmm0, xmm0
0x1800cd1fc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800cd200  mov     r13d, 7
0x1800cd206  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800cd20d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800cd211  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800cd218  mov     edx, 10080h; DesiredAccess
0x1800cd21d  mov     [rsp+0E0h+ShareAccess], r13d; ShareAccess
0x1800cd222  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800cd226  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800cd22b  call    cs:__imp_NtOpenFile
0x1800cd231  mov     edi, eax
0x1800cd233  mov     r12d, 10000h
0x1800cd239  test    eax, eax
0x1800cd23b  js      loc_1800CD367
0x1800cd241  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800cd245  lea     r9d, [r13+1]; Length
0x1800cd249  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800cd24d  mov     [rsp+0E0h+ShareAccess], 23h ; '#'; FileInformationClass
0x1800cd255  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800cd259  call    cs:__imp_NtQueryInformationFile
0x1800cd25f  mov     edi, eax
0x1800cd261  test    eax, eax
0x1800cd263  js      loc_1800CD380
0x1800cd269  test    dword ptr [rbp+57h+FileInformation], 400h
0x1800cd270  jnz     loc_1800CD39D
0x1800cd276  test    r12d, esi
0x1800cd279  jnz     loc_1800CD3C1
0x1800cd27f  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800cd283  call    cs:__imp_RtlReleaseRelativeName
0x1800cd289  mov     rcx, gs:60h
0x1800cd292  mov     r8, rbx; P
0x1800cd295  xor     edx, edx; Flags
0x1800cd297  mov     rcx, [rcx+30h]; HeapHandle
0x1800cd29b  call    cs:__imp_RtlFreeHeap
0x1800cd2a1  bt      r14, 20h ; ' '
0x1800cd2a6  mov     edi, 1
0x1800cd2ab  jb      short loc_1800CD304
0x1800cd2ad  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800cd2b1  lea     r9d, [rdi+3]; Length
0x1800cd2b5  lea     r8, [rbp+57h+arg_10]; FileInformation
0x1800cd2b9  mov     [rbp+57h+arg_10], 3
0x1800cd2c0  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800cd2c4  mov     [rsp+0E0h+ShareAccess], 40h ; '@'; FileInformationClass
0x1800cd2cc  call    cs:__imp_NtSetInformationFile
0x1800cd2d2  mov     ebx, eax
0x1800cd2d4  mov     eax, 80000000h
0x1800cd2d9  lea     ecx, [rbx+rax]
0x1800cd2dc  test    eax, ecx
0x1800cd2de  jz      short loc_1800CD2FC
0x1800cd2e0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800cd2e4  call    cs:__imp_NtClose
0x1800cd2ea  test    ebx, ebx
0x1800cd2ec  js      short loc_1800CD2F5
0x1800cd2ee  mov     eax, edi
0x1800cd2f0  jmp     loc_1800CD1B2
0x1800cd2f5  mov     ecx, ebx
0x1800cd2f7  jmp     loc_1800CD1AB
0x1800cd2fc  cmp     ebx, 0C0000121h
0x1800cd302  jz      short loc_1800CD2E0
0x1800cd304  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800cd308  lea     r8, [rbp+57h+arg_8]; FileInformation
0x1800cd30c  mov     r9d, edi; Length
0x1800cd30f  mov     [rbp+57h+arg_8], dil
0x1800cd313  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800cd317  mov     [rsp+0E0h+ShareAccess], 0Dh; FileInformationClass
0x1800cd31f  call    cs:__imp_NtSetInformationFile
0x1800cd325  mov     ebx, eax
0x1800cd327  jmp     short loc_1800CD2E0
0x1800cd329  cmp     eax, 0C000009Ah
0x1800cd32e  jz      loc_1800CD1A9
0x1800cd334  mov     ecx, 3; LastError
0x1800cd339  call    cs:__imp_RtlSetLastWin32Error
0x1800cd33f  jmp     loc_1800CD1B0
0x1800cd344  mov     word ptr [rbp+57h+P], ax
0x1800cd348  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800cd34b  mov     dword ptr [rbp+57h+P+2], eax
0x1800cd34e  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800cd352  mov     word ptr [rbp+57h+P+6], ax
0x1800cd356  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800cd35a  mov     [rbp+57h+P+8], rax
0x1800cd35e  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800cd362  jmp     loc_1800CD1E5
0x1800cd367  cmp     edi, 0C000000Dh
0x1800cd36d  jnz     loc_180193C69
0x1800cd373  mov     [rsp+0E0h+OpenOptions], 4040h
0x1800cd37b  jmp     loc_180193BEE
0x1800cd380  cmp     edi, 0C0000002h
0x1800cd386  jz      loc_1800CD276
0x1800cd38c  cmp     edi, 0C000000Dh
0x1800cd392  jz      loc_1800CD276
0x1800cd398  jmp     loc_180193C36
0x1800cd39d  mov     eax, dword ptr [rbp+57h+FileInformation+4]
0x1800cd3a0  add     eax, 5FFFFFFDh
0x1800cd3a5  cmp     eax, 16h
0x1800cd3a8  ja      loc_180193C76
0x1800cd3ae  mov     ecx, 400201h
0x1800cd3b3  bt      ecx, eax
0x1800cd3b6  jb      loc_1800CD276
0x1800cd3bc  jmp     loc_180193C76
0x1800cd3c1  mov     rdx, [rbp+57h+FileHandle]
0x1800cd3c5  mov     rcx, [rbp+57h+P+8]
0x1800cd3c9  call    BasepGetFileRedirectionStatus
0x1800cd3ce  mov     edi, eax
0x1800cd3d0  test    eax, eax
0x1800cd3d2  js      loc_180193C36
0x1800cd3d8  jmp     loc_1800CD27F
0x180193be6  mov     [rsp+0E0h+OpenOptions], 204040h; OpenOptions
0x180193bee  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180193bf2  mov     [rsp+0E0h+ShareAccess], r13d; ShareAccess
0x180193bf7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180193bfb  mov     edx, r12d; DesiredAccess
0x180193bfe  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180193c02  call    cs:__imp_NtOpenFile
0x180193c08  mov     edi, eax
0x180193c0a  test    eax, eax
0x180193c0c  jns     loc_1800CD276
0x180193c12  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x180193c16  call    cs:__imp_RtlReleaseRelativeName
0x180193c1c  mov     rcx, gs:60h
0x180193c25  mov     r8, rbx; P
0x180193c28  xor     edx, edx; Flags
0x180193c2a  mov     rcx, [rcx+30h]; HeapHandle
0x180193c2e  call    cs:__imp_RtlFreeHeap
0x180193c34  jmp     short loc_180193C62
0x180193c36  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x180193c3a  call    cs:__imp_RtlReleaseRelativeName
0x180193c40  mov     rcx, gs:60h
0x180193c49  mov     r8, rbx; P
0x180193c4c  xor     edx, edx; Flags
0x180193c4e  mov     rcx, [rcx+30h]; HeapHandle
0x180193c52  call    cs:__imp_RtlFreeHeap
0x180193c58  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180193c5c  call    cs:__imp_NtClose
0x180193c62  mov     ecx, edi
0x180193c64  jmp     loc_1800CD1AB
0x180193c69  cmp     edi, 0C0000022h
0x180193c6f  jnz     short loc_180193C12
0x180193c71  jmp     loc_180193BE6
0x180193c76  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180193c7a  call    cs:__imp_NtClose
0x180193c80  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180193c84  mov     [rsp+0E0h+OpenOptions], 4040h; OpenOptions
0x180193c8c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180193c90  mov     [rsp+0E0h+ShareAccess], r13d; ShareAccess
0x180193c95  mov     edx, r12d; DesiredAccess
0x180193c98  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180193c9c  call    cs:__imp_NtOpenFile
0x180193ca2  mov     edi, eax
0x180193ca4  test    eax, eax
0x180193ca6  jns     loc_1800CD276
0x180193cac  lea     ecx, [rax+3FFFFD8Ah]
0x180193cb2  test    ecx, 0FFFFFFFCh
0x180193cb8  jnz     loc_180193C12
0x180193cbe  cmp     eax, 0C0000277h
0x180193cc3  jz      loc_180193C12
0x180193cc9  jmp     loc_180193BE6
```
