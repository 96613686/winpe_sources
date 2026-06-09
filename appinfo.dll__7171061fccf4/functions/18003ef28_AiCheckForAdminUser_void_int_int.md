# AiCheckForAdminUser(void *,int,int *)

- ea: `0x18003ef28`
- end: `0x18003f145`
- name: `?AiCheckForAdminUser@@YAJPEAXHPEAH@Z`
- size: `541`
- prototype: `__int64 __fastcall(HANDLE Handle, __int64, int *)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017680`
- `0x180029aa0`
- `0x18002ed98`
- `0x18003d070`
- `0x18003f14c`
- `0x1800409a0`
- `0x180040d64`

## callees

- `0x18001e7bc`
- `0x180026630`
- `0x18003edf4`
- `0x18003ef28`
- `0x1800461e8`
- `0x180046e50`

## import_xrefs

- `ntdll!NtClose` at `0x18003f0ff`
- `ntdll!NtClose` at `0x18003f116`
- `ntdll!NtClose` at `0x18003f0ff`
- `ntdll!NtClose` at `0x18003f116`
- `ntdll!NtQueryInformationToken` at `0x18003f054`
- `ntdll!NtQueryInformationToken` at `0x18003f054`
- `ntdll!RtlEqualSid` at `0x18003f010`
- `ntdll!RtlEqualSid` at `0x18003f010`
- `ntdll!RtlGetLastNtStatus` at `0x18003efc2`
- `ntdll!RtlGetLastNtStatus` at `0x18003efc2`
- `ntdll!NtDuplicateToken` at `0x18003f0bf`
- `ntdll!NtDuplicateToken` at `0x18003f0bf`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003f0dd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003f0dd`

## pseudocode

```c
__int64 __fastcall AiCheckForAdminUser(HANDLE Handle, __int64 a2, int *a3)
{
  HANDLE v5; // rdi
  __int64 v6; // rcx
  NTSTATUS LastNtStatus; // eax
  void *v8; // rcx
  int LastStatusValue; // ebx
  _QWORD *v10; // rsi
  unsigned int v11; // r14d
  __int64 v12; // rax
  NTSTATUS v13; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-49h] BYREF
  void *TokenInformation; // [rsp+38h] [rbp-41h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-39h] BYREF
  void *Block; // [rsp+48h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-29h] BYREF
  __int64 v20; // [rsp+80h] [rbp+7h] BYREF
  int v21; // [rsp+88h] [rbp+Fh]

  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v20 = 0;
  v5 = Handle;
  v21 = 0;
  *a3 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( (_DWORD)a2 )
  {
LABEL_20:
    v20 = 0x20000000CLL;
    ObjectAttributes.SecurityQualityOfService = &v20;
    LOWORD(v21) = 1;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    ObjectAttributes.SecurityDescriptor = 0;
    LastStatusValue = NtDuplicateToken(v5, 0, &ObjectAttributes, 0, TokenImpersonation, &TokenHandle);
    if ( LastStatusValue >= 0 && !CheckTokenMembership(TokenHandle, *((PSID *)g_pSvchostSharedGlobals + 10), a3) )
      LastStatusValue = NtCurrentTeb()->LastStatusValue;
    goto LABEL_23;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                          a2)
    || !(unsigned int)LUAIsShadowAdminEnabled(v6) )
  {
    v13 = NtQueryInformationToken(Handle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength);
    if ( v13 < 0 )
    {
      LastStatusValue = 0;
      if ( v13 != -1073741729 )
        LastStatusValue = v13;
      goto LABEL_23;
    }
    v5 = TokenInformation;
    goto LABEL_20;
  }
  Block = 0;
  if ( (int)wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(&Block, v5) < 0 )
  {
    LastNtStatus = RtlGetLastNtStatus();
    v8 = Block;
    LastStatusValue = LastNtStatus;
    if ( !Block )
      goto LABEL_23;
    goto LABEL_6;
  }
  v10 = Block;
  LastStatusValue = 0;
  v11 = 0;
  if ( *(_DWORD *)Block )
  {
    while ( 1 )
    {
      v12 = v10[1];
      if ( (*(_BYTE *)(v12 + 16LL * v11 + 8) & 0x10) != 0 )
      {
        if ( RtlEqualSid(*(PSID *)(v12 + 16LL * v11), *((PSID *)g_pSvchostSharedGlobals + 10)) )
          break;
      }
      if ( ++v11 >= *(_DWORD *)v10 )
        goto LABEL_13;
    }
    *a3 = 1;
  }
