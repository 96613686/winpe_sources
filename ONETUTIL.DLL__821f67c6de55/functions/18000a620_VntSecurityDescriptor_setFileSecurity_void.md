# VntSecurityDescriptor::setFileSecurity(void)

- ea: `0x18000a620`
- end: `0x18000a6d6`
- name: `?setFileSecurity@VntSecurityDescriptor@@IEAAPEAVVstatus@@XZ`
- size: `182`
- prototype: `struct Vstatus *__fastcall(VntSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000a720`

## callees

- `0x18000a620`
- `0x18000a830`
- `0x180083790`
- `0x1800b93d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a684`
- `KERNEL32!GetLastError` at `0x18000a684`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000a677`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000a677`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a69e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a69e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Vstatus *__fastcall VntSecurityDescriptor::setFileSecurity(VntSecurityDescriptor *this)
{
  __int64 v2; // rbx
  struct Vstatus *result; // rax
  PSECURITY_DESCRIPTOR v4; // rdi
  DWORD LastError; // esi
  VgenericStatus *v6; // rax
  int v7; // [rsp+78h] [rbp+10h] BYREF
  PACL pDacl; // [rsp+80h] [rbp+18h] BYREF
  VgenericStatus *v9; // [rsp+88h] [rbp+20h]

  v2 = 0;
  pDacl = 0;
  v7 = 0;
  result = VntSecurityDescriptor::getDacl((PSECURITY_DESCRIPTOR *)this, &pDacl, &v7);
  if ( !result )
  {
    if ( SetNamedSecurityInfoW(*((LPWSTR *)this + 1), SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0) )
    {
      v4 = *(PSECURITY_DESCRIPTOR *)this;
      LastError = GetLastError();
      if ( dword_1802B0018 )
        v6 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v6 = (VgenericStatus *)malloc(0x20u);
      v9 = v6;
      if ( v6 )
        return VgenericStatus::VgenericStatus(v6, 0xE002Eu, LastError, v4);
      return (struct Vstatus *)v2;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a620  mov     rax, rsp
0x18000a623  push    rbx
0x18000a624  push    rsi
0x18000a625  push    rdi
0x18000a626  sub     rsp, 50h
0x18000a62a  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18000a632  mov     rdi, rcx
0x18000a635  xor     ebx, ebx
0x18000a637  mov     [rax+18h], rbx
0x18000a63b  mov     [rax+10h], ebx
0x18000a63e  lea     r8, [rax+10h]; int *
0x18000a642  lea     rdx, [rax+18h]; struct _ACL **
0x18000a646  call    ?getDacl@VntSecurityDescriptor@@IEAAPEAVVstatus@@AEAPEAU_ACL@@AEAH@Z; VntSecurityDescriptor::getDacl(_ACL * &,int &)
0x18000a64b  test    rax, rax
0x18000a64e  jnz     short loc_18000A6CE
0x18000a650  mov     [rsp+68h+pSacl], rbx; pSacl
0x18000a655  mov     rax, [rsp+68h+arg_10]
0x18000a65d  mov     [rsp+68h+pDacl], rax; pDacl
0x18000a662  mov     [rsp+68h+psidGroup], rbx; psidGroup
0x18000a667  xor     r9d, r9d; psidOwner
0x18000a66a  lea     edx, [rbx+1]; ObjectType
0x18000a66d  mov     r8d, 80000004h; SecurityInfo
0x18000a673  mov     rcx, [rdi+8]; pObjectName
0x18000a677  call    cs:SetNamedSecurityInfoW
0x18000a67d  test    eax, eax
0x18000a67f  jz      short loc_18000A6CC
0x18000a681  mov     rdi, [rdi]
0x18000a684  call    cs:GetLastError
0x18000a68a  mov     esi, eax
0x18000a68c  lea     ecx, [rbx+20h]; unsigned __int64
0x18000a68f  cmp     cs:dword_1802B0018, ebx
0x18000a695  jz      short loc_18000A69E
0x18000a697  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000a69c  jmp     short loc_18000A6A4
0x18000a69e  call    cs:malloc
0x18000a6a4  mov     [rsp+68h+arg_18], rax
0x18000a6ac  test    rax, rax
0x18000a6af  jz      short loc_18000A6C7
0x18000a6b1  mov     r9, rdi
0x18000a6b4  mov     r8d, esi; int
0x18000a6b7  mov     edx, 0E002Eh; unsigned int
0x18000a6bc  mov     rcx, rax; this
0x18000a6bf  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18000a6c4  mov     rbx, rax
0x18000a6c7  mov     rax, rbx
0x18000a6ca  jmp     short loc_18000A6CE
0x18000a6cc  xor     eax, eax
0x18000a6ce  add     rsp, 50h
0x18000a6d2  pop     rdi
0x18000a6d3  pop     rsi
0x18000a6d4  pop     rbx
0x18000a6d5  retn
```
