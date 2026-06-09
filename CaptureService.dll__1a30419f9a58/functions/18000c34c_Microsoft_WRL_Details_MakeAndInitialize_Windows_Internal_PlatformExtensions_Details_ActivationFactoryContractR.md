# Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)

- ea: `0x18000c34c`
- end: `0x18000c3db`
- name: `??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015d0c`

## callees

- `0x18000335c`
- `0x18000bcf0`
- `0x18000c34c`
- `0x18000d504`
- `0x18000dc98`
- `0x180013d90`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
        _QWORD *a1,
        int *a2)
{
  Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *v4; // rax
  unsigned int v5; // edi
  __int64 v6; // rax
  int v7; // ecx
  __int64 v8; // rbx
  Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *v10; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = (Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v4;
  if ( v4 )
  {
    v6 = Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::ActivationFactoryContractRedirectorContext(v4);
    v7 = *a2;
    v10 = 0;
    v8 = v6;
    *(_DWORD *)(v6 + 68) = v7;
    v5 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>>(
           v6,
           &GUID_7d6e17e4_e332_45e3_a8c9_b7291a38c23b,
           a1);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::Release(v8);
  }
  else
  {
    v5 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v10);
  return v5;
}

```

## disassembly

```asm
0x18000c34c  mov     [rsp+arg_8], rbx
0x18000c351  mov     [rsp+arg_10], rsi
0x18000c356  push    rdi
0x18000c357  sub     rsp, 20h
0x18000c35b  mov     rsi, rdx
0x18000c35e  mov     qword ptr [rcx], 0
0x18000c365  mov     rdi, rcx
0x18000c368  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c36f  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000c374  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c379  mov     [rsp+28h+arg_0], rax
0x18000c37e  test    rax, rax
0x18000c381  jnz     short loc_18000C38A
0x18000c383  mov     edi, 8007000Eh
0x18000c388  jmp     short loc_18000C3BF
0x18000c38a  mov     rcx, rax; this
0x18000c38d  call    ??0ActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::ActivationFactoryContractRedirectorContext(void)
0x18000c392  mov     ecx, [rsi]
0x18000c394  lea     rdx, _GUID_7d6e17e4_e332_45e3_a8c9_b7291a38c23b
0x18000c39b  mov     r8, rdi
0x18000c39e  mov     [rsp+28h+arg_0], 0
0x18000c3a7  mov     rbx, rax
0x18000c3aa  mov     [rax+44h], ecx
0x18000c3ad  mov     rcx, rax
0x18000c3b0  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x18000c3b5  mov     rcx, rbx
0x18000c3b8  mov     edi, eax
0x18000c3ba  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::Release(void)
0x18000c3bf  lea     rcx, [rsp+28h+arg_0]
0x18000c3c4  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18000c3c9  mov     rbx, [rsp+28h+arg_8]
0x18000c3ce  mov     eax, edi
0x18000c3d0  mov     rsi, [rsp+28h+arg_10]
0x18000c3d5  add     rsp, 20h
0x18000c3d9  pop     rdi
0x18000c3da  retn
```
