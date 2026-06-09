# BfsPerformPrompt

- ea: `0x14000dc70`
- end: `0x14000e1f8`
- name: `BfsPerformPrompt`
- size: `1416`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140001ba0`

## callees

- `0x140001008`
- `0x1400061d0`
- `0x1400071d4`
- `0x14000a4f4`
- `0x14000c0f4`
- `0x14000dc70`
- `0x14000e200`
- `0x14000f944`
- `0x1400100e0`
- `0x1400104ec`
- `0x1400132c4`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000dd92`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000dd92`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000e1a4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000e1a4`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e1b8`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e1b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e15a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e177`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e18f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e15a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e177`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e18f`
- `ntoskrnl!SeQueryInformationToken` at `0x14000dcff`
- `ntoskrnl!SeQueryInformationToken` at `0x14000dd5c`
- `ntoskrnl!SeQueryInformationToken` at `0x14000dcff`
- `ntoskrnl!SeQueryInformationToken` at `0x14000dd5c`
- `ntoskrnl!ExAllocatePool2` at `0x14000ddf9`
- `ntoskrnl!ExAllocatePool2` at `0x14000ddf9`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000dfda`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000dfda`
- `FLTMGR!FltReissueSynchronousIo` at `0x14000dfb8`
- `FLTMGR!FltReissueSynchronousIo` at `0x14000dfb8`

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
  int PolicyEntry; // eax
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  char *v46; // rdi
  __int64 v47; // rcx
  __int64 v48; // rcx
  int v50; // [rsp+28h] [rbp-E0h]
  int v51; // [rsp+28h] [rbp-E0h]
  int v52; // [rsp+28h] [rbp-E0h]
  PVOID v53; // [rsp+40h] [rbp-C8h] BYREF
  int v54[2]; // [rsp+48h] [rbp-C0h] BYREF
  PSID *TokenInformation; // [rsp+50h] [rbp-B8h] BYREF
  UNICODE_STRING TokenInformation_8; // [rsp+58h] [rbp-B0h]
  PVOID v57; // [rsp+68h] [rbp-A0h] BYREF
  PSID *v58; // [rsp+70h] [rbp-98h] BYREF
  __m128i v59; // [rsp+78h] [rbp-90h] BYREF
  __int64 v60; // [rsp+88h] [rbp-80h]
  PVOID P; // [rsp+90h] [rbp-78h]
  struct _UNICODE_STRING UnicodeString; // [rsp+98h] [rbp-70h] BYREF
  __int128 v63; // [rsp+A8h] [rbp-60h]
  int v64[4]; // [rsp+B8h] [rbp-50h]
  UNICODE_STRING v65; // [rsp+C8h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v66; // [rsp+D8h] [rbp-30h] BYREF
  PVOID *v67; // [rsp+F8h] [rbp-10h]
  __int64 v68; // [rsp+100h] [rbp-8h]

  v3 = (void *)a3[2];
  v60 = a2;
  *(_QWORD *)v64 = 0;
  v58 = 0;
  v53 = 0;
  v7 = 0;
  LOBYTE(v54[0]) = 0;
  v8 = 0;
  TokenInformation = 0;
  v57 = 0;
  v63 = 0;
  v65 = 0;
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
    LODWORD(v53) = InformationToken;
    goto LABEL_6;
  }
  UserToken = SeQueryInformationToken(v3, TokenAppContainerSid, (PVOID *)&v58);
  if ( UserToken >= 0 )
  {
    UserToken = RtlConvertSidToUnicodeString(&UnicodeString, *TokenInformation, 1u);
    if ( UserToken >= 0 )
    {
      v14 = *(void **)(a2 + 24);
      v7 = 1;
      v15 = *(void **)(a2 + 8);
      *((_QWORD *)&v63 + 1) = a3[6];
      *(_QWORD *)&v63 = v3;
      UserToken = BfsQueueDeferredWorkItemAndWait(v15, v14, Data, (__int64)BfsFileOpenAsUserCallback);
      if ( UserToken >= 0 )
      {
        v16 = v64[0];
        v17 = *(unsigned __int16 *)(a3[6] + 24LL);
        Pool2 = (void *)ExAllocatePool2(256, v17 + 2, 1316185666);
        P = Pool2;
        v22 = (int)Pool2;
        if ( !Pool2 )
        {
          UserToken = -1073741801;
          if ( (unsigned int)dword_140019000 > 3 )
          {
            LODWORD(v53) = -1073741801;
            v67 = &v53;
            v68 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v20, v21, v50, &v66);
          }
          goto LABEL_35;
        }
        RtlStringCbCopyUnicodeString((NTSTRSAFE_PWSTR)Pool2, v17 + 2, (PCUNICODE_STRING)(a3[6] + 24LL));
        v23 = a3[6];
        v24 = a3[7];
        TokenInformation_8 = 0;
        v25 = *(_WORD *)(v23 + 24);
        v26 = *(_WORD *)(v23 + 72);
        v27 = *(_WORD *)(v23 + 8) - v26;
        TokenInformation_8.Buffer = (PWSTR)(*(_QWORD *)(v23 + 16) + 2 * ((unsigned __int64)v25 >> 1));
        TokenInformation_8.Length = v27 - v25;
        TokenInformation_8.MaximumLength = *(_WORD *)(v23 + 10) - v26 - v25;
        v59 = (__m128i)TokenInformation_8;
        UserToken = BfsPromptForConsent(UnicodeString.Buffer, v22, TokenInformation_8.Buffer, v24, (__int64)v54);
        if ( UserToken < 0 )
        {
          v31 = (unsigned int)dword_140019000 <= 3;
          goto LABEL_17;
        }
        v32 = 3;
        if ( LOBYTE(v54[0]) == 1 )
        {
          UserToken = BfsGetUserToken(v3, &v57);
          if ( UserToken < 0 )
          {
            if ( (unsigned int)dword_140019000 > 3 )
            {
              LODWORD(v53) = UserToken;
              v67 = &v53;
              v68 = 4;
              tlgWriteTransfer_EtwWriteTransfer(v33, (int)&byte_140016D91, v34, v35, v51, &v66);
            }
            v8 = v57;
            goto LABEL_34;
          }
          v8 = v57;
          v36 = *(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8);
          v37 = *(_OWORD *)(v36 + 32);
          v38 = *(_OWORD *)(v36 + 48);
          *(_QWORD *)(v36 + 32) = v57;
          v39 = v60;
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
              LODWORD(v53) = UserToken;
              v67 = &v53;
              v68 = 4;
              tlgWriteTransfer_EtwWriteTransfer((int)SecurityContext, (int)&byte_140016D91, v29, v30, v51, &v66);
            }
LABEL_34:
            ExFreePoolWithTag(P, 0);
LABEL_35:
            v7 = 1;
            goto LABEL_36;
          }
          v32 = ((unsigned __int8)BfsQueryAccessOnly(v16, Data) != 0) + 1;
        }
        PolicyEntry = BfsGetPolicyEntry(
                        (int)gBfsFilterHandle,
                        0,
                        (__int64)&gBfsPolicyTable,
                        *TokenInformation,
                        *v58,
                        (__int64 *)&v53);
        v46 = (char *)v53;
        UserToken = PolicyEntry;
        if ( PolicyEntry < 0 )
          goto LABEL_30;
        v47 = *((_QWORD *)v53 + 6);
        v59.m128i_i64[1] = (__int64)(TokenInformation_8.Buffer + 1);
        v59.m128i_i16[0] -= 2;
        v59.m128i_i16[1] -= 2;
        UserToken = BfsAddOrModifyEntry(v47, v16, v32, 0, a3[6] + 24LL, &v59);
        if ( UserToken < 0 )
          goto LABEL_30;
        v48 = a3[6];
        TokenInformation_8 = 0;
        TokenInformation_8.Buffer = *(PWSTR *)(v48 + 16);
        v52 = v16;
        TokenInformation_8.Length = *(_WORD *)(v48 + 8) - *(_WORD *)(v48 + 72);
        TokenInformation_8.MaximumLength = TokenInformation_8.Length;
        v65 = TokenInformation_8;
        UserToken = BfsAddPolicyToGlobalFileTable(
                      (__int64)&gBfsGlobalFileTable,
                      (__int64)*TokenInformation,
                      (__int64)*v58,
                      &v65);
        if ( UserToken < 0 )
        {
LABEL_30:
          if ( (unsigned int)dword_140019000 > 3 )
          {
            v67 = &v53;
            LODWORD(v53) = UserToken;
            v68 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v43, (int)&byte_140016D91, v44, v45, v52, &v66);
          }
        }
        if ( v46 )
          BfsDereferencePolicyEntryEx(v46, 0);
        goto LABEL_34;
      }
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v53) = UserToken;
LABEL_6:
    v68 = 4;
    v67 = &v53;
    tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v10, v11, v50, &v66);
  }
