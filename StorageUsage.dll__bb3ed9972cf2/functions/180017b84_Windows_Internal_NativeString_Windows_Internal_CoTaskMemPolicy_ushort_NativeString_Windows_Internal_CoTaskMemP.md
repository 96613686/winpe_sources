# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x180017b84`
- end: `0x180017b89`
- name: `??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `5`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18002b7ae`
- `0x18002b7c0`
- `0x18002b874`
- `0x18002b886`
- `0x18002b8bc`
- `0x18002b8ce`

## callees

- `0x18001ebf4`

## pseudocode

```c
// attributes: thunk
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::~NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>()
{
  return Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free();
}

```

## disassembly

```asm
0x180017b84  jmp     ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
```
