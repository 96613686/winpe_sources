# std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(PCLmWriter::IntegerNumberObject * const,std::_Ref_count_base * const)

- ea: `0x180010ff8`
- end: `0x180011000`
- name: `??$_Set_ptr_rep_and_enable_shared@VIntegerNumberObject@PCLmWriter@@@?$shared_ptr@$$CBVIntegerNumberObject@PCLmWriter@@@std@@AEAAXQEAVIntegerNumberObject@PCLmWriter@@QEAV_Ref_count_base@1@@Z`
- size: `8`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180012420`
- `0x180012580`
- `0x1800126b0`
- `0x180012740`
- `0x180012930`
- `0x1800129e0`

## pseudocode

```c
void __fastcall std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  *a1 = a2;
  a1[1] = a3;
}

```

## disassembly

```asm
0x180010ff8  mov     [rcx], rdx
0x180010ffb  mov     [rcx+8], r8
0x180010fff  retn
```
