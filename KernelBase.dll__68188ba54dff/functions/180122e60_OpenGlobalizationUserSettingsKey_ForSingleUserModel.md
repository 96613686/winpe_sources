# OpenGlobalizationUserSettingsKey_ForSingleUserModel

- ea: `0x180122e60`
- end: `0x1801230c4`
- name: `OpenGlobalizationUserSettingsKey_ForSingleUserModel`
- size: `612`
- prototype: `__int64 __fastcall(ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)`
- caller_count: `16`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000dd50`
- `0x1800108d0`
- `0x1800123e0`
- `0x1800181e0`
- `0x180019090`
- `0x18001a230`
- `0x18001b3a0`
- `0x18001d7c0`
- `0x180037730`
- `0x1800709b0`
- `0x180070c90`
- `0x180071550`
- `0x180071b90`
- `0x180071e90`
- `0x18007217c`
- `0x180072474`

## callees

- `0x180049440`
- `0x180107ea0`
- `0x180122e60`
- `0x180126304`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180122e9b`
- `ntdll!RtlInitUnicodeString` at `0x180122ef5`
- `ntdll!RtlInitUnicodeString` at `0x180122f2e`
- `ntdll!RtlInitUnicodeString` at `0x180122fd6`
- `ntdll!RtlInitUnicodeString` at `0x180122e9b`
- `ntdll!RtlInitUnicodeString` at `0x180122ef5`
- `ntdll!RtlInitUnicodeString` at `0x180122f2e`
- `ntdll!RtlInitUnicodeString` at `0x180122fd6`
- `ntdll!RtlCopyUnicodeString` at `0x18012301b`
- `ntdll!RtlCopyUnicodeString` at `0x18012307a`
- `ntdll!RtlCopyUnicodeString` at `0x18012301b`
- `ntdll!RtlCopyUnicodeString` at `0x18012307a`
- `ntdll!ZwQueryValueKey` at `0x180122f57`
- `ntdll!ZwQueryValueKey` at `0x180122fa9`
- `ntdll!ZwQueryValueKey` at `0x180122f57`
- `ntdll!ZwQueryValueKey` at `0x180122fa9`
- `ntdll!ZwClose` at `0x1801230a4`
- `ntdll!ZwClose` at `0x1801230a4`
- `ntdll!ZwOpenKey` at `0x180122ed1`
- `ntdll!ZwOpenKey` at `0x180122ed1`

## string_xrefs

