# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800220e0`
- end: `0x180022288`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180045b50`

## callees

- `0x1800019c0`
- `0x18000266c`
- `0x180017c20`
- `0x180017d04`
- `0x18001d400`
- `0x1800204e8`
- `0x180021d9c`
- `0x1800220e0`
- `0x18002240c`
- `0x180022638`
- `0x180023844`
- `0x180025b0c`
- `0x18003e830`
- `0x180042374`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800221ff`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800221ff`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800221d4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800221d4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v1; // esi
  unsigned int v3; // edx
  signed __int32 v4; // ecx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-20h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-18h]
  unsigned int v12; // [rsp+80h] [rbp+28h] BYREF
  struct IUnknown *v13; // [rsp+88h] [rbp+30h] BYREF
  struct IRpcOptions *v14; // [rsp+90h] [rbp+38h] BYREF
  LPUNKNOWN pUnk; // [rsp+98h] [rbp+40h] BYREF

  v1 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagBroker_SetGeotagInBrokerWithPathAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagBroker_SetGeotagInBrokerWithPathAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>>(
                &v9,
                &pUnk) >= 0 )
    {
      v4 = *(_DWORD *)(a1 + 56);
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, v4, -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( *(_QWORD *)(a1 + 120) )
      {
        if ( (int)Microsoft::WRL::AgileRef::CopyTo(
                    (Microsoft::WRL::AgileRef *)(a1 + 120),
                    &GUID_4b5f2f60_19b1_5566_9df6_92a42235cbf9,
                    &v13) >= 0 )
        {
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagHelper_SetGeotagFromGeolocatorAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
          v14 = 0;
          Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v14);
          RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
          ppstm = 0;
          v11 = 0;
          if ( v14 && v13 )
          {
            v6 = pUnk;
            Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppstm);
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
          v1 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
                 v7,
                 v13,
                 *(_QWORD *)(a1 + 128));
          Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagHelper_SetGeotagAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
          AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>>(&ppstm);
          Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v14);
        }
      }
      else
      {
        v13 = 0;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v9);
  }
  return v1;
}

```

## disassembly

