# BfsPreCreatePipeOperation

- ea: `0x140001460`
- end: `0x14000185e`
- name: `BfsPreCreatePipeOperation`
- size: `1022`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001008`
- `0x140001460`
- `0x140003210`
- `0x140006af4`
- `0x14000b338`
- `0x14000b7bc`
- `0x14000bd0c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400015fc`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000161f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400015fc`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000161f`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000182b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000182b`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000181d`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000181d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400017ca`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400017ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001804`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001804`
- `ntoskrnl!SeQueryInformationToken` at `0x14000163c`
- `ntoskrnl!SeQueryInformationToken` at `0x14000165e`
- `ntoskrnl!SeQueryInformationToken` at `0x14000163c`
- `ntoskrnl!SeQueryInformationToken` at `0x14000165e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000153d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000153d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000154c`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000154c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140001529`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140001529`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400014de`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400017b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400014de`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400017b7`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400014f1`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400014f1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001501`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400017d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001501`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400017d6`
- `FLTMGR!FltGetFileNameInformation` at `0x14000158b`
- `FLTMGR!FltGetFileNameInformation` at `0x14000158b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140001798`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140001798`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14000170a`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14000170a`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140001747`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140001747`
- `FLTMGR!FltIsEcpFromUserMode` at `0x140001772`
- `FLTMGR!FltIsEcpFromUserMode` at `0x140001772`

## pseudocode

