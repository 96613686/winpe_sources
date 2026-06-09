# Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)

- ea: `0x180006270`
- end: `0x180006296`
- name: `?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, volatile int *)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002d60`
- `0x180002e00`
- `0x180002eb0`
- `0x180004320`
- `0x180004390`
- `0x1800043e0`
- `0x180004450`
- `0x180005090`
- `0x180009a00`

## callees

- `0x180006270`

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
0x180006270  mov     r9d, 7FFFFFFFh
0x180006276  jmp     short loc_180006285
0x180006278  lea     edx, [r8+1]
0x18000627c  mov     eax, r8d
0x18000627f  lock cmpxchg [rcx], edx
0x180006283  jz      short loc_180006291
0x180006285  mov     r8d, [rcx]
0x180006288  cmp     r8d, r9d
0x18000628b  jnz     short loc_180006278
0x18000628d  mov     eax, r9d
0x180006290  retn
0x180006291  lea     eax, [r8+1]
0x180006295  retn
```
