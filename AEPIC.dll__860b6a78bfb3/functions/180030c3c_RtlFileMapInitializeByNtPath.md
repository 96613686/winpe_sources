# RtlFileMapInitializeByNtPath

- ea: `0x180030c3c`
- end: `0x180030d12`
- name: `RtlFileMapInitializeByNtPath`
- size: `214`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800301b8`

## callees

- `0x180030c3c`

## import_xrefs

- `ntdll!ZwClose` at `0x180030cf5`
- `ntdll!ZwClose` at `0x180030cf5`
- `ntdll!ZwCreateFile` at `0x180030ccb`
- `ntdll!ZwCreateFile` at `0x180030ccb`

## pseudocode

```c
__int64 __fastcall RtlFileMapInitializeByNtPath(__int64 a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp+6Fh] BYREF

  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 5u, 1u, 0x60u, 0, 0);
  if ( v3 < 0 )
  {
    v4 = FileHandle;
  }
  else
  {
    v4 = 0;
    *(_QWORD *)a1 = FileHandle;
    v3 = 0;
    FileHandle = 0;
    *(_BYTE *)(a1 + 40) = 1;
  }
  if ( v4 )
    ZwClose(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180030c3c  mov     rax, rsp
0x180030c3f  mov     [rax+8], rbx
0x180030c43  mov     [rax+18h], rdi
0x180030c47  push    rbp
0x180030c48  lea     rbp, [rax-5Fh]
0x180030c4c  sub     rsp, 0A0h
0x180030c53  mov     dword ptr [rax-58h], 0
0x180030c5a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180030c5e  mov     qword ptr [rax-60h], 0
0x180030c66  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180030c6a  mov     dword ptr [rax-68h], 60h ; '`'
0x180030c71  xorps   xmm0, xmm0
0x180030c74  mov     dword ptr [rax-70h], 1
0x180030c7b  mov     rdi, rcx
0x180030c7e  mov     dword ptr [rax-78h], 5
0x180030c85  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180030c89  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x180030c8d  mov     edx, 80100080h; DesiredAccess
0x180030c92  mov     dword ptr [rax-80h], 80h
0x180030c99  mov     [rsp+0A0h+AllocationSize], 0; AllocationSize
0x180030ca2  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180030caa  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180030cb2  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180030cb6  mov     [rbp+57h+FileHandle], 0
0x180030cbe  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180030cc6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180030ccb  call    cs:__imp_ZwCreateFile
0x180030cd1  mov     ebx, eax
0x180030cd3  test    eax, eax
0x180030cd5  js      short loc_180030CEC
0x180030cd7  mov     rax, [rbp+57h+FileHandle]
0x180030cdb  xor     ecx, ecx
0x180030cdd  mov     [rdi], rax
0x180030ce0  xor     ebx, ebx
0x180030ce2  mov     [rbp+57h+FileHandle], rcx
0x180030ce6  mov     byte ptr [rdi+28h], 1
0x180030cea  jmp     short loc_180030CF0
0x180030cec  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180030cf0  test    rcx, rcx
0x180030cf3  jz      short loc_180030CFB
0x180030cf5  call    cs:__imp_ZwClose
0x180030cfb  lea     r11, [rsp+0A0h+var_s0]
0x180030d03  mov     eax, ebx
0x180030d05  mov     rbx, [r11+10h]
0x180030d09  mov     rdi, [r11+20h]
0x180030d0d  mov     rsp, r11
0x180030d10  pop     rbp
0x180030d11  retn
```
