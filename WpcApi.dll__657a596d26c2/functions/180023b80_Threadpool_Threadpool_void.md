# Threadpool::~Threadpool(void)

- ea: `0x180023b80`
- end: `0x180023d75`
- name: `??1Threadpool@@QEAA@XZ`
- size: `501`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002b3a0`

## callees

- `0x180003d20`
- `0x1800195c4`
- `0x1800212d8`
- `0x1800238ec`
- `0x180023af4`
- `0x180023b80`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023bcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023bcb`
- `KERNEL32!CloseThreadpool` at `0x180023ce1`
- `KERNEL32!CloseThreadpool` at `0x180023ce1`
- `KERNEL32!SleepConditionVariableSRW` at `0x180023c9f`
- `KERNEL32!SleepConditionVariableSRW` at `0x180023c9f`
- `KERNEL32!TlsGetValue` at `0x180023c17`
- `KERNEL32!TlsGetValue` at `0x180023c17`
- `KERNEL32!TlsSetValue` at `0x180023c28`
- `KERNEL32!TlsSetValue` at `0x180023c28`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Threadpool::~Threadpool(volatile signed __int32 **this)
{
  RTL_CONDITION_VARIABLE *v2; // rcx
  _QWORD *i; // rdi
  __int64 v4; // rbx
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  _QWORD *v7; // rdx
  unsigned int Value; // eax
  RTL_CONDITION_VARIABLE *v9; // rbx
  RTL_SRWLOCK *v10; // rdi
  unsigned __int64 v11; // rdx
  volatile signed __int32 *v12; // rbx
  signed int LastError; // eax
  __int64 v14; // [rsp+20h] [rbp-58h] BYREF
  _QWORD **v15; // [rsp+28h] [rbp-50h]
  _QWORD pExceptionObject[9]; // [rsp+30h] [rbp-48h] BYREF
  char v17; // [rsp+A0h] [rbp+28h] BYREF

  v2 = (RTL_CONDITION_VARIABLE *)*this;
  if ( v2 )
  {
    (*((void (__fastcall **)(RTL_CONDITION_VARIABLE *, __int64 *))v2[11].Ptr + 6))(v2 + 11, &v14);
    for ( i = *v15; i; i = (_QWORD *)i[11] )
    {
      (*(void (__fastcall **)(_QWORD *))(*i + 8LL))(i);
      v4 = i[8];
      if ( (_DWORD)v4 == GetCurrentThreadId() )
      {
        v5 = i[10];
        v6 = i + 11;
        if ( v5 )
          *(_QWORD *)(v5 + 88) = *v6;
        v7 = (_QWORD *)*v6;
        if ( *v6 )
        {
          v7[10] = i[10];
          v7 = (_QWORD *)*v6;
        }
        if ( i == *v15 )
          *v15 = v7;
      }
    }
    Value = (unsigned int)TlsGetValue(dwTlsIndex);
    TlsSetValue(dwTlsIndex, (LPVOID)(int)(Value + 1));
    while ( *v15 )
    {
      v9 = (RTL_CONDITION_VARIABLE *)(*this + 28);
      v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
      pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_701992cd54336967b334c5b58053aba8_,void,>::`vftable';
      pExceptionObject[1] = v9;
      pExceptionObject[7] = pExceptionObject;
      Threading::CancellationCallback::CancellationCallback((__int64)&v17, (__int64)pExceptionObject);
      if ( qword_18004A730 )
        v11 = *(_QWORD *)qword_18004A730 / 0x2710uLL;
      else
        LODWORD(v11) = -1;
      if ( !SleepConditionVariableSRW(v9, v10, v11, 0) && GetLastError() != 1460 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, LastError);
        throw (ErrorCodeException *)pExceptionObject;
      }
      Threading::CancellationCallback::~CancellationCallback((Threading::CancellationCallback *)&v17);
    }
    Threading::PreventCancellation::~PreventCancellation((Threading::PreventCancellation *)&v17);
    CloseThreadpool(*((PTP_POOL *)*this + 10));
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
  }
  v12 = this[1];
  if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
    if ( !_InterlockedDecrement(v12 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
  }
}

```

## disassembly

```asm
0x180023b80  push    rbp
0x180023b82  push    rbx
0x180023b83  push    rsi
0x180023b84  push    rdi
0x180023b85  mov     rbp, rsp
0x180023b88  sub     rsp, 78h
0x180023b8c  mov     rsi, rcx
0x180023b8f  mov     rcx, [rcx]
0x180023b92  test    rcx, rcx
0x180023b95  jz      loc_180023CFE
0x180023b9b  add     rcx, 58h ; 'X'
0x180023b9f  mov     rax, [rcx]
0x180023ba2  lea     rdx, [rbp+var_58]
0x180023ba6  mov     rax, [rax+30h]
0x180023baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023baf  mov     rax, [rbp+var_50]
0x180023bb3  mov     rdi, [rax]
0x180023bb6  jmp     short loc_180023C0C
0x180023bb8  mov     rax, [rdi]
0x180023bbb  mov     rcx, rdi
0x180023bbe  mov     rax, [rax+8]
0x180023bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bc7  mov     rbx, [rdi+40h]
0x180023bcb  call    cs:__imp_GetCurrentThreadId
0x180023bd1  cmp     ebx, eax
0x180023bd3  jnz     short loc_180023C08
0x180023bd5  mov     rdx, [rdi+50h]
0x180023bd9  lea     rcx, [rdi+58h]
0x180023bdd  test    rdx, rdx
0x180023be0  jz      short loc_180023BE9
0x180023be2  mov     rax, [rcx]
0x180023be5  mov     [rdx+58h], rax
0x180023be9  mov     rdx, [rcx]
0x180023bec  test    rdx, rdx
0x180023bef  jz      short loc_180023BFC
0x180023bf1  mov     rax, [rdi+50h]
0x180023bf5  mov     [rdx+50h], rax
0x180023bf9  mov     rdx, [rcx]
0x180023bfc  mov     rax, [rbp+var_50]
0x180023c00  cmp     rdi, [rax]
0x180023c03  jnz     short loc_180023C08
0x180023c05  mov     [rax], rdx
0x180023c08  mov     rdi, [rdi+58h]
0x180023c0c  test    rdi, rdi
0x180023c0f  jnz     short loc_180023BB8
0x180023c11  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180023c17  call    cs:__imp_TlsGetValue
0x180023c1d  inc     eax
0x180023c1f  movsxd  rdx, eax; lpTlsValue
0x180023c22  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180023c28  call    cs:__imp_TlsSetValue
0x180023c2e  jmp     loc_180023CC3
0x180023c33  mov     rbx, [rsi]
0x180023c36  add     rbx, 70h ; 'p'
0x180023c3a  mov     rcx, [rbp+var_58]
0x180023c3e  mov     rax, [rcx]
0x180023c41  mov     rax, [rax+20h]
0x180023c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c4a  mov     rdi, rax
0x180023c4d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_701992cd54336967b334c5b58053aba8_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_701992cd54336967b334c5b58053aba8_,void,>::`vftable'
0x180023c54  mov     [rbp+pExceptionObject], rax
0x180023c58  mov     [rbp+var_40], rbx
0x180023c5c  lea     rax, [rbp+pExceptionObject]
0x180023c60  mov     [rbp+var_10], rax
0x180023c64  lea     rdx, [rbp+pExceptionObject]
0x180023c68  lea     rcx, [rbp+arg_0]
0x180023c6c  call    ??0CancellationCallback@Threading@@QEAA@V?$function@$$A6AXXZ@std@@AEBV?$Optional@VTimeSpan@@@@@Z; Threading::CancellationCallback::CancellationCallback(std::function<void (void)>,Optional<TimeSpan> const &)
0x180023c71  mov     rcx, cs:qword_18004A730
0x180023c78  test    rcx, rcx
0x180023c7b  jz      short loc_180023C90
0x180023c7d  mov     rax, 346DC5D63886594Bh
0x180023c87  mul     qword ptr [rcx]
0x180023c8a  shr     rdx, 0Bh
0x180023c8e  jmp     short loc_180023C93
0x180023c90  or      edx, 0FFFFFFFFh
0x180023c93  xor     r9d, r9d; Flags
0x180023c96  mov     r8d, edx; dwMilliseconds
0x180023c99  mov     rdx, rdi; SRWLock
0x180023c9c  mov     rcx, rbx; ConditionVariable
0x180023c9f  call    cs:__imp_SleepConditionVariableSRW
0x180023ca5  test    eax, eax
0x180023ca7  jnz     short loc_180023CBA
0x180023ca9  call    cs:__imp_GetLastError
0x180023caf  cmp     eax, 5B4h
0x180023cb4  jnz     loc_180023D47
0x180023cba  lea     rcx, [rbp+arg_0]; this
0x180023cbe  call    ??1CancellationCallback@Threading@@QEAA@XZ; Threading::CancellationCallback::~CancellationCallback(void)
0x180023cc3  mov     rax, [rbp+var_50]
0x180023cc7  cmp     qword ptr [rax], 0
0x180023ccb  jnz     loc_180023C33
0x180023cd1  lea     rcx, [rbp+arg_0]; this
0x180023cd5  call    ??1PreventCancellation@Threading@@QEAA@XZ; Threading::PreventCancellation::~PreventCancellation(void)
0x180023cda  mov     rcx, [rsi]
0x180023cdd  mov     rcx, [rcx+50h]; ptpp
0x180023ce1  call    cs:__imp_CloseThreadpool
0x180023ce7  nop
0x180023ce8  mov     rcx, [rbp+var_58]
0x180023cec  test    rcx, rcx
0x180023cef  jz      short loc_180023CFE
0x180023cf1  mov     rax, [rcx]
0x180023cf4  mov     rax, [rax+18h]
0x180023cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cfd  nop
0x180023cfe  mov     rbx, [rsi+8]
0x180023d02  test    rbx, rbx
0x180023d05  jz      short loc_180023D3E
0x180023d07  or      edi, 0FFFFFFFFh
0x180023d0a  mov     eax, edi
0x180023d0c  lock xadd [rbx+8], eax
0x180023d11  add     eax, edi
0x180023d13  jnz     short loc_180023D3E
0x180023d15  mov     rax, [rbx]
0x180023d18  mov     rcx, rbx
0x180023d1b  mov     rax, [rax]
0x180023d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d23  mov     eax, edi
0x180023d25  lock xadd [rbx+0Ch], eax
0x180023d2a  add     eax, edi
0x180023d2c  jnz     short loc_180023D3E
0x180023d2e  mov     rax, [rbx]
0x180023d31  mov     rcx, rbx
0x180023d34  mov     rax, [rax+8]
0x180023d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d3d  nop
0x180023d3e  add     rsp, 78h
0x180023d42  pop     rdi
0x180023d43  pop     rsi
0x180023d44  pop     rbx
0x180023d45  pop     rbp
0x180023d46  retn
0x180023d47  call    cs:__imp_GetLastError
0x180023d4d  test    eax, eax
0x180023d4f  jle     short loc_180023D59
0x180023d51  movzx   eax, ax
0x180023d54  or      eax, 80070000h
0x180023d59  mov     edx, eax; int
0x180023d5b  lea     rcx, [rbp+pExceptionObject]; this
0x180023d5f  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180023d64  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180023d6b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180023d6f  call    _CxxThrowException_0
```
