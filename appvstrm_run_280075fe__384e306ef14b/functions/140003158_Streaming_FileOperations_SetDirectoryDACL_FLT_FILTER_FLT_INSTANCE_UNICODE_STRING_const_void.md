# Streaming::FileOperations::SetDirectoryDACL(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,void *)

- ea: `0x140003158`
- end: `0x14000327c`
- name: `?SetDirectoryDACL@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@PEAX@Z`
- size: `292`
- prototype: `int(Streaming::FileOperations *__hidden this, struct _FLT_FILTER *, struct _FLT_INSTANCE *, const struct _UNICODE_STRING *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400020c8`

## callees

- `0x140003158`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140003261`
- `ntoskrnl!ObfDereferenceObject` at `0x140003261`
- `FLTMGR!FltCreateFileEx` at `0x14000320b`
- `FLTMGR!FltCreateFileEx` at `0x14000320b`
- `FLTMGR!FltClose` at `0x140003244`
- `FLTMGR!FltClose` at `0x140003244`
- `FLTMGR!FltSetSecurityObject` at `0x14000322d`
- `FLTMGR!FltSetSecurityObject` at `0x14000322d`

## pseudocode

```c
__int64 __fastcall Streaming::FileOperations::SetDirectoryDACL(
        Streaming::FileOperations *this,
        struct _FLT_FILTER *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  NTSTATUS v6; // ebx
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-1h] BYREF
  void *FileHandle; // [rsp+110h] [rbp+77h] BYREF

  ObjectAttributes.ObjectName = a3;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  FileObject = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = FltCreateFileEx(
         this,
         a2,
         &FileHandle,
         &FileObject,
         0x40000u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x80u,
         7u,
         1u,
         0x21u,
         0,
         0,
         0);
  if ( v6 >= 0 )
    v6 = FltSetSecurityObject(a2, FileObject, 4u, a4);
  if ( FileHandle )
  {
    FltClose(FileHandle);
    FileHandle = 0;
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140003158  push    rbp
0x14000315a  push    rbx
0x14000315b  push    rsi
0x14000315c  push    rdi
0x14000315d  lea     rbp, [rsp-3Fh]
0x140003162  sub     rsp, 0D8h
0x140003169  mov     [rsp+0F0h+Flags], 0; Flags
0x140003171  lea     rax, [rbp+57h+var_68]
0x140003175  mov     [rsp+0F0h+EaLength], 0; EaLength
0x14000317d  xorps   xmm0, xmm0
0x140003180  mov     [rsp+0F0h+EaBuffer], 0; EaBuffer
0x140003189  mov     rsi, r9
0x14000318c  mov     [rsp+0F0h+CreateOptions], 21h ; '!'; CreateOptions
0x140003194  lea     r9, [rbp+57h+FileObject]; FileObject
0x140003198  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x1400031a0  mov     rdi, rdx
0x1400031a3  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1400031ab  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x1400031b3  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x1400031bc  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x1400031c1  lea     rax, [rbp+57h+var_58]
0x1400031c5  mov     [rbp+57h+var_58.ObjectName], r8
0x1400031c9  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x1400031cd  mov     [rsp+0F0h+ObjectAttributes], rax; ObjectAttributes
0x1400031d2  mov     [rsp+0F0h+DesiredAccess], 40000h; DesiredAccess
0x1400031da  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1400031de  mov     qword ptr [rbp+57h+var_58.Length], 30h ; '0'
0x1400031e6  mov     qword ptr [rbp+57h+var_58.Attributes], 240h
0x1400031ee  mov     [rbp+57h+FileObject], 0
0x1400031f6  mov     [rbp+57h+FileHandle], 0
0x1400031fe  mov     [rbp+57h+var_58.RootDirectory], 0
0x140003206  movdqu  xmmword ptr [rbp+57h+var_58.SecurityDescriptor], xmm0
0x14000320b  call    cs:__imp_FltCreateFileEx
0x140003212  nop     dword ptr [rax+rax+00h]
0x140003217  mov     ebx, eax
0x140003219  test    eax, eax
0x14000321b  js      short loc_14000323B
0x14000321d  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140003221  mov     r9, rsi; SecurityDescriptor
0x140003224  mov     r8d, 4; SecurityInformation
0x14000322a  mov     rcx, rdi; Instance
0x14000322d  call    cs:__imp_FltSetSecurityObject
0x140003234  nop     dword ptr [rax+rax+00h]
0x140003239  mov     ebx, eax
0x14000323b  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000323f  test    rcx, rcx
0x140003242  jz      short loc_140003258
0x140003244  call    cs:__imp_FltClose
0x14000324b  nop     dword ptr [rax+rax+00h]
0x140003250  mov     [rbp+57h+FileHandle], 0
0x140003258  mov     rcx, [rbp+57h+FileObject]; Object
0x14000325c  test    rcx, rcx
0x14000325f  jz      short loc_14000326D
0x140003261  call    cs:__imp_ObfDereferenceObject
0x140003268  nop     dword ptr [rax+rax+00h]
0x14000326d  mov     eax, ebx
0x14000326f  add     rsp, 0D8h
0x140003276  pop     rdi
0x140003277  pop     rsi
0x140003278  pop     rbx
0x140003279  pop     rbp
0x14000327a  retn
```
