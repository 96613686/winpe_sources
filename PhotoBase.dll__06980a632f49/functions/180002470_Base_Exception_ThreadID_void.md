# Base::Exception::ThreadID(void)

- ea: `0x180002470`
- end: `0x180002474`
- name: `?ThreadID@Exception@Base@@QEBAKXZ`
- size: `4`
- prototype: `unsigned int __fastcall(Base::Exception *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Base::Exception::ThreadID(Base::Exception *this)
{
  return *((unsigned int *)this + 3);
}

```

## disassembly

```asm
0x180002470  mov     eax, [rcx+0Ch]
0x180002473  retn
```
