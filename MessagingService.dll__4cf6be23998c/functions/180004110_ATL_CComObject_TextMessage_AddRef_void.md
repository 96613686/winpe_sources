# ATL::CComObject<TextMessage>::AddRef(void)

- ea: `0x180004110`
- end: `0x180004139`
- name: `?AddRef@?$CComObject@VTextMessage@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004110`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TextMessage>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180004110  mov     r9d, 7FFFFFFFh
0x180004116  jmp     short loc_180004126
0x180004118  lea     edx, [r8+1]
0x18000411c  mov     eax, r8d
0x18000411f  lock cmpxchg [rcx+8], edx
0x180004124  jz      short loc_180004131
0x180004126  mov     r8d, [rcx+8]
0x18000412a  cmp     r8d, r9d
0x18000412d  jnz     short loc_180004118
0x18000412f  jmp     short loc_180004135
0x180004131  lea     r9d, [r8+1]
0x180004135  mov     eax, r9d
0x180004138  retn
```
