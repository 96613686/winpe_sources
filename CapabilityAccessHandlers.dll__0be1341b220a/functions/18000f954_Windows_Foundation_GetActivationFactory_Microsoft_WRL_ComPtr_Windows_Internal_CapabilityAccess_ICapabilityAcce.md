# Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)

- ea: `0x18000f954`
- end: `0x18000f98a`
- name: `??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010a5c`
- `0x18001248c`

## callees

- `0x18000f758`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000f983`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(a2);
  return RoGetActivationFactory(a1, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, a2);
}

```

## disassembly

```asm
0x18000f954  mov     [rsp+arg_0], rbx
0x18000f959  push    rdi
0x18000f95a  sub     rsp, 20h
0x18000f95e  mov     rdi, rcx
0x18000f961  mov     rbx, rdx
0x18000f964  mov     rcx, rdx
0x18000f967  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f96c  mov     r8, rbx
0x18000f96f  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x18000f976  mov     rcx, rdi
0x18000f979  mov     rbx, [rsp+28h+arg_0]
0x18000f97e  add     rsp, 20h
0x18000f982  pop     rdi
0x18000f983  jmp     cs:__imp_RoGetActivationFactory
```
