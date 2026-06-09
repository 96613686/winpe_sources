# CProfileCache::AddRef(void)

- ea: `0x180006220`
- end: `0x18000622d`
- name: `?AddRef@CProfileCache@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CProfileCache *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CProfileCache::AddRef(CProfileCache *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 18);
}

```

## disassembly

```asm
0x180006220  mov     eax, 1
0x180006225  lock xadd [rcx+48h], eax
0x18000622a  inc     eax
0x18000622c  retn
```
