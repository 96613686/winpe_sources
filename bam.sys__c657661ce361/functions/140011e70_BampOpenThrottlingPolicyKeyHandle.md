# BampOpenThrottlingPolicyKeyHandle

- ea: `0x140011e70`
- end: `0x140011ed9`
- name: `BampOpenThrottlingPolicyKeyHandle`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000baac`
- `0x140011c68`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140011eb7`
- `ntoskrnl!ZwOpenKey` at `0x140011eb7`

## pseudocode

```c
__int64 BampOpenThrottlingPolicyKeyHandle()
{
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp+10h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&BampPolicyKeyName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  return 0;
}

```

## disassembly

```asm
0x140011e70  mov     [rsp-8+arg_8], rbx
0x140011e75  push    rbp
0x140011e76  mov     rbp, rsp
0x140011e79  sub     rsp, 50h
0x140011e7d  xor     eax, eax
0x140011e7f  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140011e87  mov     [rbp+KeyHandle], rax
0x140011e8b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140011e8f  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140011e93  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140011e97  lea     rax, BampPolicyKeyName
0x140011e9e  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140011ea6  xorps   xmm0, xmm0
0x140011ea9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140011ead  xor     ebx, ebx
0x140011eaf  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140011eb4  lea     edx, [rbx+1]; DesiredAccess
0x140011eb7  call    cs:__imp_ZwOpenKey
0x140011ebe  nop     dword ptr [rax+rax+00h]
0x140011ec3  test    eax, eax
0x140011ec5  cmovns  rbx, [rbp+KeyHandle]
0x140011eca  mov     rax, rbx
0x140011ecd  mov     rbx, [rsp+50h+arg_8]
0x140011ed2  add     rsp, 50h
0x140011ed6  pop     rbp
0x140011ed7  retn
```
