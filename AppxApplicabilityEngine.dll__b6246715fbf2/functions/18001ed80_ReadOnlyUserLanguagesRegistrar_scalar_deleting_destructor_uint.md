# ReadOnlyUserLanguagesRegistrar::`scalar deleting destructor'(uint)

- ea: `0x18001ed80`
- end: `0x18001edb0`
- name: `??_GReadOnlyUserLanguagesRegistrar@@UEAAPEAXI@Z`
- size: `48`
- prototype: `ReadOnlyUserLanguagesRegistrar *__fastcall(ReadOnlyUserLanguagesRegistrar *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001ec90`
- `0x18001ed80`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ed9c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ed9c`

## pseudocode

```c
ReadOnlyUserLanguagesRegistrar *__fastcall ReadOnlyUserLanguagesRegistrar::`scalar deleting destructor'(
        ReadOnlyUserLanguagesRegistrar *this,
        char a2)
{
  ReadOnlyUserLanguagesRegistrar::~ReadOnlyUserLanguagesRegistrar(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001ed80  mov     [rsp+arg_0], rbx
0x18001ed85  push    rdi
0x18001ed86  sub     rsp, 20h
0x18001ed8a  mov     ebx, edx
0x18001ed8c  mov     rdi, rcx
0x18001ed8f  call    ??1ReadOnlyUserLanguagesRegistrar@@UEAA@XZ; ReadOnlyUserLanguagesRegistrar::~ReadOnlyUserLanguagesRegistrar(void)
0x18001ed94  test    bl, 1
0x18001ed97  jz      short loc_18001EDA2
0x18001ed99  mov     rcx, rdi
0x18001ed9c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001eda2  mov     rbx, [rsp+28h+arg_0]
0x18001eda7  mov     rax, rdi
0x18001edaa  add     rsp, 20h
0x18001edae  pop     rdi
0x18001edaf  retn
```
