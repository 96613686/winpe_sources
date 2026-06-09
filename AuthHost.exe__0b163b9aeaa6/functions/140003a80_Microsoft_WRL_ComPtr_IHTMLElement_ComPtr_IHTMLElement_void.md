# Microsoft::WRL::ComPtr<IHTMLElement>::~ComPtr<IHTMLElement>(void)

- ea: `0x140003a80`
- end: `0x140003a85`
- name: `??1?$ComPtr@UIHTMLElement@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013173`
- `0x140013189`
- `0x14001319f`
- `0x1400131b5`
- `0x1400131cb`
- `0x140013271`
- `0x140013283`
- `0x1400132ef`
- `0x140013313`
- `0x140013325`
- `0x140013337`
- `0x140013349`
- `0x14001335b`
- `0x14001337f`
- `0x140013391`
- `0x1400133a3`
- `0x1400133b5`
- `0x1400133c7`
- `0x14001386c`
- `0x140013890`

## callees

- `0x140003a8c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IHTMLElement>::~ComPtr<IHTMLElement>(__int64 *a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x140003a80  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
