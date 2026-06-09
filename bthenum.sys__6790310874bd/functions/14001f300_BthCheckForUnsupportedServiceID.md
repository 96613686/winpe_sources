# BthCheckForUnsupportedServiceID

- ea: `0x14001f300`
- end: `0x14001f518`
- name: `BthCheckForUnsupportedServiceID`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x14001aa0c`

## callees

- `0x140001294`
- `0x140007d00`
- `0x14001f300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001f4d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f4d0`
- `ntoskrnl!ZwClose` at `0x14001f4ed`
- `ntoskrnl!ZwClose` at `0x14001f4ed`
- `ntoskrnl!ZwQueryValueKey` at `0x14001f45b`
- `ntoskrnl!ZwQueryValueKey` at `0x14001f4bc`
- `ntoskrnl!ZwQueryValueKey` at `0x14001f45b`
- `ntoskrnl!ZwQueryValueKey` at `0x14001f4bc`
- `ntoskrnl!ExAllocatePool2` at `0x14001f48b`
- `ntoskrnl!ExAllocatePool2` at `0x14001f48b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f35a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f42e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f35a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f42e`
- `ntoskrnl!ZwOpenKey` at `0x14001f39a`
- `ntoskrnl!ZwOpenKey` at `0x14001f39a`

## string_xrefs

- `0x14001f326`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters\UnsupportedServices`

## pseudocode

