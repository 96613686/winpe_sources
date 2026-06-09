# _CConfigSource::ProcessElement_::_1_::dtor$0

- ea: `0x180011c4f`
- end: `0x180011c5b`
- name: `_CConfigSource::ProcessElement_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cb5c`

## pseudocode

```c
void __fastcall CConfigSource::ProcessElement_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __1__unique_struct_U__co_array_t_PEAUIMVKey____P6AXPEAU1___E_1_FreeMvKeyArray__YAX0_Z__T_0A__wil__QEAA_XZ(a2 + 168);
}

```

## disassembly

```asm
0x180011c4f  lea     rcx, [rdx+0A8h]
0x180011c56  jmp     ??1?$unique_struct@U?$co_array_t@PEAUIMVKey@@@@P6AXPEAU1@@_E$1?FreeMvKeyArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ
```
