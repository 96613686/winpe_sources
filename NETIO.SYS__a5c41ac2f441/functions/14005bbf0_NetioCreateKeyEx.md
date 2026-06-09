# NetioCreateKeyEx

- ea: `0x14005bbf0`
- end: `0x14005bc90`
- name: `NetioCreateKeyEx`
- size: `160`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *, void *, ACCESS_MASK DesiredAccess, ULONG CreateOptions)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14005bbc0`
- `0x14005bcc0`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x14005bc77`
- `ntoskrnl!ZwCreateKey` at `0x14005bc77`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bc26`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bc26`

## pseudocode

```c
NTSTATUS __fastcall NetioCreateKeyEx(
        PHANDLE KeyHandle,
        void *a2,
        const WCHAR *a3,
        void *a4,
        ACCESS_MASK DesiredAccess,
        ULONG CreateOptions)
{
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, a3);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityQualityOfService = 0;
  *KeyHandle = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 704;
  ObjectAttributes.SecurityDescriptor = a4;
  return ZwCreateKey(KeyHandle, DesiredAccess, &ObjectAttributes, 0, 0, CreateOptions, 0);
}

```

## disassembly

```asm
0x14005bbf0  push    rbp
0x14005bbf2  push    rbx
0x14005bbf3  push    rsi
0x14005bbf4  push    rdi
0x14005bbf5  lea     rbp, [rsp-2Fh]
0x14005bbfa  sub     rsp, 88h
0x14005bc01  xorps   xmm0, xmm0
0x14005bc04  mov     rbx, rdx
0x14005bc07  mov     rsi, rcx
0x14005bc0a  xor     eax, eax
0x14005bc0c  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x14005bc10  mov     rdx, r8; SourceString
0x14005bc13  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14005bc17  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x14005bc1b  mov     rdi, r9
0x14005bc1e  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x14005bc22  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x14005bc26  call    cs:__imp_RtlInitUnicodeString
0x14005bc2d  nop     dword ptr [rax+rax+00h]
0x14005bc32  mov     edx, [rbp+47h+DesiredAccess]; DesiredAccess
0x14005bc35  lea     rax, [rbp+47h+DestinationString]
0x14005bc39  xor     ecx, ecx
0x14005bc3b  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x14005bc3f  mov     eax, [rbp+47h+arg_28]
0x14005bc42  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14005bc46  mov     [rsp+0A0h+Disposition], rcx; Disposition
0x14005bc4b  xor     r9d, r9d; TitleIndex
0x14005bc4e  mov     [rsp+0A0h+CreateOptions], eax; CreateOptions
0x14005bc52  mov     [rsp+0A0h+Class], rcx; Class
0x14005bc57  mov     [rbp+47h+ObjectAttributes.SecurityQualityOfService], rcx
0x14005bc5b  mov     [rsi], rcx
0x14005bc5e  mov     rcx, rsi; KeyHandle
0x14005bc61  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14005bc68  mov     [rbp+47h+ObjectAttributes.RootDirectory], rbx
0x14005bc6c  mov     [rbp+47h+ObjectAttributes.Attributes], 2C0h
0x14005bc73  mov     [rbp+47h+ObjectAttributes.SecurityDescriptor], rdi
0x14005bc77  call    cs:__imp_ZwCreateKey
0x14005bc7e  nop     dword ptr [rax+rax+00h]
0x14005bc83  add     rsp, 88h
0x14005bc8a  pop     rdi
0x14005bc8b  pop     rsi
0x14005bc8c  pop     rbx
0x14005bc8d  pop     rbp
0x14005bc8e  retn
```
