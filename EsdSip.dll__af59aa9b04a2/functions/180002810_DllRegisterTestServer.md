# DllRegisterTestServer

- ea: `0x180002810`
- end: `0x18000281c`
- name: `DllRegisterTestServer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800028d0`

## pseudocode

```c
__int64 DllRegisterTestServer()
{
  return RegisterServer(&GUID_ESDSIP_TEST);
}

```

## disassembly

```asm
0x180002810  lea     rcx, GUID_ESDSIP_TEST
0x180002817  jmp     RegisterServer
```
