# ReadSettingsCache

- ea: `0x1800eea70`
- end: `0x1800eed05`
- name: `ReadSettingsCache`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011b90`

## callees

- `0x1800eea70`
- `0x1800eed0c`
- `0x1800fad3c`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800eec89`
- `ntdll!RtlInitUnicodeString` at `0x1800eec89`
- `ntdll!NtOpenKey` at `0x1800eeaeb`
- `ntdll!NtOpenKey` at `0x1800eec19`
- `ntdll!NtOpenKey` at `0x1800eecae`
- `ntdll!NtOpenKey` at `0x1800eeaeb`
- `ntdll!NtOpenKey` at `0x1800eec19`
- `ntdll!NtOpenKey` at `0x1800eecae`
- `ntdll!NtQueryValueKey` at `0x1800eeb41`
- `ntdll!NtQueryValueKey` at `0x1800eeba5`
- `ntdll!NtQueryValueKey` at `0x1800eeb41`
- `ntdll!NtQueryValueKey` at `0x1800eeba5`
- `ntdll!wcsncpy_s` at `0x1800eecde`
- `ntdll!wcsncpy_s` at `0x180194cad`
- `ntdll!wcsncpy_s` at `0x180194cdd`
- `ntdll!wcsncpy_s` at `0x180194d3e`
- `ntdll!wcsncpy_s` at `0x180194d6e`
- `ntdll!wcsncpy_s` at `0x180194de4`
- `ntdll!wcsncpy_s` at `0x180194e45`
- `ntdll!wcsncpy_s` at `0x1800eecde`
- `ntdll!wcsncpy_s` at `0x180194cad`
- `ntdll!wcsncpy_s` at `0x180194cdd`
- `ntdll!wcsncpy_s` at `0x180194d3e`
- `ntdll!wcsncpy_s` at `0x180194d6e`
- `ntdll!wcsncpy_s` at `0x180194de4`
- `ntdll!wcsncpy_s` at `0x180194e45`
- `ntdll!NtClose` at `0x1800eec43`
- `ntdll!NtClose` at `0x1800eec57`
- `ntdll!NtClose` at `0x180194d89`
- `ntdll!NtClose` at `0x180194e60`
- `ntdll!NtClose` at `0x1800eec43`
- `ntdll!NtClose` at `0x1800eec57`
- `ntdll!NtClose` at `0x180194d89`
- `ntdll!NtClose` at `0x180194e60`

## pseudocode

