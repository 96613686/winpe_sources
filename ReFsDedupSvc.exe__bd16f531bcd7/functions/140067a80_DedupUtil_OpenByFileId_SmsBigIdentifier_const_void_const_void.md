# DedupUtil::OpenByFileId(SmsBigIdentifier const &,void * const,void * *)

- ea: `0x140067a80`
- end: `0x140067b07`
- name: `?OpenByFileId@DedupUtil@@YAKAEBTSmsBigIdentifier@@QEAXPEAPEAX@Z`
- size: `135`
- prototype: `unsigned int(DedupUtil *__hidden this, const union SmsBigIdentifier *, void *const, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007893c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140067ae3`
- `ntdll!NtOpenFile` at `0x140067ae3`
- `ntdll!RtlNtStatusToDosError` at `0x140067af1`
- `ntdll!RtlNtStatusToDosError` at `0x140067af1`

## pseudocode

```c
ULONG __fastcall DedupUtil::OpenByFileId(DedupUtil *this, const union SmsBigIdentifier *a2, void **a3, void **a4)
{
  NTSTATUS v4; // eax
  _QWORD v6[2]; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  v6[1] = this;
  ObjectAttributes.RootDirectory = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v6[0] = 1048592;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenFile(a3, 0x181u, &ObjectAttributes, &IoStatusBlock, 7u, 0x6848u);
  return RtlNtStatusToDosError(v4);
}

```

## disassembly

```asm
0x140067a80  push    rbp
0x140067a82  mov     rbp, rsp
0x140067a85  sub     rsp, 80h
0x140067a8c  mov     [rbp+var_48], rcx
0x140067a90  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140067a94  mov     rax, r8
0x140067a97  mov     [rbp+ObjectAttributes.RootDirectory], rdx
0x140067a9b  xorps   xmm0, xmm0
0x140067a9e  mov     [rsp+80h+OpenOptions], 6848h; OpenOptions
0x140067aa6  lea     rcx, [rbp+var_50]
0x140067aaa  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140067ab2  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140067ab6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140067aba  mov     rcx, rax; FileHandle
0x140067abd  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140067ac5  mov     edx, 181h; DesiredAccess
0x140067aca  mov     [rbp+var_50], 100010h
0x140067ad2  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140067ad6  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x140067ade  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140067ae3  call    cs:__imp_NtOpenFile
0x140067aea  nop     dword ptr [rax+rax+00h]
0x140067aef  mov     ecx, eax; Status
0x140067af1  call    cs:__imp_RtlNtStatusToDosError
0x140067af8  nop     dword ptr [rax+rax+00h]
0x140067afd  add     rsp, 80h
0x140067b04  pop     rbp
0x140067b05  retn
```
