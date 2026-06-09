# BfsCheckAndApplyPolicy

- ea: `0x1400055d8`
- end: `0x140005c06`
- name: `BfsCheckAndApplyPolicy`
- size: `1582`
- prototype: `__int64 __fastcall(PVOID FltObject, PVOID, PACCESS_TOKEN Token, PFLT_CALLBACK_DATA Data, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140002a30`

## callees

- `0x140001008`
- `0x1400034e4`
- `0x140005138`
- `0x1400055d8`
- `0x140006040`
- `0x140006630`
- `0x140006af4`
- `0x140006c24`
- `0x140006e14`
- `0x140007044`
- `0x140008e84`
- `0x14000a364`
- `0x14000ff3c`
- `0x14001033c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400058eb`
- `ntoskrnl!SeExports` at `0x140005929`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140005902`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140005940`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140005902`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140005940`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057ea`
- `ntoskrnl!SeQueryInformationToken` at `0x14000563f`
- `ntoskrnl!SeQueryInformationToken` at `0x140005699`
- `ntoskrnl!SeQueryInformationToken` at `0x14000563f`
- `ntoskrnl!SeQueryInformationToken` at `0x140005699`
- `ntoskrnl!ExAllocatePool2` at `0x140005b9c`
- `ntoskrnl!ExAllocatePool2` at `0x140005b9c`
- `FLTMGR!FltGetFileNameInformation` at `0x1400056b7`
- `FLTMGR!FltGetFileNameInformation` at `0x140005b70`
- `FLTMGR!FltGetFileNameInformation` at `0x1400056b7`
- `FLTMGR!FltGetFileNameInformation` at `0x140005b70`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400057bc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400057bc`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140005bd6`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140005bd6`

## pseudocode

