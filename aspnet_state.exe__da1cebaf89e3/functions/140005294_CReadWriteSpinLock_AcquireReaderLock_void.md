# CReadWriteSpinLock::AcquireReaderLock(void)

- ea: `0x140005294`
- end: `0x1400052d0`
- name: `?AcquireReaderLock@CReadWriteSpinLock@@QEAAXXZ`
- size: `60`
- prototype: `void __fastcall(CReadWriteSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004ab8`
- `0x140004b0c`

## callees

- `0x140005294`
- `0x1400053dc`
- `0x1400054c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400052a1`
- `KERNEL32!GetCurrentThreadId` at `0x1400052a1`

## pseudocode

```c
void __fastcall CReadWriteSpinLock::AcquireReaderLock(CReadWriteSpinLock *this)
{
  DWORD CurrentThreadId; // edi

  CurrentThreadId = GetCurrentThreadId();
  if ( !(unsigned int)CReadWriteSpinLock::_TryAcquireReaderLock(this, CurrentThreadId) )
    CReadWriteSpinLock::_Spin(this, 1, CurrentThreadId);
}

```

## disassembly

```asm
0x140005294  mov     [rsp+arg_0], rbx
0x140005299  push    rdi
0x14000529a  sub     rsp, 20h
0x14000529e  mov     rbx, rcx
0x1400052a1  call    cs:__imp_GetCurrentThreadId
0x1400052a7  mov     edx, eax; int
0x1400052a9  mov     rcx, rbx; this
0x1400052ac  mov     edi, eax
0x1400052ae  call    ?_TryAcquireReaderLock@CReadWriteSpinLock@@AEAAHH@Z; CReadWriteSpinLock::_TryAcquireReaderLock(int)
0x1400052b3  test    eax, eax
0x1400052b5  jnz     short loc_1400052C5
0x1400052b7  mov     r8d, edi; int
0x1400052ba  lea     edx, [rax+1]; int
0x1400052bd  mov     rcx, rbx; this
0x1400052c0  call    ?_Spin@CReadWriteSpinLock@@AEAAXHH@Z; CReadWriteSpinLock::_Spin(int,int)
0x1400052c5  mov     rbx, [rsp+28h+arg_0]
0x1400052ca  add     rsp, 20h
0x1400052ce  pop     rdi
0x1400052cf  retn
```
