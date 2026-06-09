# CWMVideoDecMediaObject::Release(void)

- ea: `0x180025f60`
- end: `0x180025f73`
- name: `?Release@CWMVideoDecMediaObject@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18002da30`
- `0x18002da50`
- `0x18002da70`
- `0x18002da90`
- `0x18002dab0`
- `0x18002dad0`
- `0x18002daf0`
- `0x18002db10`
- `0x18002db30`
- `0x18002db50`
- `0x18002db70`

## callees

- `0x180046010`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::Release(CWMVideoDecMediaObject *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 44) + 16LL))(*((_QWORD *)this + 44));
}

```

## disassembly

```asm
0x180025f60  mov     rcx, [rcx+160h]
0x180025f67  mov     rax, [rcx]
0x180025f6a  mov     rax, [rax+10h]
0x180025f6e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
