# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x140038194`
- end: `0x14003828d`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140037104`
- `0x140037d04`

## callees

- `0x140038194`

## import_xrefs

- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400381da`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400381da`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14003822e`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14003822e`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140038205`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140038205`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140038256`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140038256`

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
0x140038194  mov     [rsp-18h+arg_0], rbx
0x140038199  mov     [rsp-18h+arg_10], rsi
0x14003819e  push    rbp
0x14003819f  push    rdi
0x1400381a0  push    r14
0x1400381a2  mov     rbp, rsp
0x1400381a5  sub     rsp, 30h
0x1400381a9  xor     eax, eax
0x1400381ab  mov     byte ptr [rdx], 0
0x1400381ae  mov     [r8], eax
0x1400381b1  mov     rsi, r8
0x1400381b4  mov     r14, rdx
0x1400381b7  mov     [rbp+OwnerDefaulted], 0
0x1400381bb  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1400381bf  mov     [rbp+SaclPresent], 0
0x1400381c3  lea     rdx, [rbp+Owner]; Owner
0x1400381c7  mov     [rbp+Owner], 0
0x1400381cf  mov     rdi, rcx
0x1400381d2  mov     [rbp+Sacl], 0
0x1400381da  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400381e1  nop     dword ptr [rax+rax+00h]
0x1400381e6  test    eax, eax
0x1400381e8  js      loc_140038279
0x1400381ee  xor     ebx, ebx
0x1400381f0  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x1400381f4  cmp     [rbp+Owner], rbx
0x1400381f8  lea     rdx, [rbp+Owner]; Group
0x1400381fc  mov     rcx, rdi; SecurityDescriptor
0x1400381ff  lea     eax, [rbx+1]
0x140038202  cmovnz  ebx, eax
0x140038205  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14003820c  nop     dword ptr [rax+rax+00h]
0x140038211  test    eax, eax
0x140038213  js      short loc_140038279
0x140038215  cmp     [rbp+Owner], 0
0x14003821a  jz      short loc_14003821F
0x14003821c  or      ebx, 2
0x14003821f  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x140038223  mov     rcx, rdi; SecurityDescriptor
0x140038226  lea     r8, [rbp+Sacl]; Sacl
0x14003822a  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x14003822e  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140038235  nop     dword ptr [rax+rax+00h]
0x14003823a  test    eax, eax
0x14003823c  js      short loc_140038279
0x14003823e  cmp     [rbp+SaclPresent], 0
0x140038242  jz      short loc_140038247
0x140038244  or      ebx, 8
0x140038247  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x14003824b  mov     rcx, rdi; SecurityDescriptor
0x14003824e  lea     r8, [rbp+Sacl]; Dacl
0x140038252  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x140038256  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14003825d  nop     dword ptr [rax+rax+00h]
0x140038262  test    eax, eax
0x140038264  js      short loc_140038279
0x140038266  cmp     [rbp+SaclPresent], 0
0x14003826a  jz      short loc_14003826F
0x14003826c  or      ebx, 4
0x14003826f  mov     al, [rbp+OwnerDefaulted]
0x140038272  mov     [r14], al
0x140038275  xor     eax, eax
0x140038277  mov     [rsi], ebx
0x140038279  mov     rbx, [rsp+30h+arg_0]
0x14003827e  mov     rsi, [rsp+30h+arg_10]
0x140038283  add     rsp, 30h
0x140038287  pop     r14
0x140038289  pop     rdi
0x14003828a  pop     rbp
0x14003828b  retn
```
