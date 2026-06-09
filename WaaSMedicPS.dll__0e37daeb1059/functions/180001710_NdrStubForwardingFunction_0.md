# NdrStubForwardingFunction_0

- ea: `0x180001710`
- end: `0x180001716`
- name: `NdrStubForwardingFunction_0`
- size: `6`
- prototype: `void __stdcall(IRpcStubBuffer *This, IRpcChannelBuffer *pChannel, PRPC_MESSAGE pmsg, DWORD *pdwStubPhase)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrStubForwardingFunction` at `0x180001710`

## pseudocode

```c
// attributes: thunk
void __stdcall NdrStubForwardingFunction_0(
        IRpcStubBuffer *This,
        IRpcChannelBuffer *pChannel,
        PRPC_MESSAGE pmsg,
        DWORD *pdwStubPhase)
{
  NdrStubForwardingFunction(This, pChannel, pmsg, pdwStubPhase);
}

```

## disassembly

```asm
0x180001710  jmp     cs:__imp_NdrStubForwardingFunction
```
