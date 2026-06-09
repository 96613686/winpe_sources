# Completion::AddRef(void)

- ea: `0x140005710`
- end: `0x14000571d`
- name: `?AddRef@Completion@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(Completion *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall Completion::AddRef(Completion *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 12);
}

```

## disassembly

```asm
0x140005710  mov     eax, 1
0x140005715  lock xadd [rcx+30h], eax
0x14000571a  inc     eax
0x14000571c  retn
```
