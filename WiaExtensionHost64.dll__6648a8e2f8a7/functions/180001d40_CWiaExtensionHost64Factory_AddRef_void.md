# CWiaExtensionHost64Factory::AddRef(void)

- ea: `0x180001d40`
- end: `0x180001d4d`
- name: `?AddRef@CWiaExtensionHost64Factory@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CWiaExtensionHost64Factory *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall CWiaExtensionHost64Factory::AddRef(CWiaExtensionHost64Factory *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180001d40  mov     eax, 1
0x180001d45  lock xadd [rcx+8], eax
0x180001d4a  inc     eax
0x180001d4c  retn
```
