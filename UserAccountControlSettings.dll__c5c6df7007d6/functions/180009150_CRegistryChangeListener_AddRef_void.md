# CRegistryChangeListener::AddRef(void)

- ea: `0x180009150`
- end: `0x18000915d`
- name: `?AddRef@CRegistryChangeListener@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CRegistryChangeListener *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180009170`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener::AddRef(CRegistryChangeListener *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 4);
}

```

## disassembly

```asm
0x180009150  mov     eax, 1
0x180009155  lock xadd [rcx+10h], eax
0x18000915a  inc     eax
0x18000915c  retn
```