```c
int __fastcall ReadSettingsCache(wchar_t *a1, void *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  wchar_t v5; // ax
  const WCHAR *v6; // rdx
  errno_t v7; // eax
  rsize_t v8; // rcx
  errno_t v9; // eax
  rsize_t v10; // rcx
  int StringValue; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v14; // [rsp+38h] [rbp-C8h]
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp-70h] BYREF
  int v20; // [rsp+94h] [rbp-6Ch]
  wchar_t Source[90]; // [rsp+9Ch] [rbp-64h] BYREF

  ObjectAttributes.RootDirectory = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  KeyHandle = 0;
  Handle = 0;
  v14 = 0;
  ResultLength = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&ExplicitSettingsKey;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  LODWORD(v3) = NtOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( (int)v3 >= 0 )
  {
    if ( NtQueryValueKey(
           KeyHandle,
           (PUNICODE_STRING)&Currencies,
           KeyValuePartialInformation,
           KeyValueInformation,
           0xB6u,
           &ResultLength) >= 0 )
    {
      v14 = Source;
      if ( v20 == 1 && (ResultLength & 1) == 0 && ResultLength > 0xE )
      {
        ResultLength = ((ResultLength - 12) >> 1) - 1;
        if ( !Source[ResultLength] && ResultLength >= 3 && !wcsncpy_s(a1 + 622, 4u, Source, 3u) )
          a1[621] = 3;
      }
    }
    if ( NtQueryValueKey(
           KeyHandle,
           (PUNICODE_STRING)&Calendar,
           KeyValuePartialInformation,
           KeyValueInformation,
           0xB6u,
           &ResultLength) >= 0 )
    {
      v14 = Source;
      if ( v20 == 1 && (ResultLength & 1) == 0 && ResultLength > 0xE )
      {
        v4 = ((ResultLength - 12) >> 1) - 1;
        ResultLength = v4;
        if ( (unsigned int)v4 >= 4 && !Source[v4] )
        {
          v5 = CalendarIdFromString(Source);
          if ( v5 )
            a1[620] = v5;
        }
      }
    }
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&GregorianKey;
    ObjectAttributes.RootDirectory = KeyHandle;
    if ( NtOpenKey(&Handle, 1u, &ObjectAttributes) >= 0 )
    {
      if ( (unsigned int)QueryStringValue(Handle, &ShortDate, KeyValueInformation) && ResultLength - 2 <= 0x4D )
      {
        v7 = wcsncpy_s(a1 + 627, 0x50u, v14, ResultLength);
        v8 = ResultLength;
        if ( !v7 )
          a1[626] = ResultLength;
        if ( a1[620] == 1 && !wcsncpy_s(a1 + 352, 0x50u, v14, v8) )
          a1[351] = ResultLength;
      }
      if ( (unsigned int)QueryStringValue(Handle, &LongDate, KeyValueInformation) && ResultLength - 3 <= 0x4C )
      {
        v9 = wcsncpy_s(a1 + 708, 0x50u, v14, ResultLength);
        v10 = ResultLength;
        if ( !v9 )
          a1[707] = ResultLength;
        if ( a1[620] == 1 && !wcsncpy_s(a1 + 514, 0x50u, v14, v10) )
          a1[513] = ResultLength;
      }
      NtClose(Handle);
      Handle = 0;
    }
    v3 = a1[620];
    if ( (_WORD)v3 != 1 )
    {
      if ( (unsigned int)v3 >= 0x18 )
      {
        v6 = &word_180290A38;
      }
      else
      {
        _mm_lfence();
        v6 = (const WCHAR *)*((_QWORD *)&CalendarNames + v3);
      }
      if ( *v6 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, v6);
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = KeyHandle;
        LODWORD(v3) = NtOpenKey(&Handle, 1u, &ObjectAttributes);
        if ( (int)v3 >= 0 )
        {
          StringValue = QueryStringValue(Handle, &ShortDate, KeyValueInformation);
          if ( StringValue && ResultLength - 2 <= 0x4D && !wcsncpy_s(a1 + 352, 0x50u, v14, ResultLength) )
            a1[351] = ResultLength;
          if ( (unsigned int)QueryStringValue(Handle, &LongDate, KeyValueInformation)
            && ResultLength - 3 <= 0x4C
            && !wcsncpy_s(a1 + 514, 0x50u, v14, ResultLength) )
          {
            a1[513] = ResultLength;
          }
          LODWORD(v3) = NtClose(Handle);
          Handle = 0;
        }
      }
    }
    if ( KeyHandle )
      LODWORD(v3) = NtClose(KeyHandle);
    if ( Handle )
      LODWORD(v3) = NtClose(Handle);
  }
  return v3;
}

```

## disassembly

