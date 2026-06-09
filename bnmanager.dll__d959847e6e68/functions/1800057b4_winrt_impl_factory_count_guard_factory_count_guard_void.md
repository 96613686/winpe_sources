# winrt::impl::factory_count_guard::~factory_count_guard(void)

- ea: `0x1800057b4`
- end: `0x1800057bc`
- name: `??1factory_count_guard@impl@winrt@@QEAA@XZ`
- size: `8`
- prototype: `void __fastcall(volatile signed __int64 **this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cc19`
- `0x18000cc3d`
- `0x18000cc97`
- `0x18000cd32`
- `0x18000cd44`
- `0x18000cdbb`

## pseudocode

```c
void __fastcall winrt::impl::factory_count_guard::~factory_count_guard(volatile signed __int64 **this)
{
  _InterlockedDecrement64(*this);
}

```

## disassembly

```asm
0x1800057b4  mov     rax, [rcx]
0x1800057b7  lock dec qword ptr [rax]
0x1800057bb  retn
```
