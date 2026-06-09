# Microsoft::WRL::Details::Make<ToastFeedback,void * &,SendNotificationOperationResult * &>(void * &,SendNotificationOperationResult * &)

- ea: `0x14000e868`
- end: `0x14000e900`
- name: `??$Make@VToastFeedback@@AEAPEAXAEAPEAUSendNotificationOperationResult@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VToastFeedback@@@12@AEAPEAXAEAPEAUSendNotificationOperationResult@@@Z`
- size: `152`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000f45c`
- `0x14000fc50`

## callees

- `0x140001714`
- `0x14000e868`
- `0x140012010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<ToastFeedback,void * &,SendNotificationOperationResult * &>(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rbp

  *a1 = 0;
  v6 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    v8 = *a3;
    v9 = *a2;
    *((_DWORD *)v6 + 3) = 1;
    *v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<10>,IWpnToastFeedback>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v7 = &ToastFeedback::`vftable';
    v7[2] = v9;
    v7[3] = v8;
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v7;
  }
  return a1;
}

```

## disassembly

```asm
0x14000e868  push    rbx
0x14000e86a  push    rbp
0x14000e86b  push    rsi
0x14000e86c  push    rdi
0x14000e86d  sub     rsp, 28h
0x14000e871  mov     rsi, r8
0x14000e874  mov     rbp, rdx
0x14000e877  mov     rdi, rcx
0x14000e87a  mov     qword ptr [rcx], 0
0x14000e881  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e888  mov     ecx, 20h ; ' '; unsigned __int64
0x14000e88d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000e892  mov     rbx, rax
0x14000e895  test    rax, rax
0x14000e898  jz      short loc_14000E8F4
0x14000e89a  mov     rsi, [rsi]
0x14000e89d  mov     rbp, [rbp+0]
0x14000e8a1  mov     dword ptr [rax+0Ch], 1
0x14000e8a8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$09@WRL@Microsoft@@UIWpnToastFeedback@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<10>,IWpnToastFeedback>::`vftable'
0x14000e8af  mov     [rbx], rax
0x14000e8b2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000e8b9  test    rcx, rcx
0x14000e8bc  jz      short loc_14000E8CB
0x14000e8be  mov     rax, [rcx]
0x14000e8c1  mov     rax, [rax+8]
0x14000e8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e8ca  nop
0x14000e8cb  lea     rax, ??_7ToastFeedback@@6B@; const ToastFeedback::`vftable'
0x14000e8d2  mov     [rbx], rax
0x14000e8d5  mov     [rbx+10h], rbp
0x14000e8d9  mov     [rbx+18h], rsi
0x14000e8dd  mov     rcx, [rdi]
0x14000e8e0  test    rcx, rcx
0x14000e8e3  jz      short loc_14000E8F1
0x14000e8e5  mov     rax, [rcx]
0x14000e8e8  mov     rax, [rax+10h]
0x14000e8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e8f1  mov     [rdi], rbx
0x14000e8f4  mov     rax, rdi
0x14000e8f7  add     rsp, 28h
0x14000e8fb  pop     rdi
0x14000e8fc  pop     rsi
0x14000e8fd  pop     rbp
0x14000e8fe  pop     rbx
0x14000e8ff  retn
```
