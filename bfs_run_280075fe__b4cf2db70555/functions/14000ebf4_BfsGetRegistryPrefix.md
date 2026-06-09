# BfsGetRegistryPrefix

- ea: `0x14000ebf4`
- end: `0x14000ef69`
- name: `BfsGetRegistryPrefix`
- size: `885`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f174`

## callees

- `0x140001008`
- `0x140006040`
- `0x140006d20`
- `0x140007250`
- `0x140009114`
- `0x14000e848`
- `0x14000ebf4`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000ee2f`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000ee2f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000ef1e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000ef1e`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14000ee5c`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14000ee5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ee77`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ee77`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000eec3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000eec3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eedb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eef3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eedb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eef3`
- `ntoskrnl!SeQueryInformationToken` at `0x14000ec73`
- `ntoskrnl!SeQueryInformationToken` at `0x14000ecd0`
- `ntoskrnl!SeQueryInformationToken` at `0x14000ec73`
- `ntoskrnl!SeQueryInformationToken` at `0x14000ecd0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ef2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ef2a`

## pseudocode

```c
__int64 __fastcall BfsGetRegistryPrefix(PACCESS_TOKEN Token, _OWORD *a2, _OWORD *a3, int *a4)
{
  _WORD *v8; // rdi
  NTSTATUS v9; // eax
  int v10; // r8d
  int v11; // r9d
  NTSTATUS exists; // ebx
  int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int NotPresentPolicyEntryLocked; // eax
  PSID v18; // [rsp+20h] [rbp-E0h]
  NTSTATUS v19; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v20; // [rsp+48h] [rbp-B8h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+88h] [rbp-78h] BYREF
  NTSTATUS *v27; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  WCHAR SourceString[128]; // [rsp+C0h] [rbp-40h] BYREF

  P = 0;
  DestinationString = 0;
  memset(SourceString, 0, sizeof(SourceString));
  v23 = 256;
  v20 = 0;
  TokenInformation = 0;
  v8 = 0;
  UnicodeString = 0;
  v9 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  exists = v9;
  if ( v9 < 0 )
  {
    v13 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_28;
    v19 = v9;
    goto LABEL_4;
  }
  exists = SeQueryInformationToken(Token, TokenAppContainerSid, &P);
  if ( exists < 0 )
  {
LABEL_6:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v19 = exists;
LABEL_4:
      v28 = 4;
      v27 = &v19;
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v10, v11, (int)v18, &v26);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  exists = BfsPolicyEntryExistsLocked(
             (int)gBfsFilterHandle,
             v14,
             (__int64)&gBfsPolicyTable,
             *(void **)TokenInformation,
             *(PSID *)P,
             *a4);
  if ( exists )
  {
    if ( exists != -1073741275 )
    {
      if ( exists < 0 )
        goto LABEL_6;
      goto LABEL_18;
    }
    NotPresentPolicyEntryLocked = BfsGetNotPresentPolicyEntryLocked(
                                    &gBfsPolicyTable,
                                    *(_QWORD *)TokenInformation,
                                    *(_QWORD *)P,
                                    &v20);
  }
  else
  {
    v18 = *(PSID *)P;
    NotPresentPolicyEntryLocked = BfsGetPolicyEntryLocked(
                                    gBfsFilterHandle,
                                    v15,
                                    &gBfsPolicyTable,
                                    *(_QWORD *)TokenInformation);
  }
  exists = NotPresentPolicyEntryLocked;
  if ( NotPresentPolicyEntryLocked < 0 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v19 = NotPresentPolicyEntryLocked;
      v27 = &v19;
      v28 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v10, v11, (int)v18, &v26);
    }
    v8 = v20;
    goto LABEL_28;
  }
  v8 = v20;
LABEL_18:
  if ( v8[56] && v8[64] )
    goto LABEL_27;
  if ( *a4 != 2 )
  {
    exists = -1073741267;
    goto LABEL_22;
  }
  exists = RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)TokenInformation, 1u);
  if ( exists >= 0 )
  {
    LODWORD(v18) = 0;
    exists = RtlQueryPackageIdentity(Token, SourceString, &v23, 0);
    if ( exists >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      exists = BfsCalculateRegistryPrefix(&UnicodeString, &DestinationString, v8 + 56, v8 + 64);
      if ( exists >= 0 )
      {
LABEL_27:
        *a2 = *((_OWORD *)v8 + 7);
        *a3 = *((_OWORD *)v8 + 8);
        goto LABEL_28;
      }
    }
  }
