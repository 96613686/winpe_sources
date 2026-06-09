# ReadSettingsCache

- ea: `0x1800029f0`
- end: `0x180002ed2`
- name: `ReadSettingsCache`
- size: `1250`
- prototype: `int __fastcall(wchar_t *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800024b0`

## callees

- `0x1800029f0`
- `0x180002ee0`
- `0x180006850`
- `0x18000d730`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x180002af7`
- `ntdll!wcsncpy_s` at `0x180002c15`
- `ntdll!wcsncpy_s` at `0x180002c4c`
- `ntdll!wcsncpy_s` at `0x180002cb8`
- `ntdll!wcsncpy_s` at `0x180002cef`
- `ntdll!wcsncpy_s` at `0x180002df3`
- `ntdll!wcsncpy_s` at `0x180002e5c`
- `ntdll!wcsncpy_s` at `0x180002af7`
- `ntdll!wcsncpy_s` at `0x180002c15`
- `ntdll!wcsncpy_s` at `0x180002c4c`
- `ntdll!wcsncpy_s` at `0x180002cb8`
- `ntdll!wcsncpy_s` at `0x180002cef`
- `ntdll!wcsncpy_s` at `0x180002df3`
- `ntdll!wcsncpy_s` at `0x180002e5c`
- `ntdll!NtOpenKey` at `0x180002a5f`
- `ntdll!NtOpenKey` at `0x180002bb1`
- `ntdll!NtOpenKey` at `0x180002d92`
- `ntdll!NtOpenKey` at `0x180002a5f`
- `ntdll!NtOpenKey` at `0x180002bb1`
- `ntdll!NtOpenKey` at `0x180002d92`
- `ntdll!NtQueryValueKey` at `0x180002aa1`
- `ntdll!NtQueryValueKey` at `0x180002b36`
- `ntdll!NtQueryValueKey` at `0x180002aa1`
- `ntdll!NtQueryValueKey` at `0x180002b36`
- `ntdll!NtClose` at `0x180002d10`
- `ntdll!NtClose` at `0x180002e7d`
- `ntdll!NtClose` at `0x180002e98`
- `ntdll!NtClose` at `0x180002eae`
- `ntdll!NtClose` at `0x180002d10`
- `ntdll!NtClose` at `0x180002e7d`
- `ntdll!NtClose` at `0x180002e98`
- `ntdll!NtClose` at `0x180002eae`
- `ntdll!RtlInitUnicodeString` at `0x180002d64`
- `ntdll!RtlInitUnicodeString` at `0x180002d64`

## pseudocode

```c
int __fastcall ReadSettingsCache(wchar_t *a1, void *a2)
{
  __int64 v3; // rax
  wchar_t v4; // ax
  wchar_t *v5; // rdi
  errno_t v6; // eax
  rsize_t v7; // rcx
  wchar_t *v8; // rdi
  errno_t v9; // eax
  rsize_t v10; // rcx
  const WCHAR *v11; // rdx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v15; // [rsp+40h] [rbp-C0h]
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
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
  v15 = 0;
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
      v15 = Source;
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
      v15 = Source;
      if ( v20 == 1 && (ResultLength & 1) == 0 && ResultLength > 0xE )
      {
        ResultLength = ((ResultLength - 12) >> 1) - 1;
        if ( !Source[ResultLength] && ResultLength >= 4 )
        {
          v4 = CalendarIdFromString(Source);
          if ( v4 )
            a1[620] = v4;
        }
      }
    }
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&GregorianKey;
    ObjectAttributes.RootDirectory = KeyHandle;
    if ( NtOpenKey(&Handle, 1u, &ObjectAttributes) >= 0 )
    {
      if ( (unsigned int)QueryStringValue(Handle, &ShortDate, KeyValueInformation) && ResultLength - 2 <= 0x4D )
      {
        v5 = v15;
        v6 = wcsncpy_s(a1 + 627, 0x50u, v15, ResultLength);
        v7 = ResultLength;
        if ( !v6 )
          a1[626] = ResultLength;
        if ( a1[620] == 1 && !wcsncpy_s(a1 + 352, 0x50u, v5, v7) )
          a1[351] = ResultLength;
      }
      if ( (unsigned int)QueryStringValue(Handle, &LongDate, KeyValueInformation) && ResultLength - 3 <= 0x4C )
      {
        v8 = v15;
        v9 = wcsncpy_s(a1 + 708, 0x50u, v15, ResultLength);
        v10 = ResultLength;
        if ( !v9 )
          a1[707] = ResultLength;
        if ( a1[620] == 1 && !wcsncpy_s(a1 + 514, 0x50u, v8, v10) )
          a1[513] = ResultLength;
      }
      NtClose(Handle);
      Handle = 0;
    }
    v3 = a1[620];
    if ( (_DWORD)v3 != 1 && (unsigned int)v3 < 0x18 )
    {
      _mm_lfence();
      v11 = (const WCHAR *)*((_QWORD *)&CalendarNames + v3);
      if ( *v11 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, v11);
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = KeyHandle;
        LODWORD(v3) = NtOpenKey(&Handle, 1u, &ObjectAttributes);
        if ( (int)v3 >= 0 )
        {
          if ( (unsigned int)QueryStringValue(Handle, &ShortDate, KeyValueInformation)
            && ResultLength - 2 <= 0x4D
            && !wcsncpy_s(a1 + 352, 0x50u, v15, ResultLength) )
          {
            a1[351] = ResultLength;
          }
          if ( (unsigned int)QueryStringValue(Handle, &LongDate, KeyValueInformation)
            && ResultLength - 3 <= 0x4C
            && !wcsncpy_s(a1 + 514, 0x50u, v15, ResultLength) )
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
0x1800029f0  push    rbp
0x1800029f2  push    rbx
0x1800029f3  push    rsi
0x1800029f4  lea     rbp, [rsp-60h]
0x1800029f9  sub     rsp, 160h
0x180002a00  mov     rax, cs:__security_cookie
0x180002a07  xor     rax, rsp
0x180002a0a  mov     [rbp+70h+var_20], rax
0x180002a0e  xor     esi, esi
0x180002a10  mov     [rsp+170h+ObjectAttributes.RootDirectory], rdx
0x180002a15  mov     rbx, rcx
0x180002a18  mov     qword ptr [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x180002a21  lea     rax, ExplicitSettingsKey
0x180002a28  mov     qword ptr [rsp+170h+ObjectAttributes.Attributes], 40h ; '@'
0x180002a31  xorps   xmm0, xmm0
0x180002a34  mov     [rsp+170h+KeyHandle], rsi
0x180002a39  lea     edx, [rsi+1]; DesiredAccess
0x180002a3c  mov     [rsp+170h+Handle], rsi
0x180002a41  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180002a46  mov     [rsp+170h+var_130], rsi
0x180002a4b  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180002a50  mov     [rsp+170h+var_140], esi
0x180002a54  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x180002a59  movdqu  xmmword ptr [rsp+170h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002a5f  call    cs:__imp_NtOpenKey
0x180002a66  nop     dword ptr [rax+rax+00h]
0x180002a6b  test    eax, eax
0x180002a6d  js      loc_180002EBA
0x180002a73  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180002a78  lea     rax, [rsp+170h+var_140]
0x180002a7d  mov     [rsp+170h+ResultLength], rax; ResultLength
0x180002a82  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x180002a86  lea     r8d, [rsi+2]; KeyValueInformationClass
0x180002a8a  mov     [rsp+170h+Length], 0B6h; Length
0x180002a92  lea     rdx, Currencies; ValueName
0x180002a99  mov     [rsp+170h+arg_10], rdi
0x180002aa1  call    cs:__imp_NtQueryValueKey
0x180002aa8  nop     dword ptr [rax+rax+00h]
0x180002aad  test    eax, eax
0x180002aaf  js      short loc_180002B0E
0x180002ab1  cmp     [rbp+70h+var_DC], 1
0x180002ab5  lea     r8, [rbp+70h+Source]; Source
0x180002ab9  mov     [rsp+170h+var_130], r8
0x180002abe  jnz     short loc_180002B0E
0x180002ac0  mov     ecx, [rsp+170h+var_140]
0x180002ac4  test    cl, 1
0x180002ac7  jnz     short loc_180002B0E
0x180002ac9  cmp     ecx, 0Eh
0x180002acc  jbe     short loc_180002B0E
0x180002ace  add     ecx, 0FFFFFFF4h
0x180002ad1  shr     ecx, 1
0x180002ad3  dec     ecx
0x180002ad5  mov     [rsp+170h+var_140], ecx
0x180002ad9  cmp     [rbp+rcx*2+70h+Source], si
0x180002ade  jnz     short loc_180002B0E
0x180002ae0  cmp     ecx, 3
0x180002ae3  jb      short loc_180002B0E
0x180002ae5  mov     edi, 3
0x180002aea  lea     rcx, [rbx+4DCh]; Destination
0x180002af1  mov     r9d, edi; MaxCount
0x180002af4  lea     edx, [rsi+4]; SizeInWords
0x180002af7  call    cs:__imp_wcsncpy_s
0x180002afe  nop     dword ptr [rax+rax+00h]
0x180002b03  test    eax, eax
0x180002b05  jnz     short loc_180002B0E
0x180002b07  mov     [rbx+4DAh], di
0x180002b0e  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180002b13  lea     rax, [rsp+170h+var_140]
0x180002b18  mov     [rsp+170h+ResultLength], rax; ResultLength
0x180002b1d  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x180002b21  mov     r8d, 2; KeyValueInformationClass
0x180002b27  mov     [rsp+170h+Length], 0B6h; Length
0x180002b2f  lea     rdx, Calendar; ValueName
0x180002b36  call    cs:__imp_NtQueryValueKey
0x180002b3d  nop     dword ptr [rax+rax+00h]
0x180002b42  test    eax, eax
0x180002b44  js      short loc_180002B8C
0x180002b46  cmp     [rbp+70h+var_DC], 1
0x180002b4a  lea     rcx, [rbp+70h+Source]; String2
0x180002b4e  mov     [rsp+170h+var_130], rcx
0x180002b53  jnz     short loc_180002B8C
0x180002b55  mov     edx, [rsp+170h+var_140]
0x180002b59  test    dl, 1
0x180002b5c  jnz     short loc_180002B8C
0x180002b5e  cmp     edx, 0Eh
0x180002b61  jbe     short loc_180002B8C
0x180002b63  add     edx, 0FFFFFFF4h
0x180002b66  shr     edx, 1
0x180002b68  dec     edx
0x180002b6a  mov     [rsp+170h+var_140], edx
0x180002b6e  cmp     [rbp+rdx*2+70h+Source], si
0x180002b73  jnz     short loc_180002B8C
0x180002b75  cmp     edx, 4
0x180002b78  jb      short loc_180002B8C
0x180002b7a  call    CalendarIdFromString
0x180002b7f  cmp     ax, 1
0x180002b83  jb      short loc_180002B8C
0x180002b85  mov     [rbx+4D8h], ax
0x180002b8c  lea     rax, GregorianKey
0x180002b93  mov     edx, 1; DesiredAccess
0x180002b98  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x180002b9d  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180002ba2  mov     rax, [rsp+170h+KeyHandle]
0x180002ba7  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x180002bac  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x180002bb1  call    cs:__imp_NtOpenKey
0x180002bb8  nop     dword ptr [rax+rax+00h]
0x180002bbd  test    eax, eax
0x180002bbf  js      loc_180002D21
0x180002bc5  mov     rcx, [rsp+170h+Handle]
0x180002bca  lea     rax, [rsp+170h+var_140]
0x180002bcf  mov     [rsp+170h+ResultLength], rax
0x180002bd4  lea     r8, [rbp+70h+KeyValueInformation]
0x180002bd8  lea     rax, [rsp+170h+var_130]
0x180002bdd  lea     rdx, ShortDate
0x180002be4  mov     qword ptr [rsp+170h+Length], rax
0x180002be9  call    QueryStringValue
0x180002bee  test    eax, eax
0x180002bf0  jz      short loc_180002C68
0x180002bf2  mov     ecx, [rsp+170h+var_140]
0x180002bf6  lea     eax, [rcx-2]
0x180002bf9  cmp     eax, 4Dh ; 'M'
0x180002bfc  ja      short loc_180002C68
0x180002bfe  mov     rdi, [rsp+170h+var_130]
0x180002c03  mov     r9d, ecx; MaxCount
0x180002c06  mov     r8, rdi; Source
0x180002c09  lea     rcx, [rbx+4E6h]; Destination
0x180002c10  mov     edx, 50h ; 'P'; SizeInWords
0x180002c15  call    cs:__imp_wcsncpy_s
0x180002c1c  nop     dword ptr [rax+rax+00h]
0x180002c21  mov     ecx, [rsp+170h+var_140]
0x180002c25  test    eax, eax
0x180002c27  jnz     short loc_180002C30
0x180002c29  mov     [rbx+4E4h], cx
0x180002c30  cmp     word ptr [rbx+4D8h], 1
0x180002c38  jnz     short loc_180002C68
0x180002c3a  mov     r9, rcx; MaxCount
0x180002c3d  mov     r8, rdi; Source
0x180002c40  lea     rcx, [rbx+2C0h]; Destination
0x180002c47  mov     edx, 50h ; 'P'; SizeInWords
0x180002c4c  call    cs:__imp_wcsncpy_s
0x180002c53  nop     dword ptr [rax+rax+00h]
0x180002c58  test    eax, eax
0x180002c5a  jnz     short loc_180002C68
0x180002c5c  movzx   eax, word ptr [rsp+170h+var_140]
0x180002c61  mov     [rbx+2BEh], ax
0x180002c68  mov     rcx, [rsp+170h+Handle]
0x180002c6d  lea     rax, [rsp+170h+var_140]
0x180002c72  mov     [rsp+170h+ResultLength], rax
0x180002c77  lea     r8, [rbp+70h+KeyValueInformation]
0x180002c7b  lea     rax, [rsp+170h+var_130]
0x180002c80  lea     rdx, LongDate
0x180002c87  mov     qword ptr [rsp+170h+Length], rax
0x180002c8c  call    QueryStringValue
0x180002c91  test    eax, eax
0x180002c93  jz      short loc_180002D0B
0x180002c95  mov     ecx, [rsp+170h+var_140]
0x180002c99  lea     eax, [rcx-3]
0x180002c9c  cmp     eax, 4Ch ; 'L'
0x180002c9f  ja      short loc_180002D0B
0x180002ca1  mov     rdi, [rsp+170h+var_130]
0x180002ca6  mov     r9d, ecx; MaxCount
0x180002ca9  mov     r8, rdi; Source
0x180002cac  lea     rcx, [rbx+588h]; Destination
0x180002cb3  mov     edx, 50h ; 'P'; SizeInWords
0x180002cb8  call    cs:__imp_wcsncpy_s
0x180002cbf  nop     dword ptr [rax+rax+00h]
0x180002cc4  mov     ecx, [rsp+170h+var_140]
0x180002cc8  test    eax, eax
0x180002cca  jnz     short loc_180002CD3
0x180002ccc  mov     [rbx+586h], cx
0x180002cd3  cmp     word ptr [rbx+4D8h], 1
0x180002cdb  jnz     short loc_180002D0B
0x180002cdd  mov     r9, rcx; MaxCount
0x180002ce0  mov     r8, rdi; Source
0x180002ce3  lea     rcx, [rbx+404h]; Destination
0x180002cea  mov     edx, 50h ; 'P'; SizeInWords
0x180002cef  call    cs:__imp_wcsncpy_s
0x180002cf6  nop     dword ptr [rax+rax+00h]
0x180002cfb  test    eax, eax
0x180002cfd  jnz     short loc_180002D0B
0x180002cff  movzx   eax, word ptr [rsp+170h+var_140]
0x180002d04  mov     [rbx+402h], ax
0x180002d0b  mov     rcx, [rsp+170h+Handle]; Handle
0x180002d10  call    cs:__imp_NtClose
0x180002d17  nop     dword ptr [rax+rax+00h]
0x180002d1c  mov     [rsp+170h+Handle], rsi
0x180002d21  movzx   eax, word ptr [rbx+4D8h]
0x180002d28  mov     rdi, [rsp+170h+arg_10]
0x180002d30  cmp     eax, 1
0x180002d33  jz      loc_180002E8E
0x180002d39  cmp     eax, 18h
0x180002d3c  jnb     loc_180002E8E
0x180002d42  lfence
0x180002d45  lea     rdx, CalendarNames
0x180002d4c  mov     rdx, [rdx+rax*8]; SourceString
0x180002d50  cmp     [rdx], si
0x180002d53  jz      loc_180002E8E
0x180002d59  xorps   xmm0, xmm0
0x180002d5c  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x180002d60  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x180002d64  call    cs:__imp_RtlInitUnicodeString
0x180002d6b  nop     dword ptr [rax+rax+00h]
0x180002d70  lea     rax, [rbp+70h+DestinationString]
0x180002d74  mov     edx, 1; DesiredAccess
0x180002d79  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x180002d7e  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180002d83  mov     rax, [rsp+170h+KeyHandle]
0x180002d88  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x180002d8d  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x180002d92  call    cs:__imp_NtOpenKey
0x180002d99  nop     dword ptr [rax+rax+00h]
0x180002d9e  test    eax, eax
0x180002da0  js      loc_180002E8E
0x180002da6  mov     rcx, [rsp+170h+Handle]
0x180002dab  lea     rax, [rsp+170h+var_140]
0x180002db0  mov     [rsp+170h+ResultLength], rax
0x180002db5  lea     r8, [rbp+70h+KeyValueInformation]
0x180002db9  lea     rax, [rsp+170h+var_130]
0x180002dbe  lea     rdx, ShortDate
0x180002dc5  mov     qword ptr [rsp+170h+Length], rax
0x180002dca  call    QueryStringValue
0x180002dcf  test    eax, eax
0x180002dd1  jz      short loc_180002E0F
0x180002dd3  mov     ecx, [rsp+170h+var_140]
0x180002dd7  lea     eax, [rcx-2]
0x180002dda  cmp     eax, 4Dh ; 'M'
0x180002ddd  ja      short loc_180002E0F
0x180002ddf  mov     r8, [rsp+170h+var_130]; Source
0x180002de4  mov     r9d, ecx; MaxCount
0x180002de7  lea     rcx, [rbx+2C0h]; Destination
0x180002dee  mov     edx, 50h ; 'P'; SizeInWords
0x180002df3  call    cs:__imp_wcsncpy_s
0x180002dfa  nop     dword ptr [rax+rax+00h]
0x180002dff  test    eax, eax
0x180002e01  jnz     short loc_180002E0F
0x180002e03  movzx   eax, word ptr [rsp+170h+var_140]
0x180002e08  mov     [rbx+2BEh], ax
0x180002e0f  mov     rcx, [rsp+170h+Handle]
0x180002e14  lea     rax, [rsp+170h+var_140]
0x180002e19  mov     [rsp+170h+ResultLength], rax
0x180002e1e  lea     r8, [rbp+70h+KeyValueInformation]
0x180002e22  lea     rax, [rsp+170h+var_130]
0x180002e27  lea     rdx, LongDate
0x180002e2e  mov     qword ptr [rsp+170h+Length], rax
0x180002e33  call    QueryStringValue
0x180002e38  test    eax, eax
0x180002e3a  jz      short loc_180002E78
0x180002e3c  mov     ecx, [rsp+170h+var_140]
0x180002e40  lea     eax, [rcx-3]
0x180002e43  cmp     eax, 4Ch ; 'L'
0x180002e46  ja      short loc_180002E78
0x180002e48  mov     r8, [rsp+170h+var_130]; Source
0x180002e4d  mov     r9d, ecx; MaxCount
0x180002e50  lea     rcx, [rbx+404h]; Destination
0x180002e57  mov     edx, 50h ; 'P'; SizeInWords
0x180002e5c  call    cs:__imp_wcsncpy_s
0x180002e63  nop     dword ptr [rax+rax+00h]
0x180002e68  test    eax, eax
0x180002e6a  jnz     short loc_180002E78
0x180002e6c  movzx   eax, word ptr [rsp+170h+var_140]
0x180002e71  mov     [rbx+402h], ax
0x180002e78  mov     rcx, [rsp+170h+Handle]; Handle
0x180002e7d  call    cs:__imp_NtClose
0x180002e84  nop     dword ptr [rax+rax+00h]
0x180002e89  mov     [rsp+170h+Handle], rsi
0x180002e8e  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x180002e93  test    rcx, rcx
0x180002e96  jz      short loc_180002EA4
0x180002e98  call    cs:__imp_NtClose
0x180002e9f  nop     dword ptr [rax+rax+00h]
0x180002ea4  mov     rcx, [rsp+170h+Handle]; Handle
0x180002ea9  test    rcx, rcx
0x180002eac  jz      short loc_180002EBA
0x180002eae  call    cs:__imp_NtClose
0x180002eb5  nop     dword ptr [rax+rax+00h]
0x180002eba  mov     rcx, [rbp+70h+var_20]
0x180002ebe  xor     rcx, rsp; StackCookie
0x180002ec1  call    __security_check_cookie
0x180002ec6  add     rsp, 160h
0x180002ecd  pop     rsi
0x180002ece  pop     rbx
0x180002ecf  pop     rbp
0x180002ed0  retn
```
