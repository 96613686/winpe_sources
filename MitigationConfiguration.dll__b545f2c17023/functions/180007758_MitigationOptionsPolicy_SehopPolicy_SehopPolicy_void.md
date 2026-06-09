# MitigationOptionsPolicy::SehopPolicy::~SehopPolicy(void)

- ea: `0x180007758`
- end: `0x180007761`
- name: `??1SehopPolicy@MitigationOptionsPolicy@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(char **this)`
- caller_count: `32`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180013c1c`
- `0x180013c32`
- `0x180013c4b`
- `0x180013c64`
- `0x180013c7d`
- `0x180013c96`
- `0x180013caf`
- `0x180013cc8`
- `0x180013ce1`
- `0x180013cfa`
- `0x180013d13`
- `0x180013d2c`
- `0x180013d45`
- `0x180013d5e`
- `0x180013d77`
- `0x180013d90`
- `0x180013dbb`
- `0x180013dd1`
- `0x180013dea`
- `0x180013e03`
- `0x180013e1c`
- `0x180013e35`
- `0x180013e4e`
- `0x180013e67`
- `0x180013e80`
- `0x180013e99`
- `0x180013eb2`
- `0x180013ecb`
- `0x180013ee4`
- `0x180013efd`
- `0x180013f16`
- `0x180013f2f`

## callees

- `0x1800076b4`

## pseudocode

```c
void __fastcall MitigationOptionsPolicy::SehopPolicy::~SehopPolicy(char **this)
{
  std::wstring::~wstring(this + 1);
}

```

## disassembly

```asm
0x180007758  add     rcx, 8
0x18000775c  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
