# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagHelper_SetGeotagFromGeolocatorAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x180045bc0`
- end: `0x180045d76`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?GeotagHelper_SetGeotagFromGeolocatorAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b820`

## callees

- `0x1800019c0`
- `0x18000266c`
- `0x180015bc0`
- `0x180017c20`
- `0x180017d04`
- `0x18001f16c`
- `0x1800204e8`
- `0x1800238ac`
- `0x18003e880`
- `0x180042374`
- `0x180045bc0`
- `0x18004c0bc`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180045cd3`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180045cd3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180045ca7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180045ca7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagHelper_SetGeotagFromGeolocatorAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v4; // edi
  void (__fastcall *v5)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int); // rax
  bool v6; // dl
  IUnknown *v7; // rdi
  unsigned int v8; // eax
  __int64 v10; // [rsp+40h] [rbp-30h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-28h] BYREF
  HRESULT v12; // [rsp+50h] [rbp-20h]
  GUID v13; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v14; // [rsp+A0h] [rbp+30h] BYREF
  struct IRpcOptions *v15; // [rsp+B0h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+B8h] [rbp+48h] BYREF

  v10 = a1;
  v4 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v10);
  pUnk = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagHelper_SetGeotagFromGeolocatorAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1)
    && (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<IUnknown>(&v10, &pUnk) >= 0 )
  {
    v14 = 0;
    if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal<Windows::Internal::INilDelegate>(
                (Microsoft::WRL::AgileRef *)(a1 + 144),
                &v14) >= 0 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        v5 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL);
        v13 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        v5(Microsoft::WRL::gCausality, 1, 2, &v13, a1, 1);
      }
      v15 = 0;
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v15);
      RpcOptionsHelper::GetRpcOptions(v14, v6, &v15);
      ppstm = 0;
      v12 = 0;
      if ( v15 && v14 )
      {
        v7 = pUnk;
        Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppstm);
        v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( v12 >= 0 )
          v12 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
      }
      else
      {
        v12 = -2147467262;
      }
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v14->lpVtbl[1].QueryInterface)(v14, pUnk, a2);
      v4 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
             v8,
             v14,
             *(_QWORD *)(a1 + 152));
      if ( Microsoft::WRL::gCausality )
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          1);
      AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>>(&ppstm);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v15);
    }
    Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagBroker_SetGeotagInBrokerWithPathAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v10);
  return v4;
}

