# PrecacheStoreLicenseForPackageResume2$dtor$3

- ea: `0x1800122c9`
- end: `0x1800122d5`
- name: `PrecacheStoreLicenseForPackageResume2$dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006cb4`

## pseudocode

```c
void __fastcall PrecacheStoreLicenseForPackageResume2_dtor_3(__int64 a1, __int64 a2)
{
  OverrideImpersonationScope::~OverrideImpersonationScope((OverrideImpersonationScope *)(a2 + 160));
}

```

## disassembly

```asm
0x1800122c9  lea     rcx, [rdx+0A0h]; this
0x1800122d0  jmp     ??1OverrideImpersonationScope@@QEAA@XZ; OverrideImpersonationScope::~OverrideImpersonationScope(void)
```