```asm
0x1800eea70  mov     [rsp-8+arg_10], rbx
0x1800eea75  mov     [rsp-8+arg_18], rsi
0x1800eea7a  push    rbp
0x1800eea7b  push    rdi
0x1800eea7c  push    r14
0x1800eea7e  lea     rbp, [rsp-60h]
0x1800eea83  sub     rsp, 160h
0x1800eea8a  mov     rax, cs:__security_cookie
0x1800eea91  xor     rax, rsp
0x1800eea94  mov     [rbp+70h+var_20], rax
0x1800eea98  xor     edi, edi
0x1800eea9a  mov     [rsp+170h+ObjectAttributes.RootDirectory], rdx
0x1800eea9f  mov     rbx, rcx
0x1800eeaa2  mov     qword ptr [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1800eeaab  lea     rax, ExplicitSettingsKey
0x1800eeab2  mov     qword ptr [rsp+170h+ObjectAttributes.Attributes], 40h ; '@'
0x1800eeabb  xorps   xmm0, xmm0
0x1800eeabe  mov     [rsp+170h+KeyHandle], rdi
0x1800eeac3  lea     esi, [rdi+1]
0x1800eeac6  mov     [rsp+170h+Handle], rdi
0x1800eeacb  mov     edx, esi; DesiredAccess
0x1800eeacd  mov     [rsp+170h+var_138], rdi
0x1800eead2  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800eead7  mov     [rsp+170h+var_140], edi
0x1800eeadb  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800eeae0  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x1800eeae5  movdqu  xmmword ptr [rsp+170h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800eeaeb  call    cs:__imp_NtOpenKey
0x1800eeaf1  test    eax, eax
0x1800eeaf3  jns     short loc_1800EEB19
0x1800eeaf5  mov     rcx, [rbp+70h+var_20]
0x1800eeaf9  xor     rcx, rsp; StackCookie
0x1800eeafc  call    __security_check_cookie
0x1800eeb01  lea     r11, [rsp+170h+var_10]
0x1800eeb09  mov     rbx, [r11+30h]
0x1800eeb0d  mov     rsi, [r11+38h]
0x1800eeb11  mov     rsp, r11
0x1800eeb14  pop     r14
0x1800eeb16  pop     rdi
0x1800eeb17  pop     rbp
0x1800eeb18  retn
0x1800eeb19  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800eeb1e  lea     rax, [rsp+170h+var_140]
0x1800eeb23  mov     [rsp+170h+ResultLength], rax; ResultLength
0x1800eeb28  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x1800eeb2c  mov     r8d, 2; KeyValueInformationClass
0x1800eeb32  mov     [rsp+170h+Length], 0B6h; Length
0x1800eeb3a  lea     rdx, Currencies; ValueName
0x1800eeb41  call    cs:__imp_NtQueryValueKey
0x1800eeb47  test    eax, eax
0x1800eeb49  js      short loc_1800EEB7D
0x1800eeb4b  lea     rax, [rbp+70h+Source]
0x1800eeb4f  mov     [rsp+170h+var_138], rax
0x1800eeb54  cmp     [rbp+70h+var_DC], esi
0x1800eeb57  jnz     short loc_1800EEB7D
0x1800eeb59  mov     ecx, [rsp+170h+var_140]
0x1800eeb5d  test    sil, cl
0x1800eeb60  jnz     short loc_1800EEB7D
0x1800eeb62  cmp     ecx, 0Eh
0x1800eeb65  jbe     short loc_1800EEB7D
0x1800eeb67  add     ecx, 0FFFFFFF4h
0x1800eeb6a  shr     ecx, 1
0x1800eeb6c  sub     ecx, esi
0x1800eeb6e  mov     [rsp+170h+var_140], ecx
0x1800eeb72  cmp     [rbp+rcx*2+70h+Source], di
0x1800eeb77  jz      loc_1800EECBD
0x1800eeb7d  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800eeb82  lea     rax, [rsp+170h+var_140]
0x1800eeb87  mov     [rsp+170h+ResultLength], rax; ResultLength
0x1800eeb8c  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x1800eeb90  mov     r8d, 2; KeyValueInformationClass
0x1800eeb96  mov     [rsp+170h+Length], 0B6h; Length
0x1800eeb9e  lea     rdx, Calendar; ValueName
0x1800eeba5  call    cs:__imp_NtQueryValueKey
0x1800eebab  test    eax, eax
0x1800eebad  js      short loc_1800EEBF7
0x1800eebaf  lea     rax, [rbp+70h+Source]
0x1800eebb3  mov     [rsp+170h+var_138], rax
0x1800eebb8  cmp     [rbp+70h+var_DC], esi
0x1800eebbb  jnz     short loc_1800EEBF7
0x1800eebbd  mov     ecx, [rsp+170h+var_140]
0x1800eebc1  test    sil, cl
0x1800eebc4  jnz     short loc_1800EEBF7
0x1800eebc6  cmp     ecx, 0Eh
0x1800eebc9  jbe     short loc_1800EEBF7
0x1800eebcb  add     ecx, 0FFFFFFF4h
0x1800eebce  shr     ecx, 1
0x1800eebd0  sub     ecx, esi
0x1800eebd2  mov     [rsp+170h+var_140], ecx
0x1800eebd6  cmp     ecx, 4
0x1800eebd9  jb      short loc_1800EEBF7
0x1800eebdb  cmp     [rbp+rcx*2+70h+Source], di
0x1800eebe0  jnz     short loc_1800EEBF7
0x1800eebe2  lea     rcx, [rbp+70h+Source]; String2
0x1800eebe6  call    CalendarIdFromString
0x1800eebeb  cmp     ax, si
0x1800eebee  jb      short loc_1800EEBF7
0x1800eebf0  mov     [rbx+4D8h], ax
0x1800eebf7  lea     rax, GregorianKey
0x1800eebfe  mov     edx, esi; DesiredAccess
0x1800eec00  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x1800eec05  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800eec0a  mov     rax, [rsp+170h+KeyHandle]
0x1800eec0f  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x1800eec14  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x1800eec19  call    cs:__imp_NtOpenKey
0x1800eec1f  mov     r14d, 50h ; 'P'
0x1800eec25  test    eax, eax
0x1800eec27  jns     loc_180194C62
0x1800eec2d  movzx   eax, word ptr [rbx+4D8h]
0x1800eec34  cmp     ax, si
0x1800eec37  jnz     short loc_1800EEC62
0x1800eec39  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x1800eec3e  test    rcx, rcx
0x1800eec41  jz      short loc_1800EEC49
0x1800eec43  call    cs:__imp_NtClose
0x1800eec49  mov     rcx, [rsp+170h+Handle]; Handle
0x1800eec4e  test    rcx, rcx
0x1800eec51  jz      loc_1800EEAF5
0x1800eec57  call    cs:__imp_NtClose
0x1800eec5d  jmp     loc_1800EEAF5
0x1800eec62  cmp     eax, 18h
0x1800eec65  jnb     loc_1800EECF9
0x1800eec6b  lfence
0x1800eec6e  lea     rdx, CalendarNames
0x1800eec75  mov     rdx, [rdx+rax*8]; SourceString
0x1800eec79  cmp     [rdx], di
0x1800eec7c  jz      short loc_1800EEC39
0x1800eec7e  xorps   xmm0, xmm0
0x1800eec81  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x1800eec85  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x1800eec89  call    cs:__imp_RtlInitUnicodeString
0x1800eec8f  lea     rax, [rbp+70h+DestinationString]
0x1800eec93  mov     edx, esi; DesiredAccess
0x1800eec95  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x1800eec9a  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800eec9f  mov     rax, [rsp+170h+KeyHandle]
0x1800eeca4  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x1800eeca9  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x1800eecae  call    cs:__imp_NtOpenKey
0x1800eecb4  test    eax, eax
0x1800eecb6  js      short loc_1800EEC39
0x1800eecb8  jmp     loc_180194D99
0x1800eecbd  mov     r14d, 3
0x1800eecc3  cmp     ecx, r14d
0x1800eecc6  jb      loc_1800EEB7D
0x1800eeccc  lea     rcx, [rbx+4DCh]; Destination
0x1800eecd3  mov     r9d, r14d; MaxCount
0x1800eecd6  lea     r8, [rbp+70h+Source]; Source
0x1800eecda  lea     edx, [r14+1]; SizeInWords
0x1800eecde  call    cs:__imp_wcsncpy_s
0x1800eece4  test    eax, eax
0x1800eece6  jnz     loc_1800EEB7D
0x1800eecec  mov     [rbx+4DAh], r14w
0x1800eecf4  jmp     loc_1800EEB7D
0x1800eecf9  lea     rdx, word_180290A38
0x1800eed00  jmp     loc_1800EEC79
0x180194c62  mov     rcx, [rsp+170h+Handle]
0x180194c67  lea     rax, [rsp+170h+var_140]
0x180194c6c  mov     [rsp+170h+ResultLength], rax
0x180194c71  lea     r8, [rbp+70h+KeyValueInformation]
0x180194c75  lea     rax, [rsp+170h+var_138]
0x180194c7a  lea     rdx, ShortDate
0x180194c81  mov     qword ptr [rsp+170h+Length], rax
0x180194c86  call    QueryStringValue
0x180194c8b  test    eax, eax
0x180194c8d  jz      short loc_180194CF3
0x180194c8f  mov     ecx, [rsp+170h+var_140]
0x180194c93  lea     eax, [rcx-2]
0x180194c96  cmp     eax, 4Dh ; 'M'
0x180194c99  ja      short loc_180194CF3
0x180194c9b  mov     r8, [rsp+170h+var_138]; Source
0x180194ca0  mov     r9d, ecx; MaxCount
0x180194ca3  lea     rcx, [rbx+4E6h]; Destination
0x180194caa  mov     rdx, r14; SizeInWords
0x180194cad  call    cs:__imp_wcsncpy_s
0x180194cb3  mov     ecx, [rsp+170h+var_140]
0x180194cb7  test    eax, eax
0x180194cb9  jnz     short loc_180194CC2
0x180194cbb  mov     [rbx+4E4h], cx
0x180194cc2  cmp     [rbx+4D8h], si
0x180194cc9  jnz     short loc_180194CF3
0x180194ccb  mov     r8, [rsp+170h+var_138]; Source
0x180194cd0  mov     r9, rcx; MaxCount
0x180194cd3  lea     rcx, [rbx+2C0h]; Destination
0x180194cda  mov     rdx, r14; SizeInWords
0x180194cdd  call    cs:__imp_wcsncpy_s
0x180194ce3  test    eax, eax
0x180194ce5  jnz     short loc_180194CF3
0x180194ce7  movzx   eax, word ptr [rsp+170h+var_140]
0x180194cec  mov     [rbx+2BEh], ax
0x180194cf3  mov     rcx, [rsp+170h+Handle]
0x180194cf8  lea     rax, [rsp+170h+var_140]
0x180194cfd  mov     [rsp+170h+ResultLength], rax
0x180194d02  lea     r8, [rbp+70h+KeyValueInformation]
0x180194d06  lea     rax, [rsp+170h+var_138]
0x180194d0b  lea     rdx, LongDate
0x180194d12  mov     qword ptr [rsp+170h+Length], rax
0x180194d17  call    QueryStringValue
0x180194d1c  test    eax, eax
0x180194d1e  jz      short loc_180194D84
0x180194d20  mov     ecx, [rsp+170h+var_140]
0x180194d24  lea     eax, [rcx-3]
0x180194d27  cmp     eax, 4Ch ; 'L'
0x180194d2a  ja      short loc_180194D84
0x180194d2c  mov     r8, [rsp+170h+var_138]; Source
0x180194d31  mov     r9d, ecx; MaxCount
0x180194d34  lea     rcx, [rbx+588h]; Destination
0x180194d3b  mov     rdx, r14; SizeInWords
0x180194d3e  call    cs:__imp_wcsncpy_s
0x180194d44  mov     ecx, [rsp+170h+var_140]
0x180194d48  test    eax, eax
0x180194d4a  jnz     short loc_180194D53
0x180194d4c  mov     [rbx+586h], cx
0x180194d53  cmp     [rbx+4D8h], si
0x180194d5a  jnz     short loc_180194D84
0x180194d5c  mov     r8, [rsp+170h+var_138]; Source
0x180194d61  mov     r9, rcx; MaxCount
0x180194d64  lea     rcx, [rbx+404h]; Destination
0x180194d6b  mov     rdx, r14; SizeInWords
0x180194d6e  call    cs:__imp_wcsncpy_s
0x180194d74  test    eax, eax
0x180194d76  jnz     short loc_180194D84
0x180194d78  movzx   eax, word ptr [rsp+170h+var_140]
0x180194d7d  mov     [rbx+402h], ax
0x180194d84  mov     rcx, [rsp+170h+Handle]; Handle
0x180194d89  call    cs:__imp_NtClose
0x180194d8f  mov     [rsp+170h+Handle], rdi
0x180194d94  jmp     loc_1800EEC2D
0x180194d99  mov     rcx, [rsp+170h+Handle]
0x180194d9e  lea     rax, [rsp+170h+var_140]
0x180194da3  mov     [rsp+170h+ResultLength], rax
0x180194da8  lea     r8, [rbp+70h+KeyValueInformation]
0x180194dac  lea     rax, [rsp+170h+var_138]
0x180194db1  lea     rdx, ShortDate
0x180194db8  mov     qword ptr [rsp+170h+Length], rax
0x180194dbd  call    QueryStringValue
0x180194dc2  test    eax, eax
0x180194dc4  jz      short loc_180194DFA
0x180194dc6  mov     ecx, [rsp+170h+var_140]
0x180194dca  lea     eax, [rcx-2]
0x180194dcd  cmp     eax, 4Dh ; 'M'
0x180194dd0  ja      short loc_180194DFA
0x180194dd2  mov     r8, [rsp+170h+var_138]; Source
0x180194dd7  mov     r9d, ecx; MaxCount
0x180194dda  lea     rcx, [rbx+2C0h]; Destination
0x180194de1  mov     rdx, r14; SizeInWords
0x180194de4  call    cs:__imp_wcsncpy_s
0x180194dea  test    eax, eax
0x180194dec  jnz     short loc_180194DFA
0x180194dee  movzx   eax, word ptr [rsp+170h+var_140]
0x180194df3  mov     [rbx+2BEh], ax
0x180194dfa  mov     rcx, [rsp+170h+Handle]
0x180194dff  lea     rax, [rsp+170h+var_140]
0x180194e04  mov     [rsp+170h+ResultLength], rax
0x180194e09  lea     r8, [rbp+70h+KeyValueInformation]
0x180194e0d  lea     rax, [rsp+170h+var_138]
0x180194e12  lea     rdx, LongDate
0x180194e19  mov     qword ptr [rsp+170h+Length], rax
0x180194e1e  call    QueryStringValue
0x180194e23  test    eax, eax
0x180194e25  jz      short loc_180194E5B
0x180194e27  mov     ecx, [rsp+170h+var_140]
0x180194e2b  lea     eax, [rcx-3]
0x180194e2e  cmp     eax, 4Ch ; 'L'
0x180194e31  ja      short loc_180194E5B
0x180194e33  mov     r8, [rsp+170h+var_138]; Source
0x180194e38  mov     r9d, ecx; MaxCount
0x180194e3b  lea     rcx, [rbx+404h]; Destination
0x180194e42  mov     rdx, r14; SizeInWords
0x180194e45  call    cs:__imp_wcsncpy_s
0x180194e4b  test    eax, eax
0x180194e4d  jnz     short loc_180194E5B
0x180194e4f  movzx   eax, word ptr [rsp+170h+var_140]
0x180194e54  mov     [rbx+402h], ax
0x180194e5b  mov     rcx, [rsp+170h+Handle]; Handle
0x180194e60  call    cs:__imp_NtClose
0x180194e66  mov     [rsp+170h+Handle], rdi
0x180194e6b  jmp     loc_1800EEC39
```
