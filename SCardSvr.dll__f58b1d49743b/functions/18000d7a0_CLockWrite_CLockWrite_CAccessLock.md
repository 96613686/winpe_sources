# CLockWrite::CLockWrite(CAccessLock *)

- ea: `0x18000d7a0`
- end: `0x18000d9ba`
- name: `??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z`
- size: `538`
- prototype: `CLockWrite *__fastcall(CLockWrite *__hidden this, struct CAccessLock *)`
- caller_count: `30`
- callee_count: `5`
- tags: ``

## callers

- `0x180001950`
- `0x180003458`
- `0x18000371c`
- `0x1800039e0`
- `0x180003ff0`
- `0x18000457c`
- `0x18000d9c0`
- `0x18000ecb0`
- `0x18000f1c0`
- `0x180015558`
- `0x180017a84`
- `0x180017c60`
- `0x180018d4c`
- `0x180019dd8`
- `0x18001a390`
- `0x18001a748`
- `0x18001af40`
- `0x18002a970`
- `0x18002ab4c`
- `0x18002bf80`
- `0x18002ccd0`
- `0x18002d530`
- `0x18002d62c`
- `0x18002d6cc`
- `0x18002d870`
- `0x18002d928`
- `0x18002daec`
- `0x18002dcc4`
- `0x18002e524`
- `0x18003611a`

## callees

- `0x18000c870`
- `0x18000d7a0`
- `0x180012380`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d87e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d87e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d98d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d7ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d808`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d862`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d8b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d7ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d808`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d862`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d8b1`

## pseudocode

```c
CLockWrite *__fastcall CLockWrite::CLockWrite(CLockWrite *this, struct CAccessLock *a2)
{
  __int64 v4; // rbx
  LPVOID Value; // rsi
  unsigned int v6; // eax
  struct CCriticalSectionObject *v7; // rbx
  __int64 v8; // rbx
  LPVOID v9; // rsi
  unsigned int v10; // eax
  struct CCriticalSectionObject *v11; // rbx
  const unsigned __int8 *v12; // r8
  const unsigned __int8 *v13; // r9
  CAccessLock **v15; // rbx
  ulong pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  ulong LastError; // [rsp+24h] [rbp-24h] BYREF
  ulong v18; // [rsp+28h] [rbp-20h] BYREF
  struct CCriticalSectionObject **v19; // [rsp+50h] [rbp+8h] BYREF
  int v20; // [rsp+58h] [rbp+10h]
  int v21; // [rsp+60h] [rbp+18h]
  struct CCriticalSectionObject *v22; // [rsp+68h] [rbp+20h] BYREF

  v19 = (struct CCriticalSectionObject **)this;
  *(_QWORD *)this = a2;
  (**(void (__fastcall ***)(struct CAccessLock *, _QWORD, _QWORD))a2)(a2, 0, 0);
  if ( *(LPVOID *)(*(_QWORD *)this + 104LL) == TlsGetValue(dwTlsIndex) )
  {
    ++*(_DWORD *)(*(_QWORD *)this + 60LL);
    (*(void (__fastcall **)(struct CAccessLock *))(*(_QWORD *)a2 + 8LL))(a2);
    return this;
  }
  else
  {
    v20 = 0;
    v21 = 0;
    (*(void (__fastcall **)(struct CAccessLock *))(*(_QWORD *)a2 + 8LL))(a2);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      while ( 1 )
      {
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
        v7 = *(struct CCriticalSectionObject **)this;
        v22 = v7;
        (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))v7)(v7, 0, 0);
        if ( !*(_DWORD *)(*(_QWORD *)this + 60LL) )
          break;
        (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v7 + 8LL))(v7);
      }
      *(_DWORD *)(*(_QWORD *)this + 60LL) = 1;
      *(_QWORD *)(*(_QWORD *)this + 104LL) = TlsGetValue(dwTlsIndex);
      v20 = 1;
      if ( !ResetEvent(*(HANDLE *)(*(_QWORD *)this + 88LL)) )
      {
        LastError = GetLastError();
        throw &LastError;
      }
      v21 = 1;
      (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v7 + 8LL))(v7);
      while ( 1 )
      {
        v8 = *(_QWORD *)(*(_QWORD *)this + 72LL);
        v9 = TlsGetValue(dword_18004B240);
        while ( 1 )
        {
          v10 = WaitForAnyObject(0xFFFFFFFF, v8, v9, 0);
          if ( v10 == 1 )
            break;
          if ( v10 == 2 )
          {
            v18 = -2146435070;
            throw &v18;
          }
        }
        v11 = *(struct CCriticalSectionObject **)this;
        v22 = v11;
        (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))v11)(v11, 0, 0);
        if ( !*(_DWORD *)(*(_QWORD *)this + 56LL) )
          break;
        COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v22);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', 0) )
      {
        if ( v20 )
        {
          v15 = v19;
          COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v19, *v19, v12, v13);
          if ( !--*((_DWORD *)*v15 + 15) )
          {
            *((_QWORD *)*v15 + 13) = 0;
            if ( v21 )
              CAccessLock::SignalNoWriters(*v15);
          }
          COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v19);
        }
        throw;
      }
    }
    (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v11 + 8LL))(v11);
    return this;
  }
}

