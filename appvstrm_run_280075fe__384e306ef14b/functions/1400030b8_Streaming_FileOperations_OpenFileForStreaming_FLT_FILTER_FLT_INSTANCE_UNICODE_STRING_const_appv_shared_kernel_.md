# Streaming::FileOperations::OpenFileForStreaming(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)

- ea: `0x1400030b8`
- end: `0x140003152`
- name: `?OpenFileForStreaming@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEBU_UNICODE_STRING@@AEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z`
- size: `154`
- prototype: `__int64 __fastcall(int, int, int, int, PHANDLE FileHandle)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140007c24`
- `0x140008dc4`
- `0x14000f244`
- `0x140011f30`

## import_xrefs

- `FLTMGR!FltCreateFileEx` at `0x14000313d`
- `FLTMGR!FltCreateFileEx` at `0x14000313d`

## pseudocode

```c
NTSTATUS __fastcall Streaming::FileOperations::OpenFileForStreaming(
        struct _FLT_FILTER *a1,
        struct _FLT_INSTANCE *a2,
        struct _UNICODE_STRING *a3,
        PFILE_OBJECT *a4,
        PHANDLE FileHandle)
{
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-38h] BYREF

  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a3;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return FltCreateFileEx(
           a1,
           a2,
           FileHandle,
           a4,
           0x100181u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0,
           7u,
           1u,
           0x200960u,
           0,
           0,
           0x800u);
}

```

## disassembly

```asm
0x1400030b8  mov     r11, rsp
0x1400030bb  sub     rsp, 0C8h
0x1400030c2  mov     [rsp+0C8h+Flags], 800h; Flags
0x1400030ca  xor     eax, eax
0x1400030cc  mov     [rsp+0C8h+EaLength], eax; EaLength
0x1400030d0  xorps   xmm0, xmm0
0x1400030d3  mov     [r11-68h], rax
0x1400030d7  mov     [rsp+0C8h+CreateOptions], 200960h; CreateOptions
0x1400030df  mov     [rsp+0C8h+CreateDisposition], 1; CreateDisposition
0x1400030e7  mov     [rsp+0C8h+ShareAccess], 7; ShareAccess
0x1400030ef  mov     [rsp+0C8h+FileAttributes], eax; FileAttributes
0x1400030f3  mov     [rsp+0C8h+AllocationSize], rax; AllocationSize
0x1400030f8  mov     [r11-30h], rax
0x1400030fc  lea     rax, [r11-48h]
0x140003100  mov     [rsp+0C8h+IoStatusBlock], rax; IoStatusBlock
0x140003105  lea     rax, [r11-38h]
0x140003109  mov     [r11-28h], r8
0x14000310d  mov     r8, [rsp+0C8h+FileHandle]; FileHandle
0x140003115  mov     [rsp+0C8h+ObjectAttributes], rax; ObjectAttributes
0x14000311a  mov     [rsp+0C8h+DesiredAccess], 100181h; DesiredAccess
0x140003122  movups  xmmword ptr [r11-48h], xmm0
0x140003127  mov     qword ptr [r11-38h], 30h ; '0'
0x14000312f  mov     qword ptr [r11-20h], 240h
0x140003137  movdqu  xmmword ptr [r11-18h], xmm0
0x14000313d  call    cs:__imp_FltCreateFileEx
0x140003144  nop     dword ptr [rax+rax+00h]
0x140003149  add     rsp, 0C8h
0x140003150  retn
```
