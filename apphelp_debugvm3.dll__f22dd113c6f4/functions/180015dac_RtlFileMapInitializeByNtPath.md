# RtlFileMapInitializeByNtPath

- ea: `0x180015dac`
- end: `0x180015e84`
- name: `RtlFileMapInitializeByNtPath`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015a6c`

## callees

- `0x180015dac`

## import_xrefs

- `ntdll!ZwCreateFile` at `0x180015e3b`
- `ntdll!ZwCreateFile` at `0x180015e3b`
- `ntdll!ZwClose` at `0x180015e7c`
- `ntdll!ZwClose` at `0x180015e7c`

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
  if ( v3 >= 0 )
  {
    v4 = 0;
    *(_QWORD *)a1 = FileHandle;
    v3 = 0;
    FileHandle = 0;
    *(_BYTE *)(a1 + 40) = 1;
  }
  else
  {
    v4 = FileHandle;
  }
  if ( v4 )
    ZwClose(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180015dac  mov     rax, rsp
0x180015daf  mov     [rax+8], rbx
0x180015db3  mov     [rax+18h], rdi
0x180015db7  push    rbp
0x180015db8  lea     rbp, [rax-5Fh]
0x180015dbc  sub     rsp, 0A0h
0x180015dc3  mov     dword ptr [rax-58h], 0
0x180015dca  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180015dce  mov     qword ptr [rax-60h], 0
0x180015dd6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180015dda  mov     dword ptr [rax-68h], 60h ; '`'
0x180015de1  xorps   xmm0, xmm0
0x180015de4  mov     dword ptr [rax-70h], 1
0x180015deb  mov     rdi, rcx
0x180015dee  mov     dword ptr [rax-78h], 5
0x180015df5  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180015df9  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x180015dfd  mov     edx, 80100080h; DesiredAccess
0x180015e02  mov     dword ptr [rax-80h], 80h
0x180015e09  mov     [rsp+0A0h+AllocationSize], 0; AllocationSize
0x180015e12  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180015e1a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180015e22  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180015e26  mov     [rbp+57h+FileHandle], 0
0x180015e2e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180015e36  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180015e3b  call    cs:__imp_ZwCreateFile
0x180015e41  mov     ebx, eax
0x180015e43  test    eax, eax
0x180015e45  jns     short loc_180015E67
0x180015e47  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180015e4b  test    rcx, rcx
0x180015e4e  jnz     short loc_180015E7C
0x180015e50  lea     r11, [rsp+0A0h+var_s0]
0x180015e58  mov     eax, ebx
0x180015e5a  mov     rbx, [r11+10h]
0x180015e5e  mov     rdi, [r11+20h]
0x180015e62  mov     rsp, r11
0x180015e65  pop     rbp
0x180015e66  retn
0x180015e67  mov     rax, [rbp+57h+FileHandle]
0x180015e6b  xor     ecx, ecx
0x180015e6d  mov     [rdi], rax
0x180015e70  xor     ebx, ebx
0x180015e72  mov     [rbp+57h+FileHandle], rcx
0x180015e76  mov     byte ptr [rdi+28h], 1
0x180015e7a  jmp     short loc_180015E4B
0x180015e7c  call    cs:__imp_ZwClose
0x180015e82  jmp     short loc_180015E50
```
