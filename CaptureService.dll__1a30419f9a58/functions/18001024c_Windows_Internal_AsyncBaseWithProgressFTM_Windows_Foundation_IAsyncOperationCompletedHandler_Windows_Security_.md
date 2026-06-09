# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x18001024c`
- end: `0x1800103c0`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014cd0`

## callees

- `0x180007630`
- `0x18000bc00`
- `0x18000bf00`
- `0x18000dafc`
- `0x18000f6e8`
- `0x180010170`
- `0x18001024c`
- `0x180011928`
- `0x1800122c0`
- `0x1800174f4`
- `0x180017844`
- `0x180022010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v4; // edi
  bool v5; // dl
  unsigned int v6; // eax
  __int64 (__fastcall ***v8[2])(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-30h] BYREF
  GUID v9; // [rsp+50h] [rbp-20h] BYREF
  LPSTREAM ppstm[2]; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v11; // [rsp+90h] [rbp+20h] BYREF
  struct IRpcOptions *v12; // [rsp+A0h] [rbp+30h] BYREF
  IUnknown *v13; // [rsp+A8h] [rbp+38h] BYREF

  v4 = 0;
  v8[0] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(v8);
  v13 = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1)
    && (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<IUnknown>(v8, (__int64)&v13) >= 0 )
  {
    v11 = 0;
    if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal<Windows::Internal::INilDelegate>(
                a1 + 144,
                (__int64)&v11) >= 0 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        v9 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          &v9,
          a1,
          1);
      }
      v12 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v12);
      RpcOptionsHelper::GetRpcOptions(v11, v5, &v12);
      BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(ppstm, (__int64)v12, v13, (__int64)v11);
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, IUnknown *, _QWORD))v11->lpVtbl[1].QueryInterface)(v11, v13, a2);
      v4 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
             v6,
             v11,
             *(_QWORD *)(a1 + 152));
      if ( Microsoft::WRL::gCausality )
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          1);
      AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>((int *)ppstm);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v12);
    }
    Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)v8);
  return v4;
}

```

## disassembly

```asm
0x18001024c  mov     [rsp-18h+arg_8], rbx
0x180010251  push    rbp
0x180010252  push    rsi
0x180010253  push    rdi
0x180010254  mov     rbp, rsp
0x180010257  sub     rsp, 70h
0x18001025b  mov     esi, edx
0x18001025d  mov     rbx, rcx
0x180010260  xor     edi, edi
0x180010262  mov     [rbp+var_30], rcx
0x180010266  lea     rcx, [rbp+var_30]
0x18001026a  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18001026f  nop
0x180010270  mov     [rbp+arg_18], rdi
0x180010274  mov     rcx, rbx
0x180010277  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x18001027c  test    al, al
0x18001027e  jz      loc_18001039B
0x180010284  lea     rdx, [rbp+arg_18]
0x180010288  lea     rcx, [rbp+var_30]
0x18001028c  call    ??$As@UIUnknown@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x180010291  test    eax, eax
0x180010293  js      loc_18001039B
0x180010299  mov     [rbp+arg_0], rdi
0x18001029d  lea     rcx, [rbx+90h]
0x1800102a4  lea     rdx, [rbp+arg_0]
0x1800102a8  call    ??$CopyLocal@UINilDelegate@Internal@Windows@@@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UINilDelegate@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal<Windows::Internal::INilDelegate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::INilDelegate>>)
0x1800102ad  test    eax, eax
0x1800102af  js      loc_180010388
0x1800102b5  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800102bc  test    rcx, rcx
0x1800102bf  jz      short loc_1800102F1
0x1800102c1  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800102c8  movdqu  [rbp+var_20], xmm0
0x1800102cd  mov     rax, [rcx]
0x1800102d0  mov     [rsp+70h+var_48], 1
0x1800102d8  mov     [rsp+70h+var_50], rbx
0x1800102dd  lea     r9, [rbp+var_20]
0x1800102e1  lea     edx, [rdi+1]
0x1800102e4  lea     r8d, [rdi+2]
0x1800102e8  mov     rax, [rax+48h]
0x1800102ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102f1  mov     [rbp+arg_10], 0
0x1800102f9  lea     rcx, [rbp+arg_10]
0x1800102fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010302  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180010306  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18001030a  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18001030f  mov     r9, [rbp+arg_0]
0x180010313  mov     r8, [rbp+arg_18]
0x180010317  mov     rdx, [rbp+arg_10]
0x18001031b  lea     rcx, [rbp+ppstm]; ppstm
0x18001031f  call    ?CreateBias@?$BiasHelper@UIUnknown@@UINilDelegate@Internal@Windows@@$00@@SA?AV?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@PEAUIRpcOptions@@PEAUIUnknown@@PEAUINilDelegate@Internal@Windows@@@Z; BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(IRpcOptions *,IUnknown *,Windows::Internal::INilDelegate *)
0x180010324  nop
0x180010325  mov     rcx, [rbp+arg_0]
0x180010329  mov     rax, [rcx]
0x18001032c  mov     r8d, esi
0x18001032f  mov     rdx, [rbp+arg_18]
0x180010333  mov     rax, [rax+18h]
0x180010337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001033c  mov     r8, [rbx+98h]
0x180010343  mov     rdx, [rbp+arg_0]
0x180010347  mov     ecx, eax
0x180010349  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18001034e  mov     edi, eax
0x180010350  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180010357  test    rcx, rcx
0x18001035a  jz      short loc_180010375
0x18001035c  mov     r9, [rcx]
0x18001035f  mov     rax, [r9+50h]
0x180010363  mov     edx, 1
0x180010368  mov     r9d, edx
0x18001036b  lea     r8d, [rdx+1]
0x18001036f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010374  nop
0x180010375  lea     rcx, [rbp+ppstm]
0x180010379  call    ??1?$AutoStubBias@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(void)
0x18001037e  nop
0x18001037f  lea     rcx, [rbp+arg_10]
0x180010383  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010388  mov     rcx, rbx
0x18001038b  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180010390  nop
0x180010391  lea     rcx, [rbp+arg_0]
0x180010395  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001039a  nop
0x18001039b  lea     rcx, [rbp+arg_18]
0x18001039f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800103a4  nop
0x1800103a5  lea     rcx, [rbp+var_30]
0x1800103a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800103ae  mov     eax, edi
0x1800103b0  mov     rbx, [rsp+70h+arg_8]
0x1800103b8  add     rsp, 70h
0x1800103bc  pop     rdi
0x1800103bd  pop     rsi
0x1800103be  pop     rbp
0x1800103bf  retn
```
