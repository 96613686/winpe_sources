# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::~SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>(void)

- ea: `0x18006098c`
- end: `0x1800609c6`
- name: `??1?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@UEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180060b20`

## callees

- `0x18001cbc8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800609ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800609ab`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::~SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>(
        __int64 a1)
{
  WindowsDeleteString(*(HSTRING *)(a1 + 40));
  *(_QWORD *)(a1 + 40) = 0;
  WindowsDeleteString(*(HSTRING *)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>(a1);
}

```

## disassembly

```asm
0x18006098c  push    rbx
0x18006098e  sub     rsp, 20h
0x180060992  mov     rbx, rcx
0x180060995  mov     rcx, [rcx+28h]; string
0x180060999  call    cs:__imp_WindowsDeleteString
0x18006099f  mov     qword ptr [rbx+28h], 0
0x1800609a7  mov     rcx, [rbx+20h]; string
0x1800609ab  call    cs:__imp_WindowsDeleteString
0x1800609b1  mov     rcx, rbx
0x1800609b4  mov     qword ptr [rbx+20h], 0
0x1800609bc  add     rsp, 20h
0x1800609c0  pop     rbx
0x1800609c1  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>(void)
```
