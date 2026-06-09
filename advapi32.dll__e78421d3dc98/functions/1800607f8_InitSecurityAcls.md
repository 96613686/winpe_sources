# InitSecurityAcls

- ea: `0x1800607f8`
- end: `0x1800609d1`
- name: `InitSecurityAcls`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800609d8`

## callees

- `0x1800607f8`
- `0x180065090`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800608cd`
- `ntdll!RtlLengthSid` at `0x1800608d9`
- `ntdll!RtlLengthSid` at `0x1800608cd`
- `ntdll!RtlLengthSid` at `0x1800608d9`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006096e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006096e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180060872`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800608b9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180060872`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800608b9`
- `ntdll!RtlFreeSid` at `0x180060996`
- `ntdll!RtlFreeSid` at `0x1800609a5`
- `ntdll!RtlFreeSid` at `0x180060996`
- `ntdll!RtlFreeSid` at `0x1800609a5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180060985`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180060985`
- `ntdll!RtlCreateAcl` at `0x18006091e`
- `ntdll!RtlCreateAcl` at `0x18006091e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006093c`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006095a`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006093c`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006095a`
- `ntdll!RtlAllocateHeap` at `0x1800608fa`
- `ntdll!RtlAllocateHeap` at `0x1800608fa`

## pseudocode

```c
__int64 __fastcall InitSecurityAcls(PSECURITY_DESCRIPTOR *a1)
{
  NTSTATUS Acl; // ebx
  ULONG v3; // ebx
  ULONG v4; // ebx
  ACL *Heap; // rax
  ACL *v6; // rdi
  PSID Sid; // [rsp+68h] [rbp+17h] BYREF
  PSID v9; // [rsp+70h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp+27h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+80h] [rbp+2Fh] BYREF

  *(_WORD *)&v11.Value[4] = 1280;
  *a1 = 0;
  *(_DWORD *)v11.Value = 0;
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
0x1800607f8  mov     r11, rsp
0x1800607fb  mov     [r11+10h], rbx
0x1800607ff  mov     [r11+18h], rsi
0x180060803  push    rbp
0x180060804  push    rdi
0x180060805  push    r14
0x180060807  lea     rbp, [r11-5Fh]
0x18006080b  sub     rsp, 90h
0x180060812  mov     rax, cs:__security_cookie
0x180060819  xor     rax, rsp
0x18006081c  mov     [rbp+57h+var_20], rax
0x180060820  xor     r14d, r14d
0x180060823  mov     word ptr [rbp+57h+var_28.Value+4], 500h
0x180060829  lea     rax, [rbp+57h+var_40]
0x18006082d  mov     [rcx], r14
0x180060830  mov     [r11-58h], rax
0x180060834  mov     rsi, rcx
0x180060837  mov     [r11-60h], r14d
0x18006083b  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18006083f  mov     [r11-68h], r14d
0x180060843  xor     r9d, r9d; SubAuthority1
0x180060846  mov     [r11-70h], r14d
0x18006084a  xor     r8d, r8d; SubAuthority0
0x18006084d  mov     [r11-78h], r14d
0x180060851  mov     dl, 1; SubAuthorityCount
0x180060853  mov     [r11-80h], r14d
0x180060857  mov     [rsp+0A0h+SubAuthority2], r14d; SubAuthority2
0x18006085c  mov     dword ptr [rbp+57h+var_28.Value], r14d
0x180060860  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x180060864  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 100h
0x18006086a  mov     [rbp+57h+var_38], r14
0x18006086e  mov     [rbp+57h+var_40], r14
0x180060872  call    cs:__imp_RtlAllocateAndInitializeSid
0x180060878  mov     ebx, eax
0x18006087a  test    eax, eax
0x18006087c  js      loc_18006098D
0x180060882  lea     rax, [rbp+57h+var_38]
0x180060886  mov     r9d, 220h; SubAuthority1
0x18006088c  mov     [rsp+0A0h+Sid], rax; Sid
0x180060891  lea     r8d, [r14+20h]; SubAuthority0
0x180060895  mov     [rsp+0A0h+SubAuthority7], r14d; SubAuthority7
0x18006089a  lea     rcx, [rbp+57h+var_28]; IdentifierAuthority
0x18006089e  mov     [rsp+0A0h+SubAuthority6], r14d; SubAuthority6
0x1800608a3  mov     dl, 2; SubAuthorityCount
0x1800608a5  mov     [rsp+0A0h+SubAuthority5], r14d; SubAuthority5
0x1800608aa  mov     [rsp+0A0h+SubAuthority4], r14d; SubAuthority4
0x1800608af  mov     [rsp+0A0h+SubAuthority3], r14d; SubAuthority3
0x1800608b4  mov     [rsp+0A0h+SubAuthority2], r14d; SubAuthority2
0x1800608b9  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800608bf  mov     ebx, eax
0x1800608c1  test    eax, eax
0x1800608c3  js      loc_18006098D
0x1800608c9  mov     rcx, [rbp+57h+var_40]; Sid
0x1800608cd  call    cs:__imp_RtlLengthSid
0x1800608d3  mov     rcx, [rbp+57h+var_38]; Sid
0x1800608d7  mov     ebx, eax
0x1800608d9  call    cs:__imp_RtlLengthSid
0x1800608df  mov     rcx, gs:60h
0x1800608e8  xor     edx, edx; Flags
0x1800608ea  add     eax, 18h
0x1800608ed  add     ebx, eax
0x1800608ef  mov     r8d, ebx
0x1800608f2  mov     rcx, [rcx+30h]; HeapHandle
0x1800608f6  add     r8, 28h ; '('; Size
0x1800608fa  call    cs:__imp_RtlAllocateHeap
0x180060900  mov     [rsi], rax
0x180060903  test    rax, rax
0x180060906  jnz     short loc_18006090F
0x180060908  mov     ebx, 0C000009Ah
0x18006090d  jmp     short loc_18006098D
0x18006090f  lea     rdi, [rax+28h]
0x180060913  mov     r8d, 2; AclRevision
0x180060919  mov     rcx, rdi; Acl
0x18006091c  mov     edx, ebx; AclSize
0x18006091e  call    cs:__imp_RtlCreateAcl
0x180060924  mov     ebx, eax
0x180060926  test    eax, eax
0x180060928  js      short loc_18006098D
0x18006092a  mov     r9, [rbp+57h+var_40]; Sid
0x18006092e  mov     edx, 2; Revision
0x180060933  mov     r8d, 3003Fh; AccessMask
0x180060939  mov     rcx, rdi; Acl
0x18006093c  call    cs:__imp_RtlAddAccessAllowedAce
0x180060942  mov     ebx, eax
0x180060944  test    eax, eax
0x180060946  js      short loc_18006098D
0x180060948  mov     r9, [rbp+57h+var_38]; Sid
0x18006094c  mov     edx, 2; Revision
0x180060951  mov     r8d, 10000000h; AccessMask
0x180060957  mov     rcx, rdi; Acl
0x18006095a  call    cs:__imp_RtlAddAccessAllowedAce
0x180060960  mov     ebx, eax
0x180060962  test    eax, eax
0x180060964  js      short loc_18006098D
0x180060966  mov     rcx, [rsi]; SecurityDescriptor
0x180060969  mov     edx, 1; Revision
0x18006096e  call    cs:__imp_RtlCreateSecurityDescriptor
0x180060974  mov     ebx, eax
0x180060976  test    eax, eax
0x180060978  js      short loc_18006098D
0x18006097a  mov     rcx, [rsi]; SecurityDescriptor
0x18006097d  xor     r9d, r9d; DaclDefaulted
0x180060980  mov     r8, rdi; Dacl
0x180060983  mov     dl, 1; DaclPresent
0x180060985  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006098b  mov     ebx, eax
0x18006098d  mov     rcx, [rbp+57h+var_40]; Sid
0x180060991  test    rcx, rcx
0x180060994  jz      short loc_18006099C
0x180060996  call    cs:__imp_RtlFreeSid
0x18006099c  mov     rcx, [rbp+57h+var_38]; Sid
0x1800609a0  test    rcx, rcx
0x1800609a3  jz      short loc_1800609AB
0x1800609a5  call    cs:__imp_RtlFreeSid
0x1800609ab  mov     eax, ebx
0x1800609ad  mov     rcx, [rbp+57h+var_20]
0x1800609b1  xor     rcx, rsp; StackCookie
0x1800609b4  call    __security_check_cookie
0x1800609b9  lea     r11, [rsp+0A0h+var_10]
0x1800609c1  mov     rbx, [r11+28h]
0x1800609c5  mov     rsi, [r11+30h]
0x1800609c9  mov     rsp, r11
0x1800609cc  pop     r14
0x1800609ce  pop     rdi
0x1800609cf  pop     rbp
0x1800609d0  retn
```
