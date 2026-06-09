# UpdateUserLocaleLcidRegistryKey

- ea: `0x1800a3edc`
- end: `0x1800a4087`
- name: `UpdateUserLocaleLcidRegistryKey`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a2b80`

## callees

- `0x1800709b0`
- `0x1800a3edc`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800a3f5a`
- `ntdll!RtlInitUnicodeString` at `0x1800a3f6b`
- `ntdll!RtlInitUnicodeString` at `0x1800a3f5a`
- `ntdll!RtlInitUnicodeString` at `0x1800a3f6b`
- `ntdll!NtOpenKey` at `0x1800a3fb4`
- `ntdll!NtOpenKey` at `0x1800a3fb4`
- `ntdll!NtSetValueKey` at `0x1800a403e`
- `ntdll!NtSetValueKey` at `0x1800a403e`
- `ntdll!NtDeleteValueKey` at `0x1800a3fd8`
- `ntdll!NtDeleteValueKey` at `0x1800a3fd8`
- `ntdll!RtlIsMultiSessionSku` at `0x1800a3fc4`
- `ntdll!RtlIsMultiSessionSku` at `0x1800a3fc4`
- `ntdll!NtClose` at `0x1800a404b`
- `ntdll!NtClose` at `0x1800a405b`
- `ntdll!NtClose` at `0x1800a404b`
- `ntdll!NtClose` at `0x1800a405b`

## pseudocode

