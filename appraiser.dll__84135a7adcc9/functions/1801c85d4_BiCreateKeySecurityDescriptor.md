# BiCreateKeySecurityDescriptor

- ea: `0x1801c85d4`
- end: `0x1801c885f`
- name: `BiCreateKeySecurityDescriptor`
- size: `651`
- prototype: `__int64 __fastcall(ACCESS_MASK AccessMask)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801c8320`
- `0x1801c8384`
- `0x1801c95d4`

## callees

- `0x180008570`
- `0x18000a927`
- `0x1801c85d4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1801c882f`
- `ntdll!RtlFreeHeap` at `0x1801c882f`
- `ntdll!RtlAllocateHeap` at `0x1801c86df`
- `ntdll!RtlAllocateHeap` at `0x1801c86df`
- `ntdll!RtlFreeSid` at `0x1801c87fa`
- `ntdll!RtlFreeSid` at `0x1801c8809`
- `ntdll!RtlFreeSid` at `0x1801c87fa`
- `ntdll!RtlFreeSid` at `0x1801c8809`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1801c8793`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1801c87b6`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1801c8793`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1801c87b6`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1801c87e3`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1801c87e3`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801c8784`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801c8784`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801c872c`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801c8755`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801c872c`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801c8755`
- `ntdll!RtlLengthSid` at `0x1801c86a5`
- `ntdll!RtlLengthSid` at `0x1801c86b1`
- `ntdll!RtlLengthSid` at `0x1801c86c0`
- `ntdll!RtlLengthSid` at `0x1801c879f`
- `ntdll!RtlLengthSid` at `0x1801c87c5`
- `ntdll!RtlLengthSid` at `0x1801c86a5`
- `ntdll!RtlLengthSid` at `0x1801c86b1`
- `ntdll!RtlLengthSid` at `0x1801c86c0`
- `ntdll!RtlLengthSid` at `0x1801c879f`
- `ntdll!RtlLengthSid` at `0x1801c87c5`
- `ntdll!RtlCreateAcl` at `0x1801c8706`
- `ntdll!RtlCreateAcl` at `0x1801c8706`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801c876d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801c876d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1801c864c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1801c8691`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1801c864c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1801c8691`

## pseudocode

```c
struct _ACL *__fastcall BiCreateKeySecurityDescriptor(ACCESS_MASK AccessMask)
{
  struct _ACL *v2; // rdi
  NTSTATUS Acl; // ebx
  ULONG v4; // ebx
  ULONG v5; // ebx
  ULONG v6; // r15d
  struct _ACL *Heap; // rax
  struct _ACL *v8; // rsi
  ULONG v9; // ebx
  char *v10; // rbx
  ULONG v11; // eax
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  PSID Sid; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = 0;
  pSid = 0;
  Sid = 0;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid);
  if ( Acl >= 0 )
  {
    Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( Acl >= 0 )
    {
      v4 = RtlLengthSid(Sid);
      v5 = RtlLengthSid(pSid) + 24 + v4;
      v6 = v5 + RtlLengthSid(pSid) + 40;
      Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v2 = Heap;
      if ( Heap )
      {
        v8 = Heap + 5;
        Acl = RtlCreateAcl(Heap + 5, v5, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v8, 2u, 0, AccessMask, pSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v8, 2u, 0, 0xF003Fu, Sid);
            if ( Acl >= 0 )
            {
              Acl = RtlCreateSecurityDescriptor(v2, 1u);
              if ( Acl >= 0 )
              {
                Acl = RtlSetDaclSecurityDescriptor(v2, 1u, v8, 0);
                if ( Acl >= 0 )
                {
                  v9 = RtlLengthSecurityDescriptor(v2);
                  if ( RtlLengthSid(pSid) + v9 >= v6 )
                  {
                    v10 = (char *)v2 + RtlLengthSecurityDescriptor(v2);
                    v11 = RtlLengthSid(pSid);
                    memcpy_0(v10, pSid, v11);
                    Acl = RtlSetOwnerSecurityDescriptor(v2, v10, 0);
                    if ( Acl >= 0 )
                      Acl = 0;
                  }
                  else
                  {
                    Acl = -1073741789;
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        Acl = -1073741670;
      }
    }
  }
  if ( pSid )
    RtlFreeSid(pSid);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Acl >= 0 )
    return v2;
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  return 0;
}

```

## disassembly

