# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *> *)

- ea: `0x180013150`
- end: `0x18001321b`
- name: `?PutOnComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAU?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@@Z`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007630`
- `0x18000f48c`
- `0x1800122c0`
- `0x180013150`
- `0x180015b2c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001320a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001320a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  int v4; // esi
  signed __int32 v5; // ecx
  signed __int32 v7[18]; // [rsp+0h] [rbp-48h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  v4 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(a1);
  if ( v4 >= 0 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), 1, 0) )
    {
      v4 = -2147483624;
      RoOriginateError(2147483672LL, 0);
    }
    else
    {
      if ( a2 )
        *(_QWORD *)(a1 + 40) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      if ( *(_QWORD *)(a1 + 24) != a2 )
      {
        v8 = a2;
        Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v8);
        v8 = *(_QWORD *)(a1 + 24);
        *(_QWORD *)(a1 + 24) = a2;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
      }
      _InterlockedOr(v7, 0);
      _InterlockedAdd((volatile signed __int32 *)(a1 + 32), 1u);
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(a1);
      v5 = *(_DWORD *)(a1 + 56);
      LODWORD(v8) = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v8, v5, -2);
      if ( (unsigned int)(v8 - 1) <= 3 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013150  push    rbx
0x180013152  push    rbp
0x180013153  push    rsi
0x180013154  push    rdi
0x180013155  sub     rsp, 28h
0x180013159  mov     rdi, rdx
0x18001315c  mov     rbx, rcx
0x18001315f  call    ?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)
0x180013164  mov     esi, eax
0x180013166  test    eax, eax
0x180013168  js      loc_180013210
0x18001316e  mov     ebp, 1
0x180013173  xor     eax, eax
0x180013175  lock cmpxchg [rbx+14h], ebp
0x18001317a  jnz     loc_180013201
0x180013180  test    rdi, rdi
0x180013183  jz      short loc_180013190
0x180013185  mov     rax, [rdi]
0x180013188  mov     rcx, [rax+18h]
0x18001318c  mov     [rbx+28h], rcx
0x180013190  cmp     [rbx+18h], rdi
0x180013194  jz      short loc_1800131BC
0x180013196  lea     rcx, [rsp+48h+arg_10]
0x18001319b  mov     [rsp+48h+arg_10], rdi
0x1800131a0  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800131a5  mov     rax, [rbx+18h]
0x1800131a9  lea     rcx, [rsp+48h+arg_10]
0x1800131ae  mov     [rsp+48h+arg_10], rax
0x1800131b3  mov     [rbx+18h], rdi
0x1800131b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800131bc  lock or [rsp+48h+var_48], 0
0x1800131c1  lock add [rbx+20h], ebp
0x1800131c5  mov     rcx, rbx
0x1800131c8  call    ?TraceDelegateAssigned@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(void)
0x1800131cd  mov     ecx, [rbx+38h]
0x1800131d0  mov     dword ptr [rsp+48h+arg_10], 0FFFFFFFEh
0x1800131d8  mov     eax, dword ptr [rsp+48h+arg_10]
0x1800131dc  lock cmpxchg dword ptr [rsp+48h+arg_10], ecx
0x1800131e2  mov     ecx, dword ptr [rsp+48h+arg_10]
0x1800131e6  dec     ecx
0x1800131e8  cmp     ecx, 3
0x1800131eb  ja      short loc_180013210
0x1800131ed  mov     rax, [rbx]
0x1800131f0  mov     rcx, rbx
0x1800131f3  mov     rax, [rax+80h]
0x1800131fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ff  jmp     short loc_180013210
0x180013201  mov     esi, 80000018h
0x180013206  xor     edx, edx
0x180013208  mov     ecx, esi
0x18001320a  call    cs:__imp_RoOriginateError
0x180013210  mov     eax, esi
0x180013212  add     rsp, 28h
0x180013216  pop     rdi
0x180013217  pop     rsi
0x180013218  pop     rbp
0x180013219  pop     rbx
0x18001321a  retn
```
