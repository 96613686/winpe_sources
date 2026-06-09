# UserLanguageRegistryValue::`scalar deleting destructor'(uint)

- ea: `0x18001edc0`
- end: `0x18001edf0`
- name: `??_GUserLanguageRegistryValue@@UEAAPEAXI@Z`
- size: `48`
- prototype: `UserLanguageRegistryValue *__fastcall(UserLanguageRegistryValue *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x18001edc0`
- `0x180020474`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001eddc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eddc`

## pseudocode

```c
UserLanguageRegistryValue *__fastcall UserLanguageRegistryValue::`scalar deleting destructor'(
        UserLanguageRegistryValue *this,
        char a2)
{
  RegistryMultiStringValue::~RegistryMultiStringValue(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001edc0  mov     [rsp+arg_0], rbx
0x18001edc5  push    rdi
0x18001edc6  sub     rsp, 20h
0x18001edca  mov     ebx, edx
0x18001edcc  mov     rdi, rcx
0x18001edcf  call    ??1RegistryMultiStringValue@@UEAA@XZ; RegistryMultiStringValue::~RegistryMultiStringValue(void)
0x18001edd4  test    bl, 1
0x18001edd7  jz      short loc_18001EDE2
0x18001edd9  mov     rcx, rdi
0x18001eddc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ede2  mov     rbx, [rsp+28h+arg_0]
0x18001ede7  mov     rax, rdi
0x18001edea  add     rsp, 20h
0x18001edee  pop     rdi
0x18001edef  retn
```
