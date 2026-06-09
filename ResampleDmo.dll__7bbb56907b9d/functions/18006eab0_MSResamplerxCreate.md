# MSResamplerxCreate

- ea: `0x18006eab0`
- end: `0x18006eab8`
- name: `MSResamplerxCreate`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18006ec00`

## pseudocode

```c
CRSxHandle *__fastcall MSResamplerxCreate(struct WAVEFORMATEXTENSIBLE *a1, struct WAVEFORMATEXTENSIBLE *a2)
{
  return MSResamplerxParamsCreate(a1, a2, 0);
}

```

## disassembly

```asm
0x18006eab0  xor     r8d, r8d
0x18006eab3  jmp     MSResamplerxParamsCreate
```
