# SIPolicyPmCreateFolder

- ea: `0x18002225c`
- end: `0x180022306`
- name: `SIPolicyPmCreateFolder`
- size: `170`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800220e0`

## callees

- `0x18002225c`

## import_xrefs

- `ntdll!ZwClose` at `0x1800222ed`
- `ntdll!ZwClose` at `0x1800222ed`
- `ntdll!ZwCreateFile` at `0x1800222dc`
- `ntdll!ZwCreateFile` at `0x1800222dc`

## pseudocode

```c
__int64 __fastcall SIPolicyPmCreateFolder(struct _UNICODE_STRING *a1)
{
  unsigned int v1; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp+67h] BYREF

  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwCreateFile(&FileHandle, 0x40120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0x21u, 0, 0);
  if ( FileHandle )
    ZwClose(FileHandle);
  return v1;
}

```

## disassembly

```asm
0x18002225c  mov     [rsp-8+arg_8], rbx
0x180022261  push    rbp
0x180022262  lea     rbp, [rsp-57h]
0x180022267  sub     rsp, 0A0h
0x18002226e  xor     eax, eax
0x180022270  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x180022274  mov     [rsp+0A0h+EaLength], eax; EaLength
0x180022278  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002227c  mov     [rsp+0A0h+EaBuffer], rax; EaBuffer
0x180022281  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180022285  mov     [rsp+0A0h+CreateOptions], 21h ; '!'; CreateOptions
0x18002228d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180022291  xorps   xmm0, xmm0
0x180022294  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180022298  mov     eax, 3
0x18002229d  mov     [rbp+57h+FileHandle], 0
0x1800222a5  mov     [rsp+0A0h+CreateDisposition], eax; CreateDisposition
0x1800222a9  mov     edx, 40120089h; DesiredAccess
0x1800222ae  mov     [rsp+0A0h+ShareAccess], eax; ShareAccess
0x1800222b2  mov     [rsp+0A0h+FileAttributes], 80h; FileAttributes
0x1800222ba  mov     [rsp+0A0h+AllocationSize], 0; AllocationSize
0x1800222c3  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800222c7  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800222cf  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800222d7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800222dc  call    cs:__imp_ZwCreateFile
0x1800222e2  mov     ebx, eax
0x1800222e4  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800222e8  test    rcx, rcx
0x1800222eb  jz      short loc_1800222F3
0x1800222ed  call    cs:__imp_ZwClose
0x1800222f3  mov     eax, ebx
0x1800222f5  mov     rbx, [rsp+0A0h+arg_8]
0x1800222fd  add     rsp, 0A0h
0x180022304  pop     rbp
0x180022305  retn
```
