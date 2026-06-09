# CDfsShellAdmin::AdminFlushPKT(ushort *)

- ea: `0x180007d90`
- end: `0x180007ec3`
- name: `?AdminFlushPKT@CDfsShellAdmin@@UEAAJPEAG@Z`
- size: `307`
- prototype: `int(CDfsShellAdmin *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007d90`

## import_xrefs

- `ntdll!NtClose` at `0x180007e94`
- `ntdll!NtClose` at `0x180007e94`
- `ntdll!RtlInitUnicodeString` at `0x180007dd5`
- `ntdll!RtlInitUnicodeString` at `0x180007dd5`
- `ntdll!NtFsControlFile` at `0x180007e88`
- `ntdll!NtFsControlFile` at `0x180007e88`
- `ntdll!NtCreateFile` at `0x180007e3c`
- `ntdll!NtCreateFile` at `0x180007e3c`
- `ntdll!RtlNtStatusToDosError` at `0x180007e9c`
- `ntdll!RtlNtStatusToDosError` at `0x180007e9c`

## pseudocode

```c
int __fastcall CDfsShellAdmin::AdminFlushPKT(CDfsShellAdmin *this, unsigned __int16 *a2)
{
  NTSTATUS v3; // eax
  NTSTATUS v4; // ecx
  __int64 v5; // rax
  NTSTATUS v6; // ebx
  int result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+77h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Dfs");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtCreateFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 3u, 0xA0u, 0, 0);
  if ( v3 >= 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x69FF0u, a2, 2 * v5, 0, 0);
    NtClose(FileHandle);
    v4 = v6;
  }
  else
  {
    v4 = v3;
  }
  result = RtlNtStatusToDosError(v4);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007d90  mov     [rsp-8+arg_0], rbx
0x180007d95  mov     [rsp-8+arg_8], rdi
0x180007d9a  push    rbp
0x180007d9b  lea     rbp, [rsp-57h]
0x180007da0  sub     rsp, 0B0h
0x180007da7  xorps   xmm1, xmm1
0x180007daa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180007dae  xorps   xmm0, xmm0
0x180007db1  mov     rbx, rdx
0x180007db4  xor     edi, edi
0x180007db6  lea     rdx, SourceString; "\\Dfs"
0x180007dbd  mov     [rbp+57h+FileHandle], rdi
0x180007dc1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180007dc5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180007dc9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x180007dcd  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180007dd1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180007dd5  call    cs:__imp_RtlInitUnicodeString
0x180007ddb  mov     [rsp+0B0h+EaLength], edi; EaLength
0x180007ddf  lea     rax, [rbp+57h+DestinationString]
0x180007de3  mov     [rsp+0B0h+EaBuffer], rdi; EaBuffer
0x180007de8  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180007dec  mov     [rsp+0B0h+CreateOptions], 0A0h; CreateOptions
0x180007df4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180007df8  mov     [rsp+0B0h+CreateDisposition], 3; CreateDisposition
0x180007e00  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180007e04  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x180007e0c  xorps   xmm0, xmm0
0x180007e0f  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x180007e17  mov     edx, 100002h; DesiredAccess
0x180007e1c  mov     [rsp+0B0h+AllocationSize], rdi; AllocationSize
0x180007e21  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180007e28  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180007e2c  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180007e33  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180007e37  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180007e3c  call    cs:__imp_NtCreateFile
0x180007e42  test    eax, eax
0x180007e44  jns     short loc_180007E4A
0x180007e46  mov     ecx, eax
0x180007e48  jmp     short loc_180007E9C
0x180007e4a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007e4e  inc     rax
0x180007e51  cmp     [rbx+rax*2], di
0x180007e55  jnz     short loc_180007E4E
0x180007e57  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180007e5b  add     eax, eax
0x180007e5d  mov     dword ptr [rsp+0B0h+EaBuffer], edi; OutputBufferLength
0x180007e61  xor     r9d, r9d; ApcContext
0x180007e64  mov     qword ptr [rsp+0B0h+CreateOptions], rdi; OutputBuffer
0x180007e69  xor     r8d, r8d; ApcRoutine
0x180007e6c  mov     [rsp+0B0h+CreateDisposition], eax; InputBufferLength
0x180007e70  xor     edx, edx; Event
0x180007e72  mov     qword ptr [rsp+0B0h+ShareAccess], rbx; InputBuffer
0x180007e77  lea     rax, [rbp+57h+IoStatusBlock]
0x180007e7b  mov     [rsp+0B0h+FileAttributes], 69FF0h; FsControlCode
0x180007e83  mov     [rsp+0B0h+AllocationSize], rax; IoStatusBlock
0x180007e88  call    cs:__imp_NtFsControlFile
0x180007e8e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180007e92  mov     ebx, eax
0x180007e94  call    cs:__imp_NtClose
0x180007e9a  mov     ecx, ebx; Status
0x180007e9c  call    cs:__imp_RtlNtStatusToDosError
0x180007ea2  test    eax, eax
0x180007ea4  jle     short loc_180007EAE
0x180007ea6  movzx   eax, ax
0x180007ea9  or      eax, 80070000h
0x180007eae  lea     r11, [rsp+0B0h+var_s0]
0x180007eb6  mov     rbx, [r11+10h]
0x180007eba  mov     rdi, [r11+18h]
0x180007ebe  mov     rsp, r11
0x180007ec1  pop     rbp
0x180007ec2  retn
```
