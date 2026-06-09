# BfsRedirectNamedPipe

- ea: `0x14000b7bc`
- end: `0x14000bd03`
- name: `BfsRedirectNamedPipe`
- size: `1351`
- prototype: `__int64 __fastcall(PFLT_FILTER Filter, PFLT_CALLBACK_DATA Data, PSID SourceSid, PSID, __int64, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140001460`

## callees

- `0x140001008`
- `0x14000b7bc`
- `0x14000bde4`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x14000b890`
- `ntoskrnl!RtlCopySid` at `0x14000b9ad`
- `ntoskrnl!RtlCopySid` at `0x14000b890`
- `ntoskrnl!RtlCopySid` at `0x14000b9ad`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000ba6a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000bad1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000ba6a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000bad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b918`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b92f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b940`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bab9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b918`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b92f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b940`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bab9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000ba53`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bba9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bbeb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000ba53`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bba9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bbeb`
- `ntoskrnl!ExAllocatePool2` at `0x14000b824`
- `ntoskrnl!ExAllocatePool2` at `0x14000b969`
- `ntoskrnl!ExAllocatePool2` at `0x14000ba20`
- `ntoskrnl!ExAllocatePool2` at `0x14000baf7`
- `ntoskrnl!ExAllocatePool2` at `0x14000bb41`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbc2`
- `ntoskrnl!ExAllocatePool2` at `0x14000b824`
- `ntoskrnl!ExAllocatePool2` at `0x14000b969`
- `ntoskrnl!ExAllocatePool2` at `0x14000ba20`
- `ntoskrnl!ExAllocatePool2` at `0x14000baf7`
- `ntoskrnl!ExAllocatePool2` at `0x14000bb41`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbc2`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14000bc01`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14000bc01`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14000bcc2`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14000bcc2`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14000bc7c`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14000bc7c`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x14000bc3f`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x14000bc3f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14000bc23`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14000bc23`

## pseudocode

```c
__int64 __fastcall BfsRedirectNamedPipe(
        PFLT_FILTER Filter,
        PFLT_CALLBACK_DATA Data,
        unsigned __int8 *SourceSid,
        unsigned __int8 *a4,
        __int64 a5,
        PCUNICODE_STRING Source)
{
  __int64 v7; // rdx
  void *v10; // rsi
  void *Pool2; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING *v17; // rdi
  NTSTATUS v18; // eax
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  PVOID v22; // r15
  PWSTR Buffer; // rcx
  PWSTR v24; // rcx
  void *v25; // rax
  bool v26; // cc
  unsigned __int16 v27; // ax
  unsigned __int16 v28; // cx
  USHORT v29; // bx
  void *v30; // rax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  PVOID *v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rax
  int CleanupCallback; // [rsp+20h] [rbp-89h]
  __int64 v43; // [rsp+40h] [rbp-69h] BYREF
  PVOID P; // [rsp+48h] [rbp-61h]
  PECP_LIST EcpList; // [rsp+50h] [rbp-59h] BYREF
  PVOID EcpContext; // [rsp+58h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-49h] BYREF
  PVOID v48; // [rsp+70h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+78h] [rbp-31h] BYREF
  __int64 *v50; // [rsp+98h] [rbp-11h]
  __int64 v51; // [rsp+A0h] [rbp-9h]

  v7 = SourceSid[1];
  v10 = 0;
  v43 = a5;
  EcpContext = 0;
  EcpList = 0;
  DestinationString = 0;
  Pool2 = (void *)ExAllocatePool2(256, 4 * v7 + 8, 1400071746);
  P = Pool2;
  if ( !Pool2 )
  {
    appended = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v43) = -1073741801;
      v50 = &v43;
      v51 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v14, v15, CleanupCallback, &v49);
    }
    return (unsigned int)appended;
  }
  v17 = 0;
  v18 = RtlCopySid(4 * SourceSid[1] + 8, Pool2, SourceSid);
  appended = v18;
  if ( v18 >= 0 )
  {
    v25 = (void *)ExAllocatePool2(256, 4LL * a4[1] + 8, 1400071746);
    v10 = v25;
    if ( !v25 )
    {
      v21 = dword_140019000;
      v26 = (unsigned int)dword_140019000 <= 3;
LABEL_19:
      appended = -1073741801;
      if ( v26 )
        goto LABEL_8;
      LODWORD(v43) = -1073741801;
      goto LABEL_7;
    }
    appended = RtlCopySid(4 * a4[1] + 8, v25, a4);
    if ( appended < 0 )
    {
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_8;
      LODWORD(v43) = appended;
      goto LABEL_7;
    }
    v27 = *(_WORD *)(v43 + 24);
    v28 = v27 + 14;
    if ( (unsigned __int16)(v27 + 14) < v27 || (v29 = Source->Length + v28, v29 < v28) )
    {
      v21 = -1073741675;
      appended = -1073741675;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_8;
      LODWORD(v43) = -1073741675;
      goto LABEL_7;
    }
    v30 = (void *)ExAllocatePool2(256, v29, 1181967938);
    v48 = v30;
    if ( !v30 )
    {
      v26 = (unsigned int)dword_140019000 <= 3;
      goto LABEL_19;
    }
    DestinationString.Buffer = (PWSTR)v30;
    DestinationString.MaximumLength = v29;
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v43 + 24));
    appended = RtlAppendUnicodeStringToString(&DestinationString, &ReparsePrefixString);
    if ( appended < 0 || (appended = RtlAppendUnicodeStringToString(&DestinationString, Source), appended < 0) )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v43) = appended;
