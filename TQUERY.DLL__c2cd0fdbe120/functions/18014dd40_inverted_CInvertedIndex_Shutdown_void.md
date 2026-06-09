# inverted::CInvertedIndex::Shutdown(void)

- ea: `0x18014dd40`
- end: `0x18014de04`
- name: `?Shutdown@CInvertedIndex@inverted@@UEAAXXZ`
- size: `196`
- prototype: `void __fastcall(inverted::CInvertedIndex *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180036d60`
- `0x180088214`
- `0x1800ae484`
- `0x18014dd40`
- `0x18014e148`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014dd6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014ddf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014dd6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014ddf3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18014dd94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18014ddaa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18014dd94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18014ddaa`

## pseudocode

```c
void __fastcall inverted::CInvertedIndex::Shutdown(std::_Ref_count_base **this)
{
  RTL_SRWLOCK *v1; // rbx
  struct _TP_WORK *v3; // rcx
  struct _TP_WORK *v4; // rcx
  std::_Ref_count_base *v5; // rcx

  v1 = (RTL_SRWLOCK *)(this + 85);
  CSRWLock::AcquireExclusive((CSRWLock *)(this + 85));
  inverted::CInvertedIndex::_StopAllRunningMerges((inverted::CInvertedIndex *)this);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  (*((void (__fastcall **)(std::_Ref_count_base **))*this + 27))(this);
  v3 = this[57];
  *((_BYTE *)this + 465) = 0;
  WaitForThreadpoolWorkCallbacks(v3, 0);
  v4 = this[59];
  *((_BYTE *)this + 481) = 0;
  WaitForThreadpoolWorkCallbacks(v4, 0);
  CSRWLock::AcquireExclusive((CSRWLock *)v1);
  this[55] = 0;
  v5 = this[56];
  this[56] = 0;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  std::shared_ptr<inverted::IInvertedIndex>::reset(this + 30);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x18014dd40  mov     [rsp+arg_0], rbx
0x18014dd45  push    rdi
0x18014dd46  sub     rsp, 20h
0x18014dd4a  lea     rbx, [rcx+2A8h]
0x18014dd51  mov     rdi, rcx
0x18014dd54  mov     rcx, rbx; this
0x18014dd57  call    ?AcquireExclusive@CSRWLock@@QEAAXXZ; CSRWLock::AcquireExclusive(void)
0x18014dd5c  mov     rcx, rdi; this
0x18014dd5f  call    ?_StopAllRunningMerges@CInvertedIndex@inverted@@AEAAXXZ; inverted::CInvertedIndex::_StopAllRunningMerges(void)
0x18014dd64  test    rbx, rbx
0x18014dd67  jz      short loc_18014DD72
0x18014dd69  mov     rcx, rbx; SRWLock
0x18014dd6c  call    cs:__imp_ReleaseSRWLockExclusive
0x18014dd72  mov     rax, [rdi]
0x18014dd75  mov     rcx, rdi
0x18014dd78  mov     rax, [rax+0D8h]
0x18014dd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dd84  mov     rcx, [rdi+1C8h]; pwk
0x18014dd8b  xor     edx, edx; fCancelPendingCallbacks
0x18014dd8d  mov     byte ptr [rdi+1D1h], 0
0x18014dd94  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18014dd9a  mov     rcx, [rdi+1D8h]; pwk
0x18014dda1  xor     edx, edx; fCancelPendingCallbacks
0x18014dda3  mov     byte ptr [rdi+1E1h], 0
0x18014ddaa  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18014ddb0  mov     rcx, rbx; this
0x18014ddb3  call    ?AcquireExclusive@CSRWLock@@QEAAXXZ; CSRWLock::AcquireExclusive(void)
0x18014ddb8  mov     qword ptr [rdi+1B8h], 0
0x18014ddc3  mov     rcx, [rdi+1C0h]; this
0x18014ddca  mov     qword ptr [rdi+1C0h], 0
0x18014ddd5  test    rcx, rcx
0x18014ddd8  jz      short loc_18014DDDF
0x18014ddda  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014dddf  lea     rcx, [rdi+0F0h]
0x18014dde6  call    ?reset@?$shared_ptr@UIInvertedIndex@inverted@@@std@@QEAAXXZ; std::shared_ptr<inverted::IInvertedIndex>::reset(void)
0x18014ddeb  test    rbx, rbx
0x18014ddee  jz      short loc_18014DDF9
0x18014ddf0  mov     rcx, rbx; SRWLock
0x18014ddf3  call    cs:__imp_ReleaseSRWLockExclusive
0x18014ddf9  mov     rbx, [rsp+28h+arg_0]
0x18014ddfe  add     rsp, 20h
0x18014de02  pop     rdi
0x18014de03  retn
```
