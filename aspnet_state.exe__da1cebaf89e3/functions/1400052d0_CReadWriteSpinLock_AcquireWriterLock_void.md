# CReadWriteSpinLock::AcquireWriterLock(void)

- ea: `0x1400052d0`
- end: `0x140005311`
- name: `?AcquireWriterLock@CReadWriteSpinLock@@QEAAXXZ`
- size: `65`
- prototype: `void __fastcall(CReadWriteSpinLock *__hidden this)`
- caller_count: `9`
- callee_count: `3`
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

- `0x1400052d0`
- `0x1400053dc`
- `0x1400054f8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400052dd`
- `KERNEL32!GetCurrentThreadId` at `0x1400052dd`

## pseudocode

```c
void __fastcall CReadWriteSpinLock::AcquireWriterLock(CReadWriteSpinLock *this)
{
  DWORD CurrentThreadId; // edi

  CurrentThreadId = GetCurrentThreadId();
  if ( !(unsigned int)CReadWriteSpinLock::_TryAcquireWriterLock(this, CurrentThreadId, 1) )
    CReadWriteSpinLock::_Spin(this, 0, CurrentThreadId);
}

```

## disassembly

```asm
0x1400052d0  mov     [rsp+arg_0], rbx
0x1400052d5  push    rdi
0x1400052d6  sub     rsp, 20h
0x1400052da  mov     rbx, rcx
0x1400052dd  call    cs:__imp_GetCurrentThreadId
0x1400052e3  mov     r8d, 1; int
0x1400052e9  mov     rcx, rbx; this
0x1400052ec  mov     edx, eax; int
0x1400052ee  mov     edi, eax
0x1400052f0  call    ?_TryAcquireWriterLock@CReadWriteSpinLock@@AEAAHHH@Z; CReadWriteSpinLock::_TryAcquireWriterLock(int,int)
0x1400052f5  test    eax, eax
0x1400052f7  jnz     short loc_140005306
0x1400052f9  mov     r8d, edi; int
0x1400052fc  xor     edx, edx; int
0x1400052fe  mov     rcx, rbx; this
0x140005301  call    ?_Spin@CReadWriteSpinLock@@AEAAXHH@Z; CReadWriteSpinLock::_Spin(int,int)
0x140005306  mov     rbx, [rsp+28h+arg_0]
0x14000530b  add     rsp, 20h
0x14000530f  pop     rdi
0x140005310  retn
```
