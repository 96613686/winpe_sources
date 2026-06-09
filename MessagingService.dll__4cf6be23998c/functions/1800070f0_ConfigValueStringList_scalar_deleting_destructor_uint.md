# ConfigValueStringList::`scalar deleting destructor'(uint)

- ea: `0x1800070f0`
- end: `0x180007120`
- name: `??_GConfigValueStringList@@UEAAPEAXI@Z`
- size: `48`
- prototype: `ConfigValueStringList *__fastcall(ConfigValueStringList *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x18000707c`
- `0x1800070f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000710c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000710c`

## pseudocode

```c
ConfigValueStringList *__fastcall ConfigValueStringList::`scalar deleting destructor'(
        ConfigValueStringList *this,
        char a2)
{
  ConfigValueStringList::~ConfigValueStringList(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800070f0  mov     [rsp+arg_0], rbx
0x1800070f5  push    rdi
0x1800070f6  sub     rsp, 20h
0x1800070fa  mov     ebx, edx
0x1800070fc  mov     rdi, rcx
0x1800070ff  call    ??1ConfigValueStringList@@UEAA@XZ; ConfigValueStringList::~ConfigValueStringList(void)
0x180007104  test    bl, 1
0x180007107  jz      short loc_180007112
0x180007109  mov     rcx, rdi
0x18000710c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007112  mov     rbx, [rsp+28h+arg_0]
0x180007117  mov     rax, rdi
0x18000711a  add     rsp, 20h
0x18000711e  pop     rdi
0x18000711f  retn
```
