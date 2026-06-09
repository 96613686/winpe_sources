# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)

- ea: `0x18000476c`
- end: `0x18000478a`
- name: `?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004de0`

## callees

- `0x18000474c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
        __int64 a1,
        unsigned int *a2,
        __int64 a3)
{
  int v3; // ecx

  v3 = *a2;
  *(GUID *)(a3 + 16LL * *a2) = GUID_6305b671_f6cd_4ff6_9120_e0c4cd921011;
  *a2 = v3 + 1;
  return Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid();
}

```

## disassembly

```asm
0x18000476c  mov     ecx, [rdx]
0x18000476e  movups  xmm0, xmmword ptr cs:_GUID_6305b671_f6cd_4ff6_9120_e0c4cd921011.Data1
0x180004775  mov     eax, ecx
0x180004777  add     rax, rax
0x18000477a  movdqu  xmmword ptr [r8+rax*8], xmm0
0x180004780  lea     eax, [rcx+1]
0x180004783  mov     [rdx], eax
0x180004785  jmp     ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
```
