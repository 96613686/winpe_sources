# KmWlanStateSeparation_GetMutableRegistryKey

- ea: `0x1400d88c0`
- end: `0x1400d8b29`
- name: `KmWlanStateSeparation_GetMutableRegistryKey`
- size: `617`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140077e34`
- `0x1400aa060`

## callees

- `0x1400d88c0`
- `0x1400da4f0`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400d8af2`
- `ntoskrnl!ZwClose` at `0x1400d8af2`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d8a59`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d8a59`
- `ntoskrnl!ZwOpenKey` at `0x1400d89ff`
- `ntoskrnl!ZwOpenKey` at `0x1400d89ff`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d89b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d8a29`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d89b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d8a29`
- `ntoskrnl!wcscpy_s` at `0x1400d897c`
- `ntoskrnl!wcscpy_s` at `0x1400d8a73`
- `ntoskrnl!wcscpy_s` at `0x1400d8a8e`
- `ntoskrnl!wcscpy_s` at `0x1400d897c`
- `ntoskrnl!wcscpy_s` at `0x1400d8a73`
- `ntoskrnl!wcscpy_s` at `0x1400d8a8e`
- `ntoskrnl!wcscat_s` at `0x1400d899b`
- `ntoskrnl!wcscat_s` at `0x1400d8ac5`
- `ntoskrnl!wcscat_s` at `0x1400d8ada`
- `ntoskrnl!wcscat_s` at `0x1400d899b`
- `ntoskrnl!wcscat_s` at `0x1400d8ac5`
- `ntoskrnl!wcscat_s` at `0x1400d8ada`

## string_xrefs

