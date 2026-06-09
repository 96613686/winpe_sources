# CReadWriteSpinLock::ReleaseWriterLock(void)

- ea: `0x140005374`
- end: `0x140005391`
- name: `?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ`
- size: `29`
- prototype: `void __fastcall(CReadWriteSpinLock *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140001994`
- `0x140001a20`
- `0x140002d6c`
- `0x140003260`
- `0x1400038ec`
- `0x1400039c8`
- `0x140003dec`
- `0x140004784`
- `0x140004d3c`

## callees

- `0x140005314`
- `0x140005374`

## pseudocode

```c
void __fastcall CReadWriteSpinLock::ReleaseWriterLock(CReadWriteSpinLock *this)
{
  if ( (*(_DWORD *)this & 0x3FFF0000) == 0x10000 )
    *((_DWORD *)this + 1) = 0;
  CReadWriteSpinLock::AlterWriteCountHoldingWriterLock(this, *(_DWORD *)this, -1);
}

```

## disassembly

```asm
0x140005374  mov     eax, [rcx]
0x140005376  and     eax, 3FFF0000h
0x14000537b  cmp     eax, 10000h
0x140005380  jnz     short loc_140005386
0x140005382  and     dword ptr [rcx+4], 0
0x140005386  mov     edx, [rcx]; int
0x140005388  or      r8d, 0FFFFFFFFh; int
0x14000538c  jmp     ?AlterWriteCountHoldingWriterLock@CReadWriteSpinLock@@AEAAXHH@Z; CReadWriteSpinLock::AlterWriteCountHoldingWriterLock(int,int)
```
