# TerminateExtension$dtor$0

- ea: `0x18000fc88`
- end: `0x18000fc94`
- name: `TerminateExtension$dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800039dc`

## pseudocode

```c
void __fastcall TerminateExtension_dtor_0(__int64 a1, __int64 a2)
{
  CSW::~CSW((CSW *)(a2 + 56));
}

```

## disassembly

```asm
0x18000fc88  lea     rcx, [rdx+38h]; this
0x18000fc8f  jmp     ??1CSW@@QEAA@XZ; CSW::~CSW(void)
```
