# CApplicationFrameEvents::NotifyPositionChanged(IApplicationFrame *)

- ea: `0x180014c50`
- end: `0x180014ebb`
- name: `?NotifyPositionChanged@CApplicationFrameEvents@@UEAAXPEAUIApplicationFrame@@@Z`
- size: `619`
- prototype: `void __fastcall(CApplicationFrameEvents *__hidden this, struct IApplicationFrame *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800145f0`
- `0x180014c50`
- `0x180046b0c`
- `0x180054454`
- `0x180072010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180014d7b`
- `SHCORE!SHTaskPoolQueueTask` at `0x180014d7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CApplicationFrameEvents::NotifyPositionChanged(
        CApplicationFrameEvents *this,
        struct IApplicationFrame *a2,
        __int64 a3,
        int a4)
{
  signed __int32 i; // eax
  _QWORD *v7; // r14
  unsigned int v8; // r15d
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  _QWORD *v11; // r14
  __int64 v12; // rcx
  volatile signed __int32 *v13; // r8
  signed __int32 j; // edx
  signed __int32 k; // edx
  volatile signed __int32 *v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+48h] [rbp-30h]
  CApplicationFrameEvents *v18; // [rsp+88h] [rbp+10h] BYREF

  if ( a2 )
    (*(void (__fastcall **)(struct IApplicationFrame *))(*(_QWORD *)a2 + 8LL))(a2);
  v18 = this;
  if ( this )
  {
    for ( i = *((_DWORD *)this + 11); i != 0x7FFFFFFF; i = *((_DWORD *)this + 11) )
    {
      if ( i == _InterlockedCompareExchange((volatile signed __int32 *)this + 11, i + 1, i) )
        break;
    }
  }
  v7 = (_QWORD *)lambda_d73e93ec8c95ac22667ea5f0ddccd7ff_::_lambda_d73e93ec8c95ac22667ea5f0ddccd7ff_(
                   (unsigned int)&v16,
                   (unsigned int)&v18,
                   (_DWORD)this,
                   a4);
  v8 = *((_DWORD *)this + 22);
  v9 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v9;
  if ( v9 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>(v9);
    *v10 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v10[2] = 0;
    if ( v10 + 2 != v7 )
    {
      v10[2] = *v7;
      *v7 = 0;
    }
    v10[3] = v7[1];
    v11 = v7 + 3;
    v10[5] = 0;
    if ( v10 + 5 != v11 )
    {
      v10[5] = *v11;
      *v11 = 0;
    }
    *v10 = &off_1800731C8;
  }
  else
  {
    v10 = 0;
  }
  SHTaskPoolQueueTask(3, 2, v8, 0);
  if ( v10 )
    (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
  v12 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v16;
  if ( v16 )
  {
    v16 = 0;
    for ( j = *((_DWORD *)v13 + 11); j != 0x7FFFFFFF; j = *((_DWORD *)v13 + 11) )
    {
      if ( j == _InterlockedCompareExchange(v13 + 11, j - 1, j) )
        break;
    }
    if ( j == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v13 + 64LL))(v13, 1);
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
    }
  }
  for ( k = *((_DWORD *)this + 11); k != 0x7FFFFFFF; k = *((_DWORD *)this + 11) )
  {
    if ( k == _InterlockedCompareExchange((volatile signed __int32 *)this + 11, k - 1, k) )
      break;
  }
  if ( k == 1 )
  {
    (*(void (__fastcall **)(CApplicationFrameEvents *, __int64))(*(_QWORD *)this + 64LL))(this, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  if ( a2 )
    (*(void (__fastcall **)(struct IApplicationFrame *))(*(_QWORD *)a2 + 16LL))(a2);
}

```

## disassembly

