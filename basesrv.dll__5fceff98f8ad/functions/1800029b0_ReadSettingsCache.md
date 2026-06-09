# ReadSettingsCache

- ea: `0x1800029b0`
- end: `0x180002ea0`
- name: `ReadSettingsCache`
- size: `1264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800024b0`

## callees

- `0x1800029b0`
- `0x180002eb0`
- `0x180006ae0`
- `0x18000db40`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x180002ac1`
- `ntdll!wcsncpy_s` at `0x180002be3`
- `ntdll!wcsncpy_s` at `0x180002c1a`
- `ntdll!wcsncpy_s` at `0x180002c86`
- `ntdll!wcsncpy_s` at `0x180002cbd`
- `ntdll!wcsncpy_s` at `0x180002dc1`
- `ntdll!wcsncpy_s` at `0x180002e2a`
- `ntdll!wcsncpy_s` at `0x180002ac1`
- `ntdll!wcsncpy_s` at `0x180002be3`
- `ntdll!wcsncpy_s` at `0x180002c1a`
- `ntdll!wcsncpy_s` at `0x180002c86`
- `ntdll!wcsncpy_s` at `0x180002cbd`
- `ntdll!wcsncpy_s` at `0x180002dc1`
- `ntdll!wcsncpy_s` at `0x180002e2a`
- `ntdll!NtOpenKey` at `0x180002a21`
- `ntdll!NtOpenKey` at `0x180002b7f`
- `ntdll!NtOpenKey` at `0x180002d60`
- `ntdll!NtOpenKey` at `0x180002a21`
- `ntdll!NtOpenKey` at `0x180002b7f`
- `ntdll!NtOpenKey` at `0x180002d60`
- `ntdll!NtQueryValueKey` at `0x180002a65`
- `ntdll!NtQueryValueKey` at `0x180002b00`
- `ntdll!NtQueryValueKey` at `0x180002a65`
- `ntdll!NtQueryValueKey` at `0x180002b00`
- `ntdll!NtClose` at `0x180002cde`
- `ntdll!NtClose` at `0x180002e4b`
- `ntdll!NtClose` at `0x180002e66`
- `ntdll!NtClose` at `0x180002e7c`
- `ntdll!NtClose` at `0x180002cde`
- `ntdll!NtClose` at `0x180002e4b`
- `ntdll!NtClose` at `0x180002e66`
- `ntdll!NtClose` at `0x180002e7c`
- `ntdll!RtlInitUnicodeString` at `0x180002d32`
- `ntdll!RtlInitUnicodeString` at `0x180002d32`

## pseudocode

```c
int __fastcall ReadSettingsCache(wchar_t *a1, void *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  wchar_t v5; // ax
  wchar_t *v6; // rdi
  errno_t v7; // eax
  rsize_t v8; // rcx
  wchar_t *v9; // rdi
  errno_t v10; // eax
  rsize_t v11; // rcx
  const WCHAR *v12; // rdx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v16; // [rsp+40h] [rbp-C0h]
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+94h] [rbp-6Ch]
  wchar_t Source[90]; // [rsp+9Ch] [rbp-64h] BYREF

  ObjectAttributes.RootDirectory = a2;
  KeyHandle = 0;
  Handle = 0;
  v16 = 0;
  ResultLength = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&ExplicitSettingsKey;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
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
      v16 = Source;
      if ( v21 == 1 && (ResultLength & 1) == 0 && ResultLength > 0xE )
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
      v16 = Source;
      if ( v21 == 1 && (ResultLength & 1) == 0 && ResultLength > 0xE )
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
        v6 = v16;
        v7 = wcsncpy_s(a1 + 627, 0x50u, v16, ResultLength);
        v8 = ResultLength;
        if ( !v7 )
          a1[626] = ResultLength;
        if ( a1[620] == 1 && !wcsncpy_s(a1 + 352, 0x50u, v6, v8) )
          a1[351] = ResultLength;
      }
      if ( (unsigned int)QueryStringValue(Handle, &LongDate, KeyValueInformation) && ResultLength - 3 <= 0x4C )
      {
        v9 = v16;
        v10 = wcsncpy_s(a1 + 708, 0x50u, v16, ResultLength);
        v11 = ResultLength;
        if ( !v10 )
          a1[707] = ResultLength;
        if ( a1[620] == 1 && !wcsncpy_s(a1 + 514, 0x50u, v9, v11) )
          a1[513] = ResultLength;
      }
      NtClose(Handle);
      Handle = 0;
    }
    v3 = a1[620];
    if ( (_DWORD)v3 != 1 && (unsigned int)v3 < 0x18 )
    {
      _mm_lfence();
      v12 = (const WCHAR *)CalendarNames[v3];
      if ( *v12 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, v12);
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = KeyHandle;
        LODWORD(v3) = NtOpenKey(&Handle, 1u, &ObjectAttributes);
        if ( (int)v3 >= 0 )
        {
          if ( (unsigned int)QueryStringValue(Handle, &ShortDate, KeyValueInformation)
            && ResultLength - 2 <= 0x4D
            && !wcsncpy_s(a1 + 352, 0x50u, v16, ResultLength) )
          {
            a1[351] = ResultLength;
          }
          if ( (unsigned int)QueryStringValue(Handle, &LongDate, KeyValueInformation)
            && ResultLength - 3 <= 0x4C
            && !wcsncpy_s(a1 + 514, 0x50u, v16, ResultLength) )
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
0x1800029b0  push    rbp
0x1800029b2  push    rbx
0x1800029b3  push    rsi
0x1800029b4  lea     rbp, [rsp-60h]
0x1800029b9  sub     rsp, 160h
0x1800029c0  mov     rax, cs:__security_cookie
0x1800029c7  xor     rax, rsp
0x1800029ca  mov     [rbp+70h+var_20], rax
0x1800029ce  xor     esi, esi
0x1800029d0  mov     [rsp+170h+ObjectAttributes.RootDirectory], rdx
0x1800029d5  mov     rbx, rcx
0x1800029d8  mov     [rsp+170h+KeyHandle], rsi
0x1800029dd  lea     rax, ExplicitSettingsKey
0x1800029e4  mov     [rsp+170h+Handle], rsi
0x1800029e9  xorps   xmm0, xmm0
0x1800029ec  mov     [rsp+170h+var_130], rsi
0x1800029f1  mov     edx, 1; DesiredAccess
0x1800029f6  mov     [rsp+170h+var_140], esi
0x1800029fa  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800029ff  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x180002a04  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180002a09  mov     qword ptr [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x180002a12  movdqu  xmmword ptr [rsp+170h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002a18  mov     qword ptr [rsp+170h+ObjectAttributes.Attributes], 40h ; '@'
0x180002a21  call    cs:__imp_NtOpenKey
0x180002a28  nop     dword ptr [rax+rax+00h]
0x180002a2d  test    eax, eax
0x180002a2f  js      loc_180002E88
0x180002a35  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180002a3a  lea     rax, [rsp+170h+var_140]
0x180002a3f  mov     [rsp+170h+ResultLength], rax; ResultLength
0x180002a44  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x180002a48  mov     r8d, 2; KeyValueInformationClass
0x180002a4e  mov     [rsp+170h+Length], 0B6h; Length
0x180002a56  lea     rdx, Currencies; ValueName
0x180002a5d  mov     [rsp+170h+arg_10], rdi
0x180002a65  call    cs:__imp_NtQueryValueKey
0x180002a6c  nop     dword ptr [rax+rax+00h]
0x180002a71  test    eax, eax
0x180002a73  js      short loc_180002AD8
0x180002a75  cmp     [rbp+70h+var_DC], 1
0x180002a79  lea     rax, [rbp+70h+Source]
0x180002a7d  mov     [rsp+170h+var_130], rax
0x180002a82  jnz     short loc_180002AD8
0x180002a84  mov     ecx, [rsp+170h+var_140]
0x180002a88  test    cl, 1
0x180002a8b  jnz     short loc_180002AD8
0x180002a8d  cmp     ecx, 0Eh
0x180002a90  jbe     short loc_180002AD8
0x180002a92  add     ecx, 0FFFFFFF4h
0x180002a95  shr     ecx, 1
0x180002a97  dec     ecx
0x180002a99  mov     [rsp+170h+var_140], ecx
0x180002a9d  cmp     [rbp+rcx*2+70h+Source], si
0x180002aa2  jnz     short loc_180002AD8
0x180002aa4  cmp     ecx, 3
0x180002aa7  jb      short loc_180002AD8
0x180002aa9  mov     edi, 3
0x180002aae  lea     rcx, [rbx+4DCh]; Destination
0x180002ab5  mov     r9d, edi; MaxCount
0x180002ab8  lea     r8, [rbp+70h+Source]; Source
0x180002abc  mov     edx, 4; SizeInWords
0x180002ac1  call    cs:__imp_wcsncpy_s
0x180002ac8  nop     dword ptr [rax+rax+00h]
0x180002acd  test    eax, eax
0x180002acf  jnz     short loc_180002AD8
0x180002ad1  mov     [rbx+4DAh], di
0x180002ad8  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180002add  lea     rax, [rsp+170h+var_140]
0x180002ae2  mov     [rsp+170h+ResultLength], rax; ResultLength
0x180002ae7  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x180002aeb  mov     r8d, 2; KeyValueInformationClass
0x180002af1  mov     [rsp+170h+Length], 0B6h; Length
0x180002af9  lea     rdx, Calendar; ValueName
0x180002b00  call    cs:__imp_NtQueryValueKey
0x180002b07  nop     dword ptr [rax+rax+00h]
0x180002b0c  test    eax, eax
0x180002b0e  js      short loc_180002B5A
0x180002b10  cmp     [rbp+70h+var_DC], 1
0x180002b14  lea     rax, [rbp+70h+Source]
0x180002b18  mov     [rsp+170h+var_130], rax
0x180002b1d  jnz     short loc_180002B5A
0x180002b1f  mov     ecx, [rsp+170h+var_140]
0x180002b23  test    cl, 1
0x180002b26  jnz     short loc_180002B5A
0x180002b28  cmp     ecx, 0Eh
0x180002b2b  jbe     short loc_180002B5A
0x180002b2d  add     ecx, 0FFFFFFF4h
0x180002b30  shr     ecx, 1
0x180002b32  dec     ecx
0x180002b34  mov     [rsp+170h+var_140], ecx
0x180002b38  cmp     ecx, 4
0x180002b3b  jb      short loc_180002B5A
0x180002b3d  cmp     [rbp+rcx*2+70h+Source], si
0x180002b42  jnz     short loc_180002B5A
0x180002b44  lea     rcx, [rbp+70h+Source]; String2
0x180002b48  call    CalendarIdFromString
0x180002b4d  cmp     ax, 1
0x180002b51  jb      short loc_180002B5A
0x180002b53  mov     [rbx+4D8h], ax
0x180002b5a  lea     rax, GregorianKey
0x180002b61  mov     edx, 1; DesiredAccess
0x180002b66  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x180002b6b  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180002b70  mov     rax, [rsp+170h+KeyHandle]
0x180002b75  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x180002b7a  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x180002b7f  call    cs:__imp_NtOpenKey
0x180002b86  nop     dword ptr [rax+rax+00h]
0x180002b8b  test    eax, eax
0x180002b8d  js      loc_180002CEF
0x180002b93  mov     rcx, [rsp+170h+Handle]
0x180002b98  lea     rax, [rsp+170h+var_140]
0x180002b9d  mov     [rsp+170h+ResultLength], rax
0x180002ba2  lea     r8, [rbp+70h+KeyValueInformation]
0x180002ba6  lea     rax, [rsp+170h+var_130]
0x180002bab  lea     rdx, ShortDate
0x180002bb2  mov     qword ptr [rsp+170h+Length], rax
0x180002bb7  call    QueryStringValue
0x180002bbc  test    eax, eax
0x180002bbe  jz      short loc_180002C36
0x180002bc0  mov     ecx, [rsp+170h+var_140]
0x180002bc4  lea     eax, [rcx-2]
0x180002bc7  cmp     eax, 4Dh ; 'M'
0x180002bca  ja      short loc_180002C36
0x180002bcc  mov     rdi, [rsp+170h+var_130]
0x180002bd1  mov     r9d, ecx; MaxCount
0x180002bd4  mov     r8, rdi; Source
0x180002bd7  lea     rcx, [rbx+4E6h]; Destination
0x180002bde  mov     edx, 50h ; 'P'; SizeInWords
0x180002be3  call    cs:__imp_wcsncpy_s
0x180002bea  nop     dword ptr [rax+rax+00h]
0x180002bef  mov     ecx, [rsp+170h+var_140]
0x180002bf3  test    eax, eax
0x180002bf5  jnz     short loc_180002BFE
0x180002bf7  mov     [rbx+4E4h], cx
0x180002bfe  cmp     word ptr [rbx+4D8h], 1
0x180002c06  jnz     short loc_180002C36
0x180002c08  mov     r9, rcx; MaxCount
0x180002c0b  mov     r8, rdi; Source
0x180002c0e  lea     rcx, [rbx+2C0h]; Destination
0x180002c15  mov     edx, 50h ; 'P'; SizeInWords
0x180002c1a  call    cs:__imp_wcsncpy_s
0x180002c21  nop     dword ptr [rax+rax+00h]
0x180002c26  test    eax, eax
0x180002c28  jnz     short loc_180002C36
0x180002c2a  movzx   eax, word ptr [rsp+170h+var_140]
0x180002c2f  mov     [rbx+2BEh], ax
0x180002c36  mov     rcx, [rsp+170h+Handle]
0x180002c3b  lea     rax, [rsp+170h+var_140]
0x180002c40  mov     [rsp+170h+ResultLength], rax
0x180002c45  lea     r8, [rbp+70h+KeyValueInformation]
0x180002c49  lea     rax, [rsp+170h+var_130]
0x180002c4e  lea     rdx, LongDate
0x180002c55  mov     qword ptr [rsp+170h+Length], rax
0x180002c5a  call    QueryStringValue
0x180002c5f  test    eax, eax
0x180002c61  jz      short loc_180002CD9
0x180002c63  mov     ecx, [rsp+170h+var_140]
0x180002c67  lea     eax, [rcx-3]
0x180002c6a  cmp     eax, 4Ch ; 'L'
0x180002c6d  ja      short loc_180002CD9
0x180002c6f  mov     rdi, [rsp+170h+var_130]
0x180002c74  mov     r9d, ecx; MaxCount
0x180002c77  mov     r8, rdi; Source
0x180002c7a  lea     rcx, [rbx+588h]; Destination
0x180002c81  mov     edx, 50h ; 'P'; SizeInWords
0x180002c86  call    cs:__imp_wcsncpy_s
0x180002c8d  nop     dword ptr [rax+rax+00h]
0x180002c92  mov     ecx, [rsp+170h+var_140]
0x180002c96  test    eax, eax
0x180002c98  jnz     short loc_180002CA1
0x180002c9a  mov     [rbx+586h], cx
0x180002ca1  cmp     word ptr [rbx+4D8h], 1
0x180002ca9  jnz     short loc_180002CD9
0x180002cab  mov     r9, rcx; MaxCount
0x180002cae  mov     r8, rdi; Source
0x180002cb1  lea     rcx, [rbx+404h]; Destination
0x180002cb8  mov     edx, 50h ; 'P'; SizeInWords
0x180002cbd  call    cs:__imp_wcsncpy_s
0x180002cc4  nop     dword ptr [rax+rax+00h]
0x180002cc9  test    eax, eax
0x180002ccb  jnz     short loc_180002CD9
0x180002ccd  movzx   eax, word ptr [rsp+170h+var_140]
0x180002cd2  mov     [rbx+402h], ax
0x180002cd9  mov     rcx, [rsp+170h+Handle]; Handle
0x180002cde  call    cs:__imp_NtClose
0x180002ce5  nop     dword ptr [rax+rax+00h]
0x180002cea  mov     [rsp+170h+Handle], rsi
0x180002cef  movzx   eax, word ptr [rbx+4D8h]
0x180002cf6  mov     rdi, [rsp+170h+arg_10]
0x180002cfe  cmp     eax, 1
0x180002d01  jz      loc_180002E5C
0x180002d07  cmp     eax, 18h
0x180002d0a  jnb     loc_180002E5C
0x180002d10  lfence
0x180002d13  lea     rdx, CalendarNames
0x180002d1a  mov     rdx, [rdx+rax*8]; SourceString
0x180002d1e  cmp     [rdx], si
0x180002d21  jz      loc_180002E5C
0x180002d27  xorps   xmm0, xmm0
0x180002d2a  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x180002d2e  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x180002d32  call    cs:__imp_RtlInitUnicodeString
0x180002d39  nop     dword ptr [rax+rax+00h]
0x180002d3e  lea     rax, [rbp+70h+DestinationString]
0x180002d42  mov     edx, 1; DesiredAccess
0x180002d47  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x180002d4c  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180002d51  mov     rax, [rsp+170h+KeyHandle]
0x180002d56  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x180002d5b  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x180002d60  call    cs:__imp_NtOpenKey
0x180002d67  nop     dword ptr [rax+rax+00h]
0x180002d6c  test    eax, eax
0x180002d6e  js      loc_180002E5C
0x180002d74  mov     rcx, [rsp+170h+Handle]
0x180002d79  lea     rax, [rsp+170h+var_140]
0x180002d7e  mov     [rsp+170h+ResultLength], rax
0x180002d83  lea     r8, [rbp+70h+KeyValueInformation]
0x180002d87  lea     rax, [rsp+170h+var_130]
0x180002d8c  lea     rdx, ShortDate
0x180002d93  mov     qword ptr [rsp+170h+Length], rax
0x180002d98  call    QueryStringValue
0x180002d9d  test    eax, eax
0x180002d9f  jz      short loc_180002DDD
0x180002da1  mov     ecx, [rsp+170h+var_140]
0x180002da5  lea     eax, [rcx-2]
0x180002da8  cmp     eax, 4Dh ; 'M'
0x180002dab  ja      short loc_180002DDD
0x180002dad  mov     r8, [rsp+170h+var_130]; Source
0x180002db2  mov     r9d, ecx; MaxCount
0x180002db5  lea     rcx, [rbx+2C0h]; Destination
0x180002dbc  mov     edx, 50h ; 'P'; SizeInWords
0x180002dc1  call    cs:__imp_wcsncpy_s
0x180002dc8  nop     dword ptr [rax+rax+00h]
0x180002dcd  test    eax, eax
0x180002dcf  jnz     short loc_180002DDD
0x180002dd1  movzx   eax, word ptr [rsp+170h+var_140]
0x180002dd6  mov     [rbx+2BEh], ax
0x180002ddd  mov     rcx, [rsp+170h+Handle]
0x180002de2  lea     rax, [rsp+170h+var_140]
0x180002de7  mov     [rsp+170h+ResultLength], rax
0x180002dec  lea     r8, [rbp+70h+KeyValueInformation]
0x180002df0  lea     rax, [rsp+170h+var_130]
0x180002df5  lea     rdx, LongDate
0x180002dfc  mov     qword ptr [rsp+170h+Length], rax
0x180002e01  call    QueryStringValue
0x180002e06  test    eax, eax
0x180002e08  jz      short loc_180002E46
0x180002e0a  mov     ecx, [rsp+170h+var_140]
0x180002e0e  lea     eax, [rcx-3]
0x180002e11  cmp     eax, 4Ch ; 'L'
0x180002e14  ja      short loc_180002E46
0x180002e16  mov     r8, [rsp+170h+var_130]; Source
0x180002e1b  mov     r9d, ecx; MaxCount
0x180002e1e  lea     rcx, [rbx+404h]; Destination
0x180002e25  mov     edx, 50h ; 'P'; SizeInWords
0x180002e2a  call    cs:__imp_wcsncpy_s
0x180002e31  nop     dword ptr [rax+rax+00h]
0x180002e36  test    eax, eax
0x180002e38  jnz     short loc_180002E46
0x180002e3a  movzx   eax, word ptr [rsp+170h+var_140]
0x180002e3f  mov     [rbx+402h], ax
0x180002e46  mov     rcx, [rsp+170h+Handle]; Handle
0x180002e4b  call    cs:__imp_NtClose
0x180002e52  nop     dword ptr [rax+rax+00h]
0x180002e57  mov     [rsp+170h+Handle], rsi
0x180002e5c  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x180002e61  test    rcx, rcx
0x180002e64  jz      short loc_180002E72
0x180002e66  call    cs:__imp_NtClose
0x180002e6d  nop     dword ptr [rax+rax+00h]
0x180002e72  mov     rcx, [rsp+170h+Handle]; Handle
0x180002e77  test    rcx, rcx
0x180002e7a  jz      short loc_180002E88
0x180002e7c  call    cs:__imp_NtClose
0x180002e83  nop     dword ptr [rax+rax+00h]
0x180002e88  mov     rcx, [rbp+70h+var_20]
0x180002e8c  xor     rcx, rsp; StackCookie
0x180002e8f  call    __security_check_cookie
0x180002e94  add     rsp, 160h
0x180002e9b  pop     rsi
0x180002e9c  pop     rbx
0x180002e9d  pop     rbp
0x180002e9e  retn
```
