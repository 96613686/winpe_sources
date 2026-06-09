# CWMVideoDecMediaObject::Release(void)

- ea: `0x180007740`
- end: `0x180007753`
- name: `?Release@CWMVideoDecMediaObject@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007760`
- `0x180007780`
- `0x1800077a0`
- `0x1800077c0`
- `0x1800077e0`

## callees

- `0x180022010`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::Release(CWMVideoDecMediaObject *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 16LL))(*((_QWORD *)this + 42));
}

```

## disassembly

```asm
0x180007740  mov     rcx, [rcx+150h]
0x180007747  mov     rax, [rcx]
0x18000774a  mov     rax, [rax+10h]
0x18000774e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
