# BfsProcessQueryPolicySizeRequest

- ea: `0x140009aec`
- end: `0x140009d26`
- name: `BfsProcessQueryPolicySizeRequest`
- size: `570`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003770`

## callees

- `0x140001008`
- `0x140003340`
- `0x1400061d0`
- `0x140006330`
- `0x1400071d4`
- `0x140009014`
- `0x140009aec`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009b44`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009b44`
- `ntoskrnl!SeTokenObjectType` at `0x140009b0f`
- `ntoskrnl!ObfDereferenceObject` at `0x140009cc9`
- `ntoskrnl!ObfDereferenceObject` at `0x140009cc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009cf7`
- `ntoskrnl!SeQueryInformationToken` at `0x140009bc7`
- `ntoskrnl!SeQueryInformationToken` at `0x140009be6`
- `ntoskrnl!SeQueryInformationToken` at `0x140009bc7`
- `ntoskrnl!SeQueryInformationToken` at `0x140009be6`

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
  PVOID *Object; // [rsp+20h] [rbp-29h]
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
  if ( (unsigned __int8)BfsIsApplicableToken(Token) )
  {
    PolicyEntry = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
    if ( PolicyEntry >= 0 )
    {
      PolicyEntry = SeQueryInformationToken(Token, TokenAppContainerSid, &P);
      if ( PolicyEntry >= 0 )
      {
        Object = *(PVOID **)P;
        if ( (unsigned __int8)BfsPolicyEntryExists(gBfsFilterHandle, 0, &gBfsPolicyTable, *(_QWORD *)TokenInformation) )
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
    tlgWriteTransfer_EtwWriteTransfer(v7, (int)&byte_140016D91, v4, v5, (int)Object, &v19);
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
0x140009aec  mov     [rsp-8+arg_10], rbx
0x140009af1  push    rbp
0x140009af2  push    rsi
0x140009af3  push    r14
0x140009af5  lea     rbp, [rsp-47h]
0x140009afa  sub     rsp, 90h
0x140009b01  mov     rax, cs:__security_cookie
0x140009b08  xor     rax, rsp
0x140009b0b  mov     [rbp+57h+var_18], rax
0x140009b0f  mov     r8, cs:__imp_SeTokenObjectType
0x140009b16  lea     rax, [rbp+57h+Token]
0x140009b1a  xor     r14d, r14d
0x140009b1d  mov     rsi, rdx
0x140009b20  mov     [rsp+0A0h+HandleInformation], r14; HandleInformation
0x140009b25  mov     r9b, 1; AccessMode
0x140009b28  mov     [rbp+57h+P], r14
0x140009b2c  mov     r8, [r8]; ObjectType
0x140009b2f  lea     edx, [r14+8]; DesiredAccess
0x140009b33  mov     [rbp+57h+var_60], r14
0x140009b37  mov     [rbp+57h+Token], r14
0x140009b3b  mov     [rbp+57h+TokenInformation], r14
0x140009b3f  mov     [rsp+0A0h+Object], rax; int
0x140009b44  call    cs:__imp_ObReferenceObjectByHandle
0x140009b4b  nop     dword ptr [rax+rax+00h]
0x140009b50  mov     ebx, eax
0x140009b52  test    eax, eax
0x140009b54  jns     short loc_140009B92
0x140009b56  mov     ecx, cs:dword_140019000; int
0x140009b5c  cmp     ecx, 3
0x140009b5f  jbe     loc_140009CC0
0x140009b65  mov     [rbp+57h+var_70], eax
0x140009b68  lea     rax, [rbp+57h+var_70]
0x140009b6c  mov     [rbp+57h+var_20], 4
0x140009b74  mov     [rbp+57h+var_28], rax
0x140009b78  lea     rdx, byte_140016D91; int
0x140009b7f  lea     rax, [rbp+57h+var_48]
0x140009b83  mov     [rsp+0A0h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x140009b88  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009b8d  jmp     loc_140009CC0
0x140009b92  mov     rcx, [rbp+57h+Token]; Object
0x140009b96  mov     dl, 1
0x140009b98  call    BfsIsApplicableToken
0x140009b9d  test    al, al
0x140009b9f  jnz     short loc_140009BBA
0x140009ba1  mov     ebx, 0C000A200h
0x140009ba6  mov     eax, cs:dword_140019000
0x140009bac  cmp     eax, 3
0x140009baf  jbe     loc_140009CC0
0x140009bb5  mov     [rbp+57h+var_70], ebx
0x140009bb8  jmp     short loc_140009B68
0x140009bba  mov     rcx, [rbp+57h+Token]; Token
0x140009bbe  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140009bc2  mov     edx, 1; TokenInformationClass
0x140009bc7  call    cs:__imp_SeQueryInformationToken
0x140009bce  nop     dword ptr [rax+rax+00h]
0x140009bd3  mov     ebx, eax
0x140009bd5  test    eax, eax
0x140009bd7  js      short loc_140009BA6
0x140009bd9  mov     rcx, [rbp+57h+Token]; Token
0x140009bdd  lea     r8, [rbp+57h+P]; TokenInformation
0x140009be1  mov     edx, 1Fh; TokenInformationClass
0x140009be6  call    cs:__imp_SeQueryInformationToken
0x140009bed  nop     dword ptr [rax+rax+00h]
0x140009bf2  mov     ebx, eax
0x140009bf4  test    eax, eax
0x140009bf6  js      short loc_140009BA6
0x140009bf8  mov     rax, [rbp+57h+P]
0x140009bfc  lea     r8, gBfsPolicyTable
0x140009c03  mov     r9, [rbp+57h+TokenInformation]
0x140009c07  xor     edx, edx
0x140009c09  mov     rcx, [rax]
0x140009c0c  mov     r9, [r9]
0x140009c0f  mov     [rsp+0A0h+Object], rcx
0x140009c14  mov     rcx, cs:gBfsFilterHandle
0x140009c1b  call    BfsPolicyEntryExists
0x140009c20  test    al, al
0x140009c22  jnz     short loc_140009C2E
0x140009c24  mov     ebx, 0C000000Fh
0x140009c29  jmp     loc_140009BA6
0x140009c2e  mov     r9, [rbp+57h+TokenInformation]
0x140009c32  lea     rax, [rbp+57h+var_60]
0x140009c36  mov     [rsp+0A0h+HandleInformation], rax
0x140009c3b  lea     r8, gBfsPolicyTable
0x140009c42  mov     rax, [rbp+57h+P]
0x140009c46  xor     edx, edx
0x140009c48  mov     r9, [r9]
0x140009c4b  mov     rcx, [rax]
0x140009c4e  mov     [rsp+0A0h+Object], rcx; int
0x140009c53  mov     rcx, cs:gBfsFilterHandle
0x140009c5a  call    BfsGetPolicyEntry
0x140009c5f  mov     ebx, eax
0x140009c61  test    eax, eax
0x140009c63  js      short loc_140009C7C
0x140009c65  mov     rcx, [rbp+57h+var_60]
0x140009c69  mov     r9, rsi
0x140009c6c  xor     r8d, r8d
0x140009c6f  xor     edx, edx
0x140009c71  call    BfsEnumeratePolicy
0x140009c76  mov     ebx, eax
0x140009c78  test    eax, eax
0x140009c7a  jns     short loc_140009CAF
0x140009c7c  mov     eax, cs:dword_140019000
0x140009c82  cmp     eax, 3
0x140009c85  jbe     short loc_140009CAF
0x140009c87  lea     rax, [rbp+57h+var_70]
0x140009c8b  mov     [rbp+57h+var_28], rax
0x140009c8f  lea     rax, [rbp+57h+var_48]
0x140009c93  mov     [rsp+0A0h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x140009c98  lea     rdx, byte_140016D91; int
0x140009c9f  mov     [rbp+57h+var_70], ebx
0x140009ca2  mov     [rbp+57h+var_20], 4
0x140009caa  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009caf  cmp     [rbp+57h+var_60], r14
0x140009cb3  jz      short loc_140009CC0
0x140009cb5  mov     rcx, [rbp+57h+var_60]; P
0x140009cb9  xor     edx, edx
0x140009cbb  call    BfsDereferencePolicyEntryEx
0x140009cc0  mov     rcx, [rbp+57h+Token]; Object
0x140009cc4  test    rcx, rcx
0x140009cc7  jz      short loc_140009CD5
0x140009cc9  call    cs:__imp_ObfDereferenceObject
0x140009cd0  nop     dword ptr [rax+rax+00h]
0x140009cd5  mov     rcx, [rbp+57h+TokenInformation]; P
0x140009cd9  test    rcx, rcx
0x140009cdc  jz      short loc_140009CEC
0x140009cde  xor     edx, edx; Tag
0x140009ce0  call    cs:__imp_ExFreePoolWithTag
0x140009ce7  nop     dword ptr [rax+rax+00h]
0x140009cec  mov     rcx, [rbp+57h+P]; P
0x140009cf0  test    rcx, rcx
0x140009cf3  jz      short loc_140009D03
0x140009cf5  xor     edx, edx; Tag
0x140009cf7  call    cs:__imp_ExFreePoolWithTag
0x140009cfe  nop     dword ptr [rax+rax+00h]
0x140009d03  mov     eax, ebx
0x140009d05  mov     rcx, [rbp+57h+var_18]
0x140009d09  xor     rcx, rsp; StackCookie
0x140009d0c  call    __security_check_cookie
0x140009d11  mov     rbx, [rsp+0A0h+arg_10]
0x140009d19  add     rsp, 90h
0x140009d20  pop     r14
0x140009d22  pop     rsi
0x140009d23  pop     rbp
0x140009d24  retn
```
