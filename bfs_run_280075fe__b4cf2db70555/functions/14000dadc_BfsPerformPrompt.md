# BfsPerformPrompt

- ea: `0x14000dadc`
- end: `0x14000e064`
- name: `BfsPerformPrompt`
- size: `1416`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140001fb0`

## callees

- `0x140001008`
- `0x140006040`
- `0x140007044`
- `0x14000a364`
- `0x14000bf64`
- `0x14000dadc`
- `0x14000e06c`
- `0x14000f7a0`
- `0x14000ff3c`
- `0x14001033c`
- `0x14001318c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000dbfe`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000dbfe`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000e010`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000e010`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e024`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e024`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dfc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dfe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dfc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dfe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dffb`
- `ntoskrnl!SeQueryInformationToken` at `0x14000db6b`
- `ntoskrnl!SeQueryInformationToken` at `0x14000dbc8`
- `ntoskrnl!SeQueryInformationToken` at `0x14000db6b`
- `ntoskrnl!SeQueryInformationToken` at `0x14000dbc8`
- `ntoskrnl!ExAllocatePool2` at `0x14000dc65`
- `ntoskrnl!ExAllocatePool2` at `0x14000dc65`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000de46`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000de46`
- `FLTMGR!FltReissueSynchronousIo` at `0x14000de24`
- `FLTMGR!FltReissueSynchronousIo` at `0x14000de24`

## pseudocode

```c
__int64 __fastcall BfsPerformPrompt(PFLT_CALLBACK_DATA Data, __int64 a2, _QWORD *a3)
{
  void *v3; // rdi
  char v7; // r12
  PVOID v8; // r15
  NTSTATUS InformationToken; // eax
  int v10; // r8d
  int v11; // r9d
  int UserToken; // ebx
  int v13; // ecx
  void *v14; // rdx
  void *v15; // rcx
  unsigned int v16; // r12d
  __int64 v17; // rsi
  void *Pool2; // rax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // r9
  unsigned __int16 v25; // r8
  __int16 v26; // cx
  __int16 v27; // ax
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  int v29; // r8d
  int v30; // r9d
  bool v31; // cc
  int v32; // esi
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  __int64 v36; // rax
  __int128 v37; // xmm6
  __int128 v38; // xmm7
  __int64 v39; // rcx
  __int64 v40; // rax
  PACCESS_STATE AccessState; // rax
  PVOID v42; // rdi
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v49; // [rsp+28h] [rbp-E0h]
  int v50; // [rsp+28h] [rbp-E0h]
  __int64 v51; // [rsp+28h] [rbp-E0h]
  PVOID v52; // [rsp+40h] [rbp-C8h] BYREF
  int v53[2]; // [rsp+48h] [rbp-C0h] BYREF
  PSID *TokenInformation; // [rsp+50h] [rbp-B8h] BYREF
  PVOID TokenInformation_8[2]; // [rsp+58h] [rbp-B0h]
  PVOID v56; // [rsp+68h] [rbp-A0h] BYREF
  __int64 *v57; // [rsp+70h] [rbp-98h] BYREF
  PVOID v58[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v59; // [rsp+88h] [rbp-80h]
  PVOID P; // [rsp+90h] [rbp-78h]
  struct _UNICODE_STRING UnicodeString; // [rsp+98h] [rbp-70h] BYREF
  __int128 v62; // [rsp+A8h] [rbp-60h]
  int v63[4]; // [rsp+B8h] [rbp-50h]
  __int128 v64; // [rsp+C8h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v65; // [rsp+D8h] [rbp-30h] BYREF
  PVOID *v66; // [rsp+F8h] [rbp-10h]
  __int64 v67; // [rsp+100h] [rbp-8h]

  v3 = (void *)a3[2];
  v59 = a2;
  *(_QWORD *)v63 = 0;
  v57 = 0;
  v52 = 0;
  v7 = 0;
  LOBYTE(v53[0]) = 0;
  v8 = 0;
  TokenInformation = 0;
  v56 = 0;
  v62 = 0;
  v64 = 0;
  UnicodeString = 0;
  if ( !v3 )
    v3 = (void *)a3[4];
  InformationToken = SeQueryInformationToken(v3, TokenUser, (PVOID *)&TokenInformation);
  UserToken = InformationToken;
  if ( InformationToken < 0 )
  {
    v13 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_36;
    LODWORD(v52) = InformationToken;
    goto LABEL_6;
  }
  UserToken = SeQueryInformationToken(v3, TokenAppContainerSid, (PVOID *)&v57);
  if ( UserToken >= 0 )
  {
    UserToken = RtlConvertSidToUnicodeString(&UnicodeString, *TokenInformation, 1u);
    if ( UserToken >= 0 )
    {
      v14 = *(void **)(a2 + 24);
      v7 = 1;
      v15 = *(void **)(a2 + 8);
      *((_QWORD *)&v62 + 1) = a3[6];
      *(_QWORD *)&v62 = v3;
      UserToken = BfsQueueDeferredWorkItemAndWait(v15, v14, Data, (__int64)BfsFileOpenAsUserCallback);
      if ( UserToken >= 0 )
      {
        v16 = v63[0];
        v17 = *(unsigned __int16 *)(a3[6] + 24LL);
        Pool2 = (void *)ExAllocatePool2(256, v17 + 2, 1316185666);
        P = Pool2;
        v22 = (int)Pool2;
        if ( !Pool2 )
        {
          UserToken = -1073741801;
          if ( (unsigned int)dword_140019000 > 3 )
          {
            LODWORD(v52) = -1073741801;
            v66 = &v52;
            v67 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v20, v21, v49, &v65);
          }
          goto LABEL_35;
        }
        RtlStringCbCopyUnicodeString((NTSTRSAFE_PWSTR)Pool2, v17 + 2, (PCUNICODE_STRING)(a3[6] + 24LL));
        v23 = a3[6];
        v24 = a3[7];
        *(_OWORD *)TokenInformation_8 = 0;
        v25 = *(_WORD *)(v23 + 24);
        v26 = *(_WORD *)(v23 + 72);
        v27 = *(_WORD *)(v23 + 8) - v26;
        TokenInformation_8[1] = (PVOID)(*(_QWORD *)(v23 + 16) + 2 * ((unsigned __int64)v25 >> 1));
        LOWORD(TokenInformation_8[0]) = v27 - v25;
        WORD1(TokenInformation_8[0]) = *(_WORD *)(v23 + 10) - v26 - v25;
        *(_OWORD *)v58 = *(_OWORD *)TokenInformation_8;
        UserToken = BfsPromptForConsent(UnicodeString.Buffer, v22, TokenInformation_8[1], v24, (__int64)v53);
        if ( UserToken < 0 )
        {
          v31 = (unsigned int)dword_140019000 <= 3;
          goto LABEL_17;
        }
        v32 = 3;
        if ( LOBYTE(v53[0]) == 1 )
        {
          UserToken = BfsGetUserToken(v3, &v56);
          if ( UserToken < 0 )
          {
            if ( (unsigned int)dword_140019000 > 3 )
            {
              LODWORD(v52) = UserToken;
              v66 = &v52;
              v67 = 4;
              tlgWriteTransfer_EtwWriteTransfer(v33, (int)&byte_140016D91, v34, v35, v50, &v65);
            }
            v8 = v56;
            goto LABEL_34;
          }
          v8 = v56;
          v36 = *(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8);
          v37 = *(_OWORD *)(v36 + 32);
          v38 = *(_OWORD *)(v36 + 48);
          *(_QWORD *)(v36 + 32) = v56;
          v39 = v59;
          *(_DWORD *)(*(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8) + 40LL) = 2;
          FltReissueSynchronousIo(*(PFLT_INSTANCE *)(v39 + 24), Data);
          v40 = *(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8);
          *(_DWORD *)(v40 + 20) &= 0xFFF3FFFF;
          FltSetCallbackDataDirty(Data);
          SecurityContext = Data->Iopb->Parameters.Create.SecurityContext;
          AccessState = SecurityContext->AccessState;
          *(_OWORD *)&AccessState->SubjectSecurityContext.ClientToken = v37;
          *(_OWORD *)&AccessState->SubjectSecurityContext.PrimaryToken = v38;
          UserToken = Data->IoStatus.Status;
          if ( UserToken < 0 )
          {
            v31 = (unsigned int)dword_140019000 <= 3;
LABEL_17:
            if ( !v31 )
            {
              LODWORD(v52) = UserToken;
              v66 = &v52;
              v67 = 4;
              tlgWriteTransfer_EtwWriteTransfer((int)SecurityContext, (int)&byte_140016D91, v29, v30, v50, &v65);
            }
LABEL_34:
            ExFreePoolWithTag(P, 0);
LABEL_35:
            v7 = 1;
            goto LABEL_36;
          }
          v32 = ((unsigned __int8)BfsQueryAccessOnly(v16, Data) != 0) + 1;
        }
        v51 = *v57;
        v42 = v52;
        UserToken = BfsGetPolicyEntry(gBfsFilterHandle, 0, &gBfsPolicyTable, *TokenInformation);
        if ( UserToken < 0 )
          goto LABEL_30;
        v46 = *((_QWORD *)v52 + 6);
        v58[1] = (char *)TokenInformation_8[1] + 2;
        LOWORD(v58[0]) -= 2;
        WORD1(v58[0]) -= 2;
        UserToken = BfsAddOrModifyEntry(v46, v16, v32, 0, a3[6] + 24LL, (__int64)v58);
        if ( UserToken < 0 )
          goto LABEL_30;
        v47 = a3[6];
        *(_OWORD *)TokenInformation_8 = 0;
        TokenInformation_8[1] = *(PVOID *)(v47 + 16);
        LODWORD(v51) = v16;
        LOWORD(TokenInformation_8[0]) = *(_WORD *)(v47 + 8) - *(_WORD *)(v47 + 72);
        WORD1(TokenInformation_8[0]) = TokenInformation_8[0];
        v64 = *(_OWORD *)TokenInformation_8;
        UserToken = BfsAddPolicyToGlobalFileTable(&gBfsGlobalFileTable, *TokenInformation, *v57, &v64);
        if ( UserToken < 0 )
        {
LABEL_30:
          if ( (unsigned int)dword_140019000 > 3 )
          {
            v66 = &v52;
            LODWORD(v52) = UserToken;
            v67 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v43, (int)&byte_140016D91, v44, v45, v51, &v65);
          }
        }
        if ( v42 )
          BfsDereferencePolicyEntryEx(v42);
        goto LABEL_34;
      }
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v52) = UserToken;
LABEL_6:
    v67 = 4;
    v66 = &v52;
    tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v10, v11, v49, &v65);
  }
