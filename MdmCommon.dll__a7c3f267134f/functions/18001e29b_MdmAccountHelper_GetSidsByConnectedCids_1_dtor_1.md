# _MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor$1

- ea: `0x18001e29b`
- end: `0x18001e2a7`
- name: `_MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002db8`

## pseudocode

```c
_QWORD *__fastcall MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IEnumUnknown>::~ComPtr<IEnumUnknown>((_QWORD *)(a2 + 88));
}

```

## disassembly

```asm
0x18001e29b  lea     rcx, [rdx+58h]
0x18001e2a2  jmp     ??1?$ComPtr@UIEnumUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IEnumUnknown>::~ComPtr<IEnumUnknown>(void)
```
