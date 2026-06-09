# Microsoft::WRL::ComPtr<IXMLDOMNode>::~ComPtr<IXMLDOMNode>(void)

- ea: `0x18001fb84`
- end: `0x18001fb89`
- name: `??1?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `46`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800434ec`
- `0x180043510`
- `0x180043522`
- `0x180043569`
- `0x18004358d`
- `0x18004359f`
- `0x1800435b1`
- `0x18004360b`
- `0x18004361d`
- `0x18004377d`
- `0x1800437ac`
- `0x1800437be`
- `0x1800437d0`
- `0x1800437f4`
- `0x1800439e8`
- `0x180043a0c`
- `0x180043a1e`
- `0x180043a42`
- `0x180043aae`
- `0x180043ac0`
- `0x180043bdc`
- `0x180043c8b`
- `0x180043d39`
- `0x180043d6f`
- `0x180043d81`
- `0x180043dc9`
- `0x180043ddb`
- `0x180043dff`
- `0x180043e11`
- `0x180043e35`
- `0x180043e47`
- `0x180043e59`
- `0x180043e6b`
- `0x180043e7d`
- `0x180044216`
- `0x180044228`
- `0x18004423a`
- `0x180044a67`
- `0x180044a9d`
- `0x180044aaf`
- `0x180044ae5`
- `0x180044e6b`
- `0x180044efb`
- `0x180044f11`
- `0x180044f96`
- `0x1800450c2`

## callees

- `0x180014e7c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IXMLDOMNode>::~ComPtr<IXMLDOMNode>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18001fb84  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
