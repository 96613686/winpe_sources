# CLockRead::CLockRead(CAccessLock *)

- ea: `0x18000c6b0`
- end: `0x18000c85c`
- name: `??0CLockRead@@QEAA@PEAVCAccessLock@@@Z`
- size: `428`
- prototype: `CLockRead *__fastcall(CLockRead *__hidden this, struct CAccessLock *)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x18000468c`
- `0x180004730`
- `0x180004af8`
- `0x18000fb8c`
- `0x180010868`
- `0x180010d10`
- `0x1800122d0`
- `0x180013740`
- `0x180019c1c`
- `0x18002f890`
- `0x18002fa94`
- `0x18002fb6c`
- `0x18002fc20`
- `0x18002fcf0`

## callees

- `0x18000c6b0`
- `0x18000c870`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c76b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c7c9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c76b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c7c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c840`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c6e7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c717`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c7fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c6e7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c717`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c7fc`

## pseudocode

```c
CLockRead *__fastcall CLockRead::CLockRead(CLockRead *this, struct CAccessLock *a2)
{
  struct CAccessLock *v2; // rbx
  __int64 v4; // rbx
  LPVOID Value; // rsi
  unsigned int v6; // eax
  struct CAccessLock *v7; // rcx
  LPVOID v9; // rax
  ulong pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  struct CAccessLock *v11; // [rsp+38h] [rbp+10h]

  v2 = a2;
  *(_QWORD *)this = a2;
  v11 = a2;
  (**(void (__fastcall ***)(struct CAccessLock *, _QWORD, _QWORD))a2)(a2, 0, 0);
  if ( *(LPVOID *)(*(_QWORD *)this + 104LL) == TlsGetValue(dwTlsIndex) )
  {
    ++*(_DWORD *)(*(_QWORD *)this + 56LL);
    if ( !ResetEvent(*(HANDLE *)(*(_QWORD *)this + 72LL)) )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
  }
  else
  {
    do
    {
      (*(void (__fastcall **)(struct CAccessLock *))(*(_QWORD *)v2 + 8LL))(v2);
      v4 = *(_QWORD *)(*(_QWORD *)this + 88LL);
      Value = TlsGetValue(dword_18004B240);
      while ( 1 )
      {
        v6 = WaitForAnyObject(0xFFFFFFFF, v4, Value, 0);
        if ( v6 == 1 )
          break;
        if ( v6 == 2 )
        {
          pExceptionObject = -2146435070;
          throw &pExceptionObject;
        }
      }
      v2 = *(struct CAccessLock **)this;
      v11 = v2;
      (**(void (__fastcall ***)(struct CAccessLock *, _QWORD, _QWORD))v2)(v2, 0, 0);
      v7 = *(struct CAccessLock **)this;
      if ( !*(_DWORD *)(*(_QWORD *)this + 60LL) )
        break;
      v9 = TlsGetValue(dwTlsIndex);
      v7 = *(struct CAccessLock **)this;
    }
    while ( *(LPVOID *)(*(_QWORD *)this + 104LL) != v9 );
    ++*((_DWORD *)v7 + 14);
    if ( !ResetEvent(*(HANDLE *)(*(_QWORD *)this + 72LL)) )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
  }
  (*(void (__fastcall **)(struct CAccessLock *))(*(_QWORD *)v2 + 8LL))(v2);
  return this;
}

```

## disassembly

