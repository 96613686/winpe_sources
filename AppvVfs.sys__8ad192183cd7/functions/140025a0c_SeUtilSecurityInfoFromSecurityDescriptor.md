# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x140025a0c`
- end: `0x140025b05`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `NTSTATUS __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, unsigned __int8 *, _DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024924`
- `0x14002553c`

## callees

- `0x140025a0c`

## import_xrefs

- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140025a52`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140025a52`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140025a7d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140025a7d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140025ace`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140025ace`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140025aa6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140025aa6`

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
0x140025a0c  mov     [rsp-18h+arg_0], rbx
0x140025a11  mov     [rsp-18h+arg_10], rsi
0x140025a16  push    rbp
0x140025a17  push    rdi
0x140025a18  push    r14
0x140025a1a  mov     rbp, rsp
0x140025a1d  sub     rsp, 30h
0x140025a21  xor     eax, eax
0x140025a23  mov     byte ptr [rdx], 0
0x140025a26  mov     [r8], eax
0x140025a29  mov     rsi, r8
0x140025a2c  mov     r14, rdx
0x140025a2f  mov     [rbp+OwnerDefaulted], 0
0x140025a33  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140025a37  mov     [rbp+SaclPresent], 0
0x140025a3b  lea     rdx, [rbp+Owner]; Owner
0x140025a3f  mov     [rbp+Owner], 0
0x140025a47  mov     rdi, rcx
0x140025a4a  mov     [rbp+Sacl], 0
0x140025a52  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140025a59  nop     dword ptr [rax+rax+00h]
0x140025a5e  test    eax, eax
0x140025a60  js      loc_140025AF1
0x140025a66  xor     ebx, ebx
0x140025a68  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x140025a6c  cmp     [rbp+Owner], rbx
0x140025a70  lea     rdx, [rbp+Owner]; Group
0x140025a74  mov     rcx, rdi; SecurityDescriptor
0x140025a77  lea     eax, [rbx+1]
0x140025a7a  cmovnz  ebx, eax
0x140025a7d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140025a84  nop     dword ptr [rax+rax+00h]
0x140025a89  test    eax, eax
0x140025a8b  js      short loc_140025AF1
0x140025a8d  cmp     [rbp+Owner], 0
0x140025a92  jz      short loc_140025A97
0x140025a94  or      ebx, 2
0x140025a97  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x140025a9b  mov     rcx, rdi; SecurityDescriptor
0x140025a9e  lea     r8, [rbp+Sacl]; Sacl
0x140025aa2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140025aa6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140025aad  nop     dword ptr [rax+rax+00h]
0x140025ab2  test    eax, eax
0x140025ab4  js      short loc_140025AF1
0x140025ab6  cmp     [rbp+SaclPresent], 0
0x140025aba  jz      short loc_140025ABF
0x140025abc  or      ebx, 8
0x140025abf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140025ac3  mov     rcx, rdi; SecurityDescriptor
0x140025ac6  lea     r8, [rbp+Sacl]; Dacl
0x140025aca  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x140025ace  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140025ad5  nop     dword ptr [rax+rax+00h]
0x140025ada  test    eax, eax
0x140025adc  js      short loc_140025AF1
0x140025ade  cmp     [rbp+SaclPresent], 0
0x140025ae2  jz      short loc_140025AE7
0x140025ae4  or      ebx, 4
0x140025ae7  mov     al, [rbp+OwnerDefaulted]
0x140025aea  mov     [r14], al
0x140025aed  xor     eax, eax
0x140025aef  mov     [rsi], ebx
0x140025af1  mov     rbx, [rsp+30h+arg_0]
0x140025af6  mov     rsi, [rsp+30h+arg_10]
0x140025afb  add     rsp, 30h
0x140025aff  pop     r14
0x140025b01  pop     rdi
0x140025b02  pop     rbp
0x140025b03  retn
```
