# OpenDevice

- ea: `0x180088a74`
- end: `0x180088af2`
- name: `OpenDevice`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800887e4`

## callees

- `0x180088a74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180088ae2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180088ae2`
- `ntdll!RtlNtStatusToDosError` at `0x180088ada`
- `ntdll!RtlNtStatusToDosError` at `0x180088ada`
- `ntdll!NtOpenFile` at `0x180088ace`
- `ntdll!NtOpenFile` at `0x180088ace`

## pseudocode

```c
void *__fastcall OpenDevice(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  DWORD v2; // eax
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
0x180088a74  push    rbp
0x180088a76  mov     rbp, rsp
0x180088a79  sub     rsp, 70h
0x180088a7d  xorps   xmm0, xmm0
0x180088a80  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x180088a84  lea     rcx, [rbp+FileHandle]; FileHandle
0x180088a88  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x180088a90  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180088a94  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180088a9c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180088aa0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180088aa8  mov     edx, 12019Fh; DesiredAccess
0x180088aad  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180088ab5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180088aba  mov     [rbp+FileHandle], 0
0x180088ac2  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180088ac6  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x180088ace  call    cs:__imp_NtOpenFile
0x180088ad4  test    eax, eax
0x180088ad6  jz      short loc_180088AE8
0x180088ad8  mov     ecx, eax; Status
0x180088ada  call    cs:__imp_RtlNtStatusToDosError
0x180088ae0  mov     ecx, eax; dwErrCode
0x180088ae2  call    cs:__imp_SetLastError
0x180088ae8  mov     rax, [rbp+FileHandle]
0x180088aec  add     rsp, 70h
0x180088af0  pop     rbp
0x180088af1  retn
```
