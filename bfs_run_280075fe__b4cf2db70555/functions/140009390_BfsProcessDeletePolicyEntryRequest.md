# BfsProcessDeletePolicyEntryRequest

- ea: `0x140009390`
- end: `0x14000952a`
- name: `BfsProcessDeletePolicyEntryRequest`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003640`

## callees

- `0x140001008`
- `0x140003210`
- `0x140009390`
- `0x14000a4bc`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400093eb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400093eb`
- `ntoskrnl!SeTokenObjectType` at `0x1400093b1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400094d0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400094d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094fe`
- `ntoskrnl!SeQueryInformationToken` at `0x140009437`
- `ntoskrnl!SeQueryInformationToken` at `0x140009456`
- `ntoskrnl!SeQueryInformationToken` at `0x140009437`
- `ntoskrnl!SeQueryInformationToken` at `0x140009456`

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
  if ( !BfsIsApplicableToken(Token, 1) )
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
0x140009390  mov     r11, rsp
0x140009393  mov     [r11+10h], rbx
0x140009397  push    rbp
0x140009398  lea     rbp, [r11-5Fh]
0x14000939c  sub     rsp, 90h
0x1400093a3  mov     rax, cs:__security_cookie
0x1400093aa  xor     rax, rsp
0x1400093ad  mov     [rbp+57h+var_10], rax
0x1400093b1  mov     r8, cs:__imp_SeTokenObjectType
0x1400093b8  lea     rax, [rbp+57h+Token]
0x1400093bc  mov     qword ptr [r11-70h], 0
0x1400093c4  mov     r9b, 1; AccessMode
0x1400093c7  mov     edx, 8; DesiredAccess
0x1400093cc  mov     [rbp+57h+P], 0
0x1400093d4  mov     [rbp+57h+Token], 0
0x1400093dc  mov     r8, [r8]; ObjectType
0x1400093df  mov     [rbp+57h+TokenInformation], 0
0x1400093e7  mov     [r11-78h], rax
0x1400093eb  call    cs:__imp_ObReferenceObjectByHandle
0x1400093f2  nop     dword ptr [rax+rax+00h]
0x1400093f7  mov     ebx, eax
0x1400093f9  test    eax, eax
0x1400093fb  jns     short loc_140009414
0x1400093fd  mov     ecx, cs:dword_140019000
0x140009403  cmp     ecx, 3
0x140009406  jbe     loc_1400094C7
0x14000940c  mov     [rbp+57h+var_60], eax
0x14000940f  jmp     loc_1400094A2
0x140009414  mov     rcx, [rbp+57h+Token]; Object
0x140009418  mov     dl, 1
0x14000941a  call    BfsIsApplicableToken
0x14000941f  test    al, al
0x140009421  jnz     short loc_14000942A
0x140009423  mov     ebx, 0C000A200h
0x140009428  jmp     short loc_140009494
0x14000942a  mov     rcx, [rbp+57h+Token]; Token
0x14000942e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140009432  mov     edx, 1; TokenInformationClass
0x140009437  call    cs:__imp_SeQueryInformationToken
0x14000943e  nop     dword ptr [rax+rax+00h]
0x140009443  mov     ebx, eax
0x140009445  test    eax, eax
0x140009447  js      short loc_140009494
0x140009449  mov     rcx, [rbp+57h+Token]; Token
0x14000944d  lea     r8, [rbp+57h+P]; TokenInformation
0x140009451  mov     edx, 1Fh; TokenInformationClass
0x140009456  call    cs:__imp_SeQueryInformationToken
0x14000945d  nop     dword ptr [rax+rax+00h]
0x140009462  mov     ebx, eax
0x140009464  test    eax, eax
0x140009466  js      short loc_140009494
0x140009468  mov     rax, [rbp+57h+P]
0x14000946c  lea     r8, gBfsPolicyTable
0x140009473  mov     r9, [rbp+57h+TokenInformation]
0x140009477  mov     rcx, [rax]
0x14000947a  mov     r9, [r9]
0x14000947d  mov     qword ptr [rsp+90h+var_70], rcx; int
0x140009482  mov     rcx, cs:gBfsFilterHandle
0x140009489  call    BfsRemovePolicyEntry
0x14000948e  mov     ebx, eax
0x140009490  test    eax, eax
0x140009492  jns     short loc_1400094C7
0x140009494  mov     eax, cs:dword_140019000
0x14000949a  cmp     eax, 3
0x14000949d  jbe     short loc_1400094C7
0x14000949f  mov     [rbp+57h+var_60], ebx
0x1400094a2  lea     rax, [rbp+57h+var_60]
0x1400094a6  mov     [rbp+57h+var_18], 4
0x1400094ae  mov     [rbp+57h+var_20], rax
0x1400094b2  lea     rdx, byte_140016D91; int
0x1400094b9  lea     rax, [rbp+57h+var_40]
0x1400094bd  mov     qword ptr [rsp+90h+var_70+8], rax; PEVENT_DATA_DESCRIPTOR
0x1400094c2  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400094c7  mov     rcx, [rbp+57h+Token]; Object
0x1400094cb  test    rcx, rcx
0x1400094ce  jz      short loc_1400094DC
0x1400094d0  call    cs:__imp_ObfDereferenceObject
0x1400094d7  nop     dword ptr [rax+rax+00h]
0x1400094dc  mov     rcx, [rbp+57h+TokenInformation]; P
0x1400094e0  test    rcx, rcx
0x1400094e3  jz      short loc_1400094F3
0x1400094e5  xor     edx, edx; Tag
0x1400094e7  call    cs:__imp_ExFreePoolWithTag
0x1400094ee  nop     dword ptr [rax+rax+00h]
0x1400094f3  mov     rcx, [rbp+57h+P]; P
0x1400094f7  test    rcx, rcx
0x1400094fa  jz      short loc_14000950A
0x1400094fc  xor     edx, edx; Tag
0x1400094fe  call    cs:__imp_ExFreePoolWithTag
0x140009505  nop     dword ptr [rax+rax+00h]
0x14000950a  mov     eax, ebx
0x14000950c  mov     rcx, [rbp+57h+var_10]
0x140009510  xor     rcx, rsp; StackCookie
0x140009513  call    __security_check_cookie
0x140009518  mov     rbx, [rsp+90h+arg_8]
0x140009520  add     rsp, 90h
0x140009527  pop     rbp
0x140009528  retn
```
