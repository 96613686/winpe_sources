# CreateNResampler

- ea: `0x18006ea40`
- end: `0x18006ea45`
- name: `CreateNResampler`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800086f4`

## pseudocode

```c
// attributes: thunk
__int64 CreateNResampler()
{
  return Microsoft::WRL::Details::MakeAndInitialize<NResamplerWrapper,INResampler,>();
}

```

## disassembly

```asm
0x18006ea40  jmp     ??$MakeAndInitialize@VNResamplerWrapper@@UINResampler@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUINResampler@@@Z; Microsoft::WRL::Details::MakeAndInitialize<NResamplerWrapper,INResampler,>(INResampler * *)
```
