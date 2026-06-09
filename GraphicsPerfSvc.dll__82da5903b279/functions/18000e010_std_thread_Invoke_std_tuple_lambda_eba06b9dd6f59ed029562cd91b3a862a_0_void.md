# std::thread::_Invoke<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>,0>(void *)

- ea: `0x18000e010`
- end: `0x18000e035`
- name: `??$_Invoke@V?$tuple@V_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@@std@@$0A@@thread@std@@CAIPEAX@Z`
- size: `37`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e720`
- `0x18000e8e0`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18000e01e`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18000e01e`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>,0>(__int64 a1)
{
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  _lambda_eba06b9dd6f59ed029562cd91b3a862a_::operator()();
  _Cnd_do_broadcast_at_thread_exit();
  std::unique_ptr<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>>::~unique_ptr<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>>(&v2);
  return 0;
}

```

## disassembly

```asm
0x18000e010  sub     rsp, 28h
0x18000e014  mov     [rsp+28h+arg_0], rcx
0x18000e019  call    ??R_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@QEBA@XZ; _lambda_eba06b9dd6f59ed029562cd91b3a862a_::operator()(void)
0x18000e01e  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18000e024  lea     rcx, [rsp+28h+arg_0]
0x18000e029  call    ??1?$unique_ptr@V?$tuple@V_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@@std@@U?$default_delete@V?$tuple@V_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>>::~unique_ptr<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>>(void)
0x18000e02e  xor     eax, eax
0x18000e030  add     rsp, 28h
0x18000e034  retn
```
