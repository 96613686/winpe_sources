# InitSecurityAcls

- ea: `0x18006d1c4`
- end: `0x18006d3e9`
- name: `InitSecurityAcls`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006d3f0`

## callees

- `0x18006d1c4`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18006d2a5`
- `ntdll!RtlLengthSid` at `0x18006d2b7`
- `ntdll!RtlLengthSid` at `0x18006d2a5`
- `ntdll!RtlLengthSid` at `0x18006d2b7`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006d36d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006d36d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d23e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d28b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d23e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d28b`
- `ntdll!RtlFreeSid` at `0x18006d3a1`
- `ntdll!RtlFreeSid` at `0x18006d3b6`
- `ntdll!RtlFreeSid` at `0x18006d3a1`
- `ntdll!RtlFreeSid` at `0x18006d3b6`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006d38a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006d38a`
- `ntdll!RtlCreateAcl` at `0x18006d30b`
- `ntdll!RtlCreateAcl` at `0x18006d30b`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d32f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d353`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d32f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d353`
- `ntdll!RtlAllocateHeap` at `0x18006d2de`
- `ntdll!RtlAllocateHeap` at `0x18006d2de`

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
0x18006d1c4  mov     r11, rsp
0x18006d1c7  mov     [r11+10h], rbx
0x18006d1cb  mov     [r11+18h], rsi
0x18006d1cf  push    rbp
0x18006d1d0  push    rdi
0x18006d1d1  push    r14
0x18006d1d3  lea     rbp, [r11-5Fh]
0x18006d1d7  sub     rsp, 90h
0x18006d1de  mov     rax, cs:__security_cookie
0x18006d1e5  xor     rax, rsp
0x18006d1e8  mov     [rbp+57h+var_20], rax
0x18006d1ec  xor     r14d, r14d
0x18006d1ef  mov     word ptr [rbp+57h+var_28.Value+4], 500h
0x18006d1f5  lea     rax, [rbp+57h+var_40]
0x18006d1f9  mov     [rcx], r14
0x18006d1fc  mov     [r11-58h], rax
0x18006d200  mov     rsi, rcx
0x18006d203  mov     [r11-60h], r14d
0x18006d207  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18006d20b  mov     [r11-68h], r14d
0x18006d20f  xor     r9d, r9d; SubAuthority1
0x18006d212  mov     [r11-70h], r14d
0x18006d216  xor     r8d, r8d; SubAuthority0
0x18006d219  mov     [r11-78h], r14d
0x18006d21d  mov     dl, 1; SubAuthorityCount
0x18006d21f  mov     [r11-80h], r14d
0x18006d223  mov     [rsp+0A0h+SubAuthority2], r14d; SubAuthority2
0x18006d228  mov     dword ptr [rbp+57h+var_28.Value], r14d
0x18006d22c  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x18006d230  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 100h
0x18006d236  mov     [rbp+57h+var_38], r14
0x18006d23a  mov     [rbp+57h+var_40], r14
0x18006d23e  call    cs:__imp_RtlAllocateAndInitializeSid
0x18006d245  nop     dword ptr [rax+rax+00h]
0x18006d24a  mov     ebx, eax
0x18006d24c  test    eax, eax
0x18006d24e  js      loc_18006D398
0x18006d254  lea     rax, [rbp+57h+var_38]
0x18006d258  mov     r9d, 220h; SubAuthority1
0x18006d25e  mov     [rsp+0A0h+Sid], rax; Sid
0x18006d263  lea     r8d, [r14+20h]; SubAuthority0
0x18006d267  mov     [rsp+0A0h+SubAuthority7], r14d; SubAuthority7
0x18006d26c  lea     rcx, [rbp+57h+var_28]; IdentifierAuthority
0x18006d270  mov     [rsp+0A0h+SubAuthority6], r14d; SubAuthority6
0x18006d275  mov     dl, 2; SubAuthorityCount
0x18006d277  mov     [rsp+0A0h+SubAuthority5], r14d; SubAuthority5
0x18006d27c  mov     [rsp+0A0h+SubAuthority4], r14d; SubAuthority4
0x18006d281  mov     [rsp+0A0h+SubAuthority3], r14d; SubAuthority3
0x18006d286  mov     [rsp+0A0h+SubAuthority2], r14d; SubAuthority2
0x18006d28b  call    cs:__imp_RtlAllocateAndInitializeSid
0x18006d292  nop     dword ptr [rax+rax+00h]
0x18006d297  mov     ebx, eax
0x18006d299  test    eax, eax
0x18006d29b  js      loc_18006D398
0x18006d2a1  mov     rcx, [rbp+57h+var_40]; Sid
0x18006d2a5  call    cs:__imp_RtlLengthSid
0x18006d2ac  nop     dword ptr [rax+rax+00h]
0x18006d2b1  mov     rcx, [rbp+57h+var_38]; Sid
0x18006d2b5  mov     ebx, eax
0x18006d2b7  call    cs:__imp_RtlLengthSid
0x18006d2be  nop     dword ptr [rax+rax+00h]
0x18006d2c3  mov     rcx, gs:60h
0x18006d2cc  xor     edx, edx; Flags
0x18006d2ce  add     eax, 18h
0x18006d2d1  add     ebx, eax
0x18006d2d3  mov     r8d, ebx
0x18006d2d6  mov     rcx, [rcx+30h]; HeapHandle
0x18006d2da  add     r8, 28h ; '('; Size
0x18006d2de  call    cs:__imp_RtlAllocateHeap
0x18006d2e5  nop     dword ptr [rax+rax+00h]
0x18006d2ea  mov     [rsi], rax
0x18006d2ed  test    rax, rax
0x18006d2f0  jnz     short loc_18006D2FC
0x18006d2f2  mov     ebx, 0C000009Ah
0x18006d2f7  jmp     loc_18006D398
0x18006d2fc  lea     rdi, [rax+28h]
0x18006d300  mov     r8d, 2; AclRevision
0x18006d306  mov     rcx, rdi; Acl
0x18006d309  mov     edx, ebx; AclSize
0x18006d30b  call    cs:__imp_RtlCreateAcl
0x18006d312  nop     dword ptr [rax+rax+00h]
0x18006d317  mov     ebx, eax
0x18006d319  test    eax, eax
0x18006d31b  js      short loc_18006D398
0x18006d31d  mov     r9, [rbp+57h+var_40]; Sid
0x18006d321  mov     edx, 2; Revision
0x18006d326  mov     r8d, 3003Fh; AccessMask
0x18006d32c  mov     rcx, rdi; Acl
0x18006d32f  call    cs:__imp_RtlAddAccessAllowedAce
0x18006d336  nop     dword ptr [rax+rax+00h]
0x18006d33b  mov     ebx, eax
0x18006d33d  test    eax, eax
0x18006d33f  js      short loc_18006D398
0x18006d341  mov     r9, [rbp+57h+var_38]; Sid
0x18006d345  mov     edx, 2; Revision
0x18006d34a  mov     r8d, 10000000h; AccessMask
0x18006d350  mov     rcx, rdi; Acl
0x18006d353  call    cs:__imp_RtlAddAccessAllowedAce
0x18006d35a  nop     dword ptr [rax+rax+00h]
0x18006d35f  mov     ebx, eax
0x18006d361  test    eax, eax
0x18006d363  js      short loc_18006D398
0x18006d365  mov     rcx, [rsi]; SecurityDescriptor
0x18006d368  mov     edx, 1; Revision
0x18006d36d  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006d374  nop     dword ptr [rax+rax+00h]
0x18006d379  mov     ebx, eax
0x18006d37b  test    eax, eax
0x18006d37d  js      short loc_18006D398
0x18006d37f  mov     rcx, [rsi]; SecurityDescriptor
0x18006d382  xor     r9d, r9d; DaclDefaulted
0x18006d385  mov     r8, rdi; Dacl
0x18006d388  mov     dl, 1; DaclPresent
0x18006d38a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006d391  nop     dword ptr [rax+rax+00h]
0x18006d396  mov     ebx, eax
0x18006d398  mov     rcx, [rbp+57h+var_40]; Sid
0x18006d39c  test    rcx, rcx
0x18006d39f  jz      short loc_18006D3AD
0x18006d3a1  call    cs:__imp_RtlFreeSid
0x18006d3a8  nop     dword ptr [rax+rax+00h]
0x18006d3ad  mov     rcx, [rbp+57h+var_38]; Sid
0x18006d3b1  test    rcx, rcx
0x18006d3b4  jz      short loc_18006D3C2
0x18006d3b6  call    cs:__imp_RtlFreeSid
0x18006d3bd  nop     dword ptr [rax+rax+00h]
0x18006d3c2  mov     eax, ebx
0x18006d3c4  mov     rcx, [rbp+57h+var_20]
0x18006d3c8  xor     rcx, rsp; StackCookie
0x18006d3cb  call    __security_check_cookie
0x18006d3d0  lea     r11, [rsp+0A0h+var_10]
0x18006d3d8  mov     rbx, [r11+28h]
0x18006d3dc  mov     rsi, [r11+30h]
0x18006d3e0  mov     rsp, r11
0x18006d3e3  pop     r14
0x18006d3e5  pop     rdi
0x18006d3e6  pop     rbp
0x18006d3e7  retn
```
