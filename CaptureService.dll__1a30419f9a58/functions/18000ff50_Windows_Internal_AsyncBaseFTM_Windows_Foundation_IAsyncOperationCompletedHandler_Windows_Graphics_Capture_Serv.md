# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18000ff50`
- end: `0x1800100eb`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010100`

## callees

- `0x180007630`
- `0x18000bbb0`
- `0x18000dafc`
- `0x18000f618`
- `0x18000ff50`
- `0x180010170`
- `0x180011928`
- `0x1800122c0`
- `0x180015aac`
- `0x180015adc`
- `0x180015b80`
- `0x180015ca4`
- `0x1800177f8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180010064`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180010064`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180010035`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180010035`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(a1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>>(
                &v9,
                (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v11 >= 0 )
            v11 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
        }
        else
        {
          v11 = -2147467262;
        }
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v13->lpVtbl[1].QueryInterface)(
               v13,
               pUnk,
               v12);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v7,
               v13,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>((int *)&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ff50  push    rbp
0x18000ff52  push    rbx
0x18000ff53  push    rdi
0x18000ff54  mov     rbp, rsp
0x18000ff57  sub     rsp, 50h
0x18000ff5b  mov     rbx, rcx
0x18000ff5e  xor     edi, edi
0x18000ff60  lea     edx, [rdi+1]
0x18000ff63  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18000ff68  cmp     [rbx+88h], edi
0x18000ff6e  jle     loc_1800100E1
0x18000ff74  mov     eax, edx
0x18000ff76  lock xadd [rbx+10h], eax
0x18000ff7b  inc     eax
0x18000ff7d  cmp     eax, edx
0x18000ff7f  jnz     loc_1800100E1
0x18000ff85  mov     [rbp+var_20], rbx
0x18000ff89  lea     rcx, [rbp+var_20]
0x18000ff8d  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18000ff92  nop
0x18000ff93  mov     [rbp+pUnk], rdi
0x18000ff97  mov     rcx, rbx
0x18000ff9a  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18000ff9f  lea     rdx, [rbp+pUnk]
0x18000ffa3  lea     rcx, [rbp+var_20]
0x18000ffa7  call    ??$As@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>>>)
0x18000ffac  test    eax, eax
0x18000ffae  js      loc_1800100CE
0x18000ffb4  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000ffbb  mov     ecx, [rbx+38h]
0x18000ffbe  mov     eax, [rbp+arg_0]
0x18000ffc1  lock cmpxchg [rbp+arg_0], ecx
0x18000ffc6  mov     [rbp+arg_8], rdi
0x18000ffca  lea     rcx, [rbp+arg_8]
0x18000ffce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ffd3  lea     rcx, [rbx+78h]
0x18000ffd7  lea     r8, [rbp+arg_8]
0x18000ffdb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>>::CopyLocal(_GUID const &,void * *)
0x18000ffe0  test    eax, eax
0x18000ffe2  js      loc_1800100C4
0x18000ffe8  mov     rcx, rbx
0x18000ffeb  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18000fff0  mov     [rbp+arg_10], rdi
0x18000fff4  lea     rcx, [rbp+arg_10]
0x18000fff8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fffd  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180010001  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180010005  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18001000a  mov     [rbp+ppstm], rdi
0x18001000e  mov     [rbp+var_10], edi
0x180010011  cmp     [rbp+arg_10], rdi
0x180010015  jz      short loc_18001006F
0x180010017  cmp     [rbp+arg_8], rdi
0x18001001b  jz      short loc_18001006F
0x18001001d  mov     rdi, [rbp+pUnk]
0x180010021  lea     rcx, [rbp+ppstm]
0x180010025  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001002a  lea     r8, [rbp+ppstm]; ppstm
0x18001002e  mov     edx, 1; fDeleteOnRelease
0x180010033  xor     ecx, ecx; hGlobal
0x180010035  call    cs:__imp_CreateStreamOnHGlobal
0x18001003b  mov     [rbp+var_10], eax
0x18001003e  test    eax, eax
0x180010040  js      short loc_180010076
0x180010042  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18001004a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180010053  xor     r9d, r9d; dwDestContext
0x180010056  mov     r8, rdi; pUnk
0x180010059  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180010060  mov     rcx, [rbp+ppstm]; pStm
0x180010064  call    cs:__imp_CoMarshalInterface
0x18001006a  mov     [rbp+var_10], eax
0x18001006d  jmp     short loc_180010076
0x18001006f  mov     [rbp+var_10], 80004002h
0x180010076  mov     rcx, [rbp+arg_8]
0x18001007a  mov     rax, [rcx]
0x18001007d  mov     r8d, [rbp+arg_0]
0x180010081  mov     rdx, [rbp+pUnk]
0x180010085  mov     rax, [rax+18h]
0x180010089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001008e  mov     r8, [rbx+80h]
0x180010095  mov     rdx, [rbp+arg_8]
0x180010099  mov     ecx, eax
0x18001009b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800100a0  mov     edi, eax
0x1800100a2  mov     rcx, rbx
0x1800100a5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800100aa  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800100af  nop
0x1800100b0  lea     rcx, [rbp+ppstm]
0x1800100b4  call    ??1?$AutoStubBias@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(void)
0x1800100b9  nop
0x1800100ba  lea     rcx, [rbp+arg_10]
0x1800100be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800100c3  nop
0x1800100c4  lea     rcx, [rbp+arg_8]
0x1800100c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800100cd  nop
0x1800100ce  lea     rcx, [rbp+pUnk]
0x1800100d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800100d7  nop
0x1800100d8  lea     rcx, [rbp+var_20]
0x1800100dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800100e1  mov     eax, edi
0x1800100e3  add     rsp, 50h
0x1800100e7  pop     rdi
0x1800100e8  pop     rbx
0x1800100e9  pop     rbp
0x1800100ea  retn
```