```c
__int64 __fastcall BthCheckForUnsupportedServiceID(unsigned int *a1)
{
  unsigned int v1; // r15d
  NTSTATUS v3; // edi
  NTSTATUS v4; // eax
  ULONG Length; // ebx
  void *Pool2; // rsi
  NTSTATUS v7; // ebx
  ULONG ResultLength; // [rsp+70h] [rbp-90h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-80h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszDest[40]; // [rsp+D0h] [rbp-30h] BYREF

  v1 = *a1;
  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  ValueName = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\UnsupportedServices");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v3 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v3 >= 0 )
  {
    RtlStringCchPrintfW(
      pszDest,
      0x28u,
      L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
      v1,
      *((unsigned __int16 *)a1 + 2),
      *((unsigned __int16 *)a1 + 3),
      *((unsigned __int8 *)a1 + 8),
      *((unsigned __int8 *)a1 + 9),
      *((unsigned __int8 *)a1 + 10),
      *((unsigned __int8 *)a1 + 11),
      *((unsigned __int8 *)a1 + 12),
      *((unsigned __int8 *)a1 + 13),
      *((unsigned __int8 *)a1 + 14),
      *((unsigned __int8 *)a1 + 15));
    RtlInitUnicodeString(&ValueName, pszDest);
    v4 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueBasicInformation, 0, 0, &ResultLength);
    v3 = v4;
    if ( v4 == -1073741789 || v4 == -2147483643 )
    {
      Length = ResultLength;
      Pool2 = (void *)ExAllocatePool2(64, ResultLength, 1818784834);
      if ( Pool2 )
      {
        v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueBasicInformation, Pool2, Length, &ResultLength);
        ExFreePoolWithTag(Pool2, 0x6C687442u);
        v3 = 0;
        if ( v7 < 0 )
          v3 = v7;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001f300  push    rbp
0x14001f302  push    rbx
0x14001f303  push    rsi
0x14001f304  push    rdi
0x14001f305  push    r14
0x14001f307  push    r15
0x14001f309  lea     rbp, [rsp-38h]
0x14001f30e  sub     rsp, 138h
0x14001f315  mov     rax, cs:__security_cookie
0x14001f31c  xor     rax, rsp
0x14001f31f  mov     [rbp+60h+var_40], rax
0x14001f323  mov     r15d, [rcx]
0x14001f326  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001f32d  xorps   xmm0, xmm0
0x14001f330  mov     [rsp+160h+KeyHandle], 0
0x14001f339  mov     r14, rcx
0x14001f33c  xor     eax, eax
0x14001f33e  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x14001f342  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x14001f346  mov     [rsp+160h+var_F0], eax
0x14001f34a  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x14001f34e  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x14001f352  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x14001f356  movups  xmmword ptr [rbp+60h+ValueName.Length], xmm0
0x14001f35a  call    cs:__imp_RtlInitUnicodeString
0x14001f361  nop     dword ptr [rax+rax+00h]
0x14001f366  lea     rax, [rbp+60h+DestinationString]
0x14001f36a  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x14001f371  xorps   xmm0, xmm0
0x14001f374  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x14001f378  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x14001f37c  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x14001f384  mov     edx, 20019h; DesiredAccess
0x14001f389  mov     [rbp+60h+ObjectAttributes.Attributes], 240h
0x14001f390  lea     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x14001f395  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f39a  call    cs:__imp_ZwOpenKey
0x14001f3a1  nop     dword ptr [rax+rax+00h]
0x14001f3a6  mov     edi, eax
0x14001f3a8  test    eax, eax
0x14001f3aa  js      loc_14001F4E3
0x14001f3b0  movzx   eax, byte ptr [r14+0Fh]
0x14001f3b5  mov     r9d, r15d
0x14001f3b8  movzx   ecx, byte ptr [r14+0Eh]
0x14001f3bd  movzx   edx, byte ptr [r14+0Dh]
0x14001f3c2  movzx   r8d, byte ptr [r14+0Ch]
0x14001f3c7  movzx   r10d, byte ptr [r14+0Bh]
0x14001f3cc  movzx   r11d, byte ptr [r14+0Ah]
0x14001f3d1  movzx   ebx, byte ptr [r14+9]
0x14001f3d6  movzx   edi, byte ptr [r14+8]
0x14001f3db  movzx   esi, word ptr [r14+6]
0x14001f3e0  movzx   r14d, word ptr [r14+4]
0x14001f3e5  mov     [rsp+160h+var_F8], eax
0x14001f3e9  mov     [rsp+160h+var_100], ecx
0x14001f3ed  lea     rcx, [rbp+60h+pszDest]; pszDest
0x14001f3f1  mov     [rsp+160h+var_108], edx
0x14001f3f5  mov     edx, 28h ; '('; cchDest
0x14001f3fa  mov     [rsp+160h+var_110], r8d
0x14001f3ff  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x14001f406  mov     [rsp+160h+var_118], r10d
0x14001f40b  mov     [rsp+160h+var_120], r11d
0x14001f410  mov     [rsp+160h+var_128], ebx
0x14001f414  mov     [rsp+160h+var_130], edi
0x14001f418  mov     dword ptr [rsp+160h+ResultLength], esi
0x14001f41c  mov     [rsp+160h+Length], r14d
0x14001f421  call    RtlStringCchPrintfW
0x14001f426  lea     rdx, [rbp+60h+pszDest]; SourceString
0x14001f42a  lea     rcx, [rbp+60h+ValueName]; DestinationString
0x14001f42e  call    cs:__imp_RtlInitUnicodeString
0x14001f435  nop     dword ptr [rax+rax+00h]
0x14001f43a  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x14001f43f  lea     rax, [rsp+160h+var_F0]
0x14001f444  mov     [rsp+160h+ResultLength], rax; ResultLength
0x14001f449  lea     rdx, [rbp+60h+ValueName]; ValueName
0x14001f44d  xor     r9d, r9d; KeyValueInformation
0x14001f450  mov     [rsp+160h+Length], 0; Length
0x14001f458  xor     r8d, r8d; KeyValueInformationClass
0x14001f45b  call    cs:__imp_ZwQueryValueKey
0x14001f462  nop     dword ptr [rax+rax+00h]
0x14001f467  mov     edi, eax
0x14001f469  cmp     eax, 0C0000023h
0x14001f46e  jz      short loc_14001F477
0x14001f470  cmp     eax, 80000005h
0x14001f475  jnz     short loc_14001F4E3
0x14001f477  mov     ebx, [rsp+160h+var_F0]
0x14001f47b  mov     r14d, 6C687442h
0x14001f481  mov     edx, ebx
0x14001f483  mov     r8d, r14d
0x14001f486  mov     ecx, 40h ; '@'
0x14001f48b  call    cs:__imp_ExAllocatePool2
0x14001f492  nop     dword ptr [rax+rax+00h]
0x14001f497  mov     rsi, rax
0x14001f49a  test    rax, rax
0x14001f49d  jz      short loc_14001F4E3
0x14001f49f  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x14001f4a4  lea     rax, [rsp+160h+var_F0]
0x14001f4a9  mov     [rsp+160h+ResultLength], rax; ResultLength
0x14001f4ae  lea     rdx, [rbp+60h+ValueName]; ValueName
0x14001f4b2  mov     r9, rsi; KeyValueInformation
0x14001f4b5  mov     [rsp+160h+Length], ebx; Length
0x14001f4b9  xor     r8d, r8d; KeyValueInformationClass
0x14001f4bc  call    cs:__imp_ZwQueryValueKey
0x14001f4c3  nop     dword ptr [rax+rax+00h]
0x14001f4c8  mov     ebx, eax
0x14001f4ca  mov     edx, r14d; Tag
0x14001f4cd  mov     rcx, rsi; P
0x14001f4d0  call    cs:__imp_ExFreePoolWithTag
0x14001f4d7  nop     dword ptr [rax+rax+00h]
0x14001f4dc  xor     edi, edi
0x14001f4de  test    ebx, ebx
0x14001f4e0  cmovs   edi, ebx
0x14001f4e3  mov     rcx, [rsp+160h+KeyHandle]; Handle
0x14001f4e8  test    rcx, rcx
0x14001f4eb  jz      short loc_14001F4F9
0x14001f4ed  call    cs:__imp_ZwClose
0x14001f4f4  nop     dword ptr [rax+rax+00h]
0x14001f4f9  mov     eax, edi
0x14001f4fb  mov     rcx, [rbp+60h+var_40]
0x14001f4ff  xor     rcx, rsp; StackCookie
0x14001f502  call    __security_check_cookie
0x14001f507  add     rsp, 138h
0x14001f50e  pop     r15
0x14001f510  pop     r14
0x14001f512  pop     rdi
0x14001f513  pop     rsi
0x14001f514  pop     rbx
0x14001f515  pop     rbp
0x14001f516  retn
```
