# Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(void)

- ea: `0x140007360`
- end: `0x140007377`
- name: `??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1400065e8`
- `0x140006680`
- `0x140006788`
- `0x1400068c4`

## callees

- `0x140007360`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000736c`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000736c`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x140007360  sub     rsp, 28h
0x140007364  mov     rcx, [rcx]
0x140007367  test    rcx, rcx
0x14000736a  jz      short loc_140007372
0x14000736c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007372  add     rsp, 28h
0x140007376  retn
```
