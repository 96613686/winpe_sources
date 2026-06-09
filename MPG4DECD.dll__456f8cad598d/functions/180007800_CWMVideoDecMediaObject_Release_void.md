# CWMVideoDecMediaObject::Release(void)

- ea: `0x180007800`
- end: `0x180007813`
- name: `?Release@CWMVideoDecMediaObject@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007820`
- `0x180007840`
- `0x180007860`
- `0x180007880`
- `0x1800078a0`

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
0x180007800  mov     rcx, [rcx+150h]
0x180007807  mov     rax, [rcx]
0x18000780a  mov     rax, [rax+10h]
0x18000780e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
