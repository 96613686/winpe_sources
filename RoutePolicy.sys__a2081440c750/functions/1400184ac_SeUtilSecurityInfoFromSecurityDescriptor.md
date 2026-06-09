# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x1400184ac`
- end: `0x1400185a5`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400173c4`
- `0x140017fdc`

## callees

- `0x1400184ac`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140018546`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140018546`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400184f2`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400184f2`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14001851d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14001851d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14001856e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14001856e`

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
0x1400184ac  mov     [rsp-18h+arg_0], rbx
0x1400184b1  mov     [rsp-18h+arg_10], rsi
0x1400184b6  push    rbp
0x1400184b7  push    rdi
0x1400184b8  push    r14
0x1400184ba  mov     rbp, rsp
0x1400184bd  sub     rsp, 30h
0x1400184c1  xor     eax, eax
0x1400184c3  mov     byte ptr [rdx], 0
0x1400184c6  mov     [r8], eax
0x1400184c9  mov     rsi, r8
0x1400184cc  mov     r14, rdx
0x1400184cf  mov     [rbp+OwnerDefaulted], 0
0x1400184d3  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1400184d7  mov     [rbp+SaclPresent], 0
0x1400184db  lea     rdx, [rbp+Owner]; Owner
0x1400184df  mov     [rbp+Owner], 0
0x1400184e7  mov     rdi, rcx
0x1400184ea  mov     [rbp+Sacl], 0
0x1400184f2  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400184f9  nop     dword ptr [rax+rax+00h]
0x1400184fe  test    eax, eax
0x140018500  js      loc_140018591
0x140018506  xor     ebx, ebx
0x140018508  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14001850c  cmp     [rbp+Owner], rbx
0x140018510  lea     rdx, [rbp+Owner]; Group
0x140018514  mov     rcx, rdi; SecurityDescriptor
0x140018517  lea     eax, [rbx+1]
0x14001851a  cmovnz  ebx, eax
0x14001851d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140018524  nop     dword ptr [rax+rax+00h]
0x140018529  test    eax, eax
0x14001852b  js      short loc_140018591
0x14001852d  cmp     [rbp+Owner], 0
0x140018532  jz      short loc_140018537
0x140018534  or      ebx, 2
0x140018537  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14001853b  mov     rcx, rdi; SecurityDescriptor
0x14001853e  lea     r8, [rbp+Sacl]; Sacl
0x140018542  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140018546  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14001854d  nop     dword ptr [rax+rax+00h]
0x140018552  test    eax, eax
0x140018554  js      short loc_140018591
0x140018556  cmp     [rbp+SaclPresent], 0
0x14001855a  jz      short loc_14001855F
0x14001855c  or      ebx, 8
0x14001855f  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140018563  mov     rcx, rdi; SecurityDescriptor
0x140018566  lea     r8, [rbp+Sacl]; Dacl
0x14001856a  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14001856e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140018575  nop     dword ptr [rax+rax+00h]
0x14001857a  test    eax, eax
0x14001857c  js      short loc_140018591
0x14001857e  cmp     [rbp+SaclPresent], 0
0x140018582  jz      short loc_140018587
0x140018584  or      ebx, 4
0x140018587  mov     al, [rbp+OwnerDefaulted]
0x14001858a  mov     [r14], al
0x14001858d  xor     eax, eax
0x14001858f  mov     [rsi], ebx
0x140018591  mov     rbx, [rsp+30h+arg_0]
0x140018596  mov     rsi, [rsp+30h+arg_10]
0x14001859b  add     rsp, 30h
0x14001859f  pop     r14
0x1400185a1  pop     rdi
0x1400185a2  pop     rbp
0x1400185a3  retn
```
