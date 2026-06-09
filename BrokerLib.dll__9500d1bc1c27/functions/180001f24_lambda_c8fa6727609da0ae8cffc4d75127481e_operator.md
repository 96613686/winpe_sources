# _lambda_c8fa6727609da0ae8cffc4d75127481e_::operator()

- ea: `0x180001f24`
- end: `0x180001ff1`
- name: `_lambda_c8fa6727609da0ae8cffc4d75127481e_::operator()`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d70`

## callees

- `0x180001f24`
- `0x1800026b4`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001f52`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001f52`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001f80`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001f80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall lambda_c8fa6727609da0ae8cffc4d75127481e_::operator()(
        Broker::BrokerBase **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char *a5))(_QWORD, _QWORD, __int64, char *)
{
  unsigned int v6; // esi
  Broker::BrokerBase *v8; // rbx
  void (__fastcall *v9)(_QWORD, __int64, __int64, char *); // rax
  void (__fastcall *v10)(_QWORD, _QWORD, char *); // rax
  __int64 (__fastcall *result)(_QWORD, _QWORD, __int64, char *); // rax

  v6 = a2;
  v8 = *a1;
  v9 = (void (__fastcall *)(_QWORD, __int64, __int64, char *))*((_QWORD *)*a1 + 22);
  if ( v9 )
    v9(*((_QWORD *)v8 + 1), a2, a3, a5);
  RtlAcquireSRWLockExclusive(v8);
  GetCurrentThreadId();
  Broker::BrokerBase::OnUserLogoff(*a1, a3, v6, a5);
  RtlReleaseSRWLockExclusive(v8);
  v10 = (void (__fastcall *)(_QWORD, _QWORD, char *))*((_QWORD *)*a1 + 3);
  if ( v10 )
    v10(*((_QWORD *)*a1 + 1), v6, a5);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, char *))*((_QWORD *)*a1 + 23);
  if ( result )
    return (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, char *))result(*((_QWORD *)*a1 + 1), v6, a3, a5);
  return result;
}

```

## disassembly

```asm
0x180001f24  push    rbx
0x180001f26  push    rsi
0x180001f27  push    rdi
0x180001f28  push    r14
0x180001f2a  sub     rsp, 48h
0x180001f2e  mov     r14, r8
0x180001f31  mov     esi, edx
0x180001f33  mov     rdi, rcx
0x180001f36  mov     rbx, [rcx]
0x180001f39  mov     [rsp+68h+var_38], rbx
0x180001f3e  mov     [rsp+68h+var_30], 0
0x180001f43  mov     rax, [rbx+0B0h]
0x180001f4a  test    rax, rax
0x180001f4d  jnz     short loc_180001FB0
0x180001f4f  mov     rcx, rbx
0x180001f52  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001f58  call    cs:__imp_GetCurrentThreadId
0x180001f5e  mov     [rsp+68h+var_2C], eax
0x180001f62  mov     [rsp+68h+var_30], 1
0x180001f67  mov     r9, [rsp+68h+arg_20]; void *
0x180001f6f  mov     r8d, esi; unsigned int
0x180001f72  mov     rdx, r14; unsigned __int64
0x180001f75  mov     rcx, [rdi]; this
0x180001f78  call    ?OnUserLogoff@BrokerBase@Broker@@AEAAX_KKPEAX@Z; Broker::BrokerBase::OnUserLogoff(unsigned __int64,ulong,void *)
0x180001f7d  mov     rcx, rbx
0x180001f80  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001f86  mov     [rsp+68h+var_30], 0
0x180001f8b  mov     rcx, [rdi]
0x180001f8e  mov     rax, [rcx+18h]
0x180001f92  test    rax, rax
0x180001f95  jnz     short loc_180001FC3
0x180001f97  mov     rcx, [rdi]
0x180001f9a  mov     rax, [rcx+0B8h]
0x180001fa1  test    rax, rax
0x180001fa4  jnz     short loc_180001FD8
0x180001fa6  add     rsp, 48h
0x180001faa  pop     r14
0x180001fac  pop     rdi
0x180001fad  pop     rsi
0x180001fae  pop     rbx
0x180001faf  retn
0x180001fb0  mov     r9, [rsp+68h+arg_20]
0x180001fb8  mov     rcx, [rbx+8]
0x180001fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc1  jmp     short loc_180001F4F
0x180001fc3  mov     r8, [rsp+68h+arg_20]
0x180001fcb  mov     edx, esi
0x180001fcd  mov     rcx, [rcx+8]
0x180001fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fd6  jmp     short loc_180001F97
0x180001fd8  mov     r9, [rsp+68h+arg_20]
0x180001fe0  mov     r8, r14
0x180001fe3  mov     edx, esi
0x180001fe5  mov     rcx, [rcx+8]
0x180001fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fee  jmp     short loc_180001FA6
```
