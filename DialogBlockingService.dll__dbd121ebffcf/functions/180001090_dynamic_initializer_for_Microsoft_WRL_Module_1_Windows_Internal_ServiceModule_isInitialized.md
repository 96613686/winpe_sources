# _dynamic_initializer_for__Microsoft::WRL::Module_1_Windows::Internal::ServiceModule_::isInitialized__

- ea: `0x180001090`
- end: `0x1800010c1`
- name: `_dynamic_initializer_for__Microsoft::WRL::Module_1_Windows::Internal::ServiceModule_::isInitialized__`
- size: `49`
- prototype: `BOOL()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800010a8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800010a8`

## pseudocode

```c
BOOL dynamic_initializer_for__Microsoft::WRL::Module_1_Windows::Internal::ServiceModule_::isInitialized__()
{
  BOOL result; // eax

  result = InitOnceExecuteOnce(
             &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::initOnceOutOfProc_,
             _lambda_0436b89998ddae64b987abcfc9f7e79b_::_lambda_invoker_cdecl_,
             0,
             0);
  byte_180014568 = 1;
  Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x180001090  sub     rsp, 28h
0x180001094  xor     r9d, r9d; Context
0x180001097  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0436b89998ddae64b987abcfc9f7e79b_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000109e  xor     r8d, r8d; Parameter
0x1800010a1  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800010a8  call    cs:__imp_InitOnceExecuteOnce
0x1800010ae  mov     cs:byte_180014568, 1
0x1800010b5  mov     cs:?isInitialized@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@0_NA, 1; bool Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized
0x1800010bc  add     rsp, 28h
0x1800010c0  retn
```
