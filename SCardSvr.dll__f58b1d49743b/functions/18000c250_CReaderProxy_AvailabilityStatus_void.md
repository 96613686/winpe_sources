# CReaderProxy::AvailabilityStatus(void)

- ea: `0x18000c250`
- end: `0x18000c638`
- name: `?AvailabilityStatus@CReaderProxy@@QEAA?AW4AvailableState@CReader@@XZ`
- size: `1000`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007910`
- `0x180009da0`
- `0x18000a310`

## callees

- `0x18000c250`
- `0x18000c870`
- `0x18000fb50`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c323`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c3f1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c323`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c3f1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c446`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c494`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c446`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c61c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c2aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c2d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c378`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c3a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c54d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c578`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c2aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c2d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c378`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c3a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c54d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c578`

## pseudocode

```c
__int64 __fastcall CReaderProxy::AvailabilityStatus(__int64 *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rbp
  LPVOID Value; // r14
  unsigned int v5; // eax
  __int64 v6; // r14
  __int64 v7; // rdi
  __int64 v8; // rsi
  LPVOID v9; // rbp
  unsigned int v10; // eax
  unsigned int v11; // esi
  bool v12; // zf
  __int64 pExceptionObject; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h]
  __int64 v16; // [rsp+60h] [rbp+18h]

  (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))a1[1])(a1 + 1, 0, 0);
  if ( !*a1 )
  {
    (*(void (__fastcall **)(__int64 *))(a1[1] + 8))(a1 + 1);
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  v2 = *a1 + 512;
  v15 = v2;
  pExceptionObject = v2;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
  if ( *(LPVOID *)(v2 + 104) == TlsGetValue(dwTlsIndex) )
  {
    ++*(_DWORD *)(v2 + 56);
    CAccessLock::UnsignalNoReaders((CAccessLock *)v2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  else
  {
    do
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
      v3 = *(_QWORD *)(v2 + 88);
      Value = TlsGetValue(dword_18004B240);
      while ( 1 )
      {
        v5 = WaitForAnyObject(0xFFFFFFFF, v3, Value, 0);
        if ( v5 == 1 )
          break;
        if ( v5 == 2 )
        {
          LODWORD(pExceptionObject) = -2146435070;
          throw (ulong *)&pExceptionObject;
        }
      }
      v16 = v2;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
    }
    while ( *(_DWORD *)(v2 + 60) && *(LPVOID *)(v2 + 104) != TlsGetValue(dwTlsIndex) );
    ++*(_DWORD *)(v2 + 56);
    if ( !ResetEvent(*(HANDLE *)(v2 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  (*(void (__fastcall **)(__int64 *))(a1[1] + 8))(a1 + 1);
  v6 = *a1;
  v7 = *a1 + 56;
  pExceptionObject = v7;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v7)(v7, 0, 0);
  if ( *(LPVOID *)(v7 + 104) == TlsGetValue(dwTlsIndex) )
  {
    ++*(_DWORD *)(v7 + 56);
    CAccessLock::UnsignalNoReaders((CAccessLock *)v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    do
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      v8 = *(_QWORD *)(v7 + 88);
      v9 = TlsGetValue(dword_18004B240);
      while ( 1 )
      {
        v10 = WaitForAnyObject(0xFFFFFFFF, v8, v9, 0);
        if ( v10 == 1 )
          break;
        if ( v10 == 2 )
        {
          LODWORD(pExceptionObject) = -2146435070;
          throw (ulong *)&pExceptionObject;
        }
      }
      v16 = v7;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v7)(v7, 0, 0);
    }
    while ( *(_DWORD *)(v7 + 60) && *(LPVOID *)(v7 + 104) != TlsGetValue(dwTlsIndex) );
    ++*(_DWORD *)(v7 + 56);
    if ( !ResetEvent(*(HANDLE *)(v7 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  v11 = *(_DWORD *)(v6 + 192);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7) )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v7)(v7, 0, 0);
    v12 = (*(_DWORD *)(v7 + 56))-- == 1;
    if ( v12 && !SetEvent(*(HANDLE *)(v7 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
    v12 = (*(_DWORD *)(v2 + 56))-- == 1;
    if ( v12 && !SetEvent(*(HANDLE *)(v2 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  return v11;
}

```