```c
__int64 __fastcall UpdateUserLocaleLcidRegistryKey(unsigned int a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  HANDLE v4; // rcx
  char *v5; // r8
  __int16 v6; // ax
  char *v7; // rdx
  unsigned int v8; // ecx
  HANDLE KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v13; // [rsp+80h] [rbp-80h] BYREF
  _WORD Data[7]; // [rsp+90h] [rbp-70h] BYREF
  char v15; // [rsp+9Eh] [rbp-62h] BYREF
  __int16 v16; // [rsp+A0h] [rbp-60h]

  Handle = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v13 = 0;
  DestinationString = 0;
  result = OpenGlobalizationUserSettingsKey(0x20019u, 0, &Handle);
  v3 = result;
  if ( (int)result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Locale");
    RtlInitUnicodeString(&v13, L"Control Panel\\International");
    v4 = Handle;
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.ObjectName = &v13;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 1600;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( a1 )
    {
      v3 = NtOpenKey(&KeyHandle, 0x40000000u, &ObjectAttributes);
      if ( v3 >= 0 )
      {
        if ( (unsigned __int8)RtlIsMultiSessionSku() )
        {
          v5 = &v15;
          v16 = 0;
          do
          {
            v6 = 48;
            v7 = v5 - 2;
            v8 = a1 & 0xF;
            if ( v8 > 9 )
              v6 = 55;
            a1 >>= 4;
            *(_WORD *)v5 = v8 + v6;
            v5 -= 2;
          }
          while ( v7 >= (char *)Data );
          v3 = NtSetValueKey(KeyHandle, &DestinationString, 0, 1u, Data, 0x12u);
        }
        else
        {
          NtDeleteValueKey(KeyHandle, &DestinationString);
        }
        NtClose(KeyHandle);
      }
      v4 = Handle;
    }
    if ( v4 )
      NtClose(v4);
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800a3edc  mov     [rsp-8+arg_0], rbx
0x1800a3ee1  mov     [rsp-8+arg_8], rdi
0x1800a3ee6  push    rbp
0x1800a3ee7  lea     rbp, [rsp-0A0h]
0x1800a3eef  sub     rsp, 1A0h
0x1800a3ef6  mov     rax, cs:__security_cookie
0x1800a3efd  xor     rax, rsp
0x1800a3f00  mov     [rbp+0A0h+var_10], rax
0x1800a3f07  xorps   xmm0, xmm0
0x1800a3f0a  lea     r8, [rsp+1A0h+Handle]; KeyHandle
0x1800a3f0f  xor     eax, eax
0x1800a3f11  mov     edi, ecx
0x1800a3f13  xorps   xmm1, xmm1
0x1800a3f16  mov     [rsp+1A0h+Handle], rax
0x1800a3f1b  movups  xmmword ptr [rsp+1A0h+ObjectAttributes.ObjectName], xmm0
0x1800a3f20  xor     edx, edx; Sid
0x1800a3f22  mov     [rsp+1A0h+KeyHandle], rax
0x1800a3f27  mov     ecx, 20019h; DesiredAccess
0x1800a3f2c  movups  xmmword ptr [rsp+1A0h+ObjectAttributes+1Ch], xmm0
0x1800a3f31  movups  xmmword ptr [rsp+1A0h+ObjectAttributes.Length], xmm0
0x1800a3f36  movups  xmmword ptr [rbp+0A0h+var_120.Length], xmm0
0x1800a3f3a  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm1
0x1800a3f3f  call    OpenGlobalizationUserSettingsKey
0x1800a3f44  mov     ebx, eax
0x1800a3f46  test    eax, eax
0x1800a3f48  js      loc_1800A4063
0x1800a3f4e  lea     rdx, aLocale; "Locale"
0x1800a3f55  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x1800a3f5a  call    cs:__imp_RtlInitUnicodeString
0x1800a3f60  lea     rdx, aControlPanelIn; "Control Panel\\International"
0x1800a3f67  lea     rcx, [rbp+0A0h+var_120]; DestinationString
0x1800a3f6b  call    cs:__imp_RtlInitUnicodeString
0x1800a3f71  mov     rcx, [rsp+1A0h+Handle]
0x1800a3f76  lea     rax, [rbp+0A0h+var_120]
0x1800a3f7a  mov     [rsp+1A0h+ObjectAttributes.RootDirectory], rcx
0x1800a3f7f  xorps   xmm0, xmm0
0x1800a3f82  mov     [rsp+1A0h+ObjectAttributes.ObjectName], rax
0x1800a3f87  mov     [rsp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x1800a3f8f  mov     [rsp+1A0h+ObjectAttributes.Attributes], 640h
0x1800a3f97  movdqu  xmmword ptr [rsp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a3f9d  test    edi, edi
0x1800a3f9f  jz      loc_1800A4056
0x1800a3fa5  lea     r8, [rsp+1A0h+ObjectAttributes]; ObjectAttributes
0x1800a3faa  mov     edx, 40000000h; DesiredAccess
0x1800a3faf  lea     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x1800a3fb4  call    cs:__imp_NtOpenKey
0x1800a3fba  mov     ebx, eax
0x1800a3fbc  test    eax, eax
0x1800a3fbe  js      loc_1800A4051
0x1800a3fc4  call    cs:__imp_RtlIsMultiSessionSku
0x1800a3fca  test    al, al
0x1800a3fcc  jnz     short loc_1800A3FE0
0x1800a3fce  mov     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x1800a3fd3  lea     rdx, [rsp+1A0h+DestinationString]; ValueName
0x1800a3fd8  call    cs:__imp_NtDeleteValueKey
0x1800a3fde  jmp     short loc_1800A4046
0x1800a3fe0  xor     eax, eax
0x1800a3fe2  lea     r8, [rbp+0A0h+var_102]
0x1800a3fe6  mov     [rbp+0A0h+var_100], ax
0x1800a3fea  mov     eax, 30h ; '0'
0x1800a3fef  lea     rdx, [r8-2]
0x1800a3ff3  mov     ecx, edi
0x1800a3ff5  and     ecx, 0Fh
0x1800a3ff8  cmp     ecx, 9
0x1800a3ffb  lea     r9d, [rax+7]
0x1800a3fff  cmova   ax, r9w
0x1800a4004  shr     edi, 4
0x1800a4007  add     ax, cx
0x1800a400a  mov     [r8], ax
0x1800a400e  lea     rax, [rbp+0A0h+var_110]
0x1800a4012  mov     r8, rdx
0x1800a4015  cmp     rdx, rax
0x1800a4018  jnb     short loc_1800A3FEA
0x1800a401a  mov     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x1800a401f  lea     rax, [rbp+0A0h+var_110]
0x1800a4023  mov     [rsp+1A0h+DataSize], 12h; DataSize
0x1800a402b  lea     rdx, [rsp+1A0h+DestinationString]; ValueName
0x1800a4030  mov     r9d, 1; Type
0x1800a4036  mov     [rsp+1A0h+Data], rax; Data
0x1800a403b  xor     r8d, r8d; TitleIndex
0x1800a403e  call    cs:__imp_NtSetValueKey
0x1800a4044  mov     ebx, eax
0x1800a4046  mov     rcx, [rsp+1A0h+KeyHandle]; Handle
0x1800a404b  call    cs:__imp_NtClose
0x1800a4051  mov     rcx, [rsp+1A0h+Handle]; Handle
0x1800a4056  test    rcx, rcx
0x1800a4059  jz      short loc_1800A4061
0x1800a405b  call    cs:__imp_NtClose
0x1800a4061  mov     eax, ebx
0x1800a4063  mov     rcx, [rbp+0A0h+var_10]
0x1800a406a  xor     rcx, rsp; StackCookie
0x1800a406d  call    __security_check_cookie
0x1800a4072  lea     r11, [rsp+1A0h+var_s0]
0x1800a407a  mov     rbx, [r11+10h]
0x1800a407e  mov     rdi, [r11+18h]
0x1800a4082  mov     rsp, r11
0x1800a4085  pop     rbp
0x1800a4086  retn
```
