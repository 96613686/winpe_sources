# VprocessGlobals::outputDebugString(Vstring const &)

- ea: `0x1800963d0`
- end: `0x1800964e3`
- name: `?outputDebugString@VprocessGlobals@@QEAAXAEBVVstring@@@Z`
- size: `275`
- prototype: `void __fastcall(VprocessGlobals *__hidden this, const struct Vstring *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180083790`
- `0x1800963d0`
- `0x180096770`
- `0x1800b93d0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800964a2`
- `KERNEL32!TlsGetValue` at `0x1800964a2`
- `KERNEL32!GetCurrentThread` at `0x180096415`
- `KERNEL32!GetCurrentThread` at `0x180096415`
- `KERNEL32!CloseHandle` at `0x1800964c8`
- `KERNEL32!CloseHandle` at `0x1800964c8`
- `KERNEL32!GetLastError` at `0x180096458`
- `KERNEL32!GetLastError` at `0x180096458`
- `KERNEL32!OutputDebugStringA` at `0x180096443`
- `KERNEL32!OutputDebugStringA` at `0x1800964d7`
- `KERNEL32!OutputDebugStringA` at `0x180096443`
- `KERNEL32!OutputDebugStringA` at `0x1800964d7`
- `ADVAPI32!OpenThreadToken` at `0x18009642c`
- `ADVAPI32!OpenThreadToken` at `0x18009642c`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18009644e`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18009644e`
- `ADVAPI32!RevertToSelf` at `0x18009643a`
- `ADVAPI32!RevertToSelf` at `0x18009643a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180096475`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180096475`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VprocessGlobals::outputDebugString(VprocessGlobals *this, LPCSTR *a2, __int64 a3)
{
  int v4; // ecx
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  VgenericStatus *v7; // rax
  VgenericStatus *v8; // rbx
  LPVOID Value; // rax
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF
  VgenericStatus *v11; // [rsp+58h] [rbp+20h]

  if ( (unsigned __int8)sub_180096770(this, a2, a3) )
    v4 = *(_DWORD *)(qword_1802B00B0 + 4);
  else
    v4 = 0;
  if ( v4 == 2 && byte_1802AF49D )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      RevertToSelf();
      OutputDebugStringA(*a2);
      if ( !ImpersonateLoggedOnUser(TokenHandle) )
      {
        LastError = GetLastError();
        if ( dword_1802B0018 )
          v7 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
        else
          v7 = (VgenericStatus *)malloc(0x20u);
        v11 = v7;
        if ( v7 )
          v8 = VgenericStatus::VgenericStatus(v7, 0x3004Fu, LastError);
        else
          v8 = 0;
        Value = TlsGetValue(dwTlsIndex);
        if ( Value )
          (*(void (__fastcall **)(LPVOID, VgenericStatus *))(*(_QWORD *)Value + 40LL))(Value, v8);
      }
      CloseHandle(TokenHandle);
    }
  }
  else
  {
    OutputDebugStringA(*a2);
  }
}

```

## disassembly

```asm
0x1800963d0  push    rbx
0x1800963d2  sub     rsp, 30h
0x1800963d6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800963df  mov     rbx, rdx
0x1800963e2  call    sub_180096770
0x1800963e7  test    al, al
0x1800963e9  jz      short loc_1800963F7
0x1800963eb  mov     rax, cs:qword_1802B00B0
0x1800963f2  mov     ecx, [rax+4]
0x1800963f5  jmp     short loc_1800963F9
0x1800963f7  xor     ecx, ecx
0x1800963f9  cmp     ecx, 2
0x1800963fc  jnz     loc_1800964D4
0x180096402  cmp     cs:byte_1802AF49D, 0
0x180096409  jz      loc_1800964D4
0x18009640f  and     [rsp+38h+TokenHandle], 0
0x180096415  call    cs:GetCurrentThread
0x18009641b  mov     rcx, rax; ThreadHandle
0x18009641e  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180096423  mov     edx, 0Ch; DesiredAccess
0x180096428  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18009642c  call    cs:OpenThreadToken
0x180096432  test    eax, eax
0x180096434  jz      loc_1800964DD
0x18009643a  call    cs:RevertToSelf
0x180096440  mov     rcx, [rbx]; lpOutputString
0x180096443  call    cs:OutputDebugStringA
0x180096449  mov     rcx, [rsp+38h+TokenHandle]; hToken
0x18009644e  call    cs:ImpersonateLoggedOnUser
0x180096454  test    eax, eax
0x180096456  jnz     short loc_1800964C3
0x180096458  call    cs:GetLastError
0x18009645e  mov     ebx, eax
0x180096460  mov     ecx, 20h ; ' '; unsigned __int64
0x180096465  cmp     cs:dword_1802B0018, 0
0x18009646c  jz      short loc_180096475
0x18009646e  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180096473  jmp     short loc_18009647B
0x180096475  call    cs:malloc
0x18009647b  mov     [rsp+38h+arg_18], rax
0x180096480  test    rax, rax
0x180096483  jz      short loc_18009649A
0x180096485  mov     r8d, ebx; int
0x180096488  mov     edx, 3004Fh; unsigned int
0x18009648d  mov     rcx, rax; this
0x180096490  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x180096495  mov     rbx, rax
0x180096498  jmp     short loc_18009649C
0x18009649a  xor     ebx, ebx
0x18009649c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800964a2  call    cs:TlsGetValue
0x1800964a8  mov     r8, rax
0x1800964ab  test    rax, rax
0x1800964ae  jz      short loc_1800964C3
0x1800964b0  mov     rcx, [rax]
0x1800964b3  mov     rax, [rcx+28h]
0x1800964b7  mov     rdx, rbx
0x1800964ba  mov     rcx, r8
0x1800964bd  call    cs:__guard_dispatch_icall_fptr
0x1800964c3  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800964c8  call    cs:CloseHandle
0x1800964ce  add     rsp, 30h
0x1800964d2  pop     rbx
0x1800964d3  retn
0x1800964d4  mov     rcx, [rbx]; lpOutputString
0x1800964d7  call    cs:OutputDebugStringA
0x1800964dd  add     rsp, 30h
0x1800964e1  pop     rbx
0x1800964e2  retn
```
