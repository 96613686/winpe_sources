# Windows::Internal::ComTaskPool::QueueTask<_lambda_5b71e87bbd38edd0b6bc262bc572dce1_>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_5b71e87bbd38edd0b6bc262bc572dce1_ &&)

- ea: `0x1800276f4`
- end: `0x180027771`
- name: `??$QueueTask@V_lambda_5b71e87bbd38edd0b6bc262bc572dce1_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@K$$QEAV_lambda_5b71e87bbd38edd0b6bc262bc572dce1_@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011f8c`

## callees

- `0x180026a98`
- `0x1800276f4`
- `0x18002a448`
- `0x180041010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180027747`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180027747`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_5b71e87bbd38edd0b6bc262bc572dce1_>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  unsigned int v8; // edi

  v6 = operator new(0x170u, (const struct std::nothrow_t *)std::nothrow);
  if ( v6 )
    v7 = Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_5b71e87bbd38edd0b6bc262bc572dce1_>::CTaskWrapper<_lambda_5b71e87bbd38edd0b6bc262bc572dce1_>(
           v6,
           a4);
  else
    v7 = 0;
  v8 = SHTaskPoolQueueTask(0, 4096, a3, 0, v7, 0);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x1800276f4  mov     [rsp+arg_0], rbx
0x1800276f9  push    rdi
0x1800276fa  sub     rsp, 30h
0x1800276fe  mov     rbx, r9
0x180027701  mov     edi, r8d
0x180027704  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002770b  mov     ecx, 170h; unsigned __int64
0x180027710  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027715  test    rax, rax
0x180027718  jz      short loc_18002772A
0x18002771a  mov     rdx, rbx
0x18002771d  mov     rcx, rax
0x180027720  call    ??$?0V_lambda_5b71e87bbd38edd0b6bc262bc572dce1_@@@?$CTaskWrapper@V_lambda_5b71e87bbd38edd0b6bc262bc572dce1_@@@ComTaskPool@Internal@Windows@@QEAA@$$QEAV_lambda_5b71e87bbd38edd0b6bc262bc572dce1_@@@Z; Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_5b71e87bbd38edd0b6bc262bc572dce1_>::CTaskWrapper<_lambda_5b71e87bbd38edd0b6bc262bc572dce1_>(_lambda_5b71e87bbd38edd0b6bc262bc572dce1_ &&)
0x180027725  mov     rbx, rax
0x180027728  jmp     short loc_18002772C
0x18002772a  xor     ebx, ebx
0x18002772c  mov     [rsp+38h+var_10], 0
0x180027735  mov     [rsp+38h+var_18], rbx
0x18002773a  xor     r9d, r9d
0x18002773d  mov     r8d, edi
0x180027740  mov     edx, 1000h
0x180027745  xor     ecx, ecx
0x180027747  call    cs:__imp_SHTaskPoolQueueTask
0x18002774d  mov     edi, eax
0x18002774f  test    rbx, rbx
0x180027752  jz      short loc_180027764
0x180027754  mov     rcx, [rbx]
0x180027757  mov     rax, [rcx+10h]
0x18002775b  mov     rcx, rbx
0x18002775e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027763  nop
0x180027764  mov     eax, edi
0x180027766  mov     rbx, [rsp+38h+arg_0]
0x18002776b  add     rsp, 30h
0x18002776f  pop     rdi
0x180027770  retn
```
