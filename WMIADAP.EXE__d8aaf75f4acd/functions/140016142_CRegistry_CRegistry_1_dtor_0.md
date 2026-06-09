# _CRegistry::_CRegistry_::_1_::dtor$0

- ea: `0x140016142`
- end: `0x140016152`
- name: `_CRegistry::_CRegistry_::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistry::_CRegistry_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(*(_QWORD *)(a2 + 48) + 24LL));
}

```

## disassembly

```asm
0x140016142  mov     rcx, [rdx+30h]
0x140016149  add     rcx, 18h; this
0x14001614d  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
