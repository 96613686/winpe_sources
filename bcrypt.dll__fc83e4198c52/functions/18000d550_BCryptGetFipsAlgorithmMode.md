# BCryptGetFipsAlgorithmMode

- ea: `0x18000d550`
- end: `0x18000d8cd`
- name: `BCryptGetFipsAlgorithmMode`
- size: `893`
- prototype: `NTSTATUS __stdcall(BOOLEAN *pfEnabled)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000d550`
- `0x18001b7e0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18000d672`
- `ntdll!NtQueryValueKey` at `0x18000d772`
- `ntdll!NtQueryValueKey` at `0x18000d817`
- `ntdll!NtQueryValueKey` at `0x18000d672`
- `ntdll!NtQueryValueKey` at `0x18000d772`
- `ntdll!NtQueryValueKey` at `0x18000d817`
- `ntdll!NtClose` at `0x18000d86d`
- `ntdll!NtClose` at `0x18000d883`
- `ntdll!NtClose` at `0x18000d86d`
- `ntdll!NtClose` at `0x18000d883`
- `ntdll!RtlInitUnicodeString` at `0x18000d5d1`
- `ntdll!RtlInitUnicodeString` at `0x18000d5e9`
- `ntdll!RtlInitUnicodeString` at `0x18000d6d1`
- `ntdll!RtlInitUnicodeString` at `0x18000d6e9`
- `ntdll!RtlInitUnicodeString` at `0x18000d7e1`
- `ntdll!RtlInitUnicodeString` at `0x18000d5d1`
- `ntdll!RtlInitUnicodeString` at `0x18000d5e9`
- `ntdll!RtlInitUnicodeString` at `0x18000d6d1`
- `ntdll!RtlInitUnicodeString` at `0x18000d6e9`
- `ntdll!RtlInitUnicodeString` at `0x18000d7e1`
- `ntdll!NtOpenKey` at `0x18000d632`
- `ntdll!NtOpenKey` at `0x18000d732`
- `ntdll!NtOpenKey` at `0x18000d632`
- `ntdll!NtOpenKey` at `0x18000d732`

## string_xrefs

- `0x18000d5c6`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\FipsAlgorithmPolicy`
- `0x18000d6c5`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`

## pseudocode

```c
NTSTATUS __stdcall BCryptGetFipsAlgorithmMode(BOOLEAN *pfEnabled)
{
  void *v2; // rcx
  int v3; // edi
  ULONG ResultLength; // [rsp+34h] [rbp-94h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-78h] BYREF
  struct _UNICODE_STRING v9; // [rsp+58h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-60h] BYREF
  __int128 KeyValueInformation; // [rsp+98h] [rbp-30h] BYREF
  int v12; // [rsp+A8h] [rbp-20h]

  *(_QWORD *)&v9.Length = 0;
  v9.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  v2 = 0;
  KeyHandle = 0;
  Handle = 0;
  KeyValueInformation = 0;
  v12 = 0;
  ResultLength = 0;
  if ( pfEnabled )
  {
    *pfEnabled = 0;
    RtlInitUnicodeString(&v9, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\FipsAlgorithmPolicy");
    RtlInitUnicodeString(&DestinationString, L"Enabled");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &v9;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v3 = NtOpenKey(&KeyHandle, 1u, &ObjectAttributes);
    if ( v3 >= 0 )
    {
      v3 = NtQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x14u,
             &ResultLength);
      if ( v3 >= 0 )
      {
        if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
        {
          if ( BYTE12(KeyValueInformation) )
            *pfEnabled = 1;
        }
        else
        {
          v3 = -1073741762;
        }
      }
    }
    if ( v3 < 0 )
      v3 = 0;
    if ( !*pfEnabled )
    {
      RtlInitUnicodeString(&v9, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa");
      RtlInitUnicodeString(&DestinationString, L"FipsAlgorithmPolicy");
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = &v9;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v3 = NtOpenKey(&Handle, 1u, &ObjectAttributes);
      if ( v3 >= 0 )
      {
        v3 = NtQueryValueKey(
               Handle,
               &DestinationString,
               KeyValuePartialInformation,
               &KeyValueInformation,
               0x14u,
               &ResultLength);
        if ( v3 >= 0 )
        {
          if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
          {
            if ( BYTE12(KeyValueInformation) )
              *pfEnabled = 1;
          }
          else
          {
            v3 = -1073741762;
          }
        }
      }
      if ( v3 < 0 )
        v3 = 0;
      if ( !*pfEnabled )
      {
        if ( !KeyHandle )
          goto LABEL_31;
        RtlInitUnicodeString(&DestinationString, L"MDMEnabled");
        v3 = NtQueryValueKey(
               KeyHandle,
               &DestinationString,
               KeyValuePartialInformation,
               &KeyValueInformation,
               0x14u,
               &ResultLength);
        if ( v3 >= 0 )
        {
          if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
          {
            if ( BYTE12(KeyValueInformation) )
              *pfEnabled = 1;
          }
          else
          {
            v3 = -1073741762;
          }
        }
        if ( v3 < 0 )
          v3 = 0;
      }
    }
    v2 = KeyHandle;
  }
  else
  {
    v3 = -1073741811;
  }
  if ( v2 )
    NtClose(v2);
LABEL_31:
  if ( Handle )
    NtClose(Handle);
  return v3;
}

```

