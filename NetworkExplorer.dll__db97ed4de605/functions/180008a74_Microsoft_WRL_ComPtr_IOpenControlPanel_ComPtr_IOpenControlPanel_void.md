# Microsoft::WRL::ComPtr<IOpenControlPanel>::~ComPtr<IOpenControlPanel>(void)

- ea: `0x180008a74`
- end: `0x180008a79`
- name: `??1?$ComPtr@UIOpenControlPanel@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f54f`

## callees

- `0x18000a1ec`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IOpenControlPanel>::~ComPtr<IOpenControlPanel>(__int64 *a1)
{
  return Microsoft::WRL::ComPtr<IOpenControlPanel>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180008a74  jmp     ?InternalRelease@?$ComPtr@UIOpenControlPanel@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOpenControlPanel>::InternalRelease(void)
```
