# GetPolicyState

- ea: `0x18000d34c`
- end: `0x18000d48e`
- name: `GetPolicyState`
- size: `322`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d318`

## callees

- `0x18000d34c`
- `0x18000d730`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000d407`
- `ntdll!NtOpenKey` at `0x18000d407`
- `ntdll!NtQueryValueKey` at `0x18000d438`
- `ntdll!NtQueryValueKey` at `0x18000d438`
- `ntdll!NtClose` at `0x18000d44a`
- `ntdll!NtClose` at `0x18000d44a`
- `ntdll!RtlInitUnicodeString` at `0x18000d3a8`
- `ntdll!RtlInitUnicodeString` at `0x18000d3cc`
- `ntdll!RtlInitUnicodeString` at `0x18000d3a8`
- `ntdll!RtlInitUnicodeString` at `0x18000d3cc`

## string_xrefs

- `0x18000d3bd`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows\AppCompat`
- `0x18000d3b4`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\WOW`

## pseudocode

```c
__int64 __fastcall GetPolicyState(char a1)
{
  unsigned int v1; // edi
  const WCHAR *v3; // rdx
  const WCHAR *v4; // rdx
  NTSTATUS v5; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING v9; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v13; // [rsp+94h] [rbp+3Bh]
  int v14; // [rsp+9Ch] [rbp+43h]

  v1 = 0;
  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ResultLength = 0;
  v3 = L"VDMDisallowed";
  if ( !a1 )
    v3 = L"DisallowedPolicyDefault";
  v9 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v3);
  v4 = L"\\REGISTRY\\MACHINE\\Software\\Policies\\Microsoft\\Windows\\AppCompat";
  if ( !a1 )
    v4 = L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WOW";
  RtlInitUnicodeString(&v9, v4);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v9;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v5 = NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength);
    NtClose(KeyHandle);
    if ( v5 >= 0 && v13 == 4 )
      return 2 - (unsigned int)(v14 != 0);
  }
  return v1;
}

```

## disassembly

```asm
0x18000d34c  mov     [rsp-8+arg_0], rbx
0x18000d351  mov     [rsp-8+arg_8], rdi
0x18000d356  push    rbp
0x18000d357  lea     rbp, [rsp-57h]
0x18000d35c  sub     rsp, 0B0h
0x18000d363  mov     rax, cs:__security_cookie
0x18000d36a  xor     rax, rsp
0x18000d36d  mov     [rbp+57h+var_8], rax
0x18000d371  xor     edi, edi
0x18000d373  lea     rax, aDisallowedpoli; "DisallowedPolicyDefault"
0x18000d37a  test    cl, cl
0x18000d37c  mov     [rbp+57h+KeyHandle], rdi
0x18000d380  mov     bl, cl
0x18000d382  mov     dword ptr [rbp+57h+ObjectAttributes+4], edi
0x18000d385  xorps   xmm0, xmm0
0x18000d388  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], edi
0x18000d38b  xorps   xmm1, xmm1
0x18000d38e  mov     [rbp+57h+var_80], edi
0x18000d391  lea     rdx, aVdmdisallowed; "VDMDisallowed"
0x18000d398  cmovz   rdx, rax; SourceString
0x18000d39c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000d3a0  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x18000d3a4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18000d3a8  call    cs:__imp_RtlInitUnicodeString
0x18000d3af  nop     dword ptr [rax+rax+00h]
0x18000d3b4  lea     rax, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18000d3bb  test    bl, bl
0x18000d3bd  lea     rdx, aRegistryMachin_5; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x18000d3c4  cmovz   rdx, rax; SourceString
0x18000d3c8  lea     rcx, [rbp+57h+var_70]; DestinationString
0x18000d3cc  call    cs:__imp_RtlInitUnicodeString
0x18000d3d3  nop     dword ptr [rax+rax+00h]
0x18000d3d8  lea     rax, [rbp+57h+var_70]
0x18000d3dc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000d3e3  xorps   xmm0, xmm0
0x18000d3e6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000d3ea  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000d3ee  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x18000d3f2  mov     edx, 20019h; DesiredAccess
0x18000d3f7  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000d3fe  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000d402  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d407  call    cs:__imp_NtOpenKey
0x18000d40e  nop     dword ptr [rax+rax+00h]
0x18000d413  test    eax, eax
0x18000d415  js      short loc_18000D46A
0x18000d417  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000d41b  lea     rax, [rbp+57h+var_80]
0x18000d41f  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18000d424  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18000d428  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18000d42c  mov     [rsp+0B0h+Length], 14h; Length
0x18000d434  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18000d438  call    cs:__imp_NtQueryValueKey
0x18000d43f  nop     dword ptr [rax+rax+00h]
0x18000d444  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18000d448  mov     ebx, eax
0x18000d44a  call    cs:__imp_NtClose
0x18000d451  nop     dword ptr [rax+rax+00h]
0x18000d456  test    ebx, ebx
0x18000d458  js      short loc_18000D46A
0x18000d45a  cmp     [rbp+57h+var_1C], 4
0x18000d45e  jnz     short loc_18000D46A
0x18000d460  mov     eax, [rbp+57h+var_14]
0x18000d463  neg     eax
0x18000d465  sbb     ecx, ecx
0x18000d467  lea     edi, [rcx+2]
0x18000d46a  mov     eax, edi
0x18000d46c  mov     rcx, [rbp+57h+var_8]
0x18000d470  xor     rcx, rsp; StackCookie
0x18000d473  call    __security_check_cookie
0x18000d478  lea     r11, [rsp+0B0h+var_s0]
0x18000d480  mov     rbx, [r11+10h]
0x18000d484  mov     rdi, [r11+18h]
0x18000d488  mov     rsp, r11
0x18000d48b  pop     rbp
0x18000d48c  retn
```
