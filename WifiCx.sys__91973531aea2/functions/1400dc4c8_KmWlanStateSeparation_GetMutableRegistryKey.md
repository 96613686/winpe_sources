# KmWlanStateSeparation_GetMutableRegistryKey

- ea: `0x1400dc4c8`
- end: `0x1400dc731`
- name: `KmWlanStateSeparation_GetMutableRegistryKey`
- size: `617`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140033378`
- `0x14006b040`
- `0x1400c9144`
- `0x1400c9274`
- `0x1400d1010`

## callees

- `0x1400dc4c8`
- `0x1400dfd00`
- `0x1400e0100`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400dc6fa`
- `ntoskrnl!ZwClose` at `0x1400dc6fa`
- `ntoskrnl!ZwQueryValueKey` at `0x1400dc661`
- `ntoskrnl!ZwQueryValueKey` at `0x1400dc661`
- `ntoskrnl!ZwOpenKey` at `0x1400dc607`
- `ntoskrnl!ZwOpenKey` at `0x1400dc607`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400dc5c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400dc631`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400dc5c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400dc631`
- `ntoskrnl!wcscpy_s` at `0x1400dc584`
- `ntoskrnl!wcscpy_s` at `0x1400dc67b`
- `ntoskrnl!wcscpy_s` at `0x1400dc696`
- `ntoskrnl!wcscpy_s` at `0x1400dc584`
- `ntoskrnl!wcscpy_s` at `0x1400dc67b`
- `ntoskrnl!wcscpy_s` at `0x1400dc696`
- `ntoskrnl!wcscat_s` at `0x1400dc5a3`
- `ntoskrnl!wcscat_s` at `0x1400dc6cd`
- `ntoskrnl!wcscat_s` at `0x1400dc6e2`
- `ntoskrnl!wcscat_s` at `0x1400dc5a3`
- `ntoskrnl!wcscat_s` at `0x1400dc6cd`
- `ntoskrnl!wcscat_s` at `0x1400dc6e2`

## string_xrefs

