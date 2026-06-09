# ATL::CComObject<CIdentityStore>::AddRef(void)

- ea: `0x18000df90`
- end: `0x18000dfb7`
- name: `?AddRef@?$CComObject@VCIdentityStore@@@ATL@@UEAAKXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010c90`
- `0x180010ca0`

## callees

- `0x18000df90`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIdentityStore>::AddRef(__int64 a1)
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
0x18000df90  mov     r9d, 7FFFFFFFh
0x18000df96  mov     r8d, [rcx+18h]
0x18000df9a  cmp     r8d, r9d
0x18000df9d  jnz     short loc_18000DFA3
0x18000df9f  mov     eax, r9d
0x18000dfa2  retn
0x18000dfa3  lea     edx, [r8+1]
0x18000dfa7  mov     eax, r8d
0x18000dfaa  lock cmpxchg [rcx+18h], edx
0x18000dfaf  jnz     short loc_18000DF96
0x18000dfb1  lea     r9d, [r8+1]
0x18000dfb5  jmp     short loc_18000DF9F
```
