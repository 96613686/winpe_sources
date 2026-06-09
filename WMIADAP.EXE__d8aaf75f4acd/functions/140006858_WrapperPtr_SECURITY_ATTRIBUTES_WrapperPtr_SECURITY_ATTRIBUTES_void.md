# __WrapperPtr<_SECURITY_ATTRIBUTES>::~__WrapperPtr<_SECURITY_ATTRIBUTES>(void)

- ea: `0x140006858`
- end: `0x14000685d`
- name: `??1?$__WrapperPtr@U_SECURITY_ATTRIBUTES@@@@UEAA@XZ`
- size: `5`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400152ae`

## callees

- `0x1400067e8`

## pseudocode

```c
// attributes: thunk
int __fastcall __WrapperPtr<_SECURITY_ATTRIBUTES>::~__WrapperPtr<_SECURITY_ATTRIBUTES>(_QWORD *a1)
{
  return __Wrapper<_SECURITY_ATTRIBUTES>::~__Wrapper<_SECURITY_ATTRIBUTES>(a1);
}

```

## disassembly

```asm
0x140006858  jmp     ??1?$__Wrapper@U_SECURITY_ATTRIBUTES@@@@UEAA@XZ; __Wrapper<_SECURITY_ATTRIBUTES>::~__Wrapper<_SECURITY_ATTRIBUTES>(void)
```
