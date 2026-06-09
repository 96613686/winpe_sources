# _dynamic_initializer_for__UserAccountPersistence::s_ComTaskPoolContext__

- ea: `0x180003120`
- end: `0x180003135`
- name: `_dynamic_initializer_for__UserAccountPersistence::s_ComTaskPoolContext__`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x180003124`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x180003124`

## pseudocode

```c
__int64 dynamic_initializer_for__UserAccountPersistence::s_ComTaskPoolContext__()
{
  __int64 result; // rax

  result = SHTaskPoolGetUniqueContext();
  UserAccountPersistence::s_ComTaskPoolContext = result;
  return result;
}

```

## disassembly

```asm
0x180003120  sub     rsp, 28h
0x180003124  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18000312a  mov     cs:?s_ComTaskPoolContext@UserAccountPersistence@@2KA, eax; ulong UserAccountPersistence::s_ComTaskPoolContext
0x180003130  add     rsp, 28h
0x180003134  retn
```
