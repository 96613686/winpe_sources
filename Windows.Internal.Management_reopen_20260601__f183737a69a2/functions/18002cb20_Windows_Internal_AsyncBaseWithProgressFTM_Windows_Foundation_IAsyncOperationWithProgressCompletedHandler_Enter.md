# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress)

- ea: `0x18002cb20`
- end: `0x18002cd11`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJUExpectedAndCurrentResourceProgress@Enrollment@EnterpriseDeviceManagement@@@Z`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034410`

## callees

- `0x180009be4`
- `0x180017944`
- `0x180017fc0`
- `0x1800180fc`
- `0x18001823c`
- `0x180019950`
- `0x180029f34`
- `0x18002cb20`
- `0x180037b48`
- `0x180037cfc`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002cc20`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002cc20`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002cc52`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002cc52`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rdi
  unsigned int v8; // eax
  _QWORD v10[2]; // [rsp+40h] [rbp-30h] BYREF
  GUID v11; // [rsp+50h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+60h] [rbp-10h] BYREF
  HRESULT v13; // [rsp+68h] [rbp-8h]
  struct IUnknown *v14; // [rsp+A0h] [rbp+30h] BYREF
  struct IRpcOptions *v15; // [rsp+B0h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+B8h] [rbp+48h] BYREF

  v4 = 0;
  v10[0] = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(v10);
  pUnk = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1)
    && (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>(
              v10,
              &pUnk) >= 0 )
  {
    v14 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>::CopyLocal(
                a1 + 144,
                v5,
                &v14) >= 0 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        v11 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          &v11,
          a1,
          1);
      }
      v15 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
      RpcOptionsHelper::GetRpcOptions(v14, v6, &v15);
      ppstm = 0;
      v13 = 0;
      if ( v15 && v14 )
      {
        v7 = pUnk;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
        v13 = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( v13 >= 0 )
          v13 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
      }
      else
      {
        v13 = -2147467262;
      }
      *(_QWORD *)&v11.Data1 = *(_QWORD *)a2;
      *(_DWORD *)v11.Data4 = *(_DWORD *)(a2 + 8);
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, GUID *))v14->lpVtbl[1].QueryInterface)(
             v14,
             pUnk,
             &v11);
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
      AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(&ppstm);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    }
    Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v10);
  return v4;
}

