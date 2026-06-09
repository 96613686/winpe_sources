# EfsInitialization

- ea: `0x140114998`
- end: `0x14011513e`
- name: `EfsInitialization`
- size: `1958`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400dfa80`

## callees

- `0x1400578d8`
- `0x140057ee8`
- `0x14005804c`
- `0x140058218`
- `0x140059740`
- `0x1400df74c`
- `0x1400f74e0`
- `0x140114854`
- `0x140114998`
- `0x14011a264`
- `0x14011a41c`
- `0x14011d200`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14011503b`
- `ntoskrnl!ObfDereferenceObject` at `0x14011503b`
- `ntoskrnl!ZwClose` at `0x140114c4c`
- `ntoskrnl!ZwClose` at `0x140114ffa`
- `ntoskrnl!ZwClose` at `0x140115023`
- `ntoskrnl!ZwClose` at `0x140114c4c`
- `ntoskrnl!ZwClose` at `0x140114ffa`
- `ntoskrnl!ZwClose` at `0x140115023`
- `ntoskrnl!PsCreateSystemThread` at `0x140114fe2`
- `ntoskrnl!PsCreateSystemThread` at `0x140114fe2`
- `ntoskrnl!ZwOpenKey` at `0x140114b38`
- `ntoskrnl!ZwOpenKey` at `0x140114b38`
- `ntoskrnl!ZwQueryValueKey` at `0x140114bb1`
- `ntoskrnl!ZwQueryValueKey` at `0x140114c0c`
- `ntoskrnl!ZwQueryValueKey` at `0x140114bb1`
- `ntoskrnl!ZwQueryValueKey` at `0x140114c0c`
- `ntoskrnl!ZwOpenFile` at `0x140114e67`
- `ntoskrnl!ZwOpenFile` at `0x140114e67`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114ae0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114b80`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114bd9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114c7d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114dfb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114f09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114ae0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114b80`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114bd9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114c7d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114dfb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114f09`
- `ntoskrnl!KeInitializeEvent` at `0x140114a23`
- `ntoskrnl!KeInitializeEvent` at `0x140114a81`
- `ntoskrnl!KeInitializeEvent` at `0x140114aae`
- `ntoskrnl!KeInitializeEvent` at `0x140114cd4`
- `ntoskrnl!KeInitializeEvent` at `0x140114d01`
- `ntoskrnl!KeInitializeEvent` at `0x140114a23`
- `ntoskrnl!KeInitializeEvent` at `0x140114a81`
- `ntoskrnl!KeInitializeEvent` at `0x140114aae`
- `ntoskrnl!KeInitializeEvent` at `0x140114cd4`
- `ntoskrnl!KeInitializeEvent` at `0x140114d01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140114c38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140114c38`
- `ntoskrnl!ZwOpenEvent` at `0x140114f94`
- `ntoskrnl!ZwOpenEvent` at `0x140114f94`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1401150ce`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140115107`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1401150ce`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140115107`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140114d6d`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140114da3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140114d6d`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140114da3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1401150e1`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1401150f4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1401150e1`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1401150f4`
- `ntoskrnl!NtClose` at `0x1401150bb`
- `ntoskrnl!NtClose` at `0x1401150bb`
- `ntoskrnl!ExAllocatePool2` at `0x140114b5c`
- `ntoskrnl!ExAllocatePool2` at `0x140114b5c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140114d3c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140114dd4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140114d3c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140114dd4`
- `ntoskrnl!ZwCreateEvent` at `0x140114f63`
- `ntoskrnl!ZwCreateEvent` at `0x140114f63`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115055`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14011506f`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115089`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1401150a3`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115055`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14011506f`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115089`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1401150a3`

## string_xrefs

- `0x140114aba`: `\Registry\Machine\System\CurrentControlSet\Services\NTFS\EFS\Parameters`
- `0x140114bcd`: `EFSKCACHEPERIOD`

## pseudocode

