# Threadpool::~Threadpool(void)

- ea: `0x180046a18`
- end: `0x180046b78`
- name: `??1Threadpool@@QEAA@XZ`
- size: `352`
- prototype: `void __fastcall(Threadpool *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800ac520`

## callees

- `0x180039960`
- `0x180046a18`
- `0x180047980`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046a68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046a68`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046ab5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046ab5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180046ac6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180046ac6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180046b0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180046b0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Threadpool::~Threadpool(Threadpool *this)
{
  RTL_CONDITION_VARIABLE *v2; // rcx
  _QWORD *i; // rdi
  __int64 v4; // rbx
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  _QWORD *v7; // rdx
  unsigned int Value; // eax
  RTL_CONDITION_VARIABLE *v9; // rbx
  RTL_SRWLOCK *v10; // rax
  volatile signed __int32 *v11; // rbx
  __int64 v12; // [rsp+20h] [rbp-18h] BYREF
  _QWORD **v13; // [rsp+28h] [rbp-10h]
  char v14; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(RTL_CONDITION_VARIABLE **)this;
  if ( v2 )
  {
    (*((void (__fastcall **)(RTL_CONDITION_VARIABLE *, __int64 *))v2[11].Ptr + 6))(v2 + 11, &v12);
    for ( i = *v13; i; i = (_QWORD *)i[11] )
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
        if ( i == *v13 )
          *v13 = v7;
      }
    }
    Value = (unsigned int)TlsGetValue(dwTlsIndex);
    TlsSetValue(dwTlsIndex, (LPVOID)(int)(Value + 1));
    while ( *v13 )
    {
      v9 = *(RTL_CONDITION_VARIABLE **)this;
      v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
      ConditionVariable::Wait(v9 + 14, v10);
    }
    Threading::PreventCancellation::~PreventCancellation((Threading::PreventCancellation *)&v14);
    CloseThreadpool(*(PTP_POOL *)(*(_QWORD *)this + 80LL));
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
  }
  v11 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v11 && _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
    if ( !_InterlockedDecrement(v11 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
  }
}

```

## disassembly

```asm
0x180046a18  mov     [rsp+arg_8], rbx
0x180046a1d  mov     [rsp+arg_10], rsi
0x180046a22  push    rdi
0x180046a23  sub     rsp, 30h
0x180046a27  mov     rsi, rcx
0x180046a2a  mov     rcx, [rcx]
0x180046a2d  test    rcx, rcx
0x180046a30  jz      loc_180046B28
0x180046a36  add     rcx, 58h ; 'X'
0x180046a3a  mov     rax, [rcx]
0x180046a3d  lea     rdx, [rsp+38h+var_18]
0x180046a42  mov     rax, [rax+30h]
0x180046a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a4b  mov     rax, [rsp+38h+var_10]
0x180046a50  mov     rdi, [rax]
0x180046a53  jmp     short loc_180046AAA
0x180046a55  mov     rax, [rdi]
0x180046a58  mov     rcx, rdi
0x180046a5b  mov     rax, [rax+8]
0x180046a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a64  mov     rbx, [rdi+40h]
0x180046a68  call    cs:__imp_GetCurrentThreadId
0x180046a6e  cmp     ebx, eax
0x180046a70  jnz     short loc_180046AA6
0x180046a72  mov     rdx, [rdi+50h]
0x180046a76  lea     rcx, [rdi+58h]
0x180046a7a  test    rdx, rdx
0x180046a7d  jz      short loc_180046A86
0x180046a7f  mov     rax, [rcx]
0x180046a82  mov     [rdx+58h], rax
0x180046a86  mov     rdx, [rcx]
0x180046a89  test    rdx, rdx
0x180046a8c  jz      short loc_180046A99
0x180046a8e  mov     rax, [rdi+50h]
0x180046a92  mov     [rdx+50h], rax
0x180046a96  mov     rdx, [rcx]
0x180046a99  mov     rax, [rsp+38h+var_10]
0x180046a9e  cmp     rdi, [rax]
0x180046aa1  jnz     short loc_180046AA6
0x180046aa3  mov     [rax], rdx
0x180046aa6  mov     rdi, [rdi+58h]
0x180046aaa  test    rdi, rdi
0x180046aad  jnz     short loc_180046A55
0x180046aaf  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180046ab5  call    cs:__imp_TlsGetValue
0x180046abb  inc     eax
0x180046abd  movsxd  rdx, eax; lpTlsValue
0x180046ac0  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180046ac6  call    cs:__imp_TlsSetValue
0x180046acc  jmp     short loc_180046AEE
0x180046ace  mov     rbx, [rsi]
0x180046ad1  mov     rcx, [rsp+38h+var_18]
0x180046ad6  mov     rax, [rcx]
0x180046ad9  mov     rax, [rax+20h]
0x180046add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ae2  mov     rdx, rax; SRWLock
0x180046ae5  lea     rcx, [rbx+70h]; ConditionVariable
0x180046ae9  call    ?Wait@ConditionVariable@@AEBA_NPEAU_RTL_SRWLOCK@@AEBV?$Optional@VTimeSpan@@@@K@Z; ConditionVariable::Wait(_RTL_SRWLOCK *,Optional<TimeSpan> const &,ulong)
0x180046aee  mov     rax, [rsp+38h+var_10]
0x180046af3  cmp     qword ptr [rax], 0
0x180046af7  jnz     short loc_180046ACE
0x180046af9  lea     rcx, [rsp+38h+arg_0]; this
0x180046afe  call    ??1PreventCancellation@Threading@@QEAA@XZ; Threading::PreventCancellation::~PreventCancellation(void)
0x180046b03  mov     rcx, [rsi]
0x180046b06  mov     rcx, [rcx+50h]; ptpp
0x180046b0a  call    cs:__imp_CloseThreadpool
0x180046b10  nop
0x180046b11  mov     rcx, [rsp+38h+var_18]
0x180046b16  test    rcx, rcx
0x180046b19  jz      short loc_180046B28
0x180046b1b  mov     rax, [rcx]
0x180046b1e  mov     rax, [rax+18h]
0x180046b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b27  nop
0x180046b28  mov     rbx, [rsi+8]
0x180046b2c  test    rbx, rbx
0x180046b2f  jz      short loc_180046B68
0x180046b31  or      edi, 0FFFFFFFFh
0x180046b34  mov     eax, edi
0x180046b36  lock xadd [rbx+8], eax
0x180046b3b  add     eax, edi
0x180046b3d  jnz     short loc_180046B68
0x180046b3f  mov     rax, [rbx]
0x180046b42  mov     rcx, rbx
0x180046b45  mov     rax, [rax]
0x180046b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b4d  mov     eax, edi
0x180046b4f  lock xadd [rbx+0Ch], eax
0x180046b54  add     eax, edi
0x180046b56  jnz     short loc_180046B68
0x180046b58  mov     rax, [rbx]
0x180046b5b  mov     rcx, rbx
0x180046b5e  mov     rax, [rax+8]
0x180046b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b67  nop
0x180046b68  mov     rbx, [rsp+38h+arg_8]
0x180046b6d  mov     rsi, [rsp+38h+arg_10]
0x180046b72  add     rsp, 30h
0x180046b76  pop     rdi
0x180046b77  retn
```
