# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x18000f488`
- end: `0x18000f4af`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800095a0`
- `0x1800095e0`
- `0x180009600`
- `0x18000a600`

## callees

- `0x18000f488`

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
0x18000f488  mov     r9d, 7FFFFFFFh
0x18000f48e  jmp     short loc_18000F49D
0x18000f490  lea     edx, [r8+1]
0x18000f494  mov     eax, r8d
0x18000f497  lock cmpxchg [rcx], edx
0x18000f49b  jz      short loc_18000F4A7
0x18000f49d  mov     r8d, [rcx]
0x18000f4a0  cmp     r8d, r9d
0x18000f4a3  jnz     short loc_18000F490
0x18000f4a5  jmp     short loc_18000F4AB
0x18000f4a7  lea     r9d, [r8+1]
0x18000f4ab  mov     eax, r9d
0x18000f4ae  retn
```
