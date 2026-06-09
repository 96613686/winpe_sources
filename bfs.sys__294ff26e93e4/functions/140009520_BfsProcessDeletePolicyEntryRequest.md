# BfsProcessDeletePolicyEntryRequest

- ea: `0x140009520`
- end: `0x1400096ba`
- name: `BfsProcessDeletePolicyEntryRequest`
- size: `410`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003770`

## callees

- `0x140001008`
- `0x140003340`
- `0x140009520`
- `0x14000a64c`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000957b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000957b`
- `ntoskrnl!SeTokenObjectType` at `0x140009541`
- `ntoskrnl!ObfDereferenceObject` at `0x140009660`
- `ntoskrnl!ObfDereferenceObject` at `0x140009660`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009677`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000968e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009677`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000968e`
- `ntoskrnl!SeQueryInformationToken` at `0x1400095c7`
- `ntoskrnl!SeQueryInformationToken` at `0x1400095e6`
- `ntoskrnl!SeQueryInformationToken` at `0x1400095c7`
- `ntoskrnl!SeQueryInformationToken` at `0x1400095e6`

## pseudocode

```c
__int64 __fastcall BfsProcessDeletePolicyEntryRequest(void *a1)
{
  NTSTATUS v1; // eax
  int v2; // r8d
  int v3; // r9d
  int v4; // ebx
  int v5; // ecx
  __int64 v6; // rdx
  int v8; // [rsp+28h] [rbp-19h]
  NTSTATUS v9; // [rsp+38h] [rbp-9h] BYREF
  PACCESS_TOKEN Token; // [rsp+40h] [rbp-1h] BYREF
  PVOID TokenInformation; // [rsp+48h] [rbp+7h] BYREF
  PVOID P; // [rsp+50h] [rbp+Fh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+58h] [rbp+17h] BYREF
  NTSTATUS *v14; // [rsp+78h] [rbp+37h]
  __int64 v15; // [rsp+80h] [rbp+3Fh]

  P = 0;
  Token = 0;
  TokenInformation = 0;
  v1 = ObReferenceObjectByHandle(a1, 8u, (POBJECT_TYPE)SeTokenObjectType, 1, &Token, 0);
  v4 = v1;
  if ( v1 < 0 )
  {
    v5 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_12;
    v9 = v1;
LABEL_11:
    v15 = 4;
    v14 = &v9;
    tlgWriteTransfer_EtwWriteTransfer(v5, (int)&byte_140016D91, v2, v3, v8, &v13);
    goto LABEL_12;
  }
  if ( !(unsigned __int8)BfsIsApplicableToken(Token) )
  {
    v4 = -1073700352;
LABEL_9:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_12;
    v9 = v4;
    goto LABEL_11;
  }
  v4 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  if ( v4 < 0 )
    goto LABEL_9;
  v4 = SeQueryInformationToken(Token, TokenAppContainerSid, &P);
  if ( v4 < 0 )
    goto LABEL_9;
  v4 = BfsRemovePolicyEntry(
         (int)gBfsFilterHandle,
         v6,
         (__int64)&gBfsPolicyTable,
         *(void **)TokenInformation,
         *(PSID *)P);
  if ( v4 < 0 )
    goto LABEL_9;
LABEL_12:
  if ( Token )
    ObfDereferenceObject(Token);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140009520  mov     r11, rsp
0x140009523  mov     [r11+10h], rbx
0x140009527  push    rbp
0x140009528  lea     rbp, [r11-5Fh]
0x14000952c  sub     rsp, 90h
0x140009533  mov     rax, cs:__security_cookie
0x14000953a  xor     rax, rsp
0x14000953d  mov     [rbp+57h+var_10], rax
0x140009541  mov     r8, cs:__imp_SeTokenObjectType
0x140009548  lea     rax, [rbp+57h+Token]
0x14000954c  mov     qword ptr [r11-70h], 0
0x140009554  mov     r9b, 1; AccessMode
0x140009557  mov     edx, 8; DesiredAccess
0x14000955c  mov     [rbp+57h+P], 0
0x140009564  mov     [rbp+57h+Token], 0
0x14000956c  mov     r8, [r8]; ObjectType
0x14000956f  mov     [rbp+57h+TokenInformation], 0
0x140009577  mov     [r11-78h], rax
0x14000957b  call    cs:__imp_ObReferenceObjectByHandle
0x140009582  nop     dword ptr [rax+rax+00h]
0x140009587  mov     ebx, eax
0x140009589  test    eax, eax
0x14000958b  jns     short loc_1400095A4
0x14000958d  mov     ecx, cs:dword_140019000
0x140009593  cmp     ecx, 3
0x140009596  jbe     loc_140009657
0x14000959c  mov     [rbp+57h+var_60], eax
0x14000959f  jmp     loc_140009632
0x1400095a4  mov     rcx, [rbp+57h+Token]; Object
0x1400095a8  mov     dl, 1
0x1400095aa  call    BfsIsApplicableToken
0x1400095af  test    al, al
0x1400095b1  jnz     short loc_1400095BA
0x1400095b3  mov     ebx, 0C000A200h
0x1400095b8  jmp     short loc_140009624
0x1400095ba  mov     rcx, [rbp+57h+Token]; Token
0x1400095be  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1400095c2  mov     edx, 1; TokenInformationClass
0x1400095c7  call    cs:__imp_SeQueryInformationToken
0x1400095ce  nop     dword ptr [rax+rax+00h]
0x1400095d3  mov     ebx, eax
0x1400095d5  test    eax, eax
0x1400095d7  js      short loc_140009624
0x1400095d9  mov     rcx, [rbp+57h+Token]; Token
0x1400095dd  lea     r8, [rbp+57h+P]; TokenInformation
0x1400095e1  mov     edx, 1Fh; TokenInformationClass
0x1400095e6  call    cs:__imp_SeQueryInformationToken
0x1400095ed  nop     dword ptr [rax+rax+00h]
0x1400095f2  mov     ebx, eax
0x1400095f4  test    eax, eax
0x1400095f6  js      short loc_140009624
0x1400095f8  mov     rax, [rbp+57h+P]
0x1400095fc  lea     r8, gBfsPolicyTable
0x140009603  mov     r9, [rbp+57h+TokenInformation]
0x140009607  mov     rcx, [rax]
0x14000960a  mov     r9, [r9]
0x14000960d  mov     qword ptr [rsp+90h+var_70], rcx; int
0x140009612  mov     rcx, cs:gBfsFilterHandle
0x140009619  call    BfsRemovePolicyEntry
0x14000961e  mov     ebx, eax
0x140009620  test    eax, eax
0x140009622  jns     short loc_140009657
0x140009624  mov     eax, cs:dword_140019000
0x14000962a  cmp     eax, 3
0x14000962d  jbe     short loc_140009657
0x14000962f  mov     [rbp+57h+var_60], ebx
0x140009632  lea     rax, [rbp+57h+var_60]
0x140009636  mov     [rbp+57h+var_18], 4
0x14000963e  mov     [rbp+57h+var_20], rax
0x140009642  lea     rdx, byte_140016D91; int
0x140009649  lea     rax, [rbp+57h+var_40]
0x14000964d  mov     qword ptr [rsp+90h+var_70+8], rax; PEVENT_DATA_DESCRIPTOR
0x140009652  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009657  mov     rcx, [rbp+57h+Token]; Object
0x14000965b  test    rcx, rcx
0x14000965e  jz      short loc_14000966C
0x140009660  call    cs:__imp_ObfDereferenceObject
0x140009667  nop     dword ptr [rax+rax+00h]
0x14000966c  mov     rcx, [rbp+57h+TokenInformation]; P
0x140009670  test    rcx, rcx
0x140009673  jz      short loc_140009683
0x140009675  xor     edx, edx; Tag
0x140009677  call    cs:__imp_ExFreePoolWithTag
0x14000967e  nop     dword ptr [rax+rax+00h]
0x140009683  mov     rcx, [rbp+57h+P]; P
0x140009687  test    rcx, rcx
0x14000968a  jz      short loc_14000969A
0x14000968c  xor     edx, edx; Tag
0x14000968e  call    cs:__imp_ExFreePoolWithTag
0x140009695  nop     dword ptr [rax+rax+00h]
0x14000969a  mov     eax, ebx
0x14000969c  mov     rcx, [rbp+57h+var_10]
0x1400096a0  xor     rcx, rsp; StackCookie
0x1400096a3  call    __security_check_cookie
0x1400096a8  mov     rbx, [rsp+90h+arg_8]
0x1400096b0  add     rsp, 90h
0x1400096b7  pop     rbp
0x1400096b8  retn
```
