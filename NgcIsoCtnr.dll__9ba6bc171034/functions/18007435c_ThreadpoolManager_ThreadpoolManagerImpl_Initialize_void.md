# ThreadpoolManager::ThreadpoolManagerImpl::Initialize(void)

- ea: `0x18007435c`
- end: `0x1800744c4`
- name: `?Initialize@ThreadpoolManagerImpl@ThreadpoolManager@@QEAAJXZ`
- size: `360`
- prototype: `__int64 __fastcall(ThreadpoolManager::ThreadpoolManagerImpl *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180070188`
- `0x18007056c`

## callees

- `0x18000918c`
- `0x18000d60c`
- `0x180046de8`
- `0x180074254`
- `0x180074284`
- `0x1800742b4`
- `0x18007435c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180074421`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180074421`

## string_xrefs

- `0x18007444b`: `onecore\ds\security\ngc\utils\common\lib\threadpoolmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ThreadpoolManager::ThreadpoolManagerImpl::Initialize(ThreadpoolManager::ThreadpoolManagerImpl *this)
{
  int v2; // eax
  char *v3; // rsi
  char *v4; // rdi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rdi
  const char *v6; // r9
  unsigned int LastError; // ebx
  __int64 v9; // rcx
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  __int16 v11; // [rsp+28h] [rbp-20h]
  __int64 v12; // [rsp+30h] [rbp-18h] BYREF
  __int16 v13; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  char v15; // [rsp+70h] [rbp+28h] BYREF

  v2 = *(_DWORD *)this;
  if ( *(_DWORD *)this )
  {
    if ( v2 == -1 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    *(_DWORD *)this = v2 + 1;
  }
  else
  {
    v3 = (char *)this + 200;
    v4 = (char *)this + 128;
    if ( (ThreadpoolManager::ThreadpoolManagerImpl *)((char *)this + 128) == *((ThreadpoolManager::ThreadpoolManagerImpl **)this
                                                                             + 26) )
    {
      v4 = (char *)*((_QWORD *)this + 26);
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<TpCleanupGroupTraits>::Close((char *)this + 200);
      *((_QWORD *)v3 + 1) = v4;
    }
    *(_DWORD *)v4 = 3;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_DWORD *)v4 + 14) = 0;
    *((_DWORD *)v4 + 15) = 1;
    *((_DWORD *)v4 + 16) = 72;
    v10 = *(_QWORD *)_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_::_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_(
                       (_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_ *)&v15,
                       this);
    v11 = 258;
    *(_DWORD *)(*((_QWORD *)this + 26) + 56LL) |= 1u;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    if ( ThreadpoolCleanupGroup == *((PTP_CLEANUP_GROUP *)this + 28) )
    {
      ThreadpoolCleanupGroup = (PTP_CLEANUP_GROUP)*((_QWORD *)this + 28);
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<TpCleanupGroupTraits>::Close((char *)this + 216);
      *((_QWORD *)this + 28) = ThreadpoolCleanupGroup;
    }
    if ( !ThreadpoolCleanupGroup )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x5F,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\threadpoolmanager.cpp",
                    v6);
      wil::details::ScopeExitFnGuard<_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_>::operator()(&v10);
      return LastError;
    }
    v12 = *(_QWORD *)_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_::_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_(
                       (_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_ *)&v15,
                       this);
    v13 = 2;
    v9 = *((_QWORD *)this + 26);
    *(_QWORD *)(v9 + 16) = *((_QWORD *)this + 28);
    *(_QWORD *)(v9 + 24) = 0;
    HIBYTE(v11) = 0;
    *(_DWORD *)this = 1;
    wil::details::ScopeExitFnGuard<_lambda_a2423557555f3e32790dae58674b87f5_>::operator()(&v12);
    wil::details::ScopeExitFnGuard<_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_>::operator()(&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18007435c  push    rbp
0x18007435e  push    rbx
0x18007435f  push    rsi
0x180074360  push    rdi
0x180074361  mov     rbp, rsp
0x180074364  sub     rsp, 48h
0x180074368  mov     rbx, rcx
0x18007436b  mov     eax, [rcx]
0x18007436d  test    eax, eax
0x18007436f  jz      short loc_180074385
0x180074371  cmp     eax, 0FFFFFFFFh
0x180074374  jz      short loc_18007437F
0x180074376  inc     eax
0x180074378  mov     [rcx], eax
0x18007437a  jmp     loc_1800744B9
0x18007437f  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180074385  lea     rsi, [rcx+0C8h]
0x18007438c  lea     rdi, [rcx+80h]
0x180074393  cmp     rdi, [rsi+8]
0x180074397  jz      short loc_1800743A7
0x180074399  mov     rcx, rsi
0x18007439c  call    ?Close@?$HandleT@UTpCleanupGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<TpCleanupGroupTraits>::Close(void)
0x1800743a1  mov     [rsi+8], rdi
0x1800743a5  jmp     short loc_1800743AB
0x1800743a7  mov     rdi, [rsi+8]
0x1800743ab  mov     dword ptr [rdi], 3
0x1800743b1  mov     qword ptr [rdi+8], 0
0x1800743b9  mov     qword ptr [rdi+10h], 0
0x1800743c1  mov     qword ptr [rdi+18h], 0
0x1800743c9  mov     qword ptr [rdi+20h], 0
0x1800743d1  mov     qword ptr [rdi+28h], 0
0x1800743d9  mov     qword ptr [rdi+30h], 0
0x1800743e1  mov     dword ptr [rdi+38h], 0
0x1800743e8  mov     dword ptr [rdi+3Ch], 1
0x1800743ef  mov     dword ptr [rdi+40h], 48h ; 'H'
0x1800743f6  mov     rdx, rbx; struct ThreadpoolManager::ThreadpoolManagerImpl *
0x1800743f9  lea     rcx, [rbp+arg_0]; this
0x1800743fd  call    ??0_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_@@QEAA@PEAVThreadpoolManagerImpl@ThreadpoolManager@@@Z; _lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_::_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_(ThreadpoolManager::ThreadpoolManagerImpl *)
0x180074402  mov     rcx, [rax]
0x180074405  mov     [rbp+var_28], rcx
0x180074409  mov     [rbp+var_20], 102h
0x18007440f  mov     rax, [rbx+0D0h]
0x180074416  or      dword ptr [rax+38h], 1
0x18007441a  lea     rsi, [rbx+0D8h]
0x180074421  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180074427  mov     rdi, rax
0x18007442a  cmp     rax, [rsi+8]
0x18007442e  jz      short loc_18007443E
0x180074430  mov     rcx, rsi
0x180074433  call    ?Close@?$HandleT@UTpCleanupGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<TpCleanupGroupTraits>::Close(void)
0x180074438  mov     [rsi+8], rdi
0x18007443c  jmp     short loc_180074442
0x18007443e  mov     rdi, [rsi+8]
0x180074442  test    rdi, rdi
0x180074445  jnz     short loc_180074469
0x180074447  mov     rcx, [rbp+20h]; this
0x18007444b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180074452  lea     edx, [rdi+5Fh]; void *
0x180074455  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007445a  mov     ebx, eax
0x18007445c  lea     rcx, [rbp+var_28]
0x180074460  call    ??R?$ScopeExitFnGuard@V_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_@@@details@wil@@QEAAXXZ; wil::details::ScopeExitFnGuard<_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_>::operator()(void)
0x180074465  mov     eax, ebx
0x180074467  jmp     short loc_1800744BB
0x180074469  mov     rdx, rbx; struct ThreadpoolManager::ThreadpoolManagerImpl *
0x18007446c  lea     rcx, [rbp+arg_0]; this
0x180074470  call    ??0_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_@@QEAA@PEAVThreadpoolManagerImpl@ThreadpoolManager@@@Z; _lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_::_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_(ThreadpoolManager::ThreadpoolManagerImpl *)
0x180074475  mov     rcx, [rax]
0x180074478  mov     [rbp+var_18], rcx
0x18007447c  mov     [rbp+var_10], 2
0x180074482  mov     rcx, [rbx+0D0h]
0x180074489  mov     rax, [rbx+0E0h]
0x180074490  mov     [rcx+10h], rax
0x180074494  mov     qword ptr [rcx+18h], 0
0x18007449c  mov     byte ptr [rbp+var_20+1], 0
0x1800744a0  mov     dword ptr [rbx], 1
0x1800744a6  lea     rcx, [rbp+var_18]
0x1800744aa  call    ??R?$ScopeExitFnGuard@V_lambda_a2423557555f3e32790dae58674b87f5_@@@details@wil@@QEAAXXZ; wil::details::ScopeExitFnGuard<_lambda_a2423557555f3e32790dae58674b87f5_>::operator()(void)
0x1800744af  nop
0x1800744b0  lea     rcx, [rbp+var_28]
0x1800744b4  call    ??R?$ScopeExitFnGuard@V_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_@@@details@wil@@QEAAXXZ; wil::details::ScopeExitFnGuard<_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_>::operator()(void)
0x1800744b9  xor     eax, eax
0x1800744bb  add     rsp, 48h
0x1800744bf  pop     rdi
0x1800744c0  pop     rsi
0x1800744c1  pop     rbx
0x1800744c2  pop     rbp
0x1800744c3  retn
```
