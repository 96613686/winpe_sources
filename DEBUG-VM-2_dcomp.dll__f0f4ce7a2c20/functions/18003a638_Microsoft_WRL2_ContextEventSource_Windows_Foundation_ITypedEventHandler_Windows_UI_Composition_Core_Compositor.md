# Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy(Microsoft::WRL2::ContextSession *)

- ea: `0x18003a638`
- end: `0x18003a7ac`
- name: `?Destroy@?$ContextEventSource@U?$ITypedEventHandler@PEAVCompositorController@Core@Composition@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL2@Microsoft@@QEAAXPEAVContextSession@23@@Z`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800587fc`
- `0x18006f9a0`

## callees

- `0x1800093f4`
- `0x18003a598`
- `0x18003a638`
- `0x18003aa74`
- `0x18003b144`
- `0x18003b178`
- `0x1800a0fb8`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a67a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a699`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a67a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a699`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a6b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a782`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a6b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a782`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a669`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a669`

## pseudocode

```c
void __fastcall Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy(
        RTL_SRWLOCK *a1,
        _QWORD *a2)
{
  int v4; // ebx
  _QWORD *Ptr; // rax
  __int64 *i; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  _BYTE *v9; // rdx
  _QWORD v10[2]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v11[56]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE *v12; // [rsp+68h] [rbp-30h]

  v4 = *(_DWORD *)(a2[7] + 40LL);
  if ( v4 == GetCurrentThreadId() )
  {
    AcquireSRWLockExclusive(a1 + 2);
    Ptr = a1->Ptr;
    if ( a1->Ptr )
    {
      for ( i = (__int64 *)Ptr[2]; i != (__int64 *)Ptr[3]; ++i )
      {
        v7 = *i;
        *i = 0;
        if ( v7 )
        {
          v10[0] = v7;
          v12 = 0;
          v12 = (_BYTE *)std::_Func_impl_no_alloc__Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker_::_5_::_lambda_1__void_::_Func_impl_no_alloc__Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker_::_5_::_lambda_1__void___Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker_::_5_::_lambda_1__0_(
                           v11,
                           v10);
          v8 = a2[16];
          if ( v8 == a2[17] )
          {
            std::vector<std::function<void (void)>>::_Emplace_reallocate<std::function<void (void)>>(
              a2 + 15,
              a2[16],
              v11);
          }
          else
          {
            *(_QWORD *)(v8 + 56) = 0;
            std::_Func_class<void,>::_Reset_move(v8, v11);
            a2[16] += 64LL;
          }
          if ( v12 )
          {
            v9 = v11;
            LOBYTE(v9) = v12 != v11;
            (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v12 + 32LL))(v12, v9);
            v12 = 0;
          }
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(v10);
        }
        Ptr = a1->Ptr;
      }
      AcquireSRWLockExclusive(a1 + 1);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalRelease(a1);
      if ( a1 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(a1 + 1);
    }
    if ( a1 != (RTL_SRWLOCK *)-16LL )
      ReleaseSRWLockExclusive(a1 + 2);
  }
  else
  {
    Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy_NoLock(a1);
  }
}

