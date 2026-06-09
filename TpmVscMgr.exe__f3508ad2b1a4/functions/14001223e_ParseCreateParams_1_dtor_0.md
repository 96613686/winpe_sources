# _ParseCreateParams_::_1_::dtor$0

- ea: `0x14001223e`
- end: `0x14001224a`
- name: `_ParseCreateParams_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000dbfc`

## pseudocode

```c
void __fastcall ParseCreateParams_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CreateParams::~CreateParams((CreateParams *)(a2 + 272));
}

```

## disassembly

```asm
0x14001223e  lea     rcx, [rdx+110h]; this
0x140012245  jmp     ??1CreateParams@@QEAA@XZ; CreateParams::~CreateParams(void)
```
