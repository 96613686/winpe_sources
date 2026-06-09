# Windows::Internal::ComTaskPool::QueueTask<_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_ &>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_ &)

- ea: `0x180038cac`
- end: `0x180038d49`
- name: `??$QueueTask@AEAV_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@KAEAV_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_@@@Z`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044fe8`

## callees

- `0x180002bcc`
- `0x18000dccc`
- `0x180037168`
- `0x180038cac`
- `0x18005a010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180038d1a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180038d1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_ &>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  void *v6; // rax
  __int64 v7; // rbx
  unsigned int v8; // edi
  void *v10; // [rsp+30h] [rbp-18h] BYREF

  v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v6;
  v7 = 0;
  if ( v6 )
  {
    v7 = Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_ &>::CTaskWrapper<_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_ &>(
           v6,
           a4);
    v10 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(&v10);
  v8 = SHTaskPoolQueueTask(3, 2, a3, 0);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x180038cac  mov     [rsp+arg_0], rbx
0x180038cb1  mov     [rsp+arg_8], rsi
0x180038cb6  push    rdi
0x180038cb7  sub     rsp, 40h
0x180038cbb  mov     rdi, r9
0x180038cbe  mov     esi, r8d
0x180038cc1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038cc8  mov     ecx, 40h ; '@'; unsigned __int64
0x180038ccd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038cd2  mov     [rsp+48h+var_18], rax
0x180038cd7  xor     ebx, ebx
0x180038cd9  test    rax, rax
0x180038cdc  jz      short loc_180038CF5
0x180038cde  mov     rdx, rdi
0x180038ce1  mov     rcx, rax
0x180038ce4  call    ??$?0AEAV_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_@@@?$CTaskWrapper@AEAV_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_@@@ComTaskPool@Internal@Windows@@QEAA@AEAV_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_@@@Z; Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_ &>::CTaskWrapper<_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_ &>(_lambda_f9fb72aaeed3981bf3fb5e6c5660c9fb_ &)
0x180038ce9  mov     rbx, rax
0x180038cec  mov     [rsp+48h+var_18], 0
0x180038cf5  lea     rcx, [rsp+48h+var_18]
0x180038cfa  call    ??1?$MakeAllocator@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(void)
0x180038cff  mov     [rsp+48h+var_20], 0
0x180038d08  mov     [rsp+48h+var_28], rbx
0x180038d0d  xor     r9d, r9d
0x180038d10  mov     r8d, esi
0x180038d13  lea     edx, [r9+2]
0x180038d17  lea     ecx, [rdx+1]
0x180038d1a  call    cs:__imp_SHTaskPoolQueueTask
0x180038d20  mov     edi, eax
0x180038d22  test    rbx, rbx
0x180038d25  jz      short loc_180038D37
0x180038d27  mov     rdx, [rbx]
0x180038d2a  mov     rcx, rbx
0x180038d2d  mov     rax, [rdx+10h]
0x180038d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d36  nop
0x180038d37  mov     eax, edi
0x180038d39  mov     rbx, [rsp+48h+arg_0]
0x180038d3e  mov     rsi, [rsp+48h+arg_8]
0x180038d43  add     rsp, 40h
0x180038d47  pop     rdi
0x180038d48  retn
```
