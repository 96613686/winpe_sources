# _StartList::GetTempValue_::_1_::dtor$0

- ea: `0x140015cf4`
- end: `0x140015d00`
- name: `_StartList::GetTempValue_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000bdf4`

## pseudocode

```c
void __fastcall StartList::GetTempValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATManager::~ATManager((ATManager *)(a2 + 48));
}

```

## disassembly

```asm
0x140015cf4  lea     rcx, [rdx+30h]; this
0x140015cfb  jmp     ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
```
