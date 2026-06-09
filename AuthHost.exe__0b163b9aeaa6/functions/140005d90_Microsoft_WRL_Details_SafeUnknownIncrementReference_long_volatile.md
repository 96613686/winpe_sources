# Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)

- ea: `0x140005d90`
- end: `0x140005db6`
- name: `?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `38`
- prototype: `unsigned int __fastcall(Microsoft::WRL::Details *__hidden this, volatile int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400049a0`
- `0x140007070`
- `0x140008aa0`
- `0x140009570`

## callees

- `0x140005d90`

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
0x140005d90  mov     r9d, 7FFFFFFFh
0x140005d96  jmp     short loc_140005DA5
0x140005d98  lea     edx, [r8+1]
0x140005d9c  mov     eax, r8d
0x140005d9f  lock cmpxchg [rcx], edx
0x140005da3  jz      short loc_140005DB1
0x140005da5  mov     r8d, [rcx]
0x140005da8  cmp     r8d, r9d
0x140005dab  jnz     short loc_140005D98
0x140005dad  mov     eax, r9d
0x140005db0  retn
0x140005db1  lea     eax, [r8+1]
0x140005db5  retn
```
