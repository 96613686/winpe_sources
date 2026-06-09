# ThreadpoolManager::ThreadpoolManagerImpl::Initialize(void)

- ea: `0x180026c94`
- end: `0x180026df1`
- name: `?Initialize@ThreadpoolManagerImpl@ThreadpoolManager@@QEAAJXZ`
- size: `349`
- prototype: `__int64 __fastcall(ThreadpoolManager::ThreadpoolManagerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022b70`

## callees

- `0x180019c94`
- `0x180022e68`
- `0x180026c94`
- `0x1800343f4`
- `0x18005a64c`
- `0x18005a680`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180026d4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180026d4f`

## string_xrefs

- `0x180026d80`: `onecore\ds\security\ngc\utils\common\lib\threadpoolmanager.cpp`

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
  __int64 v9; // rax
  ThreadpoolManager::ThreadpoolManagerImpl *v10; // [rsp+20h] [rbp-28h] BYREF
  __int16 v11; // [rsp+28h] [rbp-20h]
  ThreadpoolManager::ThreadpoolManagerImpl *v12; // [rsp+30h] [rbp-18h] BYREF
  __int16 v13; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *(_DWORD *)this;
  if ( *(_DWORD *)this )
  {
    if ( v2 == -1 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(this);
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
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close((char *)this + 200);
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
    v10 = this;
    v11 = 258;
    *(_DWORD *)(*((_QWORD *)this + 26) + 56LL) |= 1u;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    if ( ThreadpoolCleanupGroup == *((PTP_CLEANUP_GROUP *)this + 28) )
    {
      ThreadpoolCleanupGroup = (PTP_CLEANUP_GROUP)*((_QWORD *)this + 28);
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close((char *)this + 216);
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
    v12 = this;
    v13 = 2;
    v9 = *((_QWORD *)this + 26);
    *(_QWORD *)(v9 + 16) = ThreadpoolCleanupGroup;
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
0x180026c94  mov     [rsp+arg_0], rbx
0x180026c99  mov     [rsp+arg_8], rsi
0x180026c9e  push    rdi
0x180026c9f  sub     rsp, 40h
0x180026ca3  mov     rbx, rcx
0x180026ca6  mov     eax, [rcx]
0x180026ca8  test    eax, eax
0x180026caa  jz      short loc_180026CC0
0x180026cac  cmp     eax, 0FFFFFFFFh
0x180026caf  jz      short loc_180026CBA
0x180026cb1  inc     eax
0x180026cb3  mov     [rcx], eax
0x180026cb5  jmp     loc_180026DDE
0x180026cba  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180026cc0  lea     rsi, [rcx+0C8h]
0x180026cc7  lea     rdi, [rcx+80h]
0x180026cce  cmp     rdi, [rsi+8]
0x180026cd2  jz      short loc_180026CE2
0x180026cd4  mov     rcx, rsi
0x180026cd7  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180026cdc  mov     [rsi+8], rdi
0x180026ce0  jmp     short loc_180026CE6
0x180026ce2  mov     rdi, [rsi+8]
0x180026ce6  mov     dword ptr [rdi], 3
0x180026cec  mov     qword ptr [rdi+8], 0
0x180026cf4  mov     qword ptr [rdi+10h], 0
0x180026cfc  mov     qword ptr [rdi+18h], 0
0x180026d04  mov     qword ptr [rdi+20h], 0
0x180026d0c  mov     qword ptr [rdi+28h], 0
0x180026d14  mov     qword ptr [rdi+30h], 0
0x180026d1c  mov     dword ptr [rdi+38h], 0
0x180026d23  mov     dword ptr [rdi+3Ch], 1
0x180026d2a  mov     dword ptr [rdi+40h], 48h ; 'H'
0x180026d31  mov     [rsp+48h+var_28], rbx
0x180026d36  mov     [rsp+48h+var_20], 102h
0x180026d3d  mov     rax, [rbx+0D0h]
0x180026d44  or      dword ptr [rax+38h], 1
0x180026d48  lea     rsi, [rbx+0D8h]
0x180026d4f  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180026d56  nop     dword ptr [rax+rax+00h]
0x180026d5b  mov     rdi, rax
0x180026d5e  cmp     rax, [rsi+8]
0x180026d62  jz      short loc_180026D72
0x180026d64  mov     rcx, rsi
0x180026d67  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180026d6c  mov     [rsi+8], rdi
0x180026d70  jmp     short loc_180026D76
0x180026d72  mov     rdi, [rsi+8]
0x180026d76  test    rdi, rdi
0x180026d79  jnz     short loc_180026D9F
0x180026d7b  mov     rcx, [rsp+48h]; this
0x180026d80  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180026d87  lea     edx, [rdi+5Fh]; void *
0x180026d8a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026d8f  mov     ebx, eax
0x180026d91  lea     rcx, [rsp+48h+var_28]
0x180026d96  call    ??R?$ScopeExitFnGuard@V_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_@@@details@wil@@QEAAXXZ; wil::details::ScopeExitFnGuard<_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_>::operator()(void)
0x180026d9b  mov     eax, ebx
0x180026d9d  jmp     short loc_180026DE0
0x180026d9f  mov     [rsp+48h+var_18], rbx
0x180026da4  mov     [rsp+48h+var_10], 2
0x180026dab  mov     rax, [rbx+0D0h]
0x180026db2  mov     [rax+10h], rdi
0x180026db6  mov     qword ptr [rax+18h], 0
0x180026dbe  mov     byte ptr [rsp+48h+var_20+1], 0
0x180026dc3  mov     dword ptr [rbx], 1
0x180026dc9  lea     rcx, [rsp+48h+var_18]
0x180026dce  call    ??R?$ScopeExitFnGuard@V_lambda_a2423557555f3e32790dae58674b87f5_@@@details@wil@@QEAAXXZ; wil::details::ScopeExitFnGuard<_lambda_a2423557555f3e32790dae58674b87f5_>::operator()(void)
0x180026dd3  nop
0x180026dd4  lea     rcx, [rsp+48h+var_28]
0x180026dd9  call    ??R?$ScopeExitFnGuard@V_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_@@@details@wil@@QEAAXXZ; wil::details::ScopeExitFnGuard<_lambda_61c17ebbe8f10aec1ee8f8dcb8fb6935_>::operator()(void)
0x180026dde  xor     eax, eax
0x180026de0  mov     rbx, [rsp+48h+arg_0]
0x180026de5  mov     rsi, [rsp+48h+arg_8]
0x180026dea  add     rsp, 40h
0x180026dee  pop     rdi
0x180026def  retn
```
