# RtlFileMapInitializeByNtPath

- ea: `0x14003d574`
- end: `0x14003d64a`
- name: `RtlFileMapInitializeByNtPath`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003cb70`

## callees

- `0x14003d574`

## import_xrefs

- `ntdll!ZwClose` at `0x14003d62d`
- `ntdll!ZwClose` at `0x14003d62d`
- `ntdll!ZwCreateFile` at `0x14003d603`
- `ntdll!ZwCreateFile` at `0x14003d603`

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
0x14003d574  mov     rax, rsp
0x14003d577  mov     [rax+8], rbx
0x14003d57b  mov     [rax+18h], rdi
0x14003d57f  push    rbp
0x14003d580  lea     rbp, [rax-5Fh]
0x14003d584  sub     rsp, 0A0h
0x14003d58b  mov     dword ptr [rax-58h], 0
0x14003d592  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14003d596  mov     qword ptr [rax-60h], 0
0x14003d59e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14003d5a2  mov     dword ptr [rax-68h], 60h ; '`'
0x14003d5a9  xorps   xmm0, xmm0
0x14003d5ac  mov     dword ptr [rax-70h], 1
0x14003d5b3  mov     rdi, rcx
0x14003d5b6  mov     dword ptr [rax-78h], 5
0x14003d5bd  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14003d5c1  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x14003d5c5  mov     edx, 80100080h; DesiredAccess
0x14003d5ca  mov     dword ptr [rax-80h], 80h
0x14003d5d1  mov     [rsp+0A0h+AllocationSize], 0; AllocationSize
0x14003d5da  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14003d5e2  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14003d5ea  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14003d5ee  mov     [rbp+57h+FileHandle], 0
0x14003d5f6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14003d5fe  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003d603  call    cs:__imp_ZwCreateFile
0x14003d609  mov     ebx, eax
0x14003d60b  test    eax, eax
0x14003d60d  js      short loc_14003D624
0x14003d60f  mov     rax, [rbp+57h+FileHandle]
0x14003d613  xor     ecx, ecx
0x14003d615  mov     [rdi], rax
0x14003d618  xor     ebx, ebx
0x14003d61a  mov     [rbp+57h+FileHandle], rcx
0x14003d61e  mov     byte ptr [rdi+28h], 1
0x14003d622  jmp     short loc_14003D628
0x14003d624  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14003d628  test    rcx, rcx
0x14003d62b  jz      short loc_14003D633
0x14003d62d  call    cs:__imp_ZwClose
0x14003d633  lea     r11, [rsp+0A0h+var_s0]
0x14003d63b  mov     eax, ebx
0x14003d63d  mov     rbx, [r11+10h]
0x14003d641  mov     rdi, [r11+20h]
0x14003d645  mov     rsp, r11
0x14003d648  pop     rbp
0x14003d649  retn
```
