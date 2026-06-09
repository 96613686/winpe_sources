# Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)

- ea: `0x1800141a0`
- end: `0x180014262`
- name: `??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z`
- size: `194`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a2bc`

## callees

- `0x18000446c`
- `0x180006574`
- `0x1800096c8`
- `0x18000f850`
- `0x1800141a0`
- `0x180027010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v7 = v4;
  if ( v4 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(v4);
    *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[2] = 0;
    if ( v5 + 2 != a2 )
    {
      v5[2] = *a2;
      *a2 = 0;
    }
    *v5 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vftable';
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    *a1 = v5;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v7);
  return a1;
}

```

## disassembly

```asm
0x1800141a0  mov     [rsp+arg_8], rbx
0x1800141a5  mov     [rsp+arg_10], rsi
0x1800141aa  push    rdi
0x1800141ab  sub     rsp, 20h
0x1800141af  mov     rsi, rdx
0x1800141b2  mov     rdi, rcx
0x1800141b5  mov     qword ptr [rcx], 0
0x1800141bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800141c3  mov     ecx, 18h; unsigned __int64
0x1800141c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800141cd  mov     rbx, rax
0x1800141d0  mov     [rsp+28h+arg_0], rax
0x1800141d5  test    rax, rax
0x1800141d8  jz      short loc_180014245
0x1800141da  mov     rcx, rax
0x1800141dd  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x1800141e2  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x1800141e9  mov     [rbx], rcx
0x1800141ec  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800141f3  test    rcx, rcx
0x1800141f6  jz      short loc_180014205
0x1800141f8  mov     rax, [rcx]
0x1800141fb  mov     rax, [rax+8]
0x1800141ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014204  nop
0x180014205  lea     rcx, [rbx+10h]
0x180014209  mov     qword ptr [rcx], 0
0x180014210  cmp     rcx, rsi
0x180014213  jz      short loc_180014222
0x180014215  mov     rax, [rsi]
0x180014218  mov     [rcx], rax
0x18001421b  mov     qword ptr [rsi], 0
0x180014222  lea     rax, ??_7?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vftable'
0x180014229  mov     [rbx], rax
0x18001422c  mov     rcx, [rdi]
0x18001422f  test    rcx, rcx
0x180014232  jz      short loc_180014239
0x180014234  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180014239  mov     [rdi], rbx
0x18001423c  mov     [rsp+28h+arg_0], 0
0x180014245  lea     rcx, [rsp+28h+arg_0]
0x18001424a  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18001424f  mov     rax, rdi
0x180014252  mov     rbx, [rsp+28h+arg_8]
0x180014257  mov     rsi, [rsp+28h+arg_10]
0x18001425c  add     rsp, 20h
0x180014260  pop     rdi
0x180014261  retn
```
