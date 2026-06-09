# AiGetCatalogLastWriteTime

- ea: `0x140035d30`
- end: `0x140035e63`
- name: `AiGetCatalogLastWriteTime`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140027dc8`
- `0x140028300`

## callees

- `0x140006a20`
- `0x140035d30`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x140035e11`
- `ntoskrnl!ZwQueryInformationFile` at `0x140035e11`
- `ntoskrnl!ZwCreateFile` at `0x140035dde`
- `ntoskrnl!ZwCreateFile` at `0x140035dde`
- `ntoskrnl!ZwClose` at `0x140035e37`
- `ntoskrnl!ZwClose` at `0x140035e37`

## string_xrefs

- `0x140035d89`: `\SystemRoot\System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`

## pseudocode

```c
__int64 AiGetCatalogLastWriteTime()
{
  NTSTATUS v0; // ebx
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v3[2]; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-11h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp+1Fh] BYREF
  __int128 v7; // [rsp+C8h] [rbp+2Fh]
  __int64 v8; // [rsp+D8h] [rbp+3Fh]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v8 = 0;
  v3[1] = L"\\SystemRoot\\System32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\";
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  FileInformation = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v7 = 0;
  v3[0] = 9044104;
  IoStatusBlock = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v3;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwCreateFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 1u, 0, 0);
  if ( v0 >= 0 )
  {
    IoStatusBlock = 0;
    v0 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    if ( v0 >= 0 )
      qword_1400192D8 = v7;
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140035d30  mov     [rsp-8+arg_0], rbx
0x140035d35  push    rbp
0x140035d36  lea     rbp, [rsp-57h]
0x140035d3b  sub     rsp, 0F0h
0x140035d42  mov     rax, cs:__security_cookie
0x140035d49  xor     rax, rsp
0x140035d4c  mov     [rbp+57h+var_10], rax
0x140035d50  xor     ecx, ecx
0x140035d52  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140035d5a  mov     [rsp+0F0h+EaLength], ecx; EaLength
0x140035d5e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140035d62  mov     [rsp+0F0h+EaBuffer], rcx; EaBuffer
0x140035d67  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140035d6b  xorps   xmm0, xmm0
0x140035d6e  mov     [rsp+0F0h+CreateOptions], 1; CreateOptions
0x140035d76  xor     eax, eax
0x140035d78  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x140035d80  mov     [rbp+57h+var_18], rax
0x140035d84  mov     edx, 80h; DesiredAccess
0x140035d89  lea     rax, aSystemrootSyst_8; "\\SystemRoot\\System32\\CatRoot\\{F750E"...
0x140035d90  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x140035d98  mov     [rbp+57h+var_80], rax
0x140035d9c  lea     rax, [rbp+57h+var_88]
0x140035da0  mov     [rbp+57h+FileHandle], rcx
0x140035da4  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x140035da8  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x140035db0  mov     [rsp+0F0h+AllocationSize], rcx; AllocationSize
0x140035db5  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140035db9  movups  [rbp+57h+FileInformation], xmm0
0x140035dbd  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140035dc5  movups  [rbp+57h+var_28], xmm0
0x140035dc9  mov     [rbp+57h+var_88], 8A0088h
0x140035dd1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140035dd5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140035dd9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140035dde  call    cs:__imp_ZwCreateFile
0x140035de5  nop     dword ptr [rax+rax+00h]
0x140035dea  mov     ebx, eax
0x140035dec  test    eax, eax
0x140035dee  js      short loc_140035E2E
0x140035df0  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140035df4  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140035df8  xorps   xmm0, xmm0
0x140035dfb  mov     dword ptr [rsp+0F0h+AllocationSize], 4; FileInformationClass
0x140035e03  mov     r9d, 28h ; '('; Length
0x140035e09  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140035e0d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140035e11  call    cs:__imp_ZwQueryInformationFile
0x140035e18  nop     dword ptr [rax+rax+00h]
0x140035e1d  mov     ebx, eax
0x140035e1f  test    eax, eax
0x140035e21  js      short loc_140035E2E
0x140035e23  mov     rax, qword ptr [rbp+57h+var_28]
0x140035e27  mov     cs:qword_1400192D8, rax
0x140035e2e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140035e32  test    rcx, rcx
0x140035e35  jz      short loc_140035E43
0x140035e37  call    cs:__imp_ZwClose
0x140035e3e  nop     dword ptr [rax+rax+00h]
0x140035e43  mov     eax, ebx
0x140035e45  mov     rcx, [rbp+57h+var_10]
0x140035e49  xor     rcx, rsp; StackCookie
0x140035e4c  call    __security_check_cookie
0x140035e51  mov     rbx, [rsp+0F0h+arg_0]
0x140035e59  add     rsp, 0F0h
0x140035e60  pop     rbp
0x140035e61  retn
```
