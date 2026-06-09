# OpenDevice

- ea: `0x180055cd0`
- end: `0x180055d4e`
- name: `OpenDevice`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180055a40`

## callees

- `0x180055cd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055d3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055d3e`
- `ntdll!NtOpenFile` at `0x180055d2a`
- `ntdll!NtOpenFile` at `0x180055d2a`
- `ntdll!RtlNtStatusToDosError` at `0x180055d36`
- `ntdll!RtlNtStatusToDosError` at `0x180055d36`

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
0x180055cd0  push    rbp
0x180055cd2  mov     rbp, rsp
0x180055cd5  sub     rsp, 70h
0x180055cd9  xorps   xmm0, xmm0
0x180055cdc  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x180055ce0  lea     rcx, [rbp+FileHandle]; FileHandle
0x180055ce4  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x180055cec  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180055cf0  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180055cf8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180055cfc  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180055d04  mov     edx, 12019Fh; DesiredAccess
0x180055d09  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180055d11  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180055d16  mov     [rbp+FileHandle], 0
0x180055d1e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180055d22  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x180055d2a  call    cs:__imp_NtOpenFile
0x180055d30  test    eax, eax
0x180055d32  jz      short loc_180055D44
0x180055d34  mov     ecx, eax; Status
0x180055d36  call    cs:__imp_RtlNtStatusToDosError
0x180055d3c  mov     ecx, eax; dwErrCode
0x180055d3e  call    cs:__imp_SetLastError
0x180055d44  mov     rax, [rbp+FileHandle]
0x180055d48  add     rsp, 70h
0x180055d4c  pop     rbp
0x180055d4d  retn
```
