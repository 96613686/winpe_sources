# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *> *)

- ea: `0x180013230`
- end: `0x18001334d`
- name: `?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@3@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018700`

## callees

- `0x180007630`
- `0x18000e264`
- `0x18000f48c`
- `0x180013230`
- `0x180015b2c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001329b`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001329b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  int AgileReference; // edi
  __int64 *v5; // rax
  __int64 *v6; // rdi
  signed __int32 v7; // ecx
  signed __int32 v9[10]; // [rsp+0h] [rbp-28h] BYREF
  __int64 *v10; // [rsp+40h] [rbp+18h] BYREF
  __int64 v11; // [rsp+48h] [rbp+20h] BYREF

  AgileReference = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(a1);
  if ( AgileReference >= 0 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 20)) != 1 )
      return (unsigned int)-2147483624;
    v10 = (__int64 *)(a1 + 120);
    v5 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v10);
    v6 = v5;
    if ( a2 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
      AgileReference = RoGetAgileReference(0, &GUID_98839cd8_27d9_5fa4_b00a_9e17c9d34f39, a2, v6);
      if ( AgileReference < 0 )
        return (unsigned int)AgileReference;
    }
    else
    {
      v10 = (__int64 *)*v5;
      v11 = 0;
      *v5 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v10);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      AgileReference = 0;
    }
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(a1);
    if ( a2 )
    {
      *(_QWORD *)(a1 + 128) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 136));
    }
    _InterlockedOr(v9, 0);
    v7 = *(_DWORD *)(a1 + 56);
    LODWORD(v10) = -2;
    _InterlockedCompareExchange((volatile signed __int32 *)&v10, v7, -2);
    if ( (unsigned int)((_DWORD)v10 - 1) <= 3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x180013230  mov     [rsp+arg_0], rbx
0x180013235  mov     [rsp+arg_8], rsi
0x18001323a  push    rdi
0x18001323b  sub     rsp, 20h
0x18001323f  mov     rsi, rdx
0x180013242  mov     rbx, rcx
0x180013245  call    ?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)
0x18001324a  mov     edi, eax
0x18001324c  test    eax, eax
0x18001324e  js      loc_18001333B
0x180013254  mov     eax, 1
0x180013259  lock xadd [rbx+14h], eax
0x18001325e  inc     eax
0x180013260  cmp     eax, 1
0x180013263  jnz     loc_180013336
0x180013269  lea     rax, [rbx+78h]
0x18001326d  lea     rcx, [rsp+28h+arg_10]
0x180013272  mov     [rsp+28h+arg_10], rax
0x180013277  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18001327c  mov     rdi, rax
0x18001327f  test    rsi, rsi
0x180013282  jz      short loc_1800132AD
0x180013284  mov     rcx, rax
0x180013287  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001328c  mov     r9, rdi
0x18001328f  lea     rdx, _GUID_98839cd8_27d9_5fa4_b00a_9e17c9d34f39
0x180013296  mov     r8, rsi
0x180013299  xor     ecx, ecx
0x18001329b  call    cs:__imp_RoGetAgileReference
0x1800132a1  mov     edi, eax
0x1800132a3  test    eax, eax
0x1800132a5  js      loc_18001333B
0x1800132ab  jmp     short loc_1800132DB
0x1800132ad  mov     rax, [rax]
0x1800132b0  lea     rcx, [rsp+28h+arg_10]
0x1800132b5  mov     [rsp+28h+arg_10], rax
0x1800132ba  mov     [rsp+28h+arg_18], 0
0x1800132c3  mov     qword ptr [rdi], 0
0x1800132ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800132cf  lea     rcx, [rsp+28h+arg_18]
0x1800132d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800132d9  xor     edi, edi
0x1800132db  mov     rcx, rbx
0x1800132de  call    ?TraceDelegateAssigned@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(void)
0x1800132e3  test    rsi, rsi
0x1800132e6  jz      short loc_1800132FD
0x1800132e8  mov     rax, [rsi]
0x1800132eb  mov     rcx, [rax+18h]
0x1800132ef  mov     [rbx+80h], rcx
0x1800132f6  lock inc dword ptr [rbx+88h]
0x1800132fd  lock or [rsp+28h+var_28], 0
0x180013302  mov     ecx, [rbx+38h]
0x180013305  mov     dword ptr [rsp+28h+arg_10], 0FFFFFFFEh
0x18001330d  mov     eax, dword ptr [rsp+28h+arg_10]
0x180013311  lock cmpxchg dword ptr [rsp+28h+arg_10], ecx
0x180013317  mov     ecx, dword ptr [rsp+28h+arg_10]
0x18001331b  dec     ecx
0x18001331d  cmp     ecx, 3
0x180013320  ja      short loc_18001333B
0x180013322  mov     rax, [rbx]
0x180013325  mov     rcx, rbx
0x180013328  mov     rax, [rax+80h]
0x18001332f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013334  jmp     short loc_18001333B
0x180013336  mov     edi, 80000018h
0x18001333b  mov     rbx, [rsp+28h+arg_0]
0x180013340  mov     eax, edi
0x180013342  mov     rsi, [rsp+28h+arg_8]
0x180013347  add     rsp, 20h
0x18001334b  pop     rdi
0x18001334c  retn
```
