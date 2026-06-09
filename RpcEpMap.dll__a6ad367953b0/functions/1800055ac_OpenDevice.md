# OpenDevice

- ea: `0x1800055ac`
- end: `0x18000562c`
- name: `OpenDevice`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005428`

## callees

- `0x1800055ac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000561c`
- `ntdll!RtlNtStatusToDosError` at `0x18000561c`
- `ntdll!NtOpenFile` at `0x180005606`
- `ntdll!NtOpenFile` at `0x180005606`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005624`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005624`

## pseudocode

```c
void *__fastcall OpenDevice(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  ULONG v3; // eax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
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
    v3 = RtlNtStatusToDosError(v1);
    SetLastError(v3);
  }
  return FileHandle;
}

```

## disassembly

```asm
0x1800055ac  push    rbp
0x1800055ae  mov     rbp, rsp
0x1800055b1  sub     rsp, 70h
0x1800055b5  xorps   xmm0, xmm0
0x1800055b8  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x1800055bc  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800055c0  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x1800055c8  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800055cc  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800055d4  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800055d8  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800055e0  mov     edx, 12019Fh; DesiredAccess
0x1800055e5  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800055ed  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800055f2  mov     [rbp+FileHandle], 0
0x1800055fa  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800055fe  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x180005606  call    cs:__imp_NtOpenFile
0x18000560c  test    eax, eax
0x18000560e  jnz     short loc_18000561A
0x180005610  mov     rax, [rbp+FileHandle]
0x180005614  add     rsp, 70h
0x180005618  pop     rbp
0x180005619  retn
0x18000561a  mov     ecx, eax; Status
0x18000561c  call    cs:__imp_RtlNtStatusToDosError
0x180005622  mov     ecx, eax; dwErrCode
0x180005624  call    cs:__imp_SetLastError
0x18000562a  jmp     short loc_180005610
```
