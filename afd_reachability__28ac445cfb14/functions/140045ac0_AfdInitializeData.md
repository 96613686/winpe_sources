# AfdInitializeData

- ea: `0x140045ac0`
- end: `0x140045d06`
- name: `AfdInitializeData`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14004abb4`

## callees

- `0x140045ac0`
- `0x140045d0c`
- `0x1400726a0`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140045cd8`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140045cd8`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x140045cab`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x140045cab`
- `ntoskrnl!RtlGetVersion` at `0x140045c33`
- `ntoskrnl!RtlGetVersion` at `0x140045c33`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140045be7`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140045be7`
- `ntoskrnl!InitializeSListHead` at `0x140045bc8`
- `ntoskrnl!InitializeSListHead` at `0x140045bdb`
- `ntoskrnl!InitializeSListHead` at `0x140045bc8`
- `ntoskrnl!InitializeSListHead` at `0x140045bdb`
- `ntoskrnl!KeInitializeSpinLock` at `0x140045afa`
- `ntoskrnl!KeInitializeSpinLock` at `0x140045b8b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140045afa`
- `ntoskrnl!KeInitializeSpinLock` at `0x140045b8b`

## pseudocode

```c
NTSTATUS AfdInitializeData()
{
  ULONG RecommendedSharedDataAlignment; // eax
  BOOL v1; // ebx
  int IsEnabledDeviceUsageNoInline; // eax
  int v3; // ebx
  _BYTE VersionInformation[284]; // [rsp+20h] [rbp-138h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  KeInitializeSpinLock(&AfdPollListLock);
  qword_140087C28 = (__int64)&AfdEndpointListHead;
  AfdEndpointListHead = (__int64)&AfdEndpointListHead;
  qword_140087C48 = (__int64)&AfdPollListHead;
  AfdPollListHead = (__int64)&AfdPollListHead;
  qword_140087C68 = (__int64)&AfdTransportInfoListHead;
  AfdTransportInfoListHead = (__int64)&AfdTransportInfoListHead;
  qword_140087CA8 = (__int64)&AfdWorkQueueListHead;
  AfdWorkQueueListHead = (__int64)&AfdWorkQueueListHead;
  qword_140087C18 = (__int64)&AfdConstrainedEndpointListHead;
  AfdConstrainedEndpointListHead = (__int64)&AfdConstrainedEndpointListHead;
  qword_140087D28 = (__int64)&AfdQueuedTransmitFileListHead;
  AfdQueuedTransmitFileListHead = (__int64)&AfdQueuedTransmitFileListHead;
  KeInitializeSpinLock(&AfdQueuedTransmitFileSpinLock);
  qword_140087D98 = (__int64)&AfdCompartmentList;
  AfdCompartmentList = (__int64)&AfdCompartmentList;
  qword_140087EA8 = (__int64)&AfdSanHelperList;
  AfdSanHelperList = (__int64)&AfdSanHelperList;
  InitializeSListHead(&AfdLRList);
  InitializeSListHead(&AfdLRFileMdlList);
  RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
  AfdBufferAlignment = RecommendedSharedDataAlignment;
  if ( RecommendedSharedDataAlignment < 0x10 )
  {
    AfdBufferAlignment = 16;
    RecommendedSharedDataAlignment = 16;
  }
  LODWORD(AfdAlignmentTableSize) = RecommendedSharedDataAlignment >> 4;
  memset(&VersionInformation[4], 0, 0x118u);
  *(_DWORD *)VersionInformation = 284;
  v1 = 0;
  if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0 )
    v1 = VersionInformation[282] != 1;
  AfdTransmitIoLength = 0x10000;
  AfdReceiveWindowSize = (v1 + 1) << 16;
  AfdSendWindowSize = (v1 + 1) << 16;
  if ( (Feature_TCPIP_AfdTdiProviderValidation__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_AfdTdiProviderValidation__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_AfdTdiProviderValidation__private_IsEnabledDeviceUsageNoInline();
  v3 = 2;
  AfdTdiWellKnownProviderValidationLevel = IsEnabledDeviceUsageNoInline != 0 ? 2 : 0;
  AfdTdiUnknownProviderValidationLevel = IsEnabledDeviceUsageNoInline != 0 ? 3 : 0;
  AfdAllowTdiFilters = IsEnabledDeviceUsageNoInline == 0;
  if ( MmIsThisAnNtAsSystem() )
    v3 = 0;
  else
    AfdTransmitIoLength = 4096;
  AfdMaxActiveTransmitFileCount = v3;
  return RtlCreateSecurityDescriptor(AfdEmptySd, 1u);
}

```

## disassembly

```asm
0x140045ac0  mov     [rsp+arg_0], rbx
0x140045ac5  push    rdi
0x140045ac6  sub     rsp, 150h
0x140045acd  mov     rax, cs:__security_cookie
0x140045ad4  xor     rax, rsp
0x140045ad7  mov     [rsp+158h+var_18], rax
0x140045adf  mov     ebx, 11Ch
0x140045ae4  lea     rcx, [rsp+158h+VersionInformation]; void *
0x140045ae9  mov     r8d, ebx; Size
0x140045aec  xor     edx, edx; Val
0x140045aee  call    memset
0x140045af3  lea     rcx, AfdPollListLock; SpinLock
0x140045afa  call    cs:__imp_KeInitializeSpinLock
0x140045b01  nop     dword ptr [rax+rax+00h]
0x140045b06  lea     rax, AfdEndpointListHead
0x140045b0d  mov     cs:qword_140087C28, rax
0x140045b14  lea     rcx, AfdQueuedTransmitFileSpinLock; SpinLock
0x140045b1b  mov     cs:AfdEndpointListHead, rax
0x140045b22  lea     rax, AfdPollListHead
0x140045b29  mov     cs:qword_140087C48, rax
0x140045b30  mov     cs:AfdPollListHead, rax
0x140045b37  lea     rax, AfdTransportInfoListHead
0x140045b3e  mov     cs:qword_140087C68, rax
0x140045b45  mov     cs:AfdTransportInfoListHead, rax
0x140045b4c  lea     rax, AfdWorkQueueListHead
0x140045b53  mov     cs:qword_140087CA8, rax
0x140045b5a  mov     cs:AfdWorkQueueListHead, rax
0x140045b61  lea     rax, AfdConstrainedEndpointListHead
0x140045b68  mov     cs:qword_140087C18, rax
0x140045b6f  mov     cs:AfdConstrainedEndpointListHead, rax
0x140045b76  lea     rax, AfdQueuedTransmitFileListHead
0x140045b7d  mov     cs:qword_140087D28, rax
0x140045b84  mov     cs:AfdQueuedTransmitFileListHead, rax
0x140045b8b  call    cs:__imp_KeInitializeSpinLock
0x140045b92  nop     dword ptr [rax+rax+00h]
0x140045b97  lea     rax, AfdCompartmentList
0x140045b9e  mov     cs:qword_140087D98, rax
0x140045ba5  lea     rcx, AfdLRList; SListHead
0x140045bac  mov     cs:AfdCompartmentList, rax
0x140045bb3  lea     rax, AfdSanHelperList
0x140045bba  mov     cs:qword_140087EA8, rax
0x140045bc1  mov     cs:AfdSanHelperList, rax
0x140045bc8  call    cs:__imp_InitializeSListHead
0x140045bcf  nop     dword ptr [rax+rax+00h]
0x140045bd4  lea     rcx, AfdLRFileMdlList; SListHead
0x140045bdb  call    cs:__imp_InitializeSListHead
0x140045be2  nop     dword ptr [rax+rax+00h]
0x140045be7  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x140045bee  nop     dword ptr [rax+rax+00h]
0x140045bf3  mov     cs:AfdBufferAlignment, eax
0x140045bf9  cmp     eax, 10h
0x140045bfc  jnb     short loc_140045C0D
0x140045bfe  mov     cs:AfdBufferAlignment, 10h
0x140045c08  mov     eax, 10h
0x140045c0d  shr     eax, 4
0x140045c10  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x140045c15  xor     edx, edx; Val
0x140045c17  mov     cs:AfdAlignmentTableSize, eax
0x140045c1d  mov     r8d, 118h; Size
0x140045c23  call    memset
0x140045c28  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], ebx
0x140045c2c  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x140045c31  xor     ebx, ebx
0x140045c33  call    cs:__imp_RtlGetVersion
0x140045c3a  nop     dword ptr [rax+rax+00h]
0x140045c3f  lea     edi, [rbx+1]
0x140045c42  test    eax, eax
0x140045c44  js      short loc_140045C51
0x140045c46  cmp     [rsp+158h+var_1E], dil
0x140045c4e  cmovnz  ebx, edi
0x140045c51  lea     eax, [rbx+1]
0x140045c54  mov     cs:AfdTransmitIoLength, 10000h
0x140045c5e  shl     eax, 10h
0x140045c61  mov     cs:AfdReceiveWindowSize, eax
0x140045c67  mov     cs:AfdSendWindowSize, eax
0x140045c6d  mov     eax, cs:Feature_TCPIP_AfdTdiProviderValidation__private_featureState
0x140045c73  test    al, 10h
0x140045c75  jz      short loc_140045C7B
0x140045c77  and     eax, edi
0x140045c79  jmp     short loc_140045C80
0x140045c7b  call    Feature_TCPIP_AfdTdiProviderValidation__private_IsEnabledDeviceUsageNoInline
0x140045c80  mov     ecx, eax
0x140045c82  mov     ebx, 2
0x140045c87  neg     ecx
0x140045c89  mov     ecx, eax
0x140045c8b  sbb     edx, edx
0x140045c8d  and     edx, ebx
0x140045c8f  neg     ecx
0x140045c91  mov     cs:AfdTdiWellKnownProviderValidationLevel, edx
0x140045c97  sbb     edx, edx
0x140045c99  and     edx, 3
0x140045c9c  test    eax, eax
0x140045c9e  mov     cs:AfdTdiUnknownProviderValidationLevel, edx
0x140045ca4  setz    cs:AfdAllowTdiFilters
0x140045cab  call    cs:__imp_MmIsThisAnNtAsSystem
0x140045cb2  nop     dword ptr [rax+rax+00h]
0x140045cb7  test    al, al
0x140045cb9  jz      short loc_140045CBF
0x140045cbb  xor     ebx, ebx
0x140045cbd  jmp     short loc_140045CC9
0x140045cbf  mov     cs:AfdTransmitIoLength, 1000h
0x140045cc9  mov     edx, edi; Revision
0x140045ccb  mov     cs:AfdMaxActiveTransmitFileCount, ebx
0x140045cd1  lea     rcx, AfdEmptySd; SecurityDescriptor
0x140045cd8  call    cs:__imp_RtlCreateSecurityDescriptor
0x140045cdf  nop     dword ptr [rax+rax+00h]
0x140045ce4  mov     rcx, [rsp+158h+var_18]
0x140045cec  xor     rcx, rsp; StackCookie
0x140045cef  call    __security_check_cookie
0x140045cf4  mov     rbx, [rsp+158h+arg_0]
0x140045cfc  add     rsp, 150h
0x140045d03  pop     rdi
0x140045d04  retn
```
