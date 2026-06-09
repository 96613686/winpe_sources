# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180009104`
- end: `0x180009126`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001eb0`

## callees

- `0x180009104`

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
0x180009104  mov     r9d, 7FFFFFFFh
0x18000910a  jmp     short loc_180009119
0x18000910c  lea     edx, [r8-1]
0x180009110  mov     eax, r8d
0x180009113  lock cmpxchg [rcx], edx
0x180009117  jz      short loc_180009121
0x180009119  mov     r8d, [rcx]
0x18000911c  cmp     r8d, r9d
0x18000911f  jnz     short loc_18000910C
0x180009121  lea     eax, [r8-1]
0x180009125  retn
```
