# Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)

- ea: `0x140008960`
- end: `0x140008982`
- name: `?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, volatile int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008470`
- `0x1400084f0`
- `0x140008550`
- `0x1400085d0`

## callees

- `0x140008960`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::SafeUnknownDecrementReference(
        Microsoft::WRL::Details *this,
        volatile int *a2)
{
  signed __int32 v2; // r8d

  do
    v2 = *(_DWORD *)this;
  while ( *(_DWORD *)this != 0x7FFFFFFF
       && v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, v2 - 1, v2) );
  return (unsigned int)(v2 - 1);
}

```

## disassembly

```asm
0x140008960  mov     r9d, 7FFFFFFFh
0x140008966  jmp     short loc_140008975
0x140008968  lea     edx, [r8-1]
0x14000896c  mov     eax, r8d
0x14000896f  lock cmpxchg [rcx], edx
0x140008973  jz      short loc_14000897D
0x140008975  mov     r8d, [rcx]
0x140008978  cmp     r8d, r9d
0x14000897b  jnz     short loc_140008968
0x14000897d  lea     eax, [r8-1]
0x140008981  retn
```
