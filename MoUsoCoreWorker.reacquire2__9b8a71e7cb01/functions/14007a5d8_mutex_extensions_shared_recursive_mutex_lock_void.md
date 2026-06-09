# mutex_extensions::shared_recursive_mutex::lock(void)

- ea: `0x14007a5d8`
- end: `0x14007a7d5`
- name: `?lock@shared_recursive_mutex@mutex_extensions@@QEAAXXZ`
- size: `509`
- prototype: `void __fastcall(_Mtx_t this)`
- caller_count: `36`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14007ed9c`
- `0x1400831b4`
- `0x14008353c`
- `0x14008371c`
- `0x1400838fc`
- `0x14008a974`
- `0x14008c7dc`
- `0x14008d440`
- `0x14008d974`
- `0x14008f540`
- `0x140091b28`
- `0x140093cdc`
- `0x140098104`
- `0x14009833c`
- `0x140098aa4`
- `0x140098f74`
- `0x140099860`
- `0x14009a038`
- `0x14009b0f0`
- `0x14009becc`
- `0x14009efb0`
- `0x14009f02c`
- `0x14009f30c`
- `0x14009fab4`
- `0x1400a0140`
- `0x1400a09bc`
- `0x1400a1744`
- `0x1400a2998`
- `0x1400a80c8`
- `0x1400b8984`
- `0x1400bf938`
- `0x1401a9124`
- `0x1401a9890`
- `0x1401ca464`
- `0x1401ca60c`
- `0x1401cdff0`

## callees

- `0x140041df8`
- `0x1400421f8`
- `0x140045160`
- `0x14007a5d8`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x1401a2fd0`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a66f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a6a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a6b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a66f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a6a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a6b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007a6d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007a6d2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14007a6dc`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14007a6dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall mutex_extensions::shared_recursive_mutex::lock(char *this)
{
  DWORD CurrentThreadId; // eax
  __int64 **v3; // rdx
  __int64 *i; // rcx
  const struct std::error_category *v6; // rax
  const struct std::error_category *v7; // rax
  const struct std::error_category *v8; // rax
  __int128 v9; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v10[16]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v12; // [rsp+68h] [rbp-18h]

  v12 = (unsigned __int64)this;
  if ( (unsigned int)mtx_do_lock(this, 0) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v12) = 1;
  if ( !*((_DWORD *)this + 38) )
    goto LABEL_10;
  CurrentThreadId = GetCurrentThreadId();
  v3 = (__int64 **)*((_QWORD *)this + 20);
  for ( i = *v3; i != (__int64 *)v3 && *((_DWORD *)i + 4) != CurrentThreadId; i = (__int64 *)*i )
    ;
  if ( i != (__int64 *)v3 )
  {
    v7 = std::system_category();
    v9 = *(_OWORD *)std::error_code::error_code((std::error_code *)v10, 5023, v7);
    std::system_error::system_error(pExceptionObject, &v9);
    throw (std::system_error *)pExceptionObject;
  }
  while ( 1 )
  {
    if ( *((_DWORD *)this + 38) )
      goto LABEL_12;
LABEL_10:
    if ( !*((_DWORD *)this + 44) || *((_DWORD *)this + 45) == GetCurrentThreadId() )
      break;
LABEL_12:
    Cnd_wait((_Cnd_t)(this + 80), (_Mtx_t)this);
  }
  if ( *((_DWORD *)this + 38) )
  {
    v8 = std::system_category();
    v9 = *(_OWORD *)std::error_code::error_code((std::error_code *)v10, 5023, v8);
    std::system_error::system_error(pExceptionObject, &v9);
    throw (std::system_error *)pExceptionObject;
  }
  if ( *((_DWORD *)this + 44) && *((_DWORD *)this + 45) != GetCurrentThreadId() )
  {
    v6 = std::system_category();
    v9 = *(_OWORD *)std::error_code::error_code((std::error_code *)v10, 5023, v6);
    std::system_error::system_error(pExceptionObject, &v9);
    throw (std::system_error *)pExceptionObject;
  }
  ++*((_DWORD *)this + 44);
  *((_DWORD *)this + 45) = GetCurrentThreadId();
  if ( (*((_DWORD *)this + 19))-- == 1 )
  {
    *((_DWORD *)this + 18) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 2);
  }
  WakeAllConditionVariable((PCONDITION_VARIABLE)this + 11);
}

```

## disassembly

