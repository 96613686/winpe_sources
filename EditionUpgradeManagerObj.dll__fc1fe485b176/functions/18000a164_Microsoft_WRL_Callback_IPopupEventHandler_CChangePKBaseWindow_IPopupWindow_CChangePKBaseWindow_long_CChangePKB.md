# Microsoft::WRL::Callback<IPopupEventHandler,CChangePKBaseWindow,IPopupWindow *>(CChangePKBaseWindow *,long (CChangePKBaseWindow::*)(IPopupWindow *))

- ea: `0x18000a164`
- end: `0x18000a1f6`
- name: `??$Callback@UIPopupEventHandler@@VCChangePKBaseWindow@@PEAUIPopupWindow@@@WRL@Microsoft@@YA?AV?$ComPtr@UIPopupEventHandler@@@01@PEAVCChangePKBaseWindow@@P83@EAAJPEAUIPopupWindow@@@Z@Z`
- size: `146`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int128 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aae0`
- `0x18000ac30`

## callees

- `0x180001ea8`
- `0x18000a164`
- `0x180023010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Callback<IPopupEventHandler,CChangePKBaseWindow,IPopupWindow *>(
        _QWORD *a1,
        __int64 a2,
        __int128 *a3)
{
  __int128 v4; // xmm6
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v8; // rcx
  _QWORD *result; // rax

  v4 = *a3;
  v6 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    v8 = Microsoft::WRL::Details::ModuleBase::module_;
    v6[3] = 1;
    *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupEventHandler>::`vftable';
    if ( v8 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v8 + 8LL))(v8);
    *((_QWORD *)v7 + 2) = a2;
    *(_QWORD *)v7 = &Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_e4ce5bad0469af69b33143adf1b7894d_,-1,IPopupWindow *>::`vftable';
    *(_OWORD *)(v7 + 6) = v4;
  }
  else
  {
    v7 = 0;
  }
  result = a1;
  *a1 = v7;
  return result;
}

```

## disassembly

```asm
0x18000a164  mov     [rsp+arg_0], rbx
0x18000a169  mov     [rsp+arg_8], rsi
0x18000a16e  push    rdi
0x18000a16f  sub     rsp, 30h
0x18000a173  mov     rsi, rdx
0x18000a176  movaps  [rsp+38h+var_18], xmm6
0x18000a17b  movups  xmm6, xmmword ptr [r8]
0x18000a17f  mov     rdi, rcx
0x18000a182  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a189  mov     ecx, 28h ; '('; unsigned __int64
0x18000a18e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a193  mov     rbx, rax
0x18000a196  test    rax, rax
0x18000a199  jz      short loc_18000A1D9
0x18000a19b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a1a2  mov     dword ptr [rax+0Ch], 1
0x18000a1a9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupEventHandler@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupEventHandler>::`vftable'
0x18000a1b0  mov     [rbx], rax
0x18000a1b3  test    rcx, rcx
0x18000a1b6  jz      short loc_18000A1C4
0x18000a1b8  mov     rax, [rcx]
0x18000a1bb  mov     rax, [rax+8]
0x18000a1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c4  lea     rax, ??_7?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_e4ce5bad0469af69b33143adf1b7894d_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_e4ce5bad0469af69b33143adf1b7894d_,-1,IPopupWindow *>::`vftable'
0x18000a1cb  mov     [rbx+10h], rsi
0x18000a1cf  mov     [rbx], rax
0x18000a1d2  movdqu  xmmword ptr [rbx+18h], xmm6
0x18000a1d7  jmp     short loc_18000A1DB
0x18000a1d9  xor     ebx, ebx
0x18000a1db  mov     rsi, [rsp+38h+arg_8]
0x18000a1e0  mov     rax, rdi
0x18000a1e3  movaps  xmm6, [rsp+38h+var_18]
0x18000a1e8  mov     [rdi], rbx
0x18000a1eb  mov     rbx, [rsp+38h+arg_0]
0x18000a1f0  add     rsp, 30h
0x18000a1f4  pop     rdi
0x18000a1f5  retn
```