- `0x1400d88eb`: `\REGISTRY\MACHINE\`
- `0x1400d8a15`: `RedirectedRegistryRoot`

## pseudocode

```c
__int64 __fastcall KmWlanStateSeparation_GetMutableRegistryKey(
        wchar_t *SourceString,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  errno_t v7; // ebx
  wchar_t *v8; // rdi
  __int64 v9; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t KeyValueInformation[272]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Src[20]; // [rsp+2B0h] [rbp+1B0h] BYREF

  wcscpy(Src, L"\\REGISTRY\\MACHNE\\");
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ValueName = 0;
  memset(KeyValueInformation, 0, 0x218u);
  if ( !SourceString || !a3 )
    return 87;
  v7 = wcscpy_s(SourceString, 0x104u, Src);
  if ( !v7 )
  {
    v7 = wcscat_s(SourceString, 0x104u, a3);
    if ( !v7 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      v8 = SourceString + 18;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        ResultLength = 484;
        RtlInitUnicodeString(&ValueName, L"RedirectedRegistryRoot");
        if ( ZwQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValuePartialInformation,
               KeyValueInformation,
               0x218u,
               &ResultLength) >= 0 )
        {
          v7 = wcscpy_s(v8, 0xF2u, &KeyValueInformation[6]);
          if ( v7 >= 0 )
            goto LABEL_12;
        }
      }
      v7 = wcscpy_s(v8, 0xF2u, a3);
      if ( v7 >= 0 )
      {
LABEL_12:
        if ( a4 )
        {
          v9 = -1;
          do
            ++v9;
          while ( a4[v9] );
          if ( v9 )
          {
            wcscat_s(v8, 0xF2u, L"\\");
            v7 = wcscat_s(v8, 0xF2u, a4);
          }
        }
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400d88c0  push    rbp
0x1400d88c2  push    rbx
0x1400d88c3  push    rsi
0x1400d88c4  push    rdi
0x1400d88c5  push    r12
0x1400d88c7  push    r14
0x1400d88c9  push    r15
0x1400d88cb  lea     rbp, [rsp-1E0h]
0x1400d88d3  sub     rsp, 2E0h
0x1400d88da  mov     rax, cs:__security_cookie
0x1400d88e1  xor     rax, rsp
0x1400d88e4  mov     [rbp+210h+var_38], rax
0x1400d88eb  movups  xmm0, xmmword ptr cs:aRegistryMachin; "\\REGISTRY\\MACHINE\\"
0x1400d88f2  mov     rsi, r8
0x1400d88f5  mov     rdi, rcx
0x1400d88f8  movups  xmm1, xmmword ptr cs:aRegistryMachin+10h; "Y\\MACHINE\\"
0x1400d88ff  xor     r15d, r15d
0x1400d8902  xor     edx, edx; Val
0x1400d8904  movups  xmmword ptr [rbp+210h+Src], xmm0
0x1400d890b  lea     rcx, [rbp+210h+KeyValueInformation]; void *
0x1400d890f  mov     r8d, 218h; Size
0x1400d8915  movsd   xmm0, qword ptr cs:aRegistryMachin+1Eh; "NE\\"
0x1400d891d  mov     r14, r9
0x1400d8920  movups  [rbp+210h+var_50], xmm1
0x1400d8927  mov     [rsp+310h+KeyHandle], r15
0x1400d892c  xorps   xmm1, xmm1
0x1400d892f  movsd   qword ptr [rbp+210h+var_50+0Eh], xmm0
0x1400d8937  xorps   xmm0, xmm0
0x1400d893a  movups  xmmword ptr [rsp+310h+DestinationString.Length], xmm0
0x1400d893f  movups  xmmword ptr [rsp+310h+ObjectAttributes.Length], xmm1
0x1400d8944  movups  xmmword ptr [rsp+310h+ObjectAttributes.ObjectName], xmm1
0x1400d8949  movups  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400d894d  movups  xmmword ptr [rsp+310h+ValueName.Length], xmm1
0x1400d8952  call    memset
0x1400d8957  test    rdi, rdi
0x1400d895a  jz      loc_1400D8B02
0x1400d8960  test    rsi, rsi
0x1400d8963  jz      loc_1400D8B02
0x1400d8969  mov     r12d, 104h
0x1400d896f  lea     r8, [rbp+210h+Src]; Src
0x1400d8976  mov     edx, r12d; SizeInWords
0x1400d8979  mov     rcx, rdi; Dst
0x1400d897c  call    cs:__imp_wcscpy_s
0x1400d8983  nop     dword ptr [rax+rax+00h]
0x1400d8988  mov     ebx, eax
0x1400d898a  test    eax, eax
0x1400d898c  jnz     loc_1400D8AE8
0x1400d8992  mov     r8, rsi; Src
0x1400d8995  mov     edx, r12d; SizeInWords
0x1400d8998  mov     rcx, rdi; Dst
0x1400d899b  call    cs:__imp_wcscat_s
0x1400d89a2  nop     dword ptr [rax+rax+00h]
0x1400d89a7  mov     ebx, eax
0x1400d89a9  test    eax, eax
0x1400d89ab  jnz     loc_1400D8AE8
0x1400d89b1  mov     rdx, rdi; SourceString
0x1400d89b4  lea     rcx, [rsp+310h+DestinationString]; DestinationString
0x1400d89b9  call    cs:__imp_RtlInitUnicodeString
0x1400d89c0  nop     dword ptr [rax+rax+00h]
0x1400d89c5  lea     rax, [rsp+310h+DestinationString]
0x1400d89ca  mov     [rsp+310h+ObjectAttributes.Length], 30h ; '0'
0x1400d89d2  xorps   xmm0, xmm0
0x1400d89d5  mov     [rsp+310h+ObjectAttributes.ObjectName], rax
0x1400d89da  lea     r8, [rsp+310h+ObjectAttributes]; ObjectAttributes
0x1400d89df  mov     [rsp+310h+ObjectAttributes.RootDirectory], r15
0x1400d89e4  mov     edx, 20019h; DesiredAccess
0x1400d89e9  mov     [rsp+310h+ObjectAttributes.Attributes], 240h
0x1400d89f1  lea     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x1400d89f6  add     rdi, 24h ; '$'
0x1400d89fa  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d89ff  call    cs:__imp_ZwOpenKey
0x1400d8a06  nop     dword ptr [rax+rax+00h]
0x1400d8a0b  mov     r12d, 0F2h
0x1400d8a11  test    eax, eax
0x1400d8a13  js      short loc_1400D8A85
0x1400d8a15  lea     rdx, aRedirectedregi; "RedirectedRegistryRoot"
0x1400d8a1c  mov     [rsp+310h+var_2E0], 1E4h
0x1400d8a24  lea     rcx, [rsp+310h+ValueName]; DestinationString
0x1400d8a29  call    cs:__imp_RtlInitUnicodeString
0x1400d8a30  nop     dword ptr [rax+rax+00h]
0x1400d8a35  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x1400d8a3a  lea     rax, [rsp+310h+var_2E0]
0x1400d8a3f  mov     [rsp+310h+ResultLength], rax; ResultLength
0x1400d8a44  lea     r9, [rbp+210h+KeyValueInformation]; KeyValueInformation
0x1400d8a48  lea     r8d, [r15+2]; KeyValueInformationClass
0x1400d8a4c  mov     [rsp+310h+Length], 218h; Length
0x1400d8a54  lea     rdx, [rsp+310h+ValueName]; ValueName
0x1400d8a59  call    cs:__imp_ZwQueryValueKey
0x1400d8a60  nop     dword ptr [rax+rax+00h]
0x1400d8a65  test    eax, eax
0x1400d8a67  js      short loc_1400D8A85
0x1400d8a69  lea     r8, [rbp+210h+var_274]; Src
0x1400d8a6d  mov     edx, r12d; SizeInWords
0x1400d8a70  mov     rcx, rdi; Dst
0x1400d8a73  call    cs:__imp_wcscpy_s
0x1400d8a7a  nop     dword ptr [rax+rax+00h]
0x1400d8a7f  mov     ebx, eax
0x1400d8a81  test    eax, eax
0x1400d8a83  jns     short loc_1400D8AA0
0x1400d8a85  mov     r8, rsi; Src
0x1400d8a88  mov     rdx, r12; SizeInWords
0x1400d8a8b  mov     rcx, rdi; Dst
0x1400d8a8e  call    cs:__imp_wcscpy_s
0x1400d8a95  nop     dword ptr [rax+rax+00h]
0x1400d8a9a  mov     ebx, eax
0x1400d8a9c  test    eax, eax
0x1400d8a9e  js      short loc_1400D8AE8
0x1400d8aa0  test    r14, r14
0x1400d8aa3  jz      short loc_1400D8AE8
0x1400d8aa5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400d8aa9  inc     rax
0x1400d8aac  cmp     [r14+rax*2], r15w
0x1400d8ab1  jnz     short loc_1400D8AA9
0x1400d8ab3  test    rax, rax
0x1400d8ab6  jz      short loc_1400D8AE8
0x1400d8ab8  lea     r8, Src; "\\"
0x1400d8abf  mov     rdx, r12; SizeInWords
0x1400d8ac2  mov     rcx, rdi; Dst
0x1400d8ac5  call    cs:__imp_wcscat_s
0x1400d8acc  nop     dword ptr [rax+rax+00h]
0x1400d8ad1  mov     r8, r14; Src
0x1400d8ad4  mov     rdx, r12; SizeInWords
0x1400d8ad7  mov     rcx, rdi; Dst
0x1400d8ada  call    cs:__imp_wcscat_s
0x1400d8ae1  nop     dword ptr [rax+rax+00h]
0x1400d8ae6  mov     ebx, eax
0x1400d8ae8  mov     rcx, [rsp+310h+KeyHandle]; Handle
0x1400d8aed  test    rcx, rcx
0x1400d8af0  jz      short loc_1400D8AFE
0x1400d8af2  call    cs:__imp_ZwClose
0x1400d8af9  nop     dword ptr [rax+rax+00h]
0x1400d8afe  mov     eax, ebx
0x1400d8b00  jmp     short loc_1400D8B07
0x1400d8b02  mov     eax, 57h ; 'W'
0x1400d8b07  mov     rcx, [rbp+210h+var_38]
0x1400d8b0e  xor     rcx, rsp; StackCookie
0x1400d8b11  call    __security_check_cookie
0x1400d8b16  add     rsp, 2E0h
0x1400d8b1d  pop     r15
0x1400d8b1f  pop     r14
0x1400d8b21  pop     r12
0x1400d8b23  pop     rdi
0x1400d8b24  pop     rsi
0x1400d8b25  pop     rbx
0x1400d8b26  pop     rbp
0x1400d8b27  retn
```
