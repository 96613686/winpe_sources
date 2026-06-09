# winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResourceT<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>::GetRuntimeClassName(void)

- ea: `0x180006490`
- end: `0x1800064aa`
- name: `?GetRuntimeClassName@?$ImageBufferResourceT@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@U1implementation@3456@$$V@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UEBA?AUhstring@6@XZ`
- size: `26`
- prototype: `winrt::hstring *__fastcall(__int64, winrt::hstring *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800013a0`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResourceT<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, (const wchar_t *)a2);
  return a2;
}

```

## disassembly

```asm
0x180006490  push    rbx
0x180006492  sub     rsp, 30h
0x180006496  mov     rcx, rdx; this
0x180006499  mov     rbx, rdx
0x18000649c  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1800064a1  mov     rax, rbx
0x1800064a4  add     rsp, 30h
0x1800064a8  pop     rbx
0x1800064a9  retn
```