LABEL_22:
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v19 = exists;
    goto LABEL_4;
  }
LABEL_28:
  RtlFreeUnicodeString(&UnicodeString);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v8 )
  {
    if ( *a4 == 1 )
    {
      ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
      KeLeaveCriticalRegion();
      *a4 = 0;
    }
    BfsDereferencePolicyEntryEx(v8);
  }
  return (unsigned int)exists;
}

```

## disassembly

```asm
0x14000ebf4  push    rbp
0x14000ebf6  push    rbx
0x14000ebf7  push    rsi
0x14000ebf8  push    rdi
0x14000ebf9  push    r12
0x14000ebfb  push    r13
0x14000ebfd  push    r14
0x14000ebff  push    r15
0x14000ec01  lea     rbp, [rsp-0D8h]
0x14000ec09  sub     rsp, 1D8h
0x14000ec10  mov     rax, cs:__security_cookie
0x14000ec17  xor     rax, rsp
0x14000ec1a  mov     [rbp+110h+var_50], rax
0x14000ec21  mov     r13, r8
0x14000ec24  mov     r12, rdx
0x14000ec27  mov     r15, rcx
0x14000ec2a  xorps   xmm0, xmm0
0x14000ec2d  mov     ebx, 100h
0x14000ec32  lea     rcx, [rbp+110h+SourceString]; void *
0x14000ec36  xor     esi, esi
0x14000ec38  mov     r8d, ebx; Size
0x14000ec3b  xor     edx, edx; Val
0x14000ec3d  mov     [rsp+210h+P], rsi
0x14000ec42  mov     r14, r9
0x14000ec45  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x14000ec4a  call    memset
0x14000ec4f  xorps   xmm0, xmm0
0x14000ec52  mov     [rsp+210h+var_1B0], rbx
0x14000ec57  lea     r8, [rsp+210h+TokenInformation]; TokenInformation
0x14000ec5c  mov     [rsp+210h+var_1C8], rsi
0x14000ec61  lea     edx, [rsi+1]; TokenInformationClass
0x14000ec64  mov     [rsp+210h+TokenInformation], rsi
0x14000ec69  mov     rcx, r15; Token
0x14000ec6c  mov     edi, esi
0x14000ec6e  movups  xmmword ptr [rsp+210h+UnicodeString.Length], xmm0
0x14000ec73  call    cs:__imp_SeQueryInformationToken
0x14000ec7a  nop     dword ptr [rax+rax+00h]
0x14000ec7f  mov     ebx, eax
0x14000ec81  test    eax, eax
0x14000ec83  jns     short loc_14000ECC3
0x14000ec85  mov     ecx, cs:dword_140019000; int
0x14000ec8b  cmp     ecx, 3
0x14000ec8e  jbe     loc_14000EEBE
0x14000ec94  mov     [rsp+210h+var_1D0], eax
0x14000ec98  lea     rax, [rsp+210h+var_1D0]
0x14000ec9d  mov     [rbp+110h+var_160], 4
0x14000eca5  mov     [rbp+110h+var_168], rax
0x14000eca9  lea     rdx, byte_140016D91; int
0x14000ecb0  lea     rax, [rbp+110h+var_188]
0x14000ecb4  mov     [rsp+210h+var_1E8], rax; PEVENT_DATA_DESCRIPTOR
0x14000ecb9  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ecbe  jmp     loc_14000EEBE
0x14000ecc3  lea     r8, [rsp+210h+P]; TokenInformation
0x14000ecc8  mov     edx, 1Fh; TokenInformationClass
0x14000eccd  mov     rcx, r15; Token
0x14000ecd0  call    cs:__imp_SeQueryInformationToken
0x14000ecd7  nop     dword ptr [rax+rax+00h]
0x14000ecdc  mov     ebx, eax
0x14000ecde  test    eax, eax
0x14000ece0  jns     short loc_14000ECF7
0x14000ece2  mov     eax, cs:dword_140019000
0x14000ece8  cmp     eax, 3
0x14000eceb  jbe     loc_14000EEBE
0x14000ecf1  mov     [rsp+210h+var_1D0], ebx
0x14000ecf5  jmp     short loc_14000EC98
0x14000ecf7  mov     eax, [r14]
0x14000ecfa  lea     r8, gBfsPolicyTable
0x14000ed01  mov     r9, [rsp+210h+TokenInformation]
0x14000ed06  mov     dword ptr [rsp+210h+var_1E8], eax
0x14000ed0a  mov     rax, [rsp+210h+P]
0x14000ed0f  mov     r9, [r9]
0x14000ed12  mov     rcx, [rax]
0x14000ed15  mov     qword ptr [rsp+210h+var_1F0], rcx
0x14000ed1a  mov     rcx, cs:gBfsFilterHandle
0x14000ed21  call    BfsPolicyEntryExistsLocked
0x14000ed26  mov     ebx, eax
0x14000ed28  test    eax, eax
0x14000ed2a  jnz     short loc_14000EDA8
0x14000ed2c  mov     r9, [rsp+210h+TokenInformation]
0x14000ed31  lea     rax, [rsp+210h+var_1C8]
0x14000ed36  mov     [rsp+210h+var_1E0], rax
0x14000ed3b  lea     r8, gBfsPolicyTable
0x14000ed42  mov     rax, [rsp+210h+P]
0x14000ed47  mov     [rsp+210h+var_1E8], r14
0x14000ed4c  mov     r9, [r9]
0x14000ed4f  mov     rcx, [rax]
0x14000ed52  mov     qword ptr [rsp+210h+var_1F0], rcx; int
0x14000ed57  mov     rcx, cs:gBfsFilterHandle
0x14000ed5e  call    BfsGetPolicyEntryLocked
0x14000ed63  mov     ebx, eax
0x14000ed65  test    eax, eax
0x14000ed67  jns     short loc_14000EDD3
0x14000ed69  mov     eax, cs:dword_140019000
0x14000ed6f  cmp     eax, 3
0x14000ed72  jbe     short loc_14000ED9E
0x14000ed74  lea     rax, [rsp+210h+var_1D0]
0x14000ed79  mov     [rsp+210h+var_1D0], ebx
0x14000ed7d  mov     [rbp+110h+var_168], rax
0x14000ed81  lea     rdx, byte_140016D91; int
0x14000ed88  lea     rax, [rbp+110h+var_188]
0x14000ed8c  mov     [rbp+110h+var_160], 4
0x14000ed94  mov     [rsp+210h+var_1E8], rax; PEVENT_DATA_DESCRIPTOR
0x14000ed99  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ed9e  mov     rdi, [rsp+210h+var_1C8]
0x14000eda3  jmp     loc_14000EEBE
0x14000eda8  cmp     ebx, 0C0000225h
0x14000edae  jnz     short loc_14000EDDA
0x14000edb0  mov     r8, [rsp+210h+P]
0x14000edb5  lea     r9, [rsp+210h+var_1C8]
0x14000edba  mov     rdx, [rsp+210h+TokenInformation]
0x14000edbf  lea     rcx, gBfsPolicyTable
0x14000edc6  mov     r8, [r8]
0x14000edc9  mov     rdx, [rdx]
0x14000edcc  call    BfsGetNotPresentPolicyEntryLocked
0x14000edd1  jmp     short loc_14000ED63
0x14000edd3  mov     rdi, [rsp+210h+var_1C8]
0x14000edd8  jmp     short loc_14000EDE2
0x14000edda  test    ebx, ebx
0x14000eddc  js      loc_14000ECE2
0x14000ede2  lea     rsi, [rdi+70h]
0x14000ede6  xor     eax, eax
0x14000ede8  cmp     [rsi], ax
0x14000edeb  jz      short loc_14000EDFA
0x14000eded  cmp     [rdi+80h], ax
0x14000edf4  jnz     loc_14000EEA6
0x14000edfa  cmp     dword ptr [r14], 2
0x14000edfe  jz      short loc_14000EE1F
0x14000ee00  mov     ebx, 0C000022Dh
0x14000ee05  mov     eax, cs:dword_140019000
0x14000ee0b  cmp     eax, 3
0x14000ee0e  jbe     loc_14000EEBC
0x14000ee14  mov     [rsp+210h+var_1D0], ebx
0x14000ee18  xor     esi, esi
0x14000ee1a  jmp     loc_14000EC98
0x14000ee1f  mov     rdx, [rsp+210h+TokenInformation]
0x14000ee24  lea     rcx, [rsp+210h+UnicodeString]; UnicodeString
0x14000ee29  mov     r8b, 1; AllocateDestinationString
0x14000ee2c  mov     rdx, [rdx]; Sid
0x14000ee2f  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000ee36  nop     dword ptr [rax+rax+00h]
0x14000ee3b  mov     ebx, eax
0x14000ee3d  xor     eax, eax
0x14000ee3f  test    ebx, ebx
0x14000ee41  js      short loc_14000EE05
0x14000ee43  mov     [rsp+210h+var_1E8], rax
0x14000ee48  lea     r8, [rsp+210h+var_1B0]
0x14000ee4d  xor     r9d, r9d
0x14000ee50  mov     qword ptr [rsp+210h+var_1F0], rax
0x14000ee55  lea     rdx, [rbp+110h+SourceString]
0x14000ee59  mov     rcx, r15
0x14000ee5c  call    cs:__imp_RtlQueryPackageIdentity
0x14000ee63  nop     dword ptr [rax+rax+00h]
0x14000ee68  mov     ebx, eax
0x14000ee6a  test    eax, eax
0x14000ee6c  js      short loc_14000EE05
0x14000ee6e  lea     rdx, [rbp+110h+SourceString]; SourceString
0x14000ee72  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x14000ee77  call    cs:__imp_RtlInitUnicodeString
0x14000ee7e  nop     dword ptr [rax+rax+00h]
0x14000ee83  lea     r9, [rdi+80h]
0x14000ee8a  mov     r8, rsi
0x14000ee8d  lea     rdx, [rsp+210h+DestinationString]
0x14000ee92  lea     rcx, [rsp+210h+UnicodeString]
0x14000ee97  call    BfsCalculateRegistryPrefix
0x14000ee9c  mov     ebx, eax
0x14000ee9e  test    eax, eax
0x14000eea0  js      loc_14000EE05
0x14000eea6  movups  xmm0, xmmword ptr [rsi]
0x14000eea9  movdqu  xmmword ptr [r12], xmm0
0x14000eeaf  movups  xmm1, xmmword ptr [rdi+80h]
0x14000eeb6  movdqu  xmmword ptr [r13+0], xmm1
0x14000eebc  xor     esi, esi
0x14000eebe  lea     rcx, [rsp+210h+UnicodeString]; UnicodeString
0x14000eec3  call    cs:__imp_RtlFreeUnicodeString
0x14000eeca  nop     dword ptr [rax+rax+00h]
0x14000eecf  mov     rcx, [rsp+210h+TokenInformation]; P
0x14000eed4  test    rcx, rcx
0x14000eed7  jz      short loc_14000EEE7
0x14000eed9  xor     edx, edx; Tag
0x14000eedb  call    cs:__imp_ExFreePoolWithTag
0x14000eee2  nop     dword ptr [rax+rax+00h]
0x14000eee7  mov     rcx, [rsp+210h+P]; P
0x14000eeec  test    rcx, rcx
0x14000eeef  jz      short loc_14000EEFF
0x14000eef1  xor     edx, edx; Tag
0x14000eef3  call    cs:__imp_ExFreePoolWithTag
0x14000eefa  nop     dword ptr [rax+rax+00h]
0x14000eeff  test    rdi, rdi
0x14000ef02  jz      short loc_14000EF43
0x14000ef04  mov     eax, [r14]
0x14000ef07  cmp     eax, 2
0x14000ef0a  jnz     short loc_14000EF10
0x14000ef0c  mov     dl, 1
0x14000ef0e  jmp     short loc_14000EF3B
0x14000ef10  cmp     eax, 1
0x14000ef13  jnz     short loc_14000EF39
0x14000ef15  xor     edx, edx
0x14000ef17  lea     rcx, gBfsPolicyTable
0x14000ef1e  call    cs:__imp_ExReleasePushLockSharedEx
0x14000ef25  nop     dword ptr [rax+rax+00h]
0x14000ef2a  call    cs:__imp_KeLeaveCriticalRegion
0x14000ef31  nop     dword ptr [rax+rax+00h]
0x14000ef36  mov     [r14], esi
0x14000ef39  xor     edx, edx
0x14000ef3b  mov     rcx, rdi; P
0x14000ef3e  call    BfsDereferencePolicyEntryEx
0x14000ef43  mov     eax, ebx
0x14000ef45  mov     rcx, [rbp+110h+var_50]
0x14000ef4c  xor     rcx, rsp; StackCookie
0x14000ef4f  call    __security_check_cookie
0x14000ef54  add     rsp, 1D8h
0x14000ef5b  pop     r15
0x14000ef5d  pop     r14
0x14000ef5f  pop     r13
0x14000ef61  pop     r12
0x14000ef63  pop     rdi
0x14000ef64  pop     rsi
0x14000ef65  pop     rbx
0x14000ef66  pop     rbp
0x14000ef67  retn
```
