# CReaderProxy::Protocol(void)

- ea: `0x18000f87c`
- end: `0x18000fab4`
- name: `?Protocol@CReaderProxy@@QEAAKXZ`
- size: `568`
- prototype: `__int64 __fastcall(CReaderProxy *this)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004af8`
- `0x18000f2a0`
- `0x180015790`
- `0x1800300b8`

## callees

- `0x18000c640`
- `0x18000f87c`
- `0x18000fac0`
- `0x18000fb50`
- `0x180012380`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f8da`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f978`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fa4b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fa6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f8da`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f978`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fa4b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fa6f`

## pseudocode

```c
__int64 __fastcall CReaderProxy::Protocol(CReaderProxy *this)
{
  char *v2; // rdi
  __int64 v3; // rbx
  _DWORD *v4; // rdi
  __int64 v5; // rbx
  unsigned int v6; // ebx
  __int64 pExceptionObject; // [rsp+40h] [rbp+20h] BYREF
  __int64 v9; // [rsp+48h] [rbp+28h] BYREF
  __int64 v10; // [rsp+50h] [rbp+30h] BYREF

  v2 = (char *)this + 8;
  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 1))((char *)this + 8, 0, 0);
  if ( !*(_QWORD *)this )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  v3 = *(_QWORD *)this + 512LL;
  v10 = v3;
  pExceptionObject = v3;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v3)(v3, 0, 0);
  if ( *(LPVOID *)(v3 + 104) != TlsGetValue(dwTlsIndex) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    while ( 1 )
    {
      CAccessLock::WaitOnWriters((CAccessLock *)v3);
      pExceptionObject = v3;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v3)(v3, 0, 0);
      if ( !*(_DWORD *)(v3 + 60) || *(LPVOID *)(v3 + 104) == TlsGetValue(dwTlsIndex) )
        break;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&pExceptionObject);
    }
  }
  ++*(_DWORD *)(v3 + 56);
  CAccessLock::UnsignalNoReaders((CAccessLock *)v3);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  v4 = *(_DWORD **)this;
  v5 = *(_QWORD *)this + 56LL;
  v9 = v5;
  pExceptionObject = v5;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v5)(v5, 0, 0);
  if ( *(LPVOID *)(v5 + 104) != TlsGetValue(dwTlsIndex) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    while ( 1 )
    {
      CAccessLock::WaitOnWriters((CAccessLock *)v5);
      pExceptionObject = v5;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v5)(v5, 0, 0);
      if ( !*(_DWORD *)(v5 + 60) || *(LPVOID *)(v5 + 104) == TlsGetValue(dwTlsIndex) )
        break;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&pExceptionObject);
    }
  }
  ++*(_DWORD *)(v5 + 56);
  CAccessLock::UnsignalNoReaders((CAccessLock *)v5);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v6 = v4[57];
  CLockRead::~CLockRead((CLockRead *)&v9);
  CLockRead::~CLockRead((CLockRead *)&v10);
  return v6;
}

