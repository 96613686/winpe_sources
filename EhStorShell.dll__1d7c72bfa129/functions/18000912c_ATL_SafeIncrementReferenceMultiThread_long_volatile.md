# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x18000912c`
- end: `0x180009153`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003580`

## callees

- `0x18000912c`

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
0x18000912c  mov     r9d, 7FFFFFFFh
0x180009132  jmp     short loc_180009141
0x180009134  lea     edx, [r8+1]
0x180009138  mov     eax, r8d
0x18000913b  lock cmpxchg [rcx], edx
0x18000913f  jz      short loc_18000914B
0x180009141  mov     r8d, [rcx]
0x180009144  cmp     r8d, r9d
0x180009147  jnz     short loc_180009134
0x180009149  jmp     short loc_18000914F
0x18000914b  lea     r9d, [r8+1]
0x18000914f  mov     eax, r9d
0x180009152  retn
```
