# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x18002c40c`
- end: `0x18002c505`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `NTSTATUS __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, unsigned __int8 *, _DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b324`
- `0x18002bf3c`

## callees

- `0x18002c40c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x18002c4a6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x18002c4a6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x18002c452`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x18002c452`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x18002c47d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x18002c47d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x18002c4ce`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x18002c4ce`

## pseudocode

```c
NTSTATUS __fastcall SeUtilSecurityInfoFromSecurityDescriptor(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        unsigned __int8 *a2,
        _DWORD *a3)
{
  NTSTATUS result; // eax
  int v7; // ebx
  PSID Owner; // [rsp+20h] [rbp-10h] BYREF
  PACL Sacl; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int8 SaclPresent; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  *a3 = 0;
  OwnerDefaulted = 0;
  SaclPresent = 0;
  Owner = 0;
  Sacl = 0;
  result = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  if ( result >= 0 )
  {
    v7 = Owner != 0;
    result = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
    if ( result >= 0 )
    {
      if ( Owner )
        v7 |= 2u;
      result = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &OwnerDefaulted);
      if ( result >= 0 )
      {
        if ( SaclPresent )
          v7 |= 8u;
        result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &OwnerDefaulted);
        if ( result >= 0 )
        {
          if ( SaclPresent )
            v7 |= 4u;
          *a2 = OwnerDefaulted;
          result = 0;
          *a3 = v7;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c40c  mov     [rsp-18h+arg_0], rbx
0x18002c411  mov     [rsp-18h+arg_10], rsi
0x18002c416  push    rbp
0x18002c417  push    rdi
0x18002c418  push    r14
0x18002c41a  mov     rbp, rsp
0x18002c41d  sub     rsp, 30h
0x18002c421  xor     eax, eax
0x18002c423  mov     byte ptr [rdx], 0
0x18002c426  mov     [r8], eax
0x18002c429  mov     rsi, r8
0x18002c42c  mov     r14, rdx
0x18002c42f  mov     [rbp+OwnerDefaulted], 0
0x18002c433  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x18002c437  mov     [rbp+SaclPresent], 0
0x18002c43b  lea     rdx, [rbp+Owner]; Owner
0x18002c43f  mov     [rbp+Owner], 0
0x18002c447  mov     rdi, rcx
0x18002c44a  mov     [rbp+Sacl], 0
0x18002c452  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18002c459  nop     dword ptr [rax+rax+00h]
0x18002c45e  test    eax, eax
0x18002c460  js      loc_18002C4F1
0x18002c466  xor     ebx, ebx
0x18002c468  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x18002c46c  cmp     [rbp+Owner], rbx
0x18002c470  lea     rdx, [rbp+Owner]; Group
0x18002c474  mov     rcx, rdi; SecurityDescriptor
0x18002c477  lea     eax, [rbx+1]
0x18002c47a  cmovnz  ebx, eax
0x18002c47d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18002c484  nop     dword ptr [rax+rax+00h]
0x18002c489  test    eax, eax
0x18002c48b  js      short loc_18002C4F1
0x18002c48d  cmp     [rbp+Owner], 0
0x18002c492  jz      short loc_18002C497
0x18002c494  or      ebx, 2
0x18002c497  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x18002c49b  mov     rcx, rdi; SecurityDescriptor
0x18002c49e  lea     r8, [rbp+Sacl]; Sacl
0x18002c4a2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x18002c4a6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x18002c4ad  nop     dword ptr [rax+rax+00h]
0x18002c4b2  test    eax, eax
0x18002c4b4  js      short loc_18002C4F1
0x18002c4b6  cmp     [rbp+SaclPresent], 0
0x18002c4ba  jz      short loc_18002C4BF
0x18002c4bc  or      ebx, 8
0x18002c4bf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x18002c4c3  mov     rcx, rdi; SecurityDescriptor
0x18002c4c6  lea     r8, [rbp+Sacl]; Dacl
0x18002c4ca  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x18002c4ce  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18002c4d5  nop     dword ptr [rax+rax+00h]
0x18002c4da  test    eax, eax
0x18002c4dc  js      short loc_18002C4F1
0x18002c4de  cmp     [rbp+SaclPresent], 0
0x18002c4e2  jz      short loc_18002C4E7
0x18002c4e4  or      ebx, 4
0x18002c4e7  mov     al, [rbp+OwnerDefaulted]
0x18002c4ea  mov     [r14], al
0x18002c4ed  xor     eax, eax
0x18002c4ef  mov     [rsi], ebx
0x18002c4f1  mov     rbx, [rsp+30h+arg_0]
0x18002c4f6  mov     rsi, [rsp+30h+arg_10]
0x18002c4fb  add     rsp, 30h
0x18002c4ff  pop     r14
0x18002c501  pop     rdi
0x18002c502  pop     rbp
0x18002c503  retn
```