```asm
0x18000c6b0  mov     [rsp+arg_10], rbx
0x18000c6b5  mov     [rsp+arg_18], rsi
0x18000c6ba  push    rdi
0x18000c6bb  sub     rsp, 20h
0x18000c6bf  mov     rbx, rdx
0x18000c6c2  mov     rdi, rcx
0x18000c6c5  mov     [rcx], rdx
0x18000c6c8  mov     [rsp+28h+arg_8], rdx
0x18000c6cd  mov     rax, [rdx]
0x18000c6d0  xor     r8d, r8d
0x18000c6d3  xor     edx, edx
0x18000c6d5  mov     rcx, rbx
0x18000c6d8  mov     rax, [rax]
0x18000c6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6e0  nop
0x18000c6e1  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000c6e7  call    cs:__imp_TlsGetValue
0x18000c6ed  mov     rcx, [rdi]
0x18000c6f0  cmp     [rcx+68h], rax
0x18000c6f4  jz      loc_18000C7BF
0x18000c6fa  mov     rax, [rbx]
0x18000c6fd  mov     rcx, rbx
0x18000c700  mov     rax, [rax+8]
0x18000c704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c709  nop
0x18000c70a  mov     rax, [rdi]
0x18000c70d  mov     rbx, [rax+58h]
0x18000c711  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000c717  call    cs:__imp_TlsGetValue
0x18000c71d  mov     rsi, rax
0x18000c720  xor     r9d, r9d
0x18000c723  mov     r8, rsi
0x18000c726  mov     rdx, rbx
0x18000c729  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000c72e  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000c733  cmp     eax, 1
0x18000c736  jnz     short loc_18000C79C
0x18000c738  mov     rbx, [rdi]
0x18000c73b  mov     [rsp+28h+arg_8], rbx
0x18000c740  mov     rax, [rbx]
0x18000c743  xor     r8d, r8d
0x18000c746  xor     edx, edx
0x18000c748  mov     rcx, rbx
0x18000c74b  mov     rax, [rax]
0x18000c74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c753  nop
0x18000c754  mov     rcx, [rdi]
0x18000c757  cmp     dword ptr [rcx+3Ch], 0
0x18000c75b  jnz     loc_18000C7F6
0x18000c761  inc     dword ptr [rcx+38h]
0x18000c764  mov     rcx, [rdi]
0x18000c767  mov     rcx, [rcx+48h]; hEvent
0x18000c76b  call    cs:__imp_ResetEvent
0x18000c771  test    eax, eax
0x18000c773  jz      loc_18000C840
0x18000c779  mov     rax, [rbx]
0x18000c77c  mov     rcx, rbx
0x18000c77f  mov     rax, [rax+8]
0x18000c783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c788  nop
0x18000c789  mov     rax, rdi
0x18000c78c  mov     rbx, [rsp+28h+arg_10]
0x18000c791  mov     rsi, [rsp+28h+arg_18]
0x18000c796  add     rsp, 20h
0x18000c79a  pop     rdi
0x18000c79b  retn
0x18000c79c  cmp     eax, 2
0x18000c79f  jnz     loc_18000C720
0x18000c7a5  mov     [rsp+28h+pExceptionObject], 80100002h
0x18000c7ad  lea     rdx, _TI1K; pThrowInfo
0x18000c7b4  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c7b9  call    _CxxThrowException_0
0x18000c7bf  inc     dword ptr [rcx+38h]
0x18000c7c2  mov     rcx, [rdi]
0x18000c7c5  mov     rcx, [rcx+48h]; hEvent
0x18000c7c9  call    cs:__imp_ResetEvent
0x18000c7cf  test    eax, eax
0x18000c7d1  jz      short loc_18000C824
0x18000c7d3  mov     rax, [rbx]
0x18000c7d6  mov     rcx, rbx
0x18000c7d9  mov     rax, [rax+8]
0x18000c7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7e2  nop
0x18000c7e3  mov     rax, rdi
0x18000c7e6  mov     rbx, [rsp+28h+arg_10]
0x18000c7eb  mov     rsi, [rsp+28h+arg_18]
0x18000c7f0  add     rsp, 20h
0x18000c7f4  pop     rdi
0x18000c7f5  retn
0x18000c7f6  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000c7fc  call    cs:__imp_TlsGetValue
0x18000c802  mov     rcx, [rdi]
0x18000c805  cmp     [rcx+68h], rax
0x18000c809  jz      loc_18000C761
0x18000c80f  mov     rax, [rbx]
0x18000c812  mov     rcx, rbx
0x18000c815  mov     rax, [rax+8]
0x18000c819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c81e  nop
0x18000c81f  jmp     loc_18000C70A
0x18000c824  call    cs:__imp_GetLastError
0x18000c82a  mov     [rsp+28h+pExceptionObject], eax
0x18000c82e  lea     rdx, _TI1K; pThrowInfo
0x18000c835  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c83a  call    _CxxThrowException_0
0x18000c840  call    cs:__imp_GetLastError
0x18000c846  mov     [rsp+28h+pExceptionObject], eax
0x18000c84a  lea     rdx, _TI1K; pThrowInfo
0x18000c851  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c856  call    _CxxThrowException_0
```
