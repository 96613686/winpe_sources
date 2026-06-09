# Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(_lambda_ea734d1cec1fa7b22a66fb865ad05d37_ &&)

- ea: `0x14000622c`
- end: `0x1400062c5`
- name: `??$?0V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@QEAA@$$QEAV_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@Z`
- size: `153`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400068c4`

## callees

- `0x14000622c`
- `0x1400071f4`
- `0x14000a010`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v4; // rdx
  _QWORD *v5; // rcx

  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>(a1);
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  a1[2] = *a2;
  v4 = a2 + 1;
  a1[3] = 0;
  if ( a1 + 3 != a2 + 1 )
  {
    a1[3] = *v4;
    *v4 = 0;
  }
  v5 = a2 + 2;
  a1[4] = 0;
  if ( a1 + 4 != a2 + 2 )
  {
    a1[4] = *v5;
    *v5 = 0;
  }
  *a1 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x14000622c  mov     [rsp+arg_0], rbx
0x140006231  push    rdi
0x140006232  sub     rsp, 20h
0x140006236  mov     rdi, rdx
0x140006239  mov     rbx, rcx
0x14000623c  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>(void)
0x140006241  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x140006248  mov     [rbx], rcx
0x14000624b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140006252  test    rcx, rcx
0x140006255  jz      short loc_140006264
0x140006257  mov     rax, [rcx]
0x14000625a  mov     rax, [rax+8]
0x14000625e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006263  nop
0x140006264  mov     rax, [rdi]
0x140006267  mov     [rbx+10h], rax
0x14000626b  lea     rcx, [rbx+18h]
0x14000626f  lea     rdx, [rdi+8]
0x140006273  mov     qword ptr [rcx], 0
0x14000627a  cmp     rcx, rdx
0x14000627d  jz      short loc_14000628C
0x14000627f  mov     rax, [rdx]
0x140006282  mov     [rcx], rax
0x140006285  mov     qword ptr [rdx], 0
0x14000628c  lea     rdx, [rbx+20h]
0x140006290  lea     rcx, [rdi+10h]
0x140006294  mov     qword ptr [rdx], 0
0x14000629b  cmp     rdx, rcx
0x14000629e  jz      short loc_1400062AD
0x1400062a0  mov     rax, [rcx]
0x1400062a3  mov     [rdx], rax
0x1400062a6  mov     qword ptr [rcx], 0
0x1400062ad  lea     rax, ??_7?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>::`vftable'
0x1400062b4  mov     [rbx], rax
0x1400062b7  mov     rax, rbx
0x1400062ba  mov     rbx, [rsp+28h+arg_0]
0x1400062bf  add     rsp, 20h
0x1400062c3  pop     rdi
0x1400062c4  retn
```
