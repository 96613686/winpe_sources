# _com_ptr_t<_com_IIID<IEnumWbemClassObject,&__s_GUID const _GUID_027947e1_d731_11ce_a357_000000000001>>::~_com_ptr_t<_com_IIID<IEnumWbemClassObject,&__s_GUID const _GUID_027947e1_d731_11ce_a357_000000000001>>(void)

- ea: `0x1800173f8`
- end: `0x1800173fd`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIEnumWbemClassObject@@$1?_GUID_027947e1_d731_11ce_a357_000000000001@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ed59`
- `0x18001ed7d`
- `0x18001edb3`
- `0x18001edc5`

## callees

- `0x180019818`

## pseudocode

```c
// attributes: thunk
__int64 _com_ptr_t<_com_IIID<IEnumWbemClassObject,&__s_GUID const _GUID_027947e1_d731_11ce_a357_000000000001>>::~_com_ptr_t<_com_IIID<IEnumWbemClassObject,&__s_GUID const _GUID_027947e1_d731_11ce_a357_000000000001>>()
{
  return _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release();
}

```

## disassembly

```asm
0x1800173f8  jmp     ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
```
