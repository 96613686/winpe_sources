# Microsoft::WRL::Details::Make<CShutdownPopupCommand,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,long (*)(IPopupWindow *,IPopupCommand *,void *),CSystemPopupWindow *,uint,uint &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&,long (*&&)(IPopupWindow *,IPopupCommand *,void *),CSystemPopupWindow * &&,uint &&,uint &)

- ea: `0x140007d6c`
- end: `0x140007e4c`
- name: `??$Make@VCShutdownPopupCommand@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@ZPEAVCSystemPopupWindow@@IAEAI@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCShutdownPopupCommand@@@12@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAP6AJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z$$QEAPEAVCSystemPopupWindow@@$$QEAIAEAI@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008368`

## callees

- `0x1400014c8`
- `0x140007d6c`
- `0x14000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<CShutdownPopupCommand,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,long (*)(IPopupWindow *,IPopupCommand *,void *),CSystemPopupWindow *,unsigned int,unsigned int &>(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4,
        int *a5,
        int *a6)
{
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  int v12; // ebp
  int v13; // r14d
  __int64 v14; // r15
  __int64 v15; // r12
  __int64 v16; // r13

  *a1 = 0;
  v10 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    v12 = *a6;
    v13 = *a5;
    v14 = *a4;
    v15 = *a3;
    v16 = *a2;
    *a2 = 0;
    v10[3] = 1;
    *(_QWORD *)v10 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v11 = &CShutdownPopupCommand::`vftable';
    *((_QWORD *)v11 + 2) = v16;
    *((_QWORD *)v11 + 3) = v15;
    *((_QWORD *)v11 + 4) = v14;
    v11[10] = v13;
    v11[11] = v12;
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v11;
  }
  return a1;
}

```

## disassembly

```asm
0x140007d6c  mov     [rsp+arg_10], rbx
0x140007d71  push    rbp
0x140007d72  push    rsi
0x140007d73  push    rdi
0x140007d74  push    r12
0x140007d76  push    r13
0x140007d78  push    r14
0x140007d7a  push    r15
0x140007d7c  sub     rsp, 20h
0x140007d80  mov     r15, r9
0x140007d83  mov     r12, r8
0x140007d86  mov     rsi, rdx
0x140007d89  mov     rdi, rcx
0x140007d8c  mov     qword ptr [rcx], 0
0x140007d93  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140007d9a  mov     ecx, 30h ; '0'; unsigned __int64
0x140007d9f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140007da4  mov     rbx, rax
0x140007da7  test    rax, rax
0x140007daa  jz      loc_140007E34
0x140007db0  mov     rax, [rsp+58h+arg_28]
0x140007db8  mov     ebp, [rax]
0x140007dba  mov     rax, [rsp+58h+arg_20]
0x140007dc2  mov     r14d, [rax]
0x140007dc5  mov     r15, [r15]
0x140007dc8  mov     r12, [r12]
0x140007dcc  mov     r13, [rsi]
0x140007dcf  mov     qword ptr [rsi], 0
0x140007dd6  mov     dword ptr [rbx+0Ch], 1
0x140007ddd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupCommand@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vftable'
0x140007de4  mov     [rbx], rax
0x140007de7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140007dee  test    rcx, rcx
0x140007df1  jz      short loc_140007E00
0x140007df3  mov     rax, [rcx]
0x140007df6  mov     rax, [rax+8]
0x140007dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007dff  nop
0x140007e00  lea     rax, ??_7CShutdownPopupCommand@@6B@; const CShutdownPopupCommand::`vftable'
0x140007e07  mov     [rbx], rax
0x140007e0a  mov     [rbx+10h], r13
0x140007e0e  mov     [rbx+18h], r12
0x140007e12  mov     [rbx+20h], r15
0x140007e16  mov     [rbx+28h], r14d
0x140007e1a  mov     [rbx+2Ch], ebp
0x140007e1d  mov     rcx, [rdi]
0x140007e20  test    rcx, rcx
0x140007e23  jz      short loc_140007E31
0x140007e25  mov     rdx, [rcx]
0x140007e28  mov     rax, [rdx+10h]
0x140007e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e31  mov     [rdi], rbx
0x140007e34  mov     rax, rdi
0x140007e37  mov     rbx, [rsp+58h+arg_10]
0x140007e3c  add     rsp, 20h
0x140007e40  pop     r15
0x140007e42  pop     r14
0x140007e44  pop     r13
0x140007e46  pop     r12
0x140007e48  pop     rdi
0x140007e49  pop     rsi
0x140007e4a  pop     rbp
0x140007e4b  retn
```
