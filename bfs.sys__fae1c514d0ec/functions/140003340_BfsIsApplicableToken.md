# BfsIsApplicableToken

- ea: `0x140003340`
- end: `0x14000360b`
- name: `BfsIsApplicableToken`
- size: `715`
- prototype: `_BOOL8 __fastcall(PVOID Object, char)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400010c0`
- `0x140002620`
- `0x140002d30`
- `0x14000424c`
- `0x140009520`
- `0x1400096c0`
- `0x140009aec`
- `0x140009d2c`

## callees

- `0x140003340`
- `0x140003614`
- `0x140013860`

## import_xrefs

- `ntoskrnl!SeTokenObjectType` at `0x1400034b1`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400034cc`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400034cc`
- `ntoskrnl!ZwClose` at `0x1400035d7`
- `ntoskrnl!ZwClose` at `0x1400035d7`
- `ntoskrnl!RtlCheckTokenCapability` at `0x1400035a2`
- `ntoskrnl!RtlCheckTokenCapability` at `0x1400035a2`
- `ntoskrnl!SeQueryInformationToken` at `0x14000338c`
- `ntoskrnl!SeQueryInformationToken` at `0x140003489`
- `ntoskrnl!SeQueryInformationToken` at `0x14000338c`
- `ntoskrnl!SeQueryInformationToken` at `0x140003489`
- `ntoskrnl!EtwWriteTransfer` at `0x140003445`
- `ntoskrnl!EtwWriteTransfer` at `0x140003585`
- `ntoskrnl!EtwWriteTransfer` at `0x140003445`
- `ntoskrnl!EtwWriteTransfer` at `0x140003585`

## pseudocode

```c
_BOOL8 __fastcall BfsIsApplicableToken(PVOID Object, char a2)
{
  bool v4; // bl
  NTSTATUS InformationToken; // eax
  __int64 v6; // rcx
  NTSTATUS v7; // eax
  int v8; // eax
  bool v10[4]; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v11; // [rsp+44h] [rbp-25h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-21h] BYREF
  PVOID TokenInformation; // [rsp+4Ch] [rbp-1Dh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-11h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp+7h] BYREF
  int *v17; // [rsp+80h] [rbp+17h]
  int v18; // [rsp+88h] [rbp+1Fh]
  int v19; // [rsp+8Ch] [rbp+23h]
  unsigned int *v20; // [rsp+90h] [rbp+27h]
  __int64 v21; // [rsp+98h] [rbp+2Fh]

  TokenInformation = 0;
  v10[0] = 0;
  Handle = 0;
  v4 = 0;
  InformationToken = SeQueryInformationToken(
                       Object,
                       TokenAppContainerNumber|TokenAuditPolicy,
                       (PVOID *)((char *)&TokenInformation + 4));
  v6 = (unsigned int)InformationToken;
  if ( InformationToken >= 0 )
  {
    if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline((unsigned int)InformationToken) )
    {
      if ( HIDWORD(TokenInformation) )
      {
        v4 = 1;
      }
      else if ( a2 )
      {
        LODWORD(TokenInformation) = 0;
        SeQueryInformationToken(Object, TokenIsAppContainer, &TokenInformation);
        if ( (_DWORD)TokenInformation )
        {
          v7 = ObOpenObjectByPointer(Object, 0x200u, 0, 8u, (POBJECT_TYPE)SeTokenObjectType, 0, &Handle);
          v6 = (unsigned int)v7;
          if ( v7 < 0
            || (v8 = RtlCheckTokenCapability(Handle, gApplicableCapabilitySid, v10), v6 = (unsigned int)v8, v8 < 0) )
          {
            if ( (unsigned int)dword_140019000 > 3 )
            {
              v12 = v6;
              v20 = &v12;
              UserData.Ptr = (ULONGLONG)EventInformation;
              *(_DWORD *)&EventDescriptor.Level = 3;
              v21 = 4;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              EventDescriptor.Keyword = 0;
              UserData.Size = *(unsigned __int16 *)EventInformation;
              v17 = &dword_140016D9C;
              UserData.Reserved = 2;
              v18 = 30;
              v19 = 1;
              v11 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
            }
          }
          else
          {
            v4 = v10[0];
          }
        }
      }
    }
    else
    {
      v4 = HIDWORD(TokenInformation) != 0;
    }
  }
  else if ( (unsigned int)dword_140019000 > 3 )
  {
    v11 = InformationToken;
    v20 = &v11;
    UserData.Ptr = (ULONGLONG)EventInformation;
    *(_DWORD *)&EventDescriptor.Level = 3;
    v21 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)EventInformation;
    v17 = &dword_140016D9C;
    UserData.Reserved = 2;
    v18 = 30;
    v19 = 1;
    v12 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v6) && Handle )
    ZwClose(Handle);
  return v4;
}

```

