# SiOpenDevice

- ea: `0x14001d514`
- end: `0x14001d5b4`
- name: `SiOpenDevice`
- size: `160`
- prototype: `NTSTATUS __fastcall(PCWSTR SourceString, PHANDLE FileHandle)`
- caller_count: `5`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001ce84`
- `0x14001cf6c`
- `0x14001d47c`
- `0x14001d66c`
- `0x14001d998`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14001d59d`
- `ntdll!NtOpenFile` at `0x14001d59d`
- `ntdll!RtlInitUnicodeString` at `0x14001d54d`
- `ntdll!RtlInitUnicodeString` at `0x14001d54d`

## pseudocode

```c
NTSTATUS __fastcall SiOpenDevice(PCWSTR SourceString, PHANDLE FileHandle)
{
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  *FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  return NtOpenFile(FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
}

```

## disassembly

```asm
0x14001d514  mov     [rsp-8+arg_0], rbx
0x14001d519  push    rbp
0x14001d51a  mov     rbp, rsp
0x14001d51d  sub     rsp, 80h
0x14001d524  xorps   xmm0, xmm0
0x14001d527  xor     eax, eax
0x14001d529  mov     [rdx], rax
0x14001d52c  mov     rbx, rdx
0x14001d52f  mov     rdx, rcx; SourceString
0x14001d532  xorps   xmm1, xmm1
0x14001d535  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001d539  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001d53d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001d541  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001d545  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14001d549  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14001d54d  call    cs:__imp_RtlInitUnicodeString
0x14001d553  xorps   xmm0, xmm0
0x14001d556  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x14001d55e  lea     rax, [rbp+DestinationString]
0x14001d562  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001d569  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14001d56d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001d571  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001d575  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14001d57d  mov     edx, 80100000h; DesiredAccess
0x14001d582  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14001d589  mov     rcx, rbx; FileHandle
0x14001d58c  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x14001d594  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001d599  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14001d59d  call    cs:__imp_NtOpenFile
0x14001d5a3  mov     rbx, [rsp+80h+arg_0]
0x14001d5ab  add     rsp, 80h
0x14001d5b2  pop     rbp
0x14001d5b3  retn
```
