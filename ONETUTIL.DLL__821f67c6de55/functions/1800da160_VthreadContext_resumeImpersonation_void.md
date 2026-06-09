# VthreadContext::resumeImpersonation(void *)

- ea: `0x1800da160`
- end: `0x1800da285`
- name: `?resumeImpersonation@VthreadContext@@SAPEAVVstatus@@PEAX@Z`
- size: `293`
- prototype: `struct Vstatus *__fastcall(HANDLE hObject)`
- caller_count: `14`
- callee_count: `4`
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
- `0x1800da020`
- `0x1800daa90`
- `0x1800dbb68`

## callees

- `0x180083790`
- `0x1800b93d0`
- `0x1800da160`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800da1dc`
- `KERNEL32!TlsGetValue` at `0x1800da252`
- `KERNEL32!TlsGetValue` at `0x1800da1dc`
- `KERNEL32!TlsGetValue` at `0x1800da252`
- `KERNEL32!CloseHandle` at `0x1800da200`
- `KERNEL32!CloseHandle` at `0x1800da200`
- `KERNEL32!GetLastError` at `0x1800da195`
- `KERNEL32!GetLastError` at `0x1800da20a`
- `KERNEL32!GetLastError` at `0x1800da195`
- `KERNEL32!GetLastError` at `0x1800da20a`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800da186`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800da186`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800da1af`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800da225`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800da1af`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800da225`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Vstatus *__fastcall VthreadContext::resumeImpersonation(HANDLE hObject)
{
  DWORD LastError; // edi
  VgenericStatus *v3; // rax
  VgenericStatus *v4; // rdi
  LPVOID Value; // rax
  DWORD v6; // ebx
  VgenericStatus *v7; // rax
  VgenericStatus *v8; // rbx
  LPVOID v9; // rax

  if ( hObject != (HANDLE)-1LL )
  {
    if ( !ImpersonateLoggedOnUser(hObject) )
    {
      LastError = GetLastError();
      v3 = (VgenericStatus *)(dword_1802B0018 ? COWSAllocator::AllocCurrentHeap(0x20u) : malloc(0x20u));
      v4 = v3 ? VgenericStatus::VgenericStatus(v3, 0x3004Fu, LastError) : 0LL;
      Value = TlsGetValue(dwTlsIndex);
      if ( Value )
        (*(void (__fastcall **)(LPVOID, VgenericStatus *))(*(_QWORD *)Value + 40LL))(Value, v4);
    }
    if ( !CloseHandle(hObject) )
    {
      v6 = GetLastError();
      if ( dword_1802B0018 )
        v7 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v7 = (VgenericStatus *)malloc(0x20u);
      if ( v7 )
        v8 = VgenericStatus::VgenericStatus(v7, 0x30050u, v6);
      else
        v8 = 0;
      v9 = TlsGetValue(dwTlsIndex);
      if ( v9 )
        (*(void (__fastcall **)(LPVOID, VgenericStatus *))(*(_QWORD *)v9 + 40LL))(v9, v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800da160  push    rdi
0x1800da162  sub     rsp, 30h
0x1800da166  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800da16f  mov     [rsp+38h+arg_8], rbx
0x1800da174  mov     [rsp+38h+arg_10], rsi
0x1800da179  mov     rbx, rcx
0x1800da17c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800da180  jz      loc_1800DA273
0x1800da186  call    cs:ImpersonateLoggedOnUser
0x1800da18c  mov     esi, 20h ; ' '
0x1800da191  test    eax, eax
0x1800da193  jnz     short loc_1800DA1FD
0x1800da195  call    cs:GetLastError
0x1800da19b  mov     edi, eax
0x1800da19d  mov     ecx, esi; unsigned __int64
0x1800da19f  cmp     cs:dword_1802B0018, 0
0x1800da1a6  jz      short loc_1800DA1AF
0x1800da1a8  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800da1ad  jmp     short loc_1800DA1B5
0x1800da1af  call    cs:malloc
0x1800da1b5  mov     [rsp+38h+arg_0], rax
0x1800da1ba  test    rax, rax
0x1800da1bd  jz      short loc_1800DA1D4
0x1800da1bf  mov     r8d, edi; int
0x1800da1c2  mov     edx, 3004Fh; unsigned int
0x1800da1c7  mov     rcx, rax; this
0x1800da1ca  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800da1cf  mov     rdi, rax
0x1800da1d2  jmp     short loc_1800DA1D6
0x1800da1d4  xor     edi, edi
0x1800da1d6  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800da1dc  call    cs:TlsGetValue
0x1800da1e2  mov     r8, rax
0x1800da1e5  test    rax, rax
0x1800da1e8  jz      short loc_1800DA1FD
0x1800da1ea  mov     rcx, [rax]
0x1800da1ed  mov     rax, [rcx+28h]
0x1800da1f1  mov     rdx, rdi
0x1800da1f4  mov     rcx, r8
0x1800da1f7  call    cs:__guard_dispatch_icall_fptr
0x1800da1fd  mov     rcx, rbx; hObject
0x1800da200  call    cs:CloseHandle
0x1800da206  test    eax, eax
0x1800da208  jnz     short loc_1800DA273
0x1800da20a  call    cs:GetLastError
0x1800da210  mov     ebx, eax
0x1800da212  mov     rcx, rsi; unsigned __int64
0x1800da215  cmp     cs:dword_1802B0018, 0
0x1800da21c  jz      short loc_1800DA225
0x1800da21e  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800da223  jmp     short loc_1800DA22B
0x1800da225  call    cs:malloc
0x1800da22b  mov     [rsp+38h+arg_0], rax
0x1800da230  test    rax, rax
0x1800da233  jz      short loc_1800DA24A
0x1800da235  mov     r8d, ebx; int
0x1800da238  mov     edx, 30050h; unsigned int
0x1800da23d  mov     rcx, rax; this
0x1800da240  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800da245  mov     rbx, rax
0x1800da248  jmp     short loc_1800DA24C
0x1800da24a  xor     ebx, ebx
0x1800da24c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800da252  call    cs:TlsGetValue
0x1800da258  mov     r8, rax
0x1800da25b  test    rax, rax
0x1800da25e  jz      short loc_1800DA273
0x1800da260  mov     rcx, [rax]
0x1800da263  mov     rax, [rcx+28h]
0x1800da267  mov     rdx, rbx
0x1800da26a  mov     rcx, r8
0x1800da26d  call    cs:__guard_dispatch_icall_fptr
0x1800da273  xor     eax, eax
0x1800da275  mov     rbx, [rsp+38h+arg_8]
0x1800da27a  mov     rsi, [rsp+38h+arg_10]
0x1800da27f  add     rsp, 30h
0x1800da283  pop     rdi
0x1800da284  retn
```