## disassembly

```asm
0x140003340  mov     [rsp-8+arg_8], rbx
0x140003345  mov     [rsp-8+arg_10], rsi
0x14000334a  push    rbp
0x14000334b  push    rdi
0x14000334c  push    r14
0x14000334e  lea     rbp, [rsp-47h]
0x140003353  sub     rsp, 0B0h
0x14000335a  mov     rax, cs:__security_cookie
0x140003361  xor     rax, rsp
0x140003364  mov     [rbp+57h+var_20], rax
0x140003368  xor     r14d, r14d
0x14000336b  lea     r8, [rbp+57h+TokenInformation+4]; TokenInformation
0x14000336f  movzx   esi, dl
0x140003372  mov     dword ptr [rbp+57h+TokenInformation+4], r14d
0x140003376  mov     edx, 30h ; '0'; TokenInformationClass
0x14000337b  mov     dword ptr [rbp+57h+TokenInformation], r14d
0x14000337f  mov     [rbp+57h+var_80], r14b
0x140003383  mov     rdi, rcx
0x140003386  mov     [rbp+57h+var_58], r14
0x14000338a  xor     bl, bl
0x14000338c  call    cs:__imp_SeQueryInformationToken
0x140003393  nop     dword ptr [rax+rax+00h]
0x140003398  mov     ecx, eax
0x14000339a  test    eax, eax
0x14000339c  jns     loc_140003456
0x1400033a2  mov     eax, cs:dword_140019000
0x1400033a8  cmp     eax, 3
0x1400033ab  jbe     loc_1400035C5
0x1400033b1  mov     [rbp+57h+var_7C], ecx
0x1400033b4  lea     rax, [rbp+57h+var_7C]
0x1400033b8  mov     [rbp+57h+var_30], rax
0x1400033bc  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400033c0  mov     rax, cs:qword_140016D92
0x1400033c7  xor     r9d, r9d; RelatedActivityId
0x1400033ca  movzx   ecx, ax
0x1400033cd  xor     r8d, r8d; ActivityId
0x1400033d0  mov     rax, cs:EventInformation
0x1400033d7  mov     [rbp+57h+var_50.Ptr], rax
0x1400033db  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x1400033de  lea     rcx, _TraceLoggingMetadata
0x1400033e5  mov     [rbp+57h+var_28], 4
0x1400033ed  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1400033f4  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x1400033f8  movzx   eax, word ptr [rax]
0x1400033fb  mov     [rbp+57h+var_50.Size], eax
0x1400033fe  lea     rax, dword_140016D9C
0x140003405  mov     [rbp+57h+var_40], rax
0x140003409  lea     rax, _TraceLoggingMetadataEnd
0x140003410  sub     eax, ecx
0x140003412  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x140003419  mov     [rbp+57h+var_38], 1Eh
0x140003420  mov     [rbp+57h+var_34], 1
0x140003427  mov     [rbp+57h+var_78], eax
0x14000342a  mov     eax, [rbp+57h+var_78]
0x14000342d  mov     rcx, cs:RegHandle; RegHandle
0x140003434  lea     rax, [rbp+57h+var_50]
0x140003438  mov     [rsp+0C0h+UserData], rax; UserData
0x14000343d  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x140003445  call    cs:__imp_EtwWriteTransfer
0x14000344c  nop     dword ptr [rax+rax+00h]
0x140003451  jmp     loc_1400035C5
0x140003456  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14000345b  test    eax, eax
0x14000345d  jz      loc_1400035BE
0x140003463  cmp     dword ptr [rbp+57h+TokenInformation+4], r14d
0x140003467  jz      short loc_140003470
0x140003469  mov     bl, 1
0x14000346b  jmp     loc_1400035C5
0x140003470  test    sil, sil
0x140003473  jz      loc_1400035C5
0x140003479  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14000347d  mov     dword ptr [rbp+57h+TokenInformation], r14d
0x140003481  mov     edx, 1Dh; TokenInformationClass
0x140003486  mov     rcx, rdi; Token
0x140003489  call    cs:__imp_SeQueryInformationToken
0x140003490  nop     dword ptr [rax+rax+00h]
0x140003495  cmp     dword ptr [rbp+57h+TokenInformation], r14d
0x140003499  jz      loc_1400035C5
0x14000349f  lea     rax, [rbp+57h+var_58]
0x1400034a3  mov     r9d, 8; DesiredAccess
0x1400034a9  mov     [rsp+0C0h+Handle], rax; Handle
0x1400034ae  xor     r8d, r8d; PassedAccessState
0x1400034b1  mov     rax, cs:__imp_SeTokenObjectType
0x1400034b8  mov     rcx, rdi; Object
0x1400034bb  mov     byte ptr [rsp+0C0h+UserData], bl; AccessMode
0x1400034bf  mov     rdx, [rax]
0x1400034c2  mov     qword ptr [rsp+0C0h+UserDataCount], rdx; ObjectType
0x1400034c7  mov     edx, 200h; HandleAttributes
0x1400034cc  call    cs:__imp_ObOpenObjectByPointer
0x1400034d3  nop     dword ptr [rax+rax+00h]
0x1400034d8  mov     ecx, eax
0x1400034da  test    eax, eax
0x1400034dc  jns     loc_140003593
0x1400034e2  mov     eax, cs:dword_140019000
0x1400034e8  cmp     eax, 3
0x1400034eb  jbe     loc_1400035C5
0x1400034f1  mov     [rbp+57h+var_78], ecx
0x1400034f4  lea     rax, [rbp+57h+var_78]
0x1400034f8  mov     [rbp+57h+var_30], rax
0x1400034fc  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140003500  mov     rax, cs:qword_140016D92
0x140003507  xor     r9d, r9d; RelatedActivityId
0x14000350a  movzx   ecx, ax
0x14000350d  xor     r8d, r8d; ActivityId
0x140003510  mov     rax, cs:EventInformation
0x140003517  mov     [rbp+57h+var_50.Ptr], rax
0x14000351b  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x14000351e  lea     rcx, _TraceLoggingMetadata
0x140003525  mov     [rbp+57h+var_28], 4
0x14000352d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140003534  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x140003538  movzx   eax, word ptr [rax]
0x14000353b  mov     [rbp+57h+var_50.Size], eax
0x14000353e  lea     rax, dword_140016D9C
0x140003545  mov     [rbp+57h+var_40], rax
0x140003549  lea     rax, _TraceLoggingMetadataEnd
0x140003550  sub     eax, ecx
0x140003552  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x140003559  mov     [rbp+57h+var_38], 1Eh
0x140003560  mov     [rbp+57h+var_34], 1
0x140003567  mov     [rbp+57h+var_7C], eax
0x14000356a  mov     eax, [rbp+57h+var_7C]
0x14000356d  mov     rcx, cs:RegHandle; RegHandle
0x140003574  lea     rax, [rbp+57h+var_50]
0x140003578  mov     [rsp+0C0h+UserData], rax; UserData
0x14000357d  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x140003585  call    cs:__imp_EtwWriteTransfer
0x14000358c  nop     dword ptr [rax+rax+00h]
0x140003591  jmp     short loc_1400035C5
0x140003593  mov     rdx, cs:gApplicableCapabilitySid
0x14000359a  lea     r8, [rbp+57h+var_80]
0x14000359e  mov     rcx, [rbp+57h+var_58]
0x1400035a2  call    cs:__imp_RtlCheckTokenCapability
0x1400035a9  nop     dword ptr [rax+rax+00h]
0x1400035ae  mov     ecx, eax
0x1400035b0  test    eax, eax
0x1400035b2  js      loc_1400034E2
0x1400035b8  movzx   ebx, [rbp+57h+var_80]
0x1400035bc  jmp     short loc_1400035C5
0x1400035be  cmp     dword ptr [rbp+57h+TokenInformation+4], r14d
0x1400035c2  setnz   bl
0x1400035c5  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x1400035ca  test    eax, eax
0x1400035cc  jz      short loc_1400035E3
0x1400035ce  mov     rcx, [rbp+57h+var_58]; Handle
0x1400035d2  test    rcx, rcx
0x1400035d5  jz      short loc_1400035E3
0x1400035d7  call    cs:__imp_ZwClose
0x1400035de  nop     dword ptr [rax+rax+00h]
0x1400035e3  movzx   eax, bl
0x1400035e6  mov     rcx, [rbp+57h+var_20]
0x1400035ea  xor     rcx, rsp; StackCookie
0x1400035ed  call    __security_check_cookie
0x1400035f2  lea     r11, [rsp+0C0h+var_10]
0x1400035fa  mov     rbx, [r11+28h]
0x1400035fe  mov     rsi, [r11+30h]
0x140003602  mov     rsp, r11
0x140003605  pop     r14
0x140003607  pop     rdi
0x140003608  pop     rbp
0x140003609  retn
```