```asm
0x180014c50  mov     [rsp+arg_10], rbx
0x180014c55  push    rbp
0x180014c56  push    rsi
0x180014c57  push    rdi
0x180014c58  push    r14
0x180014c5a  push    r15
0x180014c5c  sub     rsp, 50h
0x180014c60  mov     rsi, rdx
0x180014c63  mov     rdi, rcx
0x180014c66  mov     [rsp+78h+arg_0], rdx
0x180014c6e  test    rdx, rdx
0x180014c71  jz      short loc_180014C83
0x180014c73  mov     rax, [rdx]
0x180014c76  mov     rcx, rdx
0x180014c79  mov     rax, [rax+8]
0x180014c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c82  nop
0x180014c83  mov     [rsp+78h+arg_8], rdi
0x180014c8b  test    rdi, rdi
0x180014c8e  jz      short loc_180014CAE
0x180014c90  mov     eax, [rdi+2Ch]
0x180014c93  cmp     eax, 7FFFFFFFh
0x180014c98  jz      short loc_180014CAE
0x180014c9a  lea     ecx, [rax+1]
0x180014c9d  lock cmpxchg [rdi+2Ch], ecx
0x180014ca2  jz      short loc_180014CAE
0x180014ca4  mov     eax, [rdi+2Ch]
0x180014ca7  cmp     eax, 7FFFFFFFh
0x180014cac  jnz     short loc_180014C9A
0x180014cae  lea     rax, [rsp+78h+arg_0]
0x180014cb6  mov     [rsp+78h+var_50], rax
0x180014cbb  mov     r8, rdi
0x180014cbe  lea     rdx, [rsp+78h+arg_8]
0x180014cc6  lea     rcx, [rsp+78h+var_48]
0x180014ccb  call    _lambda_d73e93ec8c95ac22667ea5f0ddccd7ff____lambda_d73e93ec8c95ac22667ea5f0ddccd7ff_
0x180014cd0  mov     r14, rax
0x180014cd3  mov     r15d, [rdi+58h]
0x180014cd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014cde  mov     ecx, 30h ; '0'; unsigned __int64
0x180014ce3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014ce8  mov     rbx, rax
0x180014ceb  test    rax, rax
0x180014cee  jz      loc_180014E2D
0x180014cf4  mov     rcx, rax
0x180014cf7  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExtensionStateManager@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>(void)
0x180014cfc  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x180014d03  mov     [rbx], rcx
0x180014d06  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180014d0d  test    rcx, rcx
0x180014d10  jz      short loc_180014D1F
0x180014d12  mov     rax, [rcx]
0x180014d15  mov     rax, [rax+8]
0x180014d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d1e  nop
0x180014d1f  lea     rcx, [rbx+10h]
0x180014d23  xor     ebp, ebp
0x180014d25  mov     [rcx], rbp
0x180014d28  cmp     rcx, r14
0x180014d2b  jz      short loc_180014D36
0x180014d2d  mov     rax, [r14]
0x180014d30  mov     [rcx], rax
0x180014d33  mov     [r14], rbp
0x180014d36  mov     rax, [r14+8]
0x180014d3a  mov     [rcx+8], rax
0x180014d3e  add     rcx, 18h
0x180014d42  add     r14, 18h
0x180014d46  mov     [rcx], rbp
0x180014d49  cmp     rcx, r14
0x180014d4c  jz      short loc_180014D57
0x180014d4e  mov     rax, [r14]
0x180014d51  mov     [rcx], rax
0x180014d54  mov     [r14], rbp
0x180014d57  lea     rax, off_1800731C8
0x180014d5e  mov     [rbx], rax
0x180014d61  mov     [rsp+78h+var_50], rbp
0x180014d66  mov     [rsp+78h+var_58], rbx
0x180014d6b  xor     r9d, r9d
0x180014d6e  mov     r8d, r15d
0x180014d71  mov     edx, 2
0x180014d76  mov     ecx, 3
0x180014d7b  call    cs:__imp_SHTaskPoolQueueTask
0x180014d81  nop
0x180014d82  test    rbx, rbx
0x180014d85  jz      short loc_180014D97
0x180014d87  mov     rax, [rbx]
0x180014d8a  mov     rcx, rbx
0x180014d8d  mov     rax, [rax+10h]
0x180014d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d96  nop
0x180014d97  mov     rcx, [rsp+78h+var_30]
0x180014d9c  test    rcx, rcx
0x180014d9f  jz      short loc_180014DB3
0x180014da1  mov     [rsp+78h+var_30], rbp
0x180014da6  mov     rax, [rcx]
0x180014da9  mov     rax, [rax+10h]
0x180014dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014db2  nop
0x180014db3  mov     r8, [rsp+78h+var_48]
0x180014db8  test    r8, r8
0x180014dbb  jz      short loc_180014DE2
0x180014dbd  mov     [rsp+78h+var_48], rbp
0x180014dc2  mov     edx, [r8+2Ch]
0x180014dc6  cmp     edx, 7FFFFFFFh
0x180014dcc  jz      short loc_180014DDB
0x180014dce  lea     ecx, [rdx-1]
0x180014dd1  mov     eax, edx
0x180014dd3  lock cmpxchg [r8+2Ch], ecx
0x180014dd9  jnz     short loc_180014E36
0x180014ddb  lea     eax, [rdx-1]
0x180014dde  test    eax, eax
0x180014de0  jz      short loc_180014E51
0x180014de2  mov     edx, [rdi+2Ch]
0x180014de5  cmp     edx, 7FFFFFFFh
0x180014deb  jz      short loc_180014DF9
0x180014ded  lea     ecx, [rdx-1]
0x180014df0  mov     eax, edx
0x180014df2  lock cmpxchg [rdi+2Ch], ecx
0x180014df7  jnz     short loc_180014E44
0x180014df9  lea     eax, [rdx-1]
0x180014dfc  test    eax, eax
0x180014dfe  jz      loc_180014E86
0x180014e04  test    rsi, rsi
0x180014e07  jz      short loc_180014E19
0x180014e09  mov     rax, [rsi]
0x180014e0c  mov     rcx, rsi
0x180014e0f  mov     rax, [rax+10h]
0x180014e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e18  nop
0x180014e19  mov     rbx, [rsp+78h+arg_10]
0x180014e21  add     rsp, 50h
0x180014e25  pop     r15
0x180014e27  pop     r14
0x180014e29  pop     rdi
0x180014e2a  pop     rsi
0x180014e2b  pop     rbp
0x180014e2c  retn
0x180014e2d  xor     ebp, ebp
0x180014e2f  mov     ebx, ebp
0x180014e31  jmp     loc_180014D61
0x180014e36  mov     edx, [r8+2Ch]
0x180014e3a  cmp     edx, 7FFFFFFFh
0x180014e40  jnz     short loc_180014DCE
0x180014e42  jmp     short loc_180014DDB
0x180014e44  mov     edx, [rdi+2Ch]
0x180014e47  cmp     edx, 7FFFFFFFh
0x180014e4d  jnz     short loc_180014DED
0x180014e4f  jmp     short loc_180014DF9
0x180014e51  mov     rax, [r8]
0x180014e54  mov     edx, 1
0x180014e59  mov     rcx, r8
0x180014e5c  mov     rax, [rax+40h]
0x180014e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e65  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180014e6c  test    rcx, rcx
0x180014e6f  jz      loc_180014DE2
0x180014e75  mov     rax, [rcx]
0x180014e78  mov     rax, [rax+10h]
0x180014e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e81  jmp     loc_180014DE2
0x180014e86  mov     rax, [rdi]
0x180014e89  mov     edx, 1
0x180014e8e  mov     rcx, rdi
0x180014e91  mov     rax, [rax+40h]
0x180014e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e9a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180014ea1  test    rcx, rcx
0x180014ea4  jz      loc_180014E04
0x180014eaa  mov     rax, [rcx]
0x180014ead  mov     rax, [rax+10h]
0x180014eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb6  jmp     loc_180014E04
```
