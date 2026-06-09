# BfsProcessQueryPolicySizeRequest

- ea: `0x14000995c`
- end: `0x140009b96`
- name: `BfsProcessQueryPolicySizeRequest`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003640`

## callees

- `0x140001008`
- `0x140003210`
- `0x140006040`
- `0x1400061a0`
- `0x140007044`
- `0x140008e84`
- `0x14000995c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400099b4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400099b4`
- `ntoskrnl!SeTokenObjectType` at `0x14000997f`
- `ntoskrnl!ObfDereferenceObject` at `0x140009b39`
- `ntoskrnl!ObfDereferenceObject` at `0x140009b39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b67`
- `ntoskrnl!SeQueryInformationToken` at `0x140009a37`
- `ntoskrnl!SeQueryInformationToken` at `0x140009a56`
- `ntoskrnl!SeQueryInformationToken` at `0x140009a37`
- `ntoskrnl!SeQueryInformationToken` at `0x140009a56`

## pseudocode

```c
__int64 __fastcall BfsProcessQueryPolicySizeRequest(void *a1, __int64 a2)
{
  NTSTATUS v3; // eax
  int v4; // r8d
  int v5; // r9d
  NTSTATUS PolicyEntry; // ebx
  int v7; // ecx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int Object; // [rsp+20h] [rbp-29h]
  PVOID *Objecta; // [rsp+20h] [rbp-29h]
  NTSTATUS v14; // [rsp+30h] [rbp-19h] BYREF
  PVOID Token; // [rsp+38h] [rbp-11h] BYREF
  PVOID v16; // [rsp+40h] [rbp-9h] BYREF
  PVOID TokenInformation; // [rsp+48h] [rbp-1h] BYREF
  PVOID P; // [rsp+50h] [rbp+7h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+58h] [rbp+Fh] BYREF
  NTSTATUS *v20; // [rsp+78h] [rbp+2Fh]
  __int64 v21; // [rsp+80h] [rbp+37h]

  P = 0;
  v16 = 0;
  Token = 0;
  TokenInformation = 0;
  v3 = ObReferenceObjectByHandle(a1, 8u, (POBJECT_TYPE)SeTokenObjectType, 1, &Token, 0);
  PolicyEntry = v3;
  if ( v3 < 0 )
  {
    v7 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_19;
    v14 = v3;
    goto LABEL_4;
  }
  if ( BfsIsApplicableToken(Token, 1) )
  {
    PolicyEntry = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
    if ( PolicyEntry >= 0 )
    {
      PolicyEntry = SeQueryInformationToken(Token, TokenAppContainerSid, &P);
      if ( PolicyEntry >= 0 )
      {
        if ( BfsPolicyEntryExists(
               (int)gBfsFilterHandle,
               0,
               (__int64)&gBfsPolicyTable,
               *(void **)TokenInformation,
               *(PSID *)P) )
        {
          Objecta = *(PVOID **)P;
          PolicyEntry = BfsGetPolicyEntry(gBfsFilterHandle, 0, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
          if ( PolicyEntry < 0 || (PolicyEntry = BfsEnumeratePolicy(v16, 0, 0, a2, Objecta, &v16), PolicyEntry < 0) )
          {
            if ( (unsigned int)dword_140019000 > 3 )
            {
              v20 = &v14;
              v14 = PolicyEntry;
              v21 = 4;
              tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v9, v10, (int)Objecta, &v19);
            }
          }
          if ( v16 )
            BfsDereferencePolicyEntryEx(v16);
          goto LABEL_19;
        }
        PolicyEntry = -1073741809;
      }
    }
  }
  else
  {
    PolicyEntry = -1073700352;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v14 = PolicyEntry;
LABEL_4:
    v21 = 4;
    v20 = &v14;
    tlgWriteTransfer_EtwWriteTransfer(v7, (int)&byte_140016D91, v4, v5, Object, &v19);
  }
LABEL_19:
  if ( Token )
    ObfDereferenceObject(Token);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)PolicyEntry;
}