LABEL_36:
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v57 )
    ExFreePoolWithTag(v57, 0);
  if ( v7 )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v8 )
    ObfDereferenceObject(v8);
  return (unsigned int)UserToken;
}

```

## disassembly

```asm
0x14000dadc  mov     rax, rsp
0x14000dadf  mov     [rax+20h], rbx
0x14000dae3  push    rbp
0x14000dae4  push    rsi
0x14000dae5  push    rdi
0x14000dae6  push    r12
0x14000dae8  push    r13
0x14000daea  push    r14
0x14000daec  push    r15
0x14000daee  lea     rbp, [rax-68h]
0x14000daf2  sub     rsp, 130h
0x14000daf9  movaps  xmmword ptr [rax-48h], xmm6
0x14000dafd  movaps  xmmword ptr [rax-58h], xmm7
0x14000db01  mov     rax, cs:__security_cookie
0x14000db08  xor     rax, rsp
0x14000db0b  mov     [rbp+60h+var_60], rax
0x14000db0f  mov     rdi, [r8+10h]
0x14000db13  xorps   xmm0, xmm0
0x14000db16  xor     eax, eax
0x14000db18  mov     [rbp+60h+var_E0], rdx
0x14000db1c  mov     r13, rcx
0x14000db1f  mov     qword ptr [rbp+60h+var_B0], rax
0x14000db23  xor     ecx, ecx
0x14000db25  mov     r14, r8
0x14000db28  mov     [rsp+160h+var_F8], rcx
0x14000db2d  mov     rsi, rdx
0x14000db30  mov     [rsp+160h+var_128], rcx
0x14000db35  mov     r12b, cl
0x14000db38  mov     byte ptr [rsp+160h+var_120], cl
0x14000db3c  mov     r15d, ecx
0x14000db3f  mov     [rsp+160h+TokenInformation], rcx
0x14000db44  mov     [rsp+160h+var_100], rcx
0x14000db49  movups  [rbp+60h+var_C0], xmm0
0x14000db4d  movups  [rbp+60h+var_A0], xmm0
0x14000db51  movups  xmmword ptr [rbp+60h+UnicodeString.Length], xmm0
0x14000db55  test    rdi, rdi
0x14000db58  jnz     short loc_14000DB5E
0x14000db5a  mov     rdi, [r8+20h]
0x14000db5e  lea     r8, [rsp+160h+TokenInformation]; TokenInformation
0x14000db63  mov     edx, 1; TokenInformationClass
0x14000db68  mov     rcx, rdi; Token
0x14000db6b  call    cs:__imp_SeQueryInformationToken
0x14000db72  nop     dword ptr [rax+rax+00h]
0x14000db77  mov     ebx, eax
0x14000db79  test    eax, eax
0x14000db7b  jns     short loc_14000DBBB
0x14000db7d  mov     ecx, cs:dword_140019000; int
0x14000db83  cmp     ecx, 3
0x14000db86  jbe     loc_14000DFD7
0x14000db8c  mov     dword ptr [rsp+160h+var_128], eax
0x14000db90  lea     rax, [rsp+160h+var_128]
0x14000db95  mov     [rbp+60h+var_68], 4
0x14000db9d  mov     [rbp+60h+var_70], rax
0x14000dba1  lea     rdx, byte_140016D91; int
0x14000dba8  lea     rax, [rbp+60h+var_90]
0x14000dbac  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000dbb1  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000dbb6  jmp     loc_14000DFD7
0x14000dbbb  lea     r8, [rsp+160h+var_F8]; TokenInformation
0x14000dbc0  mov     edx, 1Fh; TokenInformationClass
0x14000dbc5  mov     rcx, rdi; Token
0x14000dbc8  call    cs:__imp_SeQueryInformationToken
0x14000dbcf  nop     dword ptr [rax+rax+00h]
0x14000dbd4  mov     ebx, eax
0x14000dbd6  test    eax, eax
0x14000dbd8  jns     short loc_14000DBEF
0x14000dbda  mov     eax, cs:dword_140019000
0x14000dbe0  cmp     eax, 3
0x14000dbe3  jbe     loc_14000DFD7
0x14000dbe9  mov     dword ptr [rsp+160h+var_128], ebx
0x14000dbed  jmp     short loc_14000DB90
0x14000dbef  mov     rdx, [rsp+160h+TokenInformation]
0x14000dbf4  lea     rcx, [rbp+60h+UnicodeString]; UnicodeString
0x14000dbf8  mov     r8b, 1; AllocateDestinationString
0x14000dbfb  mov     rdx, [rdx]; Sid
0x14000dbfe  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000dc05  nop     dword ptr [rax+rax+00h]
0x14000dc0a  mov     ebx, eax
0x14000dc0c  test    eax, eax
0x14000dc0e  js      short loc_14000DBDA
0x14000dc10  mov     rax, [r14+30h]
0x14000dc14  lea     r9, [rbp+60h+var_C0]
0x14000dc18  mov     rdx, [rsi+18h]; PVOID
0x14000dc1c  mov     r12b, 1
0x14000dc1f  mov     rcx, [rsi+8]; FltObject
0x14000dc23  mov     r8, r13; Data
0x14000dc26  mov     qword ptr [rbp+60h+var_C0+8], rax
0x14000dc2a  lea     rax, BfsFileOpenAsUserCallback
0x14000dc31  mov     [rsp+160h+var_140], rax; int
0x14000dc36  mov     byte ptr [rsp+160h+var_130], r12b
0x14000dc3b  mov     qword ptr [rbp+60h+var_C0], rdi
0x14000dc3f  call    BfsQueueDeferredWorkItemAndWait
0x14000dc44  mov     ebx, eax
0x14000dc46  test    eax, eax
0x14000dc48  js      short loc_14000DBDA
0x14000dc4a  mov     rax, [r14+30h]
0x14000dc4e  mov     r8d, 4E736642h
0x14000dc54  mov     r12d, [rbp+60h+var_B0]
0x14000dc58  mov     ecx, 100h
0x14000dc5d  movzx   esi, word ptr [rax+18h]
0x14000dc61  lea     rdx, [rsi+2]
0x14000dc65  call    cs:__imp_ExAllocatePool2
0x14000dc6c  nop     dword ptr [rax+rax+00h]
0x14000dc71  mov     [rbp+60h+P], rax
0x14000dc75  mov     rbx, rax
0x14000dc78  test    rax, rax
0x14000dc7b  jnz     short loc_14000DCC0
0x14000dc7d  mov     eax, cs:dword_140019000
0x14000dc83  mov     ebx, 0C0000017h
0x14000dc88  cmp     eax, 3
0x14000dc8b  jbe     loc_14000DFD2
0x14000dc91  lea     rax, [rsp+160h+var_128]
0x14000dc96  mov     dword ptr [rsp+160h+var_128], ebx
0x14000dc9a  mov     [rbp+60h+var_70], rax
0x14000dc9e  lea     rdx, byte_140016D91; int
0x14000dca5  lea     rax, [rbp+60h+var_90]
0x14000dca9  mov     [rbp+60h+var_68], 4
0x14000dcb1  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000dcb6  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000dcbb  jmp     loc_14000DFD2
0x14000dcc0  mov     r8, [r14+30h]
0x14000dcc4  lea     rdx, [rsi+2]; cbDest
0x14000dcc8  add     r8, 18h; SourceString
0x14000dccc  mov     rcx, rbx; pszDest
0x14000dccf  call    RtlStringCbCopyUnicodeString
0x14000dcd4  mov     rdx, [r14+30h]
0x14000dcd8  xorps   xmm0, xmm0
0x14000dcdb  mov     r9, [r14+38h]
0x14000dcdf  movups  xmmword ptr [rsp+160h+TokenInformation+8], xmm0
0x14000dce4  movzx   r8d, word ptr [rdx+18h]
0x14000dce9  mov     rax, [rdx+10h]
0x14000dced  mov     ecx, r8d
0x14000dcf0  shr     rcx, 1
0x14000dcf3  lea     r10, [rax+rcx*2]
0x14000dcf7  movzx   ecx, word ptr [rdx+48h]
0x14000dcfb  movzx   eax, word ptr [rdx+8]
0x14000dcff  sub     ax, cx
0x14000dd02  mov     [rsp+160h+var_108], r10
0x14000dd07  sub     ax, r8w
0x14000dd0b  mov     word ptr [rsp+160h+TokenInformation+8], ax
0x14000dd10  movzx   eax, word ptr [rdx+0Ah]
0x14000dd14  mov     rdx, rbx
0x14000dd17  sub     ax, cx
0x14000dd1a  mov     rcx, [rbp+60h+UnicodeString.Buffer]
0x14000dd1e  sub     ax, r8w
0x14000dd22  mov     r8, r10
0x14000dd25  mov     word ptr [rsp+160h+TokenInformation+0Ah], ax
0x14000dd2a  lea     rax, [rsp+160h+var_120]
0x14000dd2f  movaps  xmm0, xmmword ptr [rsp+160h+TokenInformation+8]
0x14000dd34  movdqa  xmmword ptr [rsp+160h+var_F8+8], xmm0
0x14000dd3a  mov     [rsp+160h+var_140], rax; int
0x14000dd3f  call    BfsPromptForConsent
0x14000dd44  mov     ebx, eax
0x14000dd46  test    eax, eax
0x14000dd48  jns     short loc_14000DD88
0x14000dd4a  mov     eax, cs:dword_140019000
0x14000dd50  cmp     eax, 3
0x14000dd53  jbe     loc_14000DFC0
0x14000dd59  lea     rax, [rsp+160h+var_128]
0x14000dd5e  mov     dword ptr [rsp+160h+var_128], ebx
0x14000dd62  mov     [rbp+60h+var_70], rax
0x14000dd66  lea     rdx, byte_140016D91; int
0x14000dd6d  lea     rax, [rbp+60h+var_90]
0x14000dd71  mov     [rbp+60h+var_68], 4
0x14000dd79  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000dd7e  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000dd83  jmp     loc_14000DFC0
0x14000dd88  cmp     byte ptr [rsp+160h+var_120], 1
0x14000dd8d  mov     esi, 3
0x14000dd92  jnz     loc_14000DE8E
0x14000dd98  lea     rdx, [rsp+160h+var_100]
0x14000dd9d  mov     rcx, rdi
0x14000dda0  call    BfsGetUserToken
0x14000dda5  mov     ebx, eax
0x14000dda7  test    eax, eax
0x14000dda9  jns     short loc_14000DDE9
0x14000ddab  mov     eax, cs:dword_140019000
0x14000ddb1  cmp     eax, esi
0x14000ddb3  jbe     short loc_14000DDDF
0x14000ddb5  lea     rax, [rsp+160h+var_128]
0x14000ddba  mov     dword ptr [rsp+160h+var_128], ebx
0x14000ddbe  mov     [rbp+60h+var_70], rax
0x14000ddc2  lea     rdx, byte_140016D91; int
0x14000ddc9  lea     rax, [rbp+60h+var_90]
0x14000ddcd  mov     [rbp+60h+var_68], 4
0x14000ddd5  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000ddda  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000dddf  mov     r15, [rsp+160h+var_100]
0x14000dde4  jmp     loc_14000DFC0
0x14000dde9  mov     rax, [r13+10h]
0x14000dded  mov     rdx, r13; CallbackData
0x14000ddf0  mov     r15, [rsp+160h+var_100]
0x14000ddf5  mov     rcx, [rax+18h]
0x14000ddf9  mov     rax, [rcx+8]
0x14000ddfd  movups  xmm6, xmmword ptr [rax+20h]
0x14000de01  movups  xmm7, xmmword ptr [rax+30h]
0x14000de05  mov     [rax+20h], r15
0x14000de09  mov     rax, [r13+10h]
0x14000de0d  mov     rcx, [rax+18h]
0x14000de11  mov     rax, [rcx+8]
0x14000de15  mov     rcx, [rbp+60h+var_E0]
0x14000de19  mov     dword ptr [rax+28h], 2
0x14000de20  mov     rcx, [rcx+18h]; InitiatingInstance
0x14000de24  call    cs:__imp_FltReissueSynchronousIo
0x14000de2b  nop     dword ptr [rax+rax+00h]
0x14000de30  mov     rax, [r13+10h]
0x14000de34  mov     rcx, [rax+18h]
0x14000de38  mov     rax, [rcx+8]
0x14000de3c  mov     rcx, r13; Data
0x14000de3f  and     dword ptr [rax+14h], 0FFF3FFFFh
0x14000de46  call    cs:__imp_FltSetCallbackDataDirty
0x14000de4d  nop     dword ptr [rax+rax+00h]
0x14000de52  mov     rax, [r13+10h]
0x14000de56  mov     rcx, [rax+18h]
0x14000de5a  mov     rax, [rcx+8]
0x14000de5e  movups  xmmword ptr [rax+20h], xmm6
0x14000de62  movups  xmmword ptr [rax+30h], xmm7
0x14000de66  mov     ebx, [r13+18h]
0x14000de6a  test    ebx, ebx
0x14000de6c  jns     short loc_14000DE7B
0x14000de6e  mov     eax, cs:dword_140019000
0x14000de74  cmp     eax, esi
0x14000de76  jmp     loc_14000DD53
0x14000de7b  mov     rdx, r13
0x14000de7e  mov     ecx, r12d
0x14000de81  call    BfsQueryAccessOnly
0x14000de86  neg     al
0x14000de88  sbb     esi, esi
0x14000de8a  neg     esi
0x14000de8c  inc     esi
0x14000de8e  mov     r9, [rsp+160h+TokenInformation]
0x14000de93  lea     rax, [rsp+160h+var_128]
0x14000de98  mov     [rsp+160h+var_138], rax
0x14000de9d  lea     r8, gBfsPolicyTable
0x14000dea4  mov     rax, [rsp+160h+var_F8]
0x14000dea9  xor     edx, edx
0x14000deab  mov     r9, [r9]
0x14000deae  mov     rcx, [rax]
0x14000deb1  mov     [rsp+160h+var_140], rcx
0x14000deb6  mov     rcx, cs:gBfsFilterHandle
0x14000debd  call    BfsGetPolicyEntry
0x14000dec2  mov     rdi, [rsp+160h+var_128]
0x14000dec7  mov     ebx, eax
0x14000dec9  test    eax, eax
0x14000decb  js      loc_14000DF7C
0x14000ded1  mov     rax, [rsp+160h+var_108]
0x14000ded6  lea     rcx, [rsp+160h+var_F8+8]
0x14000dedb  add     rax, 2
0x14000dedf  mov     [rsp+160h+var_138], rcx
0x14000dee4  mov     rcx, [rdi+30h]
0x14000dee8  xor     r9d, r9d
0x14000deeb  mov     [rsp+160h+var_E8], rax
0x14000def0  mov     r8d, esi
0x14000def3  mov     eax, 0FFFEh
0x14000def8  mov     edx, r12d
0x14000defb  add     word ptr [rsp+160h+var_F8+8], ax
0x14000df00  add     word ptr [rsp+160h+var_F8+0Ah], ax
0x14000df05  mov     rax, [r14+30h]
0x14000df09  add     rax, 18h
0x14000df0d  mov     [rsp+160h+var_140], rax
0x14000df12  call    BfsAddOrModifyEntry
0x14000df17  mov     ebx, eax
0x14000df19  test    eax, eax
0x14000df1b  js      short loc_14000DF7C
0x14000df1d  mov     rcx, [r14+30h]
0x14000df21  lea     r9, [rbp+60h+var_A0]
0x14000df25  mov     r8, [rsp+160h+var_F8]
0x14000df2a  xorps   xmm0, xmm0
0x14000df2d  mov     rdx, [rsp+160h+TokenInformation]
0x14000df32  movups  xmmword ptr [rsp+160h+TokenInformation+8], xmm0
0x14000df37  mov     rax, [rcx+10h]
0x14000df3b  mov     [rsp+160h+var_108], rax
0x14000df40  movzx   eax, word ptr [rcx+48h]
0x14000df44  movzx   ecx, word ptr [rcx+8]
0x14000df48  sub     cx, ax
0x14000df4b  mov     dword ptr [rsp+160h+var_140], r12d; int
0x14000df50  mov     word ptr [rsp+160h+TokenInformation+8], cx
0x14000df55  mov     word ptr [rsp+160h+TokenInformation+0Ah], cx
0x14000df5a  lea     rcx, gBfsGlobalFileTable
0x14000df61  movaps  xmm0, xmmword ptr [rsp+160h+TokenInformation+8]
0x14000df66  movdqa  [rbp+60h+var_A0], xmm0
0x14000df6b  mov     r8, [r8]
0x14000df6e  mov     rdx, [rdx]
0x14000df71  call    BfsAddPolicyToGlobalFileTable
0x14000df76  mov     ebx, eax
0x14000df78  test    eax, eax
0x14000df7a  jns     short loc_14000DFB1
0x14000df7c  mov     eax, cs:dword_140019000
0x14000df82  cmp     eax, 3
0x14000df85  jbe     short loc_14000DFB1
0x14000df87  lea     rax, [rsp+160h+var_128]
0x14000df8c  mov     [rbp+60h+var_70], rax
0x14000df90  lea     rax, [rbp+60h+var_90]
0x14000df94  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000df99  lea     rdx, byte_140016D91; int
0x14000dfa0  mov     dword ptr [rsp+160h+var_128], ebx
0x14000dfa4  mov     [rbp+60h+var_68], 4
0x14000dfac  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000dfb1  test    rdi, rdi
0x14000dfb4  jz      short loc_14000DFC0
  ... truncated ...
```
