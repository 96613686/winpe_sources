# CWMVideoDecMediaObject::AddRef(void)

- ea: `0x180025ca0`
- end: `0x180025cb3`
- name: `?AddRef@CWMVideoDecMediaObject@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b920`
- `0x18002b940`
- `0x18002b960`
- `0x18002b980`
- `0x18002b9a0`
- `0x18002b9c0`
- `0x18002b9e0`
- `0x18002ba00`
- `0x18002ba20`
- `0x18002ba40`
- `0x18002ba60`

## callees

- `0x180046010`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::AddRef(CWMVideoDecMediaObject *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 44) + 8LL))(*((_QWORD *)this + 44));
}

```

## disassembly

```asm
0x180025ca0  mov     rcx, [rcx+160h]
0x180025ca7  mov     rax, [rcx]
0x180025caa  mov     rax, [rax+8]
0x180025cae  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
