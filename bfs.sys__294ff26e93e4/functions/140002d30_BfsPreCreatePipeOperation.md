# BfsPreCreatePipeOperation

- ea: `0x140002d30`
- end: `0x140003266`
- name: `BfsPreCreatePipeOperation`
- size: `1334`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002d30`
- `0x140003340`
- `0x140006c84`
- `0x14000b4c8`
- `0x14000b94c`
- `0x14000be9c`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140002f46`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140002f69`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140002f46`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140002f69`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140003233`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140003233`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140003225`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140003225`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400031d2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400031d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400031f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000320c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400031f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000320c`
- `ntoskrnl!SeQueryInformationToken` at `0x140002f86`
- `ntoskrnl!SeQueryInformationToken` at `0x14000305a`
- `ntoskrnl!SeQueryInformationToken` at `0x140002f86`
- `ntoskrnl!SeQueryInformationToken` at `0x14000305a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140002e0e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140002e0e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140002e1d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140002e1d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140002dfa`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140002dfa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002daf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400031bf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002daf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400031bf`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002dc2`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002dc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002dd2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400031de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002dd2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400031de`
- `ntoskrnl!EtwWriteTransfer` at `0x140002f12`
- `ntoskrnl!EtwWriteTransfer` at `0x14000303d`
- `ntoskrnl!EtwWriteTransfer` at `0x140002f12`
- `ntoskrnl!EtwWriteTransfer` at `0x14000303d`
- `FLTMGR!FltGetFileNameInformation` at `0x140002e5b`
- `FLTMGR!FltGetFileNameInformation` at `0x140002e5b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400031a0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400031a0`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140003106`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140003106`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140003143`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140003143`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14000317a`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14000317a`

## pseudocode

```c
__int64 __fastcall BfsPreCreatePipeOperation(PFLT_CALLBACK_DATA Data, __int64 a2, _QWORD *a3)
{
  PACCESS_TOKEN v3; // rdi
  unsigned int v8; // ebx
  char v9; // r12
  BOOLEAN v10; // r13
  struct _KPROCESS *CurrentProcess; // rax
  NTSTATUS v12; // ecx
  NTSTATUS EcpListFromCallbackData; // ecx
  __int64 v14; // rax
  struct _FLT_FILTER *v15; // rcx
  NTSTATUS ExtraCreateParameter; // eax
  unsigned int v17; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-75h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+38h] [rbp-71h] BYREF
  unsigned __int8 CopyOnOpen[7]; // [rsp+39h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-69h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+50h] [rbp-59h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+58h] [rbp-51h] BYREF
  PVOID EcpContext; // [rsp+60h] [rbp-49h] BYREF
  PVOID TokenInformation; // [rsp+68h] [rbp-41h] BYREF
  PVOID P; // [rsp+70h] [rbp-39h] BYREF
  ULONG EcpContextSize; // [rsp+78h] [rbp-31h] BYREF
  PECP_LIST EcpList; // [rsp+80h] [rbp-29h] BYREF
  UNICODE_STRING String2; // [rsp+88h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+98h] [rbp-11h] BYREF
  int *v31; // [rsp+A8h] [rbp-1h]
  int v32; // [rsp+B0h] [rbp+7h]
  int v33; // [rsp+B4h] [rbp+Bh]
  unsigned int *v34; // [rsp+B8h] [rbp+Fh]
  __int64 v35; // [rsp+C0h] [rbp+17h]

  v3 = 0;
  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  EcpContext = 0;
  EcpContextSize = 0;
  EcpList = 0;
  String2 = 0;
  ImpersonationLevel = SecurityAnonymous;
  if ( !Data->RequestorMode )
    return 1;
  v8 = 1;
  v9 = 0;
  FileNameInformation = 0;
  P = 0;
  TokenInformation = 0;
  KeEnterCriticalRegion();
  v10 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( !v10 )
    goto LABEL_31;
  *a3 = 0;
  v3 = PsReferenceImpersonationToken(Data->Thread, CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  if ( v3 )
  {
    v9 = 1;
    if ( ImpersonationLevel < SecurityImpersonation )
      goto LABEL_31;
  }
  else
  {
    CurrentProcess = IoGetCurrentProcess();
    v3 = PsReferencePrimaryToken(CurrentProcess);
  }
  if ( !(unsigned __int8)BfsIsApplicableToken(v3) )
    goto LABEL_31;
  v12 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v17 = v12;
      v34 = &v17;
      UserData.Ptr = (ULONGLONG)EventInformation;
      *(_DWORD *)&EventDescriptor.Level = 3;
      v35 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)EventInformation;
      v31 = &dword_140016D9C;
      UserData.Reserved = 2;
      v32 = 30;
      v33 = 1;
      v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    goto LABEL_31;
  }
  String2 = *(UNICODE_STRING *)BfsGetFileName(&EventDescriptor, FileNameInformation);
  if ( RtlPrefixUnicodeString(&LocalPrefixString, &String2, 1u)
    || RtlPrefixUnicodeString(&SessionsPrefixString, &String2, 1u) )
  {
    EcpListFromCallbackData = FltGetEcpListFromCallbackData(*(PFLT_FILTER *)(a2 + 8), Data, &EcpList);
    if ( EcpListFromCallbackData >= 0 )
    {
      if ( !EcpList )
        goto LABEL_31;
      v15 = *(struct _FLT_FILTER **)(a2 + 8);
      EcpContext = 0;
      ExtraCreateParameter = FltFindExtraCreateParameter(v15, EcpList, &BfsEcpType, &EcpContext, &EcpContextSize);
      EcpListFromCallbackData = 0;
      if ( ExtraCreateParameter != -1073741275 )
        EcpListFromCallbackData = ExtraCreateParameter;
      if ( EcpListFromCallbackData >= 0 )
      {
        if ( EcpContext && !FltIsEcpFromUserMode(*(PFLT_FILTER *)(a2 + 8), EcpContext) )
        {
          v8 = 0;
          *a3 = *((_QWORD *)EcpContext + 1);
        }
        goto LABEL_31;
      }
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_31;
LABEL_15:
      v35 = 4;
      v34 = &v18;
      v18 = EcpListFromCallbackData;
      UserData.Ptr = (ULONGLONG)EventInformation;
      *(_DWORD *)&EventDescriptor.Level = 3;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)EventInformation;
      v31 = &dword_140016D9C;
      UserData.Reserved = 2;
      v32 = 30;
      v33 = 1;
      v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      goto LABEL_31;
    }
