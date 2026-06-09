# _NDFAdapter::ConvertRepairsToNDF_::_1_::dtor$1

- ea: `0x18001100c`
- end: `0x180011018`
- name: `_NDFAdapter::ConvertRepairsToNDF_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000c3b4`

## pseudocode

```c
void __fastcall NDFAdapter::ConvertRepairsToNDF_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  FreeNDFRepairVisitor::~FreeNDFRepairVisitor((FreeNDFRepairVisitor *)(a2 + 40));
}

```

## disassembly

```asm
0x18001100c  lea     rcx, [rdx+28h]; this
0x180011013  jmp     ??1FreeNDFRepairVisitor@@UEAA@XZ; FreeNDFRepairVisitor::~FreeNDFRepairVisitor(void)
```