- `0x1400dc4f3`: `\REGISTRY\MACHINE\`
- `0x1400dc61d`: `RedirectedRegistryRoot`

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
0x1400dc4c8  push    rbp
0x1400dc4ca  push    rbx
0x1400dc4cb  push    rsi
0x1400dc4cc  push    rdi
0x1400dc4cd  push    r12
0x1400dc4cf  push    r14
0x1400dc4d1  push    r15
0x1400dc4d3  lea     rbp, [rsp-1E0h]
0x1400dc4db  sub     rsp, 2E0h
0x1400dc4e2  mov     rax, cs:__security_cookie
0x1400dc4e9  xor     rax, rsp
0x1400dc4ec  mov     [rbp+210h+var_38], rax
0x1400dc4f3  movups  xmm0, xmmword ptr cs:aRegistryMachin; "\\REGISTRY\\MACHINE\\"
0x1400dc4fa  mov     rsi, r8
0x1400dc4fd  mov     rdi, rcx
0x1400dc500  movups  xmm1, xmmword ptr cs:aRegistryMachin+10h; "Y\\MACHINE\\"
0x1400dc507  xor     r15d, r15d
0x1400dc50a  xor     edx, edx; Val
0x1400dc50c  movups  xmmword ptr [rbp+210h+Src], xmm0
0x1400dc513  lea     rcx, [rbp+210h+KeyValueInformation]; void *
0x1400dc517  mov     r8d, 218h; Size
0x1400dc51d  movsd   xmm0, qword ptr cs:aRegistryMachin+1Eh; "NE\\"
0x1400dc525  mov     r14, r9
0x1400dc528  movups  [rbp+210h+var_50], xmm1
0x1400dc52f  mov     [rsp+310h+KeyHandle], r15
0x1400dc534  xorps   xmm1, xmm1
0x1400dc537  movsd   qword ptr [rbp+210h+var_50+0Eh], xmm0
0x1400dc53f  xorps   xmm0, xmm0
0x1400dc542  movups  xmmword ptr [rsp+310h+DestinationString.Length], xmm0
0x1400dc547  movups  xmmword ptr [rsp+310h+ObjectAttributes.Length], xmm1
0x1400dc54c  movups  xmmword ptr [rsp+310h+ObjectAttributes.ObjectName], xmm1
0x1400dc551  movups  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400dc555  movups  xmmword ptr [rsp+310h+ValueName.Length], xmm1
0x1400dc55a  call    memset
0x1400dc55f  test    rdi, rdi
0x1400dc562  jz      loc_1400DC70A
0x1400dc568  test    rsi, rsi
0x1400dc56b  jz      loc_1400DC70A
0x1400dc571  mov     r12d, 104h
0x1400dc577  lea     r8, [rbp+210h+Src]; Src
0x1400dc57e  mov     edx, r12d; SizeInWords
0x1400dc581  mov     rcx, rdi; Dst
0x1400dc584  call    cs:__imp_wcscpy_s
0x1400dc58b  nop     dword ptr [rax+rax+00h]
0x1400dc590  mov     ebx, eax
0x1400dc592  test    eax, eax
0x1400dc594  jnz     loc_1400DC6F0
0x1400dc59a  mov     r8, rsi; Src
0x1400dc59d  mov     edx, r12d; SizeInWords
0x1400dc5a0  mov     rcx, rdi; Dst
0x1400dc5a3  call    cs:__imp_wcscat_s
0x1400dc5aa  nop     dword ptr [rax+rax+00h]
0x1400dc5af  mov     ebx, eax
0x1400dc5b1  test    eax, eax
0x1400dc5b3  jnz     loc_1400DC6F0
0x1400dc5b9  mov     rdx, rdi; SourceString
0x1400dc5bc  lea     rcx, [rsp+310h+DestinationString]; DestinationString
0x1400dc5c1  call    cs:__imp_RtlInitUnicodeString
0x1400dc5c8  nop     dword ptr [rax+rax+00h]
0x1400dc5cd  lea     rax, [rsp+310h+DestinationString]
0x1400dc5d2  mov     [rsp+310h+ObjectAttributes.Length], 30h ; '0'
0x1400dc5da  xorps   xmm0, xmm0
0x1400dc5dd  mov     [rsp+310h+ObjectAttributes.ObjectName], rax
0x1400dc5e2  lea     r8, [rsp+310h+ObjectAttributes]; ObjectAttributes
0x1400dc5e7  mov     [rsp+310h+ObjectAttributes.RootDirectory], r15
0x1400dc5ec  mov     edx, 20019h; DesiredAccess
0x1400dc5f1  mov     [rsp+310h+ObjectAttributes.Attributes], 240h
0x1400dc5f9  lea     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x1400dc5fe  add     rdi, 24h ; '$'
0x1400dc602  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400dc607  call    cs:__imp_ZwOpenKey
0x1400dc60e  nop     dword ptr [rax+rax+00h]
0x1400dc613  mov     r12d, 0F2h
0x1400dc619  test    eax, eax
0x1400dc61b  js      short loc_1400DC68D
0x1400dc61d  lea     rdx, SourceString; "RedirectedRegistryRoot"
0x1400dc624  mov     [rsp+310h+var_2E0], 1E4h
0x1400dc62c  lea     rcx, [rsp+310h+ValueName]; DestinationString
0x1400dc631  call    cs:__imp_RtlInitUnicodeString
0x1400dc638  nop     dword ptr [rax+rax+00h]
0x1400dc63d  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x1400dc642  lea     rax, [rsp+310h+var_2E0]
0x1400dc647  mov     [rsp+310h+ResultLength], rax; ResultLength
0x1400dc64c  lea     r9, [rbp+210h+KeyValueInformation]; KeyValueInformation
0x1400dc650  lea     r8d, [r15+2]; KeyValueInformationClass
0x1400dc654  mov     [rsp+310h+Length], 218h; Length
0x1400dc65c  lea     rdx, [rsp+310h+ValueName]; ValueName
0x1400dc661  call    cs:__imp_ZwQueryValueKey
0x1400dc668  nop     dword ptr [rax+rax+00h]
0x1400dc66d  test    eax, eax
0x1400dc66f  js      short loc_1400DC68D
0x1400dc671  lea     r8, [rbp+210h+var_274]; Src
0x1400dc675  mov     edx, r12d; SizeInWords
0x1400dc678  mov     rcx, rdi; Dst
0x1400dc67b  call    cs:__imp_wcscpy_s
0x1400dc682  nop     dword ptr [rax+rax+00h]
0x1400dc687  mov     ebx, eax
0x1400dc689  test    eax, eax
0x1400dc68b  jns     short loc_1400DC6A8
0x1400dc68d  mov     r8, rsi; Src
0x1400dc690  mov     rdx, r12; SizeInWords
0x1400dc693  mov     rcx, rdi; Dst
0x1400dc696  call    cs:__imp_wcscpy_s
0x1400dc69d  nop     dword ptr [rax+rax+00h]
0x1400dc6a2  mov     ebx, eax
0x1400dc6a4  test    eax, eax
0x1400dc6a6  js      short loc_1400DC6F0
0x1400dc6a8  test    r14, r14
0x1400dc6ab  jz      short loc_1400DC6F0
0x1400dc6ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400dc6b1  inc     rax
0x1400dc6b4  cmp     [r14+rax*2], r15w
0x1400dc6b9  jnz     short loc_1400DC6B1
0x1400dc6bb  test    rax, rax
0x1400dc6be  jz      short loc_1400DC6F0
0x1400dc6c0  lea     r8, Src; "\\"
0x1400dc6c7  mov     rdx, r12; SizeInWords
0x1400dc6ca  mov     rcx, rdi; Dst
0x1400dc6cd  call    cs:__imp_wcscat_s
0x1400dc6d4  nop     dword ptr [rax+rax+00h]
0x1400dc6d9  mov     r8, r14; Src
0x1400dc6dc  mov     rdx, r12; SizeInWords
0x1400dc6df  mov     rcx, rdi; Dst
0x1400dc6e2  call    cs:__imp_wcscat_s
0x1400dc6e9  nop     dword ptr [rax+rax+00h]
0x1400dc6ee  mov     ebx, eax
0x1400dc6f0  mov     rcx, [rsp+310h+KeyHandle]; Handle
0x1400dc6f5  test    rcx, rcx
0x1400dc6f8  jz      short loc_1400DC706
0x1400dc6fa  call    cs:__imp_ZwClose
0x1400dc701  nop     dword ptr [rax+rax+00h]
0x1400dc706  mov     eax, ebx
0x1400dc708  jmp     short loc_1400DC70F
0x1400dc70a  mov     eax, 57h ; 'W'
0x1400dc70f  mov     rcx, [rbp+210h+var_38]
0x1400dc716  xor     rcx, rsp; StackCookie
0x1400dc719  call    __security_check_cookie
0x1400dc71e  add     rsp, 2E0h
0x1400dc725  pop     r15
0x1400dc727  pop     r14
0x1400dc729  pop     r12
0x1400dc72b  pop     rdi
0x1400dc72c  pop     rsi
0x1400dc72d  pop     rbx
0x1400dc72e  pop     rbp
0x1400dc72f  retn
```
