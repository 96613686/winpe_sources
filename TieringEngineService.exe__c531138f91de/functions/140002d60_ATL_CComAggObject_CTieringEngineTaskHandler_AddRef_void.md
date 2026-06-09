# ATL::CComAggObject<CTieringEngineTaskHandler>::AddRef(void)

- ea: `0x140002d60`
- end: `0x140002d89`
- name: `?AddRef@?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140002d60`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CTieringEngineTaskHandler>::AddRef(__int64 a1)
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
0x140002d60  mov     r9d, 7FFFFFFFh
0x140002d66  jmp     short loc_140002D76
0x140002d68  lea     edx, [r8+1]
0x140002d6c  mov     eax, r8d
0x140002d6f  lock cmpxchg [rcx+8], edx
0x140002d74  jz      short loc_140002D81
0x140002d76  mov     r8d, [rcx+8]
0x140002d7a  cmp     r8d, r9d
0x140002d7d  jnz     short loc_140002D68
0x140002d7f  jmp     short loc_140002D85
0x140002d81  lea     r9d, [r8+1]
0x140002d85  mov     eax, r9d
0x140002d88  retn
```