```c
char __fastcall BfsCheckAndApplyPolicy(
        PVOID FltObject,
        PVOID a2,
        PACCESS_TOKEN Token,
        PFLT_CALLBACK_DATA Data,
        __int64 *a5)
{
  char v9; // di
  NTSTATUS v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rcx
  int PolicyEntry; // edi
  int v15; // r8d
  int v16; // r9d
  volatile signed __int32 *v17; // rbx
  __int64 v19; // rcx
  char *v20; // r9
  int Policy; // eax
  NTSTATUS v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // eax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // eax
  __int64 Pool2; // rax
  int v34; // [rsp+20h] [rbp-91h]
  __int64 v35; // [rsp+20h] [rbp-91h]
  __int64 v36; // [rsp+20h] [rbp-91h]
  _BYTE v37[3]; // [rsp+31h] [rbp-80h] BYREF
  int v38; // [rsp+34h] [rbp-7Dh] BYREF
  char v39; // [rsp+38h] [rbp-79h] BYREF
  char v40; // [rsp+39h] [rbp-78h] BYREF
  PVOID v41; // [rsp+40h] [rbp-71h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-69h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp-61h] BYREF
  PVOID P; // [rsp+58h] [rbp-59h] BYREF
  __int128 v45; // [rsp+60h] [rbp-51h] BYREF
  __int128 v46; // [rsp+70h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+80h] [rbp-31h] BYREF
  int *v48; // [rsp+A0h] [rbp-11h]
  __int64 v49; // [rsp+A8h] [rbp-9h]

  v39 = 0;
  TokenInformation = 0;
  v41 = 0;
  FileNameInformation = 0;
  P = 0;
  v40 = 0;
  v9 = 0;
  v46 = 0;
  v10 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  if ( v10 >= 0 )
  {
    v10 = SeQueryInformationToken(Token, TokenAppContainerSid, &P);
    if ( v10 >= 0 )
    {
      v10 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
      if ( v10 == -1073741311 )
      {
        v45 = (unsigned __int64)Token;
        v10 = BfsQueueDeferredWorkItemAndWait(FltObject, a2, Data, (__int64)&BfsQueryFileNameInformationCallback);
        FileNameInformation = (PFLT_FILE_NAME_INFORMATION)*((_QWORD *)&v45 + 1);
      }
      if ( v10 >= 0 )
      {
        if ( BfsPolicyEntryExists(
               (int)FltObject,
               (int)a2,
               (__int64)&gBfsPolicyTable,
               *(void **)TokenInformation,
               *(PSID *)P) )
        {
          v35 = *(_QWORD *)P;
          PolicyEntry = BfsGetPolicyEntry(FltObject, a2, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
          if ( PolicyEntry < 0 )
            goto LABEL_10;
          v45 = *(_OWORD *)BfsGetFileName(&v45, FileNameInformation);
          v17 = (volatile signed __int32 *)v41;
          if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v19) )
            v20 = &v40;
          else
            v20 = 0;
          Policy = BfsGetPolicy(*((_QWORD *)v41 + 6), &FileNameInformation->Volume, &v45, v20);
          if ( Policy )
          {
            if ( Policy != 1 )
            {
              if ( Policy != 2 )
                goto LABEL_13;
              v9 = 0;
              if ( !(unsigned __int8)BfsQueryAccessOnly((Data->Iopb->Parameters.Create.Options & 1) + 1, Data) )
              {
                if ( (unsigned __int8)BfsQueryAccessOnly((Data->Iopb->Parameters.Create.Options & 1) + 1, Data) )
                  goto LABEL_14;
                goto LABEL_66;
              }
            }
LABEL_56:
            LODWORD(v35) = (_DWORD)a5;
            v32 = BfsApplyPolicyAsUser(Data, Token, FileNameInformation, v17);
            v22 = v32;
            if ( v32 >= 0 )
            {
              if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline((unsigned int)v32) )
                *(_BYTE *)(*a5 + 72) = v40;
LABEL_61:
              v9 = 1;
              goto LABEL_14;
            }
            goto LABEL_57;
          }
        }
        else
        {
          PolicyEntry = BfsGetNotPresentPolicyEntry(&gBfsPolicyTable, *(_QWORD *)TokenInformation, *(_QWORD *)P, &v41);
          if ( PolicyEntry < 0 )
          {
LABEL_10:
            if ( (unsigned int)dword_140019000 > 3 )
            {
              v38 = PolicyEntry;
              v48 = &v38;
              v49 = 4;
              tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v15, v16, v35, &v47);
            }
            goto LABEL_12;
          }
          v17 = (volatile signed __int32 *)v41;
        }
        v37[0] = 0;
        if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v13) )
        {
          v25 = *((_DWORD *)v17 + 27);
          if ( v25 )
          {
            v37[0] = v25 == 1;
          }
          else
          {
            PolicyEntry = RtlCheckTokenCapability(0, *(_QWORD *)&SeExports[1].SeUnsolicitedInputPrivilege, v37);
            v22 = 2 - (v37[0] != 0);
            *((_DWORD *)v17 + 27) = v22;
          }
        }
        else
        {
          PolicyEntry = RtlCheckTokenCapability(0, *(_QWORD *)&SeExports[1].SeUnsolicitedInputPrivilege, v37);
        }
        if ( PolicyEntry < 0 )
        {
          if ( PolicyEntry != -1073741790 )
          {
            if ( (unsigned int)dword_140019000 <= 3 )
              goto LABEL_13;
            v38 = PolicyEntry;
            goto LABEL_65;
          }
          goto LABEL_66;
        }
        v9 = 0;
        if ( !v37[0] )
          goto LABEL_66;
        v26 = BfsFileInPublisherDirectory(Token, FileNameInformation, &v39, &v46);
        if ( v26 < 0 )
        {
          if ( (unsigned int)dword_140019000 > 3 )
          {
            v38 = v26;
            v48 = &v38;
            v49 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v26, (int)&byte_140016D91, v27, v28, v35, &v47);
          }
          goto LABEL_14;
        }
        if ( !v39 )
        {
LABEL_66:
          if ( FileNameInformation || (v22 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation), v22 >= 0) )
          {
            Pool2 = *a5;
            if ( !*a5 )
            {
              Pool2 = ExAllocatePool2(256, 96, 1131636290);
              *a5 = Pool2;
              if ( !Pool2 )
              {
                if ( (unsigned int)dword_140019000 <= 3 )
                  goto LABEL_13;
                v38 = -1073741801;
                goto LABEL_65;
              }
            }
            *(_DWORD *)(Pool2 + 8) = 1;
            FltReferenceFileNameInformation(FileNameInformation);
            *(_QWORD *)(*a5 + 48) = FileNameInformation;
            *(_QWORD *)(*a5 + 64) = v17;
            _InterlockedIncrement(v17 + 36);
            *(_DWORD *)*a5 |= 1u;
            goto LABEL_61;
          }
LABEL_57:
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_13;
          v38 = v22;
LABEL_65:
          v49 = 4;
          v48 = &v38;
          tlgWriteTransfer_EtwWriteTransfer(v22, (int)&byte_140016D91, v23, v24, v35, &v47);
          goto LABEL_13;
        }
        if ( v17 )
        {
          if ( *((_DWORD *)v17 + 14) != 2 )
            goto LABEL_52;
          BfsDereferencePolicyEntryEx((PVOID)v17);
        }
        v36 = *(_QWORD *)P;
        v29 = BfsGetPolicyEntry(FltObject, a2, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
        if ( v29 < 0 )
        {
LABEL_49:
          if ( (unsigned int)dword_140019000 <= 3 )
          {
LABEL_12:
            v17 = (volatile signed __int32 *)v41;
LABEL_13:
            v9 = 0;
            goto LABEL_14;
          }
          v38 = v29;
          v48 = &v38;
          v49 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v29, (int)&byte_140016D91, v30, v31, v36, &v47);
          v17 = (volatile signed __int32 *)v41;
LABEL_14:
          if ( v17 )
            BfsDereferencePolicyEntryEx((PVOID)v17);
          goto LABEL_16;
        }
        v17 = (volatile signed __int32 *)v41;
LABEL_52:
        if ( *((_DWORD *)v17 + 14) == 268435457 )
        {
          v36 = *(_QWORD *)P;
          v29 = BfsGetPolicyEntry(FltObject, a2, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
          if ( v29 < 0 )
            goto LABEL_49;
          v17 = (volatile signed __int32 *)v41;
          BfsDereferencePolicyEntryEx(v41);
        }
        BfsAddOrModifyEntry(*((_QWORD *)v17 + 6), 2, 1, 2, (__int64)&FileNameInformation->Volume, (__int64)&v46);
        goto LABEL_56;
      }
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v38 = v10;
    v48 = &v38;
    v49 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v11, v12, v34, &v47);
  }
LABEL_16:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return v9;
}

```