LABEL_13:
  if ( v10 )
  {
    v8 = v10;
LABEL_6:
    operator delete(v8);
  }
LABEL_23:
  if ( TokenHandle )
  {
    NtClose(TokenHandle);
    TokenHandle = 0;
  }
  if ( v5 != Handle && v5 )
    NtClose(v5);
  return (unsigned int)LastStatusValue;
}

```

## disassembly

```asm
0x18003ef28  mov     [rsp-8+arg_8], rbx
0x18003ef2d  push    rbp
0x18003ef2e  push    rsi
0x18003ef2f  push    rdi
0x18003ef30  push    r12
0x18003ef32  push    r13
0x18003ef34  push    r14
0x18003ef36  push    r15
0x18003ef38  lea     rbp, [rsp-27h]
0x18003ef3d  sub     rsp, 0A0h
0x18003ef44  mov     rax, cs:__security_cookie
0x18003ef4b  xor     rax, rsp
0x18003ef4e  mov     [rbp+57h+var_40], rax
0x18003ef52  xor     r13d, r13d
0x18003ef55  xor     eax, eax
0x18003ef57  mov     [rbp+57h+TokenHandle], r13
0x18003ef5b  xorps   xmm0, xmm0
0x18003ef5e  mov     [rbp+57h+TokenInformation], r13
0x18003ef62  mov     r12, r8
0x18003ef65  mov     [rbp+57h+var_A0], r13d
0x18003ef69  mov     r15, rcx
0x18003ef6c  mov     [rbp+57h+var_50], rax
0x18003ef70  mov     rdi, rcx
0x18003ef73  mov     [rbp+57h+var_48], eax
0x18003ef76  mov     [r8], r13d
0x18003ef79  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003ef7d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003ef81  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ef85  test    edx, edx
0x18003ef87  jnz     loc_18003F072
0x18003ef8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18003ef94  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18003ef99  test    al, al
0x18003ef9b  jnz     loc_18003F03A
0x18003efa1  call    LUAIsShadowAdminEnabled
0x18003efa6  test    eax, eax
0x18003efa8  jz      loc_18003F03A
0x18003efae  mov     rdx, rdi
0x18003efb1  mov     [rbp+57h+Block], r13
0x18003efb5  lea     rcx, [rbp+57h+Block]
0x18003efb9  call    ??$get_token_information_nothrow@U_TOKEN_GROUPS_AND_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_GROUPS_AND_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_GROUPS_AND_PRIVILEGES,wil::details::token_info_deleter> &,void *)
0x18003efbe  test    eax, eax
0x18003efc0  jns     short loc_18003EFE1
0x18003efc2  call    cs:__imp_RtlGetLastNtStatus
0x18003efc8  mov     rcx, [rbp+57h+Block]; Block
0x18003efcc  mov     ebx, eax
0x18003efce  test    rcx, rcx
0x18003efd1  jz      loc_18003F0F6
0x18003efd7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003efdc  jmp     loc_18003F0F6
0x18003efe1  mov     rsi, [rbp+57h+Block]
0x18003efe5  mov     ebx, r13d
0x18003efe8  mov     r14d, r13d
0x18003efeb  cmp     [rsi], r13d
0x18003efee  jbe     short loc_18003F02C
0x18003eff0  mov     rax, [rsi+8]
0x18003eff4  mov     ecx, r14d
0x18003eff7  add     rcx, rcx
0x18003effa  test    byte ptr [rax+rcx*8+8], 10h
0x18003efff  jz      short loc_18003F01A
0x18003f001  mov     rdx, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x18003f008  mov     rcx, [rax+rcx*8]; Sid1
0x18003f00c  mov     rdx, [rdx+50h]; Sid2
0x18003f010  call    cs:__imp_RtlEqualSid
0x18003f016  test    al, al
0x18003f018  jnz     short loc_18003F024
0x18003f01a  inc     r14d
0x18003f01d  cmp     r14d, [rsi]
0x18003f020  jb      short loc_18003EFF0
0x18003f022  jmp     short loc_18003F02C
0x18003f024  mov     dword ptr [r12], 1
0x18003f02c  test    rsi, rsi
0x18003f02f  jz      loc_18003F0F6
0x18003f035  mov     rcx, rsi
0x18003f038  jmp     short loc_18003EFD7
0x18003f03a  mov     r9d, 8; TokenInformationLength
0x18003f040  lea     rax, [rbp+57h+var_A0]
0x18003f044  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18003f048  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18003f04d  mov     rcx, r15; TokenHandle
0x18003f050  lea     edx, [r9+0Bh]; TokenInformationClass
0x18003f054  call    cs:__imp_NtQueryInformationToken
0x18003f05a  test    eax, eax
0x18003f05c  jns     short loc_18003F06E
0x18003f05e  cmp     eax, 0C000005Fh
0x18003f063  mov     ebx, r13d
0x18003f066  cmovnz  ebx, eax
0x18003f069  jmp     loc_18003F0F6
0x18003f06e  mov     rdi, [rbp+57h+TokenInformation]
0x18003f072  mov     ecx, 2
0x18003f077  mov     dword ptr [rbp+57h+var_50], 0Ch
0x18003f07e  lea     rax, [rbp+57h+var_50]
0x18003f082  mov     dword ptr [rbp+57h+var_50+4], ecx
0x18003f085  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18003f089  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003f08d  lea     rax, [rbp+57h+TokenHandle]
0x18003f091  mov     word ptr [rbp+57h+var_48], 1
0x18003f097  mov     [rsp+0D0h+NewTokenHandle], rax; NewTokenHandle
0x18003f09c  xor     r9d, r9d; EffectiveOnly
0x18003f09f  mov     dword ptr [rsp+0D0h+ReturnLength], ecx; TokenType
0x18003f0a3  xor     edx, edx; DesiredAccess
0x18003f0a5  mov     rcx, rdi; ExistingTokenHandle
0x18003f0a8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003f0af  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x18003f0b3  mov     [rbp+57h+ObjectAttributes.Attributes], r13d
0x18003f0b7  mov     [rbp+57h+ObjectAttributes.ObjectName], r13
0x18003f0bb  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r13
0x18003f0bf  call    cs:__imp_NtDuplicateToken
0x18003f0c5  mov     ebx, eax
0x18003f0c7  test    eax, eax
0x18003f0c9  js      short loc_18003F0F6
0x18003f0cb  mov     rdx, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x18003f0d2  mov     r8, r12; IsMember
0x18003f0d5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003f0d9  mov     rdx, [rdx+50h]; SidToCheck
0x18003f0dd  call    cs:__imp_CheckTokenMembership
0x18003f0e3  test    eax, eax
0x18003f0e5  jnz     short loc_18003F0F6
0x18003f0e7  mov     rax, gs:30h
0x18003f0f0  mov     ebx, [rax+1250h]
0x18003f0f6  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18003f0fa  test    rcx, rcx
0x18003f0fd  jz      short loc_18003F109
0x18003f0ff  call    cs:__imp_NtClose
0x18003f105  mov     [rbp+57h+TokenHandle], r13
0x18003f109  cmp     rdi, r15
0x18003f10c  jz      short loc_18003F11C
0x18003f10e  test    rdi, rdi
0x18003f111  jz      short loc_18003F11C
0x18003f113  mov     rcx, rdi; Handle
0x18003f116  call    cs:__imp_NtClose
0x18003f11c  mov     eax, ebx
0x18003f11e  mov     rcx, [rbp+57h+var_40]
0x18003f122  xor     rcx, rsp; StackCookie
0x18003f125  call    __security_check_cookie
0x18003f12a  mov     rbx, [rsp+0D0h+arg_8]
0x18003f132  add     rsp, 0A0h
0x18003f139  pop     r15
0x18003f13b  pop     r14
0x18003f13d  pop     r13
0x18003f13f  pop     r12
0x18003f141  pop     rdi
0x18003f142  pop     rsi
0x18003f143  pop     rbp
0x18003f144  retn
```
