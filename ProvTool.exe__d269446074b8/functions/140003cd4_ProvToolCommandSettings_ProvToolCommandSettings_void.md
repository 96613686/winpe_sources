# _ProvToolCommandSettings::~_ProvToolCommandSettings(void)

- ea: `0x140003cd4`
- end: `0x140003cdd`
- name: `??1_ProvToolCommandSettings@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(_ProvToolCommandSettings *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e2f4`

## callees

- `0x140003a0c`

## pseudocode

```c
void __fastcall _ProvToolCommandSettings::~_ProvToolCommandSettings(_ProvToolCommandSettings *this)
{
  std::vector<std::wstring>::_Tidy((char *)this + 96);
}

```

## disassembly

```asm
0x140003cd4  add     rcx, 60h ; '`'
0x140003cd8  jmp     ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
```
