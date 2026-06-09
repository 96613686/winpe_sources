# Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____lambda_1acd6cdd80cddfb63618e898b2901780___

- ea: `0x14000becc`
- end: `0x14000bf82`
- name: `Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____lambda_1acd6cdd80cddfb63618e898b2901780___`
- size: `182`
- prototype: `volatile signed __int32 **__fastcall(volatile signed __int32 **, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000bf88`

## callees

- `0x1400036e4`
- `0x14000becc`
- `0x14000c41c`
- `0x14000c600`
- `0x14000d130`
- `0x14000f010`

## pseudocode

```c
volatile signed __int32 **__fastcall Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____lambda_1acd6cdd80cddfb63618e898b2901780___(
        volatile signed __int32 **a1,
        __int64 a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  v7 = v4;
  if ( v4 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>((__int64)v4);
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[1] = *(_OWORD *)a2;
    *((_QWORD *)v5 + 4) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)v5 = &off_140010170;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(*a1);
    *a1 = (volatile signed __int32 *)v5;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____(&v7);
  return a1;
}

```

## disassembly

```asm
0x14000becc  mov     [rsp+arg_8], rbx
0x14000bed1  mov     [rsp+arg_10], rsi
0x14000bed6  push    rdi
0x14000bed7  sub     rsp, 20h
0x14000bedb  mov     rsi, rdx
0x14000bede  mov     rdi, rcx
0x14000bee1  mov     qword ptr [rcx], 0
0x14000bee8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000beef  mov     ecx, 28h ; '('; unsigned __int64
0x14000bef4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000bef9  mov     rbx, rax
0x14000befc  mov     [rsp+28h+arg_0], rax
0x14000bf01  test    rax, rax
0x14000bf04  jz      short loc_14000BF65
0x14000bf06  mov     rcx, rax
0x14000bf09  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>(void)
0x14000bf0e  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x14000bf15  mov     [rbx], rcx
0x14000bf18  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000bf1f  test    rcx, rcx
0x14000bf22  jz      short loc_14000BF31
0x14000bf24  mov     rax, [rcx]
0x14000bf27  mov     rax, [rax+8]
0x14000bf2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf30  nop
0x14000bf31  movups  xmm0, xmmword ptr [rsi]
0x14000bf34  movups  xmmword ptr [rbx+10h], xmm0
0x14000bf38  movsd   xmm1, qword ptr [rsi+10h]
0x14000bf3d  movsd   qword ptr [rbx+20h], xmm1
0x14000bf42  lea     rax, off_140010170
0x14000bf49  mov     [rbx], rax
0x14000bf4c  mov     rcx, [rdi]
0x14000bf4f  test    rcx, rcx
0x14000bf52  jz      short loc_14000BF59
0x14000bf54  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x14000bf59  mov     [rdi], rbx
0x14000bf5c  mov     [rsp+28h+arg_0], 0
0x14000bf65  lea     rcx, [rsp+28h+arg_0]
0x14000bf6a  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____
0x14000bf6f  mov     rax, rdi
0x14000bf72  mov     rbx, [rsp+28h+arg_8]
0x14000bf77  mov     rsi, [rsp+28h+arg_10]
0x14000bf7c  add     rsp, 20h
0x14000bf80  pop     rdi
0x14000bf81  retn
```
