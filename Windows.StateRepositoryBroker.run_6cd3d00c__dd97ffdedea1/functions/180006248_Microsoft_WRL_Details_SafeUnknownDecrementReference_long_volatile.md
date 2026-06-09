# Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)

- ea: `0x180006248`
- end: `0x18000626a`
- name: `?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(Microsoft::WRL::Details *__hidden this, volatile int *)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005bb0`
- `0x180005c50`
- `0x180005cd0`
- `0x180005d70`
- `0x180005dd0`
- `0x180007290`
- `0x1800077e0`
- `0x18000a4a0`

## callees

- `0x180006248`

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
0x180006248  mov     r9d, 7FFFFFFFh
0x18000624e  jmp     short loc_18000625D
0x180006250  lea     edx, [r8-1]
0x180006254  mov     eax, r8d
0x180006257  lock cmpxchg [rcx], edx
0x18000625b  jz      short loc_180006265
0x18000625d  mov     r8d, [rcx]
0x180006260  cmp     r8d, r9d
0x180006263  jnz     short loc_180006250
0x180006265  lea     eax, [r8-1]
0x180006269  retn
```