- `0x180122ede`: `\Registry\Machine\System\CurrentControlSet\Control\CommonGlobUserSettings\`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForSingleUserModel(ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)
{
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  WCHAR *v6; // rdi
  HANDLE v7; // rax
  UNICODE_STRING SourceString; // [rsp+38h] [rbp-31h] BYREF
  UNICODE_STRING v10; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+Fh] BYREF
  ULONG ResultLength; // [rsp+E0h] [rbp+77h] BYREF
  HANDLE KeyHandlea; // [rsp+E8h] [rbp+7Fh]

  if ( dword_18039F244 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, &word_18039E950);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)ZwOpenKey(KeyHandle, DesiredAccess, &ObjectAttributes);
  }
  KeyHandlea = 0;
  v10 = 0;
  RtlInitUnicodeString(&v10, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CommonGlobUserSettings\\");
  v4 = OpenRegistryKey(DesiredAccess);
  if ( v4 >= 0 )
  {
    ResultLength = 0;
    ValueName = 0;
    RtlInitUnicodeString(&ValueName, L"RedirectedKey");
    v5 = ZwQueryValueKey(KeyHandlea, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( !ResultLength || v5 != -1073741789 && v5 != -2147483643 )
    {
      *(_QWORD *)&DestinationString.Length = 11141120;
      DestinationString.Buffer = &word_18039E950;
      if ( v10.Length <= 0xAAu )
      {
        RtlCopyUnicodeString(&DestinationString, &v10);
        dword_18039F244 = 1;
      }
      v4 = 0;
      *KeyHandle = KeyHandlea;
      KeyHandlea = 0;
      goto LABEL_21;
    }
    v6 = (WCHAR *)wil::details::heap_allocator::allocate(ResultLength);
    if ( v6 )
    {
      v4 = ZwQueryValueKey(KeyHandlea, &ValueName, KeyValuePartialInformation, v6, ResultLength, &ResultLength);
      if ( v4 >= 0 )
      {
        if ( *((_DWORD *)v6 + 1) != 1 )
        {
          v7 = KeyHandlea;
          KeyHandlea = 0;
LABEL_15:
          *KeyHandle = v7;
          goto LABEL_16;
        }
        SourceString = 0;
        RtlInitUnicodeString(&SourceString, v6 + 6);
        v4 = OpenRegistryKey(DesiredAccess);
        if ( v4 >= 0 )
        {
          *(_QWORD *)&DestinationString.Length = 11141120;
          DestinationString.Buffer = &word_18039E950;
          if ( SourceString.Length <= 0xAAu )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            dword_18039F244 = 1;
          }
          v7 = 0;
          goto LABEL_15;
        }
      }
LABEL_16:
      FreeEnvironmentStringsW(v6);
      goto LABEL_21;
    }
    v4 = -1073741801;
  }
LABEL_21:
  if ( KeyHandlea )
    ZwClose(KeyHandlea);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180122e60  mov     [rsp-8+arg_0], rbx
0x180122e65  mov     [rsp-8+arg_8], rsi
0x180122e6a  push    rbp
0x180122e6b  push    rdi
0x180122e6c  push    r14
0x180122e6e  lea     rbp, [rsp-47h]
0x180122e73  sub     rsp, 0B0h
0x180122e7a  cmp     cs:dword_18039F244, 0
0x180122e81  mov     rsi, rdx
0x180122e84  mov     r14d, ecx
0x180122e87  xorps   xmm0, xmm0
0x180122e8a  jz      short loc_180122EDE
0x180122e8c  lea     rdx, word_18039E950; SourceString
0x180122e93  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180122e97  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180122e9b  call    cs:__imp_RtlInitUnicodeString
0x180122ea1  xor     eax, eax
0x180122ea3  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180122eab  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180122eaf  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180122eb3  lea     rax, [rbp+57h+DestinationString]
0x180122eb7  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180122ebf  xorps   xmm0, xmm0
0x180122ec2  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180122ec6  mov     edx, r14d; DesiredAccess
0x180122ec9  mov     rcx, rsi; KeyHandle
0x180122ecc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180122ed1  call    cs:__imp_ZwOpenKey
0x180122ed7  mov     ebx, eax
0x180122ed9  jmp     loc_1801230AA
0x180122ede  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180122ee5  mov     [rbp+57h+KeyHandle], 0
0x180122eed  lea     rcx, [rbp+57h+var_78]; DestinationString
0x180122ef1  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x180122ef5  call    cs:__imp_RtlInitUnicodeString
0x180122efb  lea     r8, [rbp+57h+KeyHandle]
0x180122eff  mov     ecx, r14d; DesiredAccess
0x180122f02  lea     rdx, [rbp+57h+var_78]
0x180122f06  call    OpenRegistryKey
0x180122f0b  mov     ebx, eax
0x180122f0d  test    eax, eax
0x180122f0f  js      loc_18012309B
0x180122f15  xorps   xmm0, xmm0
0x180122f18  mov     [rbp+57h+arg_10], 0
0x180122f1f  lea     rdx, aRedirectedkey; "RedirectedKey"
0x180122f26  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180122f2a  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x180122f2e  call    cs:__imp_RtlInitUnicodeString
0x180122f34  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180122f38  lea     rax, [rbp+57h+arg_10]
0x180122f3c  xor     r9d, r9d; KeyValueInformation
0x180122f3f  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180122f44  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180122f48  mov     [rsp+0C0h+Length], 0; Length
0x180122f50  lea     ebx, [r9+2]
0x180122f54  mov     r8d, ebx; KeyValueInformationClass
0x180122f57  call    cs:__imp_ZwQueryValueKey
0x180122f5d  mov     ecx, [rbp+57h+arg_10]; unsigned __int64
0x180122f60  test    ecx, ecx
0x180122f62  jz      loc_180123051
0x180122f68  cmp     eax, 0C0000023h
0x180122f6d  jz      short loc_180122F7A
0x180122f6f  cmp     eax, 80000005h
0x180122f74  jnz     loc_180123051
0x180122f7a  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180122f7f  mov     rdi, rax
0x180122f82  test    rax, rax
0x180122f85  jz      loc_18012304A
0x180122f8b  mov     ecx, [rbp+57h+arg_10]
0x180122f8e  lea     rax, [rbp+57h+arg_10]
0x180122f92  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180122f97  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180122f9b  mov     [rsp+0C0h+Length], ecx; Length
0x180122f9f  mov     r9, rdi; KeyValueInformation
0x180122fa2  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180122fa6  mov     r8d, ebx; KeyValueInformationClass
0x180122fa9  call    cs:__imp_ZwQueryValueKey
0x180122faf  mov     ebx, eax
0x180122fb1  test    eax, eax
0x180122fb3  js      loc_180123040
0x180122fb9  cmp     dword ptr [rdi+4], 1
0x180122fbd  jnz     short loc_180123031
0x180122fbf  xorps   xmm0, xmm0
0x180122fc2  mov     [rbp+57h+var_90], 0
0x180122fca  lea     rdx, [rdi+0Ch]; SourceString
0x180122fce  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x180122fd2  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x180122fd6  call    cs:__imp_RtlInitUnicodeString
0x180122fdc  lea     r8, [rbp+57h+var_90]
0x180122fe0  mov     ecx, r14d; DesiredAccess
0x180122fe3  lea     rdx, [rbp+57h+SourceString]
0x180122fe7  call    OpenRegistryKey
0x180122fec  mov     ebx, eax
0x180122fee  test    eax, eax
0x180122ff0  js      short loc_180123040
0x180122ff2  mov     eax, 0AAh
0x180122ff7  lea     rdx, word_18039E950
0x180122ffe  xorps   xmm0, xmm0
0x180123001  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180123005  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x180123009  mov     [rbp+57h+DestinationString.Buffer], rdx
0x18012300d  cmp     ax, [rbp+57h+SourceString.Length]
0x180123011  jb      short loc_18012302B
0x180123013  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180123017  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18012301b  call    cs:__imp_RtlCopyUnicodeString
0x180123021  mov     cs:dword_18039F244, 1
0x18012302b  mov     rax, [rbp+57h+var_90]
0x18012302f  jmp     short loc_18012303D
0x180123031  mov     rax, [rbp+57h+KeyHandle]
0x180123035  mov     [rbp+57h+KeyHandle], 0
0x18012303d  mov     [rsi], rax
0x180123040  mov     rcx, rdi; penv
0x180123043  call    FreeEnvironmentStringsW
0x180123048  jmp     short loc_18012309B
0x18012304a  mov     ebx, 0C0000017h
0x18012304f  jmp     short loc_18012309B
0x180123051  mov     eax, 0AAh
0x180123056  lea     rdx, word_18039E950
0x18012305d  xorps   xmm0, xmm0
0x180123060  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180123064  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x180123068  mov     [rbp+57h+DestinationString.Buffer], rdx
0x18012306c  cmp     ax, [rbp+57h+var_78.Length]
0x180123070  jb      short loc_18012308A
0x180123072  lea     rdx, [rbp+57h+var_78]; SourceString
0x180123076  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18012307a  call    cs:__imp_RtlCopyUnicodeString
0x180123080  mov     cs:dword_18039F244, 1
0x18012308a  mov     rax, [rbp+57h+KeyHandle]
0x18012308e  xor     ebx, ebx
0x180123090  mov     [rsi], rax
0x180123093  mov     [rbp+57h+KeyHandle], 0
0x18012309b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18012309f  test    rcx, rcx
0x1801230a2  jz      short loc_1801230AA
0x1801230a4  call    cs:__imp_ZwClose
0x1801230aa  lea     r11, [rsp+0C0h+var_10]
0x1801230b2  mov     eax, ebx
0x1801230b4  mov     rbx, [r11+20h]
0x1801230b8  mov     rsi, [r11+28h]
0x1801230bc  mov     rsp, r11
0x1801230bf  pop     r14
0x1801230c1  pop     rdi
0x1801230c2  pop     rbp
0x1801230c3  retn
```
