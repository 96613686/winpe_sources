# OpenDevice

- ea: `0x18004490c`
- end: `0x18004498a`
- name: `OpenDevice`
- size: `126`
- prototype: `void *__fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004467c`

## callees

- `0x18004490c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004497a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004497a`
- `ntdll!NtOpenFile` at `0x180044966`
- `ntdll!NtOpenFile` at `0x180044966`
- `ntdll!RtlNtStatusToDosError` at `0x180044972`
- `ntdll!RtlNtStatusToDosError` at `0x180044972`

## pseudocode

```c
void *__fastcall OpenDevice(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  ULONG v2; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  v1 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v1 )
  {
    v2 = RtlNtStatusToDosError(v1);
    SetLastError(v2);
  }
  return FileHandle;
}

```

## disassembly

```asm
0x18004490c  push    rbp
0x18004490e  mov     rbp, rsp
0x180044911  sub     rsp, 70h
0x180044915  xorps   xmm0, xmm0
0x180044918  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18004491c  lea     rcx, [rbp+FileHandle]; FileHandle
0x180044920  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x180044928  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18004492c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180044934  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180044938  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180044940  mov     edx, 12019Fh; DesiredAccess
0x180044945  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004494d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180044952  mov     [rbp+FileHandle], 0
0x18004495a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18004495e  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x180044966  call    cs:__imp_NtOpenFile
0x18004496c  test    eax, eax
0x18004496e  jz      short loc_180044980
0x180044970  mov     ecx, eax; Status
0x180044972  call    cs:__imp_RtlNtStatusToDosError
0x180044978  mov     ecx, eax; dwErrCode
0x18004497a  call    cs:__imp_SetLastError
0x180044980  mov     rax, [rbp+FileHandle]
0x180044984  add     rsp, 70h
0x180044988  pop     rbp
0x180044989  retn
```
