# InitSecurityAcls

- ea: `0x1800c93b0`
- end: `0x1800c9579`
- name: `InitSecurityAcls`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c9130`
- `0x1800c9270`

## callees

- `0x1800c93b0`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800c9543`
- `ntdll!RtlFreeSid` at `0x1800c9552`
- `ntdll!RtlFreeSid` at `0x1800c9543`
- `ntdll!RtlFreeSid` at `0x1800c9552`
- `ntdll!RtlCreateAcl` at `0x1800c94cb`
- `ntdll!RtlCreateAcl` at `0x1800c94cb`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800c951b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800c951b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800c9532`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800c9532`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800c9426`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800c9469`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800c9426`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800c9469`
- `ntdll!RtlLengthSid` at `0x1800c947d`
- `ntdll!RtlLengthSid` at `0x1800c9489`
- `ntdll!RtlLengthSid` at `0x1800c947d`
- `ntdll!RtlLengthSid` at `0x1800c9489`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800c94e9`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800c9507`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800c94e9`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800c9507`
- `ntdll!RtlAllocateHeap` at `0x1800c94aa`
- `ntdll!RtlAllocateHeap` at `0x1800c94aa`

## pseudocode

```c
__int64 __fastcall InitSecurityAcls(PSECURITY_DESCRIPTOR *a1)
{
  NTSTATUS Acl; // ebx
  ULONG v3; // ebx
  ULONG v4; // ebx
  ACL *Heap; // rax
  ACL *v6; // rdi
  PSID Sid; // [rsp+60h] [rbp+7h] BYREF
  PSID v9; // [rsp+68h] [rbp+Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+78h] [rbp+1Fh] BYREF

  *(_DWORD *)v11.Value = 0;
  *a1 = 0;
  *(_WORD *)&v11.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  v9 = 0;
  Sid = 0;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( Acl >= 0 )
  {
    Acl = RtlAllocateAndInitializeSid(&v11, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v9);
    if ( Acl >= 0 )
    {
      v3 = RtlLengthSid(Sid);
      v4 = RtlLengthSid(v9) + 24 + v3;
      Heap = (ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4 + 40LL);
      *a1 = Heap;
      if ( Heap )
      {
        v6 = Heap + 5;
        Acl = RtlCreateAcl(Heap + 5, v4, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v6, 2u, 0x3003Fu, Sid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, v9);
            if ( Acl >= 0 )
            {
              Acl = RtlCreateSecurityDescriptor(*a1, 1u);
              if ( Acl >= 0 )
                Acl = RtlSetDaclSecurityDescriptor(*a1, 1u, v6, 0);
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
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v9 )
    RtlFreeSid(v9);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1800c93b0  push    rbp
0x1800c93b2  push    rbx
0x1800c93b3  push    rsi
0x1800c93b4  push    rdi
0x1800c93b5  lea     rbp, [rsp-3Fh]
0x1800c93ba  sub     rsp, 98h
0x1800c93c1  mov     rax, cs:__security_cookie
0x1800c93c8  xor     rax, rsp
0x1800c93cb  mov     [rbp+57h+var_30], rax
0x1800c93cf  xor     edi, edi
0x1800c93d1  mov     dword ptr [rbp+57h+var_38.Value], 0
0x1800c93d8  lea     rax, [rbp+57h+var_50]
0x1800c93dc  mov     [rcx], rdi
0x1800c93df  mov     [rsp+0B0h+Sid], rax; Sid
0x1800c93e4  mov     rsi, rcx
0x1800c93e7  mov     [rsp+0B0h+SubAuthority7], edi; SubAuthority7
0x1800c93eb  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800c93ef  mov     [rsp+0B0h+SubAuthority6], edi; SubAuthority6
0x1800c93f3  xor     r9d, r9d; SubAuthority1
0x1800c93f6  mov     [rsp+0B0h+SubAuthority5], edi; SubAuthority5
0x1800c93fa  xor     r8d, r8d; SubAuthority0
0x1800c93fd  mov     [rsp+0B0h+SubAuthority4], edi; SubAuthority4
0x1800c9401  mov     dl, 1; SubAuthorityCount
0x1800c9403  mov     [rsp+0B0h+SubAuthority3], edi; SubAuthority3
0x1800c9407  mov     [rsp+0B0h+SubAuthority2], edi; SubAuthority2
0x1800c940b  mov     word ptr [rbp+57h+var_38.Value+4], 500h
0x1800c9411  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x1800c9418  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 100h
0x1800c941e  mov     [rbp+57h+var_48], rdi
0x1800c9422  mov     [rbp+57h+var_50], rdi
0x1800c9426  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800c942c  mov     ebx, eax
0x1800c942e  test    eax, eax
0x1800c9430  js      loc_1800C953A
0x1800c9436  lea     rax, [rbp+57h+var_48]
0x1800c943a  mov     r9d, 220h; SubAuthority1
0x1800c9440  mov     [rsp+0B0h+Sid], rax; Sid
0x1800c9445  lea     rcx, [rbp+57h+var_38]; IdentifierAuthority
0x1800c9449  mov     [rsp+0B0h+SubAuthority7], edi; SubAuthority7
0x1800c944d  mov     r8d, 20h ; ' '; SubAuthority0
0x1800c9453  mov     [rsp+0B0h+SubAuthority6], edi; SubAuthority6
0x1800c9457  mov     dl, 2; SubAuthorityCount
0x1800c9459  mov     [rsp+0B0h+SubAuthority5], edi; SubAuthority5
0x1800c945d  mov     [rsp+0B0h+SubAuthority4], edi; SubAuthority4
0x1800c9461  mov     [rsp+0B0h+SubAuthority3], edi; SubAuthority3
0x1800c9465  mov     [rsp+0B0h+SubAuthority2], edi; SubAuthority2
0x1800c9469  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800c946f  mov     ebx, eax
0x1800c9471  test    eax, eax
0x1800c9473  js      loc_1800C953A
0x1800c9479  mov     rcx, [rbp+57h+var_50]; Sid
0x1800c947d  call    cs:__imp_RtlLengthSid
0x1800c9483  mov     rcx, [rbp+57h+var_48]; Sid
0x1800c9487  mov     ebx, eax
0x1800c9489  call    cs:__imp_RtlLengthSid
0x1800c948f  mov     rcx, gs:60h
0x1800c9498  xor     edx, edx; Flags
0x1800c949a  add     eax, 18h
0x1800c949d  add     ebx, eax
0x1800c949f  mov     r8d, ebx
0x1800c94a2  mov     rcx, [rcx+30h]; HeapHandle
0x1800c94a6  add     r8, 28h ; '('; Size
0x1800c94aa  call    cs:__imp_RtlAllocateHeap
0x1800c94b0  mov     [rsi], rax
0x1800c94b3  test    rax, rax
0x1800c94b6  jz      loc_1800C9572
0x1800c94bc  lea     rdi, [rax+28h]
0x1800c94c0  mov     r8d, 2; AclRevision
0x1800c94c6  mov     rcx, rdi; Acl
0x1800c94c9  mov     edx, ebx; AclSize
0x1800c94cb  call    cs:__imp_RtlCreateAcl
0x1800c94d1  mov     ebx, eax
0x1800c94d3  test    eax, eax
0x1800c94d5  js      short loc_1800C953A
0x1800c94d7  mov     r9, [rbp+57h+var_50]; Sid
0x1800c94db  mov     edx, 2; Revision
0x1800c94e0  mov     r8d, 3003Fh; AccessMask
0x1800c94e6  mov     rcx, rdi; Acl
0x1800c94e9  call    cs:__imp_RtlAddAccessAllowedAce
0x1800c94ef  mov     ebx, eax
0x1800c94f1  test    eax, eax
0x1800c94f3  js      short loc_1800C953A
0x1800c94f5  mov     r9, [rbp+57h+var_48]; Sid
0x1800c94f9  mov     edx, 2; Revision
0x1800c94fe  mov     r8d, 10000000h; AccessMask
0x1800c9504  mov     rcx, rdi; Acl
0x1800c9507  call    cs:__imp_RtlAddAccessAllowedAce
0x1800c950d  mov     ebx, eax
0x1800c950f  test    eax, eax
0x1800c9511  js      short loc_1800C953A
0x1800c9513  mov     rcx, [rsi]; SecurityDescriptor
0x1800c9516  mov     edx, 1; Revision
0x1800c951b  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800c9521  mov     ebx, eax
0x1800c9523  test    eax, eax
0x1800c9525  js      short loc_1800C953A
0x1800c9527  mov     rcx, [rsi]; SecurityDescriptor
0x1800c952a  xor     r9d, r9d; DaclDefaulted
0x1800c952d  mov     r8, rdi; Dacl
0x1800c9530  mov     dl, 1; DaclPresent
0x1800c9532  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800c9538  mov     ebx, eax
0x1800c953a  mov     rcx, [rbp+57h+var_50]; Sid
0x1800c953e  test    rcx, rcx
0x1800c9541  jz      short loc_1800C9549
0x1800c9543  call    cs:__imp_RtlFreeSid
0x1800c9549  mov     rcx, [rbp+57h+var_48]; Sid
0x1800c954d  test    rcx, rcx
0x1800c9550  jz      short loc_1800C9558
0x1800c9552  call    cs:__imp_RtlFreeSid
0x1800c9558  mov     eax, ebx
0x1800c955a  mov     rcx, [rbp+57h+var_30]
0x1800c955e  xor     rcx, rsp; StackCookie
0x1800c9561  call    __security_check_cookie
0x1800c9566  add     rsp, 98h
0x1800c956d  pop     rdi
0x1800c956e  pop     rsi
0x1800c956f  pop     rbx
0x1800c9570  pop     rbp
0x1800c9571  retn
0x1800c9572  mov     ebx, 0C000009Ah
0x1800c9577  jmp     short loc_1800C953A
```
