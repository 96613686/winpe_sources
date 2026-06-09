# QueryRegistryDWord

- ea: `0x1400126ac`
- end: `0x1400127b6`
- name: `QueryRegistryDWord`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001af74`
- `0x14001f74c`
- `0x1400215e0`
- `0x14002ead0`
- `0x140030d48`
- `0x140033a64`
- `0x140039f5c`
- `0x14003abf0`
- `0x14004159c`
- `0x140044328`
- `0x140079014`
- `0x140079a48`
- `0x14007a240`
- `0x14007aae8`
- `0x140085ae8`
- `0x140089850`

## callees

- `0x1400126ac`
- `0x14005c7d0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140012786`
- `ntoskrnl!ZwClose` at `0x140012786`
- `ntoskrnl!ZwQueryValueKey` at `0x140012764`
- `ntoskrnl!ZwQueryValueKey` at `0x140012764`
- `ntoskrnl!ZwOpenKey` at `0x140012710`
- `ntoskrnl!ZwOpenKey` at `0x140012710`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001272e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001272e`

## pseudocode

```c
__int64 __fastcall QueryRegistryDWord(struct _UNICODE_STRING *a1, const WCHAR *a2, unsigned int a3)
{
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp+37h] BYREF
  int v11; // [rsp+84h] [rbp+3Bh]
  int v12; // [rsp+88h] [rbp+3Fh]
  unsigned int v13; // [rsp+8Ch] [rbp+43h]

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    ResultLength = 0;
    if ( !ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x14u,
            &ResultLength)
      && v11 == 4
      && v12 == 4 )
    {
      a3 = v13;
    }
    ZwClose(KeyHandle);
  }
  return a3;
}

```

## disassembly

```asm
0x1400126ac  mov     [rsp-8+arg_10], rbx
0x1400126b1  mov     [rsp-8+arg_18], rdi
0x1400126b6  push    rbp
0x1400126b7  lea     rbp, [rsp-57h]
0x1400126bc  sub     rsp, 0A0h
0x1400126c3  mov     rax, cs:__security_cookie
0x1400126ca  xor     rax, rsp
0x1400126cd  mov     [rbp+57h+var_8], rax
0x1400126d1  mov     ebx, r8d
0x1400126d4  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x1400126d8  mov     rdi, rdx
0x1400126db  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400126e3  xorps   xmm0, xmm0
0x1400126e6  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x1400126ee  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400126f2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400126fa  mov     edx, 20019h; DesiredAccess
0x1400126ff  mov     [rbp+57h+KeyHandle], 0
0x140012707  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14001270b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012710  call    cs:__imp_ZwOpenKey
0x140012717  nop     dword ptr [rax+rax+00h]
0x14001271c  test    eax, eax
0x14001271e  js      short loc_140012792
0x140012720  xorps   xmm0, xmm0
0x140012723  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140012727  mov     rdx, rdi; SourceString
0x14001272a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001272e  call    cs:__imp_RtlInitUnicodeString
0x140012735  nop     dword ptr [rax+rax+00h]
0x14001273a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14001273e  lea     rax, [rbp+57h+var_70]
0x140012742  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140012747  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14001274b  mov     r8d, 2; KeyValueInformationClass
0x140012751  mov     [rsp+0A0h+Length], 14h; Length
0x140012759  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001275d  mov     [rbp+57h+var_70], 0
0x140012764  call    cs:__imp_ZwQueryValueKey
0x14001276b  nop     dword ptr [rax+rax+00h]
0x140012770  test    eax, eax
0x140012772  jnz     short loc_140012782
0x140012774  cmp     [rbp+57h+var_1C], 4
0x140012778  jnz     short loc_140012782
0x14001277a  cmp     [rbp+57h+var_18], 4
0x14001277e  cmovz   ebx, [rbp+57h+var_14]
0x140012782  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140012786  call    cs:__imp_ZwClose
0x14001278d  nop     dword ptr [rax+rax+00h]
0x140012792  mov     eax, ebx
0x140012794  mov     rcx, [rbp+57h+var_8]
0x140012798  xor     rcx, rsp; StackCookie
0x14001279b  call    __security_check_cookie
0x1400127a0  lea     r11, [rsp+0A0h+var_s0]
0x1400127a8  mov     rbx, [r11+20h]
0x1400127ac  mov     rdi, [r11+28h]
0x1400127b0  mov     rsp, r11
0x1400127b3  pop     rbp
0x1400127b4  retn
```
