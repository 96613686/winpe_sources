# _SetNoShellADAPSwitch_::_1_::dtor$0

- ea: `0x18001e8ce`
- end: `0x18001e8dc`
- name: `_SetNoShellADAPSwitch_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001e8d5`

## pseudocode

```c
void __fastcall SetNoShellADAPSwitch_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 48));
}

```

## disassembly

```asm
0x18001e8ce  lea     rcx, [rdx+30h]
0x18001e8d5  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
