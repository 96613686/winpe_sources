# ReadOnlyUserLanguagesRegistrar::~ReadOnlyUserLanguagesRegistrar(void)

- ea: `0x18001ec90`
- end: `0x18001ecb2`
- name: `??1ReadOnlyUserLanguagesRegistrar@@UEAA@XZ`
- size: `34`
- prototype: `void __fastcall(ReadOnlyUserLanguagesRegistrar *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001ec68`
- `0x18001ed80`

## callees

- `0x180020474`

## pseudocode

```c
void __fastcall ReadOnlyUserLanguagesRegistrar::~ReadOnlyUserLanguagesRegistrar(ReadOnlyUserLanguagesRegistrar *this)
{
  RegistryMultiStringValue::~RegistryMultiStringValue((ReadOnlyUserLanguagesRegistrar *)((char *)this + 8));
  *(_QWORD *)this = &IUserLanguagesRegistrar::`vftable';
}

```

## disassembly

```asm
0x18001ec90  push    rbx
0x18001ec92  sub     rsp, 20h
0x18001ec96  mov     rbx, rcx
0x18001ec99  add     rcx, 8; this
0x18001ec9d  call    ??1RegistryMultiStringValue@@UEAA@XZ; RegistryMultiStringValue::~RegistryMultiStringValue(void)
0x18001eca2  lea     rax, ??_7IUserLanguagesRegistrar@@6B@; const IUserLanguagesRegistrar::`vftable'
0x18001eca9  mov     [rbx], rax
0x18001ecac  add     rsp, 20h
0x18001ecb0  pop     rbx
0x18001ecb1  retn
```
