# GetPolicyState

- ea: `0x18000d748`
- end: `0x18000d890`
- name: `GetPolicyState`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d714`

## callees

- `0x18000d748`
- `0x18000db40`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000d809`
- `ntdll!NtOpenKey` at `0x18000d809`
- `ntdll!NtQueryValueKey` at `0x18000d83a`
- `ntdll!NtQueryValueKey` at `0x18000d83a`
- `ntdll!NtClose` at `0x18000d84c`
- `ntdll!NtClose` at `0x18000d84c`
- `ntdll!RtlInitUnicodeString` at `0x18000d7aa`
- `ntdll!RtlInitUnicodeString` at `0x18000d7ce`
- `ntdll!RtlInitUnicodeString` at `0x18000d7aa`
- `ntdll!RtlInitUnicodeString` at `0x18000d7ce`

## string_xrefs

- `0x18000d7bf`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows\AppCompat`
- `0x18000d7b6`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\WOW`

## pseudocode

```c
__int64 __fastcall GetPolicyState(char a1)
{
  unsigned int v1; // edi
  const WCHAR *v2; // rdx
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
  v2 = L"VDMDisallowed";
  KeyHandle = 0;
  ResultLength = 0;
  if ( !a1 )
    v2 = L"DisallowedPolicyDefault";
  v9 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, v2);
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
0x18000d748  mov     [rsp-8+arg_0], rbx
0x18000d74d  mov     [rsp-8+arg_8], rdi
0x18000d752  push    rbp
0x18000d753  lea     rbp, [rsp-57h]
0x18000d758  sub     rsp, 0B0h
0x18000d75f  mov     rax, cs:__security_cookie
0x18000d766  xor     rax, rsp
0x18000d769  mov     [rbp+57h+var_8], rax
0x18000d76d  xorps   xmm0, xmm0
0x18000d770  lea     rax, aDisallowedpoli; "DisallowedPolicyDefault"
0x18000d777  xor     edi, edi
0x18000d779  lea     rdx, aVdmdisallowed; "VDMDisallowed"
0x18000d780  test    cl, cl
0x18000d782  mov     [rbp+57h+KeyHandle], rdi
0x18000d786  mov     bl, cl
0x18000d788  mov     [rbp+57h+var_80], edi
0x18000d78b  xorps   xmm1, xmm1
0x18000d78e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000d792  cmovz   rdx, rax; SourceString
0x18000d796  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x18000d79a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18000d79e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000d7a2  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000d7a6  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d7aa  call    cs:__imp_RtlInitUnicodeString
0x18000d7b1  nop     dword ptr [rax+rax+00h]
0x18000d7b6  lea     rax, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18000d7bd  test    bl, bl
0x18000d7bf  lea     rdx, aRegistryMachin_5; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x18000d7c6  cmovz   rdx, rax; SourceString
0x18000d7ca  lea     rcx, [rbp+57h+var_70]; DestinationString
0x18000d7ce  call    cs:__imp_RtlInitUnicodeString
0x18000d7d5  nop     dword ptr [rax+rax+00h]
0x18000d7da  lea     rax, [rbp+57h+var_70]
0x18000d7de  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000d7e5  xorps   xmm0, xmm0
0x18000d7e8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000d7ec  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000d7f0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x18000d7f4  mov     edx, 20019h; DesiredAccess
0x18000d7f9  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000d800  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000d804  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d809  call    cs:__imp_NtOpenKey
0x18000d810  nop     dword ptr [rax+rax+00h]
0x18000d815  test    eax, eax
0x18000d817  js      short loc_18000D86C
0x18000d819  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000d81d  lea     rax, [rbp+57h+var_80]
0x18000d821  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18000d826  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18000d82a  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18000d82e  mov     [rsp+0B0h+Length], 14h; Length
0x18000d836  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18000d83a  call    cs:__imp_NtQueryValueKey
0x18000d841  nop     dword ptr [rax+rax+00h]
0x18000d846  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18000d84a  mov     ebx, eax
0x18000d84c  call    cs:__imp_NtClose
0x18000d853  nop     dword ptr [rax+rax+00h]
0x18000d858  test    ebx, ebx
0x18000d85a  js      short loc_18000D86C
0x18000d85c  cmp     [rbp+57h+var_1C], 4
0x18000d860  jnz     short loc_18000D86C
0x18000d862  mov     eax, [rbp+57h+var_14]
0x18000d865  neg     eax
0x18000d867  sbb     edi, edi
0x18000d869  add     edi, 2
0x18000d86c  mov     eax, edi
0x18000d86e  mov     rcx, [rbp+57h+var_8]
0x18000d872  xor     rcx, rsp; StackCookie
0x18000d875  call    __security_check_cookie
0x18000d87a  lea     r11, [rsp+0B0h+var_s0]
0x18000d882  mov     rbx, [r11+10h]
0x18000d886  mov     rdi, [r11+18h]
0x18000d88a  mov     rsp, r11
0x18000d88d  pop     rbp
0x18000d88e  retn
```
