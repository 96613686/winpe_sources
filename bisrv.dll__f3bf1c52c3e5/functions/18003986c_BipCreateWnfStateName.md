# BipCreateWnfStateName

- ea: `0x18003986c`
- end: `0x180039aa3`
- name: `BipCreateWnfStateName`
- size: `567`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007ebc`
- `0x180008598`
- `0x180073d7c`

## callees

- `0x18003986c`
- `0x180039aac`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x1800398f4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800398f4`
- `ntdll!RtlCreateAcl` at `0x18003992c`
- `ntdll!RtlCreateAcl` at `0x18003992c`
- `ntdll!RtlFreeSid` at `0x180039a84`
- `ntdll!RtlFreeSid` at `0x180039a84`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180039952`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180039972`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800399ef`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180039a79`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180039952`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180039972`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800399ef`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180039a79`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180039a0a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180039a0a`
- `ntdll!NtCreateWnfStateName` at `0x180039a47`
- `ntdll!NtCreateWnfStateName` at `0x180039a47`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180039911`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180039911`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800399ca`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800399ca`

## pseudocode

```c
NTSTATUS __fastcall BipCreateWnfStateName(__int64 a1, char a2, int a3, void *a4, __int64 a5)
{
  NTSTATUS result; // eax
  NTSTATUS v10; // ebx
  void *v11; // rax
  void *v12; // rdi
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h]
  _BYTE v16[80]; // [rsp+70h] [rbp-90h] BYREF
  struct _ACL Acl; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(&Acl, 0, 0xECu);
  memset_0(v16, 0, 0x44u);
  v15 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  cbSid = 0;
  result = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( result >= 0 )
  {
    result = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, qword_1800C4100, 1u);
    if ( result >= 0 )
    {
      result = RtlCreateAcl(&Acl, 0xECu, 2u);
      if ( result >= 0 )
      {
        result = RtlAddAccessAllowedAceEx(&Acl, 2u, 0, 0x10000000u, qword_1800C4100);
        if ( result >= 0 )
        {
          if ( a3 )
          {
            if ( a3 != 1 )
            {
LABEL_13:
              result = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
              if ( result >= 0 )
                return NtCreateWnfStateName(a1, a2 != 0 ? 1 : 3, 0, 0, 0, 4096, SecurityDescriptor);
              return result;
            }
            cbSid = 68;
            if ( !CreateWellKnownSid(WinWorldSid, 0, v16, &cbSid) )
              return -1073741823;
            v10 = RtlAddAccessAllowedAceEx(&Acl, 2u, 0, 1u, v16);
          }
          else
          {
            v10 = RtlAddAccessAllowedAceEx(&Acl, 2u, 0, 1u, a4);
            if ( v10 < 0 )
              return v10;
            if ( !a5 )
              goto LABEL_13;
            v11 = (void *)BipPackageIdToSid(a5);
            v12 = v11;
            if ( !v11 )
              return -1073741823;
            v10 = RtlAddAccessAllowedAceEx(&Acl, 2u, 0, 1u, v11);
            RtlFreeSid(v12);
          }
          if ( v10 < 0 )
            return v10;
          goto LABEL_13;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003986c  mov     [rsp-8+arg_8], rbx
0x180039871  push    rbp
0x180039872  push    rsi
0x180039873  push    rdi
0x180039874  push    r12
0x180039876  push    r13
0x180039878  push    r14
0x18003987a  push    r15
0x18003987c  lea     rbp, [rsp-0C0h]
0x180039884  sub     rsp, 1C0h
0x18003988b  mov     rax, cs:__security_cookie
0x180039892  xor     rax, rsp
0x180039895  mov     [rbp+0F0h+var_40], rax
0x18003989c  mov     rdi, [rbp+0F0h+arg_20]
0x1800398a3  mov     ebx, r8d
0x1800398a6  mov     sil, dl
0x1800398a9  mov     r15, rcx
0x1800398ac  xor     edx, edx; Val
0x1800398ae  lea     rcx, [rbp+0F0h+Acl]; void *
0x1800398b2  mov     r8d, 0ECh; Size
0x1800398b8  mov     r14, r9
0x1800398bb  call    memset_0
0x1800398c0  xor     edx, edx; Val
0x1800398c2  lea     rcx, [rsp+1F0h+var_180]; void *
0x1800398c7  lea     r8d, [rdx+44h]; Size
0x1800398cb  call    memset_0
0x1800398d0  xor     eax, eax
0x1800398d2  lea     rcx, [rsp+1F0h+SecurityDescriptor]; SecurityDescriptor
0x1800398d7  xorps   xmm0, xmm0
0x1800398da  mov     [rsp+1F0h+var_188], rax
0x1800398df  movups  [rsp+1F0h+SecurityDescriptor], xmm0
0x1800398e4  mov     [rsp+1F0h+cbSid], eax
0x1800398e8  lea     r12d, [rax+1]
0x1800398ec  mov     edx, r12d; Revision
0x1800398ef  movups  [rsp+1F0h+var_198], xmm0
0x1800398f4  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800398fa  test    eax, eax
0x1800398fc  js      loc_180039984
0x180039902  mov     r8b, r12b; OwnerDefaulted
0x180039905  lea     rdx, qword_1800C4100; Owner
0x18003990c  lea     rcx, [rsp+1F0h+SecurityDescriptor]; SecurityDescriptor
0x180039911  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180039917  test    eax, eax
0x180039919  js      short loc_180039984
0x18003991b  lea     r13d, [r12+1]
0x180039920  mov     edx, 0ECh; AclSize
0x180039925  mov     r8d, r13d; AclRevision
0x180039928  lea     rcx, [rbp+0F0h+Acl]; Acl
0x18003992c  call    cs:__imp_RtlCreateAcl
0x180039932  test    eax, eax
0x180039934  js      short loc_180039984
0x180039936  lea     rax, qword_1800C4100
0x18003993d  mov     r9d, 10000000h; AccessMask
0x180039943  xor     r8d, r8d; AceFlags
0x180039946  mov     [rsp+1F0h+pSid], rax; pSid
0x18003994b  mov     edx, r13d; dwAceRevision
0x18003994e  lea     rcx, [rbp+0F0h+Acl]; pAcl
0x180039952  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180039958  test    eax, eax
0x18003995a  js      short loc_180039984
0x18003995c  test    ebx, ebx
0x18003995e  jnz     short loc_1800399AE
0x180039960  mov     r9d, r12d; AccessMask
0x180039963  mov     [rsp+1F0h+pSid], r14; pSid
0x180039968  xor     r8d, r8d; AceFlags
0x18003996b  lea     rcx, [rbp+0F0h+Acl]; pAcl
0x18003996f  mov     edx, r13d; dwAceRevision
0x180039972  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180039978  mov     ebx, eax
0x18003997a  test    eax, eax
0x18003997c  jns     loc_180039A52
0x180039982  mov     eax, ebx
0x180039984  mov     rcx, [rbp+0F0h+var_40]
0x18003998b  xor     rcx, rsp; StackCookie
0x18003998e  call    __security_check_cookie
0x180039993  mov     rbx, [rsp+1F0h+arg_8]
0x18003999b  add     rsp, 1C0h
0x1800399a2  pop     r15
0x1800399a4  pop     r14
0x1800399a6  pop     r13
0x1800399a8  pop     r12
0x1800399aa  pop     rdi
0x1800399ab  pop     rsi
0x1800399ac  pop     rbp
0x1800399ad  retn
0x1800399ae  cmp     ebx, r12d
0x1800399b1  jnz     short loc_1800399FB
0x1800399b3  lea     r9, [rsp+1F0h+cbSid]; cbSid
0x1800399b8  mov     [rsp+1F0h+cbSid], 44h ; 'D'
0x1800399c0  lea     r8, [rsp+1F0h+var_180]; pSid
0x1800399c5  xor     edx, edx; DomainSid
0x1800399c7  mov     ecx, r12d; WellKnownSidType
0x1800399ca  call    cs:__imp_CreateWellKnownSid
0x1800399d0  test    eax, eax
0x1800399d2  jz      loc_180039A8F
0x1800399d8  lea     rax, [rsp+1F0h+var_180]
0x1800399dd  mov     r9d, r12d; AccessMask
0x1800399e0  xor     r8d, r8d; AceFlags
0x1800399e3  mov     [rsp+1F0h+pSid], rax; pSid
0x1800399e8  mov     edx, r13d; dwAceRevision
0x1800399eb  lea     rcx, [rbp+0F0h+Acl]; pAcl
0x1800399ef  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1800399f5  mov     ebx, eax
0x1800399f7  test    ebx, ebx
0x1800399f9  js      short loc_180039982
0x1800399fb  xor     r9d, r9d; DaclDefaulted
0x1800399fe  lea     r8, [rbp+0F0h+Acl]; Dacl
0x180039a02  mov     dl, r12b; DaclPresent
0x180039a05  lea     rcx, [rsp+1F0h+SecurityDescriptor]; SecurityDescriptor
0x180039a0a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180039a10  test    eax, eax
0x180039a12  js      loc_180039984
0x180039a18  neg     sil
0x180039a1b  lea     rax, [rsp+1F0h+SecurityDescriptor]
0x180039a20  mov     [rsp+1F0h+var_1C0], rax
0x180039a25  mov     rcx, r15
0x180039a28  sbb     edx, edx
0x180039a2a  mov     [rsp+1F0h+var_1C8], 1000h
0x180039a32  and     edx, 0FFFFFFFEh
0x180039a35  mov     [rsp+1F0h+pSid], 0
0x180039a3e  add     edx, 3
0x180039a41  xor     r9d, r9d
0x180039a44  xor     r8d, r8d
0x180039a47  call    cs:__imp_NtCreateWnfStateName
0x180039a4d  jmp     loc_180039984
0x180039a52  test    rdi, rdi
0x180039a55  jz      short loc_1800399FB
0x180039a57  mov     rcx, rdi
0x180039a5a  call    BipPackageIdToSid
0x180039a5f  mov     rdi, rax
0x180039a62  test    rax, rax
0x180039a65  jz      short loc_180039A99
0x180039a67  mov     r9d, r12d; AccessMask
0x180039a6a  mov     [rsp+1F0h+pSid], rax; pSid
0x180039a6f  xor     r8d, r8d; AceFlags
0x180039a72  lea     rcx, [rbp+0F0h+Acl]; pAcl
0x180039a76  mov     edx, r13d; dwAceRevision
0x180039a79  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180039a7f  mov     rcx, rdi; Sid
0x180039a82  mov     ebx, eax
0x180039a84  call    cs:__imp_RtlFreeSid
0x180039a8a  jmp     loc_1800399F7
0x180039a8f  mov     ebx, 0C0000001h
0x180039a94  jmp     loc_180039982
0x180039a99  mov     eax, 0C0000001h
0x180039a9e  jmp     loc_180039984
```