```c
__int64 EfsInitialization()
{
  _DWORD *Pool2; // rbx
  int v1; // ecx
  NTSTATUS inited; // ebx
  NTSTATUS v3; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-88h] BYREF
  struct _UNICODE_STRING v6; // [rsp+50h] [rbp-78h] BYREF
  struct _UNICODE_STRING v7; // [rsp+60h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-48h] BYREF
  ULONG ResultLength; // [rsp+D0h] [rbp+8h] BYREF
  void *KeyHandle; // [rsp+D8h] [rbp+10h] BYREF
  void *ThreadHandle; // [rsp+E0h] [rbp+18h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  v6 = 0;
  DestinationString = 0;
  v7 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140092288);
  TlgRegisterAggregateProviderEx(&dword_140092250);
  stru_140092460.Owner = 0;
  stru_140092460.Count = 1;
  stru_140092460.Contention = 0;
  KeInitializeEvent(&stru_140092460.Event, SynchronizationEvent, 0);
  TlgRegisterAggregateProviderEx(&dword_1400922F8);
  memset(&EfsData, 0, 0x4C0u);
  dword_140093A84 = 50000000;
  stru_140093E98.Count = 1;
  stru_140093E98.Owner = 0;
  stru_140093E98.Contention = 0;
  KeInitializeEvent(&stru_140093E98.Event, SynchronizationEvent, 0);
  stru_140093EF0.Count = 1;
  stru_140093EF0.Owner = 0;
  stru_140093EF0.Contention = 0;
  KeInitializeEvent(&stru_140093EF0.Event, SynchronizationEvent, 0);
  qword_140093ED0 = 0;
  dword_140093ED8 = 0;
  qword_140093EE0 = 0;
  dword_140093EE8 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\NTFS\\EFS\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(64, 1024, 1836279365);
    if ( Pool2 )
    {
      RtlInitUnicodeString(&DestinationString, L"MaximumBlob");
      if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, 0x400u, &ResultLength) >= 0
        && Pool2[3] )
      {
        byte_140093DE5 = 1;
      }
      RtlInitUnicodeString(&DestinationString, L"EFSKCACHEPERIOD");
      if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, 0x400u, &ResultLength) >= 0 )
      {
        v1 = Pool2[3];
        if ( (unsigned int)(v1 - 2) <= 0x1C )
          dword_140093A84 = 10000000 * v1;
      }
      ExFreePoolWithTag(Pool2, 0);
    }
    ZwClose(KeyHandle);
  }
  EfsData = 79695364;
  byte_140093DE4 = 0;
  dword_140093DE8 = 0;
  RtlInitUnicodeString(&::DestinationString, AttrName);
  stru_140093C18.Count = 1;
  qword_140093BC8 = (__int64)&qword_140093BC0;
  qword_140093BC0 = (__int64)&qword_140093BC0;
  stru_140093C18.Owner = 0;
  qword_140093C10 = (__int64)&qword_140093C08;
  qword_140093C08 = (__int64)&qword_140093C08;
  stru_140093C18.Contention = 0;
  KeInitializeEvent(&stru_140093C18.Event, SynchronizationEvent, 0);
  stru_140093BD0.Count = 1;
  stru_140093BD0.Owner = 0;
  stru_140093BD0.Contention = 0;
  KeInitializeEvent(&stru_140093BD0.Event, SynchronizationEvent, 0);
  ExInitializeNPagedLookasideList(&stru_140093AC0, 0, 0, 0x200u, 0x20u, 0x6E6F6345u, 5u);
  ExInitializePagedLookasideList(&stru_140093B40, 0, 0, 0x200u, 0x40u, 0x68636F45u, 5u);
  ExInitializePagedLookasideList(&stru_140093C80, 0, 0, 0x200u, 0x20u, 0x6D736645u, 3u);
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x80u, 0x6D736645u, 3u);
  inited = NtOfsRegisterCallBacks();
  if ( inited < 0 )
    goto LABEL_24;
  RtlInitUnicodeString(&v6, L"\\Device\\KsecDD");
  ObjectAttributes.ObjectName = &v6;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  inited = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( inited < 0 )
    goto LABEL_24;
  inited = EfsInitAes(&qword_140093D80, &dword_140093D88, &dword_140093D8C);
  if ( inited < 0 )
    goto LABEL_24;
  inited = EfsInitXtsAes(&qword_140093D90, &dword_140093D98);
  if ( inited < 0 )
    goto LABEL_24;
  inited = EfsInitDes(&qword_140093DC0, &dword_140093DC8, &qword_140093DD0, &dword_140093DD8);
  if ( inited < 0 )
    goto LABEL_24;
  inited = EfsInitFekProtection();
  if ( inited < 0 )
    goto LABEL_24;
  EfsInitFips();
  RtlInitUnicodeString(&v7, L"\\EFSInitEvent");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &v7;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwCreateEvent(&Handle, 2u, &ObjectAttributes, NotificationEvent, 0);
  inited = v3;
  if ( v3 < 0 )
  {
    if ( v3 != -1073741771 )
      goto LABEL_24;
    inited = ZwOpenEvent(&Handle, 2u, &ObjectAttributes);
    if ( inited < 0 )
      goto LABEL_24;
  }
  inited = EfsRpcInit();
  if ( inited >= 0 )
  {
    ThreadHandle = 0;
    if ( PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, EfspCheckEfsPolicy, 0) >= 0 )
      ZwClose(ThreadHandle);
    byte_140093DE4 = 1;
  }
  else
  {
LABEL_24:
    EfsRpcUnInit();
    if ( Handle )
      ZwClose(Handle);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( qword_140093D80 )
      BCryptCloseAlgorithmProvider(qword_140093D80, 0);
    if ( qword_140093D90 )
      BCryptCloseAlgorithmProvider(qword_140093D90, 0);
    if ( qword_140093DC0 )
      BCryptCloseAlgorithmProvider(qword_140093DC0, 0);
    if ( qword_140093DD0 )
      BCryptCloseAlgorithmProvider(qword_140093DD0, 0);
    if ( FileHandle )
      NtClose(FileHandle);
    ExDeleteNPagedLookasideList(&stru_140093AC0);
    ExDeletePagedLookasideList(&stru_140093B40);
    ExDeletePagedLookasideList(&stru_140093C80);
    ExDeleteNPagedLookasideList(&Lookaside);
    memset(&EfsData, 0, 0x4C0u);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140114998  mov     r11, rsp
0x14011499b  mov     [r11+20h], rbx
0x14011499f  push    rsi
0x1401149a0  push    rdi
0x1401149a1  push    r14
0x1401149a3  sub     rsp, 0B0h
0x1401149aa  xorps   xmm0, xmm0
0x1401149ad  lea     rcx, dword_140092288; CallbackContext
0x1401149b4  xorps   xmm1, xmm1
0x1401149b7  xor     esi, esi
0x1401149b9  movups  xmmword ptr [r11-38h], xmm0
0x1401149be  xor     eax, eax
0x1401149c0  mov     [r11+10h], rsi
0x1401149c4  xor     r8d, r8d
0x1401149c7  mov     [r11+8], esi
0x1401149cb  xor     edx, edx
0x1401149cd  movups  xmmword ptr [r11-2Ch], xmm0
0x1401149d2  movups  xmmword ptr [rsp+0C8h+var_78.Length], xmm0
0x1401149d7  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm1
0x1401149dc  movups  xmmword ptr [rsp+0C8h+var_68.Length], xmm0
0x1401149e1  movups  xmmword ptr [rsp+0C8h+IoStatusBlock], xmm0
0x1401149e6  movups  xmmword ptr [r11-48h], xmm0
0x1401149eb  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1401149f0  xor     edx, edx
0x1401149f2  lea     rcx, dword_140092250; CallbackContext
0x1401149f9  call    TlgRegisterAggregateProviderEx
0x1401149fe  lea     r14d, [rsi+1]
0x140114a02  mov     cs:stru_140092460.Owner, rsi
0x140114a09  mov     edx, r14d; Type
0x140114a0c  mov     cs:stru_140092460.Count, r14d
0x140114a13  xor     r8d, r8d; State
0x140114a16  mov     cs:stru_140092460.Contention, esi
0x140114a1c  lea     rcx, stru_140092460.Event; Event
0x140114a23  call    cs:__imp_KeInitializeEvent
0x140114a2a  nop     dword ptr [rax+rax+00h]
0x140114a2f  lea     rdx, EEL_EtwEventHandler
0x140114a36  lea     rcx, dword_1400922F8; CallbackContext
0x140114a3d  call    TlgRegisterAggregateProviderEx
0x140114a42  xor     edx, edx; Val
0x140114a44  lea     rcx, EfsData; void *
0x140114a4b  mov     r8d, 4C0h; Size
0x140114a51  call    memset
0x140114a56  xor     r8d, r8d; State
0x140114a59  mov     cs:dword_140093A84, 2FAF080h
0x140114a63  mov     edx, r14d; Type
0x140114a66  mov     cs:stru_140093E98.Count, r14d
0x140114a6d  lea     rcx, stru_140093E98.Event; Event
0x140114a74  mov     cs:stru_140093E98.Owner, rsi
0x140114a7b  mov     cs:stru_140093E98.Contention, esi
0x140114a81  call    cs:__imp_KeInitializeEvent
0x140114a88  nop     dword ptr [rax+rax+00h]
0x140114a8d  xor     r8d, r8d; State
0x140114a90  mov     cs:stru_140093EF0.Count, r14d
0x140114a97  mov     edx, r14d; Type
0x140114a9a  mov     cs:stru_140093EF0.Owner, rsi
0x140114aa1  lea     rcx, stru_140093EF0.Event; Event
0x140114aa8  mov     cs:stru_140093EF0.Contention, esi
0x140114aae  call    cs:__imp_KeInitializeEvent
0x140114ab5  nop     dword ptr [rax+rax+00h]
0x140114aba  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x140114ac1  mov     cs:qword_140093ED0, rsi
0x140114ac8  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140114acd  mov     cs:dword_140093ED8, esi
0x140114ad3  mov     cs:qword_140093EE0, rsi
0x140114ada  mov     cs:dword_140093EE8, esi
0x140114ae0  call    cs:__imp_RtlInitUnicodeString
0x140114ae7  nop     dword ptr [rax+rax+00h]
0x140114aec  lea     rax, [rsp+0C8h+DestinationString]
0x140114af1  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x140114afc  xorps   xmm0, xmm0
0x140114aff  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x140114b07  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x140114b0f  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x140114b17  mov     edx, 20019h; DesiredAccess
0x140114b1c  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x140114b27  lea     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x140114b2f  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140114b38  call    cs:__imp_ZwOpenKey
0x140114b3f  nop     dword ptr [rax+rax+00h]
0x140114b44  test    eax, eax
0x140114b46  js      loc_140114C58
0x140114b4c  mov     edi, 400h
0x140114b51  lea     ecx, [rsi+40h]
0x140114b54  mov     edx, edi
0x140114b56  mov     r8d, 6D736645h
0x140114b5c  call    cs:__imp_ExAllocatePool2
0x140114b63  nop     dword ptr [rax+rax+00h]
0x140114b68  mov     rbx, rax
0x140114b6b  test    rax, rax
0x140114b6e  jz      loc_140114C44
0x140114b74  lea     rdx, aMaximumblob; "MaximumBlob"
0x140114b7b  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140114b80  call    cs:__imp_RtlInitUnicodeString
0x140114b87  nop     dword ptr [rax+rax+00h]
0x140114b8c  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x140114b94  lea     rax, [rsp+0C8h+arg_0]
0x140114b9c  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x140114ba1  lea     r8d, [rsi+2]; KeyValueInformationClass
0x140114ba5  mov     r9, rbx; KeyValueInformation
0x140114ba8  mov     [rsp+0C8h+Length], edi; Length
0x140114bac  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x140114bb1  call    cs:__imp_ZwQueryValueKey
0x140114bb8  nop     dword ptr [rax+rax+00h]
0x140114bbd  test    eax, eax
0x140114bbf  js      short loc_140114BCD
0x140114bc1  cmp     [rbx+0Ch], esi
0x140114bc4  jz      short loc_140114BCD
0x140114bc6  mov     cs:byte_140093DE5, r14b
0x140114bcd  lea     rdx, aEfskcacheperio; "EFSKCACHEPERIOD"
0x140114bd4  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140114bd9  call    cs:__imp_RtlInitUnicodeString
0x140114be0  nop     dword ptr [rax+rax+00h]
0x140114be5  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x140114bed  lea     rax, [rsp+0C8h+arg_0]
0x140114bf5  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x140114bfa  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x140114bff  mov     r9, rbx; KeyValueInformation
0x140114c02  mov     [rsp+0C8h+Length], edi; Length
0x140114c06  mov     r8d, 2; KeyValueInformationClass
0x140114c0c  call    cs:__imp_ZwQueryValueKey
0x140114c13  nop     dword ptr [rax+rax+00h]
0x140114c18  test    eax, eax
0x140114c1a  js      short loc_140114C33
0x140114c1c  mov     ecx, [rbx+0Ch]
0x140114c1f  lea     eax, [rcx-2]
0x140114c22  cmp     eax, 1Ch
0x140114c25  ja      short loc_140114C33
0x140114c27  imul    eax, ecx, 989680h
0x140114c2d  mov     cs:dword_140093A84, eax
0x140114c33  xor     edx, edx; Tag
0x140114c35  mov     rcx, rbx; P
0x140114c38  call    cs:__imp_ExFreePoolWithTag
0x140114c3f  nop     dword ptr [rax+rax+00h]
0x140114c44  mov     rcx, [rsp+0C8h+KeyHandle]; Handle
0x140114c4c  call    cs:__imp_ZwClose
0x140114c53  nop     dword ptr [rax+rax+00h]
0x140114c58  lea     rdx, AttrName; "$EFS"
0x140114c5f  mov     cs:EfsData, 4C00E04h
0x140114c69  lea     rcx, DestinationString; DestinationString
0x140114c70  mov     cs:byte_140093DE4, sil
0x140114c77  mov     cs:dword_140093DE8, esi
0x140114c7d  call    cs:__imp_RtlInitUnicodeString
0x140114c84  nop     dword ptr [rax+rax+00h]
0x140114c89  lea     rax, qword_140093BC0
0x140114c90  mov     cs:stru_140093C18.Count, r14d
0x140114c97  mov     cs:qword_140093BC8, rax
0x140114c9e  lea     rcx, stru_140093C18.Event; Event
0x140114ca5  mov     cs:qword_140093BC0, rax
0x140114cac  xor     r8d, r8d; State
0x140114caf  lea     rax, qword_140093C08
0x140114cb6  mov     cs:stru_140093C18.Owner, rsi
0x140114cbd  mov     edx, r14d; Type
0x140114cc0  mov     cs:qword_140093C10, rax
0x140114cc7  mov     cs:qword_140093C08, rax
0x140114cce  mov     cs:stru_140093C18.Contention, esi
0x140114cd4  call    cs:__imp_KeInitializeEvent
0x140114cdb  nop     dword ptr [rax+rax+00h]
0x140114ce0  xor     r8d, r8d; State
0x140114ce3  mov     cs:stru_140093BD0.Count, r14d
0x140114cea  mov     edx, r14d; Type
0x140114ced  mov     cs:stru_140093BD0.Owner, rsi
0x140114cf4  lea     rcx, stru_140093BD0.Event; Event
0x140114cfb  mov     cs:stru_140093BD0.Contention, esi
0x140114d01  call    cs:__imp_KeInitializeEvent
0x140114d08  nop     dword ptr [rax+rax+00h]
0x140114d0d  mov     ebx, 5
0x140114d12  lea     rcx, stru_140093AC0; Lookaside
0x140114d19  mov     [rsp+0C8h+Depth], bx; Depth
0x140114d1e  mov     edi, 200h
0x140114d23  mov     dword ptr [rsp+0C8h+ResultLength], 6E6F6345h; Tag
0x140114d2b  mov     r9d, edi; Flags
0x140114d2e  xor     r8d, r8d; Free
0x140114d31  mov     qword ptr [rsp+0C8h+Length], 20h ; ' '; Size
0x140114d3a  xor     edx, edx; Allocate
0x140114d3c  call    cs:__imp_ExInitializeNPagedLookasideList
0x140114d43  nop     dword ptr [rax+rax+00h]
0x140114d48  mov     [rsp+0C8h+Depth], bx; Depth
0x140114d4d  lea     rcx, stru_140093B40; Lookaside
0x140114d54  mov     dword ptr [rsp+0C8h+ResultLength], 68636F45h; Tag
0x140114d5c  mov     r9d, edi; Flags
0x140114d5f  xor     r8d, r8d; Free
0x140114d62  mov     qword ptr [rsp+0C8h+Length], 40h ; '@'; Size
0x140114d6b  xor     edx, edx; Allocate
0x140114d6d  call    cs:__imp_ExInitializePagedLookasideList
0x140114d74  nop     dword ptr [rax+rax+00h]
0x140114d79  mov     ebx, 3
0x140114d7e  lea     rcx, stru_140093C80; Lookaside
0x140114d85  mov     [rsp+0C8h+Depth], bx; Depth
0x140114d8a  mov     r9d, edi; Flags
0x140114d8d  mov     dword ptr [rsp+0C8h+ResultLength], 6D736645h; Tag
0x140114d95  xor     r8d, r8d; Free
0x140114d98  xor     edx, edx; Allocate
0x140114d9a  mov     qword ptr [rsp+0C8h+Length], 20h ; ' '; Size
0x140114da3  call    cs:__imp_ExInitializePagedLookasideList
0x140114daa  nop     dword ptr [rax+rax+00h]
0x140114daf  mov     [rsp+0C8h+Depth], bx; Depth
0x140114db4  lea     rcx, Lookaside; Lookaside
0x140114dbb  mov     dword ptr [rsp+0C8h+ResultLength], 6D736645h; Tag
0x140114dc3  mov     r9d, edi; Flags
0x140114dc6  xor     r8d, r8d; Free
0x140114dc9  mov     qword ptr [rsp+0C8h+Length], 80h; Size
0x140114dd2  xor     edx, edx; Allocate
0x140114dd4  call    cs:__imp_ExInitializeNPagedLookasideList
0x140114ddb  nop     dword ptr [rax+rax+00h]
0x140114de0  call    NtOfsRegisterCallBacks
0x140114de5  mov     ebx, eax
0x140114de7  test    eax, eax
0x140114de9  js      loc_140115012
0x140114def  lea     rdx, aDeviceKsecdd; "\\Device\\KsecDD"
0x140114df6  lea     rcx, [rsp+0C8h+var_78]; DestinationString
0x140114dfb  call    cs:__imp_RtlInitUnicodeString
0x140114e02  nop     dword ptr [rax+rax+00h]
0x140114e07  lea     rax, [rsp+0C8h+var_78]
0x140114e0c  mov     dword ptr [rsp+0C8h+ResultLength], 20h ; ' '; OpenOptions
0x140114e14  xorps   xmm0, xmm0
0x140114e17  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x140114e1f  lea     r9, [rsp+0C8h+IoStatusBlock]; IoStatusBlock
0x140114e24  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x140114e2f  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x140114e37  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x140114e3f  mov     edx, 100001h; DesiredAccess
0x140114e44  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x140114e4f  lea     rcx, FileHandle; FileHandle
0x140114e56  mov     [rsp+0C8h+Length], 7; ShareAccess
0x140114e5e  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140114e67  call    cs:__imp_ZwOpenFile
0x140114e6e  nop     dword ptr [rax+rax+00h]
0x140114e73  mov     ebx, eax
0x140114e75  test    eax, eax
0x140114e77  js      loc_140115012
0x140114e7d  lea     r8, dword_140093D8C
0x140114e84  lea     rdx, dword_140093D88
0x140114e8b  lea     rcx, qword_140093D80
0x140114e92  call    EfsInitAes
0x140114e97  mov     ebx, eax
0x140114e99  test    eax, eax
0x140114e9b  js      loc_140115012
0x140114ea1  lea     rdx, dword_140093D98
0x140114ea8  lea     rcx, qword_140093D90
0x140114eaf  call    EfsInitXtsAes
0x140114eb4  mov     ebx, eax
0x140114eb6  test    eax, eax
0x140114eb8  js      loc_140115012
0x140114ebe  lea     r9, dword_140093DD8
0x140114ec5  lea     r8, qword_140093DD0
0x140114ecc  lea     rdx, dword_140093DC8
0x140114ed3  lea     rcx, qword_140093DC0
0x140114eda  call    EfsInitDes
0x140114edf  mov     ebx, eax
0x140114ee1  test    eax, eax
0x140114ee3  js      loc_140115012
0x140114ee9  call    EfsInitFekProtection
0x140114eee  mov     ebx, eax
0x140114ef0  test    eax, eax
0x140114ef2  js      loc_140115012
0x140114ef8  call    EfsInitFips
0x140114efd  lea     rdx, aEfsinitevent; "\\EFSInitEvent"
0x140114f04  lea     rcx, [rsp+0C8h+var_68]; DestinationString
0x140114f09  call    cs:__imp_RtlInitUnicodeString
0x140114f10  nop     dword ptr [rax+rax+00h]
0x140114f15  xor     r9d, r9d; EventType
0x140114f18  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x140114f23  lea     rax, [rsp+0C8h+var_68]
0x140114f28  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x140114f30  xorps   xmm0, xmm0
0x140114f33  mov     [rsp+0C8h+ObjectAttributes.Attributes], esi
0x140114f3a  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x140114f42  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x140114f4a  lea     edx, [r9+2]; DesiredAccess
0x140114f4e  mov     byte ptr [rsp+0C8h+Length], sil; InitialState
0x140114f53  lea     rcx, Handle; EventHandle
0x140114f5a  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140114f63  call    cs:__imp_ZwCreateEvent
0x140114f6a  nop     dword ptr [rax+rax+00h]
0x140114f6f  mov     ebx, eax
0x140114f71  test    eax, eax
0x140114f73  jns     short loc_140114FA6
0x140114f75  cmp     eax, 0C0000035h
0x140114f7a  jnz     loc_140115012
0x140114f80  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x140114f88  mov     edx, 2; DesiredAccess
0x140114f8d  lea     rcx, Handle; EventHandle
0x140114f94  call    cs:__imp_ZwOpenEvent
0x140114f9b  nop     dword ptr [rax+rax+00h]
0x140114fa0  mov     ebx, eax
0x140114fa2  test    eax, eax
0x140114fa4  js      short loc_140115012
0x140114fa6  call    EfsRpcInit
0x140114fab  mov     ebx, eax
0x140114fad  test    eax, eax
0x140114faf  js      short loc_140115012
0x140114fb1  lea     rax, EfspCheckEfsPolicy
0x140114fb8  mov     qword ptr [rsp+0C8h+Depth], rsi; StartContext
0x140114fbd  mov     [rsp+0C8h+ResultLength], rax; StartRoutine
0x140114fc2  lea     rcx, [rsp+0C8h+ThreadHandle]; ThreadHandle
0x140114fca  xor     r9d, r9d; ProcessHandle
0x140114fcd  mov     qword ptr [rsp+0C8h+Length], rsi; ClientId
0x140114fd2  xor     r8d, r8d; ObjectAttributes
0x140114fd5  mov     [rsp+0C8h+ThreadHandle], rsi
0x140114fdd  mov     edx, 1FFFFFh; DesiredAccess
  ... truncated ...
```
