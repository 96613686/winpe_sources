# IsNTVDMInstalled

- ea: `0x18000d494`
- end: `0x18000d5b8`
- name: `IsNTVDMInstalled`
- size: `292`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d318`

## callees

- `0x18000d494`
- `0x18000d730`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000d533`
- `ntdll!NtOpenKey` at `0x18000d533`
- `ntdll!NtQueryValueKey` at `0x18000d564`
- `ntdll!NtQueryValueKey` at `0x18000d564`
- `ntdll!NtClose` at `0x18000d576`
- `ntdll!NtClose` at `0x18000d576`
- `ntdll!RtlInitUnicodeString` at `0x18000d4e1`
- `ntdll!RtlInitUnicodeString` at `0x18000d4f8`
- `ntdll!RtlInitUnicodeString` at `0x18000d4e1`
- `ntdll!RtlInitUnicodeString` at `0x18000d4f8`

## string_xrefs

- `0x18000d4bb`: `NTVDMInstalled`
- `0x18000d4ed`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\WOW`

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

  v0 = 0;
  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v5 = 0;
  ResultLength = 0;
  DestinationString = 0;
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
0x18000d494  mov     [rsp-8+arg_0], rbx
0x18000d499  mov     [rsp-8+arg_8], rdi
0x18000d49e  push    rbp
0x18000d49f  lea     rbp, [rsp-57h]
0x18000d4a4  sub     rsp, 0B0h
0x18000d4ab  mov     rax, cs:__security_cookie
0x18000d4b2  xor     rax, rsp
0x18000d4b5  mov     [rbp+57h+var_8], rax
0x18000d4b9  xor     edi, edi
0x18000d4bb  lea     rdx, aNtvdminstalled; "NTVDMInstalled"
0x18000d4c2  xorps   xmm0, xmm0
0x18000d4c5  mov     [rbp+57h+KeyHandle], rdi
0x18000d4c9  xorps   xmm1, xmm1
0x18000d4cc  mov     dword ptr [rbp+57h+ObjectAttributes+4], edi
0x18000d4cf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000d4d3  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], edi
0x18000d4d6  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x18000d4da  mov     [rbp+57h+var_80], edi
0x18000d4dd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18000d4e1  call    cs:__imp_RtlInitUnicodeString
0x18000d4e8  nop     dword ptr [rax+rax+00h]
0x18000d4ed  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18000d4f4  lea     rcx, [rbp+57h+var_70]; DestinationString
0x18000d4f8  call    cs:__imp_RtlInitUnicodeString
0x18000d4ff  nop     dword ptr [rax+rax+00h]
0x18000d504  lea     rax, [rbp+57h+var_70]
0x18000d508  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000d50f  xorps   xmm0, xmm0
0x18000d512  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000d516  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000d51a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x18000d51e  mov     edx, 20019h; DesiredAccess
0x18000d523  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000d52a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000d52e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d533  call    cs:__imp_NtOpenKey
0x18000d53a  nop     dword ptr [rax+rax+00h]
0x18000d53f  test    eax, eax
0x18000d541  js      short loc_18000D593
0x18000d543  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000d547  lea     rax, [rbp+57h+var_80]
0x18000d54b  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18000d550  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18000d554  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18000d558  mov     [rsp+0B0h+Length], 14h; Length
0x18000d560  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18000d564  call    cs:__imp_NtQueryValueKey
0x18000d56b  nop     dword ptr [rax+rax+00h]
0x18000d570  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18000d574  mov     ebx, eax
0x18000d576  call    cs:__imp_NtClose
0x18000d57d  nop     dword ptr [rax+rax+00h]
0x18000d582  test    ebx, ebx
0x18000d584  js      short loc_18000D593
0x18000d586  cmp     [rbp+57h+var_1C], 4
0x18000d58a  jnz     short loc_18000D593
0x18000d58c  cmp     [rbp+57h+var_14], edi
0x18000d58f  setnz   dil
0x18000d593  mov     al, dil
0x18000d596  mov     rcx, [rbp+57h+var_8]
0x18000d59a  xor     rcx, rsp; StackCookie
0x18000d59d  call    __security_check_cookie
0x18000d5a2  lea     r11, [rsp+0B0h+var_s0]
0x18000d5aa  mov     rbx, [r11+10h]
0x18000d5ae  mov     rdi, [r11+18h]
0x18000d5b2  mov     rsp, r11
0x18000d5b5  pop     rbp
0x18000d5b6  retn
```