```

## disassembly

```asm
0x14000995c  mov     [rsp-8+arg_10], rbx
0x140009961  push    rbp
0x140009962  push    rsi
0x140009963  push    r14
0x140009965  lea     rbp, [rsp-47h]
0x14000996a  sub     rsp, 90h
0x140009971  mov     rax, cs:__security_cookie
0x140009978  xor     rax, rsp
0x14000997b  mov     [rbp+57h+var_18], rax
0x14000997f  mov     r8, cs:__imp_SeTokenObjectType
0x140009986  lea     rax, [rbp+57h+Token]
0x14000998a  xor     r14d, r14d
0x14000998d  mov     rsi, rdx
0x140009990  mov     [rsp+0A0h+HandleInformation], r14; HandleInformation
0x140009995  mov     r9b, 1; AccessMode
0x140009998  mov     [rbp+57h+P], r14
0x14000999c  mov     r8, [r8]; ObjectType
0x14000999f  lea     edx, [r14+8]; DesiredAccess
0x1400099a3  mov     [rbp+57h+var_60], r14
0x1400099a7  mov     [rbp+57h+Token], r14
0x1400099ab  mov     [rbp+57h+TokenInformation], r14
0x1400099af  mov     [rsp+0A0h+Object], rax; int
0x1400099b4  call    cs:__imp_ObReferenceObjectByHandle
0x1400099bb  nop     dword ptr [rax+rax+00h]
0x1400099c0  mov     ebx, eax
0x1400099c2  test    eax, eax
0x1400099c4  jns     short loc_140009A02
0x1400099c6  mov     ecx, cs:dword_140019000; int
0x1400099cc  cmp     ecx, 3
0x1400099cf  jbe     loc_140009B30
0x1400099d5  mov     [rbp+57h+var_70], eax
0x1400099d8  lea     rax, [rbp+57h+var_70]
0x1400099dc  mov     [rbp+57h+var_20], 4
0x1400099e4  mov     [rbp+57h+var_28], rax
0x1400099e8  lea     rdx, byte_140016D91; int
0x1400099ef  lea     rax, [rbp+57h+var_48]
0x1400099f3  mov     [rsp+0A0h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x1400099f8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400099fd  jmp     loc_140009B30
0x140009a02  mov     rcx, [rbp+57h+Token]; Object
0x140009a06  mov     dl, 1
0x140009a08  call    BfsIsApplicableToken
0x140009a0d  test    al, al
0x140009a0f  jnz     short loc_140009A2A
0x140009a11  mov     ebx, 0C000A200h
0x140009a16  mov     eax, cs:dword_140019000
0x140009a1c  cmp     eax, 3
0x140009a1f  jbe     loc_140009B30
0x140009a25  mov     [rbp+57h+var_70], ebx
0x140009a28  jmp     short loc_1400099D8
0x140009a2a  mov     rcx, [rbp+57h+Token]; Token
0x140009a2e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140009a32  mov     edx, 1; TokenInformationClass
0x140009a37  call    cs:__imp_SeQueryInformationToken
0x140009a3e  nop     dword ptr [rax+rax+00h]
0x140009a43  mov     ebx, eax
0x140009a45  test    eax, eax
0x140009a47  js      short loc_140009A16
0x140009a49  mov     rcx, [rbp+57h+Token]; Token
0x140009a4d  lea     r8, [rbp+57h+P]; TokenInformation
0x140009a51  mov     edx, 1Fh; TokenInformationClass
0x140009a56  call    cs:__imp_SeQueryInformationToken
0x140009a5d  nop     dword ptr [rax+rax+00h]
0x140009a62  mov     ebx, eax
0x140009a64  test    eax, eax
0x140009a66  js      short loc_140009A16
0x140009a68  mov     rax, [rbp+57h+P]
0x140009a6c  lea     r8, gBfsPolicyTable
0x140009a73  mov     r9, [rbp+57h+TokenInformation]
0x140009a77  xor     edx, edx
0x140009a79  mov     rcx, [rax]
0x140009a7c  mov     r9, [r9]
0x140009a7f  mov     [rsp+0A0h+Object], rcx
0x140009a84  mov     rcx, cs:gBfsFilterHandle
0x140009a8b  call    BfsPolicyEntryExists
0x140009a90  test    al, al
0x140009a92  jnz     short loc_140009A9E
0x140009a94  mov     ebx, 0C000000Fh
0x140009a99  jmp     loc_140009A16
0x140009a9e  mov     r9, [rbp+57h+TokenInformation]
0x140009aa2  lea     rax, [rbp+57h+var_60]
0x140009aa6  mov     [rsp+0A0h+HandleInformation], rax
0x140009aab  lea     r8, gBfsPolicyTable
0x140009ab2  mov     rax, [rbp+57h+P]
0x140009ab6  xor     edx, edx
0x140009ab8  mov     r9, [r9]
0x140009abb  mov     rcx, [rax]
0x140009abe  mov     [rsp+0A0h+Object], rcx; int
0x140009ac3  mov     rcx, cs:gBfsFilterHandle
0x140009aca  call    BfsGetPolicyEntry
0x140009acf  mov     ebx, eax
0x140009ad1  test    eax, eax
0x140009ad3  js      short loc_140009AEC
0x140009ad5  mov     rcx, [rbp+57h+var_60]
0x140009ad9  mov     r9, rsi
0x140009adc  xor     r8d, r8d
0x140009adf  xor     edx, edx
0x140009ae1  call    BfsEnumeratePolicy
0x140009ae6  mov     ebx, eax
0x140009ae8  test    eax, eax
0x140009aea  jns     short loc_140009B1F
0x140009aec  mov     eax, cs:dword_140019000
0x140009af2  cmp     eax, 3
0x140009af5  jbe     short loc_140009B1F
0x140009af7  lea     rax, [rbp+57h+var_70]
0x140009afb  mov     [rbp+57h+var_28], rax
0x140009aff  lea     rax, [rbp+57h+var_48]
0x140009b03  mov     [rsp+0A0h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x140009b08  lea     rdx, byte_140016D91; int
0x140009b0f  mov     [rbp+57h+var_70], ebx
0x140009b12  mov     [rbp+57h+var_20], 4
0x140009b1a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009b1f  cmp     [rbp+57h+var_60], r14
0x140009b23  jz      short loc_140009B30
0x140009b25  mov     rcx, [rbp+57h+var_60]; P
0x140009b29  xor     edx, edx
0x140009b2b  call    BfsDereferencePolicyEntryEx
0x140009b30  mov     rcx, [rbp+57h+Token]; Object
0x140009b34  test    rcx, rcx
0x140009b37  jz      short loc_140009B45
0x140009b39  call    cs:__imp_ObfDereferenceObject
0x140009b40  nop     dword ptr [rax+rax+00h]
0x140009b45  mov     rcx, [rbp+57h+TokenInformation]; P
0x140009b49  test    rcx, rcx
0x140009b4c  jz      short loc_140009B5C
0x140009b4e  xor     edx, edx; Tag
0x140009b50  call    cs:__imp_ExFreePoolWithTag
0x140009b57  nop     dword ptr [rax+rax+00h]
0x140009b5c  mov     rcx, [rbp+57h+P]; P
0x140009b60  test    rcx, rcx
0x140009b63  jz      short loc_140009B73
0x140009b65  xor     edx, edx; Tag
0x140009b67  call    cs:__imp_ExFreePoolWithTag
0x140009b6e  nop     dword ptr [rax+rax+00h]
0x140009b73  mov     eax, ebx
0x140009b75  mov     rcx, [rbp+57h+var_18]
0x140009b79  xor     rcx, rsp; StackCookie
0x140009b7c  call    __security_check_cookie
0x140009b81  mov     rbx, [rsp+0A0h+arg_10]
0x140009b89  add     rsp, 90h
0x140009b90  pop     r14
0x140009b92  pop     rsi
0x140009b93  pop     rbp
0x140009b94  retn
```
