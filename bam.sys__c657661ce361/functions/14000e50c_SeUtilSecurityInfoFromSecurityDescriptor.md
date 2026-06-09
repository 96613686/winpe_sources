# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14000e50c`
- end: `0x14000e605`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d434`
- `0x14000e03c`

## callees

- `0x14000e50c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000e5a6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000e5a6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000e552`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000e552`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000e57d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000e57d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000e5ce`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000e5ce`

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
0x14000e50c  mov     [rsp-18h+arg_0], rbx
0x14000e511  mov     [rsp-18h+arg_10], rsi
0x14000e516  push    rbp
0x14000e517  push    rdi
0x14000e518  push    r14
0x14000e51a  mov     rbp, rsp
0x14000e51d  sub     rsp, 30h
0x14000e521  xor     eax, eax
0x14000e523  mov     byte ptr [rdx], 0
0x14000e526  mov     [r8], eax
0x14000e529  mov     rsi, r8
0x14000e52c  mov     r14, rdx
0x14000e52f  mov     [rbp+OwnerDefaulted], 0
0x14000e533  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x14000e537  mov     [rbp+SaclPresent], 0
0x14000e53b  lea     rdx, [rbp+Owner]; Owner
0x14000e53f  mov     [rbp+Owner], 0
0x14000e547  mov     rdi, rcx
0x14000e54a  mov     [rbp+Sacl], 0
0x14000e552  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14000e559  nop     dword ptr [rax+rax+00h]
0x14000e55e  test    eax, eax
0x14000e560  js      loc_14000E5F1
0x14000e566  xor     ebx, ebx
0x14000e568  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14000e56c  cmp     [rbp+Owner], rbx
0x14000e570  lea     rdx, [rbp+Owner]; Group
0x14000e574  mov     rcx, rdi; SecurityDescriptor
0x14000e577  lea     eax, [rbx+1]
0x14000e57a  cmovnz  ebx, eax
0x14000e57d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14000e584  nop     dword ptr [rax+rax+00h]
0x14000e589  test    eax, eax
0x14000e58b  js      short loc_14000E5F1
0x14000e58d  cmp     [rbp+Owner], 0
0x14000e592  jz      short loc_14000E597
0x14000e594  or      ebx, 2
0x14000e597  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14000e59b  mov     rcx, rdi; SecurityDescriptor
0x14000e59e  lea     r8, [rbp+Sacl]; Sacl
0x14000e5a2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x14000e5a6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14000e5ad  nop     dword ptr [rax+rax+00h]
0x14000e5b2  test    eax, eax
0x14000e5b4  js      short loc_14000E5F1
0x14000e5b6  cmp     [rbp+SaclPresent], 0
0x14000e5ba  jz      short loc_14000E5BF
0x14000e5bc  or      ebx, 8
0x14000e5bf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x14000e5c3  mov     rcx, rdi; SecurityDescriptor
0x14000e5c6  lea     r8, [rbp+Sacl]; Dacl
0x14000e5ca  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14000e5ce  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000e5d5  nop     dword ptr [rax+rax+00h]
0x14000e5da  test    eax, eax
0x14000e5dc  js      short loc_14000E5F1
0x14000e5de  cmp     [rbp+SaclPresent], 0
0x14000e5e2  jz      short loc_14000E5E7
0x14000e5e4  or      ebx, 4
0x14000e5e7  mov     al, [rbp+OwnerDefaulted]
0x14000e5ea  mov     [r14], al
0x14000e5ed  xor     eax, eax
0x14000e5ef  mov     [rsi], ebx
0x14000e5f1  mov     rbx, [rsp+30h+arg_0]
0x14000e5f6  mov     rsi, [rsp+30h+arg_10]
0x14000e5fb  add     rsp, 30h
0x14000e5ff  pop     r14
0x14000e601  pop     rdi
0x14000e602  pop     rbp
0x14000e603  retn
```
