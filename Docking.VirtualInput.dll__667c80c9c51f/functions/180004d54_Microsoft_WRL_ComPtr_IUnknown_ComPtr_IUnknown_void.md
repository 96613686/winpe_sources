# Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(void)

- ea: `0x180004d54`
- end: `0x180004d59`
- name: `??1?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c464`
- `0x180013a30`

## callees

- `0x18000601c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(__int64 *a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180004d54  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
