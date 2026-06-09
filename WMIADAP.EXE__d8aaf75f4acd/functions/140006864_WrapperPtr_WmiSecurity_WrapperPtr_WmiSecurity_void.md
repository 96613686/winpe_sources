# __WrapperPtr<WmiSecurity>::~__WrapperPtr<WmiSecurity>(void)

- ea: `0x140006864`
- end: `0x140006869`
- name: `??1?$__WrapperPtr@VWmiSecurity@@@@UEAA@XZ`
- size: `5`
- prototype: `void **__fastcall(_QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400152c0`

## callees

- `0x140006820`

## pseudocode

```c
// attributes: thunk
void **__fastcall __WrapperPtr<WmiSecurity>::~__WrapperPtr<WmiSecurity>(_QWORD *a1, unsigned int a2)
{
  return __Wrapper<WmiSecurity>::~__Wrapper<WmiSecurity>(a1, a2);
}

```

## disassembly

```asm
0x140006864  jmp     ??1?$__Wrapper@VWmiSecurity@@@@UEAA@XZ; __Wrapper<WmiSecurity>::~__Wrapper<WmiSecurity>(void)
```
