# _dynamic_initializer_for__s_comTaskPoolCallingContext__

- ea: `0x1800020d0`
- end: `0x1800020e5`
- name: `_dynamic_initializer_for__s_comTaskPoolCallingContext__`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800020d4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800020d4`

## pseudocode

```c
__int64 dynamic_initializer_for__s_comTaskPoolCallingContext__()
{
  __int64 result; // rax

  result = SHTaskPoolGetUniqueContext();
  dword_18007EB30 = result;
  return result;
}

```

## disassembly

```asm
0x1800020d0  sub     rsp, 28h
0x1800020d4  call    cs:__imp_SHTaskPoolGetUniqueContext
0x1800020da  mov     cs:dword_18007EB30, eax
0x1800020e0  add     rsp, 28h
0x1800020e4  retn
```
