# __anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry_::_1_::dtor$0

- ea: `0x140015f10`
- end: `0x140015f1c`
- name: `__anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000c2bc`

## pseudocode

```c
void __fastcall _anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  _Trace::~_Trace((_Trace *)(a2 + 56));
}

```

## disassembly

```asm
0x140015f10  lea     rcx, [rdx+38h]; this
0x140015f17  jmp     ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
```