```

## disassembly

```asm
0x18002cb20  push    rbp
0x18002cb22  push    rbx
0x18002cb23  push    rsi
0x18002cb24  push    rdi
0x18002cb25  push    r15
0x18002cb27  mov     rbp, rsp
0x18002cb2a  sub     rsp, 70h
0x18002cb2e  mov     rsi, rdx
0x18002cb31  mov     rbx, rcx
0x18002cb34  xor     edi, edi
0x18002cb36  mov     [rbp+var_30], rcx
0x18002cb3a  lea     rcx, [rbp+var_30]
0x18002cb3e  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002cb43  nop
0x18002cb44  mov     [rbp+pUnk], rdi
0x18002cb48  mov     rcx, rbx
0x18002cb4b  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVReflectedEnrollmentResult@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x18002cb50  test    al, al
0x18002cb52  jz      loc_18002CCF0
0x18002cb58  lea     rdx, [rbp+pUnk]
0x18002cb5c  lea     rcx, [rbp+var_30]
0x18002cb60  call    ??$As@U?$IAsyncOperationWithProgress@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>>)
0x18002cb65  test    eax, eax
0x18002cb67  js      loc_18002CCF0
0x18002cb6d  mov     [rbp+arg_0], rdi
0x18002cb71  lea     rcx, [rbp+arg_0]
0x18002cb75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002cb7a  lea     rcx, [rbx+90h]
0x18002cb81  lea     r8, [rbp+arg_0]
0x18002cb85  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationProgressHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>::CopyLocal(_GUID const &,void * *)
0x18002cb8a  test    eax, eax
0x18002cb8c  js      loc_18002CCDD
0x18002cb92  lea     r15d, [rdi+1]
0x18002cb96  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002cb9d  test    rcx, rcx
0x18002cba0  jz      short loc_18002CBCF
0x18002cba2  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002cba9  movdqu  [rbp+var_20], xmm0
0x18002cbae  mov     rax, [rcx]
0x18002cbb1  mov     [rsp+70h+mshlflags], r15d
0x18002cbb6  mov     [rsp+70h+pvDestContext], rbx
0x18002cbbb  lea     r9, [rbp+var_20]
0x18002cbbf  lea     r8d, [rdi+2]
0x18002cbc3  mov     edx, r15d
0x18002cbc6  mov     rax, [rax+48h]
0x18002cbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbcf  mov     [rbp+arg_10], 0
0x18002cbd7  lea     rcx, [rbp+arg_10]
0x18002cbdb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002cbe0  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18002cbe4  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18002cbe8  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002cbed  mov     [rbp+ppstm], 0
0x18002cbf5  mov     [rbp+var_8], 0
0x18002cbfc  cmp     [rbp+arg_10], 0
0x18002cc01  jz      short loc_18002CC63
0x18002cc03  cmp     [rbp+arg_0], 0
0x18002cc08  jz      short loc_18002CC63
0x18002cc0a  mov     rdi, [rbp+pUnk]
0x18002cc0e  lea     rcx, [rbp+ppstm]
0x18002cc12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002cc17  lea     r8, [rbp+ppstm]; ppstm
0x18002cc1b  mov     edx, r15d; fDeleteOnRelease
0x18002cc1e  xor     ecx, ecx; hGlobal
0x18002cc20  call    cs:__imp_CreateStreamOnHGlobal
0x18002cc27  nop     dword ptr [rax+rax+00h]
0x18002cc2c  mov     [rbp+var_8], eax
0x18002cc2f  test    eax, eax
0x18002cc31  js      short loc_18002CC6A
0x18002cc33  mov     [rsp+70h+mshlflags], r15d; mshlflags
0x18002cc38  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x18002cc41  xor     r9d, r9d; dwDestContext
0x18002cc44  mov     r8, rdi; pUnk
0x18002cc47  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002cc4e  mov     rcx, [rbp+ppstm]; pStm
0x18002cc52  call    cs:__imp_CoMarshalInterface
0x18002cc59  nop     dword ptr [rax+rax+00h]
0x18002cc5e  mov     [rbp+var_8], eax
0x18002cc61  jmp     short loc_18002CC6A
0x18002cc63  mov     [rbp+var_8], 80004002h
0x18002cc6a  mov     rcx, [rbp+arg_0]
0x18002cc6e  movsd   xmm0, qword ptr [rsi]
0x18002cc72  movsd   qword ptr [rbp+var_20], xmm0
0x18002cc77  mov     eax, [rsi+8]
0x18002cc7a  mov     dword ptr [rbp+var_20+8], eax
0x18002cc7d  mov     rax, [rcx]
0x18002cc80  lea     r8, [rbp+var_20]
0x18002cc84  mov     rdx, [rbp+pUnk]
0x18002cc88  mov     rax, [rax+18h]
0x18002cc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc91  mov     r8, [rbx+98h]
0x18002cc98  mov     rdx, [rbp+arg_0]
0x18002cc9c  mov     ecx, eax
0x18002cc9e  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002cca3  mov     edi, eax
0x18002cca5  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002ccac  test    rcx, rcx
0x18002ccaf  jz      short loc_18002CCCA
0x18002ccb1  mov     r9, [rcx]
0x18002ccb4  mov     rax, [r9+50h]
0x18002ccb8  mov     r9d, r15d
0x18002ccbb  mov     r8d, 2
0x18002ccc1  mov     edx, r15d
0x18002ccc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccc9  nop
0x18002ccca  lea     rcx, [rbp+ppstm]
0x18002ccce  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(void)
0x18002ccd3  nop
0x18002ccd4  lea     rcx, [rbp+arg_10]
0x18002ccd8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ccdd  mov     rcx, rbx
0x18002cce0  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x18002cce5  nop
0x18002cce6  lea     rcx, [rbp+arg_0]
0x18002ccea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ccef  nop
0x18002ccf0  lea     rcx, [rbp+pUnk]
0x18002ccf4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ccf9  nop
0x18002ccfa  lea     rcx, [rbp+var_30]
0x18002ccfe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002cd03  mov     eax, edi
0x18002cd05  add     rsp, 70h
0x18002cd09  pop     r15
0x18002cd0b  pop     rdi
0x18002cd0c  pop     rsi
0x18002cd0d  pop     rbx
0x18002cd0e  pop     rbp
0x18002cd0f  retn
```
