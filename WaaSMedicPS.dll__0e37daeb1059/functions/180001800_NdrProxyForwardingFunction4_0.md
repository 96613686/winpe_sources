# NdrProxyForwardingFunction4_0

- ea: `0x180001800`
- end: `0x180001806`
- name: `NdrProxyForwardingFunction4_0`
- size: `6`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-midlproxystub-l1-1-0!NdrProxyForwardingFunction4` at `0x180001800`

## pseudocode

```c
// attributes: thunk
void __stdcall NdrProxyForwardingFunction4_0()
{
  NdrProxyForwardingFunction4();
}

```

## disassembly

```asm
0x180001800  jmp     cs:__imp_NdrProxyForwardingFunction4
```
