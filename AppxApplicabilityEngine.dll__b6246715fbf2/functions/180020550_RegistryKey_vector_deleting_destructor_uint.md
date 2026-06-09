# RegistryKey::`vector deleting destructor'(uint)

- ea: `0x180020550`
- end: `0x180020580`
- name: `??_ERegistryKey@@UEAAPEAXI@Z`
- size: `48`
- prototype: `RegistryKey *__fastcall(RegistryKey *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180020424`
- `0x180020550`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002056c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002056c`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::`vector deleting destructor'(RegistryKey *this, char a2)
{
  RegistryKey::~RegistryKey(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180020550  mov     [rsp+arg_0], rbx
0x180020555  push    rdi
0x180020556  sub     rsp, 20h
0x18002055a  mov     ebx, edx
0x18002055c  mov     rdi, rcx
0x18002055f  call    ??1RegistryKey@@UEAA@XZ; RegistryKey::~RegistryKey(void)
0x180020564  test    bl, 1
0x180020567  jz      short loc_180020572
0x180020569  mov     rcx, rdi
0x18002056c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020572  mov     rbx, [rsp+28h+arg_0]
0x180020577  mov     rax, rdi
0x18002057a  add     rsp, 20h
0x18002057e  pop     rdi
0x18002057f  retn
```