```asm
0x1801c85d4  mov     r11, rsp
0x1801c85d7  mov     [r11+10h], rbx
0x1801c85db  mov     [r11+18h], rsi
0x1801c85df  push    rbp
0x1801c85e0  push    rdi
0x1801c85e1  push    r12
0x1801c85e3  push    r14
0x1801c85e5  push    r15
0x1801c85e7  mov     rbp, rsp
0x1801c85ea  sub     rsp, 80h
0x1801c85f1  mov     rax, cs:__security_cookie
0x1801c85f8  xor     rax, rsp
0x1801c85fb  mov     [rbp+var_8], rax
0x1801c85ff  xor     r12d, r12d
0x1801c8602  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1801c8608  lea     rax, [rbp+pSid]
0x1801c860c  mov     dword ptr [rbp+IdentifierAuthority.Value], r12d
0x1801c8610  mov     [r11-58h], rax
0x1801c8614  mov     r14d, ecx
0x1801c8617  mov     [r11-60h], r12d
0x1801c861b  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1801c861f  mov     [r11-68h], r12d
0x1801c8623  lea     r8d, [r12+20h]; SubAuthority0
0x1801c8628  mov     [r11-70h], r12d
0x1801c862c  mov     r9d, 220h; SubAuthority1
0x1801c8632  mov     [r11-78h], r12d
0x1801c8636  mov     dl, 2; SubAuthorityCount
0x1801c8638  mov     [r11-80h], r12d
0x1801c863c  mov     edi, r12d
0x1801c863f  mov     [rsp+80h+SubAuthority2], r12d; SubAuthority2
0x1801c8644  mov     [rbp+pSid], r12
0x1801c8648  mov     [rbp+var_18], r12
0x1801c864c  call    cs:__imp_RtlAllocateAndInitializeSid
0x1801c8652  mov     ebx, eax
0x1801c8654  test    eax, eax
0x1801c8656  js      loc_1801C87F1
0x1801c865c  lea     rax, [rbp+var_18]
0x1801c8660  xor     r9d, r9d; SubAuthority1
0x1801c8663  mov     [rsp+80h+Sid], rax; Sid
0x1801c8668  lea     r8d, [r12+12h]; SubAuthority0
0x1801c866d  mov     [rsp+80h+SubAuthority7], r12d; SubAuthority7
0x1801c8672  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1801c8676  mov     [rsp+80h+SubAuthority6], r12d; SubAuthority6
0x1801c867b  mov     dl, 1; SubAuthorityCount
0x1801c867d  mov     [rsp+80h+SubAuthority5], r12d; SubAuthority5
0x1801c8682  mov     [rsp+80h+SubAuthority4], r12d; SubAuthority4
0x1801c8687  mov     [rsp+80h+SubAuthority3], r12d; SubAuthority3
0x1801c868c  mov     [rsp+80h+SubAuthority2], r12d; SubAuthority2
0x1801c8691  call    cs:__imp_RtlAllocateAndInitializeSid
0x1801c8697  mov     ebx, eax
0x1801c8699  test    eax, eax
0x1801c869b  js      loc_1801C87F1
0x1801c86a1  mov     rcx, [rbp+var_18]; Sid
0x1801c86a5  call    cs:__imp_RtlLengthSid
0x1801c86ab  mov     rcx, [rbp+pSid]; Sid
0x1801c86af  mov     ebx, eax
0x1801c86b1  call    cs:__imp_RtlLengthSid
0x1801c86b7  mov     rcx, [rbp+pSid]; Sid
0x1801c86bb  add     eax, 18h
0x1801c86be  add     ebx, eax
0x1801c86c0  call    cs:__imp_RtlLengthSid
0x1801c86c6  mov     rcx, gs:60h
0x1801c86cf  xor     edx, edx; Flags
0x1801c86d1  lea     r15d, [rax+28h]
0x1801c86d5  mov     rcx, [rcx+30h]; HeapHandle
0x1801c86d9  add     r15d, ebx
0x1801c86dc  mov     r8d, r15d; Size
0x1801c86df  call    cs:__imp_RtlAllocateHeap
0x1801c86e5  mov     rdi, rax
0x1801c86e8  test    rax, rax
0x1801c86eb  jnz     short loc_1801C86F7
0x1801c86ed  mov     ebx, 0C000009Ah
0x1801c86f2  jmp     loc_1801C87F1
0x1801c86f7  lea     rsi, [rax+28h]
0x1801c86fb  mov     r8d, 2; AclRevision
0x1801c8701  mov     rcx, rsi; Acl
0x1801c8704  mov     edx, ebx; AclSize
0x1801c8706  call    cs:__imp_RtlCreateAcl
0x1801c870c  mov     ebx, eax
0x1801c870e  test    eax, eax
0x1801c8710  js      loc_1801C87F1
0x1801c8716  mov     rax, [rbp+pSid]
0x1801c871a  xor     r8d, r8d; AceFlags
0x1801c871d  mov     r9d, r14d; AccessMask
0x1801c8720  mov     qword ptr [rsp+80h+SubAuthority2], rax; pSid
0x1801c8725  mov     rcx, rsi; pAcl
0x1801c8728  lea     edx, [r8+2]; dwAceRevision
0x1801c872c  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801c8732  mov     ebx, eax
0x1801c8734  test    eax, eax
0x1801c8736  js      loc_1801C87F1
0x1801c873c  mov     rax, [rbp+var_18]
0x1801c8740  xor     r8d, r8d; AceFlags
0x1801c8743  mov     r9d, 0F003Fh; AccessMask
0x1801c8749  mov     qword ptr [rsp+80h+SubAuthority2], rax; pSid
0x1801c874e  mov     rcx, rsi; pAcl
0x1801c8751  lea     edx, [r8+2]; dwAceRevision
0x1801c8755  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801c875b  mov     ebx, eax
0x1801c875d  test    eax, eax
0x1801c875f  js      loc_1801C87F1
0x1801c8765  mov     edx, 1; Revision
0x1801c876a  mov     rcx, rdi; SecurityDescriptor
0x1801c876d  call    cs:__imp_RtlCreateSecurityDescriptor
0x1801c8773  mov     ebx, eax
0x1801c8775  test    eax, eax
0x1801c8777  js      short loc_1801C87F1
0x1801c8779  xor     r9d, r9d; DaclDefaulted
0x1801c877c  mov     r8, rsi; Dacl
0x1801c877f  mov     dl, 1; DaclPresent
0x1801c8781  mov     rcx, rdi; SecurityDescriptor
0x1801c8784  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1801c878a  mov     ebx, eax
0x1801c878c  test    eax, eax
0x1801c878e  js      short loc_1801C87F1
0x1801c8790  mov     rcx, rdi; SecurityDescriptor
0x1801c8793  call    cs:__imp_RtlLengthSecurityDescriptor
0x1801c8799  mov     rcx, [rbp+pSid]; Sid
0x1801c879d  mov     ebx, eax
0x1801c879f  call    cs:__imp_RtlLengthSid
0x1801c87a5  add     ebx, eax
0x1801c87a7  cmp     ebx, r15d
0x1801c87aa  jnb     short loc_1801C87B3
0x1801c87ac  mov     ebx, 0C0000023h
0x1801c87b1  jmp     short loc_1801C87F1
0x1801c87b3  mov     rcx, rdi; SecurityDescriptor
0x1801c87b6  call    cs:__imp_RtlLengthSecurityDescriptor
0x1801c87bc  mov     rcx, [rbp+pSid]; Sid
0x1801c87c0  mov     ebx, eax
0x1801c87c2  add     rbx, rdi
0x1801c87c5  call    cs:__imp_RtlLengthSid
0x1801c87cb  mov     rdx, [rbp+pSid]; Src
0x1801c87cf  mov     rcx, rbx; void *
0x1801c87d2  mov     r8d, eax; Size
0x1801c87d5  call    memcpy_0
0x1801c87da  xor     r8d, r8d; OwnerDefaulted
0x1801c87dd  mov     rdx, rbx; Owner
0x1801c87e0  mov     rcx, rdi; SecurityDescriptor
0x1801c87e3  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1801c87e9  test    eax, eax
0x1801c87eb  mov     ebx, eax
0x1801c87ed  cmovns  ebx, r12d
0x1801c87f1  mov     rcx, [rbp+pSid]; Sid
0x1801c87f5  test    rcx, rcx
0x1801c87f8  jz      short loc_1801C8800
0x1801c87fa  call    cs:__imp_RtlFreeSid
0x1801c8800  mov     rcx, [rbp+var_18]; Sid
0x1801c8804  test    rcx, rcx
0x1801c8807  jz      short loc_1801C880F
0x1801c8809  call    cs:__imp_RtlFreeSid
0x1801c880f  test    ebx, ebx
0x1801c8811  js      short loc_1801C8818
0x1801c8813  mov     rax, rdi
0x1801c8816  jmp     short loc_1801C8837
0x1801c8818  test    rdi, rdi
0x1801c881b  jz      short loc_1801C8835
0x1801c881d  mov     rcx, gs:60h
0x1801c8826  mov     r8, rdi; P
0x1801c8829  xor     edx, edx; Flags
0x1801c882b  mov     rcx, [rcx+30h]; HeapHandle
0x1801c882f  call    cs:__imp_RtlFreeHeap
0x1801c8835  xor     eax, eax
0x1801c8837  mov     rcx, [rbp+var_8]
0x1801c883b  xor     rcx, rsp; StackCookie
0x1801c883e  call    __security_check_cookie
0x1801c8843  lea     r11, [rsp+80h+var_s0]
0x1801c884b  mov     rbx, [r11+38h]
0x1801c884f  mov     rsi, [r11+40h]
0x1801c8853  mov     rsp, r11
0x1801c8856  pop     r15
0x1801c8858  pop     r14
0x1801c885a  pop     r12
0x1801c885c  pop     rdi
0x1801c885d  pop     rbp
0x1801c885e  retn
```
