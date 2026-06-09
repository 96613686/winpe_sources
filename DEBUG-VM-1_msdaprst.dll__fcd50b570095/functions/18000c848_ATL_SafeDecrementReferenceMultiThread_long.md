# ATL::SafeDecrementReferenceMultiThread(long *)

- ea: `0x18000c848`
- end: `0x18000c86a`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPEAJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `21`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c4f0`
- `0x18000c530`
- `0x18000c570`
- `0x18000c5b0`
- `0x18000c5f0`
- `0x18000c630`
- `0x18000c670`
- `0x18000c6b0`
- `0x18000c6f0`
- `0x18000c730`
- `0x18000c770`
- `0x18000c7d0`
- `0x180014e30`
- `0x180014e70`
- `0x180014ef0`
- `0x180014f30`
- `0x180018e60`
- `0x1800193b0`
- `0x1800194c0`
- `0x1800223b0`
- `0x1800223f0`

## callees

- `0x18000c848`

## pseudocode

```c
__int64 __fastcall ATL::SafeDecrementReferenceMultiThread(int *a1)
{
  signed __int32 v1; // r8d

  do
    v1 = *a1;
  while ( *a1 != 0x7FFFFFFF && v1 != _InterlockedCompareExchange(a1, v1 - 1, v1) );
  return (unsigned int)(v1 - 1);
}

```

## disassembly

```asm
0x18000c848  mov     r9d, 7FFFFFFFh
0x18000c84e  jmp     short loc_18000C85D
0x18000c850  lea     edx, [r8-1]
0x18000c854  mov     eax, r8d
0x18000c857  lock cmpxchg [rcx], edx
0x18000c85b  jz      short loc_18000C865
0x18000c85d  mov     r8d, [rcx]
0x18000c860  cmp     r8d, r9d
0x18000c863  jnz     short loc_18000C850
0x18000c865  lea     eax, [r8-1]
0x18000c869  retn
```