## disassembly

```asm
0x1400055d8  push    rbp
0x1400055da  push    rbx
0x1400055db  push    rsi
0x1400055dc  push    rdi
0x1400055dd  push    r12
0x1400055df  push    r13
0x1400055e1  push    r14
0x1400055e3  push    r15
0x1400055e5  lea     rbp, [rsp-17h]
0x1400055ea  sub     rsp, 0C8h
0x1400055f1  mov     rax, cs:__security_cookie
0x1400055f8  xor     rax, rsp
0x1400055fb  mov     [rbp+4Fh+var_50], rax
0x1400055ff  mov     rsi, [rbp+4Fh+arg_20]
0x140005603  xor     ebx, ebx
0x140005605  mov     r13, r8
0x140005608  mov     [rbp+4Fh+var_C8], bl
0x14000560b  mov     r12, rdx
0x14000560e  mov     [rbp+4Fh+TokenInformation], rbx
0x140005612  mov     r15, rcx
0x140005615  mov     [rbp+4Fh+var_C0], rbx
0x140005619  xorps   xmm0, xmm0
0x14000561c  mov     [rsp+100h+var_D0], bl
0x140005620  lea     edx, [rbx+1]; TokenInformationClass
0x140005623  mov     [rbp+4Fh+FileNameInformation], rbx
0x140005627  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x14000562b  mov     [rbp+4Fh+P], rbx
0x14000562f  mov     rcx, r13; Token
0x140005632  mov     [rbp+4Fh+var_C7], bl
0x140005635  mov     r14, r9
0x140005638  mov     dil, bl
0x14000563b  movups  [rbp+4Fh+var_90], xmm0
0x14000563f  call    cs:__imp_SeQueryInformationToken
0x140005646  nop     dword ptr [rax+rax+00h]
0x14000564b  mov     ecx, eax; int
0x14000564d  test    eax, eax
0x14000564f  jns     short loc_14000568D
0x140005651  mov     eax, cs:dword_140019000
0x140005657  cmp     eax, 3
0x14000565a  jbe     loc_1400057B3
0x140005660  lea     rax, [rbp+4Fh+var_CC]
0x140005664  mov     [rbp+4Fh+var_CC], ecx
0x140005667  mov     [rbp+4Fh+var_60], rax
0x14000566b  lea     rdx, byte_140016D91; int
0x140005672  lea     rax, [rbp+4Fh+var_80]
0x140005676  mov     [rbp+4Fh+var_58], 4
0x14000567e  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005683  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005688  jmp     loc_1400057B3
0x14000568d  lea     r8, [rbp+4Fh+P]; TokenInformation
0x140005691  mov     edx, 1Fh; TokenInformationClass
0x140005696  mov     rcx, r13; Token
0x140005699  call    cs:__imp_SeQueryInformationToken
0x1400056a0  nop     dword ptr [rax+rax+00h]
0x1400056a5  mov     ecx, eax
0x1400056a7  test    eax, eax
0x1400056a9  js      short loc_140005651
0x1400056ab  lea     r8, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x1400056af  mov     edx, 101h; NameOptions
0x1400056b4  mov     rcx, r14; CallbackData
0x1400056b7  call    cs:__imp_FltGetFileNameInformation
0x1400056be  nop     dword ptr [rax+rax+00h]
0x1400056c3  mov     ecx, eax
0x1400056c5  cmp     eax, 0C0000201h
0x1400056ca  jnz     short loc_1400056FC
0x1400056cc  lea     rax, BfsQueryFileNameInformationCallback
0x1400056d3  mov     qword ptr [rbp+4Fh+var_A0+8], rbx
0x1400056d7  lea     r9, [rbp+4Fh+var_A0]
0x1400056db  mov     [rsp+100h+var_E0], rax; __int64
0x1400056e0  mov     r8, r14; Data
0x1400056e3  mov     qword ptr [rbp+4Fh+var_A0], r13
0x1400056e7  mov     rdx, r12; PVOID
0x1400056ea  mov     rcx, r15; FltObject
0x1400056ed  call    BfsQueueDeferredWorkItemAndWait
0x1400056f2  mov     ecx, eax
0x1400056f4  mov     rax, qword ptr [rbp+4Fh+var_A0+8]
0x1400056f8  mov     [rbp+4Fh+FileNameInformation], rax
0x1400056fc  test    ecx, ecx
0x1400056fe  js      loc_140005651
0x140005704  mov     rax, [rbp+4Fh+P]
0x140005708  lea     rdi, gBfsPolicyTable
0x14000570f  mov     r9, [rbp+4Fh+TokenInformation]
0x140005713  mov     r8, rdi
0x140005716  mov     rdx, r12
0x140005719  mov     rcx, [rax]
0x14000571c  mov     r9, [r9]
0x14000571f  mov     [rsp+100h+var_E0], rcx; int
0x140005724  mov     rcx, r15
0x140005727  call    BfsPolicyEntryExists
0x14000572c  test    al, al
0x14000572e  jz      loc_1400058AF
0x140005734  mov     r9, [rbp+4Fh+TokenInformation]
0x140005738  lea     rax, [rbp+4Fh+var_C0]
0x14000573c  mov     [rsp+100h+var_D8], rax
0x140005741  mov     r8, rdi
0x140005744  mov     rax, [rbp+4Fh+P]
0x140005748  mov     rdx, r12
0x14000574b  mov     r9, [r9]
0x14000574e  mov     rcx, [rax]
0x140005751  mov     [rsp+100h+var_E0], rcx; int
0x140005756  mov     rcx, r15
0x140005759  call    BfsGetPolicyEntry
0x14000575e  mov     edi, eax
0x140005760  test    eax, eax
0x140005762  jns     loc_14000581A
0x140005768  mov     eax, cs:dword_140019000
0x14000576e  cmp     eax, 3
0x140005771  jbe     short loc_14000579B
0x140005773  lea     rax, [rbp+4Fh+var_CC]
0x140005777  mov     [rbp+4Fh+var_CC], edi
0x14000577a  mov     [rbp+4Fh+var_60], rax
0x14000577e  lea     rdx, byte_140016D91; int
0x140005785  lea     rax, [rbp+4Fh+var_80]
0x140005789  mov     [rbp+4Fh+var_58], 4
0x140005791  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005796  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000579b  mov     rbx, [rbp+4Fh+var_C0]
0x14000579f  mov     dil, [rsp+100h+var_D0]
0x1400057a4  test    rbx, rbx
0x1400057a7  jz      short loc_1400057B3
0x1400057a9  xor     edx, edx
0x1400057ab  mov     rcx, rbx; P
0x1400057ae  call    BfsDereferencePolicyEntryEx
0x1400057b3  mov     rcx, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x1400057b7  test    rcx, rcx
0x1400057ba  jz      short loc_1400057C8
0x1400057bc  call    cs:__imp_FltReleaseFileNameInformation
0x1400057c3  nop     dword ptr [rax+rax+00h]
0x1400057c8  mov     rcx, [rbp+4Fh+TokenInformation]; P
0x1400057cc  test    rcx, rcx
0x1400057cf  jz      short loc_1400057DF
0x1400057d1  xor     edx, edx; Tag
0x1400057d3  call    cs:__imp_ExFreePoolWithTag
0x1400057da  nop     dword ptr [rax+rax+00h]
0x1400057df  mov     rcx, [rbp+4Fh+P]; P
0x1400057e3  test    rcx, rcx
0x1400057e6  jz      short loc_1400057F6
0x1400057e8  xor     edx, edx; Tag
0x1400057ea  call    cs:__imp_ExFreePoolWithTag
0x1400057f1  nop     dword ptr [rax+rax+00h]
0x1400057f6  mov     al, dil
0x1400057f9  mov     rcx, [rbp+4Fh+var_50]
0x1400057fd  xor     rcx, rsp; StackCookie
0x140005800  call    __security_check_cookie
0x140005805  add     rsp, 0C8h
0x14000580c  pop     r15
0x14000580e  pop     r14
0x140005810  pop     r13
0x140005812  pop     r12
0x140005814  pop     rdi
0x140005815  pop     rsi
0x140005816  pop     rbx
0x140005817  pop     rbp
0x140005818  retn
0x14000581a  mov     rdx, [rbp+4Fh+FileNameInformation]
0x14000581e  lea     rcx, [rbp+4Fh+var_A0]
0x140005822  call    BfsGetFileName
0x140005827  movups  xmm1, xmmword ptr [rax]
0x14000582a  movdqu  [rbp+4Fh+var_A0], xmm1
0x14000582f  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140005834  mov     rdx, [rbp+4Fh+FileNameInformation]
0x140005838  lea     r8, [rbp+4Fh+var_A0]
0x14000583c  mov     rbx, [rbp+4Fh+var_C0]
0x140005840  add     rdx, 18h
0x140005844  mov     rcx, [rbx+30h]
0x140005848  test    eax, eax
0x14000584a  jz      short loc_140005852
0x14000584c  lea     r9, [rbp+4Fh+var_C7]
0x140005850  jmp     short loc_140005855
0x140005852  xor     r9d, r9d
0x140005855  call    BfsGetPolicy
0x14000585a  test    eax, eax
0x14000585c  jz      short loc_1400058D7
0x14000585e  cmp     eax, 1
0x140005861  jz      loc_140005ACD
0x140005867  cmp     eax, 2
0x14000586a  jnz     loc_14000579F
0x140005870  mov     rax, [r14+10h]
0x140005874  mov     rdx, r14
0x140005877  mov     ecx, [rax+20h]
0x14000587a  and     ecx, 1
0x14000587d  inc     ecx
0x14000587f  call    BfsQueryAccessOnly
0x140005884  xor     edi, edi
0x140005886  test    al, al
0x140005888  jnz     loc_140005ACD
0x14000588e  mov     rax, [r14+10h]
0x140005892  mov     rdx, r14
0x140005895  mov     ecx, [rax+20h]
0x140005898  and     ecx, 1
0x14000589b  inc     ecx
0x14000589d  call    BfsQueryAccessOnly
0x1400058a2  test    al, al
0x1400058a4  jnz     loc_1400057A4
0x1400058aa  jmp     loc_140005B5E
0x1400058af  mov     r8, [rbp+4Fh+P]
0x1400058b3  lea     r9, [rbp+4Fh+var_C0]
0x1400058b7  mov     rdx, [rbp+4Fh+TokenInformation]
0x1400058bb  mov     rcx, rdi
0x1400058be  mov     r8, [r8]
0x1400058c1  mov     rdx, [rdx]
0x1400058c4  call    BfsGetNotPresentPolicyEntry
0x1400058c9  mov     edi, eax
0x1400058cb  test    eax, eax
0x1400058cd  js      loc_140005768
0x1400058d3  mov     rbx, [rbp+4Fh+var_C0]
0x1400058d7  mov     [rbp+4Fh+var_CF], 0
0x1400058db  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x1400058e0  test    eax, eax
0x1400058e2  jz      short loc_140005929
0x1400058e4  mov     eax, [rbx+6Ch]
0x1400058e7  test    eax, eax
0x1400058e9  jnz     short loc_14000591F
0x1400058eb  mov     rax, cs:__imp_SeExports
0x1400058f2  lea     r8, [rbp+4Fh+var_CF]
0x1400058f6  xor     ecx, ecx
0x1400058f8  mov     rdx, [rax]
0x1400058fb  mov     rdx, [rdx+250h]
0x140005902  call    cs:__imp_RtlCheckTokenCapability
0x140005909  nop     dword ptr [rax+rax+00h]
0x14000590e  mov     edi, eax
0x140005910  mov     al, [rbp+4Fh+var_CF]
0x140005913  neg     al
0x140005915  sbb     ecx, ecx
0x140005917  add     ecx, 2
0x14000591a  mov     [rbx+6Ch], ecx
0x14000591d  jmp     short loc_14000594E
0x14000591f  cmp     eax, 1
0x140005922  jnz     short loc_14000594E
0x140005924  mov     [rbp+4Fh+var_CF], al
0x140005927  jmp     short loc_14000594E
0x140005929  mov     rax, cs:__imp_SeExports
0x140005930  lea     r8, [rbp+4Fh+var_CF]
0x140005934  xor     ecx, ecx
0x140005936  mov     rdx, [rax]
0x140005939  mov     rdx, [rdx+250h]
0x140005940  call    cs:__imp_RtlCheckTokenCapability
0x140005947  nop     dword ptr [rax+rax+00h]
0x14000594c  mov     edi, eax
0x14000594e  test    edi, edi
0x140005950  js      loc_140005B18
0x140005956  xor     edi, edi
0x140005958  cmp     [rbp+4Fh+var_CF], dil
0x14000595c  jz      loc_140005B5E
0x140005962  mov     rdx, [rbp+4Fh+FileNameInformation]
0x140005966  lea     r9, [rbp+4Fh+var_90]
0x14000596a  lea     r8, [rbp+4Fh+var_C8]
0x14000596e  mov     rcx, r13
0x140005971  call    BfsFileInPublisherDirectory
0x140005976  mov     ecx, eax; int
0x140005978  test    eax, eax
0x14000597a  jns     short loc_1400059B8
0x14000597c  mov     eax, cs:dword_140019000
0x140005982  cmp     eax, 3
0x140005985  jbe     loc_1400057A4
0x14000598b  lea     rax, [rbp+4Fh+var_CC]
0x14000598f  mov     [rbp+4Fh+var_CC], ecx
0x140005992  mov     [rbp+4Fh+var_60], rax
0x140005996  lea     rdx, byte_140016D91; int
0x14000599d  lea     rax, [rbp+4Fh+var_80]
0x1400059a1  mov     [rbp+4Fh+var_58], 4
0x1400059a9  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x1400059ae  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400059b3  jmp     loc_1400057A4
0x1400059b8  cmp     [rbp+4Fh+var_C8], dil
0x1400059bc  jz      loc_140005B5E
0x1400059c2  test    rbx, rbx
0x1400059c5  jz      short loc_1400059DB
0x1400059c7  cmp     dword ptr [rbx+38h], 2
0x1400059cb  jnz     loc_140005A53
0x1400059d1  xor     edx, edx
0x1400059d3  mov     rcx, rbx; P
0x1400059d6  call    BfsDereferencePolicyEntryEx
0x1400059db  mov     r9, [rbp+4Fh+TokenInformation]
0x1400059df  lea     rax, [rbp+4Fh+var_C0]
0x1400059e3  mov     [rsp+100h+var_D8], rax
0x1400059e8  lea     r8, gBfsPolicyTable
0x1400059ef  mov     rax, [rbp+4Fh+P]
0x1400059f3  mov     rdx, r12
0x1400059f6  mov     r9, [r9]
0x1400059f9  mov     rcx, [rax]
0x1400059fc  mov     [rsp+100h+var_E0], rcx; int
0x140005a01  mov     rcx, r15
0x140005a04  call    BfsGetPolicyEntry
0x140005a09  mov     ecx, eax; int
0x140005a0b  test    eax, eax
0x140005a0d  jns     short loc_140005A4F
0x140005a0f  mov     eax, cs:dword_140019000
0x140005a15  cmp     eax, 3
0x140005a18  jbe     loc_14000579B
0x140005a1e  lea     rax, [rbp+4Fh+var_CC]
0x140005a22  mov     [rbp+4Fh+var_CC], ecx
0x140005a25  mov     [rbp+4Fh+var_60], rax
0x140005a29  lea     rdx, byte_140016D91; int
0x140005a30  lea     rax, [rbp+4Fh+var_80]
0x140005a34  mov     [rbp+4Fh+var_58], 4
0x140005a3c  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005a41  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005a46  mov     rbx, [rbp+4Fh+var_C0]
0x140005a4a  jmp     loc_1400057A4
  ... truncated ...
```