```

## disassembly

```asm
0x18003a638  mov     [rsp+arg_10], rbx
0x18003a63d  mov     [rsp+arg_18], rbp
0x18003a642  push    rsi
0x18003a643  push    rdi
0x18003a644  push    r14
0x18003a646  sub     rsp, 80h
0x18003a64d  mov     rax, cs:__security_cookie
0x18003a654  xor     rax, rsp
0x18003a657  mov     [rsp+98h+var_28], rax
0x18003a65c  mov     rax, [rdx+38h]
0x18003a660  mov     r14, rdx
0x18003a663  mov     rdi, rcx
0x18003a666  mov     ebx, [rax+28h]
0x18003a669  call    cs:__imp_GetCurrentThreadId
0x18003a66f  cmp     ebx, eax
0x18003a671  jnz     short loc_18003A6C0
0x18003a673  lea     rbx, [rdi+10h]
0x18003a677  mov     rcx, rbx; SRWLock
0x18003a67a  call    cs:__imp_AcquireSRWLockExclusive
0x18003a680  mov     rax, [rdi]
0x18003a683  test    rax, rax
0x18003a686  jz      short loc_18003A6B0
0x18003a688  mov     rsi, [rax+10h]
0x18003a68c  cmp     rsi, [rax+18h]
0x18003a690  jnz     short loc_18003A6ED
0x18003a692  lea     rsi, [rdi+8]
0x18003a696  mov     rcx, rsi; SRWLock
0x18003a699  call    cs:__imp_AcquireSRWLockExclusive
0x18003a69f  mov     rcx, rdi
0x18003a6a2  call    ?InternalRelease@?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalRelease(void)
0x18003a6a7  test    rsi, rsi
0x18003a6aa  jnz     loc_18003A77F
0x18003a6b0  test    rbx, rbx
0x18003a6b3  jz      short loc_18003A6C8
0x18003a6b5  mov     rcx, rbx; SRWLock
0x18003a6b8  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a6be  jmp     short loc_18003A6C8
0x18003a6c0  mov     rcx, rdi
0x18003a6c3  call    ?Destroy_NoLock@?$ContextEventSource@U?$ITypedEventHandler@PEAVCompositorController@Core@Composition@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy_NoLock(void)
0x18003a6c8  mov     rcx, [rsp+98h+var_28]
0x18003a6cd  xor     rcx, rsp; StackCookie
0x18003a6d0  call    __security_check_cookie
0x18003a6d5  lea     r11, [rsp+98h+var_18]
0x18003a6dd  mov     rbx, [r11+30h]
0x18003a6e1  mov     rbp, [r11+38h]
0x18003a6e5  mov     rsp, r11
0x18003a6e8  pop     r14
0x18003a6ea  pop     rdi
0x18003a6eb  pop     rsi
0x18003a6ec  retn
0x18003a6ed  mov     rax, [rsi]
0x18003a6f0  mov     qword ptr [rsi], 0
0x18003a6f7  test    rax, rax
0x18003a6fa  jz      short loc_18003A773
0x18003a6fc  lea     rdx, [rsp+98h+var_78]
0x18003a701  mov     [rsp+98h+var_78], rax
0x18003a706  lea     rcx, [rsp+98h+var_68]
0x18003a70b  mov     [rsp+98h+var_30], 0
0x18003a714  call    std___Func_impl_no_alloc__Microsoft__WRL2__ContextSession__EnqueueReleaseAndPassOwnershipWorker____5____lambda_1__void____Func_impl_no_alloc__Microsoft__WRL2__ContextSession__EnqueueReleaseAndPassOwnershipWorker____5____lambda_1__void___Microsoft__WRL2__ContextSession__EnqueueReleaseAndPassOwnershipWorker____5____lambda_1__0_
0x18003a719  mov     [rsp+98h+var_30], rax
0x18003a71e  mov     rax, [r14+80h]
0x18003a725  cmp     rax, [r14+88h]
0x18003a72c  jnz     short loc_18003A78D
0x18003a72e  lea     r8, [rsp+98h+var_68]
0x18003a733  mov     rdx, rax
0x18003a736  lea     rcx, [r14+78h]
0x18003a73a  call    ??$_Emplace_reallocate@V?$function@$$A6AXXZ@std@@@?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAPEAV?$function@$$A6AXXZ@1@QEAV21@$$QEAV21@@Z; std::vector<std::function<void (void)>>::_Emplace_reallocate<std::function<void (void)>>(std::function<void (void)> * const,std::function<void (void)> &&)
0x18003a73f  mov     rcx, [rsp+98h+var_30]
0x18003a744  test    rcx, rcx
0x18003a747  jz      short loc_18003A769
0x18003a749  mov     rax, [rcx]
0x18003a74c  lea     rdx, [rsp+98h+var_68]
0x18003a751  cmp     rcx, rdx
0x18003a754  setnz   dl
0x18003a757  mov     rax, [rax+20h]
0x18003a75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a760  mov     [rsp+98h+var_30], 0
0x18003a769  lea     rcx, [rsp+98h+var_78]
0x18003a76e  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18003a773  mov     rax, [rdi]
0x18003a776  add     rsi, 8
0x18003a77a  jmp     loc_18003A68C
0x18003a77f  mov     rcx, rsi; SRWLock
0x18003a782  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a788  jmp     loc_18003A6B0
0x18003a78d  lea     rdx, [rsp+98h+var_68]
0x18003a792  mov     qword ptr [rax+38h], 0
0x18003a79a  mov     rcx, rax
0x18003a79d  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x18003a7a2  add     qword ptr [r14+80h], 40h ; '@'
0x18003a7aa  jmp     short loc_18003A73F
```
