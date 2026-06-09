# CReadWriteSpinLock::_TryAcquireReaderLock(int)

- ea: `0x1400054c8`
- end: `0x1400054f5`
- name: `?_TryAcquireReaderLock@CReadWriteSpinLock@@AEAAHH@Z`
- size: `45`
- prototype: `__int64 __fastcall(CReadWriteSpinLock *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005294`
- `0x1400053dc`

## callees

- `0x1400054c8`

## pseudocode

```c
__int64 __fastcall CReadWriteSpinLock::_TryAcquireReaderLock(CReadWriteSpinLock *this, int a2)
{
  signed __int32 v2; // eax
  unsigned int v3; // r9d
  bool v4; // zf

  v2 = *(_DWORD *)this;
  v3 = 0;
  if ( *((_DWORD *)this + 1) )
    v4 = *((_DWORD *)this + 1) == a2;
  else
    v4 = (v2 & 0x3FFF0000) == 0;
  if ( !v4 )
    return 0;
  LOBYTE(v3) = v2 == _InterlockedCompareExchange((volatile signed __int32 *)this, v2 + 1, v2);
  return v3;
}

```

## disassembly

```asm
0x1400054c8  mov     eax, [rcx]
0x1400054ca  xor     r9d, r9d
0x1400054cd  mov     r8, rcx
0x1400054d0  cmp     [rcx+4], r9d
0x1400054d4  jnz     short loc_1400054DD
0x1400054d6  test    eax, 3FFF0000h
0x1400054db  jmp     short loc_1400054E0
0x1400054dd  cmp     [rcx+4], edx
0x1400054e0  jz      short loc_1400054E5
0x1400054e2  xor     eax, eax
0x1400054e4  retn
0x1400054e5  lea     ecx, [rax+1]
0x1400054e8  lock cmpxchg [r8], ecx
0x1400054ed  setz    r9b
0x1400054f1  mov     eax, r9d
0x1400054f4  retn
```
