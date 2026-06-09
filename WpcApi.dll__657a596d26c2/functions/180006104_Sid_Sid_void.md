# Sid::~Sid(void)

- ea: `0x180006104`
- end: `0x18000610d`
- name: `??1Sid@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(char **this)`
- caller_count: `13`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800291b1`
- `0x1800295f6`
- `0x180029649`
- `0x18002965b`
- `0x18002966d`
- `0x18002967f`
- `0x180029876`
- `0x1800299b0`
- `0x1800299e6`
- `0x180029dda`
- `0x180029f78`
- `0x18002ad98`
- `0x18002adce`

## callees

- `0x180005f9c`

## pseudocode

```c
void __fastcall Sid::~Sid(char **this)
{
  std::wstring::~wstring(this + 9);
}

```

## disassembly

```asm
0x180006104  add     rcx, 48h ; 'H'
0x180006108  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
