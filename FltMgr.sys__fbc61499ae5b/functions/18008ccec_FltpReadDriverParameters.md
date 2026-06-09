# FltpReadDriverParameters

- ea: `0x18008ccec`
- end: `0x18008d129`
- name: `FltpReadDriverParameters`
- size: `1085`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18008c078`

## callees

- `0x180009f20`
- `0x180024800`
- `0x18008ccec`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18008cd92`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cdf7`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008ce43`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008ce93`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cee4`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cf35`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cf81`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cfcd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d019`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d065`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d0b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cd92`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cdf7`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008ce43`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008ce93`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cee4`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cf35`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cf81`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cfcd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d019`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d065`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d0b1`
- `ntoskrnl!ZwClose` at `0x18008d0fb`
- `ntoskrnl!ZwClose` at `0x18008d0fb`
- `ntoskrnl!ZwOpenKey` at `0x18008cd4b`
- `ntoskrnl!ZwOpenKey` at `0x18008cd4b`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cdba`
- `ntoskrnl!ZwQueryValueKey` at `0x18008ce1f`
- `ntoskrnl!ZwQueryValueKey` at `0x18008ce6b`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cebb`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cf0c`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cf5d`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cfa9`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cff5`
- `ntoskrnl!ZwQueryValueKey` at `0x18008d041`
- `ntoskrnl!ZwQueryValueKey` at `0x18008d08d`
- `ntoskrnl!ZwQueryValueKey` at `0x18008d0d9`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cdba`
- `ntoskrnl!ZwQueryValueKey` at `0x18008ce1f`
- `ntoskrnl!ZwQueryValueKey` at `0x18008ce6b`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cebb`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cf0c`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cf5d`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cfa9`
- `ntoskrnl!ZwQueryValueKey` at `0x18008cff5`
- `ntoskrnl!ZwQueryValueKey` at `0x18008d041`
- `ntoskrnl!ZwQueryValueKey` at `0x18008d08d`
- `ntoskrnl!ZwQueryValueKey` at `0x18008d0d9`

## pseudocode

```c
NTSTATUS __fastcall FltpReadDriverParameters(UNICODE_STRING *a1)
{
  unsigned int v1; // eax
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp+37h] BYREF
  int v8; // [rsp+84h] [rbp+3Bh]
  __int64 v9; // [rsp+8Ch] [rbp+43h]

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  DestinationString = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  result = FltpDbgStatus(v1, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 11422, 0);
  if ( result >= 0 )
  {
    if ( !FltGlobals[0] )
    {
      RtlInitUnicodeString(&DestinationString, L"DebugFlags");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x18u,
             &ResultLength) >= 0
        && v8 == 4 )
      {
        FltGlobals[0] = v9;
      }
    }
    if ( !dword_1800402F0 )
    {
      dword_1800402F0 = 30;
      RtlInitUnicodeString(&DestinationString, L"LostItemDetectionDelay");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x18u,
             &ResultLength) >= 0 )
        dword_1800402F0 = v9;
    }
    RtlInitUnicodeString(&DestinationString, L"UseTildeShortcut");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0
      && (_DWORD)v9 )
    {
      dword_18003ECD0 &= ~2u;
    }
    RtlInitUnicodeString(&DestinationString, L"FastManualAttachTimerPeriod");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0
      && (_DWORD)v9 )
    {
      dword_18003EF70 = v9;
    }
    RtlInitUnicodeString(&DestinationString, L"ManualAttachTimerPeriod");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0
      && (_DWORD)v9 )
    {
      LODWORD(qword_18003EF74) = v9;
    }
    RtlInitUnicodeString(&DestinationString, L"ManualAttachDelay");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      HIDWORD(qword_18003EF74) = v9;
    RtlInitUnicodeString(&DestinationString, L"CallbackStackSwapThreshold");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      dword_18003EF80 = v9;
    RtlInitUnicodeString(&DestinationString, L"ManualAttachIgnoredDevices");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      byte_18003EF7C = v9;
    RtlInitUnicodeString(&DestinationString, L"ManualAttachOnlyOnceDevices");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      byte_18003EF7D = v9;
    RtlInitUnicodeString(&DestinationString, L"ManualAttachFastAttachDevices");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      byte_18003EF7E = v9;
    RtlInitUnicodeString(&DestinationString, L"DisableFrameMonitoring");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
    {
      if ( (_DWORD)v9 )
        dword_18003ECD0 &= ~0x100u;
    }
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x18008ccec  mov     [rsp-8+arg_8], rsi
0x18008ccf1  mov     [rsp-8+arg_10], rdi
0x18008ccf6  push    rbp
0x18008ccf7  lea     rbp, [rsp-57h]
0x18008ccfc  sub     rsp, 0A0h
0x18008cd03  mov     rax, cs:__security_cookie
0x18008cd0a  xor     rax, rsp
0x18008cd0d  mov     [rbp+57h+var_8], rax
0x18008cd11  xor     eax, eax
0x18008cd13  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x18008cd17  xorps   xmm0, xmm0
0x18008cd1a  mov     [rbp+57h+KeyHandle], rax
0x18008cd1e  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008cd22  mov     [rbp+57h+var_70], eax
0x18008cd25  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008cd29  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008cd2d  mov     edx, 20019h; DesiredAccess
0x18008cd32  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008cd3a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18008cd3e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008cd46  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008cd4b  call    cs:__imp_ZwOpenKey
0x18008cd52  nop     dword ptr [rax+rax+00h]
0x18008cd57  mov     r8d, 2C9Eh
0x18008cd5d  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18008cd64  mov     ecx, eax
0x18008cd66  xor     r9d, r9d
0x18008cd69  call    FltpDbgStatus
0x18008cd6e  test    eax, eax
0x18008cd70  js      loc_18008D107
0x18008cd76  cmp     cs:FltGlobals, 0
0x18008cd7d  mov     edi, 18h
0x18008cd82  lea     esi, [rdi-16h]
0x18008cd85  jnz     short loc_18008CDD9
0x18008cd87  lea     rdx, aDebugflags; "DebugFlags"
0x18008cd8e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008cd92  call    cs:__imp_RtlInitUnicodeString
0x18008cd99  nop     dword ptr [rax+rax+00h]
0x18008cd9e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008cda2  lea     rax, [rbp+57h+var_70]
0x18008cda6  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008cdab  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008cdaf  mov     r8d, esi; KeyValueInformationClass
0x18008cdb2  mov     [rsp+0A0h+Length], edi; Length
0x18008cdb6  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008cdba  call    cs:__imp_ZwQueryValueKey
0x18008cdc1  nop     dword ptr [rax+rax+00h]
0x18008cdc6  test    eax, eax
0x18008cdc8  js      short loc_18008CDD9
0x18008cdca  cmp     [rbp+57h+var_1C], 4
0x18008cdce  jnz     short loc_18008CDD9
0x18008cdd0  mov     eax, dword ptr [rbp+57h+var_14]
0x18008cdd3  mov     cs:FltGlobals, eax
0x18008cdd9  cmp     cs:dword_1800402F0, 0
0x18008cde0  jnz     short loc_18008CE38
0x18008cde2  lea     rdx, aLostitemdetect; "LostItemDetectionDelay"
0x18008cde9  mov     cs:dword_1800402F0, 1Eh
0x18008cdf3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008cdf7  call    cs:__imp_RtlInitUnicodeString
0x18008cdfe  nop     dword ptr [rax+rax+00h]
0x18008ce03  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008ce07  lea     rax, [rbp+57h+var_70]
0x18008ce0b  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008ce10  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008ce14  mov     r8d, esi; KeyValueInformationClass
0x18008ce17  mov     [rsp+0A0h+Length], edi; Length
0x18008ce1b  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008ce1f  call    cs:__imp_ZwQueryValueKey
0x18008ce26  nop     dword ptr [rax+rax+00h]
0x18008ce2b  test    eax, eax
0x18008ce2d  js      short loc_18008CE38
0x18008ce2f  mov     eax, dword ptr [rbp+57h+var_14]
0x18008ce32  mov     cs:dword_1800402F0, eax
0x18008ce38  lea     rdx, aUsetildeshortc; "UseTildeShortcut"
0x18008ce3f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008ce43  call    cs:__imp_RtlInitUnicodeString
0x18008ce4a  nop     dword ptr [rax+rax+00h]
0x18008ce4f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008ce53  lea     rax, [rbp+57h+var_70]
0x18008ce57  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008ce5c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008ce60  mov     r8d, esi; KeyValueInformationClass
0x18008ce63  mov     [rsp+0A0h+Length], edi; Length
0x18008ce67  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008ce6b  call    cs:__imp_ZwQueryValueKey
0x18008ce72  nop     dword ptr [rax+rax+00h]
0x18008ce77  test    eax, eax
0x18008ce79  js      short loc_18008CE88
0x18008ce7b  cmp     dword ptr [rbp+57h+var_14], 0
0x18008ce7f  jz      short loc_18008CE88
0x18008ce81  and     cs:dword_18003ECD0, 0FFFFFFFDh
0x18008ce88  lea     rdx, aFastmanualatta; "FastManualAttachTimerPeriod"
0x18008ce8f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008ce93  call    cs:__imp_RtlInitUnicodeString
0x18008ce9a  nop     dword ptr [rax+rax+00h]
0x18008ce9f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008cea3  lea     rax, [rbp+57h+var_70]
0x18008cea7  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008ceac  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008ceb0  mov     r8d, esi; KeyValueInformationClass
0x18008ceb3  mov     [rsp+0A0h+Length], edi; Length
0x18008ceb7  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008cebb  call    cs:__imp_ZwQueryValueKey
0x18008cec2  nop     dword ptr [rax+rax+00h]
0x18008cec7  test    eax, eax
0x18008cec9  js      short loc_18008CED9
0x18008cecb  mov     rax, [rbp+57h+var_14]
0x18008cecf  test    eax, eax
0x18008ced1  jz      short loc_18008CED9
0x18008ced3  mov     cs:dword_18003EF70, eax
0x18008ced9  lea     rdx, aManualattachti; "ManualAttachTimerPeriod"
0x18008cee0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008cee4  call    cs:__imp_RtlInitUnicodeString
0x18008ceeb  nop     dword ptr [rax+rax+00h]
0x18008cef0  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008cef4  lea     rax, [rbp+57h+var_70]
0x18008cef8  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008cefd  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008cf01  mov     r8d, esi; KeyValueInformationClass
0x18008cf04  mov     [rsp+0A0h+Length], edi; Length
0x18008cf08  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008cf0c  call    cs:__imp_ZwQueryValueKey
0x18008cf13  nop     dword ptr [rax+rax+00h]
0x18008cf18  test    eax, eax
0x18008cf1a  js      short loc_18008CF2A
0x18008cf1c  mov     rax, [rbp+57h+var_14]
0x18008cf20  test    eax, eax
0x18008cf22  jz      short loc_18008CF2A
0x18008cf24  mov     dword ptr cs:qword_18003EF74, eax
0x18008cf2a  lea     rdx, aManualattachde; "ManualAttachDelay"
0x18008cf31  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008cf35  call    cs:__imp_RtlInitUnicodeString
0x18008cf3c  nop     dword ptr [rax+rax+00h]
0x18008cf41  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008cf45  lea     rax, [rbp+57h+var_70]
0x18008cf49  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008cf4e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008cf52  mov     r8d, esi; KeyValueInformationClass
0x18008cf55  mov     [rsp+0A0h+Length], edi; Length
0x18008cf59  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008cf5d  call    cs:__imp_ZwQueryValueKey
0x18008cf64  nop     dword ptr [rax+rax+00h]
0x18008cf69  test    eax, eax
0x18008cf6b  js      short loc_18008CF76
0x18008cf6d  mov     eax, dword ptr [rbp+57h+var_14]
0x18008cf70  mov     dword ptr cs:qword_18003EF74+4, eax
0x18008cf76  lea     rdx, aCallbackstacks; "CallbackStackSwapThreshold"
0x18008cf7d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008cf81  call    cs:__imp_RtlInitUnicodeString
0x18008cf88  nop     dword ptr [rax+rax+00h]
0x18008cf8d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008cf91  lea     rax, [rbp+57h+var_70]
0x18008cf95  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008cf9a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008cf9e  mov     r8d, esi; KeyValueInformationClass
0x18008cfa1  mov     [rsp+0A0h+Length], edi; Length
0x18008cfa5  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008cfa9  call    cs:__imp_ZwQueryValueKey
0x18008cfb0  nop     dword ptr [rax+rax+00h]
0x18008cfb5  test    eax, eax
0x18008cfb7  js      short loc_18008CFC2
0x18008cfb9  mov     eax, dword ptr [rbp+57h+var_14]
0x18008cfbc  mov     cs:dword_18003EF80, eax
0x18008cfc2  lea     rdx, aManualattachig; "ManualAttachIgnoredDevices"
0x18008cfc9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008cfcd  call    cs:__imp_RtlInitUnicodeString
0x18008cfd4  nop     dword ptr [rax+rax+00h]
0x18008cfd9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008cfdd  lea     rax, [rbp+57h+var_70]
0x18008cfe1  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008cfe6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008cfea  mov     r8d, esi; KeyValueInformationClass
0x18008cfed  mov     [rsp+0A0h+Length], edi; Length
0x18008cff1  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008cff5  call    cs:__imp_ZwQueryValueKey
0x18008cffc  nop     dword ptr [rax+rax+00h]
0x18008d001  test    eax, eax
0x18008d003  js      short loc_18008D00E
0x18008d005  mov     al, byte ptr [rbp+57h+var_14]
0x18008d008  mov     cs:byte_18003EF7C, al
0x18008d00e  lea     rdx, aManualattachon; "ManualAttachOnlyOnceDevices"
0x18008d015  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008d019  call    cs:__imp_RtlInitUnicodeString
0x18008d020  nop     dword ptr [rax+rax+00h]
0x18008d025  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008d029  lea     rax, [rbp+57h+var_70]
0x18008d02d  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008d032  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008d036  mov     r8d, esi; KeyValueInformationClass
0x18008d039  mov     [rsp+0A0h+Length], edi; Length
0x18008d03d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008d041  call    cs:__imp_ZwQueryValueKey
0x18008d048  nop     dword ptr [rax+rax+00h]
0x18008d04d  test    eax, eax
0x18008d04f  js      short loc_18008D05A
0x18008d051  mov     al, byte ptr [rbp+57h+var_14]
0x18008d054  mov     cs:byte_18003EF7D, al
0x18008d05a  lea     rdx, aManualattachfa; "ManualAttachFastAttachDevices"
0x18008d061  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008d065  call    cs:__imp_RtlInitUnicodeString
0x18008d06c  nop     dword ptr [rax+rax+00h]
0x18008d071  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008d075  lea     rax, [rbp+57h+var_70]
0x18008d079  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008d07e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008d082  mov     r8d, esi; KeyValueInformationClass
0x18008d085  mov     [rsp+0A0h+Length], edi; Length
0x18008d089  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008d08d  call    cs:__imp_ZwQueryValueKey
0x18008d094  nop     dword ptr [rax+rax+00h]
0x18008d099  test    eax, eax
0x18008d09b  js      short loc_18008D0A6
0x18008d09d  mov     al, byte ptr [rbp+57h+var_14]
0x18008d0a0  mov     cs:byte_18003EF7E, al
0x18008d0a6  lea     rdx, aDisableframemo; "DisableFrameMonitoring"
0x18008d0ad  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008d0b1  call    cs:__imp_RtlInitUnicodeString
0x18008d0b8  nop     dword ptr [rax+rax+00h]
0x18008d0bd  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008d0c1  lea     rax, [rbp+57h+var_70]
0x18008d0c5  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008d0ca  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008d0ce  mov     r8d, esi; KeyValueInformationClass
0x18008d0d1  mov     [rsp+0A0h+Length], edi; Length
0x18008d0d5  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008d0d9  call    cs:__imp_ZwQueryValueKey
0x18008d0e0  nop     dword ptr [rax+rax+00h]
0x18008d0e5  test    eax, eax
0x18008d0e7  js      short loc_18008D0F7
0x18008d0e9  cmp     dword ptr [rbp+57h+var_14], 0
0x18008d0ed  jz      short loc_18008D0F7
0x18008d0ef  btr     cs:dword_18003ECD0, 8
0x18008d0f7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008d0fb  call    cs:__imp_ZwClose
0x18008d102  nop     dword ptr [rax+rax+00h]
0x18008d107  mov     rcx, [rbp+57h+var_8]
0x18008d10b  xor     rcx, rsp; StackCookie
0x18008d10e  call    __security_check_cookie
0x18008d113  lea     r11, [rsp+0A0h+var_s0]
0x18008d11b  mov     rsi, [r11+18h]
0x18008d11f  mov     rdi, [r11+20h]
0x18008d123  mov     rsp, r11
0x18008d126  pop     rbp
0x18008d127  retn
```
