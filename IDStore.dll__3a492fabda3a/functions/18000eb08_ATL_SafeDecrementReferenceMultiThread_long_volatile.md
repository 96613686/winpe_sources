# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x18000eb08`
- end: `0x18000eb2a`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e330`
- `0x180011a60`

## callees

- `0x18000eb08`

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
0x18000eb08  mov     r9d, 7FFFFFFFh
0x18000eb0e  jmp     short loc_18000EB1D
0x18000eb10  lea     edx, [r8-1]
0x18000eb14  mov     eax, r8d
0x18000eb17  lock cmpxchg [rcx], edx
0x18000eb1b  jz      short loc_18000EB25
0x18000eb1d  mov     r8d, [rcx]
0x18000eb20  cmp     r8d, r9d
0x18000eb23  jnz     short loc_18000EB10
0x18000eb25  lea     eax, [r8-1]
0x18000eb29  retn
```
