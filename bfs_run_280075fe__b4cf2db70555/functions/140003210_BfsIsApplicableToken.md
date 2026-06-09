# BfsIsApplicableToken

- ea: `0x140003210`
- end: `0x1400034db`
- name: `BfsIsApplicableToken`
- size: `715`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400010c0`
- `0x140001460`
- `0x140002a30`
- `0x14000411c`
- `0x140009390`
- `0x140009530`
- `0x14000995c`
- `0x140009b9c`

## callees

- `0x140003210`
- `0x1400034e4`
- `0x140013730`

## import_xrefs

- `ntoskrnl!SeTokenObjectType` at `0x140003381`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000339c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000339c`
- `ntoskrnl!ZwClose` at `0x1400034a7`
- `ntoskrnl!ZwClose` at `0x1400034a7`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140003472`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140003472`
- `ntoskrnl!SeQueryInformationToken` at `0x14000325c`
- `ntoskrnl!SeQueryInformationToken` at `0x140003359`
- `ntoskrnl!SeQueryInformationToken` at `0x14000325c`
- `ntoskrnl!SeQueryInformationToken` at `0x140003359`
- `ntoskrnl!EtwWriteTransfer` at `0x140003315`
- `ntoskrnl!EtwWriteTransfer` at `0x140003455`
- `ntoskrnl!EtwWriteTransfer` at `0x140003315`
- `ntoskrnl!EtwWriteTransfer` at `0x140003455`

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
0x140003210  mov     [rsp-8+arg_8], rbx
0x140003215  mov     [rsp-8+arg_10], rsi
0x14000321a  push    rbp
0x14000321b  push    rdi
0x14000321c  push    r14
0x14000321e  lea     rbp, [rsp-47h]
0x140003223  sub     rsp, 0B0h
0x14000322a  mov     rax, cs:__security_cookie
0x140003231  xor     rax, rsp
0x140003234  mov     [rbp+57h+var_20], rax
0x140003238  xor     r14d, r14d
0x14000323b  lea     r8, [rbp+57h+TokenInformation+4]; TokenInformation
0x14000323f  movzx   esi, dl
0x140003242  mov     dword ptr [rbp+57h+TokenInformation+4], r14d
0x140003246  mov     edx, 30h ; '0'; TokenInformationClass
0x14000324b  mov     dword ptr [rbp+57h+TokenInformation], r14d
0x14000324f  mov     [rbp+57h+var_80], r14b
0x140003253  mov     rdi, rcx
0x140003256  mov     [rbp+57h+var_58], r14
0x14000325a  xor     bl, bl
0x14000325c  call    cs:__imp_SeQueryInformationToken
0x140003263  nop     dword ptr [rax+rax+00h]
0x140003268  mov     ecx, eax
0x14000326a  test    eax, eax
0x14000326c  jns     loc_140003326
0x140003272  mov     eax, cs:dword_140019000
0x140003278  cmp     eax, 3
0x14000327b  jbe     loc_140003495
0x140003281  mov     [rbp+57h+var_7C], ecx
0x140003284  lea     rax, [rbp+57h+var_7C]
0x140003288  mov     [rbp+57h+var_30], rax
0x14000328c  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140003290  mov     rax, cs:qword_140016D92
0x140003297  xor     r9d, r9d; RelatedActivityId
0x14000329a  movzx   ecx, ax
0x14000329d  xor     r8d, r8d; ActivityId
0x1400032a0  mov     rax, cs:EventInformation
0x1400032a7  mov     [rbp+57h+var_50.Ptr], rax
0x1400032ab  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x1400032ae  lea     rcx, _TraceLoggingMetadata
0x1400032b5  mov     [rbp+57h+var_28], 4
0x1400032bd  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1400032c4  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x1400032c8  movzx   eax, word ptr [rax]
0x1400032cb  mov     [rbp+57h+var_50.Size], eax
0x1400032ce  lea     rax, dword_140016D9C
0x1400032d5  mov     [rbp+57h+var_40], rax
0x1400032d9  lea     rax, _TraceLoggingMetadataEnd
0x1400032e0  sub     eax, ecx
0x1400032e2  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x1400032e9  mov     [rbp+57h+var_38], 1Eh
0x1400032f0  mov     [rbp+57h+var_34], 1
0x1400032f7  mov     [rbp+57h+var_78], eax
0x1400032fa  mov     eax, [rbp+57h+var_78]
0x1400032fd  mov     rcx, cs:RegHandle; RegHandle
0x140003304  lea     rax, [rbp+57h+var_50]
0x140003308  mov     [rsp+0C0h+UserData], rax; UserData
0x14000330d  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x140003315  call    cs:__imp_EtwWriteTransfer
0x14000331c  nop     dword ptr [rax+rax+00h]
0x140003321  jmp     loc_140003495
0x140003326  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14000332b  test    eax, eax
0x14000332d  jz      loc_14000348E
0x140003333  cmp     dword ptr [rbp+57h+TokenInformation+4], r14d
0x140003337  jz      short loc_140003340
0x140003339  mov     bl, 1
0x14000333b  jmp     loc_140003495
0x140003340  test    sil, sil
0x140003343  jz      loc_140003495
0x140003349  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14000334d  mov     dword ptr [rbp+57h+TokenInformation], r14d
0x140003351  mov     edx, 1Dh; TokenInformationClass
0x140003356  mov     rcx, rdi; Token
0x140003359  call    cs:__imp_SeQueryInformationToken
0x140003360  nop     dword ptr [rax+rax+00h]
0x140003365  cmp     dword ptr [rbp+57h+TokenInformation], r14d
0x140003369  jz      loc_140003495
0x14000336f  lea     rax, [rbp+57h+var_58]
0x140003373  mov     r9d, 8; DesiredAccess
0x140003379  mov     [rsp+0C0h+Handle], rax; Handle
0x14000337e  xor     r8d, r8d; PassedAccessState
0x140003381  mov     rax, cs:__imp_SeTokenObjectType
0x140003388  mov     rcx, rdi; Object
0x14000338b  mov     byte ptr [rsp+0C0h+UserData], bl; AccessMode
0x14000338f  mov     rdx, [rax]
0x140003392  mov     qword ptr [rsp+0C0h+UserDataCount], rdx; ObjectType
0x140003397  mov     edx, 200h; HandleAttributes
0x14000339c  call    cs:__imp_ObOpenObjectByPointer
0x1400033a3  nop     dword ptr [rax+rax+00h]
0x1400033a8  mov     ecx, eax
0x1400033aa  test    eax, eax
0x1400033ac  jns     loc_140003463
0x1400033b2  mov     eax, cs:dword_140019000
0x1400033b8  cmp     eax, 3
0x1400033bb  jbe     loc_140003495
0x1400033c1  mov     [rbp+57h+var_78], ecx
0x1400033c4  lea     rax, [rbp+57h+var_78]
0x1400033c8  mov     [rbp+57h+var_30], rax
0x1400033cc  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400033d0  mov     rax, cs:qword_140016D92
0x1400033d7  xor     r9d, r9d; RelatedActivityId
0x1400033da  movzx   ecx, ax
0x1400033dd  xor     r8d, r8d; ActivityId
0x1400033e0  mov     rax, cs:EventInformation
0x1400033e7  mov     [rbp+57h+var_50.Ptr], rax
0x1400033eb  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x1400033ee  lea     rcx, _TraceLoggingMetadata
0x1400033f5  mov     [rbp+57h+var_28], 4
0x1400033fd  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140003404  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x140003408  movzx   eax, word ptr [rax]
0x14000340b  mov     [rbp+57h+var_50.Size], eax
0x14000340e  lea     rax, dword_140016D9C
0x140003415  mov     [rbp+57h+var_40], rax
0x140003419  lea     rax, _TraceLoggingMetadataEnd
0x140003420  sub     eax, ecx
0x140003422  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x140003429  mov     [rbp+57h+var_38], 1Eh
0x140003430  mov     [rbp+57h+var_34], 1
0x140003437  mov     [rbp+57h+var_7C], eax
0x14000343a  mov     eax, [rbp+57h+var_7C]
0x14000343d  mov     rcx, cs:RegHandle; RegHandle
0x140003444  lea     rax, [rbp+57h+var_50]
0x140003448  mov     [rsp+0C0h+UserData], rax; UserData
0x14000344d  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x140003455  call    cs:__imp_EtwWriteTransfer
0x14000345c  nop     dword ptr [rax+rax+00h]
0x140003461  jmp     short loc_140003495
0x140003463  mov     rdx, cs:gApplicableCapabilitySid
0x14000346a  lea     r8, [rbp+57h+var_80]
0x14000346e  mov     rcx, [rbp+57h+var_58]
0x140003472  call    cs:__imp_RtlCheckTokenCapability
0x140003479  nop     dword ptr [rax+rax+00h]
0x14000347e  mov     ecx, eax
0x140003480  test    eax, eax
0x140003482  js      loc_1400033B2
0x140003488  movzx   ebx, [rbp+57h+var_80]
0x14000348c  jmp     short loc_140003495
0x14000348e  cmp     dword ptr [rbp+57h+TokenInformation+4], r14d
0x140003492  setnz   bl
0x140003495  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14000349a  test    eax, eax
0x14000349c  jz      short loc_1400034B3
0x14000349e  mov     rcx, [rbp+57h+var_58]; Handle
0x1400034a2  test    rcx, rcx
0x1400034a5  jz      short loc_1400034B3
0x1400034a7  call    cs:__imp_ZwClose
0x1400034ae  nop     dword ptr [rax+rax+00h]
0x1400034b3  movzx   eax, bl
0x1400034b6  mov     rcx, [rbp+57h+var_20]
0x1400034ba  xor     rcx, rsp; StackCookie
0x1400034bd  call    __security_check_cookie
0x1400034c2  lea     r11, [rsp+0C0h+var_10]
0x1400034ca  mov     rbx, [r11+28h]
0x1400034ce  mov     rsi, [r11+30h]
0x1400034d2  mov     rsp, r11
0x1400034d5  pop     r14
0x1400034d7  pop     rdi
0x1400034d8  pop     rbp
0x1400034d9  retn
```
