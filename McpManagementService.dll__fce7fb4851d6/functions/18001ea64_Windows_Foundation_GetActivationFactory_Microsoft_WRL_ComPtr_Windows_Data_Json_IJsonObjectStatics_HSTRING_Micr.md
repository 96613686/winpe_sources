# Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)

- ea: `0x18001ea64`
- end: `0x18001ea9a`
- name: `??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ef30`
- `0x18001f77c`
- `0x18001f9a4`
- `0x1800203b0`
- `0x180020e9c`

## callees

- `0x180009fc0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ea93`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return RoGetActivationFactory(a1, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, a2);
}

```

## disassembly

```asm
0x18001ea64  mov     [rsp+arg_0], rbx
0x18001ea69  push    rdi
0x18001ea6a  sub     rsp, 20h
0x18001ea6e  mov     rdi, rcx
0x18001ea71  mov     rbx, rdx
0x18001ea74  mov     rcx, rdx
0x18001ea77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ea7c  mov     r8, rbx
0x18001ea7f  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18001ea86  mov     rcx, rdi
0x18001ea89  mov     rbx, [rsp+28h+arg_0]
0x18001ea8e  add     rsp, 20h
0x18001ea92  pop     rdi
0x18001ea93  jmp     cs:__imp_RoGetActivationFactory
```