```

## disassembly

```asm
0x180045bc0  push    rbp
0x180045bc2  push    rbx
0x180045bc3  push    rsi
0x180045bc4  push    rdi
0x180045bc5  push    r15
0x180045bc7  mov     rbp, rsp
0x180045bca  sub     rsp, 70h
0x180045bce  mov     rbx, rcx
0x180045bd1  mov     [rbp+var_30], rcx
0x180045bd5  lea     rcx, [rbp+var_30]
0x180045bd9  mov     esi, edx
0x180045bdb  xor     edi, edi
0x180045bdd  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180045be2  mov     rcx, rbx
0x180045be5  mov     [rbp+pUnk], rdi
0x180045be9  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?GeotagHelper_SetGeotagFromGeolocatorAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagHelper_SetGeotagFromGeolocatorAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x180045bee  test    al, al
0x180045bf0  jz      loc_180045D57
0x180045bf6  lea     rdx, [rbp+pUnk]
0x180045bfa  lea     rcx, [rbp+var_30]
0x180045bfe  call    ??$As@UIUnknown@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x180045c03  test    eax, eax
0x180045c05  js      loc_180045D57
0x180045c0b  lea     rcx, [rbx+90h]; this
0x180045c12  mov     [rbp+arg_0], rdi
0x180045c16  lea     rdx, [rbp+arg_0]; struct IUnknown **
0x180045c1a  call    ??$CopyLocal@UINilDelegate@Internal@Windows@@@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UINilDelegate@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal<Windows::Internal::INilDelegate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::INilDelegate>>)
0x180045c1f  test    eax, eax
0x180045c21  js      loc_180045D46
0x180045c27  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180045c2e  lea     r15d, [rdi+1]
0x180045c32  test    rcx, rcx
0x180045c35  jz      short loc_180045C64
0x180045c37  mov     rax, [rcx]
0x180045c3a  lea     r9, [rbp+var_10]
0x180045c3e  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180045c45  mov     [rsp+70h+mshlflags], r15d
0x180045c4a  lea     r8d, [rdi+2]
0x180045c4e  mov     edx, r15d
0x180045c51  mov     [rsp+70h+pvDestContext], rbx
0x180045c56  mov     rax, [rax+48h]
0x180045c5a  movdqu  [rbp+var_10], xmm0
0x180045c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c64  lea     rcx, [rbp+arg_10]
0x180045c68  mov     [rbp+arg_10], rdi
0x180045c6c  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180045c71  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180045c75  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180045c79  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180045c7e  mov     [rbp+ppstm], rdi
0x180045c82  mov     [rbp+var_20], edi
0x180045c85  cmp     [rbp+arg_10], rdi
0x180045c89  jz      short loc_180045CDE
0x180045c8b  cmp     [rbp+arg_0], rdi
0x180045c8f  jz      short loc_180045CDE
0x180045c91  mov     rdi, [rbp+pUnk]
0x180045c95  lea     rcx, [rbp+ppstm]
0x180045c99  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180045c9e  lea     r8, [rbp+ppstm]; ppstm
0x180045ca2  mov     edx, r15d; fDeleteOnRelease
0x180045ca5  xor     ecx, ecx; hGlobal
0x180045ca7  call    cs:__imp_CreateStreamOnHGlobal
0x180045cad  mov     [rbp+var_20], eax
0x180045cb0  test    eax, eax
0x180045cb2  js      short loc_180045CE5
0x180045cb4  mov     rcx, [rbp+ppstm]; pStm
0x180045cb8  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180045cbf  mov     [rsp+70h+mshlflags], r15d; mshlflags
0x180045cc4  xor     r9d, r9d; dwDestContext
0x180045cc7  mov     r8, rdi; pUnk
0x180045cca  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x180045cd3  call    cs:__imp_CoMarshalInterface
0x180045cd9  mov     [rbp+var_20], eax
0x180045cdc  jmp     short loc_180045CE5
0x180045cde  mov     [rbp+var_20], 80004002h
0x180045ce5  mov     rcx, [rbp+arg_0]
0x180045ce9  mov     r8d, esi
0x180045cec  mov     rdx, [rbp+pUnk]
0x180045cf0  mov     rax, [rcx]
0x180045cf3  mov     rax, [rax+18h]
0x180045cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cfc  mov     r8, [rbx+98h]
0x180045d03  mov     ecx, eax
0x180045d05  mov     rdx, [rbp+arg_0]
0x180045d09  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180045d0e  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180045d15  mov     edi, eax
0x180045d17  test    rcx, rcx
0x180045d1a  jz      short loc_180045D34
0x180045d1c  mov     r9, [rcx]
0x180045d1f  mov     r8d, 2
0x180045d25  mov     edx, r15d
0x180045d28  mov     rax, [r9+50h]
0x180045d2c  mov     r9d, r15d
0x180045d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d34  lea     rcx, [rbp+ppstm]
0x180045d38  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>>(void)
0x180045d3d  lea     rcx, [rbp+arg_10]
0x180045d41  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180045d46  mov     rcx, rbx
0x180045d49  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?GeotagBroker_SetGeotagInBrokerWithPathAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagBroker_SetGeotagInBrokerWithPathAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180045d4e  lea     rcx, [rbp+arg_0]
0x180045d52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045d57  lea     rcx, [rbp+pUnk]
0x180045d5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045d60  lea     rcx, [rbp+var_30]
0x180045d64  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180045d69  mov     eax, edi
0x180045d6b  add     rsp, 70h
0x180045d6f  pop     r15
0x180045d71  pop     rdi
0x180045d72  pop     rsi
0x180045d73  pop     rbx
0x180045d74  pop     rbp
0x180045d75  retn
```
