# SiOpenRegistryKey

- ea: `0x14001d5bc`
- end: `0x14001d664`
- name: `SiOpenRegistryKey`
- size: `168`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001d260`

## callees

- `0x14001d5bc`

## import_xrefs

- `ntdll!NtOpenKey` at `0x14001d62c`
- `ntdll!NtOpenKey` at `0x14001d62c`
- `ntdll!NtClose` at `0x14001d64a`
- `ntdll!NtClose` at `0x14001d64a`
- `ntdll!RtlInitUnicodeString` at `0x14001d5f3`
- `ntdll!RtlInitUnicodeString` at `0x14001d5f3`

## pseudocode

```c
__int64 __fastcall SiOpenRegistryKey(__int64 a1, const WCHAR *a2, __int64 a3, void **a4)
{
  NTSTATUS v5; // eax
  void *v6; // rcx
  unsigned int v7; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v6 = KeyHandle;
  v7 = v5;
  if ( v5 >= 0 )
  {
    *a4 = KeyHandle;
    v6 = 0;
    KeyHandle = 0;
  }
  if ( v6 )
    NtClose(v6);
  return v7;
}

```

## disassembly

```asm
0x14001d5bc  mov     [rsp-8+arg_8], rbx
0x14001d5c1  mov     [rsp-8+arg_10], rdi
0x14001d5c6  mov     [rsp-8+KeyHandle], rcx
0x14001d5cb  push    rbp
0x14001d5cc  mov     rbp, rsp
0x14001d5cf  sub     rsp, 60h
0x14001d5d3  xorps   xmm0, xmm0
0x14001d5d6  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001d5da  xor     eax, eax
0x14001d5dc  mov     rdi, r9
0x14001d5df  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001d5e3  mov     [rbp+KeyHandle], rax
0x14001d5e7  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001d5eb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001d5ef  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001d5f3  call    cs:__imp_RtlInitUnicodeString
0x14001d5f9  lea     rax, [rbp+DestinationString]
0x14001d5fd  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001d604  xorps   xmm0, xmm0
0x14001d607  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001d60b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001d60f  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14001d617  mov     edx, 20019h; DesiredAccess
0x14001d61c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14001d623  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14001d627  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001d62c  call    cs:__imp_NtOpenKey
0x14001d632  mov     rcx, [rbp+KeyHandle]
0x14001d636  mov     ebx, eax
0x14001d638  test    eax, eax
0x14001d63a  js      short loc_14001D645
0x14001d63c  mov     [rdi], rcx
0x14001d63f  xor     ecx, ecx; Handle
0x14001d641  mov     [rbp+KeyHandle], rcx
0x14001d645  test    rcx, rcx
0x14001d648  jz      short loc_14001D650
0x14001d64a  call    cs:__imp_NtClose
0x14001d650  lea     r11, [rsp+60h+var_s0]
0x14001d655  mov     eax, ebx
0x14001d657  mov     rbx, [r11+18h]
0x14001d65b  mov     rdi, [r11+20h]
0x14001d65f  mov     rsp, r11
0x14001d662  pop     rbp
0x14001d663  retn
```
