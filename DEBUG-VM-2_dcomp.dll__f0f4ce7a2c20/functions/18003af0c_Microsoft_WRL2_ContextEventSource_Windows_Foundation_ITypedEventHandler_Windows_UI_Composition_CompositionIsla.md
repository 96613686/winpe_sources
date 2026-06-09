# Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::CompositionIsland *,Windows::UI::Composition::CompositionIslandAutomationProviderRequestedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy(Microsoft::WRL2::ContextSession *)

- ea: `0x18003af0c`
- end: `0x18003b099`
- name: `?Destroy@?$ContextEventSource@U?$ITypedEventHandler@PEAVCompositionIsland@Composition@UI@Windows@@PEAVCompositionIslandAutomationProviderRequestedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL2@Microsoft@@QEAAXPEAVContextSession@23@@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ac640`

## callees

- `0x1800093f4`
- `0x18003a598`
- `0x18003af0c`
- `0x18003b0a0`
- `0x18003b144`
- `0x18003b178`
- `0x1800a0fb8`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003af7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b038`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003af7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b038`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b05a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b06c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b05a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b06c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003af3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003af3d`

## pseudocode

```c
void __fastcall Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::CompositionIsland *,Windows::UI::Composition::CompositionIslandAutomationProviderRequestedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy(
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
      if ( a1->Ptr )
      {
        a1->Ptr = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
      }
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
0x18003af0c  mov     [rsp+arg_10], rbx
0x18003af11  mov     [rsp+arg_18], rbp
0x18003af16  push    rsi
0x18003af17  push    rdi
0x18003af18  push    r14
0x18003af1a  sub     rsp, 80h
0x18003af21  mov     rax, cs:__security_cookie
0x18003af28  xor     rax, rsp
0x18003af2b  mov     [rsp+98h+var_28], rax
0x18003af30  mov     rax, [rdx+38h]
0x18003af34  mov     r14, rdx
0x18003af37  mov     rdi, rcx
0x18003af3a  mov     ebx, [rax+28h]
0x18003af3d  call    cs:__imp_GetCurrentThreadId
0x18003af43  cmp     ebx, eax
0x18003af45  jz      short loc_18003AF74
0x18003af47  mov     rcx, rdi
0x18003af4a  call    ?Destroy_NoLock@?$ContextEventSource@U?$ITypedEventHandler@PEAVCompositorController@Core@Composition@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy_NoLock(void)
0x18003af4f  mov     rcx, [rsp+98h+var_28]
0x18003af54  xor     rcx, rsp; StackCookie
0x18003af57  call    __security_check_cookie
0x18003af5c  lea     r11, [rsp+98h+var_18]
0x18003af64  mov     rbx, [r11+30h]
0x18003af68  mov     rbp, [r11+38h]
0x18003af6c  mov     rsp, r11
0x18003af6f  pop     r14
0x18003af71  pop     rdi
0x18003af72  pop     rsi
0x18003af73  retn
0x18003af74  lea     rbx, [rdi+10h]
0x18003af78  mov     rcx, rbx; SRWLock
0x18003af7b  call    cs:__imp_AcquireSRWLockExclusive
0x18003af81  mov     rax, [rdi]
0x18003af84  test    rax, rax
0x18003af87  jz      loc_18003B060
0x18003af8d  mov     rsi, [rax+10h]
0x18003af91  jmp     loc_18003B027
0x18003af96  mov     rax, [rsi]
0x18003af99  mov     qword ptr [rsi], 0
0x18003afa0  test    rax, rax
0x18003afa3  jz      short loc_18003B020
0x18003afa5  lea     rdx, [rsp+98h+var_78]
0x18003afaa  mov     [rsp+98h+var_78], rax
0x18003afaf  lea     rcx, [rsp+98h+var_68]
0x18003afb4  mov     [rsp+98h+var_30], 0
0x18003afbd  call    std___Func_impl_no_alloc__Microsoft__WRL2__ContextSession__EnqueueReleaseAndPassOwnershipWorker____5____lambda_1__void____Func_impl_no_alloc__Microsoft__WRL2__ContextSession__EnqueueReleaseAndPassOwnershipWorker____5____lambda_1__void___Microsoft__WRL2__ContextSession__EnqueueReleaseAndPassOwnershipWorker____5____lambda_1__0_
0x18003afc2  mov     [rsp+98h+var_30], rax
0x18003afc7  mov     rax, [r14+80h]
0x18003afce  cmp     rax, [r14+88h]
0x18003afd5  jnz     loc_18003B077
0x18003afdb  lea     r8, [rsp+98h+var_68]
0x18003afe0  mov     rdx, rax
0x18003afe3  lea     rcx, [r14+78h]
0x18003afe7  call    ??$_Emplace_reallocate@V?$function@$$A6AXXZ@std@@@?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAPEAV?$function@$$A6AXXZ@1@QEAV21@$$QEAV21@@Z; std::vector<std::function<void (void)>>::_Emplace_reallocate<std::function<void (void)>>(std::function<void (void)> * const,std::function<void (void)> &&)
0x18003afec  mov     rcx, [rsp+98h+var_30]
0x18003aff1  test    rcx, rcx
0x18003aff4  jz      short loc_18003B016
0x18003aff6  mov     rax, [rcx]
0x18003aff9  lea     rdx, [rsp+98h+var_68]
0x18003affe  cmp     rcx, rdx
0x18003b001  setnz   dl
0x18003b004  mov     rax, [rax+20h]
0x18003b008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b00d  mov     [rsp+98h+var_30], 0
0x18003b016  lea     rcx, [rsp+98h+var_78]
0x18003b01b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18003b020  mov     rax, [rdi]
0x18003b023  add     rsi, 8
0x18003b027  cmp     rsi, [rax+18h]
0x18003b02b  jnz     loc_18003AF96
0x18003b031  lea     rsi, [rdi+8]
0x18003b035  mov     rcx, rsi; SRWLock
0x18003b038  call    cs:__imp_AcquireSRWLockExclusive
0x18003b03e  mov     rcx, [rdi]
0x18003b041  test    rcx, rcx
0x18003b044  jz      short loc_18003B052
0x18003b046  mov     qword ptr [rdi], 0
0x18003b04d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18003b052  test    rsi, rsi
0x18003b055  jz      short loc_18003B060
0x18003b057  mov     rcx, rsi; SRWLock
0x18003b05a  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b060  test    rbx, rbx
0x18003b063  jz      loc_18003AF4F
0x18003b069  mov     rcx, rbx; SRWLock
0x18003b06c  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b072  jmp     loc_18003AF4F
0x18003b077  lea     rdx, [rsp+98h+var_68]
0x18003b07c  mov     qword ptr [rax+38h], 0
0x18003b084  mov     rcx, rax
0x18003b087  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x18003b08c  add     qword ptr [r14+80h], 40h ; '@'
0x18003b094  jmp     loc_18003AFEC
```
