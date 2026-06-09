# Microsoft::WRL::Details::Make<FeedbackResponseHandler,>(void)

- ea: `0x18000a7b4`
- end: `0x18000a859`
- name: `??$Make@VFeedbackResponseHandler@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFeedbackResponseHandler@@@12@XZ`
- size: `165`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bc70`

## callees

- `0x180003050`
- `0x18000a7b4`
- `0x18000b39c`
- `0x18000b464`
- `0x18001c010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<FeedbackResponseHandler,>(_QWORD *a1)
{
  _OWORD *v2; // rax
  _QWORD *v3; // rbx
  _OWORD *v5; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v5 = v2;
  if ( v2 )
  {
    *v2 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INotificationActivationCallback>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INotificationActivationCallback>(v2);
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,INotificationActivationCallback>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v3 = &FeedbackResponseHandler::`vftable';
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
    v5 = 0;
  }
  Z::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate,Windows::Foundation::AJPEAUIAsyncAction,enum tagCOWAIT_FLAGS,unsigned long,bool *>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate,Windows::Foundation::AJPEAUIAsyncAction,enum tagCOWAIT_FLAGS,unsigned long,bool *>(&v5);
  return a1;
}

```

## disassembly

```asm
0x18000a7b4  mov     [rsp+arg_8], rbx
0x18000a7b9  push    rdi
0x18000a7ba  sub     rsp, 20h
0x18000a7be  mov     rdi, rcx
0x18000a7c1  mov     qword ptr [rcx], 0
0x18000a7c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a7cf  mov     ecx, 10h; unsigned __int64
0x18000a7d4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a7d9  mov     rbx, rax
0x18000a7dc  mov     [rsp+28h+arg_0], rax
0x18000a7e1  test    rax, rax
0x18000a7e4  jz      short loc_18000A841
0x18000a7e6  xorps   xmm0, xmm0
0x18000a7e9  movups  xmmword ptr [rax], xmm0
0x18000a7ec  mov     rcx, rax
0x18000a7ef  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UINotificationActivationCallback@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INotificationActivationCallback>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INotificationActivationCallback>(void)
0x18000a7f4  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UINotificationActivationCallback@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,INotificationActivationCallback>::`vftable'
0x18000a7fb  mov     [rbx], rcx
0x18000a7fe  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a805  test    rcx, rcx
0x18000a808  jz      short loc_18000A817
0x18000a80a  mov     rax, [rcx]
0x18000a80d  mov     rax, [rax+8]
0x18000a811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a816  nop
0x18000a817  lea     rax, ??_7FeedbackResponseHandler@@6B@; const FeedbackResponseHandler::`vftable'
0x18000a81e  mov     [rbx], rax
0x18000a821  mov     rcx, [rdi]
0x18000a824  test    rcx, rcx
0x18000a827  jz      short loc_18000A835
0x18000a829  mov     rax, [rcx]
0x18000a82c  mov     rax, [rax+10h]
0x18000a830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a835  mov     [rdi], rbx
0x18000a838  mov     [rsp+28h+arg_0], 0
0x18000a841  lea     rcx, [rsp+28h+arg_0]
0x18000a846  call    ??1?$MakeAllocator@VCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>(void)
0x18000a84b  mov     rax, rdi
0x18000a84e  mov     rbx, [rsp+28h+arg_8]
0x18000a853  add     rsp, 20h
0x18000a857  pop     rdi
0x18000a858  retn
```
