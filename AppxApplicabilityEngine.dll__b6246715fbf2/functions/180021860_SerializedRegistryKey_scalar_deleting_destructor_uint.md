# SerializedRegistryKey::`scalar deleting destructor'(uint)

- ea: `0x180021860`
- end: `0x180021890`
- name: `??_GSerializedRegistryKey@@UEAAPEAXI@Z`
- size: `48`
- prototype: `SerializedRegistryKey *__fastcall(SerializedRegistryKey *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x18002180c`
- `0x180021860`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002187c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002187c`

## pseudocode

```c
SerializedRegistryKey *__fastcall SerializedRegistryKey::`scalar deleting destructor'(
        SerializedRegistryKey *this,
        char a2)
{
  SerializedRegistryKey::~SerializedRegistryKey(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180021860  mov     [rsp+arg_0], rbx
0x180021865  push    rdi
0x180021866  sub     rsp, 20h
0x18002186a  mov     ebx, edx
0x18002186c  mov     rdi, rcx
0x18002186f  call    ??1SerializedRegistryKey@@UEAA@XZ; SerializedRegistryKey::~SerializedRegistryKey(void)
0x180021874  test    bl, 1
0x180021877  jz      short loc_180021882
0x180021879  mov     rcx, rdi
0x18002187c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180021882  mov     rbx, [rsp+28h+arg_0]
0x180021887  mov     rax, rdi
0x18002188a  add     rsp, 20h
0x18002188e  pop     rdi
0x18002188f  retn
```