## disassembly

```asm
0x18000d550  mov     r11, rsp
0x18000d553  mov     [r11+10h], rbx
0x18000d557  mov     [r11+18h], rsi
0x18000d55b  push    rdi
0x18000d55c  sub     rsp, 0C0h
0x18000d563  mov     rax, cs:__security_cookie
0x18000d56a  xor     rax, rsp
0x18000d56d  mov     [rsp+0C8h+var_18], rax
0x18000d575  mov     rbx, rcx
0x18000d578  xor     esi, esi
0x18000d57a  mov     [rsp+0C8h+var_98], esi
0x18000d57e  mov     [r11-70h], rsi
0x18000d582  mov     [r11-68h], rsi
0x18000d586  mov     qword ptr [rsp+0C8h+DestinationString.Length], rsi
0x18000d58b  mov     [r11-80h], rsi
0x18000d58f  xor     eax, eax
0x18000d591  xorps   xmm0, xmm0
0x18000d594  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.Length], xmm0
0x18000d599  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.ObjectName], xmm0
0x18000d59e  movups  xmmword ptr [r11-44h], xmm0
0x18000d5a3  mov     ecx, esi
0x18000d5a5  mov     [rsp+0C8h+KeyHandle], rcx
0x18000d5aa  mov     [r11-78h], rsi
0x18000d5ae  movups  xmmword ptr [r11-30h], xmm0
0x18000d5b3  mov     [r11-20h], eax
0x18000d5b7  mov     [rsp+0C8h+var_94], esi
0x18000d5bb  test    rbx, rbx
0x18000d5be  jz      loc_18000D8B7
0x18000d5c4  mov     [rbx], al
0x18000d5c6  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000d5cd  lea     rcx, [r11-70h]; DestinationString
0x18000d5d1  call    cs:__imp_RtlInitUnicodeString
0x18000d5d8  nop     dword ptr [rax+rax+00h]
0x18000d5dd  lea     rdx, aEnabled; "Enabled"
0x18000d5e4  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x18000d5e9  call    cs:__imp_RtlInitUnicodeString
0x18000d5f0  nop     dword ptr [rax+rax+00h]
0x18000d5f5  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x18000d5fd  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x18000d602  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x18000d60d  lea     rax, [rsp+0C8h+var_70]
0x18000d612  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x18000d617  xorps   xmm0, xmm0
0x18000d61a  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d623  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x18000d628  mov     edx, 1; DesiredAccess
0x18000d62d  lea     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18000d632  call    cs:__imp_NtOpenKey
0x18000d639  nop     dword ptr [rax+rax+00h]
0x18000d63e  mov     edi, eax
0x18000d640  mov     [rsp+0C8h+var_98], eax
0x18000d644  test    eax, eax
0x18000d646  js      short loc_18000D6B4
0x18000d648  lea     rax, [rsp+0C8h+var_94]
0x18000d64d  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18000d652  mov     [rsp+0C8h+Length], 14h; Length
0x18000d65a  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x18000d662  mov     r8d, 2; KeyValueInformationClass
0x18000d668  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x18000d66d  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18000d672  call    cs:__imp_NtQueryValueKey
0x18000d679  nop     dword ptr [rax+rax+00h]
0x18000d67e  mov     edi, eax
0x18000d680  mov     [rsp+0C8h+var_98], eax
0x18000d684  test    eax, eax
0x18000d686  js      short loc_18000D6B4
0x18000d688  cmp     [rsp+0C8h+var_28], 4
0x18000d690  jnz     short loc_18000D6AB
0x18000d692  cmp     [rsp+0C8h+var_2C], 4
0x18000d69a  jnz     short loc_18000D6AB
0x18000d69c  cmp     [rsp+0C8h+var_24], sil
0x18000d6a4  jz      short loc_18000D6B4
0x18000d6a6  mov     byte ptr [rbx], 1
0x18000d6a9  jmp     short loc_18000D6B4
0x18000d6ab  mov     edi, 0C000003Eh
0x18000d6b0  mov     [rsp+0C8h+var_98], edi
0x18000d6b4  test    edi, edi
0x18000d6b6  js      loc_18000D8C2
0x18000d6bc  cmp     byte ptr [rbx], 0
0x18000d6bf  jnz     loc_18000D863
0x18000d6c5  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000d6cc  lea     rcx, [rsp+0C8h+var_70]; DestinationString
0x18000d6d1  call    cs:__imp_RtlInitUnicodeString
0x18000d6d8  nop     dword ptr [rax+rax+00h]
0x18000d6dd  lea     rdx, aFipsalgorithmp; "FipsAlgorithmPolicy"
0x18000d6e4  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x18000d6e9  call    cs:__imp_RtlInitUnicodeString
0x18000d6f0  nop     dword ptr [rax+rax+00h]
0x18000d6f5  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x18000d6fd  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x18000d702  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x18000d70d  lea     rax, [rsp+0C8h+var_70]
0x18000d712  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x18000d717  xorps   xmm0, xmm0
0x18000d71a  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d723  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x18000d728  mov     edx, 1; DesiredAccess
0x18000d72d  lea     rcx, [rsp+0C8h+Handle]; KeyHandle
0x18000d732  call    cs:__imp_NtOpenKey
0x18000d739  nop     dword ptr [rax+rax+00h]
0x18000d73e  mov     edi, eax
0x18000d740  mov     [rsp+0C8h+var_98], eax
0x18000d744  test    eax, eax
0x18000d746  js      short loc_18000D7B4
0x18000d748  lea     rax, [rsp+0C8h+var_94]
0x18000d74d  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18000d752  mov     [rsp+0C8h+Length], 14h; Length
0x18000d75a  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x18000d762  mov     r8d, 2; KeyValueInformationClass
0x18000d768  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x18000d76d  mov     rcx, [rsp+0C8h+Handle]; KeyHandle
0x18000d772  call    cs:__imp_NtQueryValueKey
0x18000d779  nop     dword ptr [rax+rax+00h]
0x18000d77e  mov     edi, eax
0x18000d780  mov     [rsp+0C8h+var_98], eax
0x18000d784  test    eax, eax
0x18000d786  js      short loc_18000D7B4
0x18000d788  cmp     [rsp+0C8h+var_2C], 4
0x18000d790  jnz     short loc_18000D7AB
0x18000d792  cmp     [rsp+0C8h+var_28], 4
0x18000d79a  jnz     short loc_18000D7AB
0x18000d79c  cmp     [rsp+0C8h+var_24], 0
0x18000d7a4  jz      short loc_18000D7B4
0x18000d7a6  mov     byte ptr [rbx], 1
0x18000d7a9  jmp     short loc_18000D7B4
0x18000d7ab  mov     edi, 0C000003Eh
0x18000d7b0  mov     [rsp+0C8h+var_98], edi
0x18000d7b4  test    edi, edi
0x18000d7b6  jns     short loc_18000D7BE
0x18000d7b8  mov     edi, esi
0x18000d7ba  mov     [rsp+0C8h+var_98], esi
0x18000d7be  cmp     byte ptr [rbx], 0
0x18000d7c1  jnz     loc_18000D863
0x18000d7c7  mov     rcx, [rsp+0C8h+KeyHandle]
0x18000d7cc  test    rcx, rcx
0x18000d7cf  jz      loc_18000D879
0x18000d7d5  lea     rdx, aMdmenabled; "MDMEnabled"
0x18000d7dc  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x18000d7e1  call    cs:__imp_RtlInitUnicodeString
0x18000d7e8  nop     dword ptr [rax+rax+00h]
0x18000d7ed  lea     rax, [rsp+0C8h+var_94]
0x18000d7f2  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18000d7f7  mov     [rsp+0C8h+Length], 14h; Length
0x18000d7ff  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x18000d807  mov     r8d, 2; KeyValueInformationClass
0x18000d80d  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x18000d812  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18000d817  call    cs:__imp_NtQueryValueKey
0x18000d81e  nop     dword ptr [rax+rax+00h]
0x18000d823  mov     edi, eax
0x18000d825  mov     [rsp+0C8h+var_98], eax
0x18000d829  test    eax, eax
0x18000d82b  js      short loc_18000D859
0x18000d82d  cmp     [rsp+0C8h+var_2C], 4
0x18000d835  jz      short loc_18000D842
0x18000d837  mov     edi, 0C000003Eh
0x18000d83c  mov     [rsp+0C8h+var_98], edi
0x18000d840  jmp     short loc_18000D859
0x18000d842  cmp     [rsp+0C8h+var_28], 4
0x18000d84a  jnz     short loc_18000D837
0x18000d84c  cmp     [rsp+0C8h+var_24], 0
0x18000d854  jz      short loc_18000D859
0x18000d856  mov     byte ptr [rbx], 1
0x18000d859  test    edi, edi
0x18000d85b  jns     short loc_18000D863
0x18000d85d  mov     edi, esi
0x18000d85f  mov     [rsp+0C8h+var_98], esi
0x18000d863  mov     rcx, [rsp+0C8h+KeyHandle]; Handle
0x18000d868  test    rcx, rcx
0x18000d86b  jz      short loc_18000D879
0x18000d86d  call    cs:__imp_NtClose
0x18000d874  nop     dword ptr [rax+rax+00h]
0x18000d879  mov     rcx, [rsp+0C8h+Handle]; Handle
0x18000d87e  test    rcx, rcx
0x18000d881  jz      short loc_18000D88F
0x18000d883  call    cs:__imp_NtClose
0x18000d88a  nop     dword ptr [rax+rax+00h]
0x18000d88f  mov     eax, edi
0x18000d891  mov     rcx, [rsp+0C8h+var_18]
0x18000d899  xor     rcx, rsp; StackCookie
0x18000d89c  call    __security_check_cookie
0x18000d8a1  lea     r11, [rsp+0C8h+var_8]
0x18000d8a9  mov     rbx, [r11+18h]
0x18000d8ad  mov     rsi, [r11+20h]
0x18000d8b1  mov     rsp, r11
0x18000d8b4  pop     rdi
0x18000d8b5  retn
0x18000d8b7  mov     edi, 0C000000Dh
0x18000d8bc  mov     [rsp+0C8h+var_98], edi
0x18000d8c0  jmp     short loc_18000D868
0x18000d8c2  mov     edi, esi
0x18000d8c4  mov     [rsp+0C8h+var_98], esi
0x18000d8c8  jmp     loc_18000D6BC
0x18001b8c0  push    rbp
0x18001b8c2  sub     rsp, 30h
0x18001b8c6  mov     rbp, rdx
0x18001b8c9  mov     eax, [rbp+30h]
0x18001b8cc  xor     ecx, ecx
0x18001b8ce  test    eax, eax
0x18001b8d0  cmovs   eax, ecx
0x18001b8d3  mov     [rbp+30h], eax
0x18001b8d6  add     rsp, 30h
0x18001b8da  pop     rbp
0x18001b8db  retn
0x18001b8dd  push    rbp
0x18001b8df  sub     rsp, 30h
0x18001b8e3  mov     rbp, rdx
0x18001b8e6  mov     eax, [rbp+30h]
0x18001b8e9  xor     ecx, ecx
0x18001b8eb  test    eax, eax
0x18001b8ed  cmovs   eax, ecx
0x18001b8f0  mov     [rbp+30h], eax
0x18001b8f3  add     rsp, 30h
0x18001b8f7  pop     rbp
0x18001b8f8  retn
0x18001b8fa  push    rbp
0x18001b8fc  sub     rsp, 30h
0x18001b900  mov     rbp, rdx
0x18001b903  mov     eax, [rbp+30h]
0x18001b906  xor     ecx, ecx
0x18001b908  test    eax, eax
0x18001b90a  cmovs   eax, ecx
0x18001b90d  mov     [rbp+30h], eax
0x18001b910  add     rsp, 30h
0x18001b914  pop     rbp
0x18001b915  retn
```
