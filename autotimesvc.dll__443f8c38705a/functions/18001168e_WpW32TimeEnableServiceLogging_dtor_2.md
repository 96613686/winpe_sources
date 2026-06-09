# WpW32TimeEnableServiceLogging$dtor$2

- ea: `0x18001168e`
- end: `0x18001169a`
- name: `WpW32TimeEnableServiceLogging$dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000dfa8`

## pseudocode

```c
void __fastcall WpW32TimeEnableServiceLogging_dtor_2(__int64 a1, __int64 a2)
{
  RegKey::~RegKey((RegKey *)(a2 + 40));
}

```

## disassembly

```asm
0x18001168e  lea     rcx, [rdx+28h]; this
0x180011695  jmp     ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
```