```asm
0x1800220e0  push    rbp
0x1800220e2  push    rbx
0x1800220e3  push    rsi
0x1800220e4  push    rdi
0x1800220e5  mov     rbp, rsp
0x1800220e8  sub     rsp, 58h
0x1800220ec  xor     esi, esi
0x1800220ee  mov     rbx, rcx
0x1800220f1  lea     edx, [rsi+1]
0x1800220f4  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?GeotagBroker_SetGeotagInBrokerWithPathAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagBroker_SetGeotagInBrokerWithPathAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800220f9  cmp     [rbx+88h], esi
0x1800220ff  jle     loc_18002227D
0x180022105  mov     eax, edx
0x180022107  lock xadd [rbx+10h], eax
0x18002210c  inc     eax
0x18002210e  cmp     eax, edx
0x180022110  jnz     loc_18002227D
0x180022116  lea     rcx, [rbp+var_28]
0x18002211a  mov     [rbp+var_28], rbx
0x18002211e  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180022123  mov     rcx, rbx
0x180022126  mov     [rbp+pUnk], rsi
0x18002212a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?GeotagBroker_SetGeotagInBrokerWithPathAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagBroker_SetGeotagInBrokerWithPathAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18002212f  lea     rdx, [rbp+pUnk]
0x180022133  lea     rcx, [rbp+var_28]
0x180022137  call    ??$As@U?$IAsyncOperation@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>>>)
0x18002213c  test    eax, eax
0x18002213e  js      loc_18002226B
0x180022144  mov     ecx, [rbx+38h]
0x180022147  mov     [rbp+arg_0], 0FFFFFFFEh
0x18002214e  mov     eax, [rbp+arg_0]
0x180022151  lock cmpxchg [rbp+arg_0], ecx
0x180022156  lea     rcx, [rbp+arg_8]
0x18002215a  mov     [rbp+arg_8], rsi
0x18002215e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022163  cmp     [rbx+78h], rsi
0x180022167  jz      loc_18002225E
0x18002216d  lea     r8, [rbp+arg_8]; struct IUnknown **
0x180022171  lea     rdx, _GUID_4b5f2f60_19b1_5566_9df6_92a42235cbf9; struct _GUID *
0x180022178  lea     rcx, [rbx+78h]; this
0x18002217c  call    ?CopyTo@AgileRef@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; Microsoft::WRL::AgileRef::CopyTo(_GUID const &,IUnknown * *)
0x180022181  test    eax, eax
0x180022183  js      loc_180022262
0x180022189  mov     rcx, rbx
0x18002218c  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?GeotagHelper_SetGeotagFromGeolocatorAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagHelper_SetGeotagFromGeolocatorAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180022191  lea     rcx, [rbp+arg_10]
0x180022195  mov     [rbp+arg_10], rsi
0x180022199  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18002219e  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x1800221a2  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x1800221a6  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800221ab  mov     [rbp+ppstm], rsi
0x1800221af  mov     [rbp+var_18], esi
0x1800221b2  cmp     [rbp+arg_10], rsi
0x1800221b6  jz      short loc_18002220A
0x1800221b8  cmp     [rbp+arg_8], rsi
0x1800221bc  jz      short loc_18002220A
0x1800221be  mov     rdi, [rbp+pUnk]
0x1800221c2  lea     rcx, [rbp+ppstm]
0x1800221c6  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800221cb  lea     r8, [rbp+ppstm]; ppstm
0x1800221cf  xor     ecx, ecx; hGlobal
0x1800221d1  lea     edx, [rsi+1]; fDeleteOnRelease
0x1800221d4  call    cs:__imp_CreateStreamOnHGlobal
0x1800221da  mov     [rbp+var_18], eax
0x1800221dd  test    eax, eax
0x1800221df  js      short loc_180022211
0x1800221e1  mov     rcx, [rbp+ppstm]; pStm
0x1800221e5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800221ec  mov     [rsp+58h+mshlflags], 1; mshlflags
0x1800221f4  xor     r9d, r9d; dwDestContext
0x1800221f7  mov     r8, rdi; pUnk
0x1800221fa  mov     [rsp+58h+pvDestContext], rsi; pvDestContext
0x1800221ff  call    cs:__imp_CoMarshalInterface
0x180022205  mov     [rbp+var_18], eax
0x180022208  jmp     short loc_180022211
0x18002220a  mov     [rbp+var_18], 80004002h
0x180022211  mov     rcx, [rbp+arg_8]
0x180022215  mov     r8d, [rbp+arg_0]
0x180022219  mov     rdx, [rbp+pUnk]
0x18002221d  mov     rax, [rcx]
0x180022220  mov     rax, [rax+18h]
0x180022224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022229  mov     r8, [rbx+80h]
0x180022230  mov     ecx, eax
0x180022232  mov     rdx, [rbp+arg_8]
0x180022236  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002223b  mov     rcx, rbx
0x18002223e  mov     esi, eax
0x180022240  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x180022245  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?GeotagHelper_SetGeotagAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagHelper_SetGeotagAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18002224a  lea     rcx, [rbp+ppstm]
0x18002224e  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>>(void)
0x180022253  lea     rcx, [rbp+arg_10]
0x180022257  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18002225c  jmp     short loc_180022262
0x18002225e  mov     [rbp+arg_8], rsi
0x180022262  lea     rcx, [rbp+arg_8]
0x180022266  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002226b  lea     rcx, [rbp+pUnk]
0x18002226f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022274  lea     rcx, [rbp+var_28]
0x180022278  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18002227d  mov     eax, esi
0x18002227f  add     rsp, 58h
0x180022283  pop     rdi
0x180022284  pop     rsi
0x180022285  pop     rbx
0x180022286  pop     rbp
0x180022287  retn
```
