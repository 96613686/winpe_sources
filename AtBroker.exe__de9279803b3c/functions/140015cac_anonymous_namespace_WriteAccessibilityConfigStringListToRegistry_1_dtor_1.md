# __anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry_::_1_::dtor$1

- ea: `0x140015cac`
- end: `0x140015cb8`
- name: `__anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003944`

## pseudocode

```c
void __fastcall _anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  ATL::CRegKey::~CRegKey((HKEY *)(a2 + 72));
}

```

## disassembly

```asm
0x140015cac  lea     rcx, [rdx+48h]; this
0x140015cb3  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
