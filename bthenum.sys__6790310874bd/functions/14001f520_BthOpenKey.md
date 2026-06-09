# BthOpenKey

- ea: `0x14001f520`
- end: `0x14001f591`
- name: `BthOpenKey`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001cf90`
- `0x14001df2c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001f53b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f53b`
- `ntoskrnl!ZwOpenKey` at `0x14001f579`
- `ntoskrnl!ZwOpenKey` at `0x14001f579`

## pseudocode

```c
NTSTATUS __fastcall BthOpenKey(__int64 a1, const WCHAR *a2, void **a3)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenKey(a3, 0xF003Fu, &ObjectAttributes);
}

```

## disassembly

```asm
0x14001f520  mov     [rsp-8+arg_0], rbx
0x14001f525  push    rbp
0x14001f526  mov     rbp, rsp
0x14001f529  sub     rsp, 60h
0x14001f52d  xorps   xmm0, xmm0
0x14001f530  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001f534  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001f538  mov     rbx, r8
0x14001f53b  call    cs:__imp_RtlInitUnicodeString
0x14001f542  nop     dword ptr [rax+rax+00h]
0x14001f547  xor     eax, eax
0x14001f549  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001f551  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14001f555  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001f559  lea     rax, [rbp+DestinationString]
0x14001f55d  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14001f565  xorps   xmm0, xmm0
0x14001f568  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001f56c  mov     edx, 0F003Fh; DesiredAccess
0x14001f571  mov     rcx, rbx; KeyHandle
0x14001f574  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f579  call    cs:__imp_ZwOpenKey
0x14001f580  nop     dword ptr [rax+rax+00h]
0x14001f585  mov     rbx, [rsp+60h+arg_0]
0x14001f58a  add     rsp, 60h
0x14001f58e  pop     rbp
0x14001f58f  retn
```
