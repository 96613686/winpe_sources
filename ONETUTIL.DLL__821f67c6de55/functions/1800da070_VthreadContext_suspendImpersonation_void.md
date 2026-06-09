# VthreadContext::suspendImpersonation(void * &)

- ea: `0x1800da070`
- end: `0x1800da153`
- name: `?suspendImpersonation@VthreadContext@@SAPEAVVstatus@@AEAPEAX@Z`
- size: `227`
- prototype: `struct Vstatus *__fastcall(PHANDLE TokenHandle)`
- caller_count: `14`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180070340`
- `0x1800a5280`
- `0x1800a53f0`
- `0x1800a54b0`
- `0x1800a5590`
- `0x1800a5670`
- `0x1800a5750`
- `0x1800a5810`
- `0x1800a58c0`
- `0x1800a5970`
- `0x1800a5a80`
- `0x1800d9fd0`
- `0x1800daa40`
- `0x1800dbb68`

## callees

- `0x180083790`
- `0x1800b93d0`
- `0x1800da070`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800da087`
- `KERNEL32!GetCurrentThread` at `0x1800da087`
- `KERNEL32!GetLastError` at `0x1800da0a8`
- `KERNEL32!GetLastError` at `0x1800da0b9`
- `KERNEL32!GetLastError` at `0x1800da105`
- `KERNEL32!GetLastError` at `0x1800da0a8`
- `KERNEL32!GetLastError` at `0x1800da0b9`
- `KERNEL32!GetLastError` at `0x1800da105`
- `ADVAPI32!OpenThreadToken` at `0x1800da09c`
- `ADVAPI32!OpenThreadToken` at `0x1800da09c`
- `ADVAPI32!RevertToSelf` at `0x1800da0fb`
- `ADVAPI32!RevertToSelf` at `0x1800da0fb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800da0d3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800da121`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800da0d3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800da121`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Vstatus *__fastcall VthreadContext::suspendImpersonation(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  __int64 v4; // rbx
  DWORD v5; // edi
  VgenericStatus *v6; // rax
  DWORD LastError; // edi
  VgenericStatus *v9; // rax

  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0xCu, 1, TokenHandle);
  v4 = 0;
  if ( v3 )
  {
    if ( !RevertToSelf() )
    {
      LastError = GetLastError();
      if ( dword_1802B0018 )
        v9 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v9 = (VgenericStatus *)malloc(0x20u);
      if ( v9 )
        return VgenericStatus::VgenericStatus(v9, 0x3004Eu, LastError);
      return (struct Vstatus *)v4;
    }
  }
  else if ( GetLastError() != 1008 )
  {
    v5 = GetLastError();
    if ( dword_1802B0018 )
      v6 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v6 = (VgenericStatus *)malloc(0x20u);
    if ( v6 )
      return VgenericStatus::VgenericStatus(v6, 0x30051u, v5);
    return (struct Vstatus *)v4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800da070  push    rdi
0x1800da072  sub     rsp, 30h
0x1800da076  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800da07f  mov     [rsp+38h+arg_0], rbx
0x1800da084  mov     rbx, rcx
0x1800da087  call    cs:GetCurrentThread
0x1800da08d  mov     rcx, rax; ThreadHandle
0x1800da090  mov     r9, rbx; TokenHandle
0x1800da093  mov     edx, 0Ch; DesiredAccess
0x1800da098  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800da09c  call    cs:OpenThreadToken
0x1800da0a2  xor     ebx, ebx
0x1800da0a4  test    eax, eax
0x1800da0a6  jnz     short loc_1800DA0FB
0x1800da0a8  call    cs:GetLastError
0x1800da0ae  cmp     eax, 3F0h
0x1800da0b3  jz      loc_1800DA146
0x1800da0b9  call    cs:GetLastError
0x1800da0bf  mov     edi, eax
0x1800da0c1  lea     ecx, [rbx+20h]; unsigned __int64
0x1800da0c4  cmp     cs:dword_1802B0018, ebx
0x1800da0ca  jz      short loc_1800DA0D3
0x1800da0cc  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800da0d1  jmp     short loc_1800DA0D9
0x1800da0d3  call    cs:malloc
0x1800da0d9  mov     [rsp+38h+arg_8], rax
0x1800da0de  test    rax, rax
0x1800da0e1  jz      short loc_1800DA0F6
0x1800da0e3  mov     r8d, edi; int
0x1800da0e6  mov     edx, 30051h; unsigned int
0x1800da0eb  mov     rcx, rax; this
0x1800da0ee  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800da0f3  mov     rbx, rax
0x1800da0f6  mov     rax, rbx
0x1800da0f9  jmp     short loc_1800DA148
0x1800da0fb  call    cs:RevertToSelf
0x1800da101  test    eax, eax
0x1800da103  jnz     short loc_1800DA146
0x1800da105  call    cs:GetLastError
0x1800da10b  mov     edi, eax
0x1800da10d  mov     ecx, 20h ; ' '; unsigned __int64
0x1800da112  cmp     cs:dword_1802B0018, ebx
0x1800da118  jz      short loc_1800DA121
0x1800da11a  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800da11f  jmp     short loc_1800DA127
0x1800da121  call    cs:malloc
0x1800da127  mov     [rsp+38h+arg_8], rax
0x1800da12c  test    rax, rax
0x1800da12f  jz      short loc_1800DA144
0x1800da131  mov     r8d, edi; int
0x1800da134  mov     edx, 3004Eh; unsigned int
0x1800da139  mov     rcx, rax; this
0x1800da13c  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800da141  mov     rbx, rax
0x1800da144  jmp     short loc_1800DA0F6
0x1800da146  xor     eax, eax
0x1800da148  mov     rbx, [rsp+38h+arg_0]
0x1800da14d  add     rsp, 30h
0x1800da151  pop     rdi
0x1800da152  retn
```