LABEL_36:
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v58 )
    ExFreePoolWithTag(v58, 0);
  if ( v7 )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v8 )
    ObfDereferenceObject(v8);
  return (unsigned int)UserToken;
}

```

## disassembly

```asm
0x14000dc70  mov     rax, rsp
0x14000dc73  mov     [rax+20h], rbx
0x14000dc77  push    rbp
0x14000dc78  push    rsi
0x14000dc79  push    rdi
0x14000dc7a  push    r12
0x14000dc7c  push    r13
0x14000dc7e  push    r14
0x14000dc80  push    r15
0x14000dc82  lea     rbp, [rax-68h]
0x14000dc86  sub     rsp, 130h
0x14000dc8d  movaps  xmmword ptr [rax-48h], xmm6
0x14000dc91  movaps  xmmword ptr [rax-58h], xmm7
0x14000dc95  mov     rax, cs:__security_cookie
0x14000dc9c  xor     rax, rsp
0x14000dc9f  mov     [rbp+60h+var_60], rax
0x14000dca3  mov     rdi, [r8+10h]
0x14000dca7  xorps   xmm0, xmm0
0x14000dcaa  xor     eax, eax
0x14000dcac  mov     [rbp+60h+var_E0], rdx
0x14000dcb0  mov     r13, rcx
0x14000dcb3  mov     qword ptr [rbp+60h+var_B0], rax
0x14000dcb7  xor     ecx, ecx
0x14000dcb9  mov     r14, r8
0x14000dcbc  mov     [rsp+160h+var_F8], rcx
0x14000dcc1  mov     rsi, rdx
0x14000dcc4  mov     [rsp+160h+var_128], rcx
0x14000dcc9  mov     r12b, cl
0x14000dccc  mov     byte ptr [rsp+160h+var_120], cl
0x14000dcd0  mov     r15d, ecx
0x14000dcd3  mov     [rsp+160h+TokenInformation], rcx
0x14000dcd8  mov     [rsp+160h+var_100], rcx
0x14000dcdd  movups  [rbp+60h+var_C0], xmm0
0x14000dce1  movups  [rbp+60h+var_A0], xmm0
0x14000dce5  movups  xmmword ptr [rbp+60h+UnicodeString.Length], xmm0
0x14000dce9  test    rdi, rdi
0x14000dcec  jnz     short loc_14000DCF2
0x14000dcee  mov     rdi, [r8+20h]
0x14000dcf2  lea     r8, [rsp+160h+TokenInformation]; TokenInformation
0x14000dcf7  mov     edx, 1; TokenInformationClass
0x14000dcfc  mov     rcx, rdi; Token
0x14000dcff  call    cs:__imp_SeQueryInformationToken
0x14000dd06  nop     dword ptr [rax+rax+00h]
0x14000dd0b  mov     ebx, eax
0x14000dd0d  test    eax, eax
0x14000dd0f  jns     short loc_14000DD4F
0x14000dd11  mov     ecx, cs:dword_140019000; int
0x14000dd17  cmp     ecx, 3
0x14000dd1a  jbe     loc_14000E16B
0x14000dd20  mov     dword ptr [rsp+160h+var_128], eax
0x14000dd24  lea     rax, [rsp+160h+var_128]
0x14000dd29  mov     [rbp+60h+var_68], 4
0x14000dd31  mov     [rbp+60h+var_70], rax
0x14000dd35  lea     rdx, byte_140016D91; int
0x14000dd3c  lea     rax, [rbp+60h+var_90]
0x14000dd40  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000dd45  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000dd4a  jmp     loc_14000E16B
0x14000dd4f  lea     r8, [rsp+160h+var_F8]; TokenInformation
0x14000dd54  mov     edx, 1Fh; TokenInformationClass
0x14000dd59  mov     rcx, rdi; Token
0x14000dd5c  call    cs:__imp_SeQueryInformationToken
0x14000dd63  nop     dword ptr [rax+rax+00h]
0x14000dd68  mov     ebx, eax
0x14000dd6a  test    eax, eax
0x14000dd6c  jns     short loc_14000DD83
0x14000dd6e  mov     eax, cs:dword_140019000
0x14000dd74  cmp     eax, 3
0x14000dd77  jbe     loc_14000E16B
0x14000dd7d  mov     dword ptr [rsp+160h+var_128], ebx
0x14000dd81  jmp     short loc_14000DD24
0x14000dd83  mov     rdx, [rsp+160h+TokenInformation]
0x14000dd88  lea     rcx, [rbp+60h+UnicodeString]; UnicodeString
0x14000dd8c  mov     r8b, 1; AllocateDestinationString
0x14000dd8f  mov     rdx, [rdx]; Sid
0x14000dd92  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000dd99  nop     dword ptr [rax+rax+00h]
0x14000dd9e  mov     ebx, eax
0x14000dda0  test    eax, eax
0x14000dda2  js      short loc_14000DD6E
0x14000dda4  mov     rax, [r14+30h]
0x14000dda8  lea     r9, [rbp+60h+var_C0]
0x14000ddac  mov     rdx, [rsi+18h]; PVOID
0x14000ddb0  mov     r12b, 1
0x14000ddb3  mov     rcx, [rsi+8]; FltObject
0x14000ddb7  mov     r8, r13; Data
0x14000ddba  mov     qword ptr [rbp+60h+var_C0+8], rax
0x14000ddbe  lea     rax, BfsFileOpenAsUserCallback
0x14000ddc5  mov     [rsp+160h+var_140], rax; int
0x14000ddca  mov     byte ptr [rsp+160h+var_130], r12b
0x14000ddcf  mov     qword ptr [rbp+60h+var_C0], rdi
0x14000ddd3  call    BfsQueueDeferredWorkItemAndWait
0x14000ddd8  mov     ebx, eax
0x14000ddda  test    eax, eax
0x14000dddc  js      short loc_14000DD6E
0x14000ddde  mov     rax, [r14+30h]
0x14000dde2  mov     r8d, 4E736642h
0x14000dde8  mov     r12d, [rbp+60h+var_B0]
0x14000ddec  mov     ecx, 100h
0x14000ddf1  movzx   esi, word ptr [rax+18h]
0x14000ddf5  lea     rdx, [rsi+2]
0x14000ddf9  call    cs:__imp_ExAllocatePool2
0x14000de00  nop     dword ptr [rax+rax+00h]
0x14000de05  mov     [rbp+60h+P], rax
0x14000de09  mov     rbx, rax
0x14000de0c  test    rax, rax
0x14000de0f  jnz     short loc_14000DE54
0x14000de11  mov     eax, cs:dword_140019000
0x14000de17  mov     ebx, 0C0000017h
0x14000de1c  cmp     eax, 3
0x14000de1f  jbe     loc_14000E166
0x14000de25  lea     rax, [rsp+160h+var_128]
0x14000de2a  mov     dword ptr [rsp+160h+var_128], ebx
0x14000de2e  mov     [rbp+60h+var_70], rax
0x14000de32  lea     rdx, byte_140016D91; int
0x14000de39  lea     rax, [rbp+60h+var_90]
0x14000de3d  mov     [rbp+60h+var_68], 4
0x14000de45  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000de4a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000de4f  jmp     loc_14000E166
0x14000de54  mov     r8, [r14+30h]
0x14000de58  lea     rdx, [rsi+2]; cbDest
0x14000de5c  add     r8, 18h; SourceString
0x14000de60  mov     rcx, rbx; pszDest
0x14000de63  call    RtlStringCbCopyUnicodeString
0x14000de68  mov     rdx, [r14+30h]
0x14000de6c  xorps   xmm0, xmm0
0x14000de6f  mov     r9, [r14+38h]
0x14000de73  movups  xmmword ptr [rsp+160h+TokenInformation+8], xmm0
0x14000de78  movzx   r8d, word ptr [rdx+18h]
0x14000de7d  mov     rax, [rdx+10h]
0x14000de81  mov     ecx, r8d
0x14000de84  shr     rcx, 1
0x14000de87  lea     r10, [rax+rcx*2]
0x14000de8b  movzx   ecx, word ptr [rdx+48h]
0x14000de8f  movzx   eax, word ptr [rdx+8]
0x14000de93  sub     ax, cx
0x14000de96  mov     [rsp+160h+var_108], r10
0x14000de9b  sub     ax, r8w
0x14000de9f  mov     word ptr [rsp+160h+TokenInformation+8], ax
0x14000dea4  movzx   eax, word ptr [rdx+0Ah]
0x14000dea8  mov     rdx, rbx
0x14000deab  sub     ax, cx
0x14000deae  mov     rcx, [rbp+60h+UnicodeString.Buffer]
0x14000deb2  sub     ax, r8w
0x14000deb6  mov     r8, r10
0x14000deb9  mov     word ptr [rsp+160h+TokenInformation+0Ah], ax
0x14000debe  lea     rax, [rsp+160h+var_120]
0x14000dec3  movaps  xmm0, xmmword ptr [rsp+160h+TokenInformation+8]
0x14000dec8  movdqa  xmmword ptr [rsp+160h+var_F8+8], xmm0
0x14000dece  mov     [rsp+160h+var_140], rax; int
0x14000ded3  call    BfsPromptForConsent
0x14000ded8  mov     ebx, eax
0x14000deda  test    eax, eax
0x14000dedc  jns     short loc_14000DF1C
0x14000dede  mov     eax, cs:dword_140019000
0x14000dee4  cmp     eax, 3
0x14000dee7  jbe     loc_14000E154
0x14000deed  lea     rax, [rsp+160h+var_128]
0x14000def2  mov     dword ptr [rsp+160h+var_128], ebx
0x14000def6  mov     [rbp+60h+var_70], rax
0x14000defa  lea     rdx, byte_140016D91; int
0x14000df01  lea     rax, [rbp+60h+var_90]
0x14000df05  mov     [rbp+60h+var_68], 4
0x14000df0d  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000df12  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000df17  jmp     loc_14000E154
0x14000df1c  cmp     byte ptr [rsp+160h+var_120], 1
0x14000df21  mov     esi, 3
0x14000df26  jnz     loc_14000E022
0x14000df2c  lea     rdx, [rsp+160h+var_100]
0x14000df31  mov     rcx, rdi
0x14000df34  call    BfsGetUserToken
0x14000df39  mov     ebx, eax
0x14000df3b  test    eax, eax
0x14000df3d  jns     short loc_14000DF7D
0x14000df3f  mov     eax, cs:dword_140019000
0x14000df45  cmp     eax, esi
0x14000df47  jbe     short loc_14000DF73
0x14000df49  lea     rax, [rsp+160h+var_128]
0x14000df4e  mov     dword ptr [rsp+160h+var_128], ebx
0x14000df52  mov     [rbp+60h+var_70], rax
0x14000df56  lea     rdx, byte_140016D91; int
0x14000df5d  lea     rax, [rbp+60h+var_90]
0x14000df61  mov     [rbp+60h+var_68], 4
0x14000df69  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000df6e  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000df73  mov     r15, [rsp+160h+var_100]
0x14000df78  jmp     loc_14000E154
0x14000df7d  mov     rax, [r13+10h]
0x14000df81  mov     rdx, r13; CallbackData
0x14000df84  mov     r15, [rsp+160h+var_100]
0x14000df89  mov     rcx, [rax+18h]
0x14000df8d  mov     rax, [rcx+8]
0x14000df91  movups  xmm6, xmmword ptr [rax+20h]
0x14000df95  movups  xmm7, xmmword ptr [rax+30h]
0x14000df99  mov     [rax+20h], r15
0x14000df9d  mov     rax, [r13+10h]
0x14000dfa1  mov     rcx, [rax+18h]
0x14000dfa5  mov     rax, [rcx+8]
0x14000dfa9  mov     rcx, [rbp+60h+var_E0]
0x14000dfad  mov     dword ptr [rax+28h], 2
0x14000dfb4  mov     rcx, [rcx+18h]; InitiatingInstance
0x14000dfb8  call    cs:__imp_FltReissueSynchronousIo
0x14000dfbf  nop     dword ptr [rax+rax+00h]
0x14000dfc4  mov     rax, [r13+10h]
0x14000dfc8  mov     rcx, [rax+18h]
0x14000dfcc  mov     rax, [rcx+8]
0x14000dfd0  mov     rcx, r13; Data
0x14000dfd3  and     dword ptr [rax+14h], 0FFF3FFFFh
0x14000dfda  call    cs:__imp_FltSetCallbackDataDirty
0x14000dfe1  nop     dword ptr [rax+rax+00h]
0x14000dfe6  mov     rax, [r13+10h]
0x14000dfea  mov     rcx, [rax+18h]
0x14000dfee  mov     rax, [rcx+8]
0x14000dff2  movups  xmmword ptr [rax+20h], xmm6
0x14000dff6  movups  xmmword ptr [rax+30h], xmm7
0x14000dffa  mov     ebx, [r13+18h]
0x14000dffe  test    ebx, ebx
0x14000e000  jns     short loc_14000E00F
0x14000e002  mov     eax, cs:dword_140019000
0x14000e008  cmp     eax, esi
0x14000e00a  jmp     loc_14000DEE7
0x14000e00f  mov     rdx, r13
0x14000e012  mov     ecx, r12d
0x14000e015  call    BfsQueryAccessOnly
0x14000e01a  neg     al
0x14000e01c  sbb     esi, esi
0x14000e01e  neg     esi
0x14000e020  inc     esi
0x14000e022  mov     r9, [rsp+160h+TokenInformation]
0x14000e027  lea     rax, [rsp+160h+var_128]
0x14000e02c  mov     [rsp+160h+var_138], rax
0x14000e031  lea     r8, gBfsPolicyTable
0x14000e038  mov     rax, [rsp+160h+var_F8]
0x14000e03d  xor     edx, edx
0x14000e03f  mov     r9, [r9]
0x14000e042  mov     rcx, [rax]
0x14000e045  mov     [rsp+160h+var_140], rcx
0x14000e04a  mov     rcx, cs:gBfsFilterHandle
0x14000e051  call    BfsGetPolicyEntry
0x14000e056  mov     rdi, [rsp+160h+var_128]
0x14000e05b  mov     ebx, eax
0x14000e05d  test    eax, eax
0x14000e05f  js      loc_14000E110
0x14000e065  mov     rax, [rsp+160h+var_108]
0x14000e06a  lea     rcx, [rsp+160h+var_F8+8]
0x14000e06f  add     rax, 2
0x14000e073  mov     [rsp+160h+var_138], rcx
0x14000e078  mov     rcx, [rdi+30h]
0x14000e07c  xor     r9d, r9d
0x14000e07f  mov     [rsp+160h+var_E8], rax
0x14000e084  mov     r8d, esi
0x14000e087  mov     eax, 0FFFEh
0x14000e08c  mov     edx, r12d
0x14000e08f  add     word ptr [rsp+160h+var_F8+8], ax
0x14000e094  add     word ptr [rsp+160h+var_F8+0Ah], ax
0x14000e099  mov     rax, [r14+30h]
0x14000e09d  add     rax, 18h
0x14000e0a1  mov     [rsp+160h+var_140], rax
0x14000e0a6  call    BfsAddOrModifyEntry
0x14000e0ab  mov     ebx, eax
0x14000e0ad  test    eax, eax
0x14000e0af  js      short loc_14000E110
0x14000e0b1  mov     rcx, [r14+30h]
0x14000e0b5  lea     r9, [rbp+60h+var_A0]
0x14000e0b9  mov     r8, [rsp+160h+var_F8]
0x14000e0be  xorps   xmm0, xmm0
0x14000e0c1  mov     rdx, [rsp+160h+TokenInformation]
0x14000e0c6  movups  xmmword ptr [rsp+160h+TokenInformation+8], xmm0
0x14000e0cb  mov     rax, [rcx+10h]
0x14000e0cf  mov     [rsp+160h+var_108], rax
0x14000e0d4  movzx   eax, word ptr [rcx+48h]
0x14000e0d8  movzx   ecx, word ptr [rcx+8]
0x14000e0dc  sub     cx, ax
0x14000e0df  mov     dword ptr [rsp+160h+var_140], r12d; int
0x14000e0e4  mov     word ptr [rsp+160h+TokenInformation+8], cx
0x14000e0e9  mov     word ptr [rsp+160h+TokenInformation+0Ah], cx
0x14000e0ee  lea     rcx, gBfsGlobalFileTable
0x14000e0f5  movaps  xmm0, xmmword ptr [rsp+160h+TokenInformation+8]
0x14000e0fa  movdqa  [rbp+60h+var_A0], xmm0
0x14000e0ff  mov     r8, [r8]
0x14000e102  mov     rdx, [rdx]
0x14000e105  call    BfsAddPolicyToGlobalFileTable
0x14000e10a  mov     ebx, eax
0x14000e10c  test    eax, eax
0x14000e10e  jns     short loc_14000E145
0x14000e110  mov     eax, cs:dword_140019000
0x14000e116  cmp     eax, 3
0x14000e119  jbe     short loc_14000E145
0x14000e11b  lea     rax, [rsp+160h+var_128]
0x14000e120  mov     [rbp+60h+var_70], rax
0x14000e124  lea     rax, [rbp+60h+var_90]
0x14000e128  mov     [rsp+160h+var_138], rax; PEVENT_DATA_DESCRIPTOR
0x14000e12d  lea     rdx, byte_140016D91; int
0x14000e134  mov     dword ptr [rsp+160h+var_128], ebx
0x14000e138  mov     [rbp+60h+var_68], 4
0x14000e140  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e145  test    rdi, rdi
0x14000e148  jz      short loc_14000E154
  ... truncated ...
```
