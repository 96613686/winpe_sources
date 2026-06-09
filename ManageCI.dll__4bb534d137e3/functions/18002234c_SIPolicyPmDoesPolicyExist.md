# SIPolicyPmDoesPolicyExist

- ea: `0x18002234c`
- end: `0x1800223fb`
- name: `SIPolicyPmDoesPolicyExist`
- size: `175`
- prototype: `bool __fastcall(__int64, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021270`
- `0x18002195c`
- `0x180021af4`
- `0x180021bd8`

## callees

- `0x18002234c`

## import_xrefs

- `ntdll!ZwClose` at `0x1800223e2`
- `ntdll!ZwClose` at `0x1800223e2`
- `ntdll!ZwCreateFile` at `0x1800223cb`
- `ntdll!ZwCreateFile` at `0x1800223cb`

## pseudocode

```c
bool __fastcall SIPolicyPmDoesPolicyExist(__int64 a1, struct _UNICODE_STRING *a2)
{
  bool v2; // bl
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+6Fh] BYREF

  ObjectAttributes.ObjectName = a2;
  FileHandle = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0x20u, 0, 0) >= 0;
  if ( FileHandle )
    ZwClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x18002234c  mov     [rsp-8+arg_0], rbx
0x180022351  push    rbp
0x180022352  lea     rbp, [rsp-57h]
0x180022357  sub     rsp, 0A0h
0x18002235e  xor     eax, eax
0x180022360  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x180022364  mov     [rsp+0A0h+EaLength], eax; EaLength
0x180022368  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002236c  mov     [rsp+0A0h+EaBuffer], rax; EaBuffer
0x180022371  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180022375  mov     [rsp+0A0h+CreateOptions], 20h ; ' '; CreateOptions
0x18002237d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180022381  mov     [rsp+0A0h+CreateDisposition], 1; CreateDisposition
0x180022389  xorps   xmm0, xmm0
0x18002238c  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x180022394  mov     edx, 120089h; DesiredAccess
0x180022399  mov     [rsp+0A0h+FileAttributes], 80h; FileAttributes
0x1800223a1  mov     [rsp+0A0h+AllocationSize], rax; AllocationSize
0x1800223a6  mov     [rbp+57h+FileHandle], 0
0x1800223ae  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800223b2  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800223ba  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800223c2  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800223c6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800223cb  call    cs:__imp_ZwCreateFile
0x1800223d1  mov     ebx, eax
0x1800223d3  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800223d7  shr     ebx, 1Fh
0x1800223da  xor     bl, 1
0x1800223dd  test    rcx, rcx
0x1800223e0  jz      short loc_1800223E8
0x1800223e2  call    cs:__imp_ZwClose
0x1800223e8  mov     al, bl
0x1800223ea  mov     rbx, [rsp+0A0h+arg_0]
0x1800223f2  add     rsp, 0A0h
0x1800223f9  pop     rbp
0x1800223fa  retn
```
