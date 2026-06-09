# Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(void)

- ea: `0x180015034`
- end: `0x180015039`
- name: `??1?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800207b5`
- `0x1800207c7`
- `0x1800207eb`
- `0x1800207fd`
- `0x18002080f`
- `0x180020845`
- `0x180020857`
- `0x180020869`
- `0x1800208b1`

## callees

- `0x180017348`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180015034  jmp     ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
```
