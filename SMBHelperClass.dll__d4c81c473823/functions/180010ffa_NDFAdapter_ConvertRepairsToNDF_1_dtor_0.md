# _NDFAdapter::ConvertRepairsToNDF_::_1_::dtor$0

- ea: `0x180010ffa`
- end: `0x180011006`
- name: `_NDFAdapter::ConvertRepairsToNDF_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000c3b4`

## pseudocode

```c
void __fastcall NDFAdapter::ConvertRepairsToNDF_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  FreeNDFRepairVisitor::~FreeNDFRepairVisitor((FreeNDFRepairVisitor *)(a2 + 48));
}

```

## disassembly

```asm
0x180010ffa  lea     rcx, [rdx+30h]; this
0x180011001  jmp     ??1FreeNDFRepairVisitor@@UEAA@XZ; FreeNDFRepairVisitor::~FreeNDFRepairVisitor(void)
```
