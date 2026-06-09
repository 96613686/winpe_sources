# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x18000f460`
- end: `0x18000f482`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a600`
- `0x18000edf0`
- `0x18000ee90`
- `0x18000ef10`

## callees

- `0x18000f460`

## pseudocode

```c
__int64 __fastcall ATL::SafeDecrementReferenceMultiThread(volatile int *a1)
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
0x18000f460  mov     r9d, 7FFFFFFFh
0x18000f466  jmp     short loc_18000F475
0x18000f468  lea     edx, [r8-1]
0x18000f46c  mov     eax, r8d
0x18000f46f  lock cmpxchg [rcx], edx
0x18000f473  jz      short loc_18000F47D
0x18000f475  mov     r8d, [rcx]
0x18000f478  cmp     r8d, r9d
0x18000f47b  jnz     short loc_18000F468
0x18000f47d  lea     eax, [r8-1]
0x18000f481  retn
```
