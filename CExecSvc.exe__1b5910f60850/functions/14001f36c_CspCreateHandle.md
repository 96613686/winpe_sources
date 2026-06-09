# CspCreateHandle

- ea: `0x14001f36c`
- end: `0x14001f403`
- name: `CspCreateHandle`
- size: `151`
- prototype: `__int64 __usercall@<rax>(PHANDLE FileHandle@<rcx>, char, ULONG)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001b9d8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001f3a6`
- `ntdll!RtlInitUnicodeString` at `0x14001f3a6`
- `ntdll!NtOpenFile` at `0x14001f3f1`
- `ntdll!NtOpenFile` at `0x14001f3f1`

## pseudocode

```c
NTSTATUS __fastcall CspCreateHandle(
        PHANDLE FileHandle,
        const WCHAR *a2,
        ACCESS_MASK a3,
        void *a4,
        char a5,
        ULONG OpenOptions)
{
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF

  IoStatusBlock = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a4;
  ObjectAttributes.Attributes = a5 != 0 ? 66 : 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtOpenFile(FileHandle, a3, &ObjectAttributes, &IoStatusBlock, 7u, OpenOptions);
}

```

## disassembly

```asm
0x14001f36c  push    rbp
0x14001f36e  push    rbx
0x14001f36f  push    rsi
0x14001f370  push    rdi
0x14001f371  lea     rbp, [rsp-2Fh]
0x14001f376  sub     rsp, 88h
0x14001f37d  xorps   xmm0, xmm0
0x14001f380  mov     rdi, rcx
0x14001f383  xorps   xmm1, xmm1
0x14001f386  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14001f38a  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x14001f38e  xor     eax, eax
0x14001f390  mov     rbx, r9
0x14001f393  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x14001f397  mov     esi, r8d
0x14001f39a  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x14001f39e  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x14001f3a2  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x14001f3a6  call    cs:__imp_RtlInitUnicodeString
0x14001f3ac  neg     [rbp+47h+arg_20]
0x14001f3af  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x14001f3b3  xorps   xmm0, xmm0
0x14001f3b6  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14001f3bd  sbb     eax, eax
0x14001f3bf  mov     [rbp+47h+ObjectAttributes.RootDirectory], rbx
0x14001f3c3  and     eax, 2
0x14001f3c6  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14001f3ca  add     eax, 40h ; '@'
0x14001f3cd  mov     edx, esi; DesiredAccess
0x14001f3cf  mov     [rbp+47h+ObjectAttributes.Attributes], eax
0x14001f3d2  mov     rcx, rdi; FileHandle
0x14001f3d5  lea     rax, [rbp+47h+DestinationString]
0x14001f3d9  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x14001f3dd  mov     eax, [rbp+47h+arg_28]
0x14001f3e0  mov     [rsp+0A0h+OpenOptions], eax; OpenOptions
0x14001f3e4  mov     [rsp+0A0h+ShareAccess], 7; ShareAccess
0x14001f3ec  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f3f1  call    cs:__imp_NtOpenFile
0x14001f3f7  add     rsp, 88h
0x14001f3fe  pop     rdi
0x14001f3ff  pop     rsi
0x14001f400  pop     rbx
0x14001f401  pop     rbp
0x14001f402  retn
```
