# NsipEnsureKeyExistsWithSecurityDescriptor

- ea: `0x14005f890`
- end: `0x14005f993`
- name: `NsipEnsureKeyExistsWithSecurityDescriptor`
- size: `259`
- prototype: `NTSTATUS __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14005fc08`

## callees

- `0x14005f890`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14005f96f`
- `ntoskrnl!ZwClose` at `0x14005f96f`
- `ntoskrnl!ZwCreateKey` at `0x14005f93b`
- `ntoskrnl!ZwCreateKey` at `0x14005f93b`
- `ntoskrnl!ZwSetSecurityObject` at `0x14005f95d`
- `ntoskrnl!ZwSetSecurityObject` at `0x14005f95d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f8d4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f8d4`

## pseudocode

```c
NTSTATUS __fastcall NsipEnsureKeyExistsWithSecurityDescriptor(PCWSTR SourceString)
{
  NTSTATUS result; // eax
  NTSTATUS v2; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Disposition; // [rsp+98h] [rbp+18h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+20h] BYREF

  KeyHandle = 0;
  Disposition = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 1600;
  ObjectAttributes.SecurityDescriptor = NsiDefaultSecurityDescriptorBytes;
  ObjectAttributes.SecurityQualityOfService = 0;
  result = ZwCreateKey(&KeyHandle, 0x40000u, &ObjectAttributes, 0, 0, 0, &Disposition);
  v2 = result;
  if ( !result )
  {
    if ( Disposition == 2 )
      v2 = ZwSetSecurityObject(KeyHandle, 4u, NsiDefaultSecurityDescriptorBytes);
    ZwClose(KeyHandle);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x14005f890  mov     rax, rsp
0x14005f893  mov     [rax+8], rbx
0x14005f897  mov     [rax+20h], rsi
0x14005f89b  mov     [rax+18h], r8
0x14005f89f  mov     [rax+10h], edx
0x14005f8a2  push    rbp
0x14005f8a3  mov     rbp, rsp
0x14005f8a6  sub     rsp, 80h
0x14005f8ad  xorps   xmm0, xmm0
0x14005f8b0  mov     [rbp+KeyHandle], 0
0x14005f8b8  xor     eax, eax
0x14005f8ba  mov     rdx, rcx; SourceString
0x14005f8bd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14005f8c1  lea     rcx, [rbp+DestinationString]; DestinationString
0x14005f8c5  mov     [rbp+arg_8], eax
0x14005f8c8  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14005f8cc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14005f8d0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14005f8d4  call    cs:__imp_RtlInitUnicodeString
0x14005f8db  nop     dword ptr [rax+rax+00h]
0x14005f8e0  lea     rax, [rbp+DestinationString]
0x14005f8e4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14005f8eb  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14005f8ef  lea     rsi, NsiDefaultSecurityDescriptorBytes
0x14005f8f6  lea     rax, [rbp+arg_8]
0x14005f8fa  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14005f902  mov     [rsp+80h+Disposition], rax; Disposition
0x14005f907  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14005f90b  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x14005f913  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14005f917  xor     r9d, r9d; TitleIndex
0x14005f91a  mov     [rsp+80h+Class], 0; Class
0x14005f923  mov     edx, 40000h; DesiredAccess
0x14005f928  mov     [rbp+ObjectAttributes.Attributes], 640h
0x14005f92f  mov     [rbp+ObjectAttributes.SecurityDescriptor], rsi
0x14005f933  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x14005f93b  call    cs:__imp_ZwCreateKey
0x14005f942  nop     dword ptr [rax+rax+00h]
0x14005f947  mov     ebx, eax
0x14005f949  test    eax, eax
0x14005f94b  jnz     short loc_14005F97D
0x14005f94d  cmp     [rbp+arg_8], 2
0x14005f951  jnz     short loc_14005F96B
0x14005f953  mov     rcx, [rbp+KeyHandle]; Handle
0x14005f957  lea     edx, [rax+4]; SecurityInformation
0x14005f95a  mov     r8, rsi; SecurityDescriptor
0x14005f95d  call    cs:__imp_ZwSetSecurityObject
0x14005f964  nop     dword ptr [rax+rax+00h]
0x14005f969  mov     ebx, eax
0x14005f96b  mov     rcx, [rbp+KeyHandle]; Handle
0x14005f96f  call    cs:__imp_ZwClose
0x14005f976  nop     dword ptr [rax+rax+00h]
0x14005f97b  mov     eax, ebx
0x14005f97d  lea     r11, [rsp+80h+var_s0]
0x14005f985  mov     rbx, [r11+10h]
0x14005f989  mov     rsi, [r11+28h]
0x14005f98d  mov     rsp, r11
0x14005f990  pop     rbp
0x14005f991  retn
```
