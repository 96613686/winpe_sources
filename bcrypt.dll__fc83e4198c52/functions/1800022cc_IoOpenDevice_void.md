# _IoOpenDevice(void)

- ea: `0x1800022cc`
- end: `0x180002369`
- name: `?_IoOpenDevice@@YAJXZ`
- size: `157`
- prototype: `NTSTATUS(void)`
- caller_count: `3`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002040`
- `0x1800023f0`
- `0x1800030a0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180002353`
- `ntdll!NtOpenFile` at `0x180002353`
- `ntdll!RtlInitUnicodeString` at `0x1800022fd`
- `ntdll!RtlInitUnicodeString` at `0x1800022fd`

## pseudocode

```c
NTSTATUS _IoOpenDevice(void)
{
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\KsecDD");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtOpenFile(&g_hIoDevice, 0x100003u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
}

```

## disassembly

```asm
0x1800022cc  push    rbp
0x1800022ce  mov     rbp, rsp
0x1800022d1  sub     rsp, 80h
0x1800022d8  xorps   xmm1, xmm1
0x1800022db  lea     rdx, SourceString; "\\Device\\KsecDD"
0x1800022e2  xorps   xmm0, xmm0
0x1800022e5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800022e9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800022ed  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1800022f1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1800022f5  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1800022f9  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800022fd  call    cs:__imp_RtlInitUnicodeString
0x180002304  nop     dword ptr [rax+rax+00h]
0x180002309  lea     rax, [rbp+DestinationString]
0x18000230d  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x180002315  xorps   xmm0, xmm0
0x180002318  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000231c  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180002320  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180002327  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000232b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180002333  mov     edx, 100003h; DesiredAccess
0x180002338  mov     [rbp+ObjectAttributes.Attributes], 0
0x18000233f  lea     rcx, ?g_hIoDevice@@3REAXEA; FileHandle
0x180002346  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x18000234e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180002353  call    cs:__imp_NtOpenFile
0x18000235a  nop     dword ptr [rax+rax+00h]
0x18000235f  add     rsp, 80h
0x180002366  pop     rbp
0x180002367  retn
```
