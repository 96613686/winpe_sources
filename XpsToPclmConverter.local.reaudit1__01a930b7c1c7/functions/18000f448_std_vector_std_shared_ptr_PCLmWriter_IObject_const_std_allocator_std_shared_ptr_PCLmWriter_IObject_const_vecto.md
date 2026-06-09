# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(void)

- ea: `0x18000f448`
- end: `0x18000f459`
- name: `??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ`
- size: `17`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180010290`
- `0x180014760`
- `0x180014a14`
- `0x1800152f4`
- `0x180015de4`
- `0x180016704`
- `0x180016cc8`
- `0x180016da4`
- `0x1800183d8`
- `0x18001a854`
- `0x18001b130`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x18000f448  xor     eax, eax
0x18000f44a  mov     [rcx], rax
0x18000f44d  mov     [rcx+8], rax
0x18000f451  mov     [rcx+10h], rax
0x18000f455  mov     rax, rcx
0x18000f458  retn
```
