# CDMOSA::RemoveListener(void)

- ea: `0x180081b20`
- end: `0x180081b27`
- name: `?RemoveListener@CDMOSA@@UEAAJXZ`
- size: `7`
- prototype: `__int64 __fastcall(CDMOSA *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CDMOSA::RemoveListener(CDMOSA *this)
{
  _InterlockedDecrement((volatile signed __int32 *)this + 2);
  return 0;
}

```

## disassembly

```asm
0x180081b20  lock dec dword ptr [rcx+8]
0x180081b24  xor     eax, eax
0x180081b26  retn
```
