# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress)

- ea: `0x18002e0ac`
- end: `0x18002e290`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJUExpectedAndCurrentResourceProgress@Enrollment@EnterpriseDeviceManagement@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800352d0`

## callees

- `0x18000992c`
- `0x180017154`
- `0x180017838`
- `0x180018eb8`
- `0x180018ff0`
- `0x18001b498`
- `0x18002b578`
- `0x18002e0ac`
- `0x180038898`
- `0x180038a48`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002e1d8`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002e1d8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002e1ac`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002e1ac`

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
  __int64 (__fastcall ***v10[2])(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-30h] BYREF
  GUID v11; // [rsp+50h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+60h] [rbp-10h] BYREF
  HRESULT v13; // [rsp+68h] [rbp-8h]
  struct IUnknown *v14; // [rsp+A0h] [rbp+30h] BYREF
  struct IRpcOptions *v15; // [rsp+B0h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+B8h] [rbp+48h] BYREF

  v4 = 0;
  v10[0] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(v10);
  pUnk = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1)
    && (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>(
              v10,
              (__int64)&pUnk) >= 0 )
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
0x18002e0ac  push    rbp
0x18002e0ae  push    rbx
0x18002e0af  push    rsi
0x18002e0b0  push    rdi
0x18002e0b1  push    r15
0x18002e0b3  mov     rbp, rsp
0x18002e0b6  sub     rsp, 70h
0x18002e0ba  mov     rsi, rdx
0x18002e0bd  mov     rbx, rcx
0x18002e0c0  xor     edi, edi
0x18002e0c2  mov     [rbp+var_30], rcx
0x18002e0c6  lea     rcx, [rbp+var_30]
0x18002e0ca  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002e0cf  nop
0x18002e0d0  mov     [rbp+pUnk], rdi
0x18002e0d4  mov     rcx, rbx
0x18002e0d7  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVReflectedEnrollmentResult@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x18002e0dc  test    al, al
0x18002e0de  jz      loc_18002E270
0x18002e0e4  lea     rdx, [rbp+pUnk]
0x18002e0e8  lea     rcx, [rbp+var_30]
0x18002e0ec  call    ??$As@U?$IAsyncOperationWithProgress@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>>)
0x18002e0f1  test    eax, eax
0x18002e0f3  js      loc_18002E270
0x18002e0f9  mov     [rbp+arg_0], rdi
0x18002e0fd  lea     rcx, [rbp+arg_0]
0x18002e101  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e106  lea     rcx, [rbx+90h]
0x18002e10d  lea     r8, [rbp+arg_0]
0x18002e111  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationProgressHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>::CopyLocal(_GUID const &,void * *)
0x18002e116  test    eax, eax
0x18002e118  js      loc_18002E25D
0x18002e11e  lea     r15d, [rdi+1]
0x18002e122  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002e129  test    rcx, rcx
0x18002e12c  jz      short loc_18002E15B
0x18002e12e  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002e135  movdqu  [rbp+var_20], xmm0
0x18002e13a  mov     rax, [rcx]
0x18002e13d  mov     [rsp+70h+mshlflags], r15d
0x18002e142  mov     [rsp+70h+pvDestContext], rbx
0x18002e147  lea     r9, [rbp+var_20]
0x18002e14b  lea     r8d, [rdi+2]
0x18002e14f  mov     edx, r15d
0x18002e152  mov     rax, [rax+48h]
0x18002e156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e15b  mov     [rbp+arg_10], 0
0x18002e163  lea     rcx, [rbp+arg_10]
0x18002e167  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e16c  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18002e170  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18002e174  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002e179  mov     [rbp+ppstm], 0
0x18002e181  mov     [rbp+var_8], 0
0x18002e188  cmp     [rbp+arg_10], 0
0x18002e18d  jz      short loc_18002E1E3
0x18002e18f  cmp     [rbp+arg_0], 0
0x18002e194  jz      short loc_18002E1E3
0x18002e196  mov     rdi, [rbp+pUnk]
0x18002e19a  lea     rcx, [rbp+ppstm]
0x18002e19e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e1a3  lea     r8, [rbp+ppstm]; ppstm
0x18002e1a7  mov     edx, r15d; fDeleteOnRelease
0x18002e1aa  xor     ecx, ecx; hGlobal
0x18002e1ac  call    cs:__imp_CreateStreamOnHGlobal
0x18002e1b2  mov     [rbp+var_8], eax
0x18002e1b5  test    eax, eax
0x18002e1b7  js      short loc_18002E1EA
0x18002e1b9  mov     [rsp+70h+mshlflags], r15d; mshlflags
0x18002e1be  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x18002e1c7  xor     r9d, r9d; dwDestContext
0x18002e1ca  mov     r8, rdi; pUnk
0x18002e1cd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002e1d4  mov     rcx, [rbp+ppstm]; pStm
0x18002e1d8  call    cs:__imp_CoMarshalInterface
0x18002e1de  mov     [rbp+var_8], eax
0x18002e1e1  jmp     short loc_18002E1EA
0x18002e1e3  mov     [rbp+var_8], 80004002h
0x18002e1ea  mov     rcx, [rbp+arg_0]
0x18002e1ee  movsd   xmm0, qword ptr [rsi]
0x18002e1f2  movsd   qword ptr [rbp+var_20], xmm0
0x18002e1f7  mov     eax, [rsi+8]
0x18002e1fa  mov     dword ptr [rbp+var_20+8], eax
0x18002e1fd  mov     rax, [rcx]
0x18002e200  lea     r8, [rbp+var_20]
0x18002e204  mov     rdx, [rbp+pUnk]
0x18002e208  mov     rax, [rax+18h]
0x18002e20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e211  mov     r8, [rbx+98h]
0x18002e218  mov     rdx, [rbp+arg_0]
0x18002e21c  mov     ecx, eax
0x18002e21e  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002e223  mov     edi, eax
0x18002e225  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002e22c  test    rcx, rcx
0x18002e22f  jz      short loc_18002E24A
0x18002e231  mov     r9, [rcx]
0x18002e234  mov     rax, [r9+50h]
0x18002e238  mov     r9d, r15d
0x18002e23b  mov     r8d, 2
0x18002e241  mov     edx, r15d
0x18002e244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e249  nop
0x18002e24a  lea     rcx, [rbp+ppstm]
0x18002e24e  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(void)
0x18002e253  nop
0x18002e254  lea     rcx, [rbp+arg_10]
0x18002e258  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e25d  mov     rcx, rbx
0x18002e260  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,Windows::Foundation::IAsyncOperationProgressHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x18002e265  nop
0x18002e266  lea     rcx, [rbp+arg_0]
0x18002e26a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e26f  nop
0x18002e270  lea     rcx, [rbp+pUnk]
0x18002e274  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e279  nop
0x18002e27a  lea     rcx, [rbp+var_30]
0x18002e27e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e283  mov     eax, edi
0x18002e285  add     rsp, 70h
0x18002e289  pop     r15
0x18002e28b  pop     rdi
0x18002e28c  pop     rsi
0x18002e28d  pop     rbx
0x18002e28e  pop     rbp
0x18002e28f  retn
```
