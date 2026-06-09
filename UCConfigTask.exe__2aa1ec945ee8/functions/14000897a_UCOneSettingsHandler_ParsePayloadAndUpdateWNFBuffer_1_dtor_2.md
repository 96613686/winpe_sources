# _UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$2

- ea: `0x14000897a`
- end: `0x140008986`
- name: `_UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140007e80`

## pseudocode

```c
void __fastcall UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor_2(__int64 a1, unsigned __int64 a2)
{
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>((void **)(a2 + 72), a2);
}

```

## disassembly

```asm
0x14000897a  lea     rcx, [rdx+48h]
0x140008981  jmp     ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
```