```

## disassembly

```asm
0x18000f87c  mov     [rsp-18h+arg_18], rbx
0x18000f881  push    rbp
0x18000f882  push    rsi
0x18000f883  push    rdi
0x18000f884  mov     rbp, rsp
0x18000f887  sub     rsp, 20h
0x18000f88b  mov     rsi, rcx
0x18000f88e  lea     rdi, [rcx+8]
0x18000f892  mov     rax, [rdi]
0x18000f895  xor     r8d, r8d
0x18000f898  xor     edx, edx
0x18000f89a  mov     rcx, rdi
0x18000f89d  mov     rax, [rax]
0x18000f8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8a5  mov     rbx, [rsi]
0x18000f8a8  test    rbx, rbx
0x18000f8ab  jz      loc_18000FA8D
0x18000f8b1  add     rbx, 200h
0x18000f8b8  mov     [rbp+arg_10], rbx
0x18000f8bc  mov     [rbp+pExceptionObject], rbx
0x18000f8c0  mov     rax, [rbx]
0x18000f8c3  xor     r8d, r8d
0x18000f8c6  xor     edx, edx
0x18000f8c8  mov     rcx, rbx
0x18000f8cb  mov     rax, [rax]
0x18000f8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8d3  nop
0x18000f8d4  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000f8da  call    cs:__imp_TlsGetValue
0x18000f8e0  cmp     [rbx+68h], rax
0x18000f8e4  jz      loc_18000FA06
0x18000f8ea  mov     rax, [rbx]
0x18000f8ed  mov     rcx, rbx
0x18000f8f0  mov     rax, [rax+8]
0x18000f8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8f9  nop
0x18000f8fa  mov     rcx, rbx; this
0x18000f8fd  call    ?WaitOnWriters@CAccessLock@@IEAAXXZ; CAccessLock::WaitOnWriters(void)
0x18000f902  mov     [rbp+pExceptionObject], rbx
0x18000f906  mov     rax, [rbx]
0x18000f909  xor     r8d, r8d
0x18000f90c  xor     edx, edx
0x18000f90e  mov     rcx, rbx
0x18000f911  mov     rax, [rax]
0x18000f914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f919  nop
0x18000f91a  cmp     dword ptr [rbx+3Ch], 0
0x18000f91e  jnz     loc_18000FA45
0x18000f924  inc     dword ptr [rbx+38h]
0x18000f927  mov     rcx, rbx; this
0x18000f92a  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000f92f  nop
0x18000f930  mov     rax, [rbx]
0x18000f933  mov     rcx, rbx
0x18000f936  mov     rax, [rax+8]
0x18000f93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f93f  nop
0x18000f940  mov     rax, [rdi]
0x18000f943  mov     rcx, rdi
0x18000f946  mov     rax, [rax+8]
0x18000f94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f94f  mov     rdi, [rsi]
0x18000f952  lea     rbx, [rdi+38h]
0x18000f956  mov     [rbp+arg_8], rbx
0x18000f95a  mov     [rbp+pExceptionObject], rbx
0x18000f95e  mov     rax, [rbx]
0x18000f961  xor     r8d, r8d
0x18000f964  xor     edx, edx
0x18000f966  mov     rcx, rbx
0x18000f969  mov     rax, [rax]
0x18000f96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f971  nop
0x18000f972  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000f978  call    cs:__imp_TlsGetValue
0x18000f97e  cmp     [rbx+68h], rax
0x18000f982  jz      loc_18000FA27
0x18000f988  mov     rax, [rbx]
0x18000f98b  mov     rcx, rbx
0x18000f98e  mov     rax, [rax+8]
0x18000f992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f997  nop
0x18000f998  mov     rcx, rbx; this
0x18000f99b  call    ?WaitOnWriters@CAccessLock@@IEAAXXZ; CAccessLock::WaitOnWriters(void)
0x18000f9a0  mov     [rbp+pExceptionObject], rbx
0x18000f9a4  mov     rax, [rbx]
0x18000f9a7  xor     r8d, r8d
0x18000f9aa  xor     edx, edx
0x18000f9ac  mov     rcx, rbx
0x18000f9af  mov     rax, [rax]
0x18000f9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9b7  nop
0x18000f9b8  cmp     dword ptr [rbx+3Ch], 0
0x18000f9bc  jnz     loc_18000FA69
0x18000f9c2  inc     dword ptr [rbx+38h]
0x18000f9c5  mov     rcx, rbx; this
0x18000f9c8  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000f9cd  nop
0x18000f9ce  mov     rax, [rbx]
0x18000f9d1  mov     rcx, rbx
0x18000f9d4  mov     rax, [rax+8]
0x18000f9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9dd  nop
0x18000f9de  mov     ebx, [rdi+0E4h]
0x18000f9e4  lea     rcx, [rbp+arg_8]; this
0x18000f9e8  call    ??1CLockRead@@QEAA@XZ; CLockRead::~CLockRead(void)
0x18000f9ed  nop
0x18000f9ee  lea     rcx, [rbp+arg_10]; this
0x18000f9f2  call    ??1CLockRead@@QEAA@XZ; CLockRead::~CLockRead(void)
0x18000f9f7  mov     eax, ebx
0x18000f9f9  mov     rbx, [rsp+20h+arg_18]
0x18000f9fe  add     rsp, 20h
0x18000fa02  pop     rdi
0x18000fa03  pop     rsi
0x18000fa04  pop     rbp
0x18000fa05  retn
0x18000fa06  inc     dword ptr [rbx+38h]
0x18000fa09  mov     rcx, rbx; this
0x18000fa0c  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000fa11  nop
0x18000fa12  mov     rax, [rbx]
0x18000fa15  mov     rcx, rbx
0x18000fa18  mov     rax, [rax+8]
0x18000fa1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa21  nop
0x18000fa22  jmp     loc_18000F940
0x18000fa27  inc     dword ptr [rbx+38h]
0x18000fa2a  mov     rcx, rbx; this
0x18000fa2d  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000fa32  nop
0x18000fa33  mov     rax, [rbx]
0x18000fa36  mov     rcx, rbx
0x18000fa39  mov     rax, [rax+8]
0x18000fa3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa42  nop
0x18000fa43  jmp     short loc_18000F9DE
0x18000fa45  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000fa4b  call    cs:__imp_TlsGetValue
0x18000fa51  cmp     [rbx+68h], rax
0x18000fa55  jz      loc_18000F924
0x18000fa5b  lea     rcx, [rbp+pExceptionObject]; this
0x18000fa5f  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18000fa64  jmp     loc_18000F8FA
0x18000fa69  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000fa6f  call    cs:__imp_TlsGetValue
0x18000fa75  cmp     [rbx+68h], rax
0x18000fa79  jz      loc_18000F9C2
0x18000fa7f  lea     rcx, [rbp+pExceptionObject]; this
0x18000fa83  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18000fa88  jmp     loc_18000F998
0x18000fa8d  mov     rax, [rdi]
0x18000fa90  mov     rcx, rdi
0x18000fa93  mov     rax, [rax+8]
0x18000fa97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa9c  mov     dword ptr [rbp+pExceptionObject], 80100017h
0x18000faa3  lea     rdx, _TI1K; pThrowInfo
0x18000faaa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000faae  call    _CxxThrowException_0
```
