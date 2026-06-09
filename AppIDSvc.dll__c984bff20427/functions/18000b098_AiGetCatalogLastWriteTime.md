# AiGetCatalogLastWriteTime

- ea: `0x18000b098`
- end: `0x18000b1c5`
- name: `AiGetCatalogLastWriteTime`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a0f8`

## callees

- `0x18000b098`
- `0x18000c0e0`

## import_xrefs

- `ntdll!NtClose` at `0x18000b19c`
- `ntdll!NtClose` at `0x18000b19c`
- `ntdll!NtQueryInformationFile` at `0x18000b180`
- `ntdll!NtQueryInformationFile` at `0x18000b180`
- `ntdll!NtCreateFile` at `0x18000b153`
- `ntdll!NtCreateFile` at `0x18000b153`

## string_xrefs

- `0x18000b0e3`: `\SystemRoot\System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`

## pseudocode

```c
__int64 __fastcall AiGetCatalogLastWriteTime(_QWORD *a1)
{
  NTSTATUS v2; // ebx
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v5[2]; // [rsp+68h] [rbp-31h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-11h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp+1Fh] BYREF
  __int128 v9; // [rsp+C8h] [rbp+2Fh]
  __int64 v10; // [rsp+D8h] [rbp+3Fh]

  v10 = 0;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v5[1] = L"\\SystemRoot\\System32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\";
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v5;
  v5[0] = 9044104;
  ObjectAttributes.RootDirectory = 0;
  FileInformation = 0;
  v9 = 0;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtCreateFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 1u, 0, 0);
  if ( v2 >= 0 )
  {
    IoStatusBlock = 0;
    v2 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    if ( v2 >= 0 )
      *a1 = v9;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b098  mov     [rsp-8+arg_8], rbx
0x18000b09d  mov     [rsp-8+arg_10], rdi
0x18000b0a2  push    rbp
0x18000b0a3  lea     rbp, [rsp-57h]
0x18000b0a8  sub     rsp, 0F0h
0x18000b0af  mov     rax, cs:__security_cookie
0x18000b0b6  xor     rax, rsp
0x18000b0b9  mov     [rbp+57h+var_10], rax
0x18000b0bd  xor     eax, eax
0x18000b0bf  mov     [rsp+0F0h+EaLength], 0; EaLength
0x18000b0c7  mov     [rsp+0F0h+EaBuffer], 0; EaBuffer
0x18000b0d0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000b0d4  xorps   xmm0, xmm0
0x18000b0d7  mov     [rbp+57h+var_18], rax
0x18000b0db  mov     [rbp+57h+FileHandle], rax
0x18000b0df  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000b0e3  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\CatRoot\\{F750E"...
0x18000b0ea  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000b0f2  mov     [rbp+57h+var_80], rax
0x18000b0f6  mov     rdi, rcx
0x18000b0f9  lea     rax, [rbp+57h+var_88]
0x18000b0fd  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18000b105  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000b109  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000b10d  mov     eax, 1
0x18000b112  mov     [rbp+57h+var_88], 8A0088h
0x18000b11a  mov     [rsp+0F0h+CreateOptions], eax; CreateOptions
0x18000b11e  mov     [rsp+0F0h+CreateDisposition], eax; CreateDisposition
0x18000b122  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x18000b12a  lea     edx, [rax+7Fh]; DesiredAccess
0x18000b12d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000b135  mov     [rsp+0F0h+FileAttributes], edx; FileAttributes
0x18000b139  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x18000b142  movups  [rbp+57h+FileInformation], xmm0
0x18000b146  movups  [rbp+57h+var_28], xmm0
0x18000b14a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000b14e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b153  call    cs:__imp_NtCreateFile
0x18000b159  mov     ebx, eax
0x18000b15b  test    eax, eax
0x18000b15d  js      short loc_18000B193
0x18000b15f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000b163  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000b167  xorps   xmm0, xmm0
0x18000b16a  mov     dword ptr [rsp+0F0h+AllocationSize], 4; FileInformationClass
0x18000b172  mov     r9d, 28h ; '('; Length
0x18000b178  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000b17c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000b180  call    cs:__imp_NtQueryInformationFile
0x18000b186  mov     ebx, eax
0x18000b188  test    eax, eax
0x18000b18a  js      short loc_18000B193
0x18000b18c  mov     rax, qword ptr [rbp+57h+var_28]
0x18000b190  mov     [rdi], rax
0x18000b193  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000b197  test    rcx, rcx
0x18000b19a  jz      short loc_18000B1A2
0x18000b19c  call    cs:__imp_NtClose
0x18000b1a2  mov     eax, ebx
0x18000b1a4  mov     rcx, [rbp+57h+var_10]
0x18000b1a8  xor     rcx, rsp; StackCookie
0x18000b1ab  call    __security_check_cookie
0x18000b1b0  lea     r11, [rsp+0F0h+var_s0]
0x18000b1b8  mov     rbx, [r11+18h]
0x18000b1bc  mov     rdi, [r11+20h]
0x18000b1c0  mov     rsp, r11
0x18000b1c3  pop     rbp
0x18000b1c4  retn
```
