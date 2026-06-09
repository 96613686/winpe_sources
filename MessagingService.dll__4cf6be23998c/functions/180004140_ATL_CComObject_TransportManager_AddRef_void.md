# ATL::CComObject<TransportManager>::AddRef(void)

- ea: `0x180004140`
- end: `0x180004169`
- name: `?AddRef@?$CComObject@VTransportManager@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004170`
- `0x180004180`

## callees

- `0x180004140`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TransportManager>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 24);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180004140  mov     r9d, 7FFFFFFFh
0x180004146  jmp     short loc_180004156
0x180004148  lea     edx, [r8+1]
0x18000414c  mov     eax, r8d
0x18000414f  lock cmpxchg [rcx+18h], edx
0x180004154  jz      short loc_180004161
0x180004156  mov     r8d, [rcx+18h]
0x18000415a  cmp     r8d, r9d
0x18000415d  jnz     short loc_180004148
0x18000415f  jmp     short loc_180004165
0x180004161  lea     r9d, [r8+1]
0x180004165  mov     eax, r9d
0x180004168  retn
```
