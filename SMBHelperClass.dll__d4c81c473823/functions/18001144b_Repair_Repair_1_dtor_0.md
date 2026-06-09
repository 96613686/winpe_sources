# _Repair::Repair_::_1_::dtor$0

- ea: `0x18001144b`
- end: `0x18001145b`
- name: `_Repair::Repair_::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000d4d8`

## pseudocode

```c
void __fastcall Repair::Repair_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AttributeList::~AttributeList((HANDLE *)(*(_QWORD *)(a2 + 48) + 8LL));
}

```

## disassembly

```asm
0x18001144b  mov     rcx, [rdx+30h]
0x180011452  add     rcx, 8; this
0x180011456  jmp     ??1AttributeList@@QEAA@XZ; AttributeList::~AttributeList(void)
```
