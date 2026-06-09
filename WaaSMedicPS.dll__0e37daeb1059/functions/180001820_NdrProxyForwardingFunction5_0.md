# NdrProxyForwardingFunction5_0

- ea: `0x180001820`
- end: `0x180001826`
- name: `NdrProxyForwardingFunction5_0`
- size: `6`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-midlproxystub-l1-1-0!NdrProxyForwardingFunction5` at `0x180001820`

## pseudocode

```c
// attributes: thunk
void __stdcall NdrProxyForwardingFunction5_0()
{
  NdrProxyForwardingFunction5();
}

```

## disassembly

```asm
0x180001820  jmp     cs:__imp_NdrProxyForwardingFunction5
```
