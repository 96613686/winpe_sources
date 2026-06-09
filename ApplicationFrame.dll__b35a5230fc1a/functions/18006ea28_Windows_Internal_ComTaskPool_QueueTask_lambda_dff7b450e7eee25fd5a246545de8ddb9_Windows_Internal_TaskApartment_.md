# Windows::Internal::ComTaskPool::QueueTask<_lambda_dff7b450e7eee25fd5a246545de8ddb9_>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_dff7b450e7eee25fd5a246545de8ddb9_ &&)

- ea: `0x18006ea28`
- end: `0x18006eac0`
- name: `??$QueueTask@V_lambda_dff7b450e7eee25fd5a246545de8ddb9_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@K$$QEAV_lambda_dff7b450e7eee25fd5a246545de8ddb9_@@@Z`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180004fbc`

## callees

- `0x1800145b0`
- `0x180025bcc`
- `0x180046b0c`
- `0x18006ea28`
- `0x180072010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18006ea98`
- `SHCORE!SHTaskPoolQueueTask` at `0x18006ea98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask<_lambda_dff7b450e7eee25fd5a246545de8ddb9_>(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        ...)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  unsigned int v8; // edi
  _QWORD *v10; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, _QWORD *);
  v5 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  v10 = v5;
  v7 = 0;
  if ( v5 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v5);
    *v6 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_dff7b450e7eee25fd5a246545de8ddb9_>::`vftable';
    v10 = 0;
    v7 = v6;
  }
  Microsoft::WRL::Details::MakeAllocator<NonAgileDispatcher>::~MakeAllocator<NonAgileDispatcher>((_QWORD **)va);
  v8 = SHTaskPoolQueueTask(3, a2, a3, 0);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x18006ea28  mov     [rsp+arg_18], r9
0x18006ea2d  push    rbx
0x18006ea2e  push    rbp
0x18006ea2f  push    rsi
0x18006ea30  push    rdi
0x18006ea31  sub     rsp, 38h
0x18006ea35  mov     esi, r8d
0x18006ea38  mov     ebp, edx
0x18006ea3a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006ea41  mov     ecx, 18h; unsigned __int64
0x18006ea46  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006ea4b  mov     rdi, rax
0x18006ea4e  mov     [rsp+58h+arg_18], rax
0x18006ea53  xor     ebx, ebx
0x18006ea55  test    rax, rax
0x18006ea58  jz      short loc_18006EA74
0x18006ea5a  mov     rcx, rax
0x18006ea5d  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x18006ea62  lea     rax, ??_7?$CTaskWrapper@V_lambda_dff7b450e7eee25fd5a246545de8ddb9_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_dff7b450e7eee25fd5a246545de8ddb9_>::`vftable'
0x18006ea69  mov     [rdi], rax
0x18006ea6c  mov     [rsp+58h+arg_18], rbx
0x18006ea71  mov     rbx, rdi
0x18006ea74  lea     rcx, [rsp+58h+arg_18]
0x18006ea79  call    ??1?$MakeAllocator@VNonAgileDispatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<NonAgileDispatcher>::~MakeAllocator<NonAgileDispatcher>(void)
0x18006ea7e  mov     [rsp+58h+var_30], 0
0x18006ea87  mov     [rsp+58h+var_38], rbx
0x18006ea8c  xor     r9d, r9d
0x18006ea8f  mov     r8d, esi
0x18006ea92  mov     edx, ebp
0x18006ea94  lea     ecx, [r9+3]
0x18006ea98  call    cs:__imp_SHTaskPoolQueueTask
0x18006ea9e  mov     edi, eax
0x18006eaa0  test    rbx, rbx
0x18006eaa3  jz      short loc_18006EAB5
0x18006eaa5  mov     rdx, [rbx]
0x18006eaa8  mov     rcx, rbx
0x18006eaab  mov     rax, [rdx+10h]
0x18006eaaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eab4  nop
0x18006eab5  mov     eax, edi
0x18006eab7  add     rsp, 38h
0x18006eabb  pop     rdi
0x18006eabc  pop     rsi
0x18006eabd  pop     rbp
0x18006eabe  pop     rbx
0x18006eabf  retn
```
