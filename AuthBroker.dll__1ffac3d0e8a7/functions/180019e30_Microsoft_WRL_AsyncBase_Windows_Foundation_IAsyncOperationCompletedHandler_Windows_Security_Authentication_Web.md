# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *> *)

- ea: `0x180019e30`
- end: `0x180019efb`
- name: `?PutOnComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAU?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z`
- size: `203`
- prototype: `HRESULT __fastcall(Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this, Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *> *completeHandler)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bd50`

## callees

- `0x180006060`
- `0x180018050`
- `0x180018fe4`
- `0x180019e30`
- `0x18001b5e8`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180019eea`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180019eea`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this,
        Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *> *completeHandler)
{
  int v4; // esi
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  signed __int32 v7[18]; // [rsp+0h] [rbp-48h] BYREF
  Microsoft::WRL::ComPtr<IAsyncInfo> v8; // [rsp+60h] [rbp+18h] BYREF

  v4 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(this);
  if ( v4 >= 0 )
  {
    if ( _InterlockedCompareExchange(&this->cCompleteDelegateAssigned_, 1, 0) )
    {
      v4 = -2147483624;
      RoOriginateError(2147483672LL, 0);
    }
    else
    {
      if ( completeHandler )
        this->completeDelegateBucketAssist_ = completeHandler->Invoke;
      if ( this->completeDelegate_.ptr_ != completeHandler )
      {
        v8.ptr_ = (IAsyncInfo *)completeHandler;
        Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v8);
        v8.ptr_ = (IAsyncInfo *)this->completeDelegate_.ptr_;
        this->completeDelegate_.ptr_ = completeHandler;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&v8);
      }
      _InterlockedOr(v7, 0);
      _InterlockedAdd(&this->cCompleteDelegateRefCount_, 1u);
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(this);
      currentStatus = this->currentStatus_;
      LODWORD(v8.ptr_) = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v8, currentStatus, -2);
      if ( (unsigned int)(LODWORD(v8.ptr_) - 1) <= 3 )
        this->FireCompletion(this);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019e30  push    rbx
0x180019e32  push    rbp
0x180019e33  push    rsi
0x180019e34  push    rdi
0x180019e35  sub     rsp, 28h
0x180019e39  mov     rdi, completeHandler
0x180019e3c  mov     rbx, this
0x180019e3f  call    ?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)
0x180019e44  mov     esi, eax
0x180019e46  test    eax, eax
0x180019e48  js      loc_180019EF0
0x180019e4e  mov     ebp, 1
0x180019e53  xor     eax, eax
0x180019e55  lock cmpxchg [rbx+14h], ebp
0x180019e5a  jnz     loc_180019EE1
0x180019e60  test    rdi, rdi
0x180019e63  jz      short loc_180019E70
0x180019e65  mov     rax, [rdi]
0x180019e68  mov     this, [rax+18h]
0x180019e6c  mov     [rbx+28h], this
0x180019e70  cmp     [rbx+18h], rdi
0x180019e74  jz      short loc_180019E9C
0x180019e76  lea     this, [rsp+48h+arg_10]; this
0x180019e7b  mov     [rsp+48h+arg_10.ptr_], rdi
0x180019e80  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x180019e85  mov     rax, [rbx+18h]
0x180019e89  lea     this, [rsp+48h+arg_10]; this
0x180019e8e  mov     [rsp+48h+arg_10.ptr_], rax
0x180019e93  mov     [rbx+18h], rdi
0x180019e97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019e9c  lock or [rsp+48h+var_48], 0
0x180019ea1  lock add [rbx+20h], ebp
0x180019ea5  mov     this, rbx; this
0x180019ea8  call    ?TraceDelegateAssigned@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(void)
0x180019ead  mov     ecx, [rbx+38h]
0x180019eb0  mov     dword ptr [rsp+48h+arg_10.ptr_], 0FFFFFFFEh
0x180019eb8  mov     eax, dword ptr [rsp+48h+arg_10.ptr_]
0x180019ebc  lock cmpxchg dword ptr [rsp+48h+arg_10.ptr_], ecx
0x180019ec2  mov     ecx, dword ptr [rsp+48h+arg_10.ptr_]
0x180019ec6  dec     ecx
0x180019ec8  cmp     ecx, 3
0x180019ecb  ja      short loc_180019EF0
0x180019ecd  mov     rax, [rbx]
0x180019ed0  mov     this, rbx
0x180019ed3  mov     rax, [rax+80h]
0x180019eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019edf  jmp     short loc_180019EF0
0x180019ee1  mov     esi, 80000018h
0x180019ee6  xor     edx, edx
0x180019ee8  mov     ecx, esi
0x180019eea  call    cs:__imp_RoOriginateError
0x180019ef0  mov     eax, esi
0x180019ef2  add     rsp, 28h
0x180019ef6  pop     rdi
0x180019ef7  pop     rsi
0x180019ef8  pop     rbp
0x180019ef9  pop     rbx
0x180019efa  retn
```
