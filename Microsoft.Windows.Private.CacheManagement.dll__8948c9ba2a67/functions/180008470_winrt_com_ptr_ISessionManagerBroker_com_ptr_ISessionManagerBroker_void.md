# winrt::com_ptr<ISessionManagerBroker>::~com_ptr<ISessionManagerBroker>(void)

- ea: `0x180008470`
- end: `0x18000847b`
- name: `??1?$com_ptr@UISessionManagerBroker@@@winrt@@QEAA@XZ`
- size: `11`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001dff8`
- `0x18001e004`

## callees

- `0x18000a740`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<ISessionManagerBroker>::~com_ptr<ISessionManagerBroker>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x180008470  cmp     qword ptr [rcx], 0
0x180008474  jnz     ?unconditional_release_ref@?$com_ptr@UISessionManagerBroker@@@winrt@@AEAAXXZ; winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(void)
0x18000847a  retn
```
