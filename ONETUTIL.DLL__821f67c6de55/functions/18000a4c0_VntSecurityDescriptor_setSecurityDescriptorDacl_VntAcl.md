# VntSecurityDescriptor::setSecurityDescriptorDacl(VntAcl &)

- ea: `0x18000a4c0`
- end: `0x18000a5a7`
- name: `?setSecurityDescriptorDacl@VntSecurityDescriptor@@IEAAPEAVVstatus@@AEAVVntAcl@@@Z`
- size: `231`
- prototype: `struct Vstatus *__fastcall(VntSecurityDescriptor *__hidden this, struct VntAcl *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a720`

## callees

- `0x18000a4c0`
- `0x180083790`
- `0x1800b93d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a4f1`
- `KERNEL32!GetLastError` at `0x18000a551`
- `KERNEL32!GetLastError` at `0x18000a4f1`
- `KERNEL32!GetLastError` at `0x18000a551`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000a544`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000a544`
- `ADVAPI32!IsValidAcl` at `0x18000a4e2`
- `ADVAPI32!IsValidAcl` at `0x18000a4e2`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a50b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a56d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a50b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a56d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Vstatus *__fastcall VntSecurityDescriptor::setSecurityDescriptorDacl(PSECURITY_DESCRIPTOR *this, PACL *a2)
{
  __int64 v4; // rbx
  PSECURITY_DESCRIPTOR v5; // rdi
  DWORD LastError; // esi
  VgenericStatus *v7; // rax
  PSECURITY_DESCRIPTOR v9; // rdi
  DWORD v10; // esi
  VgenericStatus *v11; // rax

  v4 = 0;
  if ( !IsValidAcl(*a2) )
  {
    v5 = *this;
    LastError = GetLastError();
    if ( dword_1802B0018 )
      v7 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v7 = (VgenericStatus *)malloc(0x20u);
    if ( v7 )
      return VgenericStatus::VgenericStatus(v7, 0xE002Eu, LastError, v5, -2);
    return (struct Vstatus *)v4;
  }
  if ( !SetSecurityDescriptorDacl(this[5], 1, *a2, 0) )
  {
    v9 = *this;
    v10 = GetLastError();
    if ( dword_1802B0018 )
      v11 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v11 = (VgenericStatus *)malloc(0x20u);
    if ( v11 )
      return VgenericStatus::VgenericStatus(v11, 0xE002Eu, v10, v9, -2);
    return (struct Vstatus *)v4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a4c0  push    rdi
0x18000a4c2  sub     rsp, 30h
0x18000a4c6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a4cf  mov     [rsp+38h+arg_0], rbx
0x18000a4d4  mov     [rsp+38h+arg_10], rsi
0x18000a4d9  mov     rsi, rdx
0x18000a4dc  mov     rdi, rcx
0x18000a4df  mov     rcx, [rdx]; pAcl
0x18000a4e2  call    cs:IsValidAcl
0x18000a4e8  xor     ebx, ebx
0x18000a4ea  test    eax, eax
0x18000a4ec  jnz     short loc_18000A536
0x18000a4ee  mov     rdi, [rdi]
0x18000a4f1  call    cs:GetLastError
0x18000a4f7  mov     esi, eax
0x18000a4f9  lea     ecx, [rbx+20h]; unsigned __int64
0x18000a4fc  cmp     cs:dword_1802B0018, ebx
0x18000a502  jz      short loc_18000A50B
0x18000a504  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000a509  jmp     short loc_18000A511
0x18000a50b  call    cs:malloc
0x18000a511  mov     [rsp+38h+arg_8], rax
0x18000a516  test    rax, rax
0x18000a519  jz      short loc_18000A531
0x18000a51b  mov     r9, rdi
0x18000a51e  mov     r8d, esi; int
0x18000a521  mov     edx, 0E002Eh; unsigned int
0x18000a526  mov     rcx, rax; this
0x18000a529  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18000a52e  mov     rbx, rax
0x18000a531  mov     rax, rbx
0x18000a534  jmp     short loc_18000A597
0x18000a536  xor     r9d, r9d; bDaclDefaulted
0x18000a539  mov     r8, [rsi]; pDacl
0x18000a53c  lea     edx, [r9+1]; bDaclPresent
0x18000a540  mov     rcx, [rdi+28h]; pSecurityDescriptor
0x18000a544  call    cs:SetSecurityDescriptorDacl
0x18000a54a  test    eax, eax
0x18000a54c  jnz     short loc_18000A595
0x18000a54e  mov     rdi, [rdi]
0x18000a551  call    cs:GetLastError
0x18000a557  mov     esi, eax
0x18000a559  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a55e  cmp     cs:dword_1802B0018, ebx
0x18000a564  jz      short loc_18000A56D
0x18000a566  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000a56b  jmp     short loc_18000A573
0x18000a56d  call    cs:malloc
0x18000a573  mov     [rsp+38h+arg_8], rax
0x18000a578  test    rax, rax
0x18000a57b  jz      short loc_18000A593
0x18000a57d  mov     r9, rdi
0x18000a580  mov     r8d, esi; int
0x18000a583  mov     edx, 0E002Eh; unsigned int
0x18000a588  mov     rcx, rax; this
0x18000a58b  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18000a590  mov     rbx, rax
0x18000a593  jmp     short loc_18000A531
0x18000a595  xor     eax, eax
0x18000a597  mov     rbx, [rsp+38h+arg_0]
0x18000a59c  mov     rsi, [rsp+38h+arg_10]
0x18000a5a1  add     rsp, 30h
0x18000a5a5  pop     rdi
0x18000a5a6  retn
```