```asm
0x14007a5d8  mov     [rsp-8+arg_8], rbx
0x14007a5dd  mov     [rsp-8+arg_10], rdi
0x14007a5e2  push    rbp
0x14007a5e3  mov     rbp, rsp
0x14007a5e6  sub     rsp, 80h
0x14007a5ed  mov     rax, cs:__security_cookie
0x14007a5f4  xor     rax, rsp
0x14007a5f7  mov     [rbp+var_8], rax
0x14007a5fb  mov     rbx, rcx
0x14007a5fe  xorps   xmm0, xmm0
0x14007a601  movups  [rbp+var_18], xmm0
0x14007a605  mov     qword ptr [rbp+var_18], rcx
0x14007a609  mov     byte ptr [rbp+var_18+8], 0
0x14007a60d  xor     edx, edx
0x14007a60f  call    mtx_do_lock
0x14007a614  test    eax, eax
0x14007a616  jnz     loc_14007A740
0x14007a61c  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x14007a623  jz      loc_14007A74B
0x14007a629  mov     byte ptr [rbp+var_18+8], 1
0x14007a62d  cmp     [rbx+98h], eax
0x14007a633  jz      short loc_14007A666
0x14007a635  call    cs:__imp_GetCurrentThreadId
0x14007a63b  mov     rdx, [rbx+0A0h]
0x14007a642  mov     rcx, [rdx]
0x14007a645  jmp     short loc_14007A64F
0x14007a647  cmp     [rcx+10h], eax
0x14007a64a  jz      short loc_14007A654
0x14007a64c  mov     rcx, [rcx]
0x14007a64f  cmp     rcx, rdx
0x14007a652  jnz     short loc_14007A647
0x14007a654  cmp     rcx, rdx
0x14007a657  jnz     loc_14007A75D
0x14007a65d  cmp     dword ptr [rbx+98h], 0
0x14007a664  jnz     short loc_14007A67D
0x14007a666  cmp     dword ptr [rbx+0B0h], 0
0x14007a66d  jz      short loc_14007A68B
0x14007a66f  call    cs:__imp_GetCurrentThreadId
0x14007a675  cmp     [rbx+0B4h], eax
0x14007a67b  jz      short loc_14007A68B
0x14007a67d  mov     rdx, rbx; _Mtx_t
0x14007a680  lea     rcx, [rbx+50h]; _Cnd_t
0x14007a684  call    _Cnd_wait
0x14007a689  jmp     short loc_14007A65D
0x14007a68b  cmp     dword ptr [rbx+98h], 0
0x14007a692  jnz     loc_14007A799
0x14007a698  cmp     dword ptr [rbx+0B0h], 0
0x14007a69f  jz      short loc_14007A6AF
0x14007a6a1  call    cs:__imp_GetCurrentThreadId
0x14007a6a7  cmp     [rbx+0B4h], eax
0x14007a6ad  jnz     short loc_14007A703
0x14007a6af  inc     dword ptr [rbx+0B0h]
0x14007a6b5  call    cs:__imp_GetCurrentThreadId
0x14007a6bb  mov     [rbx+0B4h], eax
0x14007a6c1  sub     dword ptr [rbx+4Ch], 1
0x14007a6c5  jnz     short loc_14007A6D8
0x14007a6c7  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x14007a6ce  lea     rcx, [rbx+10h]; SRWLock
0x14007a6d2  call    cs:__imp_ReleaseSRWLockExclusive
0x14007a6d8  lea     rcx, [rbx+58h]; ConditionVariable
0x14007a6dc  call    cs:__imp_WakeAllConditionVariable
0x14007a6e2  mov     rcx, [rbp+var_8]
0x14007a6e6  xor     rcx, rsp; StackCookie
0x14007a6e9  call    __security_check_cookie
0x14007a6ee  lea     r11, [rsp+80h+var_s0]
0x14007a6f6  mov     rbx, [r11+18h]
0x14007a6fa  mov     rdi, [r11+20h]
0x14007a6fe  mov     rsp, r11
0x14007a701  pop     rbp
0x14007a702  retn
0x14007a703  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x14007a708  nop
0x14007a709  mov     r8, rax; struct std::error_category *
0x14007a70c  mov     edx, 139Fh; int
0x14007a711  lea     rcx, [rbp+var_50]; this
0x14007a715  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x14007a71a  movups  xmm0, xmmword ptr [rax]
0x14007a71d  movdqu  [rbp+var_60], xmm0
0x14007a722  lea     rdx, [rbp+var_60]
0x14007a726  lea     rcx, [rbp+pExceptionObject]
0x14007a72a  call    ??0system_error@std@@QEAA@Verror_code@1@@Z; std::system_error::system_error(std::error_code)
0x14007a72f  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x14007a736  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14007a73a  call    _CxxThrowException
0x14007a740  mov     ecx, 5; int
0x14007a745  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14007a74b  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x14007a752  mov     ecx, 6; int
0x14007a757  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14007a75d  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x14007a762  mov     r8, rax; struct std::error_category *
0x14007a765  mov     edx, 139Fh; int
0x14007a76a  lea     rcx, [rbp+var_50]; this
0x14007a76e  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x14007a773  movups  xmm0, xmmword ptr [rax]
0x14007a776  movdqu  [rbp+var_60], xmm0
0x14007a77b  lea     rdx, [rbp+var_60]
0x14007a77f  lea     rcx, [rbp+pExceptionObject]
0x14007a783  call    ??0system_error@std@@QEAA@Verror_code@1@@Z; std::system_error::system_error(std::error_code)
0x14007a788  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x14007a78f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14007a793  call    _CxxThrowException
0x14007a799  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x14007a79e  mov     r8, rax; struct std::error_category *
0x14007a7a1  mov     edx, 139Fh; int
0x14007a7a6  lea     rcx, [rbp+var_50]; this
0x14007a7aa  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x14007a7af  movups  xmm0, xmmword ptr [rax]
0x14007a7b2  movdqu  [rbp+var_60], xmm0
0x14007a7b7  lea     rdx, [rbp+var_60]
0x14007a7bb  lea     rcx, [rbp+pExceptionObject]
0x14007a7bf  call    ??0system_error@std@@QEAA@Verror_code@1@@Z; std::system_error::system_error(std::error_code)
0x14007a7c4  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x14007a7cb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14007a7cf  call    _CxxThrowException
```
