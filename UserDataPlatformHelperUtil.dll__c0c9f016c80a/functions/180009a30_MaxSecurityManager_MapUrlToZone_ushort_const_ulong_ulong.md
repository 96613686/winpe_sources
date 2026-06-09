# MaxSecurityManager::MapUrlToZone(ushort const *,ulong *,ulong)

- ea: `0x180009a30`
- end: `0x180009a36`
- name: `?MapUrlToZone@MaxSecurityManager@@UEAAJPEBGPEAKK@Z`
- size: `6`
- prototype: `__int64 __fastcall(MaxSecurityManager *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall MaxSecurityManager::MapUrlToZone(
        MaxSecurityManager *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  return 2148270097LL;
}

```

## disassembly

```asm
0x180009a30  mov     eax, 800C0011h
0x180009a35  retn
```
