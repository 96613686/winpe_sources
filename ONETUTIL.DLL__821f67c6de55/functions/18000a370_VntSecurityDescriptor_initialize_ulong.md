# VntSecurityDescriptor::initialize(ulong)

- ea: `0x18000a370`
- end: `0x18000a4be`
- name: `?initialize@VntSecurityDescriptor@@IEAAPEAVVstatus@@K@Z`
- size: `334`
- prototype: `struct Vstatus *(VntSecurityDescriptor *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a720`

## callees

- `0x18000a370`
- `0x180083790`
- `0x1800b93d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a3b1`
- `KERNEL32!GetLastError` at `0x18000a410`
- `KERNEL32!GetLastError` at `0x18000a465`
- `KERNEL32!GetLastError` at `0x18000a3b1`
- `KERNEL32!GetLastError` at `0x18000a410`
- `KERNEL32!GetLastError` at `0x18000a465`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18000a458`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18000a458`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000a403`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000a403`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a39f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a3cd`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a42c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a481`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a39f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a3cd`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a42c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000a481`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct Vstatus *__fastcall VntSecurityDescriptor::initialize(VntSecurityDescriptor *this, unsigned int a2)
{
  __int64 v3; // rbx
  void *v4; // rax
  __int64 v5; // rdi
  DWORD LastError; // esi
  VgenericStatus *v7; // rax
  __int64 v9; // rdi
  DWORD v10; // esi
  VgenericStatus *v11; // rax
  __int64 v12; // rdi
  DWORD v13; // esi
  VgenericStatus *v14; // rax

  v3 = 0;
  if ( dword_1802B0018 )
    v4 = COWSAllocator::AllocCurrentHeap(a2);
  else
    v4 = malloc(a2);
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
  {
    v5 = *(_QWORD *)this;
    LastError = GetLastError();
    if ( dword_1802B0018 )
      v7 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v7 = (VgenericStatus *)malloc(0x20u);
    if ( v7 )
      return VgenericStatus::VgenericStatus(v7, 0xE002Cu, LastError, v5, -2);
    return (struct Vstatus *)v3;
  }
  if ( !InitializeSecurityDescriptor(v4, 1u) )
  {
    v9 = *(_QWORD *)this;
    v10 = GetLastError();
    if ( dword_1802B0018 )
      v11 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v11 = (VgenericStatus *)malloc(0x20u);
    if ( v11 )
      return VgenericStatus::VgenericStatus(v11, 0xE002Cu, v10, v9, -2);
    return (struct Vstatus *)v3;
  }
  if ( !IsValidSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)this + 5)) )
  {
    v12 = *(_QWORD *)this;
    v13 = GetLastError();
    if ( dword_1802B0018 )
      v14 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v14 = (VgenericStatus *)malloc(0x20u);
    if ( v14 )
      return VgenericStatus::VgenericStatus(v14, 0xE002Cu, v13, v12, -2);
    return (struct Vstatus *)v3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a370  push    rdi
0x18000a372  sub     rsp, 30h
0x18000a376  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a37f  mov     [rsp+38h+arg_8], rbx
0x18000a384  mov     [rsp+38h+arg_10], rsi
0x18000a389  mov     rdi, rcx
0x18000a38c  mov     ecx, edx; unsigned __int64
0x18000a38e  xor     ebx, ebx
0x18000a390  cmp     cs:dword_1802B0018, ebx
0x18000a396  jz      short loc_18000A39F
0x18000a398  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000a39d  jmp     short loc_18000A3A5
0x18000a39f  call    cs:malloc
0x18000a3a5  mov     [rdi+28h], rax
0x18000a3a9  test    rax, rax
0x18000a3ac  jnz     short loc_18000A3FB
0x18000a3ae  mov     rdi, [rdi]
0x18000a3b1  call    cs:GetLastError
0x18000a3b7  mov     esi, eax
0x18000a3b9  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a3be  cmp     cs:dword_1802B0018, ebx
0x18000a3c4  jz      short loc_18000A3CD
0x18000a3c6  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000a3cb  jmp     short loc_18000A3D3
0x18000a3cd  call    cs:malloc
0x18000a3d3  mov     [rsp+38h+arg_0], rax
0x18000a3d8  test    rax, rax
0x18000a3db  jz      short loc_18000A3F3
0x18000a3dd  mov     r9, rdi
0x18000a3e0  mov     r8d, esi; int
0x18000a3e3  mov     edx, 0E002Ch; unsigned int
0x18000a3e8  mov     rcx, rax; this
0x18000a3eb  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18000a3f0  mov     rbx, rax
0x18000a3f3  mov     rax, rbx
0x18000a3f6  jmp     loc_18000A4AE
0x18000a3fb  mov     edx, 1; dwRevision
0x18000a400  mov     rcx, rax; pSecurityDescriptor
0x18000a403  call    cs:InitializeSecurityDescriptor
0x18000a409  test    eax, eax
0x18000a40b  jnz     short loc_18000A454
0x18000a40d  mov     rdi, [rdi]
0x18000a410  call    cs:GetLastError
0x18000a416  mov     esi, eax
0x18000a418  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a41d  cmp     cs:dword_1802B0018, ebx
0x18000a423  jz      short loc_18000A42C
0x18000a425  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000a42a  jmp     short loc_18000A432
0x18000a42c  call    cs:malloc
0x18000a432  mov     [rsp+38h+arg_0], rax
0x18000a437  test    rax, rax
0x18000a43a  jz      short loc_18000A452
0x18000a43c  mov     r9, rdi
0x18000a43f  mov     r8d, esi; int
0x18000a442  mov     edx, 0E002Ch; unsigned int
0x18000a447  mov     rcx, rax; this
0x18000a44a  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18000a44f  mov     rbx, rax
0x18000a452  jmp     short loc_18000A3F3
0x18000a454  mov     rcx, [rdi+28h]; pSecurityDescriptor
0x18000a458  call    cs:IsValidSecurityDescriptor
0x18000a45e  test    eax, eax
0x18000a460  jnz     short loc_18000A4AC
0x18000a462  mov     rdi, [rdi]
0x18000a465  call    cs:GetLastError
0x18000a46b  mov     esi, eax
0x18000a46d  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a472  cmp     cs:dword_1802B0018, ebx
0x18000a478  jz      short loc_18000A481
0x18000a47a  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000a47f  jmp     short loc_18000A487
0x18000a481  call    cs:malloc
0x18000a487  mov     [rsp+38h+arg_0], rax
0x18000a48c  test    rax, rax
0x18000a48f  jz      short loc_18000A4A7
0x18000a491  mov     r9, rdi
0x18000a494  mov     r8d, esi; int
0x18000a497  mov     edx, 0E002Ch; unsigned int
0x18000a49c  mov     rcx, rax; this
0x18000a49f  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18000a4a4  mov     rbx, rax
0x18000a4a7  jmp     loc_18000A3F3
0x18000a4ac  xor     eax, eax
0x18000a4ae  mov     rbx, [rsp+38h+arg_8]
0x18000a4b3  mov     rsi, [rsp+38h+arg_10]
0x18000a4b8  add     rsp, 30h
0x18000a4bc  pop     rdi
0x18000a4bd  retn
```
