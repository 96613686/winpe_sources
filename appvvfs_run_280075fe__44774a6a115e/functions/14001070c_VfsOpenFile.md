# VfsOpenFile

- ea: `0x14001070c`
- end: `0x1400107c1`
- name: `VfsOpenFile`
- size: `181`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, ULONG, ULONG, PHANDLE FileHandle, PFILE_OBJECT *FileObject)`
- caller_count: `12`
- callee_count: `0`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400037ac`
- `0x140003978`
- `0x140006c10`
- `0x14000783c`
- `0x14000be3c`
- `0x14000c40c`
- `0x14000cd04`
- `0x14000e944`
- `0x14000eb14`
- `0x14000f7ac`
- `0x140010654`
- `0x1400107c8`

## import_xrefs

- `FLTMGR!FltCreateFileEx2` at `0x1400107ac`
- `FLTMGR!FltCreateFileEx2` at `0x1400107ac`

## pseudocode

```c
NTSTATUS __fastcall VfsOpenFile(
        PFLT_INSTANCE Instance,
        void *a2,
        struct _UNICODE_STRING *a3,
        ACCESS_MASK DesiredAccess,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        PHANDLE FileHandle,
        PFILE_OBJECT *FileObject)
{
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-38h] BYREF

  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.ObjectName = a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return FltCreateFileEx2(
           VfsData,
           Instance,
           FileHandle,
           FileObject,
           DesiredAccess,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0,
           7u,
           CreateDisposition,
           CreateOptions,
           0,
           0,
           0x900u,
           0);
}

```

## disassembly

```asm
0x14001070c  mov     r11, rsp
0x14001070f  sub     rsp, 0C8h
0x140010716  mov     eax, [rsp+0C8h+arg_28]
0x14001071d  xor     r10d, r10d
0x140010720  mov     [r11-50h], r10
0x140010724  xorps   xmm0, xmm0
0x140010727  mov     [rsp+0C8h+Flags], 900h; Flags
0x14001072f  mov     [r11-60h], r10d
0x140010733  mov     [r11-68h], r10
0x140010737  mov     [rsp+0C8h+CreateOptions], eax; CreateOptions
0x14001073b  mov     eax, [rsp+0C8h+arg_20]
0x140010742  mov     [rsp+0C8h+CreateDisposition], eax; CreateDisposition
0x140010746  lea     rax, [r11-48h]
0x14001074a  mov     [rsp+0C8h+ShareAccess], 7; ShareAccess
0x140010752  mov     [rsp+0C8h+FileAttributes], r10d; FileAttributes
0x140010757  mov     [rsp+0C8h+AllocationSize], r10; AllocationSize
0x14001075c  mov     [rsp+0C8h+IoStatusBlock], rax; IoStatusBlock
0x140010761  lea     rax, [r11-38h]
0x140010765  mov     [rsp+0C8h+ObjectAttributes], rax; ObjectAttributes
0x14001076a  mov     [r11-30h], rdx
0x14001076e  mov     rdx, rcx; Instance
0x140010771  mov     rcx, cs:VfsData; Filter
0x140010778  mov     [rsp+0C8h+DesiredAccess], r9d; DesiredAccess
0x14001077d  mov     r9, [rsp+0C8h+FileObject]; FileObject
0x140010785  mov     [r11-28h], r8
0x140010789  mov     r8, [rsp+0C8h+FileHandle]; FileHandle
0x140010791  mov     qword ptr [r11-38h], 30h ; '0'
0x140010799  mov     qword ptr [r11-20h], 240h
0x1400107a1  movups  xmmword ptr [r11-48h], xmm0
0x1400107a6  movdqu  xmmword ptr [r11-18h], xmm0
0x1400107ac  call    cs:__imp_FltCreateFileEx2
0x1400107b3  nop     dword ptr [rax+rax+00h]
0x1400107b8  add     rsp, 0C8h
0x1400107bf  retn
```
