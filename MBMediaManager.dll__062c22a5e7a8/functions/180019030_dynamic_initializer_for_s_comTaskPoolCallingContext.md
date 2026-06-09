# _dynamic_initializer_for__s_comTaskPoolCallingContext__

- ea: `0x180019030`
- end: `0x180019045`
- name: `_dynamic_initializer_for__s_comTaskPoolCallingContext__`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180019034`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180019034`

## pseudocode

```c
__int64 dynamic_initializer_for__s_comTaskPoolCallingContext__()
{
  __int64 result; // rax

  result = SHTaskPoolGetUniqueContext();
  dword_18007EE80 = result;
  return result;
}

```

## disassembly

```asm
0x180019030  sub     rsp, 28h
0x180019034  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18001903a  mov     cs:dword_18007EE80, eax
0x180019040  add     rsp, 28h
0x180019044  retn
```
