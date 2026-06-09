# _PolicyModel::CFileHashCondition::Deserialize_::_1_::dtor$1

- ea: `0x140014b60`
- end: `0x140014b6c`
- name: `_PolicyModel::CFileHashCondition::Deserialize_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14001377c`

## pseudocode

```c
void __fastcall PolicyModel::CFileHashCondition::Deserialize_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Sharp::Util::Xml::CNodeCollection::~CNodeCollection((Sharp::Util::Xml::CNodeCollection *)(a2 + 48));
}

```

## disassembly

```asm
0x140014b60  lea     rcx, [rdx+30h]; this
0x140014b67  jmp     ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
```
