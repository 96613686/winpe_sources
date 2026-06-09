# _COpusDecMFT::ConfigOutputTypes_::_1_::dtor$0

- ea: `0x180022fc5`
- end: `0x180022fd1`
- name: `_COpusDecMFT::ConfigOutputTypes_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001b31c`

## pseudocode

```c
__int64 __fastcall COpusDecMFT::ConfigOutputTypes_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IMFSample>::~CComPtr<IMFSample>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x180022fc5  lea     rcx, [rdx+60h]
0x180022fcc  jmp     ??1?$CComPtr@UIMFSample@@@ATL@@QEAA@XZ; ATL::CComPtr<IMFSample>::~CComPtr<IMFSample>(void)
```
