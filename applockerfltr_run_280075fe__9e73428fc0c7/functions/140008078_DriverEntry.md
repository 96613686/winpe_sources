# DriverEntry

- ea: `0x140008078`
- end: `0x140008558`
- name: `DriverEntry`
- size: `1248`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140008010`

## callees

- `0x140001820`
- `0x140001860`
- `0x140008078`
- `0x140008560`

## import_xrefs

- `ntoskrnl!CmRegisterCallback` at `0x140008465`
- `ntoskrnl!CmRegisterCallback` at `0x140008465`
- `ntoskrnl!ZwClose` at `0x1400081ec`
- `ntoskrnl!ZwClose` at `0x140008495`
- `ntoskrnl!ZwClose` at `0x1400081ec`
- `ntoskrnl!ZwClose` at `0x140008495`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008150`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400081d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008150`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400081d1`
- `ntoskrnl!ZwQueryValueKey` at `0x14000819e`
- `ntoskrnl!ZwQueryValueKey` at `0x14000819e`
- `ntoskrnl!ZwOpenKey` at `0x140008127`
- `ntoskrnl!ZwOpenKey` at `0x140008127`
- `ntoskrnl!EtwRegister` at `0x1400082b4`
- `ntoskrnl!EtwRegister` at `0x1400082fd`
- `ntoskrnl!EtwRegister` at `0x1400082b4`
- `ntoskrnl!EtwRegister` at `0x1400082fd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008223`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008223`
- `ntoskrnl!EtwUnregister` at `0x1400084bd`
- `ntoskrnl!EtwUnregister` at `0x1400084d5`
- `ntoskrnl!EtwUnregister` at `0x1400084bd`
- `ntoskrnl!EtwUnregister` at `0x1400084d5`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400084f4`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400084f4`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140008513`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140008513`
- `ntoskrnl!ExAllocatePool2` at `0x14000816a`
- `ntoskrnl!ExAllocatePool2` at `0x14000816a`
- `ntoskrnl!ZwCreateFile` at `0x140008361`
- `ntoskrnl!ZwCreateFile` at `0x140008361`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400083bf`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400083bf`
- `ntoskrnl!EtwSetInformation` at `0x1400082d9`
- `ntoskrnl!EtwSetInformation` at `0x1400082d9`
- `FLTMGR!FltStartFiltering` at `0x140008443`
- `FLTMGR!FltStartFiltering` at `0x140008443`
- `FLTMGR!FltRegisterFilter` at `0x14000842a`
- `FLTMGR!FltRegisterFilter` at `0x14000842a`
- `FLTMGR!FltUnregisterFilter` at `0x140008482`
- `FLTMGR!FltUnregisterFilter` at `0x140008482`

## string_xrefs

- `0x1400080c0`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v2; // di
  __int64 Pool2; // rbx
  __int64 Length; // rsi
  NTSTATUS v6; // eax
  PVOID SystemRoutineAddress; // rax
  int started; // ebx
  REGHANDLE v10; // rcx
  _BYTE v11[4]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ResultLength; // [rsp+64h] [rbp-9Ch] BYREF
  void *KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v15[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES v16; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+F0h] [rbp-10h] BYREF

  v15[0] = 10879140;
  *(_QWORD *)&ValueName.Length = 1179664;
  v2 = 0;
  KeyHandle = 0;
  v15[1] = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ValueName.Buffer = L"DISABLED";
  ResultLength = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v15;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  memset(&v16, 0, 44);
  Pool2 = 0;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    while ( 1 )
    {
      Length = ResultLength;
      if ( Pool2 )
        ExFreePoolWithTag((PVOID)Pool2, 0x52746D73u);
      Pool2 = ExAllocatePool2(258, Length, 1383361907);
      if ( !Pool2 )
        break;
      v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, (PVOID)Pool2, Length, &ResultLength);
      if ( v6 != -2147483643 )
      {
        if ( v6 >= 0 && *(_DWORD *)(Pool2 + 4) == 11 && *(_DWORD *)(Pool2 + 8) == 8 && *(_QWORD *)(Pool2 + 12) )
          v2 = 1;
        ExFreePoolWithTag((PVOID)Pool2, 0x52746D73u);
        break;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v2 )
    return -1073741823;
  v11[0] = 0;
  ValueName.Buffer = L"NtQuerySystemInformation";
  *(_QWORD *)&ValueName.Length = 3276848;
  SystemRoutineAddress = MmGetSystemRoutineAddress(&ValueName);
  if ( SystemRoutineAddress
    && ((int (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))SystemRoutineAddress)(227, v11, 1, 0) >= 0
    && v11[0] )
  {
    ExPoolZeroingNativelySupported = 1;
  }
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  ValueName = (struct _UNICODE_STRING)*((_OWORD *)EventInformation - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_140004038 = 0;
  if ( !EtwRegister((LPCGUID)&ValueName, tlgEnableCallback, &dword_140004010, &RegHandle) )
    EtwSetInformation(RegHandle, EventProviderSetTraits, EventInformation, *(unsigned __int16 *)EventInformation);
  wil_InitializeFeatureStaging();
  EtwRegister(&SrpEventProviderId, 0, 0, &g_EtwEventHandle);
  v16.Length = 48;
  v16.RootDirectory = 0;
  v16.Attributes = 576;
  v16.ObjectName = (PUNICODE_STRING)&qword_140003150;
  *(_OWORD *)&v16.SecurityDescriptor = 0;
  started = ZwCreateFile(&Handle, 0x40000000u, &v16, &IoStatusBlock, 0, 0, 3u, 1u, 0, 0, 0);
  if ( started < 0 )
    goto LABEL_30;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  started = ZwDeviceIoControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x22A014u, 0, 0, &ObjectAttributes, 0x30u);
  if ( started < 0 )
    goto LABEL_30;
  Resource = *(PERESOURCE *)&ObjectAttributes.Length;
  qword_1400040D0 = (__int64)ObjectAttributes.RootDirectory;
  qword_1400040C8 = (__int64)ObjectAttributes.ObjectName;
  qword_140004078 = *(_QWORD *)&ObjectAttributes.Attributes;
  qword_140004098 = (__int64)ObjectAttributes.SecurityDescriptor;
  qword_140004080 = (__int64)ObjectAttributes.SecurityQualityOfService;
  started = FltRegisterFilter(DriverObject, &FilterRegistration, &Filter);
  if ( started < 0 )
    goto LABEL_30;
  started = FltStartFiltering(Filter);
  if ( started < 0 || (started = CmRegisterCallback(SmpRegistryCallback, 0, &Cookie), started < 0) )
  {
    FltUnregisterFilter(Filter);
LABEL_30:
    ZwClose(Handle);
    v10 = RegHandle;
    Handle = 0;
    dword_140004010 = 0;
    RegHandle = 0;
    EtwUnregister(v10);
    if ( g_EtwEventHandle )
    {
      EtwUnregister(g_EtwEventHandle);
      g_EtwEventHandle = 0;
    }
    if ( g_wil_details_featureChangeNotification )
    {
      RtlUnregisterFeatureConfigurationChangeNotification();
      g_wil_details_featureChangeNotification = 0;
    }
    if ( g_wil_details_featureUsageProvider )
    {
      RtlUnregisterFeatureUsageProvider();
      g_wil_details_featureUsageProvider = 0;
    }
    g_wil_details_isFeatureStagingInitialized = 0;
  }
  return started;
}

```

