# Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)

- ea: `0x140008988`
- end: `0x1400089ae`
- name: `?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, volatile int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400078f0`
- `0x140007940`
- `0x140007950`

## callees

- `0x140008988`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::SafeUnknownIncrementReference(
        Microsoft::WRL::Details *this,
        volatile int *a2)
{
  signed __int32 v2; // r8d

  do
  {
    v2 = *(_DWORD *)this;
    if ( *(_DWORD *)this == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, v2 + 1, v2) );
  return (unsigned int)(v2 + 1);
}

```

## disassembly

```asm
0x140008988  mov     r9d, 7FFFFFFFh
0x14000898e  jmp     short loc_14000899D
0x140008990  lea     edx, [r8+1]
0x140008994  mov     eax, r8d
0x140008997  lock cmpxchg [rcx], edx
0x14000899b  jz      short loc_1400089A9
0x14000899d  mov     r8d, [rcx]
0x1400089a0  cmp     r8d, r9d
0x1400089a3  jnz     short loc_140008990
0x1400089a5  mov     eax, r9d
0x1400089a8  retn
0x1400089a9  lea     eax, [r8+1]
0x1400089ad  retn
```
