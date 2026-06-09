# MaxSecurityManager::AddRef(void)

- ea: `0x180009560`
- end: `0x18000956d`
- name: `?AddRef@MaxSecurityManager@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(MaxSecurityManager *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall MaxSecurityManager::AddRef(MaxSecurityManager *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180009560  mov     eax, 1
0x180009565  lock xadd [rcx+8], eax
0x18000956a  inc     eax
0x18000956c  retn
```
