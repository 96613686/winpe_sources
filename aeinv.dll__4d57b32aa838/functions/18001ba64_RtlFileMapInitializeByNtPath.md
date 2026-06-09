# RtlFileMapInitializeByNtPath

- ea: `0x18001ba64`
- end: `0x18001bb3c`
- name: `RtlFileMapInitializeByNtPath`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b5bc`

## callees

- `0x18001ba64`

## import_xrefs

- `ntdll!ZwCreateFile` at `0x18001baf3`
- `ntdll!ZwCreateFile` at `0x18001baf3`
- `ntdll!ZwClose` at `0x18001bb34`
- `ntdll!ZwClose` at `0x18001bb34`

## pseudocode

```c
__int64 __fastcall RtlFileMapInitializeByNtPath(__int64 a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp+17h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+27h] BYREF
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
0x18001ba64  mov     rax, rsp
0x18001ba67  mov     [rax+8], rbx
0x18001ba6b  mov     [rax+18h], rdi
0x18001ba6f  push    rbp
0x18001ba70  lea     rbp, [rax-5Fh]
0x18001ba74  sub     rsp, 0A0h
0x18001ba7b  mov     dword ptr [rax-58h], 0
0x18001ba82  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001ba86  mov     qword ptr [rax-60h], 0
0x18001ba8e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001ba92  mov     dword ptr [rax-68h], 60h ; '`'
0x18001ba99  xorps   xmm0, xmm0
0x18001ba9c  mov     dword ptr [rax-70h], 1
0x18001baa3  mov     rdi, rcx
0x18001baa6  mov     dword ptr [rax-78h], 5
0x18001baad  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001bab1  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x18001bab5  mov     edx, 80100080h; DesiredAccess
0x18001baba  mov     dword ptr [rax-80h], 80h
0x18001bac1  mov     [rsp+0A0h+AllocationSize], 0; AllocationSize
0x18001baca  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001bad2  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001bada  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001bade  mov     [rbp+57h+FileHandle], 0
0x18001bae6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18001baee  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001baf3  call    cs:__imp_ZwCreateFile
0x18001baf9  mov     ebx, eax
0x18001bafb  test    eax, eax
0x18001bafd  jns     short loc_18001BB1F
0x18001baff  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18001bb03  test    rcx, rcx
0x18001bb06  jnz     short loc_18001BB34
0x18001bb08  lea     r11, [rsp+0A0h+var_s0]
0x18001bb10  mov     eax, ebx
0x18001bb12  mov     rbx, [r11+10h]
0x18001bb16  mov     rdi, [r11+20h]
0x18001bb1a  mov     rsp, r11
0x18001bb1d  pop     rbp
0x18001bb1e  retn
0x18001bb1f  mov     rax, [rbp+57h+FileHandle]
0x18001bb23  xor     ecx, ecx
0x18001bb25  mov     [rdi], rax
0x18001bb28  xor     ebx, ebx
0x18001bb2a  mov     [rbp+57h+FileHandle], rcx
0x18001bb2e  mov     byte ptr [rdi+28h], 1
0x18001bb32  jmp     short loc_18001BB03
0x18001bb34  call    cs:__imp_ZwClose
0x18001bb3a  jmp     short loc_18001BB08
```
