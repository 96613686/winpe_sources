# BiCreateHive

- ea: `0x14001e648`
- end: `0x14001e728`
- name: `BiCreateHive`
- size: `224`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001a964`

## callees

- `0x14001e648`
- `0x14002166c`
- `0x140021888`

## import_xrefs

- `ntdll!ZwClose` at `0x14001e70b`
- `ntdll!ZwClose` at `0x14001e70b`
- `ntdll!ZwCreateFile` at `0x14001e6ca`
- `ntdll!ZwCreateFile` at `0x14001e6ca`
- `ntdll!ZwSaveKey` at `0x14001e6f1`
- `ntdll!ZwSaveKey` at `0x14001e6f1`

## pseudocode

```c
__int64 __fastcall BiCreateHive(HANDLE KeyHandle, struct _UNICODE_STRING *a2)
{
  NTSTATUS v3; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp+6Fh] BYREF
  __int64 v8; // [rsp+C8h] [rbp+77h] BYREF

  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  v8 = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwCreateFile(&FileHandle, 0x1F01FFu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 2u, 0, 0, 0);
  if ( v3 >= 0 )
  {
    v3 = BiAcquirePrivilege(0x11u, (__int64)&v8);
    if ( v3 >= 0 )
    {
      v3 = ZwSaveKey(KeyHandle, FileHandle);
      BiReleasePrivilege(&v8);
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001e648  mov     r11, rsp
0x14001e64b  mov     [r11+8], rbx
0x14001e64f  mov     [r11+20h], rdi
0x14001e653  push    rbp
0x14001e654  lea     rbp, [r11-5Fh]
0x14001e658  sub     rsp, 0A0h
0x14001e65f  xor     eax, eax
0x14001e661  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x14001e665  mov     [rsp+0A0h+EaLength], eax; EaLength
0x14001e669  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001e66d  mov     [r11-60h], rax
0x14001e671  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001e675  mov     [rsp+0A0h+CreateOptions], eax; CreateOptions
0x14001e679  xorps   xmm0, xmm0
0x14001e67c  mov     [rsp+0A0h+CreateDisposition], 2; CreateDisposition
0x14001e684  mov     rdi, rcx
0x14001e687  mov     [rsp+0A0h+ShareAccess], 1; ShareAccess
0x14001e68f  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001e693  mov     [rsp+0A0h+FileAttributes], 80h; FileAttributes
0x14001e69b  mov     edx, 1F01FFh; DesiredAccess
0x14001e6a0  mov     [rsp+0A0h+AllocationSize], rax; AllocationSize
0x14001e6a5  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001e6ad  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0C0h
0x14001e6b5  mov     [rbp+57h+arg_10], rax
0x14001e6b9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14001e6bd  mov     [rbp+57h+FileHandle], rax
0x14001e6c1  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14001e6c5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001e6ca  call    cs:__imp_ZwCreateFile
0x14001e6d0  mov     ebx, eax
0x14001e6d2  test    eax, eax
0x14001e6d4  js      short loc_14001E702
0x14001e6d6  lea     rdx, [rbp+57h+arg_10]
0x14001e6da  mov     ecx, 11h
0x14001e6df  call    BiAcquirePrivilege
0x14001e6e4  mov     ebx, eax
0x14001e6e6  test    eax, eax
0x14001e6e8  js      short loc_14001E702
0x14001e6ea  mov     rdx, [rbp+57h+FileHandle]; FileHandle
0x14001e6ee  mov     rcx, rdi; KeyHandle
0x14001e6f1  call    cs:__imp_ZwSaveKey
0x14001e6f7  lea     rcx, [rbp+57h+arg_10]
0x14001e6fb  mov     ebx, eax
0x14001e6fd  call    BiReleasePrivilege
0x14001e702  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14001e706  test    rcx, rcx
0x14001e709  jz      short loc_14001E711
0x14001e70b  call    cs:__imp_ZwClose
0x14001e711  lea     r11, [rsp+0A0h+var_s0]
0x14001e719  mov     eax, ebx
0x14001e71b  mov     rbx, [r11+10h]
0x14001e71f  mov     rdi, [r11+28h]
0x14001e723  mov     rsp, r11
0x14001e726  pop     rbp
0x14001e727  retn
```
