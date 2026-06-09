# BiCreateKeySecurityDescriptor

- ea: `0x14001e980`
- end: `0x14001ec0b`
- name: `BiCreateKeySecurityDescriptor`
- size: `651`
- prototype: `struct _ACL *__fastcall(ACCESS_MASK AccessMask)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001e5e4`
- `0x14001e730`
- `0x14001f980`

## callees

- `0x14001e980`
- `0x1400265e2`
- `0x140026650`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x14001eb3f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x14001eb62`
- `ntdll!RtlLengthSecurityDescriptor` at `0x14001eb3f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x14001eb62`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x14001eb8f`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x14001eb8f`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14001eb30`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14001eb30`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x14001ead8`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x14001eb01`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x14001ead8`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x14001eb01`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14001e9f8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14001ea3d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14001e9f8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14001ea3d`
- `ntdll!RtlLengthSid` at `0x14001ea51`
- `ntdll!RtlLengthSid` at `0x14001ea5d`
- `ntdll!RtlLengthSid` at `0x14001ea6c`
- `ntdll!RtlLengthSid` at `0x14001eb4b`
- `ntdll!RtlLengthSid` at `0x14001eb71`
- `ntdll!RtlLengthSid` at `0x14001ea51`
- `ntdll!RtlLengthSid` at `0x14001ea5d`
- `ntdll!RtlLengthSid` at `0x14001ea6c`
- `ntdll!RtlLengthSid` at `0x14001eb4b`
- `ntdll!RtlLengthSid` at `0x14001eb71`
- `ntdll!RtlFreeSid` at `0x14001eba6`
- `ntdll!RtlFreeSid` at `0x14001ebb5`
- `ntdll!RtlFreeSid` at `0x14001eba6`
- `ntdll!RtlFreeSid` at `0x14001ebb5`
- `ntdll!RtlCreateAcl` at `0x14001eab2`
- `ntdll!RtlCreateAcl` at `0x14001eab2`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14001eb19`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14001eb19`
- `ntdll!RtlAllocateHeap` at `0x14001ea8b`
- `ntdll!RtlAllocateHeap` at `0x14001ea8b`
- `ntdll!RtlFreeHeap` at `0x14001ebdb`
- `ntdll!RtlFreeHeap` at `0x14001ebdb`

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
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

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
0x14001e980  mov     r11, rsp
0x14001e983  mov     [r11+10h], rbx
0x14001e987  mov     [r11+18h], rsi
0x14001e98b  push    rbp
0x14001e98c  push    rdi
0x14001e98d  push    r12
0x14001e98f  push    r14
0x14001e991  push    r15
0x14001e993  mov     rbp, rsp
0x14001e996  sub     rsp, 80h
0x14001e99d  mov     rax, cs:__security_cookie
0x14001e9a4  xor     rax, rsp
0x14001e9a7  mov     [rbp+var_8], rax
0x14001e9ab  xor     r12d, r12d
0x14001e9ae  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14001e9b4  lea     rax, [rbp+pSid]
0x14001e9b8  mov     dword ptr [rbp+IdentifierAuthority.Value], r12d
0x14001e9bc  mov     [r11-58h], rax
0x14001e9c0  mov     r14d, ecx
0x14001e9c3  mov     [r11-60h], r12d
0x14001e9c7  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14001e9cb  mov     [r11-68h], r12d
0x14001e9cf  lea     r8d, [r12+20h]; SubAuthority0
0x14001e9d4  mov     [r11-70h], r12d
0x14001e9d8  mov     r9d, 220h; SubAuthority1
0x14001e9de  mov     [r11-78h], r12d
0x14001e9e2  mov     dl, 2; SubAuthorityCount
0x14001e9e4  mov     [r11-80h], r12d
0x14001e9e8  mov     edi, r12d
0x14001e9eb  mov     [rsp+80h+SubAuthority2], r12d; SubAuthority2
0x14001e9f0  mov     [rbp+pSid], r12
0x14001e9f4  mov     [rbp+var_18], r12
0x14001e9f8  call    cs:__imp_RtlAllocateAndInitializeSid
0x14001e9fe  mov     ebx, eax
0x14001ea00  test    eax, eax
0x14001ea02  js      loc_14001EB9D
0x14001ea08  lea     rax, [rbp+var_18]
0x14001ea0c  xor     r9d, r9d; SubAuthority1
0x14001ea0f  mov     [rsp+80h+Sid], rax; Sid
0x14001ea14  lea     r8d, [r12+12h]; SubAuthority0
0x14001ea19  mov     [rsp+80h+SubAuthority7], r12d; SubAuthority7
0x14001ea1e  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14001ea22  mov     [rsp+80h+SubAuthority6], r12d; SubAuthority6
0x14001ea27  mov     dl, 1; SubAuthorityCount
0x14001ea29  mov     [rsp+80h+SubAuthority5], r12d; SubAuthority5
0x14001ea2e  mov     [rsp+80h+SubAuthority4], r12d; SubAuthority4
0x14001ea33  mov     [rsp+80h+SubAuthority3], r12d; SubAuthority3
0x14001ea38  mov     [rsp+80h+SubAuthority2], r12d; SubAuthority2
0x14001ea3d  call    cs:__imp_RtlAllocateAndInitializeSid
0x14001ea43  mov     ebx, eax
0x14001ea45  test    eax, eax
0x14001ea47  js      loc_14001EB9D
0x14001ea4d  mov     rcx, [rbp+var_18]; Sid
0x14001ea51  call    cs:__imp_RtlLengthSid
0x14001ea57  mov     rcx, [rbp+pSid]; Sid
0x14001ea5b  mov     ebx, eax
0x14001ea5d  call    cs:__imp_RtlLengthSid
0x14001ea63  mov     rcx, [rbp+pSid]; Sid
0x14001ea67  add     eax, 18h
0x14001ea6a  add     ebx, eax
0x14001ea6c  call    cs:__imp_RtlLengthSid
0x14001ea72  mov     rcx, gs:60h
0x14001ea7b  xor     edx, edx; Flags
0x14001ea7d  lea     r15d, [rax+28h]
0x14001ea81  mov     rcx, [rcx+30h]; HeapHandle
0x14001ea85  add     r15d, ebx
0x14001ea88  mov     r8d, r15d; Size
0x14001ea8b  call    cs:__imp_RtlAllocateHeap
0x14001ea91  mov     rdi, rax
0x14001ea94  test    rax, rax
0x14001ea97  jnz     short loc_14001EAA3
0x14001ea99  mov     ebx, 0C000009Ah
0x14001ea9e  jmp     loc_14001EB9D
0x14001eaa3  lea     rsi, [rax+28h]
0x14001eaa7  mov     r8d, 2; AclRevision
0x14001eaad  mov     rcx, rsi; Acl
0x14001eab0  mov     edx, ebx; AclSize
0x14001eab2  call    cs:__imp_RtlCreateAcl
0x14001eab8  mov     ebx, eax
0x14001eaba  test    eax, eax
0x14001eabc  js      loc_14001EB9D
0x14001eac2  mov     rax, [rbp+pSid]
0x14001eac6  xor     r8d, r8d; AceFlags
0x14001eac9  mov     r9d, r14d; AccessMask
0x14001eacc  mov     qword ptr [rsp+80h+SubAuthority2], rax; pSid
0x14001ead1  mov     rcx, rsi; pAcl
0x14001ead4  lea     edx, [r8+2]; dwAceRevision
0x14001ead8  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14001eade  mov     ebx, eax
0x14001eae0  test    eax, eax
0x14001eae2  js      loc_14001EB9D
0x14001eae8  mov     rax, [rbp+var_18]
0x14001eaec  xor     r8d, r8d; AceFlags
0x14001eaef  mov     r9d, 0F003Fh; AccessMask
0x14001eaf5  mov     qword ptr [rsp+80h+SubAuthority2], rax; pSid
0x14001eafa  mov     rcx, rsi; pAcl
0x14001eafd  lea     edx, [r8+2]; dwAceRevision
0x14001eb01  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14001eb07  mov     ebx, eax
0x14001eb09  test    eax, eax
0x14001eb0b  js      loc_14001EB9D
0x14001eb11  mov     edx, 1; Revision
0x14001eb16  mov     rcx, rdi; SecurityDescriptor
0x14001eb19  call    cs:__imp_RtlCreateSecurityDescriptor
0x14001eb1f  mov     ebx, eax
0x14001eb21  test    eax, eax
0x14001eb23  js      short loc_14001EB9D
0x14001eb25  xor     r9d, r9d; DaclDefaulted
0x14001eb28  mov     r8, rsi; Dacl
0x14001eb2b  mov     dl, 1; DaclPresent
0x14001eb2d  mov     rcx, rdi; SecurityDescriptor
0x14001eb30  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001eb36  mov     ebx, eax
0x14001eb38  test    eax, eax
0x14001eb3a  js      short loc_14001EB9D
0x14001eb3c  mov     rcx, rdi; SecurityDescriptor
0x14001eb3f  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001eb45  mov     rcx, [rbp+pSid]; Sid
0x14001eb49  mov     ebx, eax
0x14001eb4b  call    cs:__imp_RtlLengthSid
0x14001eb51  add     ebx, eax
0x14001eb53  cmp     ebx, r15d
0x14001eb56  jnb     short loc_14001EB5F
0x14001eb58  mov     ebx, 0C0000023h
0x14001eb5d  jmp     short loc_14001EB9D
0x14001eb5f  mov     rcx, rdi; SecurityDescriptor
0x14001eb62  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001eb68  mov     rcx, [rbp+pSid]; Sid
0x14001eb6c  mov     ebx, eax
0x14001eb6e  add     rbx, rdi
0x14001eb71  call    cs:__imp_RtlLengthSid
0x14001eb77  mov     rdx, [rbp+pSid]; Src
0x14001eb7b  mov     rcx, rbx; void *
0x14001eb7e  mov     r8d, eax; Size
0x14001eb81  call    memcpy_0
0x14001eb86  xor     r8d, r8d; OwnerDefaulted
0x14001eb89  mov     rdx, rbx; Owner
0x14001eb8c  mov     rcx, rdi; SecurityDescriptor
0x14001eb8f  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14001eb95  test    eax, eax
0x14001eb97  mov     ebx, eax
0x14001eb99  cmovns  ebx, r12d
0x14001eb9d  mov     rcx, [rbp+pSid]; Sid
0x14001eba1  test    rcx, rcx
0x14001eba4  jz      short loc_14001EBAC
0x14001eba6  call    cs:__imp_RtlFreeSid
0x14001ebac  mov     rcx, [rbp+var_18]; Sid
0x14001ebb0  test    rcx, rcx
0x14001ebb3  jz      short loc_14001EBBB
0x14001ebb5  call    cs:__imp_RtlFreeSid
0x14001ebbb  test    ebx, ebx
0x14001ebbd  js      short loc_14001EBC4
0x14001ebbf  mov     rax, rdi
0x14001ebc2  jmp     short loc_14001EBE3
0x14001ebc4  test    rdi, rdi
0x14001ebc7  jz      short loc_14001EBE1
0x14001ebc9  mov     rcx, gs:60h
0x14001ebd2  mov     r8, rdi; P
0x14001ebd5  xor     edx, edx; Flags
0x14001ebd7  mov     rcx, [rcx+30h]; HeapHandle
0x14001ebdb  call    cs:__imp_RtlFreeHeap
0x14001ebe1  xor     eax, eax
0x14001ebe3  mov     rcx, [rbp+var_8]
0x14001ebe7  xor     rcx, rsp; StackCookie
0x14001ebea  call    __security_check_cookie
0x14001ebef  lea     r11, [rsp+80h+var_s0]
0x14001ebf7  mov     rbx, [r11+38h]
0x14001ebfb  mov     rsi, [r11+40h]
0x14001ebff  mov     rsp, r11
0x14001ec02  pop     r15
0x14001ec04  pop     r14
0x14001ec06  pop     r12
0x14001ec08  pop     rdi
0x14001ec09  pop     rbp
0x14001ec0a  retn
```
