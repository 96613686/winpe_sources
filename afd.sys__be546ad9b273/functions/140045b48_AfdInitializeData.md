# AfdInitializeData

- ea: `0x140045b48`
- end: `0x140045d8e`
- name: `AfdInitializeData`
- size: `582`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14004ac54`

## callees

- `0x140045b48`
- `0x140045d94`
- `0x140072840`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140045d60`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140045d60`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x140045d33`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x140045d33`
- `ntoskrnl!RtlGetVersion` at `0x140045cbb`
- `ntoskrnl!RtlGetVersion` at `0x140045cbb`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140045c6f`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140045c6f`
- `ntoskrnl!InitializeSListHead` at `0x140045c50`
- `ntoskrnl!InitializeSListHead` at `0x140045c63`
- `ntoskrnl!InitializeSListHead` at `0x140045c50`
- `ntoskrnl!InitializeSListHead` at `0x140045c63`
- `ntoskrnl!KeInitializeSpinLock` at `0x140045b82`
- `ntoskrnl!KeInitializeSpinLock` at `0x140045c13`
- `ntoskrnl!KeInitializeSpinLock` at `0x140045b82`
- `ntoskrnl!KeInitializeSpinLock` at `0x140045c13`

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
0x140045b48  mov     [rsp+arg_0], rbx
0x140045b4d  push    rdi
0x140045b4e  sub     rsp, 150h
0x140045b55  mov     rax, cs:__security_cookie
0x140045b5c  xor     rax, rsp
0x140045b5f  mov     [rsp+158h+var_18], rax
0x140045b67  mov     ebx, 11Ch
0x140045b6c  lea     rcx, [rsp+158h+VersionInformation]; void *
0x140045b71  mov     r8d, ebx; Size
0x140045b74  xor     edx, edx; Val
0x140045b76  call    memset
0x140045b7b  lea     rcx, AfdPollListLock; SpinLock
0x140045b82  call    cs:__imp_KeInitializeSpinLock
0x140045b89  nop     dword ptr [rax+rax+00h]
0x140045b8e  lea     rax, AfdEndpointListHead
0x140045b95  mov     cs:qword_140087C28, rax
0x140045b9c  lea     rcx, AfdQueuedTransmitFileSpinLock; SpinLock
0x140045ba3  mov     cs:AfdEndpointListHead, rax
0x140045baa  lea     rax, AfdPollListHead
0x140045bb1  mov     cs:qword_140087C48, rax
0x140045bb8  mov     cs:AfdPollListHead, rax
0x140045bbf  lea     rax, AfdTransportInfoListHead
0x140045bc6  mov     cs:qword_140087C68, rax
0x140045bcd  mov     cs:AfdTransportInfoListHead, rax
0x140045bd4  lea     rax, AfdWorkQueueListHead
0x140045bdb  mov     cs:qword_140087CA8, rax
0x140045be2  mov     cs:AfdWorkQueueListHead, rax
0x140045be9  lea     rax, AfdConstrainedEndpointListHead
0x140045bf0  mov     cs:qword_140087C18, rax
0x140045bf7  mov     cs:AfdConstrainedEndpointListHead, rax
0x140045bfe  lea     rax, AfdQueuedTransmitFileListHead
0x140045c05  mov     cs:qword_140087D28, rax
0x140045c0c  mov     cs:AfdQueuedTransmitFileListHead, rax
0x140045c13  call    cs:__imp_KeInitializeSpinLock
0x140045c1a  nop     dword ptr [rax+rax+00h]
0x140045c1f  lea     rax, AfdCompartmentList
0x140045c26  mov     cs:qword_140087D98, rax
0x140045c2d  lea     rcx, AfdLRList; SListHead
0x140045c34  mov     cs:AfdCompartmentList, rax
0x140045c3b  lea     rax, AfdSanHelperList
0x140045c42  mov     cs:qword_140087EA8, rax
0x140045c49  mov     cs:AfdSanHelperList, rax
0x140045c50  call    cs:__imp_InitializeSListHead
0x140045c57  nop     dword ptr [rax+rax+00h]
0x140045c5c  lea     rcx, AfdLRFileMdlList; SListHead
0x140045c63  call    cs:__imp_InitializeSListHead
0x140045c6a  nop     dword ptr [rax+rax+00h]
0x140045c6f  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x140045c76  nop     dword ptr [rax+rax+00h]
0x140045c7b  mov     cs:AfdBufferAlignment, eax
0x140045c81  cmp     eax, 10h
0x140045c84  jnb     short loc_140045C95
0x140045c86  mov     cs:AfdBufferAlignment, 10h
0x140045c90  mov     eax, 10h
0x140045c95  shr     eax, 4
0x140045c98  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x140045c9d  xor     edx, edx; Val
0x140045c9f  mov     cs:AfdAlignmentTableSize, eax
0x140045ca5  mov     r8d, 118h; Size
0x140045cab  call    memset
0x140045cb0  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], ebx
0x140045cb4  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x140045cb9  xor     ebx, ebx
0x140045cbb  call    cs:__imp_RtlGetVersion
0x140045cc2  nop     dword ptr [rax+rax+00h]
0x140045cc7  lea     edi, [rbx+1]
0x140045cca  test    eax, eax
0x140045ccc  js      short loc_140045CD9
0x140045cce  cmp     [rsp+158h+var_1E], dil
0x140045cd6  cmovnz  ebx, edi
0x140045cd9  lea     eax, [rbx+1]
0x140045cdc  mov     cs:AfdTransmitIoLength, 10000h
0x140045ce6  shl     eax, 10h
0x140045ce9  mov     cs:AfdReceiveWindowSize, eax
0x140045cef  mov     cs:AfdSendWindowSize, eax
0x140045cf5  mov     eax, cs:Feature_TCPIP_AfdTdiProviderValidation__private_featureState
0x140045cfb  test    al, 10h
0x140045cfd  jz      short loc_140045D03
0x140045cff  and     eax, edi
0x140045d01  jmp     short loc_140045D08
0x140045d03  call    Feature_TCPIP_AfdTdiProviderValidation__private_IsEnabledDeviceUsageNoInline
0x140045d08  mov     ecx, eax
0x140045d0a  mov     ebx, 2
0x140045d0f  neg     ecx
0x140045d11  mov     ecx, eax
0x140045d13  sbb     edx, edx
0x140045d15  and     edx, ebx
0x140045d17  neg     ecx
0x140045d19  mov     cs:AfdTdiWellKnownProviderValidationLevel, edx
0x140045d1f  sbb     edx, edx
0x140045d21  and     edx, 3
0x140045d24  test    eax, eax
0x140045d26  mov     cs:AfdTdiUnknownProviderValidationLevel, edx
0x140045d2c  setz    cs:AfdAllowTdiFilters
0x140045d33  call    cs:__imp_MmIsThisAnNtAsSystem
0x140045d3a  nop     dword ptr [rax+rax+00h]
0x140045d3f  test    al, al
0x140045d41  jz      short loc_140045D47
0x140045d43  xor     ebx, ebx
0x140045d45  jmp     short loc_140045D51
0x140045d47  mov     cs:AfdTransmitIoLength, 1000h
0x140045d51  mov     edx, edi; Revision
0x140045d53  mov     cs:AfdMaxActiveTransmitFileCount, ebx
0x140045d59  lea     rcx, AfdEmptySd; SecurityDescriptor
0x140045d60  call    cs:__imp_RtlCreateSecurityDescriptor
0x140045d67  nop     dword ptr [rax+rax+00h]
0x140045d6c  mov     rcx, [rsp+158h+var_18]
0x140045d74  xor     rcx, rsp; StackCookie
0x140045d77  call    __security_check_cookie
0x140045d7c  mov     rbx, [rsp+158h+arg_0]
0x140045d84  add     rsp, 150h
0x140045d8b  pop     rdi
0x140045d8c  retn
```
