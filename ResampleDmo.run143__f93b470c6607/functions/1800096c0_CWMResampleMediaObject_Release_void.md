# CWMResampleMediaObject::Release(void)

- ea: `0x1800096c0`
- end: `0x1800096d0`
- name: `?Release@CWMResampleMediaObject@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CWMResampleMediaObject *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18006b780`
- `0x18006b790`
- `0x18006b7b0`
- `0x18006b7d0`
- `0x18006b7f0`
- `0x180081ab0`
- `0x180081ad0`
- `0x180081af0`
- `0x180081b10`

## callees

- `0x180085010`

## pseudocode

```c
__int64 __fastcall CWMResampleMediaObject::Release(CWMResampleMediaObject *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this - 2) + 16LL))(*((_QWORD *)this - 2));
}

```

## disassembly

```asm
0x1800096c0  mov     rcx, [rcx-10h]
0x1800096c4  mov     rax, [rcx]
0x1800096c7  mov     rax, [rax+10h]
0x1800096cb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
