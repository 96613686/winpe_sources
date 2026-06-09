# std::unique_ptr<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam,std::default_delete<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam>>::~unique_ptr<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam,std::default_delete<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam>>(void)

- ea: `0x1800120b4`
- end: `0x1800120ca`
- name: `??1?$unique_ptr@UWorkerParam@?1???$QueueThis@VMigrationEngine@@@Threadpool@@QEAAXPEAVMigrationEngine@@P83@EAAJXZ@Z@U?$default_delete@UWorkerParam@?1???$QueueThis@VMigrationEngine@@@Threadpool@@QEAAXPEAVMigrationEngine@@P83@EAAJXZ@Z@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800114e0`
- `0x1800115b0`
- `0x180011694`
- `0x18001189c`
- `0x18001199c`
- `0x18001b3a0`
- `0x180022754`
- `0x180023ab1`
- `0x180023ac3`

## callees

- `0x1800033f4`
- `0x1800120b4`

## pseudocode

```c
void __fastcall __1__unique_ptr_UWorkerParam__1____QueueThis_VMigrationEngine___Threadpool__QEAAXPEAVMigrationEngine__P83_EAAJXZ_Z_U__default_delete_UWorkerParam__1____QueueThis_VMigrationEngine___Threadpool__QEAAXPEAVMigrationEngine__P83_EAAJXZ_Z__std___std__QEAA_XZ(
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
0x1800120b4  sub     rsp, 28h
0x1800120b8  mov     rcx, [rcx]; Block
0x1800120bb  test    rcx, rcx
0x1800120be  jz      short loc_1800120C5
0x1800120c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800120c5  add     rsp, 28h
0x1800120c9  retn
```
