# Microsoft::WRL::Details::OutOfProcModuleBase<MultipleUseOutOfProcModule>::Create(void)

- ea: `0x1400079f4`
- end: `0x140007a25`
- name: `?Create@?$OutOfProcModuleBase@VMultipleUseOutOfProcModule@@@Details@WRL@Microsoft@@SAAEAVMultipleUseOutOfProcModule@@XZ`
- size: `49`
- prototype: `__int64 *()`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001990`
- `0x140008fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140007a0c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140007a0c`

## pseudocode

```c
__int64 *Microsoft::WRL::Details::OutOfProcModuleBase<MultipleUseOutOfProcModule>::Create()
{
  __int64 *result; // rax

  InitOnceExecuteOnce(
    &Microsoft::WRL::Details::OutOfProcModuleBase<MultipleUseOutOfProcModule>::initOnceOutOfProc_,
    _lambda_7cb3f1da0a0e9a3a23678494bd451f36_::_lambda_invoker_cdecl_,
    0,
    0);
  result = &Microsoft::WRL::Details::StaticStorage<MultipleUseOutOfProcModule,1,int>::instance_;
  byte_140011A78 = 1;
  return result;
}

```

## disassembly

```asm
0x1400079f4  sub     rsp, 28h
0x1400079f8  xor     r9d, r9d; Context
0x1400079fb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_7cb3f1da0a0e9a3a23678494bd451f36_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x140007a02  xor     r8d, r8d; Parameter
0x140007a05  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VMultipleUseOutOfProcModule@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x140007a0c  call    cs:__imp_InitOnceExecuteOnce
0x140007a12  lea     rax, ?instance_@?$StaticStorage@VMultipleUseOutOfProcModule@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<MultipleUseOutOfProcModule,1,int> Microsoft::WRL::Details::StaticStorage<MultipleUseOutOfProcModule,1,int>::instance_
0x140007a19  mov     cs:byte_140011A78, 1
0x140007a20  add     rsp, 28h
0x140007a24  retn
```
