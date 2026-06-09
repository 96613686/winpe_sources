# Settings::Read(void)

- ea: `0x18000f6a4`
- end: `0x18000f6d8`
- name: `?Read@Settings@@SA?AV?$shared_ptr@VSettings@@@std@@XZ`
- size: `52`
- prototype: `Settings **__fastcall(Settings **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000891c`

## callees

- `0x18000f540`
- `0x18000f6e0`

## pseudocode

```c
Settings **__fastcall Settings::Read(Settings **a1)
{
  std::make_shared<Settings,Settings::SharedHelper>(a1);
  Settings::ReadInt(*a1);
  return a1;
}

```

## disassembly

```asm
0x18000f6a4  mov     [rsp+arg_0], rcx
0x18000f6a9  push    rbx
0x18000f6aa  sub     rsp, 30h
0x18000f6ae  mov     rbx, rcx
0x18000f6b1  mov     [rsp+38h+var_18], 0
0x18000f6b9  call    ??$make_shared@VSettings@@USharedHelper@1@@std@@YA?AV?$shared_ptr@VSettings@@@0@$$QEAUSharedHelper@Settings@@@Z; std::make_shared<Settings,Settings::SharedHelper>(Settings::SharedHelper &&)
0x18000f6be  mov     [rsp+38h+var_18], 1
0x18000f6c6  mov     rcx, [rbx]; this
0x18000f6c9  call    ?ReadInt@Settings@@AEAAXXZ; Settings::ReadInt(void)
0x18000f6ce  mov     rax, rbx
0x18000f6d1  add     rsp, 30h
0x18000f6d5  pop     rbx
0x18000f6d6  retn
```
