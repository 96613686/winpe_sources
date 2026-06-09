# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x14000a258`
- end: `0x14000a27f`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004550`
- `0x1400045b0`
- `0x1400045d0`
- `0x140005818`
- `0x140005944`
- `0x140005c6c`

## callees

- `0x14000a258`

## pseudocode

```c
__int64 __fastcall ATL::SafeIncrementReferenceMultiThread(volatile int *a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *a1;
    if ( *a1 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange(a1, v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x14000a258  mov     r9d, 7FFFFFFFh
0x14000a25e  jmp     short loc_14000A26D
0x14000a260  lea     edx, [r8+1]
0x14000a264  mov     eax, r8d
0x14000a267  lock cmpxchg [rcx], edx
0x14000a26b  jz      short loc_14000A277
0x14000a26d  mov     r8d, [rcx]
0x14000a270  cmp     r8d, r9d
0x14000a273  jnz     short loc_14000A260
0x14000a275  jmp     short loc_14000A27B
0x14000a277  lea     r9d, [r8+1]
0x14000a27b  mov     eax, r9d
0x14000a27e  retn
```
