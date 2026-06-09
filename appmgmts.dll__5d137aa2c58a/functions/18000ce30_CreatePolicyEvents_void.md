# CreatePolicyEvents(void)

- ea: `0x18000ce30`
- end: `0x18000d116`
- name: `?CreatePolicyEvents@@YAXXZ`
- size: `742`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000bdf0`

## callees

- `0x1800016d0`
- `0x18000ce30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d0cc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d0db`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d0ea`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d0cc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d0db`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d0ea`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000d057`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000d057`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000d03f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000d03f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000cfdd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000d001`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000d028`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000cfdd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000d001`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000d028`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000cfb4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000cfb4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cf6d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cf79`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cf85`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cf6d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cf79`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000cf85`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000cedf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000cf20`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000cf5b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000cedf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000cf20`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000cf5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cf97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cf97`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d08e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d0b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d08e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d0b6`

## pseudocode

```c
void CreatePolicyEvents(void)
{
  struct _ACL *v0; // rbx
  DWORD LengthSid; // edi
  DWORD v2; // edi
  DWORD v3; // edi
  struct _ACL *v4; // rax
  PSID pSid; // [rsp+60h] [rbp-39h] BYREF
  PSID v6; // [rsp+68h] [rbp-31h] BYREF
  PSID v7; // [rsp+70h] [rbp-29h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+78h] [rbp-21h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v10; // [rsp+B0h] [rbp+17h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v12; // [rsp+C0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v10 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  *(_DWORD *)v12.Value = 0;
  *(_WORD *)&v12.Value[4] = 256;
  v6 = 0;
  pSid = 0;
  v7 = 0;
  if ( (gDebugLevel & 0x10) != 0 && (!ghUserPolicyEvent || !ghMachinePolicyEvent) )
  {
    v0 = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v6) )
      {
        if ( AllocateAndInitializeSid(&v12, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v7) )
        {
          LengthSid = GetLengthSid(v7);
          v2 = GetLengthSid(pSid) + LengthSid;
          v3 = GetLengthSid(v6) + 32 + v2;
          v4 = (struct _ACL *)LocalAlloc(0x40u, v3);
          v0 = v4;
          if ( v4 )
          {
            if ( InitializeAcl(v4, v3, 2u)
              && AddAccessAllowedAceEx(v0, 2u, 0, 0x10000000u, pSid)
              && AddAccessAllowedAceEx(v0, 2u, 0, 0x10000000u, v6)
              && AddAccessAllowedAceEx(v0, 2u, 0, 0x100000u, v7)
              && InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
              && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v0, 0) )
            {
              EventAttributes.lpSecurityDescriptor = pSecurityDescriptor;
              EventAttributes.nLength = 24;
              EventAttributes.bInheritHandle = 0;
              if ( !ghUserPolicyEvent )
                ghUserPolicyEvent = CreateEventW(&EventAttributes, 1, 0, L"AppMgmtUserPolicyEvent");
              if ( !ghMachinePolicyEvent )
                ghMachinePolicyEvent = CreateEventW(&EventAttributes, 1, 0, L"AppMgmtMachinePolicyEvent");
            }
          }
        }
      }
    }
    if ( pSid )
      FreeSid(pSid);
    if ( v6 )
      FreeSid(v6);
    if ( v7 )
      FreeSid(v7);
    if ( v0 )
      LocalFree(v0);
  }
}

```

## disassembly