```

## disassembly

```asm
0x18000d7a0  mov     [rsp+arg_0], rcx
0x18000d7a5  push    rbx
0x18000d7a6  push    rsi
0x18000d7a7  push    rdi
0x18000d7a8  sub     rsp, 30h
0x18000d7ac  mov     rbx, rdx
0x18000d7af  mov     rdi, rcx
0x18000d7b2  mov     [rcx], rdx
0x18000d7b5  mov     rax, [rdx]
0x18000d7b8  xor     r8d, r8d
0x18000d7bb  xor     edx, edx
0x18000d7bd  mov     rcx, rbx
0x18000d7c0  mov     rax, [rax]
0x18000d7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c8  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000d7ce  call    cs:__imp_TlsGetValue
0x18000d7d4  mov     rcx, [rdi]
0x18000d7d7  cmp     [rcx+68h], rax
0x18000d7db  jz      loc_18000D95A
0x18000d7e1  xor     eax, eax
0x18000d7e3  mov     [rsp+48h+arg_8], eax
0x18000d7e7  mov     [rsp+48h+arg_10], eax
0x18000d7eb  mov     rax, [rbx]
0x18000d7ee  mov     rcx, rbx
0x18000d7f1  mov     rax, [rax+8]
0x18000d7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7fa  nop
0x18000d7fb  mov     rax, [rdi]
0x18000d7fe  mov     rbx, [rax+58h]
0x18000d802  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000d808  call    cs:__imp_TlsGetValue
0x18000d80e  mov     rsi, rax
0x18000d811  xor     r9d, r9d
0x18000d814  mov     r8, rsi
0x18000d817  mov     rdx, rbx
0x18000d81a  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000d81f  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000d824  cmp     eax, 1
0x18000d827  jnz     loc_18000D915
0x18000d82d  mov     rbx, [rdi]
0x18000d830  mov     [rsp+48h+arg_18], rbx
0x18000d835  mov     rax, [rbx]
0x18000d838  xor     r8d, r8d
0x18000d83b  xor     edx, edx
0x18000d83d  mov     rcx, rbx
0x18000d840  mov     rax, [rax]
0x18000d843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d848  nop
0x18000d849  mov     rcx, [rdi]
0x18000d84c  mov     eax, [rcx+3Ch]
0x18000d84f  test    eax, eax
0x18000d851  jnz     loc_18000D978
0x18000d857  inc     eax
0x18000d859  mov     [rcx+3Ch], eax
0x18000d85c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000d862  call    cs:__imp_TlsGetValue
0x18000d868  mov     rcx, [rdi]
0x18000d86b  mov     [rcx+68h], rax
0x18000d86f  mov     [rsp+48h+arg_8], 1
0x18000d877  mov     rcx, [rdi]
0x18000d87a  mov     rcx, [rcx+58h]; hEvent
0x18000d87e  call    cs:__imp_ResetEvent
0x18000d884  test    eax, eax
0x18000d886  jz      loc_18000D98D
0x18000d88c  mov     [rsp+48h+arg_10], 1
0x18000d894  mov     rax, [rbx]
0x18000d897  mov     rcx, rbx
0x18000d89a  mov     rax, [rax+8]
0x18000d89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a3  nop
0x18000d8a4  mov     rax, [rdi]
0x18000d8a7  mov     rbx, [rax+48h]
0x18000d8ab  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000d8b1  call    cs:__imp_TlsGetValue
0x18000d8b7  mov     rsi, rax
0x18000d8ba  xor     r9d, r9d
0x18000d8bd  mov     r8, rsi
0x18000d8c0  mov     rdx, rbx
0x18000d8c3  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000d8c8  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000d8cd  cmp     eax, 1
0x18000d8d0  jnz     short loc_18000D937
0x18000d8d2  mov     rbx, [rdi]
0x18000d8d5  mov     [rsp+48h+arg_18], rbx
0x18000d8da  mov     rax, [rbx]
0x18000d8dd  xor     r8d, r8d
0x18000d8e0  xor     edx, edx
0x18000d8e2  mov     rcx, rbx
0x18000d8e5  mov     rax, [rax]
0x18000d8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ed  mov     rax, [rdi]
0x18000d8f0  cmp     dword ptr [rax+38h], 0
0x18000d8f4  jnz     loc_18000D9A9
0x18000d8fa  mov     rax, [rbx]
0x18000d8fd  mov     rcx, rbx
0x18000d900  mov     rax, [rax+8]
0x18000d904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d909  nop
0x18000d90a  mov     rax, rdi
0x18000d90d  add     rsp, 30h
0x18000d911  pop     rdi
0x18000d912  pop     rsi
0x18000d913  pop     rbx
0x18000d914  retn
0x18000d915  cmp     eax, 2
0x18000d918  jnz     loc_18000D811
0x18000d91e  mov     [rsp+48h+pExceptionObject], 80100002h
0x18000d926  lea     rdx, _TI1K; pThrowInfo
0x18000d92d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000d932  call    _CxxThrowException_0
0x18000d937  cmp     eax, 2
0x18000d93a  jnz     loc_18000D8BA
0x18000d940  mov     [rsp+48h+var_20], 80100002h
0x18000d948  lea     rdx, _TI1K; pThrowInfo
0x18000d94f  lea     rcx, [rsp+48h+var_20]; pExceptionObject
0x18000d954  call    _CxxThrowException_0
0x18000d95a  inc     dword ptr [rcx+3Ch]
0x18000d95d  mov     rax, [rbx]
0x18000d960  mov     rcx, rbx
0x18000d963  mov     rax, [rax+8]
0x18000d967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d96c  nop
0x18000d96d  mov     rax, rdi
0x18000d970  add     rsp, 30h
0x18000d974  pop     rdi
0x18000d975  pop     rsi
0x18000d976  pop     rbx
0x18000d977  retn
0x18000d978  mov     rax, [rbx]
0x18000d97b  mov     rcx, rbx
0x18000d97e  mov     rax, [rax+8]
0x18000d982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d987  nop
0x18000d988  jmp     loc_18000D7FB
0x18000d98d  call    cs:__imp_GetLastError
0x18000d993  mov     [rsp+48h+var_24], eax
0x18000d997  lea     rdx, _TI1K; pThrowInfo
0x18000d99e  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x18000d9a3  call    _CxxThrowException_0
0x18000d9a9  lea     rcx, [rsp+48h+arg_18]; this
0x18000d9ae  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18000d9b3  jmp     loc_18000D8A4
```
