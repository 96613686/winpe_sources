# Streaming::FileOperations::CreateDirectoryInternal(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,ulong,ulong,void *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)

- ea: `0x140002864`
- end: `0x140002907`
- name: `?CreateDirectoryInternal@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KKPEAXAEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z`
- size: `163`
- prototype: `NTSTATUS __fastcall(struct _FLT_FILTER *, struct _FLT_INSTANCE *, struct _UNICODE_STRING *, ACCESS_MASK DesiredAccess, ULONG CreateDisposition, __int64, PFILE_OBJECT *FileObject, void **FileHandle)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140002910`
- `0x140007fe4`
- `0x14000abd8`

## import_xrefs

- `FLTMGR!FltCreateFileEx` at `0x1400028f2`
- `FLTMGR!FltCreateFileEx` at `0x1400028f2`

## pseudocode

```c
NTSTATUS __fastcall Streaming::FileOperations::CreateDirectoryInternal(
        struct _FLT_FILTER *a1,
        struct _FLT_INSTANCE *a2,
        struct _UNICODE_STRING *a3,
        ACCESS_MASK DesiredAccess,
        ULONG CreateDisposition,
        __int64 a6,
        PFILE_OBJECT *FileObject,
        void **FileHandle)
{
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-38h] BYREF

  ObjectAttributes.ObjectName = a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return FltCreateFileEx(
           a1,
           a2,
           FileHandle,
           FileObject,
           DesiredAccess,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0x80u,
           7u,
           CreateDisposition,
           0x4021u,
           0,
           0,
           0);
}

```

## disassembly

```asm
0x140002864  mov     r11, rsp
0x140002867  sub     rsp, 0C8h
0x14000286e  mov     eax, [rsp+0C8h+arg_20]
0x140002875  xor     r10d, r10d
0x140002878  mov     [r11-58h], r10d
0x14000287c  xorps   xmm0, xmm0
0x14000287f  mov     [r11-60h], r10d
0x140002883  mov     [r11-68h], r10
0x140002887  mov     [rsp+0C8h+CreateOptions], 4021h; CreateOptions
0x14000288f  mov     [rsp+0C8h+CreateDisposition], eax; CreateDisposition
0x140002893  lea     rax, [r11-48h]
0x140002897  mov     [rsp+0C8h+ShareAccess], 7; ShareAccess
0x14000289f  mov     [rsp+0C8h+FileAttributes], 80h; FileAttributes
0x1400028a7  mov     [rsp+0C8h+AllocationSize], r10; AllocationSize
0x1400028ac  mov     [rsp+0C8h+IoStatusBlock], rax; IoStatusBlock
0x1400028b1  lea     rax, [r11-38h]
0x1400028b5  mov     [rsp+0C8h+ObjectAttributes], rax; ObjectAttributes
0x1400028ba  mov     [rsp+0C8h+DesiredAccess], r9d; DesiredAccess
0x1400028bf  mov     r9, [rsp+0C8h+FileObject]; FileObject
0x1400028c7  mov     [r11-28h], r8
0x1400028cb  mov     r8, [rsp+0C8h+FileHandle]; FileHandle
0x1400028d3  mov     qword ptr [r11-38h], 30h ; '0'
0x1400028db  mov     qword ptr [r11-20h], 240h
0x1400028e3  movups  xmmword ptr [r11-48h], xmm0
0x1400028e8  mov     [r11-30h], r10
0x1400028ec  movdqu  xmmword ptr [r11-18h], xmm0
0x1400028f2  call    cs:__imp_FltCreateFileEx
0x1400028f9  nop     dword ptr [rax+rax+00h]
0x1400028fe  add     rsp, 0C8h
0x140002905  retn
```