```asm
0x18000ce30  push    rbp
0x18000ce32  push    rbx
0x18000ce33  push    rsi
0x18000ce34  push    rdi
0x18000ce35  lea     rbp, [rsp-3Fh]
0x18000ce3a  sub     rsp, 0D8h
0x18000ce41  mov     rax, cs:__security_cookie
0x18000ce48  xor     rax, rsp
0x18000ce4b  mov     [rbp+57h+var_28], rax
0x18000ce4f  xor     esi, esi
0x18000ce51  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000ce57  xor     eax, eax
0x18000ce59  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18000ce5c  test    byte ptr cs:?gDebugLevel@@3KA, 10h; ulong gDebugLevel
0x18000ce63  xorps   xmm1, xmm1
0x18000ce66  xorps   xmm0, xmm0
0x18000ce69  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x18000ce6d  movups  xmmword ptr [rbp+57h+EventAttributes.nLength], xmm0
0x18000ce71  mov     [rbp+57h+var_40], rax
0x18000ce75  movups  [rbp+57h+pSecurityDescriptor], xmm1
0x18000ce79  mov     dword ptr [rbp+57h+var_30.Value], esi
0x18000ce7c  movups  [rbp+57h+var_50], xmm1
0x18000ce80  mov     word ptr [rbp+57h+var_30.Value+4], 100h
0x18000ce86  mov     [rbp+57h+var_88], rsi
0x18000ce8a  mov     [rbp+57h+var_90], rsi
0x18000ce8e  mov     [rbp+57h+var_80], rsi
0x18000ce92  jz      loc_18000D0FE
0x18000ce98  cmp     cs:?ghUserPolicyEvent@@3PEAXEA, rsi; void * ghUserPolicyEvent
0x18000ce9f  jz      short loc_18000CEAE
0x18000cea1  cmp     cs:?ghMachinePolicyEvent@@3PEAXEA, rsi; void * ghMachinePolicyEvent
0x18000cea8  jnz     loc_18000D0FE
0x18000ceae  lea     rax, [rbp+57h+var_90]
0x18000ceb2  xor     r9d, r9d; nSubAuthority1
0x18000ceb5  mov     [rsp+0F0h+pSid], rax; pSid
0x18000ceba  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000cebe  mov     [rsp+0F0h+nSubAuthority7], esi; nSubAuthority7
0x18000cec2  mov     dl, 1; nSubAuthorityCount
0x18000cec4  mov     [rsp+0F0h+nSubAuthority6], esi; nSubAuthority6
0x18000cec8  mov     rbx, rsi
0x18000cecb  mov     [rsp+0F0h+nSubAuthority5], esi; nSubAuthority5
0x18000cecf  lea     r8d, [r9+12h]; nSubAuthority0
0x18000ced3  mov     [rsp+0F0h+nSubAuthority4], esi; nSubAuthority4
0x18000ced7  mov     [rsp+0F0h+nSubAuthority3], esi; nSubAuthority3
0x18000cedb  mov     [rsp+0F0h+nSubAuthority2], esi; nSubAuthority2
0x18000cedf  call    cs:__imp_AllocateAndInitializeSid
0x18000cee5  test    eax, eax
0x18000cee7  jz      loc_18000D0C3
0x18000ceed  lea     rax, [rbp+57h+var_88]
0x18000cef1  mov     r9d, 220h; nSubAuthority1
0x18000cef7  mov     [rsp+0F0h+pSid], rax; pSid
0x18000cefc  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000cf00  mov     [rsp+0F0h+nSubAuthority7], esi; nSubAuthority7
0x18000cf04  mov     r8d, 20h ; ' '; nSubAuthority0
0x18000cf0a  mov     [rsp+0F0h+nSubAuthority6], esi; nSubAuthority6
0x18000cf0e  mov     dl, 2; nSubAuthorityCount
0x18000cf10  mov     [rsp+0F0h+nSubAuthority5], esi; nSubAuthority5
0x18000cf14  mov     [rsp+0F0h+nSubAuthority4], esi; nSubAuthority4
0x18000cf18  mov     [rsp+0F0h+nSubAuthority3], esi; nSubAuthority3
0x18000cf1c  mov     [rsp+0F0h+nSubAuthority2], esi; nSubAuthority2
0x18000cf20  call    cs:__imp_AllocateAndInitializeSid
0x18000cf26  test    eax, eax
0x18000cf28  jz      loc_18000D0C3
0x18000cf2e  lea     rax, [rbp+57h+var_80]
0x18000cf32  xor     r9d, r9d; nSubAuthority1
0x18000cf35  mov     [rsp+0F0h+pSid], rax; pSid
0x18000cf3a  lea     rcx, [rbp+57h+var_30]; pIdentifierAuthority
0x18000cf3e  mov     [rsp+0F0h+nSubAuthority7], esi; nSubAuthority7
0x18000cf42  xor     r8d, r8d; nSubAuthority0
0x18000cf45  mov     [rsp+0F0h+nSubAuthority6], esi; nSubAuthority6
0x18000cf49  mov     dl, 1; nSubAuthorityCount
0x18000cf4b  mov     [rsp+0F0h+nSubAuthority5], esi; nSubAuthority5
0x18000cf4f  mov     [rsp+0F0h+nSubAuthority4], esi; nSubAuthority4
0x18000cf53  mov     [rsp+0F0h+nSubAuthority3], esi; nSubAuthority3
0x18000cf57  mov     [rsp+0F0h+nSubAuthority2], esi; nSubAuthority2
0x18000cf5b  call    cs:__imp_AllocateAndInitializeSid
0x18000cf61  test    eax, eax
0x18000cf63  jz      loc_18000D0C3
0x18000cf69  mov     rcx, [rbp+57h+var_80]; pSid
0x18000cf6d  call    cs:__imp_GetLengthSid
0x18000cf73  mov     rcx, [rbp+57h+var_90]; pSid
0x18000cf77  mov     edi, eax
0x18000cf79  call    cs:__imp_GetLengthSid
0x18000cf7f  mov     rcx, [rbp+57h+var_88]; pSid
0x18000cf83  add     edi, eax
0x18000cf85  call    cs:__imp_GetLengthSid
0x18000cf8b  add     eax, 20h ; ' '
0x18000cf8e  mov     ecx, 40h ; '@'; uFlags
0x18000cf93  add     edi, eax
0x18000cf95  mov     edx, edi; uBytes
0x18000cf97  call    cs:__imp_LocalAlloc
0x18000cf9d  mov     rbx, rax
0x18000cfa0  test    rax, rax
0x18000cfa3  jz      loc_18000D0C3
0x18000cfa9  mov     r8d, 2; dwAclRevision
0x18000cfaf  mov     edx, edi; nAclLength
0x18000cfb1  mov     rcx, rax; pAcl
0x18000cfb4  call    cs:__imp_InitializeAcl
0x18000cfba  test    eax, eax
0x18000cfbc  jz      loc_18000D0C3
0x18000cfc2  mov     rcx, [rbp+57h+var_90]
0x18000cfc6  xor     r8d, r8d; AceFlags
0x18000cfc9  mov     qword ptr [rsp+0F0h+nSubAuthority2], rcx; pSid
0x18000cfce  mov     edi, 10000000h
0x18000cfd3  mov     r9d, edi; AccessMask
0x18000cfd6  mov     rcx, rbx; pAcl
0x18000cfd9  lea     edx, [r8+2]; dwAceRevision
0x18000cfdd  call    cs:__imp_AddAccessAllowedAceEx
0x18000cfe3  test    eax, eax
0x18000cfe5  jz      loc_18000D0C3
0x18000cfeb  mov     rax, [rbp+57h+var_88]
0x18000cfef  xor     r8d, r8d; AceFlags
0x18000cff2  mov     r9d, edi; AccessMask
0x18000cff5  mov     qword ptr [rsp+0F0h+nSubAuthority2], rax; pSid
0x18000cffa  mov     rcx, rbx; pAcl
0x18000cffd  lea     edx, [r8+2]; dwAceRevision
0x18000d001  call    cs:__imp_AddAccessAllowedAceEx
0x18000d007  test    eax, eax
0x18000d009  jz      loc_18000D0C3
0x18000d00f  mov     rax, [rbp+57h+var_80]
0x18000d013  xor     r8d, r8d; AceFlags
0x18000d016  mov     r9d, 100000h; AccessMask
0x18000d01c  mov     qword ptr [rsp+0F0h+nSubAuthority2], rax; pSid
0x18000d021  mov     rcx, rbx; pAcl
0x18000d024  lea     edx, [r8+2]; dwAceRevision
0x18000d028  call    cs:__imp_AddAccessAllowedAceEx
0x18000d02e  test    eax, eax
0x18000d030  jz      loc_18000D0C3
0x18000d036  mov     edx, 1; dwRevision
0x18000d03b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000d03f  call    cs:__imp_InitializeSecurityDescriptor
0x18000d045  test    eax, eax
0x18000d047  jz      short loc_18000D0C3
0x18000d049  xor     r9d, r9d; bDaclDefaulted
0x18000d04c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000d050  mov     r8, rbx; pDacl
0x18000d053  lea     edx, [r9+1]; bDaclPresent
0x18000d057  call    cs:__imp_SetSecurityDescriptorDacl
0x18000d05d  test    eax, eax
0x18000d05f  jz      short loc_18000D0C3
0x18000d061  cmp     cs:?ghUserPolicyEvent@@3PEAXEA, rsi; void * ghUserPolicyEvent
0x18000d068  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18000d06c  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x18000d070  mov     [rbp+57h+EventAttributes.nLength], 18h
0x18000d077  mov     [rbp+57h+EventAttributes.bInheritHandle], esi
0x18000d07a  jnz     short loc_18000D09B
0x18000d07c  xor     r8d, r8d; bInitialState
0x18000d07f  lea     r9, Name; "AppMgmtUserPolicyEvent"
0x18000d086  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x18000d08a  lea     edx, [r8+1]; bManualReset
0x18000d08e  call    cs:__imp_CreateEventW
0x18000d094  mov     cs:?ghUserPolicyEvent@@3PEAXEA, rax; void * ghUserPolicyEvent
0x18000d09b  cmp     cs:?ghMachinePolicyEvent@@3PEAXEA, rsi; void * ghMachinePolicyEvent
0x18000d0a2  jnz     short loc_18000D0C3
0x18000d0a4  xor     r8d, r8d; bInitialState
0x18000d0a7  lea     r9, aAppmgmtmachine; "AppMgmtMachinePolicyEvent"
0x18000d0ae  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x18000d0b2  lea     edx, [r8+1]; bManualReset
0x18000d0b6  call    cs:__imp_CreateEventW
0x18000d0bc  mov     cs:?ghMachinePolicyEvent@@3PEAXEA, rax; void * ghMachinePolicyEvent
0x18000d0c3  mov     rcx, [rbp+57h+var_90]; pSid
0x18000d0c7  test    rcx, rcx
0x18000d0ca  jz      short loc_18000D0D2
0x18000d0cc  call    cs:__imp_FreeSid
0x18000d0d2  mov     rcx, [rbp+57h+var_88]; pSid
0x18000d0d6  test    rcx, rcx
0x18000d0d9  jz      short loc_18000D0E1
0x18000d0db  call    cs:__imp_FreeSid
0x18000d0e1  mov     rcx, [rbp+57h+var_80]; pSid
0x18000d0e5  test    rcx, rcx
0x18000d0e8  jz      short loc_18000D0F0
0x18000d0ea  call    cs:__imp_FreeSid
0x18000d0f0  test    rbx, rbx
0x18000d0f3  jz      short loc_18000D0FE
0x18000d0f5  mov     rcx, rbx; hMem
0x18000d0f8  call    cs:__imp_LocalFree
0x18000d0fe  mov     rcx, [rbp+57h+var_28]
0x18000d102  xor     rcx, rsp; StackCookie
0x18000d105  call    __security_check_cookie
0x18000d10a  add     rsp, 0D8h
0x18000d111  pop     rdi
0x18000d112  pop     rsi
0x18000d113  pop     rbx
0x18000d114  pop     rbp
0x18000d115  retn
```
