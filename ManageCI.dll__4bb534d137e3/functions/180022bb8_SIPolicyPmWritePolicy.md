# SIPolicyPmWritePolicy

- ea: `0x180022bb8`
- end: `0x180022c9d`
- name: `SIPolicyPmWritePolicy`
- size: `229`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, void *, ULONG)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021bd8`
- `0x180021e34`
- `0x180021ffc`

## callees

- `0x180022bb8`

## import_xrefs

- `ntdll!ZwWriteFile` at `0x180022c78`
- `ntdll!ZwWriteFile` at `0x180022c78`
- `ntdll!ZwClose` at `0x180022c89`
- `ntdll!ZwClose` at `0x180022c89`
- `ntdll!ZwCreateFile` at `0x180022c3c`
- `ntdll!ZwCreateFile` at `0x180022c3c`

## pseudocode

```c
__int64 __fastcall SIPolicyPmWritePolicy(__int64 a1, struct _UNICODE_STRING *a2, void *a3, ULONG a4)
{
  NTSTATUS v6; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+67h] BYREF

  ObjectAttributes.ObjectName = a2;
  FileHandle = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 5u, 0x20u, 0, 0);
  if ( v6 >= 0 )
    v6 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, a3, a4, 0, 0);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022bb8  mov     [rsp-8+FileHandle], rcx
0x180022bbd  push    rbp
0x180022bbe  push    rbx
0x180022bbf  push    rsi
0x180022bc0  push    rdi
0x180022bc1  lea     rbp, [rsp-3Fh]
0x180022bc6  sub     rsp, 0A8h
0x180022bcd  xor     eax, eax
0x180022bcf  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x180022bd3  mov     [rsp+0C0h+EaLength], eax; EaLength
0x180022bd7  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180022bdb  mov     [rsp+0C0h+EaBuffer], rax; EaBuffer
0x180022be0  xorps   xmm0, xmm0
0x180022be3  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x180022beb  mov     edi, r9d
0x180022bee  mov     [rsp+0C0h+CreateDisposition], 5; CreateDisposition
0x180022bf6  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180022bfa  mov     [rsp+0C0h+ShareAccess], eax; ShareAccess
0x180022bfe  mov     rsi, r8
0x180022c01  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x180022c09  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180022c0d  mov     edx, 12019Fh; DesiredAccess
0x180022c12  mov     [rsp+0C0h+AllocationSize], rax; AllocationSize
0x180022c17  mov     [rbp+57h+FileHandle], 0
0x180022c1f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180022c23  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180022c2b  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180022c33  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180022c37  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180022c3c  call    cs:__imp_ZwCreateFile
0x180022c42  mov     ebx, eax
0x180022c44  test    eax, eax
0x180022c46  js      short loc_180022C80
0x180022c48  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180022c4c  lea     rax, [rbp+57h+IoStatusBlock]
0x180022c50  mov     qword ptr [rsp+0C0h+CreateOptions], 0; Key
0x180022c59  xor     r9d, r9d; ApcContext
0x180022c5c  mov     qword ptr [rsp+0C0h+CreateDisposition], 0; ByteOffset
0x180022c65  xor     r8d, r8d; ApcRoutine
0x180022c68  mov     [rsp+0C0h+ShareAccess], edi; Length
0x180022c6c  xor     edx, edx; Event
0x180022c6e  mov     qword ptr [rsp+0C0h+FileAttributes], rsi; Buffer
0x180022c73  mov     [rsp+0C0h+AllocationSize], rax; IoStatusBlock
0x180022c78  call    cs:__imp_ZwWriteFile
0x180022c7e  mov     ebx, eax
0x180022c80  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180022c84  test    rcx, rcx
0x180022c87  jz      short loc_180022C8F
0x180022c89  call    cs:__imp_ZwClose
0x180022c8f  mov     eax, ebx
0x180022c91  add     rsp, 0A8h
0x180022c98  pop     rdi
0x180022c99  pop     rsi
0x180022c9a  pop     rbx
0x180022c9b  pop     rbp
0x180022c9c  retn
```
