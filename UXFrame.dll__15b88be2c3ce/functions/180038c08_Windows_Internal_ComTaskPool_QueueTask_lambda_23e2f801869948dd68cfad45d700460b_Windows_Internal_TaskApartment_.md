# Windows::Internal::ComTaskPool::QueueTask<_lambda_23e2f801869948dd68cfad45d700460b_ &>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_23e2f801869948dd68cfad45d700460b_ &)

- ea: `0x180038c08`
- end: `0x180038ca3`
- name: `??$QueueTask@AEAV_lambda_23e2f801869948dd68cfad45d700460b_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@KAEAV_lambda_23e2f801869948dd68cfad45d700460b_@@@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041fd0`

## callees

- `0x180002bcc`
- `0x18000d1a0`
- `0x18000dccc`
- `0x180038c08`
- `0x18005a010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180038c77`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180038c77`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_23e2f801869948dd68cfad45d700460b_ &>(
        __int64 a1,
        unsigned int a2,
        unsigned int a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  unsigned int v8; // edi
  _QWORD *v10; // [rsp+30h] [rbp-28h] BYREF

  v5 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  v10 = v5;
  v7 = 0;
  if ( v5 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v5);
    *v6 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_23e2f801869948dd68cfad45d700460b_ &>::`vftable';
    v10 = 0;
    v7 = v6;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(&v10);
  v8 = SHTaskPoolQueueTask(3, a2, a3, 0);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x180038c08  mov     [rsp+arg_0], rbx
0x180038c0d  push    rbp
0x180038c0e  push    rsi
0x180038c0f  push    rdi
0x180038c10  sub     rsp, 40h
0x180038c14  mov     ebp, r8d
0x180038c17  mov     esi, edx
0x180038c19  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038c20  mov     ecx, 18h; unsigned __int64
0x180038c25  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038c2a  mov     rdi, rax
0x180038c2d  mov     [rsp+58h+var_28], rax
0x180038c32  xor     ebx, ebx
0x180038c34  test    rax, rax
0x180038c37  jz      short loc_180038C53
0x180038c39  mov     rcx, rax
0x180038c3c  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180038c41  lea     rax, ??_7?$CTaskWrapper@AEAV_lambda_23e2f801869948dd68cfad45d700460b_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_23e2f801869948dd68cfad45d700460b_ &>::`vftable'
0x180038c48  mov     [rdi], rax
0x180038c4b  mov     [rsp+58h+var_28], rbx
0x180038c50  mov     rbx, rdi
0x180038c53  lea     rcx, [rsp+58h+var_28]
0x180038c58  call    ??1?$MakeAllocator@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(void)
0x180038c5d  mov     [rsp+58h+var_30], 0
0x180038c66  mov     [rsp+58h+var_38], rbx
0x180038c6b  xor     r9d, r9d
0x180038c6e  mov     r8d, ebp
0x180038c71  mov     edx, esi
0x180038c73  lea     ecx, [r9+3]
0x180038c77  call    cs:__imp_SHTaskPoolQueueTask
0x180038c7d  mov     edi, eax
0x180038c7f  test    rbx, rbx
0x180038c82  jz      short loc_180038C94
0x180038c84  mov     rdx, [rbx]
0x180038c87  mov     rcx, rbx
0x180038c8a  mov     rax, [rdx+10h]
0x180038c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c93  nop
0x180038c94  mov     eax, edi
0x180038c96  mov     rbx, [rsp+58h+arg_0]
0x180038c9b  add     rsp, 40h
0x180038c9f  pop     rdi
0x180038ca0  pop     rsi
0x180038ca1  pop     rbp
0x180038ca2  retn
```
