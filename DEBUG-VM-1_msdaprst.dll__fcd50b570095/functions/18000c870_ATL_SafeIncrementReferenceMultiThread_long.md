# ATL::SafeIncrementReferenceMultiThread(long *)

- ea: `0x18000c870`
- end: `0x18000c896`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPEAJ@Z`
- size: `38`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aac0`
- `0x180013ce0`
- `0x180018770`
- `0x180018850`
- `0x180018e60`

## callees

- `0x18000c870`

## pseudocode

```c
__int64 __fastcall ATL::SafeIncrementReferenceMultiThread(int *a1)
{
  signed __int32 v1; // r8d

  do
  {
    v1 = *a1;
    if ( *a1 == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  while ( v1 != _InterlockedCompareExchange(a1, v1 + 1, v1) );
  return (unsigned int)(v1 + 1);
}

```

## disassembly

```asm
0x18000c870  mov     r9d, 7FFFFFFFh
0x18000c876  jmp     short loc_18000C885
0x18000c878  lea     edx, [r8+1]
0x18000c87c  mov     eax, r8d
0x18000c87f  lock cmpxchg [rcx], edx
0x18000c883  jz      short loc_18000C891
0x18000c885  mov     r8d, [rcx]
0x18000c888  cmp     r8d, r9d
0x18000c88b  jnz     short loc_18000C878
0x18000c88d  mov     eax, r9d
0x18000c890  retn
0x18000c891  lea     eax, [r8+1]
0x18000c895  retn
```
