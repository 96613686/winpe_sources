# BiCreateDirectoryPath

- ea: `0x14001ff78`
- end: `0x140020098`
- name: `BiCreateDirectoryPath`
- size: `288`
- prototype: `__int64 __fastcall(void *, const wchar_t *, ULONG)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001ff78`
- `0x1400200a0`

## callees

- `0x14001ff78`

## import_xrefs

- `msvcrt!wcschr` at `0x14001ffaa`
- `msvcrt!wcschr` at `0x14001ffaa`
- `ntdll!ZwClose` at `0x140020080`
- `ntdll!ZwClose` at `0x140020080`
- `ntdll!ZwCreateFile` at `0x14002004b`
- `ntdll!ZwCreateFile` at `0x14002004b`
- `ntdll!RtlInitUnicodeString` at `0x14001ffdf`
- `ntdll!RtlInitUnicodeString` at `0x14001ffdf`

## pseudocode

```c
__int64 __fastcall BiCreateDirectoryPath(void *a1, const wchar_t *a2, ULONG a3)
{
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  NTSTATUS v8; // eax
  unsigned int DirectoryPath; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+67h] BYREF

  FileHandle = 0;
  v6 = wcschr(a2, 0x5Cu);
  v7 = v6;
  if ( v6 )
    *v6 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 192;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, a3, 3u, 3u, 0x4021u, 0, 0);
  DirectoryPath = v8;
  if ( v7 )
    *v7 = 92;
  if ( v8 >= 0 && v7 )
    DirectoryPath = BiCreateDirectoryPath(FileHandle, v7 + 1, a3);
  if ( FileHandle )
    ZwClose(FileHandle);
  return DirectoryPath;
}

```

## disassembly

```asm
0x14001ff78  push    rbp
0x14001ff7a  push    rbx
0x14001ff7b  push    rsi
0x14001ff7c  push    rdi
0x14001ff7d  push    r12
0x14001ff7f  push    r14
0x14001ff81  lea     rbp, [rsp-2Fh]
0x14001ff86  sub     rsp, 0B8h
0x14001ff8d  mov     rdi, rdx
0x14001ff90  mov     [rbp+57h+FileHandle], 0
0x14001ff98  mov     r14, rcx
0x14001ff9b  mov     r12d, 5Ch ; '\'
0x14001ffa1  mov     edx, r12d; Ch
0x14001ffa4  mov     rcx, rdi; Str
0x14001ffa7  mov     esi, r8d
0x14001ffaa  call    cs:__imp_wcschr
0x14001ffb0  mov     rbx, rax
0x14001ffb3  test    rax, rax
0x14001ffb6  jz      short loc_14001FFBF
0x14001ffb8  xor     r8d, r8d
0x14001ffbb  mov     [rax], r8w
0x14001ffbf  xorps   xmm0, xmm0
0x14001ffc2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001ffc6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14001ffca  xor     eax, eax
0x14001ffcc  mov     rdx, rdi; SourceString
0x14001ffcf  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001ffd3  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14001ffd7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001ffdb  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001ffdf  call    cs:__imp_RtlInitUnicodeString
0x14001ffe5  mov     [rsp+0E0h+EaLength], 0; EaLength
0x14001ffed  lea     rax, [rbp+57h+DestinationString]
0x14001fff1  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x14001fffa  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001fffe  mov     [rsp+0E0h+CreateOptions], 4021h; CreateOptions
0x140020006  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002000a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002000e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140020012  mov     eax, 3
0x140020017  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002001e  mov     [rsp+0E0h+CreateDisposition], eax; CreateDisposition
0x140020022  xorps   xmm0, xmm0
0x140020025  mov     [rsp+0E0h+ShareAccess], eax; ShareAccess
0x140020029  mov     edx, 100001h; DesiredAccess
0x14002002e  mov     [rsp+0E0h+FileAttributes], esi; FileAttributes
0x140020032  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x14002003b  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14002003f  mov     [rbp+57h+ObjectAttributes.Attributes], 0C0h
0x140020046  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002004b  call    cs:__imp_ZwCreateFile
0x140020051  mov     edi, eax
0x140020053  test    rbx, rbx
0x140020056  jz      short loc_14002005C
0x140020058  mov     [rbx], r12w
0x14002005c  test    eax, eax
0x14002005e  js      short loc_140020077
0x140020060  test    rbx, rbx
0x140020063  jz      short loc_140020077
0x140020065  mov     rcx, [rbp+57h+FileHandle]
0x140020069  lea     rdx, [rbx+2]
0x14002006d  mov     r8d, esi
0x140020070  call    BiCreateDirectoryPath
0x140020075  mov     edi, eax
0x140020077  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14002007b  test    rcx, rcx
0x14002007e  jz      short loc_140020086
0x140020080  call    cs:__imp_ZwClose
0x140020086  mov     eax, edi
0x140020088  add     rsp, 0B8h
0x14002008f  pop     r14
0x140020091  pop     r12
0x140020093  pop     rdi
0x140020094  pop     rsi
0x140020095  pop     rbx
0x140020096  pop     rbp
0x140020097  retn
```