LABEL_14:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_31;
    goto LABEL_15;
  }
  EcpListFromCallbackData = SeQueryInformationToken(v3, TokenUser, &TokenInformation);
  if ( EcpListFromCallbackData < 0 )
    goto LABEL_14;
  EcpListFromCallbackData = SeQueryInformationToken(v3, TokenAppContainerSid, &P);
  if ( EcpListFromCallbackData < 0 )
    goto LABEL_14;
  if ( (Data->Iopb->Parameters.Create.Options & 0xFF000000) != 0x1000000 )
  {
LABEL_20:
    v8 = (((int)BfsRedirectNamedPipe(
                  *(PFLT_FILTER *)(a2 + 8),
                  Data,
                  *(PSID *)TokenInformation,
                  *(PSID *)P,
                  (__int64)FileNameInformation,
                  &String2) >> 31)
        & 0xFFFFFFFD)
       + 4;
    goto LABEL_31;
  }
  v14 = BfsAcquireNamedPipeMapping(
          &gBfsPipeMappingTable,
          *(_QWORD *)TokenInformation,
          *(_QWORD *)P,
          &FileNameInformation->Name);
  if ( v14 )
  {
    BfsReleaseNamedPipeMapping(&gBfsPipeMappingTable, v14);
    goto LABEL_20;
  }
LABEL_31:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v10 && !*a3 )
  {
    KeEnterCriticalRegion();
    ExReleaseRundownProtection(&gBfsRundownProtection);
    KeLeaveCriticalRegion();
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v3 )
  {
    if ( v9 )
      PsDereferenceImpersonationToken(v3);
    else
      PsDereferencePrimaryToken(v3);
  }
  return v8;
}

