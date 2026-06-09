# SID_MAPPER::AddRef(void)

- ea: `0x180002310`
- end: `0x18000231d`
- name: `?AddRef@SID_MAPPER@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(SID_MAPPER *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
__int64 __fastcall SID_MAPPER::AddRef(SID_MAPPER *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 5);
}

```

## disassembly

```asm
0x180002310  mov     eax, 1
0x180002315  lock xadd [rcx+14h], eax
0x18000231a  inc     eax
0x18000231c  retn
```