## disassembly

```asm
0x140008078  mov     [rsp-8+arg_8], rbx
0x14000807d  mov     [rsp-8+arg_10], rsi
0x140008082  push    rbp
0x140008083  push    rdi
0x140008084  push    r13
0x140008086  push    r14
0x140008088  push    r15
0x14000808a  lea     rbp, [rsp-10h]
0x14000808f  sub     rsp, 110h
0x140008096  mov     rax, cs:__security_cookie
0x14000809d  xor     rax, rsp
0x1400080a0  mov     [rbp+30h+var_30], rax
0x1400080a4  xorps   xmm0, xmm0
0x1400080a7  mov     [rbp+30h+var_90], 0A600A4h
0x1400080af  xor     r15d, r15d
0x1400080b2  mov     qword ptr [rbp+30h+ValueName.Length], 120010h
0x1400080ba  xor     eax, eax
0x1400080bc  movzx   edi, r15b
0x1400080c0  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x1400080c7  mov     [rsp+130h+KeyHandle], r15
0x1400080cc  mov     [rbp+30h+var_88], rax
0x1400080d0  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1400080d5  lea     rax, aDisabled; "DISABLED"
0x1400080dc  mov     qword ptr [rbp+30h+ObjectAttributes.Attributes], 240h
0x1400080e4  mov     [rbp+30h+ValueName.Buffer], rax
0x1400080e8  lea     esi, [r15+30h]
0x1400080ec  lea     rax, [rbp+30h+var_90]
0x1400080f0  mov     [rsp+130h+var_CC], esi
0x1400080f4  mov     r14, rcx
0x1400080f7  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x1400080fb  movups  xmmword ptr [rbp+30h+var_80.ObjectName], xmm0
0x1400080ff  mov     edx, 20019h; DesiredAccess
0x140008104  mov     qword ptr [rsp+130h+ObjectAttributes.Length], rsi
0x140008109  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14000810e  mov     [rsp+130h+ObjectAttributes.RootDirectory], r15
0x140008113  movups  xmmword ptr [rbp+30h+var_80.Length], xmm0
0x140008117  mov     ebx, r15d
0x14000811a  movups  xmmword ptr [rbp+30h+var_80+1Ch], xmm0
0x14000811e  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x140008122  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x140008127  call    cs:__imp_ZwOpenKey
0x14000812e  nop     dword ptr [rax+rax+00h]
0x140008133  lea     r13d, [r15+1]
0x140008137  test    eax, eax
0x140008139  js      loc_1400081E2
0x14000813f  mov     esi, [rsp+130h+var_CC]
0x140008143  test    rbx, rbx
0x140008146  jz      short loc_14000815C
0x140008148  mov     edx, 52746D73h; Tag
0x14000814d  mov     rcx, rbx; P
0x140008150  call    cs:__imp_ExFreePoolWithTag
0x140008157  nop     dword ptr [rax+rax+00h]
0x14000815c  mov     rdx, rsi
0x14000815f  mov     ecx, 102h
0x140008164  mov     r8d, 52746D73h
0x14000816a  call    cs:__imp_ExAllocatePool2
0x140008171  nop     dword ptr [rax+rax+00h]
0x140008176  mov     rbx, rax
0x140008179  test    rax, rax
0x14000817c  jz      short loc_1400081DD
0x14000817e  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140008183  lea     rax, [rsp+130h+var_CC]
0x140008188  mov     [rsp+130h+ResultLength], rax; ResultLength
0x14000818d  lea     rdx, [rbp+30h+ValueName]; ValueName
0x140008191  mov     r9, rbx; KeyValueInformation
0x140008194  mov     [rsp+130h+Length], esi; Length
0x140008198  mov     r8d, 2; KeyValueInformationClass
0x14000819e  call    cs:__imp_ZwQueryValueKey
0x1400081a5  nop     dword ptr [rax+rax+00h]
0x1400081aa  cmp     eax, 80000005h
0x1400081af  jz      short loc_14000813F
0x1400081b1  test    eax, eax
0x1400081b3  js      short loc_1400081C9
0x1400081b5  cmp     dword ptr [rbx+4], 0Bh
0x1400081b9  jnz     short loc_1400081C9
0x1400081bb  cmp     dword ptr [rbx+8], 8
0x1400081bf  jnz     short loc_1400081C9
0x1400081c1  cmp     [rbx+0Ch], r15
0x1400081c5  cmovnz  edi, r13d
0x1400081c9  mov     edx, 52746D73h; Tag
0x1400081ce  mov     rcx, rbx; P
0x1400081d1  call    cs:__imp_ExFreePoolWithTag
0x1400081d8  nop     dword ptr [rax+rax+00h]
0x1400081dd  mov     esi, 30h ; '0'
0x1400081e2  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x1400081e7  test    rcx, rcx
0x1400081ea  jz      short loc_1400081F8
0x1400081ec  call    cs:__imp_ZwClose
0x1400081f3  nop     dword ptr [rax+rax+00h]
0x1400081f8  test    dil, dil
0x1400081fb  jz      short loc_140008207
0x1400081fd  mov     eax, 0C0000001h
0x140008202  jmp     loc_14000852F
0x140008207  lea     rax, aNtquerysystemi; "NtQuerySystemInformation"
0x14000820e  mov     [rsp+130h+var_D0], r15b
0x140008213  lea     rcx, [rbp+30h+ValueName]; SystemRoutineName
0x140008217  mov     [rbp+30h+ValueName.Buffer], rax
0x14000821b  mov     qword ptr [rbp+30h+ValueName.Length], 320030h
0x140008223  call    cs:__imp_MmGetSystemRoutineAddress
0x14000822a  nop     dword ptr [rax+rax+00h]
0x14000822f  test    rax, rax
0x140008232  jz      short loc_14000825B
0x140008234  xor     r9d, r9d
0x140008237  lea     rdx, [rsp+130h+var_D0]
0x14000823c  mov     r8d, r13d
0x14000823f  mov     ecx, 0E3h
0x140008244  call    _guard_dispatch_icall
0x140008249  test    eax, eax
0x14000824b  js      short loc_14000825B
0x14000824d  cmp     [rsp+130h+var_D0], r15b
0x140008252  jz      short loc_14000825B
0x140008254  mov     cs:ExPoolZeroingNativelySupported, r13b
0x14000825b  cmp     cs:RegHandle, r15
0x140008262  mov     ebx, 40000000h
0x140008267  mov     rax, cs:EventInformation
0x14000826e  mov     cs:ExDefaultNonPagedPoolType, 200h
0x140008278  mov     cs:ExDefaultMdlProtection, ebx
0x14000827e  movups  xmm0, xmmword ptr [rax-10h]
0x140008282  movdqu  xmmword ptr [rbp+30h+ValueName.Length], xmm0
0x140008287  jz      short loc_140008290
0x140008289  mov     ecx, 5
0x14000828e  int     29h; Win8: RtlFailFast(ecx)
0x140008290  xorps   xmm0, xmm0
0x140008293  lea     r9, RegHandle; RegHandle
0x14000829a  lea     r8, dword_140004010; CallbackContext
0x1400082a1  lea     rdx, _tlgEnableCallback; EnableCallback
0x1400082a8  lea     rcx, [rbp+30h+ValueName]; ProviderId
0x1400082ac  movdqu  cs:xmmword_140004038, xmm0
0x1400082b4  call    cs:__imp_EtwRegister
0x1400082bb  nop     dword ptr [rax+rax+00h]
0x1400082c0  test    eax, eax
0x1400082c2  jnz     short loc_1400082E5
0x1400082c4  mov     r8, cs:EventInformation; EventInformation
0x1400082cb  lea     edx, [rax+2]; InformationClass
0x1400082ce  mov     rcx, cs:RegHandle; RegHandle
0x1400082d5  movzx   r9d, word ptr [r8]; InformationLength
0x1400082d9  call    cs:__imp_EtwSetInformation
0x1400082e0  nop     dword ptr [rax+rax+00h]
0x1400082e5  call    wil_InitializeFeatureStaging
0x1400082ea  lea     r9, g_EtwEventHandle; RegHandle
0x1400082f1  xor     r8d, r8d; CallbackContext
0x1400082f4  xor     edx, edx; EnableCallback
0x1400082f6  lea     rcx, SrpEventProviderId; ProviderId
0x1400082fd  call    cs:__imp_EtwRegister
0x140008304  nop     dword ptr [rax+rax+00h]
0x140008309  mov     [rsp+130h+EaLength], r15d; EaLength
0x14000830e  lea     rax, qword_140003150
0x140008315  mov     [rsp+130h+EaBuffer], r15; EaBuffer
0x14000831a  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x14000831e  mov     [rsp+130h+CreateOptions], r15d; CreateOptions
0x140008323  lea     r8, [rbp+30h+var_80]; ObjectAttributes
0x140008327  mov     [rsp+130h+CreateDisposition], r13d; CreateDisposition
0x14000832c  lea     rcx, Handle; FileHandle
0x140008333  mov     [rsp+130h+ShareAccess], 3; ShareAccess
0x14000833b  xorps   xmm0, xmm0
0x14000833e  mov     dword ptr [rsp+130h+ResultLength], r15d; FileAttributes
0x140008343  mov     edx, ebx; DesiredAccess
0x140008345  mov     qword ptr [rsp+130h+Length], r15; AllocationSize
0x14000834a  mov     [rbp+30h+var_80.Length], esi
0x14000834d  mov     [rbp+30h+var_80.RootDirectory], r15
0x140008351  mov     [rbp+30h+var_80.Attributes], 240h
0x140008358  mov     [rbp+30h+var_80.ObjectName], rax
0x14000835c  movdqu  xmmword ptr [rbp+30h+var_80.SecurityDescriptor], xmm0
0x140008361  call    cs:__imp_ZwCreateFile
0x140008368  nop     dword ptr [rax+rax+00h]
0x14000836d  mov     ebx, eax
0x14000836f  test    eax, eax
0x140008371  js      loc_14000848E
0x140008377  mov     rcx, cs:Handle; FileHandle
0x14000837e  lea     rax, [rsp+130h+ObjectAttributes]
0x140008383  mov     dword ptr [rsp+130h+EaBuffer], esi; OutputBufferLength
0x140008387  xorps   xmm0, xmm0
0x14000838a  mov     qword ptr [rsp+130h+CreateOptions], rax; OutputBuffer
0x14000838f  xor     r9d, r9d; ApcContext
0x140008392  mov     [rsp+130h+CreateDisposition], r15d; InputBufferLength
0x140008397  lea     rax, [rbp+30h+IoStatusBlock]
0x14000839b  mov     qword ptr [rsp+130h+ShareAccess], r15; InputBuffer
0x1400083a0  xor     r8d, r8d; ApcRoutine
0x1400083a3  mov     dword ptr [rsp+130h+ResultLength], 22A014h; IoControlCode
0x1400083ab  xor     edx, edx; Event
0x1400083ad  mov     qword ptr [rsp+130h+Length], rax; IoStatusBlock
0x1400083b2  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x1400083b7  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x1400083bb  movups  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400083bf  call    cs:__imp_ZwDeviceIoControlFile
0x1400083c6  nop     dword ptr [rax+rax+00h]
0x1400083cb  mov     ebx, eax
0x1400083cd  test    eax, eax
0x1400083cf  js      loc_14000848E
0x1400083d5  mov     rax, qword ptr [rsp+130h+ObjectAttributes.Length]
0x1400083da  lea     r8, Filter; RetFilter
0x1400083e1  mov     cs:Resource, rax
0x1400083e8  lea     rdx, FilterRegistration; Registration
0x1400083ef  mov     rax, [rsp+130h+ObjectAttributes.RootDirectory]
0x1400083f4  mov     rcx, r14; Driver
0x1400083f7  mov     cs:qword_1400040D0, rax
0x1400083fe  mov     rax, [rbp+30h+ObjectAttributes.ObjectName]
0x140008402  mov     cs:qword_1400040C8, rax
0x140008409  mov     rax, qword ptr [rbp+30h+ObjectAttributes.Attributes]
0x14000840d  mov     cs:qword_140004078, rax
0x140008414  mov     rax, [rbp+30h+ObjectAttributes.SecurityDescriptor]
0x140008418  mov     cs:qword_140004098, rax
0x14000841f  mov     rax, [rbp+30h+ObjectAttributes.SecurityQualityOfService]
0x140008423  mov     cs:qword_140004080, rax
0x14000842a  call    cs:__imp_FltRegisterFilter
0x140008431  nop     dword ptr [rax+rax+00h]
0x140008436  mov     ebx, eax
0x140008438  test    eax, eax
0x14000843a  js      short loc_14000848E
0x14000843c  mov     rcx, cs:Filter; Filter
0x140008443  call    cs:__imp_FltStartFiltering
0x14000844a  nop     dword ptr [rax+rax+00h]
0x14000844f  mov     ebx, eax
0x140008451  test    eax, eax
0x140008453  js      short loc_14000847B
0x140008455  lea     r8, Cookie; Cookie
0x14000845c  xor     edx, edx; Context
0x14000845e  lea     rcx, SmpRegistryCallback; Function
0x140008465  call    cs:__imp_CmRegisterCallback
0x14000846c  nop     dword ptr [rax+rax+00h]
0x140008471  mov     ebx, eax
0x140008473  test    eax, eax
0x140008475  jns     loc_14000852D
0x14000847b  mov     rcx, cs:Filter; Filter
0x140008482  call    cs:__imp_FltUnregisterFilter
0x140008489  nop     dword ptr [rax+rax+00h]
0x14000848e  mov     rcx, cs:Handle; Handle
0x140008495  call    cs:__imp_ZwClose
0x14000849c  nop     dword ptr [rax+rax+00h]
0x1400084a1  mov     rcx, cs:RegHandle; RegHandle
0x1400084a8  mov     cs:Handle, r15
0x1400084af  mov     cs:dword_140004010, r15d
0x1400084b6  mov     cs:RegHandle, r15
0x1400084bd  call    cs:__imp_EtwUnregister
0x1400084c4  nop     dword ptr [rax+rax+00h]
0x1400084c9  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1400084d0  test    rcx, rcx
0x1400084d3  jz      short loc_1400084E8
0x1400084d5  call    cs:__imp_EtwUnregister
0x1400084dc  nop     dword ptr [rax+rax+00h]
0x1400084e1  mov     cs:g_EtwEventHandle, r15
0x1400084e8  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400084ef  test    rcx, rcx
0x1400084f2  jz      short loc_140008507
0x1400084f4  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400084fb  nop     dword ptr [rax+rax+00h]
0x140008500  mov     cs:g_wil_details_featureChangeNotification, r15
0x140008507  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000850e  test    rcx, rcx
0x140008511  jz      short loc_140008526
0x140008513  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000851a  nop     dword ptr [rax+rax+00h]
0x14000851f  mov     cs:g_wil_details_featureUsageProvider, r15
0x140008526  mov     cs:g_wil_details_isFeatureStagingInitialized, r15d
0x14000852d  mov     eax, ebx
0x14000852f  mov     rcx, [rbp+30h+var_30]
0x140008533  xor     rcx, rsp; StackCookie
0x140008536  call    __security_check_cookie
0x14000853b  lea     r11, [rsp+130h+var_20]
0x140008543  mov     rbx, [r11+38h]
0x140008547  mov     rsi, [r11+40h]
0x14000854b  mov     rsp, r11
0x14000854e  pop     r15
0x140008550  pop     r14
0x140008552  pop     r13
0x140008554  pop     rdi
0x140008555  pop     rbp
0x140008556  retn
```
