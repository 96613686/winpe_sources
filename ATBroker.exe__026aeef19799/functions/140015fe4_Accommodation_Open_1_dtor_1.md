# _Accommodation::Open_::_1_::dtor$1

- ea: `0x140015fe4`
- end: `0x140015ff0`
- name: `_Accommodation::Open_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003944`

## pseudocode

```c
void __fastcall Accommodation::Open_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 48));
}

```

## disassembly

```asm
0x140015fe4  lea     rcx, [rdx+30h]; this
0x140015feb  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
