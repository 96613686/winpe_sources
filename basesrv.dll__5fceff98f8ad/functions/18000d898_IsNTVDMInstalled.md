# IsNTVDMInstalled

- ea: `0x18000d898`
- end: `0x18000d9d2`
- name: `IsNTVDMInstalled`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d714`

## callees

- `0x18000d898`
- `0x18000db40`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000d94a`
- `ntdll!NtOpenKey` at `0x18000d94a`
- `ntdll!NtQueryValueKey` at `0x18000d97d`
- `ntdll!NtQueryValueKey` at `0x18000d97d`
- `ntdll!NtClose` at `0x18000d98f`
- `ntdll!NtClose` at `0x18000d98f`
- `ntdll!RtlInitUnicodeString` at `0x18000d8f4`
- `ntdll!RtlInitUnicodeString` at `0x18000d90b`
- `ntdll!RtlInitUnicodeString` at `0x18000d8f4`
- `ntdll!RtlInitUnicodeString` at `0x18000d90b`

## string_xrefs

- `0x18000d8d2`: `NTVDMInstalled`
- `0x18000d900`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\WOW`

## pseudocode

```c
bool IsNTVDMInstalled()
{
  char v0; // di
  NTSTATUS v1; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING v5; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v9; // [rsp+94h] [rbp+3Bh]
  int v10; // [rsp+9Ch] [rbp+43h]

  KeyHandle = 0;
  ResultLength = 0;
  v0 = 0;
  v5 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"NTVDMInstalled");
  RtlInitUnicodeString(&v5, L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WOW");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v5;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v1 = NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength);
    NtClose(KeyHandle);
    if ( v1 >= 0 && v9 == 4 )
      return v10 != 0;
  }
  return v0;
}

```

## disassembly

```asm
0x18000d898  mov     [rsp-8+arg_0], rbx
0x18000d89d  mov     [rsp-8+arg_8], rdi
0x18000d8a2  push    rbp
0x18000d8a3  lea     rbp, [rsp-57h]
0x18000d8a8  sub     rsp, 0B0h
0x18000d8af  mov     rax, cs:__security_cookie
0x18000d8b6  xor     rax, rsp
0x18000d8b9  mov     [rbp+57h+var_8], rax
0x18000d8bd  xorps   xmm0, xmm0
0x18000d8c0  mov     [rbp+57h+KeyHandle], 0
0x18000d8c8  xorps   xmm1, xmm1
0x18000d8cb  mov     [rbp+57h+var_80], 0
0x18000d8d2  lea     rdx, aNtvdminstalled; "NTVDMInstalled"
0x18000d8d9  xor     dil, dil
0x18000d8dc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000d8e0  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x18000d8e4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18000d8e8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000d8ec  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000d8f0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d8f4  call    cs:__imp_RtlInitUnicodeString
0x18000d8fb  nop     dword ptr [rax+rax+00h]
0x18000d900  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18000d907  lea     rcx, [rbp+57h+var_70]; DestinationString
0x18000d90b  call    cs:__imp_RtlInitUnicodeString
0x18000d912  nop     dword ptr [rax+rax+00h]
0x18000d917  lea     rax, [rbp+57h+var_70]
0x18000d91b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000d922  xorps   xmm0, xmm0
0x18000d925  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000d929  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000d92d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000d935  mov     edx, 20019h; DesiredAccess
0x18000d93a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000d941  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000d945  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d94a  call    cs:__imp_NtOpenKey
0x18000d951  nop     dword ptr [rax+rax+00h]
0x18000d956  test    eax, eax
0x18000d958  js      short loc_18000D9AD
0x18000d95a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000d95e  lea     rax, [rbp+57h+var_80]
0x18000d962  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18000d967  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18000d96b  mov     r8d, 2; KeyValueInformationClass
0x18000d971  mov     [rsp+0B0h+Length], 14h; Length
0x18000d979  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18000d97d  call    cs:__imp_NtQueryValueKey
0x18000d984  nop     dword ptr [rax+rax+00h]
0x18000d989  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18000d98d  mov     ebx, eax
0x18000d98f  call    cs:__imp_NtClose
0x18000d996  nop     dword ptr [rax+rax+00h]
0x18000d99b  test    ebx, ebx
0x18000d99d  js      short loc_18000D9AD
0x18000d99f  cmp     [rbp+57h+var_1C], 4
0x18000d9a3  jnz     short loc_18000D9AD
0x18000d9a5  cmp     [rbp+57h+var_14], 0
0x18000d9a9  setnz   dil
0x18000d9ad  mov     al, dil
0x18000d9b0  mov     rcx, [rbp+57h+var_8]
0x18000d9b4  xor     rcx, rsp; StackCookie
0x18000d9b7  call    __security_check_cookie
0x18000d9bc  lea     r11, [rsp+0B0h+var_s0]
0x18000d9c4  mov     rbx, [r11+10h]
0x18000d9c8  mov     rdi, [r11+18h]
0x18000d9cc  mov     rsp, r11
0x18000d9cf  pop     rbp
0x18000d9d0  retn
```
