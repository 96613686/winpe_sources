# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,0>::~SimpleKeyValuePair<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,0>(void)

- ea: `0x180011af4`
- end: `0x180011b1c`
- name: `??1?$SimpleKeyValuePair@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@E@3456@$0A@@Internal@Collections@Foundation@Windows@@UEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012320`

## callees

- `0x180007c48`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011b01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011b01`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,0>::~SimpleKeyValuePair<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,0>(
        __int64 a1)
{
  WindowsDeleteString(*(HSTRING *)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>(a1);
}

```

## disassembly

```asm
0x180011af4  push    rbx
0x180011af6  sub     rsp, 20h
0x180011afa  mov     rbx, rcx
0x180011afd  mov     rcx, [rcx+20h]; string
0x180011b01  call    cs:__imp_WindowsDeleteString
0x180011b07  mov     rcx, rbx
0x180011b0a  mov     qword ptr [rbx+20h], 0
0x180011b12  add     rsp, 20h
0x180011b16  pop     rbx
0x180011b17  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIStaticIpConfig@UX@Networking@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>(void)
```
