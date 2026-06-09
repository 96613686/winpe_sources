# winrt::com_ptr<ISessionManagerBroker2>::~com_ptr<ISessionManagerBroker2>(void)

- ea: `0x18000a340`
- end: `0x18000a34b`
- name: `??1?$com_ptr@UISessionManagerBroker2@@@winrt@@QEAA@XZ`
- size: `11`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003cef1`
- `0x18003cefd`
- `0x18003f285`
- `0x18003f2a0`
- `0x18003f350`
- `0x18003f510`
- `0x18003f51c`
- `0x18003f550`
- `0x18003f55c`
- `0x18003f5c0`
- `0x18003f5cc`
- `0x18003f660`
- `0x18003f66c`
- `0x1800416f7`
- `0x180041722`

## callees

- `0x18000d970`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<ISessionManagerBroker2>::~com_ptr<ISessionManagerBroker2>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref();
  return result;
}

```

## disassembly

```asm
0x18000a340  cmp     qword ptr [rcx], 0
0x18000a344  jnz     ?unconditional_release_ref@?$com_ptr@UISessionManagerBroker@@@winrt@@AEAAXXZ; winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(void)
0x18000a34a  retn
```