## disassembly

```asm
0x18000c250  push    rbx
0x18000c252  push    rbp
0x18000c253  push    rsi
0x18000c254  push    rdi
0x18000c255  push    r14
0x18000c257  sub     rsp, 20h
0x18000c25b  mov     rsi, rcx
0x18000c25e  mov     rax, [rcx+8]
0x18000c262  xor     r8d, r8d
0x18000c265  xor     edx, edx
0x18000c267  add     rcx, 8
0x18000c26b  mov     rax, [rax]
0x18000c26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c273  mov     rbx, [rsi]
0x18000c276  test    rbx, rbx
0x18000c279  jz      loc_18000C59D
0x18000c27f  add     rbx, 200h
0x18000c286  mov     [rsp+48h+arg_8], rbx
0x18000c28b  mov     [rsp+48h+pExceptionObject], rbx
0x18000c290  mov     rax, [rbx]
0x18000c293  xor     r8d, r8d
0x18000c296  xor     edx, edx
0x18000c298  mov     rcx, rbx
0x18000c29b  mov     rax, [rax]
0x18000c29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a3  nop
0x18000c2a4  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000c2aa  call    cs:__imp_TlsGetValue
0x18000c2b0  cmp     [rbx+68h], rax
0x18000c2b4  jz      loc_18000C505
0x18000c2ba  mov     rax, [rbx]
0x18000c2bd  mov     rcx, rbx
0x18000c2c0  mov     rax, [rax+8]
0x18000c2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c9  nop
0x18000c2ca  mov     rbp, [rbx+58h]
0x18000c2ce  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000c2d4  call    cs:__imp_TlsGetValue
0x18000c2da  mov     r14, rax
0x18000c2dd  xor     r9d, r9d
0x18000c2e0  mov     r8, r14
0x18000c2e3  mov     rdx, rbp
0x18000c2e6  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000c2eb  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000c2f0  cmp     eax, 1
0x18000c2f3  jnz     loc_18000C4BF
0x18000c2f9  mov     [rsp+48h+arg_10], rbx
0x18000c2fe  mov     rax, [rbx]
0x18000c301  xor     r8d, r8d
0x18000c304  xor     edx, edx
0x18000c306  mov     rcx, rbx
0x18000c309  mov     rax, [rax]
0x18000c30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c311  nop
0x18000c312  cmp     dword ptr [rbx+3Ch], 0
0x18000c316  jnz     loc_18000C547
0x18000c31c  inc     dword ptr [rbx+38h]
0x18000c31f  mov     rcx, [rbx+48h]; hEvent
0x18000c323  call    cs:__imp_ResetEvent
0x18000c329  test    eax, eax
0x18000c32b  jz      loc_18000C5C8
0x18000c331  mov     rax, [rbx]
0x18000c334  mov     rcx, rbx
0x18000c337  mov     rax, [rax+8]
0x18000c33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c340  nop
0x18000c341  mov     rax, [rsi+8]
0x18000c345  lea     rcx, [rsi+8]
0x18000c349  mov     rax, [rax+8]
0x18000c34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c352  mov     r14, [rsi]
0x18000c355  lea     rdi, [r14+38h]
0x18000c359  mov     [rsp+48h+pExceptionObject], rdi
0x18000c35e  mov     rax, [rdi]
0x18000c361  xor     r8d, r8d
0x18000c364  xor     edx, edx
0x18000c366  mov     rcx, rdi
0x18000c369  mov     rax, [rax]
0x18000c36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c371  nop
0x18000c372  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000c378  call    cs:__imp_TlsGetValue
0x18000c37e  cmp     [rdi+68h], rax
0x18000c382  jz      loc_18000C526
0x18000c388  mov     rax, [rdi]
0x18000c38b  mov     rcx, rdi
0x18000c38e  mov     rax, [rax+8]
0x18000c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c397  nop
0x18000c398  mov     rsi, [rdi+58h]
0x18000c39c  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000c3a2  call    cs:__imp_TlsGetValue
0x18000c3a8  mov     rbp, rax
0x18000c3ab  xor     r9d, r9d
0x18000c3ae  mov     r8, rbp
0x18000c3b1  mov     rdx, rsi
0x18000c3b4  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000c3b9  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000c3be  cmp     eax, 1
0x18000c3c1  jnz     loc_18000C4E2
0x18000c3c7  mov     [rsp+48h+arg_10], rdi
0x18000c3cc  mov     rax, [rdi]
0x18000c3cf  xor     r8d, r8d
0x18000c3d2  xor     edx, edx
0x18000c3d4  mov     rcx, rdi
0x18000c3d7  mov     rax, [rax]
0x18000c3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3df  nop
0x18000c3e0  cmp     dword ptr [rdi+3Ch], 0
0x18000c3e4  jnz     loc_18000C572
0x18000c3ea  inc     dword ptr [rdi+38h]
0x18000c3ed  mov     rcx, [rdi+48h]; hEvent
0x18000c3f1  call    cs:__imp_ResetEvent
0x18000c3f7  test    eax, eax
0x18000c3f9  jz      loc_18000C5E4
0x18000c3ff  mov     rax, [rdi]
0x18000c402  mov     rcx, rdi
0x18000c405  mov     rax, [rax+8]
0x18000c409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c40e  nop
0x18000c40f  mov     esi, [r14+0C0h]
0x18000c416  mov     rax, [rdi]
0x18000c419  mov     rcx, rdi
0x18000c41c  mov     rax, [rax+10h]
0x18000c420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c425  test    eax, eax
0x18000c427  jnz     short loc_18000C464
0x18000c429  mov     rax, [rdi]
0x18000c42c  xor     r8d, r8d
0x18000c42f  xor     edx, edx
0x18000c431  mov     rcx, rdi
0x18000c434  mov     rax, [rax]
0x18000c437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c43c  add     dword ptr [rdi+38h], 0FFFFFFFFh
0x18000c440  jnz     short loc_18000C454
0x18000c442  mov     rcx, [rdi+48h]; hEvent
0x18000c446  call    cs:__imp_SetEvent
0x18000c44c  test    eax, eax
0x18000c44e  jz      loc_18000C600
0x18000c454  mov     rax, [rdi]
0x18000c457  mov     rcx, rdi
0x18000c45a  mov     rax, [rax+8]
0x18000c45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c463  nop
0x18000c464  mov     rax, [rbx]
0x18000c467  mov     rcx, rbx
0x18000c46a  mov     rax, [rax+10h]
0x18000c46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c473  test    eax, eax
0x18000c475  jnz     short loc_18000C4B2
0x18000c477  mov     rax, [rbx]
0x18000c47a  xor     r8d, r8d
0x18000c47d  xor     edx, edx
0x18000c47f  mov     rcx, rbx
0x18000c482  mov     rax, [rax]
0x18000c485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c48a  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18000c48e  jnz     short loc_18000C4A2
0x18000c490  mov     rcx, [rbx+48h]; hEvent
0x18000c494  call    cs:__imp_SetEvent
0x18000c49a  test    eax, eax
0x18000c49c  jz      loc_18000C61C
0x18000c4a2  mov     rcx, [rbx]
0x18000c4a5  mov     rax, [rcx+8]
0x18000c4a9  mov     rcx, rbx
0x18000c4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4b1  nop
0x18000c4b2  mov     eax, esi
0x18000c4b4  add     rsp, 20h
0x18000c4b8  pop     r14
0x18000c4ba  pop     rdi
0x18000c4bb  pop     rsi
0x18000c4bc  pop     rbp
0x18000c4bd  pop     rbx
0x18000c4be  retn
0x18000c4bf  cmp     eax, 2
0x18000c4c2  jnz     loc_18000C2DD
0x18000c4c8  mov     dword ptr [rsp+48h+pExceptionObject], 80100002h
0x18000c4d0  lea     rdx, _TI1K; pThrowInfo
0x18000c4d7  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c4dc  call    _CxxThrowException_0
0x18000c4e2  cmp     eax, 2
0x18000c4e5  jnz     loc_18000C3AB
0x18000c4eb  mov     dword ptr [rsp+48h+pExceptionObject], 80100002h
0x18000c4f3  lea     rdx, _TI1K; pThrowInfo
0x18000c4fa  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c4ff  call    _CxxThrowException_0
0x18000c505  inc     dword ptr [rbx+38h]
0x18000c508  mov     rcx, rbx; this
0x18000c50b  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000c510  nop
0x18000c511  mov     rax, [rbx]
0x18000c514  mov     rcx, rbx
0x18000c517  mov     rax, [rax+8]
0x18000c51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c520  nop
0x18000c521  jmp     loc_18000C341
0x18000c526  inc     dword ptr [rdi+38h]
0x18000c529  mov     rcx, rdi; this
0x18000c52c  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000c531  nop
0x18000c532  mov     rax, [rdi]
0x18000c535  mov     rcx, rdi
0x18000c538  mov     rax, [rax+8]
0x18000c53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c541  nop
0x18000c542  jmp     loc_18000C40F
0x18000c547  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000c54d  call    cs:__imp_TlsGetValue
0x18000c553  cmp     [rbx+68h], rax
0x18000c557  jz      loc_18000C31C
0x18000c55d  mov     rax, [rbx]
0x18000c560  mov     rcx, rbx
0x18000c563  mov     rax, [rax+8]
0x18000c567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c56c  nop
0x18000c56d  jmp     loc_18000C2CA
0x18000c572  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000c578  call    cs:__imp_TlsGetValue
0x18000c57e  cmp     [rdi+68h], rax
0x18000c582  jz      loc_18000C3EA
0x18000c588  mov     rax, [rdi]
0x18000c58b  mov     rcx, rdi
0x18000c58e  mov     rax, [rax+8]
0x18000c592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c597  nop
0x18000c598  jmp     loc_18000C398
0x18000c59d  mov     rax, [rsi+8]
0x18000c5a1  lea     rcx, [rsi+8]
0x18000c5a5  mov     rax, [rax+8]
0x18000c5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ae  mov     dword ptr [rsp+48h+pExceptionObject], 80100017h
0x18000c5b6  lea     rdx, _TI1K; pThrowInfo
0x18000c5bd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c5c2  call    _CxxThrowException_0
0x18000c5c8  call    cs:__imp_GetLastError
0x18000c5ce  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x18000c5d2  lea     rdx, _TI1K; pThrowInfo
0x18000c5d9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c5de  call    _CxxThrowException_0
0x18000c5e4  call    cs:__imp_GetLastError
0x18000c5ea  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x18000c5ee  lea     rdx, _TI1K; pThrowInfo
0x18000c5f5  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c5fa  call    _CxxThrowException_0
0x18000c600  call    cs:__imp_GetLastError
0x18000c606  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x18000c60a  lea     rdx, _TI1K; pThrowInfo
0x18000c611  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c616  call    _CxxThrowException_0
0x18000c61c  call    cs:__imp_GetLastError
0x18000c622  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x18000c626  lea     rdx, _TI1K; pThrowInfo
0x18000c62d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c632  call    _CxxThrowException_0
```