LABEL_33:
        v51 = 4;
        v50 = &v43;
        tlgWriteTransfer_EtwWriteTransfer(v31, (int)&byte_140016D91, v32, v33, CleanupCallback, &v49);
      }
    }
    else
    {
      v34 = (PVOID *)ExAllocatePool2(256, 48, 1383294530);
      v17 = (struct _UNICODE_STRING *)v34;
      if ( v34 )
      {
        v35 = v43;
        v22 = P;
        *v34 = P;
        v34[1] = v10;
        v36 = ExAllocatePool2(256, *(unsigned __int16 *)(v35 + 8), 1181967938);
        v17[1].Buffer = (PWSTR)v36;
        if ( v36
          && (v17[1].MaximumLength = *(_WORD *)(v35 + 8),
              RtlCopyUnicodeString(v17 + 1, (PCUNICODE_STRING)(v35 + 8)),
              v40 = ExAllocatePool2(256, DestinationString.Length, 1181967938),
              (v17[2].Buffer = (PWSTR)v40) != 0) )
        {
          v17[2].MaximumLength = DestinationString.Length;
          RtlCopyUnicodeString(v17 + 2, &DestinationString);
          appended = FltGetEcpListFromCallbackData(Filter, Data, &EcpList);
          if ( appended >= 0 )
          {
            if ( EcpList
              || (appended = FltAllocateExtraCreateParameterList(Filter, 0, &EcpList), appended >= 0)
              && (appended = FltSetEcpListIntoCallbackData(Filter, Data, EcpList), appended >= 0) )
            {
              appended = FltAllocateExtraCreateParameter(Filter, &BfsEcpType, 0x10u, 0, 0, 0x70736642u, &EcpContext);
              if ( appended >= 0 )
              {
                *(_DWORD *)EcpContext = 1;
                *((_QWORD *)EcpContext + 1) = v17;
                appended = FltInsertExtraCreateParameter(Filter, EcpList, EcpContext);
                if ( appended >= 0 )
                {
                  BfsReparseNamedPipe(Data);
                  return (unsigned int)appended;
                }
              }
            }
          }
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_35;
          LODWORD(v43) = appended;
        }
        else
        {
          appended = -1073741801;
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_35;
          LODWORD(v43) = -1073741801;
        }
        v51 = 4;
        v50 = &v43;
        tlgWriteTransfer_EtwWriteTransfer(v37, (int)&byte_140016D91, v38, v39, CleanupCallback, &v49);
        goto LABEL_35;
      }
      appended = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v43) = -1073741801;
        goto LABEL_33;
      }
    }
    v22 = P;
LABEL_35:
    ExFreePoolWithTag(v48, 0);
    goto LABEL_9;
  }
  v21 = dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v43) = v18;
LABEL_7:
    v51 = 4;
    v50 = &v43;
    tlgWriteTransfer_EtwWriteTransfer(v21, (int)&byte_140016D91, v19, v20, CleanupCallback, &v49);
  }
LABEL_8:
  v22 = P;
