# TelemetryData_pDeleteDumpFile

- ea: `0x140080c80`
- end: `0x140080d8e`
- name: `TelemetryData_pDeleteDumpFile`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400809b8`

## callees

- `0x140080c80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140080cc1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080cc1`
- `ntoskrnl!IoCreateFile` at `0x140080d57`
- `ntoskrnl!IoCreateFile` at `0x140080d57`
- `ntoskrnl!ZwClose` at `0x140080d6b`
- `ntoskrnl!ZwClose` at `0x140080d6b`

## pseudocode

```c
NTSTATUS __fastcall TelemetryData_pDeleteDumpFile(__int64 a1)
{
  _WORD *v1; // rbx
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+67h] BYREF

  FileHandle = 0;
  v1 = (_WORD *)(a1 + 736);
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, (PCWSTR)(a1 + 736));
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = IoCreateFile(
             &FileHandle,
             0x110000u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0x80u,
             7u,
             1u,
             0x1000u,
             0,
             0,
             CreateFileTypeNone,
             0,
             0x100u);
  if ( result >= 0 )
  {
    ZwClose(FileHandle);
    result = 0;
    *v1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140080c80  mov     [rsp-8+arg_8], rbx
0x140080c85  push    rbp
0x140080c86  lea     rbp, [rsp-57h]
0x140080c8b  sub     rsp, 0C0h
0x140080c92  xorps   xmm0, xmm0
0x140080c95  mov     [rbp+57h+FileHandle], 0
0x140080c9d  lea     rbx, [rcx+2E0h]
0x140080ca4  xor     eax, eax
0x140080ca6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140080caa  mov     rdx, rbx; SourceString
0x140080cad  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140080cb1  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140080cb5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140080cb9  movups  xmmword ptr [rbp+57h+IoStatusBlock.___u0], xmm0
0x140080cbd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140080cc1  call    cs:__imp_RtlInitUnicodeString
0x140080cc8  nop     dword ptr [rax+rax+00h]
0x140080ccd  mov     [rsp+0C0h+Options], 100h; Options
0x140080cd5  lea     rax, [rbp+57h+DestinationString]
0x140080cd9  mov     [rsp+0C0h+InternalParameters], 0; InternalParameters
0x140080ce2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140080ce6  mov     [rsp+0C0h+CreateFileType], 0; CreateFileType
0x140080cee  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140080cf2  mov     [rsp+0C0h+EaLength], 0; EaLength
0x140080cfa  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140080cfe  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x140080d07  xorps   xmm0, xmm0
0x140080d0a  mov     [rsp+0C0h+CreateOptions], 1000h; CreateOptions
0x140080d12  mov     edx, 110000h; DesiredAccess
0x140080d17  mov     [rsp+0C0h+Disposition], 1; Disposition
0x140080d1f  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x140080d27  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x140080d2f  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x140080d38  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140080d3f  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140080d47  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140080d4e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140080d52  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140080d57  call    cs:__imp_IoCreateFile
0x140080d5e  nop     dword ptr [rax+rax+00h]
0x140080d63  test    eax, eax
0x140080d65  js      short loc_140080D7C
0x140080d67  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140080d6b  call    cs:__imp_ZwClose
0x140080d72  nop     dword ptr [rax+rax+00h]
0x140080d77  xor     eax, eax
0x140080d79  mov     [rbx], ax
0x140080d7c  mov     rbx, [rsp+0C0h+arg_8]
0x140080d84  add     rsp, 0C0h
0x140080d8b  pop     rbp
0x140080d8c  retn
```
