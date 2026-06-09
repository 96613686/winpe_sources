# NdrProxyForwardingFunction3_0

- ea: `0x180001900`
- end: `0x180001906`
- name: `NdrProxyForwardingFunction3_0`
- size: `6`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-midlproxystub-l1-1-0!NdrProxyForwardingFunction3` at `0x180001900`

## pseudocode

```c
// attributes: thunk
void __stdcall NdrProxyForwardingFunction3_0()
{
  NdrProxyForwardingFunction3();
}

```

## disassembly

```asm
0x180001900  jmp     cs:__imp_NdrProxyForwardingFunction3
```
