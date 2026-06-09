# Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>)

- ea: `0x140008814`
- end: `0x14000884a`
- name: `??$GetActivationFactory@V?$ComPtr@UIJsonArrayStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArrayStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000bc30`
- `0x14000c848`

## callees

- `0x14000d49c`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008843`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(a2);
  return RoGetActivationFactory(a1, &GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba, a2);
}

```

## disassembly

```asm
0x140008814  mov     [rsp+arg_0], rbx
0x140008819  push    rdi
0x14000881a  sub     rsp, 20h
0x14000881e  mov     rdi, rcx
0x140008821  mov     rbx, rdx
0x140008824  mov     rcx, rdx
0x140008827  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000882c  mov     r8, rbx
0x14000882f  lea     rdx, _GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba
0x140008836  mov     rcx, rdi
0x140008839  mov     rbx, [rsp+28h+arg_0]
0x14000883e  add     rsp, 20h
0x140008842  pop     rdi
0x140008843  jmp     cs:__imp_RoGetActivationFactory
```