LABEL_9:
  ExFreePoolWithTag(v22, 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( v17 )
  {
    Buffer = v17[1].Buffer;
    if ( Buffer )
      ExFreePoolWithTag(Buffer, 0);
    v24 = v17[2].Buffer;
    if ( v24 )
      ExFreePoolWithTag(v24, 0);
    ExFreePoolWithTag(v17, 0);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14000b7bc  push    rbp
0x14000b7be  push    rbx
0x14000b7bf  push    rsi
0x14000b7c0  push    rdi
0x14000b7c1  push    r12
0x14000b7c3  push    r13
0x14000b7c5  push    r14
0x14000b7c7  push    r15
0x14000b7c9  lea     rbp, [rsp-0Fh]
0x14000b7ce  sub     rsp, 0B8h
0x14000b7d5  mov     rax, cs:__security_cookie
0x14000b7dc  xor     rax, rsp
0x14000b7df  mov     [rbp+47h+var_48], rax
0x14000b7e3  mov     rax, [rbp+47h+arg_20]
0x14000b7e7  mov     r12, rdx
0x14000b7ea  movzx   edx, byte ptr [r8+1]
0x14000b7ef  mov     rbx, r8
0x14000b7f2  mov     r13, [rbp+47h+Source]
0x14000b7f6  mov     r14, rcx
0x14000b7f9  xor     esi, esi
0x14000b7fb  mov     [rbp+47h+var_B0], rax
0x14000b7ff  xorps   xmm0, xmm0
0x14000b802  mov     [rbp+47h+var_98], rsi
0x14000b806  lea     rdx, ds:8[rdx*4]
0x14000b80e  mov     [rbp+47h+EcpList], rsi
0x14000b812  mov     ecx, 100h
0x14000b817  mov     r8d, 53736642h
0x14000b81d  mov     r15, r9
0x14000b820  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x14000b824  call    cs:__imp_ExAllocatePool2
0x14000b82b  nop     dword ptr [rax+rax+00h]
0x14000b830  mov     [rbp+47h+P], rax
0x14000b834  test    rax, rax
0x14000b837  jnz     short loc_14000B87C
0x14000b839  mov     eax, cs:dword_140019000
0x14000b83f  mov     edx, 0C0000017h
0x14000b844  mov     ebx, edx
0x14000b846  cmp     eax, 3
0x14000b849  jbe     loc_14000BCE0
0x14000b84f  lea     rax, [rbp+47h+var_B0]
0x14000b853  mov     dword ptr [rbp+47h+var_B0], edx
0x14000b856  mov     [rbp+47h+var_58], rax
0x14000b85a  lea     rdx, byte_140016D91; int
0x14000b861  lea     rax, [rbp+47h+var_78]
0x14000b865  mov     [rbp+47h+var_50], 4
0x14000b86d  mov     qword ptr [rsp+0F0h+PoolTag], rax; PEVENT_DATA_DESCRIPTOR
0x14000b872  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000b877  jmp     loc_14000BCE0
0x14000b87c  movzx   ecx, byte ptr [rbx+1]
0x14000b880  mov     r8, rbx; SourceSid
0x14000b883  mov     rdx, rax; DestinationSid
0x14000b886  mov     rdi, rsi
0x14000b889  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000b890  call    cs:__imp_RtlCopySid
0x14000b897  nop     dword ptr [rax+rax+00h]
0x14000b89c  mov     ebx, eax
0x14000b89e  test    eax, eax
0x14000b8a0  jns     loc_14000B951
0x14000b8a6  mov     ecx, cs:dword_140019000; int
0x14000b8ac  cmp     ecx, 3
0x14000b8af  jbe     short loc_14000B8D9
0x14000b8b1  mov     dword ptr [rbp+47h+var_B0], eax
0x14000b8b4  lea     rax, [rbp+47h+var_B0]
0x14000b8b8  mov     [rbp+47h+var_50], 4
0x14000b8c0  mov     [rbp+47h+var_58], rax
0x14000b8c4  lea     rdx, byte_140016D91; int
0x14000b8cb  lea     rax, [rbp+47h+var_78]
0x14000b8cf  mov     qword ptr [rsp+0F0h+PoolTag], rax; PEVENT_DATA_DESCRIPTOR
0x14000b8d4  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000b8d9  mov     r15, [rbp+47h+P]
0x14000b8dd  xor     edx, edx; Tag
0x14000b8df  mov     rcx, r15; P
0x14000b8e2  call    cs:__imp_ExFreePoolWithTag
0x14000b8e9  nop     dword ptr [rax+rax+00h]
0x14000b8ee  test    rsi, rsi
0x14000b8f1  jz      short loc_14000B904
0x14000b8f3  xor     edx, edx; Tag
0x14000b8f5  mov     rcx, rsi; P
0x14000b8f8  call    cs:__imp_ExFreePoolWithTag
0x14000b8ff  nop     dword ptr [rax+rax+00h]
0x14000b904  test    rdi, rdi
0x14000b907  jz      loc_14000BCE0
0x14000b90d  mov     rcx, [rdi+18h]; P
0x14000b911  test    rcx, rcx
0x14000b914  jz      short loc_14000B924
0x14000b916  xor     edx, edx; Tag
0x14000b918  call    cs:__imp_ExFreePoolWithTag
0x14000b91f  nop     dword ptr [rax+rax+00h]
0x14000b924  mov     rcx, [rdi+28h]; P
0x14000b928  test    rcx, rcx
0x14000b92b  jz      short loc_14000B93B
0x14000b92d  xor     edx, edx; Tag
0x14000b92f  call    cs:__imp_ExFreePoolWithTag
0x14000b936  nop     dword ptr [rax+rax+00h]
0x14000b93b  xor     edx, edx; Tag
0x14000b93d  mov     rcx, rdi; P
0x14000b940  call    cs:__imp_ExFreePoolWithTag
0x14000b947  nop     dword ptr [rax+rax+00h]
0x14000b94c  jmp     loc_14000BCE0
0x14000b951  movzx   edx, byte ptr [r15+1]
0x14000b956  mov     ecx, 100h
0x14000b95b  mov     r8d, 53736642h
0x14000b961  lea     rdx, ds:8[rdx*4]
0x14000b969  call    cs:__imp_ExAllocatePool2
0x14000b970  nop     dword ptr [rax+rax+00h]
0x14000b975  mov     rsi, rax
0x14000b978  test    rax, rax
0x14000b97b  jnz     short loc_14000B99B
0x14000b97d  mov     ecx, cs:dword_140019000
0x14000b983  cmp     ecx, 3
0x14000b986  mov     edx, 0C0000017h
0x14000b98b  mov     ebx, edx
0x14000b98d  jbe     loc_14000B8D9
0x14000b993  mov     dword ptr [rbp+47h+var_B0], edx
0x14000b996  jmp     loc_14000B8B4
0x14000b99b  movzx   ecx, byte ptr [r15+1]
0x14000b9a0  mov     r8, r15; SourceSid
0x14000b9a3  mov     rdx, rsi; DestinationSid
0x14000b9a6  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000b9ad  call    cs:__imp_RtlCopySid
0x14000b9b4  nop     dword ptr [rax+rax+00h]
0x14000b9b9  mov     ebx, eax
0x14000b9bb  test    eax, eax
0x14000b9bd  jns     short loc_14000B9D6
0x14000b9bf  mov     eax, cs:dword_140019000
0x14000b9c5  cmp     eax, 3
0x14000b9c8  jbe     loc_14000B8D9
0x14000b9ce  mov     dword ptr [rbp+47h+var_B0], ebx
0x14000b9d1  jmp     loc_14000B8B4
0x14000b9d6  mov     r15, [rbp+47h+var_B0]
0x14000b9da  movzx   eax, word ptr [r15+18h]
0x14000b9df  lea     ecx, [rax+0Eh]
0x14000b9e2  cmp     cx, ax
0x14000b9e5  jnb     short loc_14000BA05
0x14000b9e7  mov     eax, cs:dword_140019000
0x14000b9ed  mov     ecx, 0C0000095h
0x14000b9f2  mov     ebx, ecx
0x14000b9f4  cmp     eax, 3
0x14000b9f7  jbe     loc_14000B8D9
0x14000b9fd  mov     dword ptr [rbp+47h+var_B0], ecx
0x14000ba00  jmp     loc_14000B8B4
0x14000ba05  movzx   ebx, cx
0x14000ba08  add     bx, [r13+0]
0x14000ba0d  cmp     bx, cx
0x14000ba10  jb      short loc_14000B9E7
0x14000ba12  movzx   edx, bx
0x14000ba15  mov     ecx, 100h
0x14000ba1a  mov     r8d, 46736642h
0x14000ba20  call    cs:__imp_ExAllocatePool2
0x14000ba27  nop     dword ptr [rax+rax+00h]
0x14000ba2c  mov     [rbp+47h+var_80], rax
0x14000ba30  test    rax, rax
0x14000ba33  jnz     short loc_14000BA43
0x14000ba35  mov     eax, cs:dword_140019000
0x14000ba3b  cmp     eax, 3
0x14000ba3e  jmp     loc_14000B986
0x14000ba43  lea     rdx, [r15+18h]; SourceString
0x14000ba47  mov     [rbp+47h+DestinationString.Buffer], rax
0x14000ba4b  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14000ba4f  mov     [rbp+47h+DestinationString.MaximumLength], bx
0x14000ba53  call    cs:__imp_RtlCopyUnicodeString
0x14000ba5a  nop     dword ptr [rax+rax+00h]
0x14000ba5f  lea     rdx, ReparsePrefixString; Source
0x14000ba66  lea     rcx, [rbp+47h+DestinationString]; Destination
0x14000ba6a  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000ba71  nop     dword ptr [rax+rax+00h]
0x14000ba76  mov     ebx, eax
0x14000ba78  test    eax, eax
0x14000ba7a  jns     short loc_14000BACA
0x14000ba7c  mov     eax, cs:dword_140019000
0x14000ba82  cmp     eax, 3
0x14000ba85  jbe     short loc_14000BAAF
0x14000ba87  mov     dword ptr [rbp+47h+var_B0], ebx
0x14000ba8a  lea     rax, [rbp+47h+var_B0]
0x14000ba8e  mov     [rbp+47h+var_50], 4
0x14000ba96  mov     [rbp+47h+var_58], rax
0x14000ba9a  lea     rdx, byte_140016D91; int
0x14000baa1  lea     rax, [rbp+47h+var_78]
0x14000baa5  mov     qword ptr [rsp+0F0h+PoolTag], rax; PEVENT_DATA_DESCRIPTOR
0x14000baaa  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000baaf  mov     r15, [rbp+47h+P]
0x14000bab3  mov     rcx, [rbp+47h+var_80]; P
0x14000bab7  xor     edx, edx; Tag
0x14000bab9  call    cs:__imp_ExFreePoolWithTag
0x14000bac0  nop     dword ptr [rax+rax+00h]
0x14000bac5  jmp     loc_14000B8DD
0x14000baca  mov     rdx, r13; Source
0x14000bacd  lea     rcx, [rbp+47h+DestinationString]; Destination
0x14000bad1  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000bad8  nop     dword ptr [rax+rax+00h]
0x14000badd  mov     ebx, eax
0x14000badf  test    eax, eax
0x14000bae1  js      short loc_14000BA7C
0x14000bae3  mov     r13d, 100h
0x14000bae9  mov     edx, 30h ; '0'
0x14000baee  mov     ecx, r13d
0x14000baf1  mov     r8d, 52736642h
0x14000baf7  call    cs:__imp_ExAllocatePool2
0x14000bafe  nop     dword ptr [rax+rax+00h]
0x14000bb03  mov     rdi, rax
0x14000bb06  test    rax, rax
0x14000bb09  jnz     short loc_14000BB25
0x14000bb0b  mov     eax, cs:dword_140019000
0x14000bb11  mov     edx, 0C0000017h
0x14000bb16  mov     ebx, edx
0x14000bb18  cmp     eax, 3
0x14000bb1b  jbe     short loc_14000BAAF
0x14000bb1d  mov     dword ptr [rbp+47h+var_B0], edx
0x14000bb20  jmp     loc_14000BA8A
0x14000bb25  mov     rbx, [rbp+47h+var_B0]
0x14000bb29  mov     r8d, 46736642h
0x14000bb2f  mov     r15, [rbp+47h+P]
0x14000bb33  mov     rcx, r13
0x14000bb36  mov     [rax], r15
0x14000bb39  mov     [rax+8], rsi
0x14000bb3d  movzx   edx, word ptr [rbx+8]
0x14000bb41  call    cs:__imp_ExAllocatePool2
0x14000bb48  nop     dword ptr [rax+rax+00h]
0x14000bb4d  mov     [rdi+18h], rax
0x14000bb51  test    rax, rax
0x14000bb54  jnz     short loc_14000BB99
0x14000bb56  mov     eax, cs:dword_140019000
0x14000bb5c  mov     edx, 0C0000017h
0x14000bb61  mov     ebx, edx
0x14000bb63  cmp     eax, 3
0x14000bb66  jbe     loc_14000BAB3
0x14000bb6c  mov     dword ptr [rbp+47h+var_B0], edx
0x14000bb6f  lea     rax, [rbp+47h+var_B0]
0x14000bb73  mov     [rbp+47h+var_50], 4
0x14000bb7b  mov     [rbp+47h+var_58], rax
0x14000bb7f  lea     rdx, byte_140016D91; int
0x14000bb86  lea     rax, [rbp+47h+var_78]
0x14000bb8a  mov     qword ptr [rsp+0F0h+PoolTag], rax; PEVENT_DATA_DESCRIPTOR
0x14000bb8f  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000bb94  jmp     loc_14000BAB3
0x14000bb99  movzx   eax, word ptr [rbx+8]
0x14000bb9d  lea     rcx, [rdi+10h]; DestinationString
0x14000bba1  lea     rdx, [rbx+8]; SourceString
0x14000bba5  mov     [rdi+12h], ax
0x14000bba9  call    cs:__imp_RtlCopyUnicodeString
0x14000bbb0  nop     dword ptr [rax+rax+00h]
0x14000bbb5  movzx   edx, [rbp+47h+DestinationString.Length]
0x14000bbb9  mov     r8d, 46736642h
0x14000bbbf  mov     rcx, r13
0x14000bbc2  call    cs:__imp_ExAllocatePool2
0x14000bbc9  nop     dword ptr [rax+rax+00h]
0x14000bbce  mov     [rdi+28h], rax
0x14000bbd2  test    rax, rax
0x14000bbd5  jz      loc_14000BB56
0x14000bbdb  movzx   eax, [rbp+47h+DestinationString.Length]
0x14000bbdf  lea     rcx, [rdi+20h]; DestinationString
0x14000bbe3  lea     rdx, [rbp+47h+DestinationString]; SourceString
0x14000bbe7  mov     [rdi+22h], ax
0x14000bbeb  call    cs:__imp_RtlCopyUnicodeString
0x14000bbf2  nop     dword ptr [rax+rax+00h]
0x14000bbf7  lea     r8, [rbp+47h+EcpList]; EcpList
0x14000bbfb  mov     rdx, r12; CallbackData
0x14000bbfe  mov     rcx, r14; Filter
0x14000bc01  call    cs:__imp_FltGetEcpListFromCallbackData
0x14000bc08  nop     dword ptr [rax+rax+00h]
0x14000bc0d  mov     ebx, eax
0x14000bc0f  test    eax, eax
0x14000bc11  js      short loc_14000BC8E
0x14000bc13  cmp     [rbp+47h+EcpList], 0
0x14000bc18  jnz     short loc_14000BC51
0x14000bc1a  lea     r8, [rbp+47h+EcpList]; EcpList
0x14000bc1e  xor     edx, edx; Flags
0x14000bc20  mov     rcx, r14; Filter
0x14000bc23  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14000bc2a  nop     dword ptr [rax+rax+00h]
0x14000bc2f  mov     ebx, eax
0x14000bc31  test    eax, eax
0x14000bc33  js      short loc_14000BC8E
0x14000bc35  mov     r8, [rbp+47h+EcpList]; EcpList
0x14000bc39  mov     rdx, r12; CallbackData
0x14000bc3c  mov     rcx, r14; Filter
0x14000bc3f  call    cs:__imp_FltSetEcpListIntoCallbackData
0x14000bc46  nop     dword ptr [rax+rax+00h]
0x14000bc4b  mov     ebx, eax
0x14000bc4d  test    eax, eax
0x14000bc4f  js      short loc_14000BC8E
0x14000bc51  xor     r9d, r9d; Flags
0x14000bc54  lea     rax, [rbp+47h+var_98]
0x14000bc58  mov     [rsp+0F0h+EcpContext], rax; EcpContext
0x14000bc5d  lea     rdx, BfsEcpType; EcpType
0x14000bc64  mov     [rsp+0F0h+PoolTag], 70736642h; PoolTag
0x14000bc6c  mov     rcx, r14; Filter
0x14000bc6f  mov     [rsp+0F0h+CleanupCallback], 0; CleanupCallback
0x14000bc78  lea     r8d, [r9+10h]; SizeOfContext
0x14000bc7c  call    cs:__imp_FltAllocateExtraCreateParameter
0x14000bc83  nop     dword ptr [rax+rax+00h]
0x14000bc88  mov     ebx, eax
0x14000bc8a  test    eax, eax
0x14000bc8c  jns     short loc_14000BCA5
0x14000bc8e  mov     eax, cs:dword_140019000
0x14000bc94  cmp     eax, 3
0x14000bc97  jbe     loc_14000BAB3
0x14000bc9d  mov     dword ptr [rbp+47h+var_B0], ebx
0x14000bca0  jmp     loc_14000BB6F
0x14000bca5  mov     rax, [rbp+47h+var_98]
  ... truncated ...
```
