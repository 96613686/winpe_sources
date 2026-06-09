# NetSetup2::TransactionObject::~TransactionObject(void)

- ea: `0x18000d7d0`
- end: `0x18000d7d9`
- name: `??1TransactionObject@NetSetup2@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(NetSetup2::TransactionObject *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800129a9`
- `0x1800129bb`
- `0x1800129df`
- `0x180014172`

## callees

- `0x1800072d8`

## pseudocode

```c
void __fastcall NetSetup2::TransactionObject::~TransactionObject(NetSetup2::TransactionObject *this)
{
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete((char *)this + 8);
}

```

## disassembly

```asm
0x18000d7d0  add     rcx, 8
0x18000d7d4  jmp     ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
```
