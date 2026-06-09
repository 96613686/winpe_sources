# Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)

- ea: `0x14000cd88`
- end: `0x14000cdae`
- name: `?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `38`
- prototype: `unsigned int __fastcall(Microsoft::WRL::Details *__hidden this, volatile int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c514`
- `0x14000c7e0`
- `0x14000c840`
- `0x14000c930`

## callees

- `0x14000cd88`

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
0x14000cd88  mov     r9d, 7FFFFFFFh
0x14000cd8e  jmp     short loc_14000CD9D
0x14000cd90  lea     edx, [r8+1]
0x14000cd94  mov     eax, r8d
0x14000cd97  lock cmpxchg [rcx], edx
0x14000cd9b  jz      short loc_14000CDA9
0x14000cd9d  mov     r8d, [rcx]
0x14000cda0  cmp     r8d, r9d
0x14000cda3  jnz     short loc_14000CD90
0x14000cda5  mov     eax, r9d
0x14000cda8  retn
0x14000cda9  lea     eax, [r8+1]
0x14000cdad  retn
```