```

## disassembly

```asm
0x140002d30  push    rbp
0x140002d32  push    rbx
0x140002d33  push    rsi
0x140002d34  push    rdi
0x140002d35  push    r14
0x140002d37  push    r15
0x140002d39  lea     rbp, [rsp-2Fh]
0x140002d3e  sub     rsp, 0D8h
0x140002d45  mov     rax, cs:__security_cookie
0x140002d4c  xor     rax, rsp
0x140002d4f  mov     [rbp+57h+var_38], rax
0x140002d53  xor     edi, edi
0x140002d55  mov     [rbp+57h+CopyOnOpen], 0
0x140002d59  xorps   xmm0, xmm0
0x140002d5c  mov     r15, r8
0x140002d5f  mov     r14, rdx
0x140002d62  mov     rsi, rcx
0x140002d65  mov     [rbp+57h+EffectiveOnly], 0
0x140002d69  mov     [rbp+57h+EcpContext], rdi
0x140002d6d  mov     [rbp+57h+EcpContextSize], edi
0x140002d70  mov     [rbp+57h+EcpList], rdi
0x140002d74  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x140002d78  mov     [rbp+57h+ImpersonationLevel], edi
0x140002d7b  cmp     [rcx+50h], dil
0x140002d7f  jnz     short loc_140002D8B
0x140002d81  mov     eax, 1
0x140002d86  jmp     loc_140003249
0x140002d8b  mov     [rsp+100h+arg_18], r12
0x140002d93  mov     ebx, 1
0x140002d98  mov     [rsp+100h+var_30], r13
0x140002da0  xor     r12b, r12b
0x140002da3  mov     [rbp+57h+FileNameInformation], rdi
0x140002da7  mov     [rbp+57h+P], rdi
0x140002dab  mov     [rbp+57h+TokenInformation], rdi
0x140002daf  call    cs:__imp_KeEnterCriticalRegion
0x140002db6  nop     dword ptr [rax+rax+00h]
0x140002dbb  lea     rcx, gBfsRundownProtection; RunRef
0x140002dc2  call    cs:__imp_ExAcquireRundownProtection
0x140002dc9  nop     dword ptr [rax+rax+00h]
0x140002dce  movzx   r13d, al
0x140002dd2  call    cs:__imp_KeLeaveCriticalRegion
0x140002dd9  nop     dword ptr [rax+rax+00h]
0x140002dde  test    r13b, r13b
0x140002de1  jz      loc_140003197
0x140002de7  mov     [r15], rdi
0x140002dea  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x140002dee  mov     rcx, [rsi+8]; Thread
0x140002df2  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x140002df6  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x140002dfa  call    cs:__imp_PsReferenceImpersonationToken
0x140002e01  nop     dword ptr [rax+rax+00h]
0x140002e06  mov     rdi, rax
0x140002e09  test    rax, rax
0x140002e0c  jnz     short loc_140002E2E
0x140002e0e  call    cs:__imp_IoGetCurrentProcess
0x140002e15  nop     dword ptr [rax+rax+00h]
0x140002e1a  mov     rcx, rax; Process
0x140002e1d  call    cs:__imp_PsReferencePrimaryToken
0x140002e24  nop     dword ptr [rax+rax+00h]
0x140002e29  mov     rdi, rax
0x140002e2c  jmp     short loc_140002E3C
0x140002e2e  cmp     [rbp+57h+ImpersonationLevel], 2
0x140002e32  movzx   r12d, bl
0x140002e36  jl      loc_140003197
0x140002e3c  movzx   edx, bl
0x140002e3f  mov     rcx, rdi; Object
0x140002e42  call    BfsIsApplicableToken
0x140002e47  test    al, al
0x140002e49  jz      loc_140003197
0x140002e4f  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140002e53  mov     edx, 101h; NameOptions
0x140002e58  mov     rcx, rsi; CallbackData
0x140002e5b  call    cs:__imp_FltGetFileNameInformation
0x140002e62  nop     dword ptr [rax+rax+00h]
0x140002e67  mov     ecx, eax
0x140002e69  test    eax, eax
0x140002e6b  jns     loc_140002F23
0x140002e71  mov     eax, cs:dword_140019000
0x140002e77  cmp     eax, 3
0x140002e7a  jbe     loc_140003197
0x140002e80  mov     [rbp+57h+var_D0], ecx
0x140002e83  lea     rax, [rbp+57h+var_D0]
0x140002e87  mov     [rbp+57h+var_48], rax
0x140002e8b  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002e8f  mov     rax, cs:qword_140016D92
0x140002e96  xor     esi, esi
0x140002e98  movzx   ecx, ax
0x140002e9b  xor     r9d, r9d; RelatedActivityId
0x140002e9e  mov     rax, cs:EventInformation
0x140002ea5  xor     r8d, r8d; ActivityId
0x140002ea8  mov     [rbp+57h+var_68.Ptr], rax
0x140002eac  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140002eaf  lea     rcx, _TraceLoggingMetadata
0x140002eb6  mov     [rbp+57h+var_40], 4
0x140002ebe  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002ec5  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x140002ec9  movzx   eax, word ptr [rax]
0x140002ecc  mov     [rbp+57h+var_68.Size], eax
0x140002ecf  lea     rax, dword_140016D9C
0x140002ed6  mov     [rbp+57h+var_58], rax
0x140002eda  lea     rax, _TraceLoggingMetadataEnd
0x140002ee1  sub     eax, ecx
0x140002ee3  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x140002eea  mov     [rbp+57h+var_50], 1Eh
0x140002ef1  mov     [rbp+57h+var_4C], ebx
0x140002ef4  mov     [rbp+57h+var_CC], eax
0x140002ef7  mov     eax, [rbp+57h+var_CC]
0x140002efa  mov     rcx, cs:RegHandle; RegHandle
0x140002f01  lea     rax, [rbp+57h+var_68]
0x140002f05  mov     [rsp+100h+UserData], rax; UserData
0x140002f0a  mov     [rsp+100h+UserDataCount], 3; UserDataCount
0x140002f12  call    cs:__imp_EtwWriteTransfer
0x140002f19  nop     dword ptr [rax+rax+00h]
0x140002f1e  jmp     loc_140003197
0x140002f23  mov     rdx, [rbp+57h+FileNameInformation]
0x140002f27  lea     rcx, [rbp+57h+EventDescriptor]
0x140002f2b  call    BfsGetFileName
0x140002f30  movzx   r8d, bl; CaseInSensitive
0x140002f34  lea     rdx, [rbp+57h+String2]; String2
0x140002f38  lea     rcx, LocalPrefixString; String1
0x140002f3f  movups  xmm1, xmmword ptr [rax]
0x140002f42  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x140002f46  call    cs:__imp_RtlPrefixUnicodeString
0x140002f4d  nop     dword ptr [rax+rax+00h]
0x140002f52  test    al, al
0x140002f54  jnz     loc_1400030FB
0x140002f5a  movzx   r8d, bl; CaseInSensitive
0x140002f5e  lea     rdx, [rbp+57h+String2]; String2
0x140002f62  lea     rcx, SessionsPrefixString; String1
0x140002f69  call    cs:__imp_RtlPrefixUnicodeString
0x140002f70  nop     dword ptr [rax+rax+00h]
0x140002f75  test    al, al
0x140002f77  jnz     loc_1400030FB
0x140002f7d  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140002f81  mov     edx, ebx; TokenInformationClass
0x140002f83  mov     rcx, rdi; Token
0x140002f86  call    cs:__imp_SeQueryInformationToken
0x140002f8d  nop     dword ptr [rax+rax+00h]
0x140002f92  mov     ecx, eax
0x140002f94  test    eax, eax
0x140002f96  jns     loc_14000304E
0x140002f9c  mov     eax, cs:dword_140019000
0x140002fa2  cmp     eax, 3
0x140002fa5  jbe     loc_140003197
0x140002fab  xor     esi, esi
0x140002fad  lea     rax, [rbp+57h+var_CC]
0x140002fb1  mov     [rbp+57h+var_40], 4
0x140002fb9  mov     [rbp+57h+var_48], rax
0x140002fbd  mov     rax, cs:qword_140016D92
0x140002fc4  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002fc8  mov     [rbp+57h+var_CC], ecx
0x140002fcb  xor     r9d, r9d; RelatedActivityId
0x140002fce  movzx   ecx, ax
0x140002fd1  xor     r8d, r8d; ActivityId
0x140002fd4  mov     rax, cs:EventInformation
0x140002fdb  mov     [rbp+57h+var_68.Ptr], rax
0x140002fdf  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140002fe2  lea     rcx, _TraceLoggingMetadata
0x140002fe9  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002ff0  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x140002ff4  movzx   eax, word ptr [rax]
0x140002ff7  mov     [rbp+57h+var_68.Size], eax
0x140002ffa  lea     rax, dword_140016D9C
0x140003001  mov     [rbp+57h+var_58], rax
0x140003005  lea     rax, _TraceLoggingMetadataEnd
0x14000300c  sub     eax, ecx
0x14000300e  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x140003015  mov     [rbp+57h+var_50], 1Eh
0x14000301c  mov     [rbp+57h+var_4C], ebx
0x14000301f  mov     [rbp+57h+var_D0], eax
0x140003022  mov     eax, [rbp+57h+var_D0]
0x140003025  mov     rcx, cs:RegHandle; RegHandle
0x14000302c  lea     rax, [rbp+57h+var_68]
0x140003030  mov     [rsp+100h+UserData], rax; UserData
0x140003035  mov     [rsp+100h+UserDataCount], 3; UserDataCount
0x14000303d  call    cs:__imp_EtwWriteTransfer
0x140003044  nop     dword ptr [rax+rax+00h]
0x140003049  jmp     loc_140003197
0x14000304e  lea     r8, [rbp+57h+P]; TokenInformation
0x140003052  mov     edx, 1Fh; TokenInformationClass
0x140003057  mov     rcx, rdi; Token
0x14000305a  call    cs:__imp_SeQueryInformationToken
0x140003061  nop     dword ptr [rax+rax+00h]
0x140003066  mov     ecx, eax
0x140003068  test    eax, eax
0x14000306a  js      loc_140002F9C
0x140003070  mov     rax, [rsi+10h]
0x140003074  mov     ecx, [rax+20h]
0x140003077  and     ecx, 0FF000000h
0x14000307d  cmp     ecx, 1000000h
0x140003083  jnz     short loc_1400030BF
0x140003085  mov     r8, [rbp+57h+P]
0x140003089  lea     rcx, gBfsPipeMappingTable
0x140003090  mov     rdx, [rbp+57h+TokenInformation]
0x140003094  mov     r9, [rbp+57h+FileNameInformation]
0x140003098  add     r9, 8
0x14000309c  mov     r8, [r8]
0x14000309f  mov     rdx, [rdx]
0x1400030a2  call    BfsAcquireNamedPipeMapping
0x1400030a7  test    rax, rax
0x1400030aa  jz      loc_140003197
0x1400030b0  mov     rdx, rax
0x1400030b3  lea     rcx, gBfsPipeMappingTable
0x1400030ba  call    BfsReleaseNamedPipeMapping
0x1400030bf  mov     r9, [rbp+57h+P]
0x1400030c3  lea     rax, [rbp+57h+String2]
0x1400030c7  mov     r8, [rbp+57h+TokenInformation]
0x1400030cb  mov     rdx, rsi; Data
0x1400030ce  mov     rcx, [r14+8]; Filter
0x1400030d2  mov     [rsp+100h+UserData], rax; Source
0x1400030d7  mov     rax, [rbp+57h+FileNameInformation]
0x1400030db  mov     r9, [r9]; PSID
0x1400030de  mov     r8, [r8]; SourceSid
0x1400030e1  mov     qword ptr [rsp+100h+UserDataCount], rax; __int64
0x1400030e6  call    BfsRedirectNamedPipe
0x1400030eb  mov     ebx, eax
0x1400030ed  sar     ebx, 1Fh
0x1400030f0  and     ebx, 0FFFFFFFDh
0x1400030f3  add     ebx, 4
0x1400030f6  jmp     loc_140003197
0x1400030fb  mov     rcx, [r14+8]; Filter
0x1400030ff  lea     r8, [rbp+57h+EcpList]; EcpList
0x140003103  mov     rdx, rsi; CallbackData
0x140003106  call    cs:__imp_FltGetEcpListFromCallbackData
0x14000310d  nop     dword ptr [rax+rax+00h]
0x140003112  mov     ecx, eax
0x140003114  test    eax, eax
0x140003116  js      loc_140002F9C
0x14000311c  mov     rdx, [rbp+57h+EcpList]; EcpList
0x140003120  test    rdx, rdx
0x140003123  jz      short loc_140003197
0x140003125  mov     rcx, [r14+8]; Filter
0x140003129  lea     rax, [rbp+57h+EcpContextSize]
0x14000312d  xor     esi, esi
0x14000312f  mov     qword ptr [rsp+100h+UserDataCount], rax; EcpContextSize
0x140003134  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x140003138  mov     [rbp+57h+EcpContext], rsi
0x14000313c  lea     r8, BfsEcpType; EcpType
0x140003143  call    cs:__imp_FltFindExtraCreateParameter
0x14000314a  nop     dword ptr [rax+rax+00h]
0x14000314f  cmp     eax, 0C0000225h
0x140003154  mov     ecx, esi
0x140003156  cmovnz  ecx, eax
0x140003159  test    ecx, ecx
0x14000315b  jns     short loc_14000316D
0x14000315d  mov     eax, cs:dword_140019000
0x140003163  cmp     eax, 3
0x140003166  jbe     short loc_140003197
0x140003168  jmp     loc_140002FAD
0x14000316d  mov     rdx, [rbp+57h+EcpContext]; EcpContext
0x140003171  test    rdx, rdx
0x140003174  jz      short loc_140003197
0x140003176  mov     rcx, [r14+8]; Filter
0x14000317a  call    cs:__imp_FltIsEcpFromUserMode
0x140003181  nop     dword ptr [rax+rax+00h]
0x140003186  test    al, al
0x140003188  jnz     short loc_140003197
0x14000318a  mov     rax, [rbp+57h+EcpContext]
0x14000318e  mov     ebx, esi
0x140003190  mov     rcx, [rax+8]
0x140003194  mov     [r15], rcx
0x140003197  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x14000319b  test    rcx, rcx
0x14000319e  jz      short loc_1400031AC
0x1400031a0  call    cs:__imp_FltReleaseFileNameInformation
0x1400031a7  nop     dword ptr [rax+rax+00h]
0x1400031ac  test    r13b, r13b
0x1400031af  mov     r13, [rsp+100h+var_30]
0x1400031b7  jz      short loc_1400031EA
0x1400031b9  cmp     qword ptr [r15], 0
0x1400031bd  jnz     short loc_1400031EA
0x1400031bf  call    cs:__imp_KeEnterCriticalRegion
0x1400031c6  nop     dword ptr [rax+rax+00h]
0x1400031cb  lea     rcx, gBfsRundownProtection; RunRef
0x1400031d2  call    cs:__imp_ExReleaseRundownProtection
0x1400031d9  nop     dword ptr [rax+rax+00h]
0x1400031de  call    cs:__imp_KeLeaveCriticalRegion
0x1400031e5  nop     dword ptr [rax+rax+00h]
0x1400031ea  mov     rcx, [rbp+57h+TokenInformation]; P
0x1400031ee  test    rcx, rcx
0x1400031f1  jz      short loc_140003201
0x1400031f3  xor     edx, edx; Tag
0x1400031f5  call    cs:__imp_ExFreePoolWithTag
0x1400031fc  nop     dword ptr [rax+rax+00h]
0x140003201  mov     rcx, [rbp+57h+P]; P
0x140003205  test    rcx, rcx
0x140003208  jz      short loc_140003218
0x14000320a  xor     edx, edx; Tag
0x14000320c  call    cs:__imp_ExFreePoolWithTag
0x140003213  nop     dword ptr [rax+rax+00h]
0x140003218  test    rdi, rdi
0x14000321b  jz      short loc_14000323F
0x14000321d  mov     rcx, rdi; PrimaryToken
0x140003220  test    r12b, r12b
0x140003223  jz      short loc_140003233
0x140003225  call    cs:__imp_PsDereferenceImpersonationToken
0x14000322c  nop     dword ptr [rax+rax+00h]
0x140003231  jmp     short loc_14000323F
0x140003233  call    cs:__imp_PsDereferencePrimaryToken
0x14000323a  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
