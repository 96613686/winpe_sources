# NetSetup2::Aggregate::ConfigurationPath_Value::~ConfigurationPath_Value(void)

- ea: `0x18000d79c`
- end: `0x18000d7aa`
- name: `??1ConfigurationPath_Value@Aggregate@NetSetup2@@QEAA@XZ`
- size: `14`
- prototype: `void __fastcall(NetSetup2::Aggregate::ConfigurationPath_Value *this, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180014184`
- `0x1800141f2`

## callees

- `0x180007274`

## pseudocode

```c
void __fastcall NetSetup2::Aggregate::ConfigurationPath_Value::~ConfigurationPath_Value(
        NetSetup2::Aggregate::ConfigurationPath_Value *this,
        __int64 a2)
{
  LOBYTE(a2) = 1;
  std::wstring::_Tidy((char *)this + 8, a2, 0);
}

```

## disassembly

```asm
0x18000d79c  add     rcx, 8
0x18000d7a0  xor     r8d, r8d
0x18000d7a3  mov     dl, 1
0x18000d7a5  jmp     ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
