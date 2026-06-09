# Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)

- ea: `0x140005850`
- end: `0x1400058df`
- name: `??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140016a54`

## callees

- `0x140003644`
- `0x140005850`
- `0x140008024`
- `0x140008920`
- `0x140011cc0`
- `0x140012ce0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
        _QWORD *a1,
        int *a2)
{
  Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *v4; // rax
  unsigned int Interface; // edi
  __int64 v6; // rax
  int v7; // ecx
  __int64 v8; // rbx
  Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *v10; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = (Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v4;
  if ( v4 )
  {
    v6 = Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::ActivationFactoryContractRedirectorContext(v4);
    v7 = *a2;
    v10 = 0;
    v8 = v6;
    *(_DWORD *)(v6 + 68) = v7;
    Interface = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::QueryInterface(
                  v6,
                  &GUID_7d6e17e4_e332_45e3_a8c9_b7291a38c23b,
                  a1);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::Release(v8);
  }
  else
  {
    Interface = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(&v10);
  return Interface;
}

```

## disassembly

```asm
0x140005850  mov     [rsp+arg_8], rbx
0x140005855  mov     [rsp+arg_10], rsi
0x14000585a  push    rdi
0x14000585b  sub     rsp, 20h
0x14000585f  mov     rsi, rdx
0x140005862  mov     qword ptr [rcx], 0
0x140005869  mov     rdi, rcx
0x14000586c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005873  mov     ecx, 48h ; 'H'; unsigned __int64
0x140005878  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000587d  mov     [rsp+28h+arg_0], rax
0x140005882  test    rax, rax
0x140005885  jnz     short loc_14000588E
0x140005887  mov     edi, 8007000Eh
0x14000588c  jmp     short loc_1400058C3
0x14000588e  mov     rcx, rax; this
0x140005891  call    ??0ActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::ActivationFactoryContractRedirectorContext(void)
0x140005896  mov     ecx, [rsi]
0x140005898  lea     rdx, _GUID_7d6e17e4_e332_45e3_a8c9_b7291a38c23b
0x14000589f  mov     r8, rdi
0x1400058a2  mov     [rsp+28h+arg_0], 0
0x1400058ab  mov     rbx, rax
0x1400058ae  mov     [rax+44h], ecx
0x1400058b1  mov     rcx, rax
0x1400058b4  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
0x1400058b9  mov     rcx, rbx
0x1400058bc  mov     edi, eax
0x1400058be  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::Release(void)
0x1400058c3  lea     rcx, [rsp+28h+arg_0]
0x1400058c8  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x1400058cd  mov     rbx, [rsp+28h+arg_8]
0x1400058d2  mov     eax, edi
0x1400058d4  mov     rsi, [rsp+28h+arg_10]
0x1400058d9  add     rsp, 20h
0x1400058dd  pop     rdi
0x1400058de  retn
```