```c
__int64 __fastcall BfsPreCreatePipeOperation(PFLT_CALLBACK_DATA Data, __int64 a2, _QWORD *a3)
{
  PACCESS_TOKEN v3; // rbx
  unsigned int v8; // edi
  char v9; // r12
  BOOLEAN v10; // r13
  struct _KPROCESS *CurrentProcess; // rax
  NTSTATUS EcpListFromCallbackData; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rax
  struct _FLT_FILTER *v16; // rcx
  NTSTATUS ExtraCreateParameter; // eax
  int EcpContextSize; // [rsp+20h] [rbp-89h]
  NTSTATUS v19; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+34h] [rbp-75h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+35h] [rbp-74h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+38h] [rbp-71h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp-69h] BYREF
  PVOID EcpContext; // [rsp+48h] [rbp-61h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp-59h] BYREF
  PVOID P; // [rsp+58h] [rbp-51h] BYREF
  ULONG v27; // [rsp+60h] [rbp-49h] BYREF
  PECP_LIST EcpList; // [rsp+68h] [rbp-41h] BYREF
  UNICODE_STRING String2; // [rsp+70h] [rbp-39h] BYREF
  char v30[16]; // [rsp+80h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+90h] [rbp-19h] BYREF
  NTSTATUS *v32; // [rsp+B0h] [rbp+7h]
  __int64 v33; // [rsp+B8h] [rbp+Fh]

  v3 = 0;
  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  EcpContext = 0;
  v27 = 0;
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
    goto LABEL_27;
  *a3 = 0;
  v3 = PsReferenceImpersonationToken(Data->Thread, CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  if ( v3 )
  {
    v9 = 1;
    if ( ImpersonationLevel < SecurityImpersonation )
      goto LABEL_27;
  }
  else
  {
    CurrentProcess = IoGetCurrentProcess();
    v3 = PsReferencePrimaryToken(CurrentProcess);
  }
  if ( !(unsigned __int8)BfsIsApplicableToken(v3) )
    goto LABEL_27;
  EcpListFromCallbackData = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
  if ( EcpListFromCallbackData < 0 )
    goto LABEL_9;
  String2 = *(UNICODE_STRING *)BfsGetFileName(v30, FileNameInformation);
  if ( RtlPrefixUnicodeString(&LocalPrefixString, &String2, 1u)
    || RtlPrefixUnicodeString(&SessionsPrefixString, &String2, 1u) )
  {
    EcpListFromCallbackData = FltGetEcpListFromCallbackData(*(PFLT_FILTER *)(a2 + 8), Data, &EcpList);
    if ( EcpListFromCallbackData >= 0 )
    {
      if ( EcpList )
      {
        v16 = *(struct _FLT_FILTER **)(a2 + 8);
        EcpContext = 0;
        ExtraCreateParameter = FltFindExtraCreateParameter(v16, EcpList, &BfsEcpType, &EcpContext, &v27);
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
          goto LABEL_27;
        }
        goto LABEL_9;
      }
      goto LABEL_27;
    }
LABEL_9:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v19 = EcpListFromCallbackData;
      v32 = &v19;
      v33 = 4;
      tlgWriteTransfer_EtwWriteTransfer(EcpListFromCallbackData, (int)&byte_140016D91, v13, v14, EcpContextSize, &v31);
    }
    goto LABEL_27;
  }
  EcpListFromCallbackData = SeQueryInformationToken(v3, TokenUser, &TokenInformation);
  if ( EcpListFromCallbackData < 0 )
    goto LABEL_9;
  EcpListFromCallbackData = SeQueryInformationToken(v3, TokenAppContainerSid, &P);
  if ( EcpListFromCallbackData < 0 )
    goto LABEL_9;
  if ( (Data->Iopb->Parameters.Create.Options & 0xFF000000) != 0x1000000 )
  {
LABEL_18:
    v8 = (((int)BfsRedirectNamedPipe(
                  *(PFLT_FILTER *)(a2 + 8),
                  Data,
                  *(unsigned __int8 **)TokenInformation,
                  *(unsigned __int8 **)P,
                  (__int64)FileNameInformation,
                  &String2) >> 31)
        & 0xFFFFFFFD)
       + 4;
    goto LABEL_27;
  }
  v15 = BfsAcquireNamedPipeMapping(
          &gBfsPipeMappingTable,
          *(_QWORD *)TokenInformation,
          *(_QWORD *)P,
          &FileNameInformation->Name);
  if ( v15 )
  {
    BfsReleaseNamedPipeMapping(&gBfsPipeMappingTable, v15);
    goto LABEL_18;
  }
LABEL_27:
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
0x140001460  push    rbp
0x140001462  push    rbx
0x140001463  push    rsi
0x140001464  push    rdi
0x140001465  push    r14
0x140001467  push    r15
0x140001469  lea     rbp, [rsp-2Fh]
0x14000146e  sub     rsp, 0D8h
0x140001475  mov     rax, cs:__security_cookie
0x14000147c  xor     rax, rsp
0x14000147f  mov     [rbp+57h+var_40], rax
0x140001483  xor     ebx, ebx
0x140001485  mov     [rbp+57h+CopyOnOpen], 0
0x140001489  xorps   xmm0, xmm0
0x14000148c  mov     r15, r8
0x14000148f  mov     r14, rdx
0x140001492  mov     rsi, rcx
0x140001495  mov     [rbp+57h+EffectiveOnly], 0
0x140001499  mov     [rbp+57h+EcpContext], rbx
0x14000149d  mov     [rbp+57h+var_A0], ebx
0x1400014a0  mov     [rbp+57h+EcpList], rbx
0x1400014a4  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x1400014a8  mov     [rbp+57h+ImpersonationLevel], ebx
0x1400014ab  cmp     [rcx+50h], bl
0x1400014ae  jnz     short loc_1400014BA
0x1400014b0  mov     eax, 1
0x1400014b5  jmp     loc_140001841
0x1400014ba  mov     [rsp+100h+arg_18], r12
0x1400014c2  mov     edi, 1
0x1400014c7  mov     [rsp+100h+var_30], r13
0x1400014cf  xor     r12b, r12b
0x1400014d2  mov     [rbp+57h+FileNameInformation], rbx
0x1400014d6  mov     [rbp+57h+P], rbx
0x1400014da  mov     [rbp+57h+TokenInformation], rbx
0x1400014de  call    cs:__imp_KeEnterCriticalRegion
0x1400014e5  nop     dword ptr [rax+rax+00h]
0x1400014ea  lea     rcx, gBfsRundownProtection; RunRef
0x1400014f1  call    cs:__imp_ExAcquireRundownProtection
0x1400014f8  nop     dword ptr [rax+rax+00h]
0x1400014fd  movzx   r13d, al
0x140001501  call    cs:__imp_KeLeaveCriticalRegion
0x140001508  nop     dword ptr [rax+rax+00h]
0x14000150d  test    r13b, r13b
0x140001510  jz      loc_14000178F
0x140001516  mov     [r15], rbx
0x140001519  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x14000151d  mov     rcx, [rsi+8]; Thread
0x140001521  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x140001525  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x140001529  call    cs:__imp_PsReferenceImpersonationToken
0x140001530  nop     dword ptr [rax+rax+00h]
0x140001535  mov     rbx, rax
0x140001538  test    rax, rax
0x14000153b  jnz     short loc_14000155D
0x14000153d  call    cs:__imp_IoGetCurrentProcess
0x140001544  nop     dword ptr [rax+rax+00h]
0x140001549  mov     rcx, rax; Process
0x14000154c  call    cs:__imp_PsReferencePrimaryToken
0x140001553  nop     dword ptr [rax+rax+00h]
0x140001558  mov     rbx, rax
0x14000155b  jmp     short loc_14000156B
0x14000155d  cmp     [rbp+57h+ImpersonationLevel], 2
0x140001561  movzx   r12d, dil
0x140001565  jl      loc_14000178F
0x14000156b  movzx   edx, dil
0x14000156f  mov     rcx, rbx; Object
0x140001572  call    BfsIsApplicableToken
0x140001577  test    al, al
0x140001579  jz      loc_14000178F
0x14000157f  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140001583  mov     edx, 101h; NameOptions
0x140001588  mov     rcx, rsi; CallbackData
0x14000158b  call    cs:__imp_FltGetFileNameInformation
0x140001592  nop     dword ptr [rax+rax+00h]
0x140001597  mov     ecx, eax; int
0x140001599  test    eax, eax
0x14000159b  jns     short loc_1400015D9
0x14000159d  mov     eax, cs:dword_140019000
0x1400015a3  cmp     eax, 3
0x1400015a6  jbe     loc_14000178F
0x1400015ac  lea     rax, [rbp+57h+var_D0]
0x1400015b0  mov     [rbp+57h+var_D0], ecx
0x1400015b3  mov     [rbp+57h+var_50], rax
0x1400015b7  lea     rdx, byte_140016D91; int
0x1400015be  lea     rax, [rbp+57h+var_70]
0x1400015c2  mov     [rbp+57h+var_48], 4
0x1400015ca  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x1400015cf  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400015d4  jmp     loc_14000178F
0x1400015d9  mov     rdx, [rbp+57h+FileNameInformation]
0x1400015dd  lea     rcx, [rbp+57h+var_80]
0x1400015e1  call    BfsGetFileName
0x1400015e6  movzx   r8d, dil; CaseInSensitive
0x1400015ea  lea     rdx, [rbp+57h+String2]; String2
0x1400015ee  lea     rcx, LocalPrefixString; String1
0x1400015f5  movups  xmm1, xmmword ptr [rax]
0x1400015f8  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x1400015fc  call    cs:__imp_RtlPrefixUnicodeString
0x140001603  nop     dword ptr [rax+rax+00h]
0x140001608  test    al, al
0x14000160a  jnz     loc_1400016FF
0x140001610  movzx   r8d, dil; CaseInSensitive
0x140001614  lea     rdx, [rbp+57h+String2]; String2
0x140001618  lea     rcx, SessionsPrefixString; String1
0x14000161f  call    cs:__imp_RtlPrefixUnicodeString
0x140001626  nop     dword ptr [rax+rax+00h]
0x14000162b  test    al, al
0x14000162d  jnz     loc_1400016FF
0x140001633  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140001637  mov     edx, edi; TokenInformationClass
0x140001639  mov     rcx, rbx; Token
0x14000163c  call    cs:__imp_SeQueryInformationToken
0x140001643  nop     dword ptr [rax+rax+00h]
0x140001648  mov     ecx, eax
0x14000164a  test    eax, eax
0x14000164c  js      loc_14000159D
0x140001652  lea     r8, [rbp+57h+P]; TokenInformation
0x140001656  mov     edx, 1Fh; TokenInformationClass
0x14000165b  mov     rcx, rbx; Token
0x14000165e  call    cs:__imp_SeQueryInformationToken
0x140001665  nop     dword ptr [rax+rax+00h]
0x14000166a  mov     ecx, eax
0x14000166c  test    eax, eax
0x14000166e  js      loc_14000159D
0x140001674  mov     rax, [rsi+10h]
0x140001678  mov     ecx, [rax+20h]
0x14000167b  and     ecx, 0FF000000h
0x140001681  cmp     ecx, 1000000h
0x140001687  jnz     short loc_1400016C3
0x140001689  mov     r8, [rbp+57h+P]
0x14000168d  lea     rcx, gBfsPipeMappingTable
0x140001694  mov     rdx, [rbp+57h+TokenInformation]
0x140001698  mov     r9, [rbp+57h+FileNameInformation]
0x14000169c  add     r9, 8
0x1400016a0  mov     r8, [r8]
0x1400016a3  mov     rdx, [rdx]
0x1400016a6  call    BfsAcquireNamedPipeMapping
0x1400016ab  test    rax, rax
0x1400016ae  jz      loc_14000178F
0x1400016b4  mov     rdx, rax
0x1400016b7  lea     rcx, gBfsPipeMappingTable
0x1400016be  call    BfsReleaseNamedPipeMapping
0x1400016c3  mov     r9, [rbp+57h+P]
0x1400016c7  lea     rax, [rbp+57h+String2]
0x1400016cb  mov     r8, [rbp+57h+TokenInformation]
0x1400016cf  mov     rdx, rsi; Data
0x1400016d2  mov     rcx, [r14+8]; Filter
0x1400016d6  mov     [rsp+100h+var_D8], rax; Source
0x1400016db  mov     rax, [rbp+57h+FileNameInformation]
0x1400016df  mov     r9, [r9]; PSID
0x1400016e2  mov     r8, [r8]; SourceSid
0x1400016e5  mov     [rsp+100h+EcpContextSize], rax; __int64
0x1400016ea  call    BfsRedirectNamedPipe
0x1400016ef  mov     edi, eax
0x1400016f1  sar     edi, 1Fh
0x1400016f4  and     edi, 0FFFFFFFDh
0x1400016f7  add     edi, 4
0x1400016fa  jmp     loc_14000178F
0x1400016ff  mov     rcx, [r14+8]; Filter
0x140001703  lea     r8, [rbp+57h+EcpList]; EcpList
0x140001707  mov     rdx, rsi; CallbackData
0x14000170a  call    cs:__imp_FltGetEcpListFromCallbackData
0x140001711  nop     dword ptr [rax+rax+00h]
0x140001716  mov     ecx, eax
0x140001718  test    eax, eax
0x14000171a  js      loc_14000159D
0x140001720  mov     rdx, [rbp+57h+EcpList]; EcpList
0x140001724  test    rdx, rdx
0x140001727  jz      short loc_14000178F
0x140001729  mov     rcx, [r14+8]; Filter
0x14000172d  lea     rax, [rbp+57h+var_A0]
0x140001731  xor     esi, esi
0x140001733  mov     [rsp+100h+EcpContextSize], rax; EcpContextSize
0x140001738  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x14000173c  mov     [rbp+57h+EcpContext], rsi
0x140001740  lea     r8, BfsEcpType; EcpType
0x140001747  call    cs:__imp_FltFindExtraCreateParameter
0x14000174e  nop     dword ptr [rax+rax+00h]
0x140001753  cmp     eax, 0C0000225h
0x140001758  mov     ecx, esi
0x14000175a  cmovnz  ecx, eax
0x14000175d  test    ecx, ecx
0x14000175f  js      loc_14000159D
0x140001765  mov     rdx, [rbp+57h+EcpContext]; EcpContext
0x140001769  test    rdx, rdx
0x14000176c  jz      short loc_14000178F
0x14000176e  mov     rcx, [r14+8]; Filter
0x140001772  call    cs:__imp_FltIsEcpFromUserMode
0x140001779  nop     dword ptr [rax+rax+00h]
0x14000177e  test    al, al
0x140001780  jnz     short loc_14000178F
0x140001782  mov     rax, [rbp+57h+EcpContext]
0x140001786  mov     edi, esi
0x140001788  mov     rcx, [rax+8]
0x14000178c  mov     [r15], rcx
0x14000178f  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140001793  test    rcx, rcx
0x140001796  jz      short loc_1400017A4
0x140001798  call    cs:__imp_FltReleaseFileNameInformation
0x14000179f  nop     dword ptr [rax+rax+00h]
0x1400017a4  test    r13b, r13b
0x1400017a7  mov     r13, [rsp+100h+var_30]
0x1400017af  jz      short loc_1400017E2
0x1400017b1  cmp     qword ptr [r15], 0
0x1400017b5  jnz     short loc_1400017E2
0x1400017b7  call    cs:__imp_KeEnterCriticalRegion
0x1400017be  nop     dword ptr [rax+rax+00h]
0x1400017c3  lea     rcx, gBfsRundownProtection; RunRef
0x1400017ca  call    cs:__imp_ExReleaseRundownProtection
0x1400017d1  nop     dword ptr [rax+rax+00h]
0x1400017d6  call    cs:__imp_KeLeaveCriticalRegion
0x1400017dd  nop     dword ptr [rax+rax+00h]
0x1400017e2  mov     rcx, [rbp+57h+TokenInformation]; P
0x1400017e6  test    rcx, rcx
0x1400017e9  jz      short loc_1400017F9
0x1400017eb  xor     edx, edx; Tag
0x1400017ed  call    cs:__imp_ExFreePoolWithTag
0x1400017f4  nop     dword ptr [rax+rax+00h]
0x1400017f9  mov     rcx, [rbp+57h+P]; P
0x1400017fd  test    rcx, rcx
0x140001800  jz      short loc_140001810
0x140001802  xor     edx, edx; Tag
0x140001804  call    cs:__imp_ExFreePoolWithTag
0x14000180b  nop     dword ptr [rax+rax+00h]
0x140001810  test    rbx, rbx
0x140001813  jz      short loc_140001837
0x140001815  mov     rcx, rbx; PrimaryToken
0x140001818  test    r12b, r12b
0x14000181b  jz      short loc_14000182B
0x14000181d  call    cs:__imp_PsDereferenceImpersonationToken
0x140001824  nop     dword ptr [rax+rax+00h]
0x140001829  jmp     short loc_140001837
0x14000182b  call    cs:__imp_PsDereferencePrimaryToken
0x140001832  nop     dword ptr [rax+rax+00h]
0x140001837  mov     r12, [rsp+100h+arg_18]
0x14000183f  mov     eax, edi
0x140001841  mov     rcx, [rbp+57h+var_40]
0x140001845  xor     rcx, rsp; StackCookie
0x140001848  call    __security_check_cookie
0x14000184d  add     rsp, 0D8h
0x140001854  pop     r15
0x140001856  pop     r14
0x140001858  pop     rdi
0x140001859  pop     rsi
0x14000185a  pop     rbx
0x14000185b  pop     rbp
0x14000185c  retn
```
