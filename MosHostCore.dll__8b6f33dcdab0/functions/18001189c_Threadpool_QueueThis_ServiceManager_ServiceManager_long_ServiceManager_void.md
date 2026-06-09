# Threadpool::QueueThis<ServiceManager>(ServiceManager *,long (ServiceManager::*)(void))

- ea: `0x18001189c`
- end: `0x180011916`
- name: `??$QueueThis@VServiceManager@@@Threadpool@@QEAAXPEAVServiceManager@@P81@EAAJXZ@Z`
- size: `122`
- prototype: `__int64 __fastcall(PTP_CALLBACK_ENVIRON pcbe, __int64, _OWORD *)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180012f00`
- `0x180013174`
- `0x18001400c`
- `0x180014980`
- `0x180014c00`
- `0x180015898`
- `0x18001b420`
- `0x18001d070`

## callees

- `0x18000381c`
- `0x1800120b4`
- `0x18001f3c4`

## pseudocode

```c
__int64 __fastcall Threadpool::QueueThis<ServiceManager>(PTP_CALLBACK_ENVIRON pcbe, __int64 a2, _OWORD *a3)
{
  char *v6; // rax
  int v8; // [rsp+2Ch] [rbp-Ch]
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  v6 = (char *)operator new(0x18u);
  *((_QWORD *)v6 + 1) = 0;
  *((_DWORD *)v6 + 4) = 0;
  *((_DWORD *)v6 + 5) = v8;
  *(_QWORD *)v6 = a2;
  *(_OWORD *)(v6 + 8) = *a3;
  Threadpool::QueueWorkItem(
    pcbe,
    (PTP_WORK_CALLBACK)_lambda_3df60c5059ddd2516e9829084db6b71b_::_lambda_invoker_cdecl_,
    v6);
  v9 = 0;
  return __1__unique_ptr_UWorkerParam__1____QueueThis_VMigrationEngine___Threadpool__QEAAXPEAVMigrationEngine__P83_EAAJXZ_Z_U__default_delete_UWorkerParam__1____QueueThis_VMigrationEngine___Threadpool__QEAAXPEAVMigrationEngine__P83_EAAJXZ_Z__std___std__QEAA_XZ(&v9);
}

```

## disassembly

```asm
0x18001189c  mov     [rsp+arg_0], rbx
0x1800118a1  mov     [rsp+arg_10], rsi
0x1800118a6  push    rdi
0x1800118a7  sub     rsp, 30h
0x1800118ab  mov     rsi, rcx
0x1800118ae  mov     rdi, r8
0x1800118b1  mov     ecx, 18h; Size
0x1800118b6  mov     rbx, rdx
0x1800118b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800118be  mov     r9d, [rsp+38h+var_C]
0x1800118c3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3df60c5059ddd2516e9829084db6b71b_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800118ca  mov     r8, rax; pv
0x1800118cd  mov     rcx, rsi; pcbe
0x1800118d0  mov     qword ptr [rax+8], 0
0x1800118d8  mov     dword ptr [rax+10h], 0
0x1800118df  mov     [rax+14h], r9d
0x1800118e3  mov     [rax], rbx
0x1800118e6  movaps  xmm0, xmmword ptr [rdi]
0x1800118e9  movdqu  xmmword ptr [rax+8], xmm0
0x1800118ee  call    ?QueueWorkItem@Threadpool@@AEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; Threadpool::QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x1800118f3  lea     rcx, [rsp+38h+arg_8]
0x1800118f8  mov     [rsp+38h+arg_8], 0
0x180011901  call    ??1?$unique_ptr@UWorkerParam@?1???$QueueThis@VMigrationEngine@@@Threadpool@@QEAAXPEAVMigrationEngine@@P83@EAAJXZ@Z@U?$default_delete@UWorkerParam@?1???$QueueThis@VMigrationEngine@@@Threadpool@@QEAAXPEAVMigrationEngine@@P83@EAAJXZ@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam,std::default_delete<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam>>::~unique_ptr<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam,std::default_delete<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam>>(void)
0x180011906  mov     rbx, [rsp+38h+arg_0]
0x18001190b  mov     rsi, [rsp+38h+arg_10]
0x180011910  add     rsp, 30h
0x180011914  pop     rdi
0x180011915  retn
```
