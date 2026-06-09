# MesDecodeBufferHandleCreate

- ea: `0x18008b054`
- end: `0x18008b05a`
- name: `MesDecodeBufferHandleCreate`
- size: `6`
- prototype: `RPC_STATUS __stdcall(char *Buffer, unsigned int BufferSize, handle_t *pHandle)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18006b1a8`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18008b054`

## pseudocode

```c
// attributes: thunk
RPC_STATUS __stdcall MesDecodeBufferHandleCreate(char *Buffer, unsigned int BufferSize, handle_t *pHandle)
{
  return __imp_MesDecodeBufferHandleCreate(Buffer, BufferSize, pHandle);
}

```

## disassembly

```asm
0x18008b054  jmp     cs:__imp_MesDecodeBufferHandleCreate
```
